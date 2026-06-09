# UtilGetNonElevationInfo(_WERSVC_NON_ELEVATION_INFO *)

- ea: `0x14001aaa4`
- end: `0x14001acd1`
- name: `?UtilGetNonElevationInfo@@YAJPEAU_WERSVC_NON_ELEVATION_INFO@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(struct _WERSVC_NON_ELEVATION_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14000a1ac`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x14000a6dc`
- `0x14000e318`
- `0x14000e340`
- `0x14001a608`
- `0x14001aaa4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001ab2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001ab2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ab97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001abf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ab97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001abf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ac9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ac9f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001abeb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001abeb`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14001ab85`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14001ab85`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001acad`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001acad`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x14001ac8c`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x14001ac8c`

## pseudocode

```c
__int64 __fastcall UtilGetNonElevationInfo(struct _WERSVC_NON_ELEVATION_INFO *a1)
{
  const void *v2; // rbx
  char *v3; // rdi
  signed int v4; // esi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  _OWORD *v9; // rax
  HANDLE Handle; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(Name, 0, 0x208u);
  v2 = 0;
  Handle = 0;
  v3 = 0;
  v4 = OpenPrivateNamespaceW(&Handle);
  if ( v4 >= 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v4 = StringCchPrintfW(Name, 0x104u, L"WerSvc\\WerSvcNonElevationInfoSectionName%d", CurrentProcessId);
    if ( v4 >= 0 )
    {
      v3 = (char *)OpenFileMappingW(4u, 0, Name);
      if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 55;
          goto LABEL_5;
        }
      }
      else
      {
        v9 = MapViewOfFile(v3, 4u, 0, 0, 0x18u);
        v2 = v9;
        if ( v9 )
        {
          if ( *(_DWORD *)v9 == 24 && *((_QWORD *)v9 + 1) && *((_QWORD *)v9 + 2) )
          {
            v4 = 0;
            *(_OWORD *)a1 = *v9;
            *((_QWORD *)a1 + 2) = *((_QWORD *)v9 + 2);
          }
          else
          {
            v4 = -2147024883;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
          }
        }
        else
        {
          v4 = GetLastError();
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 56;
            goto LABEL_5;
          }
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 54;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 53;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, (unsigned int)v4);
    }
  }
  if ( Handle )
    ClosePrivateNamespace(Handle, 1u);
  if ( (unsigned __int64)(v3 + 1) > 1 )
    CloseHandle(v3);
  if ( v2 )
    UnmapViewOfFile(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001aaa4  push    rbx
0x14001aaa6  push    rbp
0x14001aaa7  push    rsi
0x14001aaa8  push    rdi
0x14001aaa9  sub     rsp, 268h
0x14001aab0  mov     rax, cs:__security_cookie
0x14001aab7  xor     rax, rsp
0x14001aaba  mov     [rsp+288h+var_38], rax
0x14001aac2  mov     rbp, rcx
0x14001aac5  xor     edx, edx; Val
0x14001aac7  lea     rcx, [rsp+288h+Name]; void *
0x14001aacc  mov     r8d, 208h; Size
0x14001aad2  call    memset_0
0x14001aad7  xor     ebx, ebx
0x14001aad9  lea     rcx, [rsp+288h+Handle]; void **
0x14001aade  mov     [rsp+288h+Handle], rbx
0x14001aae3  xor     edi, edi
0x14001aae5  call    ?OpenPrivateNamespaceW@@YAJPEAPEAX@Z; OpenPrivateNamespaceW(void * *)
0x14001aaea  mov     esi, eax
0x14001aaec  test    eax, eax
0x14001aaee  jns     short loc_14001AB2C
0x14001aaf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aaf7  lea     rax, WPP_GLOBAL_Control
0x14001aafe  cmp     rcx, rax
0x14001ab01  jz      loc_14001AC7D
0x14001ab07  test    byte ptr [rcx+1Ch], 1
0x14001ab0b  jz      loc_14001AC7D
0x14001ab11  lea     edx, [rbx+35h]
0x14001ab14  mov     rcx, [rcx+10h]
0x14001ab18  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001ab1f  mov     r9d, esi
0x14001ab22  call    WPP_SF_d
0x14001ab27  jmp     loc_14001AC7D
0x14001ab2c  call    cs:__imp_GetCurrentProcessId
0x14001ab32  lea     r8, aWersvcWersvcno; "WerSvc\\WerSvcNonElevationInfoSectionNa"...
0x14001ab39  mov     edx, 104h; unsigned __int64
0x14001ab3e  mov     r9d, eax
0x14001ab41  lea     rcx, [rsp+288h+Name]; wchar_t *
0x14001ab46  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14001ab4b  mov     esi, eax
0x14001ab4d  test    eax, eax
0x14001ab4f  jns     short loc_14001AB79
0x14001ab51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab58  lea     rax, WPP_GLOBAL_Control
0x14001ab5f  cmp     rcx, rax
0x14001ab62  jz      loc_14001AC7D
0x14001ab68  test    byte ptr [rcx+1Ch], 1
0x14001ab6c  jz      loc_14001AC7D
0x14001ab72  mov     edx, 36h ; '6'
0x14001ab77  jmp     short loc_14001AB14
0x14001ab79  xor     edx, edx; bInheritHandle
0x14001ab7b  lea     r8, [rsp+288h+Name]; lpName
0x14001ab80  lea     esi, [rdx+4]
0x14001ab83  mov     ecx, esi; dwDesiredAccess
0x14001ab85  call    cs:__imp_OpenFileMappingW
0x14001ab8b  mov     rdi, rax
0x14001ab8e  inc     rax
0x14001ab91  cmp     rax, 1
0x14001ab95  ja      short loc_14001ABD7
0x14001ab97  call    cs:__imp_GetLastError
0x14001ab9d  mov     esi, eax
0x14001ab9f  test    eax, eax
0x14001aba1  jle     short loc_14001ABAC
0x14001aba3  movzx   esi, ax
0x14001aba6  or      esi, 80070000h
0x14001abac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abb3  lea     rax, WPP_GLOBAL_Control
0x14001abba  cmp     rcx, rax
0x14001abbd  jz      loc_14001AC7D
0x14001abc3  test    byte ptr [rcx+1Ch], 1
0x14001abc7  jz      loc_14001AC7D
0x14001abcd  mov     edx, 37h ; '7'
0x14001abd2  jmp     loc_14001AB14
0x14001abd7  xor     r9d, r9d; dwFileOffsetLow
0x14001abda  mov     [rsp+288h+dwNumberOfBytesToMap], 18h; dwNumberOfBytesToMap
0x14001abe3  xor     r8d, r8d; dwFileOffsetHigh
0x14001abe6  mov     edx, esi; dwDesiredAccess
0x14001abe8  mov     rcx, rdi; hFileMappingObject
0x14001abeb  call    cs:__imp_MapViewOfFile
0x14001abf1  mov     rbx, rax
0x14001abf4  test    rax, rax
0x14001abf7  jnz     short loc_14001AC22
0x14001abf9  call    cs:__imp_GetLastError
0x14001abff  mov     esi, eax
0x14001ac01  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac08  lea     rax, WPP_GLOBAL_Control
0x14001ac0f  cmp     rcx, rax
0x14001ac12  jz      short loc_14001AC7D
0x14001ac14  test    byte ptr [rcx+1Ch], 1
0x14001ac18  jz      short loc_14001AC7D
0x14001ac1a  lea     edx, [rbx+38h]
0x14001ac1d  jmp     loc_14001AB14
0x14001ac22  cmp     dword ptr [rax], 18h
0x14001ac25  jnz     short loc_14001AC4A
0x14001ac27  cmp     qword ptr [rax+8], 0
0x14001ac2c  jz      short loc_14001AC4A
0x14001ac2e  cmp     qword ptr [rax+10h], 0
0x14001ac33  jz      short loc_14001AC4A
0x14001ac35  movups  xmm0, xmmword ptr [rax]
0x14001ac38  xor     esi, esi
0x14001ac3a  movups  xmmword ptr [rbp+0], xmm0
0x14001ac3e  movsd   xmm1, qword ptr [rax+10h]
0x14001ac43  movsd   qword ptr [rbp+10h], xmm1
0x14001ac48  jmp     short loc_14001AC7D
0x14001ac4a  mov     esi, 8007000Dh
0x14001ac4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac56  lea     rax, WPP_GLOBAL_Control
0x14001ac5d  cmp     rcx, rax
0x14001ac60  jz      short loc_14001AC7D
0x14001ac62  test    byte ptr [rcx+1Ch], 1
0x14001ac66  jz      short loc_14001AC7D
0x14001ac68  mov     rcx, [rcx+10h]
0x14001ac6c  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001ac73  mov     edx, 39h ; '9'
0x14001ac78  call    WPP_SF_
0x14001ac7d  mov     rcx, [rsp+288h+Handle]; Handle
0x14001ac82  test    rcx, rcx
0x14001ac85  jz      short loc_14001AC92
0x14001ac87  mov     edx, 1; Flags
0x14001ac8c  call    cs:__imp_ClosePrivateNamespace
0x14001ac92  lea     rax, [rdi+1]
0x14001ac96  cmp     rax, 1
0x14001ac9a  jbe     short loc_14001ACA5
0x14001ac9c  mov     rcx, rdi; hObject
0x14001ac9f  call    cs:__imp_CloseHandle
0x14001aca5  test    rbx, rbx
0x14001aca8  jz      short loc_14001ACB3
0x14001acaa  mov     rcx, rbx; lpBaseAddress
0x14001acad  call    cs:__imp_UnmapViewOfFile
0x14001acb3  mov     eax, esi
0x14001acb5  mov     rcx, [rsp+288h+var_38]
0x14001acbd  xor     rcx, rsp; StackCookie
0x14001acc0  call    __security_check_cookie
0x14001acc5  add     rsp, 268h
0x14001accc  pop     rdi
0x14001accd  pop     rsi
0x14001acce  pop     rbp
0x14001accf  pop     rbx
0x14001acd0  retn
```
