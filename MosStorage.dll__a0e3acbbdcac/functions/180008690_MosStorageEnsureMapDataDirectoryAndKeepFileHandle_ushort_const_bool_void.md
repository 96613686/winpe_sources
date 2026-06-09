# MosStorageEnsureMapDataDirectoryAndKeepFileHandle(ushort const *,bool,void * *)

- ea: `0x180008690`
- end: `0x180008914`
- name: `?MosStorageEnsureMapDataDirectoryAndKeepFileHandle@@YAJPEBG_NPEAPEAX@Z`
- size: `644`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, char, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180008680`
- `0x180008920`
- `0x18000c060`

## callees

- `0x180008690`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008882`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008878`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008878`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008739`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008739`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800087d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800087d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000886a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000886a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800087f9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800087f9`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800086ea`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000877e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000883a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800088ac`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800086ea`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000877e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000883a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800088ac`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800086cd`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800086cd`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800088f7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800088f7`

## string_xrefs

- `0x1800086c3`: `MapsCache`
- `0x1800086e1`: `MosStorageEnsureMapDataDirectoryAndKeepFileHandle`
- `0x180008775`: `MosStorageEnsureMapDataDirectoryAndKeepFileHandle`
- `0x180008831`: `MosStorageEnsureMapDataDirectoryAndKeepFileHandle`
- `0x1800088a3`: `MosStorageEnsureMapDataDirectoryAndKeepFileHandle`

## pseudocode

```c
__int64 __fastcall MosStorageEnsureMapDataDirectoryAndKeepFileHandle(LPCWSTR lpFileName, char a2, void **a3)
{
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // ebx
  signed int LastError; // eax
  HANDLE FileW; // rax
  signed int v11; // eax
  DWORD FileAttributesW; // eax
  signed int v13; // eax
  void *v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-28h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-20h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v15 = 0;
  v6 = QueryTransientObjectSecurityDescriptor(12, L"MapsCache", &v15);
  if ( v6 < 0 )
  {
    v7 = ZTraceReportOriginationNoThis(v6 | 0x10000000, "MosStorageEnsureMapDataDirectoryAndKeepFileHandle", 1114);
    goto LABEL_35;
  }
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = v15;
  v8 = 0;
  if ( qword_1800184A8 )
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, 3);
  if ( CreateDirectoryW(lpFileName, &SecurityAttributes) )
    goto LABEL_40;
  if ( GetLastError() != 183 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v7 = ZTraceReportOriginationNoThis(LastError, "MosStorageEnsureMapDataDirectoryAndKeepFileHandle", 1124);
    if ( qword_1800184A8 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v8);
    goto LABEL_35;
  }
  if ( !a3
    || (FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x2200000u, 0),
        *a3 = FileW,
        FileInformation = 0,
        !GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u))
    || (FileInformation & 0x410) == 0x10 )
  {
LABEL_40:
    if ( a2 || (FileAttributesW = GetFileAttributesW(lpFileName), SetFileAttributesW(lpFileName, FileAttributesW | 6)) )
    {
      v7 = 0;
      if ( qword_1800184A8 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v8);
    }
    else
    {
      v13 = GetLastError();
      if ( v13 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
      }
      else
      {
        v13 = -2143748092;
      }
      v7 = ZTraceReportOriginationNoThis(v13, "MosStorageEnsureMapDataDirectoryAndKeepFileHandle", 1136);
      if ( qword_1800184A8 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v8);
    }
  }
  else
  {
    v11 = GetLastError();
    if ( v11 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v11 = -2143748092;
    }
    v7 = ZTraceReportOriginationNoThis(v11, "MosStorageEnsureMapDataDirectoryAndKeepFileHandle", 1128);
    if ( qword_1800184A8 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v8);
  }
LABEL_35:
  if ( v15 )
    FreeTransientObjectSecurityDescriptor();
  return v7;
}

```

## disassembly

