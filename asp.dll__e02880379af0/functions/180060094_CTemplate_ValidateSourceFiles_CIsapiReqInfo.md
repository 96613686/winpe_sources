# CTemplate::ValidateSourceFiles(CIsapiReqInfo *)

- ea: `0x180060094`
- end: `0x1800602f7`
- name: `?ValidateSourceFiles@CTemplate@@QEAAHPEAVCIsapiReqInfo@@@Z`
- size: `611`
- prototype: `int(CTemplate *__hidden this, struct CIsapiReqInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800108d0`

## callees

- `0x1800033e8`
- `0x180003424`
- `0x180016b50`
- `0x180023dd0`
- `0x1800432d8`
- `0x180049124`
- `0x18005c1e0`
- `0x180060094`
- `0x180062418`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180060133`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180060133`
- `KERNEL32!CompareFileTime` at `0x1800601ac`
- `KERNEL32!CompareFileTime` at `0x1800601ac`
- `KERNEL32!CloseHandle` at `0x18006018a`
- `KERNEL32!CloseHandle` at `0x18006018a`
- `KERNEL32!GetTickCount` at `0x1800601c7`
- `KERNEL32!GetTickCount` at `0x1800601c7`
- `iisutil!PuDbgPrint` at `0x180060249`
- `iisutil!PuDbgPrint` at `0x180060249`

## string_xrefs

- `0x180060242`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x180060229`: `VALIDATE SOUCE FILES : Template is Invalid\n`
- `0x180060230`: `CTemplate::ValidateSourceFiles`

## pseudocode

```c
__int64 __fastcall CTemplate::ValidateSourceFiles(CTemplate *this, struct CIsapiReqInfo *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rax
  BOOL v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // rcx
  signed int FileAttributes; // edi
  __int64 v10; // rcx
  __int64 result; // rax
  __int64 v12; // r9
  const WCHAR *v13; // r8
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hToken; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+50h] [rbp-B0h] BYREF

  FileTime2 = 0;
  hToken = 0;
  v4 = 0;
  TokenHandle = 0;
  if ( *((_DWORD *)this + 74) )
  {
    while ( 1 )
    {
      v5 = *((_QWORD *)this + 34);
      v6 = 0;
      hToken = 0;
      TokenHandle = 0;
      v7 = *(_QWORD *)(v5 + 8LL * v4);
      if ( (*(_BYTE *)(v7 + 76) & 1) != 0
        && (int)CIsapiReqInfo::GetVirtualPathTokenW(a2, *(const unsigned __int16 **)v7, &hToken) >= 0 )
      {
        AspDoRevertHack(&TokenHandle);
        v6 = ImpersonateLoggedOnUser(hToken);
        if ( !v6 )
          AspUndoRevertHack(&TokenHandle);
      }
      v8 = *(_QWORD *)(*((_QWORD *)this + 34) + 8LL * v4);
      FileAttributes = AspGetFileAttributes(*(const unsigned __int16 **)(v8 + 8), *(void **)(v8 + 32), &FileTime2, 0, 0);
      if ( v6 )
        AspUndoRevertHack(&TokenHandle);
      v10 = (__int64)hToken;
      if ( hToken )
        CloseHandle(hToken);
      if ( FileAttributes < 0 )
        break;
      if ( CompareFileTime((const FILETIME *)(*(_QWORD *)(*((_QWORD *)this + 34) + 8LL * v4) + 80LL), &FileTime2) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
            6088,
            "CTemplate::ValidateSourceFiles",
            "VALIDATE SOUCE FILES : Template is Invalid\n");
        return 0;
      }
      if ( ++v4 >= *((_DWORD *)this + 74) )
        goto LABEL_13;
    }
    if ( FileAttributes != -2147024775 )
    {
      if ( (unsigned int)(FileAttributes + 2147024845) > 0x10
        || (v10 = 73997, !_bittest((const int *)&v10, FileAttributes + 2147024845)) )
      {
        if ( FileAttributes != -2147023665 )
          return 0;
      }
    }
    v14 = 0;
    CAspRegistryParams::GetDisableCachedResponseOnUNCAccessFailure((CAspRegistryParams *)v10, &v14);
    if ( !_InterlockedCompareExchange(&g_fUNCFailureLogged, 1, 0) )
    {
      v12 = -1;
      v13 = *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 34) + 8LL * v4) + 8LL);
      do
        ++v12;
      while ( v13[v12] );
      WstrToMBstrEx(MultiByteStr, 1024, v13, v12, *((_DWORD *)this + 100));
      MSG_Error(0xC00001F4, MultiByteStr, FileAttributes, 0);
    }
    if ( v14 )
      return 0;
    result = 1;
  }
  else
  {
LABEL_13:
    *((_DWORD *)this + 124) = GetTickCount();
    *((_DWORD *)this + 125) = dword_180079E20;
    result = 1;
  }
  *((_DWORD *)this + 123) = 0;
  return result;
}

