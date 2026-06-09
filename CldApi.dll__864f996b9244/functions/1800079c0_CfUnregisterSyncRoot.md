# CfUnregisterSyncRoot

- ea: `0x1800079c0`
- end: `0x180007ce9`
- name: `CfUnregisterSyncRoot`
- size: `809`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x18000446c`
- `0x1800079c0`
- `0x18000f6fc`
- `0x180010c9c`
- `0x180011338`
- `0x1800115f8`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007a1e`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007cbe`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007a1e`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007cbe`
- `ntdll!RtlNtStatusToDosError` at `0x180007ab0`
- `ntdll!RtlNtStatusToDosError` at `0x180007ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c11`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007a40`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007a40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180007c03`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180007c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cb5`

## string_xrefs

- `0x180007ac9`: `CfpCreateFile Failed`
- `0x180007a65`: `SyncRootPath can't be NULL`

## pseudocode

```c
__int64 __fastcall CfUnregisterSyncRoot(__int64 a1)
{
  char *v2; // rsi
  __int64 v3; // rcx
  char *v4; // r14
  _DWORD *v5; // r15
  char v6; // r12
  int SyncRootInfoByHandle; // ebx
  const wchar_t *v8; // rdi
  __int64 v9; // rdx
  NTSTATUS File; // eax
  signed int v11; // eax
  int v12; // r12d
  unsigned int v13; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  int v16; // ecx
  int v17; // edx
  signed int LastError; // eax
  HANDLE v19; // rax
  __int64 v20; // rcx
  HANDLE FileHandle; // [rsp+28h] [rbp-D8h]
  char v23; // [rsp+50h] [rbp-B0h]
  __int64 FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v29; // [rsp+D4h] [rbp-2Ch] BYREF
  char v30; // [rsp+2D4h] [rbp+1D4h] BYREF

  memset_0(v28, 0, 0x404u);
  LODWORD(v2) = 0;
  LOBYTE(v3) = 2;
  UnbiasedTime = 0;
  v4 = 0;
  FileInformation = 0;
  v5 = 0;
  v23 = RtlSetThreadPlaceholderCompatibilityMode(v3);
  v6 = v23;
  memset_0(v26, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByHandle = a1 == 0 ? 0x57 : 0;
  if ( !a1 )
    SyncRootInfoByHandle |= 0x80070000;
  if ( SyncRootInfoByHandle > -1 )
  {
    SyncRootInfoByHandle = GlobalPortInit(0);
    if ( SyncRootInfoByHandle > -1 )
    {
      LODWORD(FileHandle) = 2097185;
      File = CfpCreateFile(a1, v9, 129, 7);
      v11 = RtlNtStatusToDosError(File);
      SyncRootInfoByHandle = v11;
      if ( v11 > 0 )
        SyncRootInfoByHandle = (unsigned __int16)v11 | 0x80070000;
      if ( SyncRootInfoByHandle > -1 )
      {
        v4 = &v30;
        v2 = &v29;
        if ( (int)CfpGetSyncRootInfoByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0) < 0 )
        {
          v4 = 0;
          LODWORD(v2) = 0;
        }
        v12 = 0;
        while ( 1 )
        {
          if ( v5 )
          {
            v13 = v5[263] + 1056;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v5);
          }
          else
          {
            v13 = 1056;
          }
          v15 = GetProcessHeap();
          v5 = HeapAlloc(v15, 0, v13);
          SyncRootInfoByHandle = v5 == 0 ? 8 : 0;
          if ( !v5 )
            SyncRootInfoByHandle |= 0x80070000;
          if ( SyncRootInfoByHandle < 0 )
          {
            v8 = L"Allocating Memory for syncRootStdInfo Failed";
            goto LABEL_37;
          }
          SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0);
          if ( SyncRootInfoByHandle != -2147024662 )
            break;
          if ( ++v12 >= 2 )
            goto LABEL_25;
        }
        if ( SyncRootInfoByHandle <= -1 )
        {
LABEL_25:
          v8 = L"CfpGetSyncRootInfoByHandle Failed";
          goto LABEL_37;
        }
        v16 = v5[6];
        if ( !v16 || (unsigned int)(v16 + 0x3FFFFFFF) <= 1 || (v16 & 0x40) != 0 )
        {
          if ( GetFileInformationByHandleEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, FileAttributeTagInfo, &FileInformation, 8u) )
          {
            SyncRootInfoByHandle = 0;
          }
          else
          {
            LastError = GetLastError();
            SyncRootInfoByHandle = LastError;
            if ( LastError > 0 )
              SyncRootInfoByHandle = (unsigned __int16)LastError | 0x80070000;
          }
          if ( SyncRootInfoByHandle > -1 )
          {
            v8 = 0;
            CfpRecurseDirectory(-1, v17, FileInformation, SHIDWORD(FileInformation), 0, FileHandle);
            RevertSyncRoot((HANDLE)0xFFFFFFFFFFFFFFFFLL);
          }
          else
          {
            v8 = L"GetFileInformationByHandleEx Failed";
          }
        }
        else
        {
          SyncRootInfoByHandle = -2147024516;
          v8 = L"Can't unregister when a provider is Connected";
        }
LABEL_37:
        v6 = v23;
      }
      else
      {
        v8 = L"CfpCreateFile Failed";
      }
    }
    else
    {
      v8 = L"GlobalPortInit Failed";
    }
  }
  else
  {
    v8 = L"SyncRootPath can't be NULL";
  }
  v27 = v8;
  TlmLogApiReliability(10, 0, a1, (_DWORD)v2, (__int64)v4, UnbiasedTime, (__int64)v26, SyncRootInfoByHandle);
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  v20 = -1;
  LOBYTE(v20) = v6;
  RtlSetThreadPlaceholderCompatibilityMode(v20);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x1800079c0  push    rbp
0x1800079c2  push    rbx
0x1800079c3  push    rsi
0x1800079c4  push    rdi
0x1800079c5  push    r12
0x1800079c7  push    r13
0x1800079c9  push    r14
0x1800079cb  push    r15
0x1800079cd  lea     rbp, [rsp-3F8h]
0x1800079d5  sub     rsp, 4F8h
0x1800079dc  mov     rax, cs:__security_cookie
0x1800079e3  xor     rax, rsp
0x1800079e6  mov     [rbp+430h+var_50], rax
0x1800079ed  mov     r13, rcx
0x1800079f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800079f4  lea     rcx, [rbp+430h+var_460]; void *
0x1800079f8  mov     [rsp+530h+hFile], rdi
0x1800079fd  xor     edx, edx; Val
0x1800079ff  mov     r8d, 404h; Size
0x180007a05  call    memset_0
0x180007a0a  xor     esi, esi
0x180007a0c  mov     cl, 2
0x180007a0e  mov     [rsp+530h+UnbiasedTime], rsi
0x180007a13  xor     r14d, r14d
0x180007a16  mov     [rsp+530h+FileInformation], rsi
0x180007a1b  xor     r15d, r15d
0x180007a1e  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x180007a24  xor     edx, edx; Val
0x180007a26  lea     r8d, [rdi+59h]; Size
0x180007a2a  lea     rcx, [rsp+530h+var_4C0]; void *
0x180007a2f  mov     [rsp+530h+var_4E0], al
0x180007a33  mov     r12b, al
0x180007a36  call    memset_0
0x180007a3b  lea     rcx, [rsp+530h+UnbiasedTime]; UnbiasedTime
0x180007a40  call    cs:__imp_QueryUnbiasedInterruptTime
0x180007a46  mov     rcx, r13
0x180007a49  neg     rcx
0x180007a4c  sbb     ebx, ebx
0x180007a4e  not     ebx
0x180007a50  and     ebx, 57h
0x180007a53  mov     ecx, ebx
0x180007a55  or      ecx, 80070000h
0x180007a5b  test    r13, r13
0x180007a5e  cmovz   ebx, ecx
0x180007a61  cmp     ebx, edi
0x180007a63  jg      short loc_180007A71
0x180007a65  lea     rdi, aSyncrootpathCa; "SyncRootPath can't be NULL"
0x180007a6c  jmp     loc_180007C5D
0x180007a71  xor     ecx, ecx
0x180007a73  call    GlobalPortInit
0x180007a78  mov     ebx, eax
0x180007a7a  cmp     eax, edi
0x180007a7c  jg      short loc_180007A8A
0x180007a7e  lea     rdi, aGlobalportinit; "GlobalPortInit Failed"
0x180007a85  jmp     loc_180007C5D
0x180007a8a  mov     r9d, 7
0x180007a90  lea     rax, [rsp+530h+hFile]
0x180007a95  mov     [rsp+530h+var_4F8], rax
0x180007a9a  mov     rcx, r13
0x180007a9d  mov     dword ptr [rsp+530h+FileHandle], 200021h; FileHandle
0x180007aa5  lea     r8d, [r9+7Ah]
0x180007aa9  call    CfpCreateFile
0x180007aae  mov     ecx, eax; Status
0x180007ab0  call    cs:__imp_RtlNtStatusToDosError
0x180007ab6  mov     ebx, eax
0x180007ab8  test    eax, eax
0x180007aba  jle     short loc_180007AC5
0x180007abc  movzx   ebx, ax
0x180007abf  or      ebx, 80070000h
0x180007ac5  cmp     ebx, edi
0x180007ac7  jg      short loc_180007AD5
0x180007ac9  lea     rdi, aCfpcreatefileF; "CfpCreateFile Failed"
0x180007ad0  jmp     loc_180007C5D
0x180007ad5  mov     rcx, [rsp+530h+hFile]; hFile
0x180007ada  lea     r8, [rbp+430h+var_460]
0x180007ade  mov     r9d, 404h
0x180007ae4  mov     [rsp+530h+var_510], rsi; __int64
0x180007ae9  mov     edx, 2
0x180007aee  call    CfpGetSyncRootInfoByHandle
0x180007af3  xor     ecx, ecx
0x180007af5  lea     r14, [rbp+430h+var_25C]
0x180007afc  test    eax, eax
0x180007afe  lea     rsi, [rbp+430h+var_45C]
0x180007b02  cmovs   r14, rcx
0x180007b06  cmovs   rsi, rcx
0x180007b0a  xor     r12d, r12d
0x180007b0d  test    r15, r15
0x180007b10  jnz     short loc_180007B19
0x180007b12  mov     edi, 420h
0x180007b17  jmp     short loc_180007B3A
0x180007b19  mov     edi, [r15+41Ch]
0x180007b20  add     edi, 420h
0x180007b26  call    cs:__imp_GetProcessHeap
0x180007b2c  mov     r8, r15; lpMem
0x180007b2f  xor     edx, edx; dwFlags
0x180007b31  mov     rcx, rax; hHeap
0x180007b34  call    cs:__imp_HeapFree
0x180007b3a  call    cs:__imp_GetProcessHeap
0x180007b40  mov     r8d, edi; dwBytes
0x180007b43  xor     edx, edx; dwFlags
0x180007b45  mov     rcx, rax; hHeap
0x180007b48  call    cs:__imp_HeapAlloc
0x180007b4e  mov     r15, rax
0x180007b51  neg     rax
0x180007b54  sbb     ebx, ebx
0x180007b56  not     ebx
0x180007b58  and     ebx, 8
0x180007b5b  mov     eax, ebx
0x180007b5d  or      eax, 80070000h
0x180007b62  test    r15, r15
0x180007b65  cmovz   ebx, eax
0x180007b68  test    ebx, ebx
0x180007b6a  jz      short loc_180007B6E
0x180007b6c  js      short loc_180007BA4
0x180007b6e  mov     rcx, [rsp+530h+hFile]; hFile
0x180007b73  mov     r9d, edi
0x180007b76  mov     r8, r15
0x180007b79  mov     [rsp+530h+var_510], 0; __int64
0x180007b82  mov     edx, 1
0x180007b87  call    CfpGetSyncRootInfoByHandle
0x180007b8c  mov     ebx, eax
0x180007b8e  cmp     eax, 800700EAh
0x180007b93  jnz     short loc_180007BB0
0x180007b95  inc     r12d
0x180007b98  cmp     r12d, 2
0x180007b9c  jl      loc_180007B0D
0x180007ba2  jmp     short loc_180007BB5
0x180007ba4  lea     rdi, aAllocatingMemo; "Allocating Memory for syncRootStdInfo F"...
0x180007bab  jmp     loc_180007C58
0x180007bb0  cmp     ebx, 0FFFFFFFFh
0x180007bb3  jg      short loc_180007BC1
0x180007bb5  lea     rdi, aCfpgetsyncroot; "CfpGetSyncRootInfoByHandle Failed"
0x180007bbc  jmp     loc_180007C58
0x180007bc1  mov     ecx, [r15+18h]
0x180007bc5  test    ecx, ecx
0x180007bc7  jz      short loc_180007BE0
0x180007bc9  lea     eax, [rcx+3FFFFFFFh]
0x180007bcf  cmp     eax, 1
0x180007bd2  jbe     short loc_180007BE0
0x180007bd4  test    cl, 40h
0x180007bd7  jnz     short loc_180007BE0
0x180007bd9  mov     ebx, 8007017Ch
0x180007bde  jmp     short loc_180007BE6
0x180007be0  test    ebx, ebx
0x180007be2  jz      short loc_180007BEF
0x180007be4  jns     short loc_180007BEF
0x180007be6  lea     rdi, aCanTUnregister; "Can't unregister when a provider is Con"...
0x180007bed  jmp     short loc_180007C58
0x180007bef  mov     rcx, [rsp+530h+hFile]; hFile
0x180007bf4  lea     r8, [rsp+530h+FileInformation]; lpFileInformation
0x180007bf9  mov     r9d, 8; dwBufferSize
0x180007bff  lea     edx, [r9+1]; FileInformationClass
0x180007c03  call    cs:__imp_GetFileInformationByHandleEx
0x180007c09  test    eax, eax
0x180007c0b  jz      short loc_180007C11
0x180007c0d  xor     ebx, ebx
0x180007c0f  jmp     short loc_180007C26
0x180007c11  call    cs:__imp_GetLastError
0x180007c17  mov     ebx, eax
0x180007c19  test    eax, eax
0x180007c1b  jle     short loc_180007C26
0x180007c1d  movzx   ebx, ax
0x180007c20  or      ebx, 80070000h
0x180007c26  cmp     ebx, 0FFFFFFFFh
0x180007c29  jg      short loc_180007C34
0x180007c2b  lea     rdi, aGetfileinforma; "GetFileInformationByHandleEx Failed"
0x180007c32  jmp     short loc_180007C58
0x180007c34  mov     r9d, dword ptr [rsp+530h+FileInformation+4]; int
0x180007c39  xor     edi, edi
0x180007c3b  mov     r8d, dword ptr [rsp+530h+FileInformation]; int
0x180007c40  mov     rcx, [rsp+530h+hFile]; int
0x180007c45  mov     dword ptr [rsp+530h+var_510], edi; int
0x180007c49  call    CfpRecurseDirectory
0x180007c4e  mov     rcx, [rsp+530h+hFile]; hFile
0x180007c53  call    RevertSyncRoot
0x180007c58  mov     r12b, [rsp+530h+var_4E0]
0x180007c5d  mov     dword ptr [rsp+530h+var_4F8], ebx
0x180007c61  lea     rax, [rsp+530h+var_4C0]
0x180007c66  mov     [rsp+530h+var_500], rax
0x180007c6b  mov     ecx, 0Ah
0x180007c70  mov     rax, [rsp+530h+UnbiasedTime]
0x180007c75  mov     r9, rsi
0x180007c78  mov     [rsp+530h+FileHandle], rax
0x180007c7d  mov     r8, r13
0x180007c80  xor     edx, edx
0x180007c82  mov     [rsp+530h+var_510], r14
0x180007c87  mov     [rsp+530h+var_4B8], rdi
0x180007c8c  call    TlmLogApiReliability
0x180007c91  test    r15, r15
0x180007c94  jz      short loc_180007CAA
0x180007c96  call    cs:__imp_GetProcessHeap
0x180007c9c  mov     r8, r15; lpMem
0x180007c9f  xor     edx, edx; dwFlags
0x180007ca1  mov     rcx, rax; hHeap
0x180007ca4  call    cs:__imp_HeapFree
0x180007caa  mov     rcx, [rsp+530h+hFile]; hObject
0x180007caf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007cb3  jz      short loc_180007CBB
0x180007cb5  call    cs:__imp_CloseHandle
0x180007cbb  mov     cl, r12b
0x180007cbe  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x180007cc4  mov     eax, ebx
0x180007cc6  mov     rcx, [rbp+430h+var_50]
0x180007ccd  xor     rcx, rsp; StackCookie
0x180007cd0  call    __security_check_cookie
0x180007cd5  add     rsp, 4F8h
0x180007cdc  pop     r15
0x180007cde  pop     r14
0x180007ce0  pop     r13
0x180007ce2  pop     r12
0x180007ce4  pop     rdi
0x180007ce5  pop     rsi
0x180007ce6  pop     rbx
0x180007ce7  pop     rbp
0x180007ce8  retn
```