```asm
0x180008690  mov     [rsp-18h+arg_0], rbx
0x180008695  mov     [rsp-18h+arg_8], rsi
0x18000869a  push    rbp
0x18000869b  push    rdi
0x18000869c  push    r14
0x18000869e  mov     rbp, rsp
0x1800086a1  sub     rsp, 70h
0x1800086a5  mov     rsi, r8
0x1800086a8  mov     r14b, dl
0x1800086ab  mov     rdi, rcx
0x1800086ae  xorps   xmm0, xmm0
0x1800086b1  xor     eax, eax
0x1800086b3  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x1800086b7  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x1800086bb  mov     [rbp+var_30], rax
0x1800086bf  lea     r8, [rbp+var_30]
0x1800086c3  lea     rdx, aMapscache; "MapsCache"
0x1800086ca  lea     ecx, [rax+0Ch]
0x1800086cd  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800086d3  test    eax, eax
0x1800086d5  jns     short loc_1800086F7
0x1800086d7  bts     eax, 1Ch
0x1800086db  mov     r8d, 45Ah
0x1800086e1  lea     rdx, aMosstorageensu_3; "MosStorageEnsureMapDataDirectoryAndKeep"...
0x1800086e8  mov     ecx, eax
0x1800086ea  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800086f0  mov     edi, eax
0x1800086f2  jmp     loc_1800088EE
0x1800086f7  mov     [rbp+SecurityAttributes.nLength], 18h
0x1800086fe  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x180008705  mov     rax, [rbp+var_30]
0x180008709  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18000870d  xor     ebx, ebx
0x18000870f  mov     [rbp+arg_18], ebx
0x180008712  mov     rcx, cs:qword_1800184A8
0x180008719  test    rcx, rcx
0x18000871c  jz      short loc_180008732
0x18000871e  mov     rax, [rcx]
0x180008721  lea     edx, [rbx+3]
0x180008724  mov     rax, [rax+18h]
0x180008728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872d  mov     ebx, eax
0x18000872f  mov     [rbp+arg_18], eax
0x180008732  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180008736  mov     rcx, rdi; lpPathName
0x180008739  call    cs:__imp_CreateDirectoryW
0x18000873f  test    eax, eax
0x180008741  jnz     loc_180008862
0x180008747  call    cs:__imp_GetLastError
0x18000874d  cmp     eax, 0B7h
0x180008752  jz      short loc_1800087A6
0x180008754  call    cs:__imp_GetLastError
0x18000875a  test    eax, eax
0x18000875c  jz      short loc_18000876A
0x18000875e  jle     short loc_18000876F
0x180008760  movzx   eax, ax
0x180008763  or      eax, 80070000h
0x180008768  jmp     short loc_18000876F
0x18000876a  mov     eax, 80390004h
0x18000876f  mov     r8d, 464h
0x180008775  lea     rdx, aMosstorageensu_3; "MosStorageEnsureMapDataDirectoryAndKeep"...
0x18000877c  mov     ecx, eax
0x18000877e  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008784  mov     edi, eax
0x180008786  mov     rcx, cs:qword_1800184A8
0x18000878d  test    rcx, rcx
0x180008790  jz      short loc_1800087A1
0x180008792  mov     rax, [rcx]
0x180008795  mov     edx, ebx
0x180008797  mov     rax, [rax+18h]
0x18000879b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a0  nop
0x1800087a1  jmp     loc_1800088EE
0x1800087a6  test    rsi, rsi
0x1800087a9  jz      loc_180008862
0x1800087af  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800087b8  mov     [rsp+70h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800087c0  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x1800087c8  xor     r9d, r9d; lpSecurityAttributes
0x1800087cb  mov     edx, 80000000h; dwDesiredAccess
0x1800087d0  lea     r8d, [r9+1]; dwShareMode
0x1800087d4  mov     rcx, rdi; lpFileName
0x1800087d7  call    cs:__imp_CreateFileW
0x1800087dd  mov     [rsi], rax
0x1800087e0  mov     [rbp+FileInformation], 0
0x1800087e8  mov     r9d, 8; dwBufferSize
0x1800087ee  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800087f2  lea     edx, [r9+1]; FileInformationClass
0x1800087f6  mov     rcx, rax; hFile
0x1800087f9  call    cs:__imp_GetFileInformationByHandleEx
0x1800087ff  test    eax, eax
0x180008801  jz      short loc_180008862
0x180008803  mov     eax, dword ptr [rbp+FileInformation]
0x180008806  and     eax, 410h
0x18000880b  cmp     eax, 10h
0x18000880e  jz      short loc_180008862
0x180008810  call    cs:__imp_GetLastError
0x180008816  test    eax, eax
0x180008818  jz      short loc_180008826
0x18000881a  jle     short loc_18000882B
0x18000881c  movzx   eax, ax
0x18000881f  or      eax, 80070000h
0x180008824  jmp     short loc_18000882B
0x180008826  mov     eax, 80390004h
0x18000882b  mov     r8d, 468h
0x180008831  lea     rdx, aMosstorageensu_3; "MosStorageEnsureMapDataDirectoryAndKeep"...
0x180008838  mov     ecx, eax
0x18000883a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008840  mov     edi, eax
0x180008842  mov     rcx, cs:qword_1800184A8
0x180008849  test    rcx, rcx
0x18000884c  jz      short loc_18000885D
0x18000884e  mov     rax, [rcx]
0x180008851  mov     edx, ebx
0x180008853  mov     rax, [rax+18h]
0x180008857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885c  nop
0x18000885d  jmp     loc_1800088EE
0x180008862  test    r14b, r14b
0x180008865  jnz     short loc_1800088D1
0x180008867  mov     rcx, rdi; lpFileName
0x18000886a  call    cs:__imp_GetFileAttributesW
0x180008870  or      eax, 6
0x180008873  mov     edx, eax; dwFileAttributes
0x180008875  mov     rcx, rdi; lpFileName
0x180008878  call    cs:__imp_SetFileAttributesW
0x18000887e  test    eax, eax
0x180008880  jnz     short loc_1800088D1
0x180008882  call    cs:__imp_GetLastError
0x180008888  test    eax, eax
0x18000888a  jz      short loc_180008898
0x18000888c  jle     short loc_18000889D
0x18000888e  movzx   eax, ax
0x180008891  or      eax, 80070000h
0x180008896  jmp     short loc_18000889D
0x180008898  mov     eax, 80390004h
0x18000889d  mov     r8d, 470h
0x1800088a3  lea     rdx, aMosstorageensu_3; "MosStorageEnsureMapDataDirectoryAndKeep"...
0x1800088aa  mov     ecx, eax
0x1800088ac  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800088b2  mov     edi, eax
0x1800088b4  mov     rcx, cs:qword_1800184A8
0x1800088bb  test    rcx, rcx
0x1800088be  jz      short loc_1800088CF
0x1800088c0  mov     rax, [rcx]
0x1800088c3  mov     edx, ebx
0x1800088c5  mov     rax, [rax+18h]
0x1800088c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ce  nop
0x1800088cf  jmp     short loc_1800088EE
0x1800088d1  xor     edi, edi
0x1800088d3  mov     rcx, cs:qword_1800184A8
0x1800088da  test    rcx, rcx
0x1800088dd  jz      short loc_1800088EE
0x1800088df  mov     rax, [rcx]
0x1800088e2  mov     edx, ebx
0x1800088e4  mov     rax, [rax+18h]
0x1800088e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ed  nop
0x1800088ee  mov     rcx, [rbp+var_30]
0x1800088f2  test    rcx, rcx
0x1800088f5  jz      short loc_1800088FD
0x1800088f7  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800088fd  mov     eax, edi
0x1800088ff  lea     r11, [rsp+70h+var_s0]
0x180008904  mov     rbx, [r11+20h]
0x180008908  mov     rsi, [r11+28h]
0x18000890c  mov     rsp, r11
0x18000890f  pop     r14
0x180008911  pop     rdi
0x180008912  pop     rbp
0x180008913  retn
```