```

## disassembly

```asm
0x180060094  mov     [rsp-8+arg_10], rbx
0x180060099  push    rbp
0x18006009a  push    rsi
0x18006009b  push    rdi
0x18006009c  push    r12
0x18006009e  push    r13
0x1800600a0  push    r14
0x1800600a2  push    r15
0x1800600a4  lea     rbp, [rsp-360h]
0x1800600ac  sub     rsp, 460h
0x1800600b3  mov     rax, cs:__security_cookie
0x1800600ba  xor     rax, rsp
0x1800600bd  mov     [rbp+390h+var_40], rax
0x1800600c4  xor     r13d, r13d
0x1800600c7  mov     rbx, rcx
0x1800600ca  mov     r12, rdx
0x1800600cd  mov     qword ptr [rsp+490h+FileTime2.dwLowDateTime], r13
0x1800600d2  mov     [rsp+490h+hToken], r13
0x1800600d7  mov     esi, r13d
0x1800600da  mov     [rsp+490h+TokenHandle], r13
0x1800600df  lea     ecx, [r13+1]
0x1800600e3  cmp     [rbx+128h], r13d
0x1800600ea  jbe     loc_1800601C7
0x1800600f0  mov     rax, [rbx+110h]
0x1800600f7  mov     r14d, r13d
0x1800600fa  mov     [rsp+490h+hToken], r13
0x1800600ff  mov     [rsp+490h+TokenHandle], r13
0x180060104  mov     r15d, esi
0x180060107  mov     rdx, [rax+r15*8]
0x18006010b  test    [rdx+4Ch], cl
0x18006010e  jz      short loc_18006014A
0x180060110  mov     rdx, [rdx]; unsigned __int16 *
0x180060113  lea     r8, [rsp+490h+hToken]; void **
0x180060118  mov     rcx, r12; this
0x18006011b  call    ?GetVirtualPathTokenW@CIsapiReqInfo@@QEAAJPEBGPEAPEAX@Z; CIsapiReqInfo::GetVirtualPathTokenW(ushort const *,void * *)
0x180060120  test    eax, eax
0x180060122  js      short loc_18006014A
0x180060124  lea     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x180060129  call    ?AspDoRevertHack@@YAXPEAPEAX@Z; AspDoRevertHack(void * *)
0x18006012e  mov     rcx, [rsp+490h+hToken]; hToken
0x180060133  call    cs:__imp_ImpersonateLoggedOnUser
0x180060139  mov     r14d, eax
0x18006013c  test    eax, eax
0x18006013e  jnz     short loc_18006014A
0x180060140  lea     rcx, [rsp+490h+TokenHandle]; void **
0x180060145  call    ?AspUndoRevertHack@@YAXPEAPEAX@Z; AspUndoRevertHack(void * *)
0x18006014a  mov     rcx, [rbx+110h]
0x180060151  lea     r8, [rsp+490h+FileTime2]; struct _FILETIME *
0x180060156  xor     r9d, r9d; unsigned int *
0x180060159  mov     qword ptr [rsp+490h+CodePage], r13; unsigned int *
0x18006015e  mov     rcx, [rcx+r15*8]
0x180060162  mov     rdx, [rcx+20h]; void *
0x180060166  mov     rcx, [rcx+8]; unsigned __int16 *
0x18006016a  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x18006016f  mov     edi, eax
0x180060171  test    r14d, r14d
0x180060174  jz      short loc_180060180
0x180060176  lea     rcx, [rsp+490h+TokenHandle]; void **
0x18006017b  call    ?AspUndoRevertHack@@YAXPEAPEAX@Z; AspUndoRevertHack(void * *)
0x180060180  mov     rcx, [rsp+490h+hToken]; hObject
0x180060185  test    rcx, rcx
0x180060188  jz      short loc_180060190
0x18006018a  call    cs:__imp_CloseHandle
0x180060190  test    edi, edi
0x180060192  js      loc_180060254
0x180060198  mov     rax, [rbx+110h]
0x18006019f  lea     rdx, [rsp+490h+FileTime2]; lpFileTime2
0x1800601a4  mov     rcx, [rax+r15*8]
0x1800601a8  add     rcx, 50h ; 'P'; lpFileTime1
0x1800601ac  call    cs:__imp_CompareFileTime
0x1800601b2  test    eax, eax
0x1800601b4  jnz     short loc_180060215
0x1800601b6  lea     ecx, [rax+1]
0x1800601b9  add     esi, ecx
0x1800601bb  cmp     esi, [rbx+128h]
0x1800601c1  jb      loc_1800600F0
0x1800601c7  call    cs:__imp_GetTickCount
0x1800601cd  mov     [rbx+1F0h], eax
0x1800601d3  mov     eax, cs:dword_180079E20
0x1800601d9  mov     [rbx+1F4h], eax
0x1800601df  mov     eax, 1
0x1800601e4  mov     [rbx+1ECh], r13d
0x1800601eb  mov     rcx, [rbp+390h+var_40]
0x1800601f2  xor     rcx, rsp; StackCookie
0x1800601f5  call    __security_check_cookie
0x1800601fa  mov     rbx, [rsp+490h+arg_10]
0x180060202  add     rsp, 460h
0x180060209  pop     r15
0x18006020b  pop     r14
0x18006020d  pop     r13
0x18006020f  pop     r12
0x180060211  pop     rdi
0x180060212  pop     rsi
0x180060213  pop     rbp
0x180060214  retn
0x180060215  test    byte ptr cs:g_dwDebugFlags, 3
0x18006021c  jz      loc_1800602E9
0x180060222  mov     rcx, cs:g_pDebug
0x180060229  lea     rax, aValidateSouceF; "VALIDATE SOUCE FILES : Template is Inva"...
0x180060230  lea     r9, aCtemplateValid; "CTemplate::ValidateSourceFiles"
0x180060237  mov     qword ptr [rsp+490h+CodePage], rax
0x18006023c  mov     r8d, 17C8h
0x180060242  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x180060249  call    cs:__imp_PuDbgPrint
0x18006024f  jmp     loc_1800602E9
0x180060254  cmp     edi, 80070079h
0x18006025a  jz      short loc_180060279
0x18006025c  lea     eax, [rdi+7FF8FFCDh]
0x180060262  cmp     eax, 10h
0x180060265  ja      short loc_180060271
0x180060267  mov     ecx, 1210Dh; this
0x18006026c  bt      ecx, eax
0x18006026f  jb      short loc_180060279
0x180060271  cmp     edi, 800704CFh
0x180060277  jnz     short loc_1800602E9
0x180060279  lea     rdx, [rsp+490h+var_460]; unsigned int *
0x18006027e  mov     [rsp+490h+var_460], r13d
0x180060283  call    ?GetDisableCachedResponseOnUNCAccessFailure@CAspRegistryParams@@QEAAJPEAK@Z; CAspRegistryParams::GetDisableCachedResponseOnUNCAccessFailure(ulong *)
0x180060288  xor     eax, eax
0x18006028a  lea     esi, [rax+1]
0x18006028d  lock cmpxchg cs:?g_fUNCFailureLogged@@3JA, esi; long g_fUNCFailureLogged
0x180060295  jnz     short loc_1800602E2
0x180060297  mov     rax, [rbx+110h]
0x18006029e  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800602a2  mov     rcx, [rax+r15*8]
0x1800602a6  mov     r8, [rcx+8]; lpWideCharStr
0x1800602aa  inc     r9; cchWideChar
0x1800602ad  cmp     [r8+r9*2], r13w
0x1800602b2  jnz     short loc_1800602AA
0x1800602b4  mov     eax, [rbx+190h]
0x1800602ba  lea     rcx, [rsp+490h+MultiByteStr]; lpMultiByteStr
0x1800602bf  mov     edx, 400h; cbMultiByte
0x1800602c4  mov     [rsp+490h+CodePage], eax; CodePage
0x1800602c8  call    ?WstrToMBstrEx@@YAIPEADHPEBGHI@Z; WstrToMBstrEx(char *,int,ushort const *,int,uint)
0x1800602cd  xor     r9d, r9d; unsigned int
0x1800602d0  lea     rdx, [rsp+490h+MultiByteStr]; Source
0x1800602d5  mov     r8d, edi; UINT
0x1800602d8  mov     ecx, 0C00001F4h; uID
0x1800602dd  call    ?MSG_Error@@YAXIPEBDIK@Z; MSG_Error(uint,char const *,uint,ulong)
0x1800602e2  cmp     [rsp+490h+var_460], r13d
0x1800602e7  jz      short loc_1800602F0
0x1800602e9  xor     eax, eax
0x1800602eb  jmp     loc_1800601EB
0x1800602f0  mov     eax, esi
0x1800602f2  jmp     loc_1800601E4
```
