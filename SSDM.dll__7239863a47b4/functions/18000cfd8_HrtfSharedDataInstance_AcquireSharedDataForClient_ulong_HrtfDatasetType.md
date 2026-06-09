# HrtfSharedDataInstance::AcquireSharedDataForClient(ulong,_HrtfDatasetType)

- ea: `0x18000cfd8`
- end: `0x18000d3f7`
- name: `?AcquireSharedDataForClient@HrtfSharedDataInstance@@QEAAPEAU_HrtfSharedData@@KW4_HrtfDatasetType@@@Z`
- size: `1055`
- prototype: `_QWORD *__fastcall(__int64, int, int, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005ec0`

## callees

- `0x180002c18`
- `0x1800056e4`
- `0x180007468`
- `0x180007484`
- `0x18000c89c`
- `0x18000cfd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d08c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d114`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d08c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d114`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d0f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d18c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d26a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d0f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d18c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d26a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d325`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d2cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d2cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d052`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d0b4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d14c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d226`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d0b4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d14c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d33a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d34f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d33a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d34f`

## pseudocode

```c
_QWORD *__fastcall HrtfSharedDataInstance::AcquireSharedDataForClient(__int64 a1, int a2, int a3, const char *a4)
{
  int v5; // r8d
  int v6; // r15d
  _QWORD *v7; // r14
  HANDLE CurrentProcess; // rbx
  void *v9; // rdi
  HANDLE v10; // rax
  const char *v11; // r9
  HANDLE v12; // r12
  HANDLE *v13; // rdi
  HANDLE v14; // r13
  DWORD LastError; // ebx
  HANDLE v16; // rdi
  void *v17; // rbx
  HANDLE v18; // rax
  const char *v19; // r9
  HANDLE v20; // r12
  HANDLE *v21; // rdi
  HANDLE v22; // r13
  DWORD v23; // ebx
  HANDLE v24; // rax
  HANDLE v25; // rax
  unsigned int v26; // r12d
  int v27; // r15d
  HANDLE v28; // rdi
  void *v29; // rbx
  HANDLE v30; // rax
  const char *v31; // r9
  HANDLE *v32; // rdi
  HANDLE v33; // r13
  DWORD v34; // ebx
  HANDLE v35; // rcx
  __int64 v36; // rdi
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-60h]
  HANDLE v42; // [rsp+40h] [rbp-40h] BYREF
  HANDLE v43; // [rsp+48h] [rbp-38h] BYREF
  HANDLE v44; // [rsp+50h] [rbp-30h]
  __int64 v45; // [rsp+58h] [rbp-28h]
  _QWORD *v46; // [rsp+60h] [rbp-20h]
  HANDLE *p_hObject; // [rsp+68h] [rbp-18h]
  HANDLE TargetHandle; // [rsp+70h] [rbp-10h] BYREF
  char v49; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v51; // [rsp+C8h] [rbp+48h] BYREF
  int v52; // [rsp+D0h] [rbp+50h]
  HANDLE hObject; // [rsp+D8h] [rbp+58h] BYREF

  v51 = a2;
  if ( !a3 )
  {
    v6 = 8;
LABEL_8:
    v52 = 0;
    goto LABEL_9;
  }
  v5 = a3 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6B,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
        a4);
    v6 = 5;
    goto LABEL_8;
  }
  v6 = ((__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32)) >> 3) - 8;
  if ( v6 <= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5E,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      a4);
  v52 = 8;
LABEL_9:
  v7 = CoTaskMemAlloc(16 * (v6 + 3LL));
  v46 = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      (const char *)0x8007000ELL,
      dwDesiredAccess);
  v43 = 0;
  p_hObject = &v43;
  TargetHandle = 0;
  v49 = 1;
  CurrentProcess = GetCurrentProcess();
  v9 = *(void **)a1;
  v10 = GetCurrentProcess();
  if ( !DuplicateHandle(v10, v9, CurrentProcess, &TargetHandle, 0, 1, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x78,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v11);
  if ( v49 )
  {
    v12 = TargetHandle;
    v13 = p_hObject;
    v14 = *p_hObject;
    if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v14);
      SetLastError(LastError);
    }
    *v13 = v12;
  }
  v42 = 0;
  p_hObject = &v42;
  TargetHandle = 0;
  v49 = 1;
  v16 = GetCurrentProcess();
  v17 = **(void ***)(a1 + 16);
  v18 = GetCurrentProcess();
  if ( !DuplicateHandle(v18, v17, v16, &TargetHandle, 4u, 1, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7C,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v19);
  if ( v49 )
  {
    v20 = TargetHandle;
    v21 = p_hObject;
    v22 = *p_hObject;
    if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v23 = GetLastError();
      CloseHandle(v22);
      SetLastError(v23);
    }
    *v21 = v20;
  }
  v24 = v43;
  v43 = 0;
  *v7 = v24;
  v25 = v42;
  v42 = 0;
  v7[1] = v25;
  *((_DWORD *)v7 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL);
  *((_DWORD *)v7 + 6) = v6;
  v26 = 0;
  v27 = v52;
  do
  {
    hObject = 0;
    p_hObject = &hObject;
    TargetHandle = 0;
    v49 = 1;
    v28 = GetCurrentProcess();
    v45 = v26 + v27;
    v29 = **(void ***)(*(_QWORD *)(a1 + 32) + 8 * v45);
    v30 = GetCurrentProcess();
    if ( !DuplicateHandle(v30, v29, v28, &TargetHandle, 4u, 1, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
        v31);
    if ( v49 )
    {
      v44 = TargetHandle;
      v32 = p_hObject;
      v33 = *p_hObject;
      if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v34 = GetLastError();
        CloseHandle(v33);
        SetLastError(v34);
      }
      *v32 = v44;
    }
    v35 = hObject;
    hObject = 0;
    v7[2 * v26 + 4] = v35;
    LODWORD(v7[2 * v26 + 5]) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v45) + 16LL);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    ++v26;
  }
  while ( v26 < *((_DWORD *)v7 + 6) );
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  hObject = (HANDLE)(a1 + 72);
  v36 = *(_QWORD *)(a1 + 56);
  v38 = std::_List_buy<unsigned long const>::_Buynode<unsigned long const &>(v37, v36, *(_QWORD *)(v36 + 8), &v51);
  v39 = *(_QWORD *)(a1 + 64);
  if ( v39 == 0xAAAAAAAAAAAAAA9LL )
    std::_Xlength_error("list<T> too long");
  *(_QWORD *)(a1 + 64) = v39 + 1;
  *(_QWORD *)(v36 + 8) = v38;
  **(_QWORD **)(v38 + 8) = v38;
  if ( a1 != -72 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( (char *)v42 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v42);
  if ( (char *)v43 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v43);
  return v7;
}

```

## disassembly

```asm
0x18000cfd8  mov     [rsp-38h+arg_0], rbx
0x18000cfdd  mov     [rsp-38h+arg_8], edx
0x18000cfe1  push    rbp
0x18000cfe2  push    rsi
0x18000cfe3  push    rdi
0x18000cfe4  push    r12
0x18000cfe6  push    r13
0x18000cfe8  push    r14
0x18000cfea  push    r15
0x18000cfec  mov     rbp, rsp
0x18000cfef  sub     rsp, 80h
0x18000cff6  mov     rsi, rcx
0x18000cff9  xor     r13d, r13d
0x18000cffc  test    r8d, r8d
0x18000cfff  jz      short loc_18000D03D
0x18000d001  sub     r8d, 1
0x18000d005  jz      short loc_18000D017
0x18000d007  cmp     r8d, 1
0x18000d00b  jnz     loc_18000D39E
0x18000d011  lea     r15d, [r13+5]
0x18000d015  jmp     short loc_18000D043
0x18000d017  mov     r15, [rcx+28h]
0x18000d01b  sub     r15, [rcx+20h]
0x18000d01f  sar     r15, 3
0x18000d023  add     r15d, 0FFFFFFF8h
0x18000d027  mov     rcx, [rbp+38h]; this
0x18000d02b  test    r15d, r15d
0x18000d02e  jle     loc_18000D3B4
0x18000d034  mov     [rbp+arg_10], 8
0x18000d03b  jmp     short loc_18000D047
0x18000d03d  mov     r15d, 8
0x18000d043  mov     [rbp+arg_10], r13d
0x18000d047  movsxd  rcx, r15d
0x18000d04a  add     rcx, 3
0x18000d04e  shl     rcx, 4; cb
0x18000d052  call    cs:__imp_CoTaskMemAlloc
0x18000d058  mov     r14, rax
0x18000d05b  mov     [rbp+var_20], rax
0x18000d05f  mov     rcx, [rbp+38h]; this
0x18000d063  test    rax, rax
0x18000d066  jz      loc_18000D386
0x18000d06c  mov     [rbp+var_38], r13
0x18000d070  lea     rax, [rbp+var_38]
0x18000d074  mov     [rbp+var_18], rax
0x18000d078  mov     [rbp+TargetHandle], r13
0x18000d07c  mov     [rbp+var_8], 1
0x18000d080  call    cs:__imp_GetCurrentProcess
0x18000d086  mov     rbx, rax
0x18000d089  mov     rdi, [rsi]
0x18000d08c  call    cs:__imp_GetCurrentProcess
0x18000d092  mov     [rsp+80h+dwOptions], 2; dwOptions
0x18000d09a  mov     [rsp+80h+bInheritHandle], 1; bInheritHandle
0x18000d0a2  mov     [rsp+80h+dwDesiredAccess], r13d; dwDesiredAccess
0x18000d0a7  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000d0ab  mov     r8, rbx; hTargetProcessHandle
0x18000d0ae  mov     rdx, rdi; hSourceHandle
0x18000d0b1  mov     rcx, rax; hSourceProcessHandle
0x18000d0b4  call    cs:__imp_DuplicateHandle
0x18000d0ba  mov     rcx, [rbp+38h]; this
0x18000d0be  test    eax, eax
0x18000d0c0  jz      loc_18000D3C6
0x18000d0c6  cmp     [rbp+var_8], r13b
0x18000d0ca  jz      short loc_18000D100
0x18000d0cc  mov     r12, [rbp+TargetHandle]
0x18000d0d0  mov     rdi, [rbp+var_18]
0x18000d0d4  mov     r13, [rdi]
0x18000d0d7  lea     rax, [r13-1]
0x18000d0db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d0df  ja      short loc_18000D0FA
0x18000d0e1  call    cs:__imp_GetLastError
0x18000d0e7  mov     ebx, eax
0x18000d0e9  mov     rcx, r13; hObject
0x18000d0ec  call    cs:__imp_CloseHandle
0x18000d0f2  mov     ecx, ebx; dwErrCode
0x18000d0f4  call    cs:__imp_SetLastError
0x18000d0fa  mov     [rdi], r12
0x18000d0fd  xor     r13d, r13d
0x18000d100  mov     [rbp+var_40], r13
0x18000d104  lea     rax, [rbp+var_40]
0x18000d108  mov     [rbp+var_18], rax
0x18000d10c  mov     [rbp+TargetHandle], r13
0x18000d110  mov     [rbp+var_8], 1
0x18000d114  call    cs:__imp_GetCurrentProcess
0x18000d11a  mov     rdi, rax
0x18000d11d  mov     rcx, [rsi+10h]
0x18000d121  mov     rbx, [rcx]
0x18000d124  call    cs:__imp_GetCurrentProcess
0x18000d12a  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x18000d12f  mov     [rsp+80h+bInheritHandle], 1; bInheritHandle
0x18000d137  mov     [rsp+80h+dwDesiredAccess], 4; dwDesiredAccess
0x18000d13f  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000d143  mov     r8, rdi; hTargetProcessHandle
0x18000d146  mov     rdx, rbx; hSourceHandle
0x18000d149  mov     rcx, rax; hSourceProcessHandle
0x18000d14c  call    cs:__imp_DuplicateHandle
0x18000d152  mov     rcx, [rbp+38h]; this
0x18000d156  test    eax, eax
0x18000d158  jz      loc_18000D3D8
0x18000d15e  cmp     [rbp+var_8], r13b
0x18000d162  jz      short loc_18000D198
0x18000d164  mov     r12, [rbp+TargetHandle]
0x18000d168  mov     rdi, [rbp+var_18]
0x18000d16c  mov     r13, [rdi]
0x18000d16f  lea     rax, [r13-1]
0x18000d173  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d177  ja      short loc_18000D192
0x18000d179  call    cs:__imp_GetLastError
0x18000d17f  mov     ebx, eax
0x18000d181  mov     rcx, r13; hObject
0x18000d184  call    cs:__imp_CloseHandle
0x18000d18a  mov     ecx, ebx; dwErrCode
0x18000d18c  call    cs:__imp_SetLastError
0x18000d192  mov     [rdi], r12
0x18000d195  xor     r13d, r13d
0x18000d198  mov     rax, [rbp+var_38]
0x18000d19c  mov     [rbp+var_38], r13
0x18000d1a0  mov     [r14], rax
0x18000d1a3  mov     rax, [rbp+var_40]
0x18000d1a7  mov     [rbp+var_40], r13
0x18000d1ab  mov     [r14+8], rax
0x18000d1af  mov     rax, [rsi+10h]
0x18000d1b3  mov     ecx, [rax+10h]
0x18000d1b6  mov     [r14+10h], ecx
0x18000d1ba  mov     [r14+18h], r15d
0x18000d1be  mov     r12d, r13d
0x18000d1c1  test    r15d, r15d
0x18000d1c4  jz      loc_18000D2C8
0x18000d1ca  mov     r15d, [rbp+arg_10]
0x18000d1ce  mov     [rbp+hObject], r13
0x18000d1d2  lea     rax, [rbp+hObject]
0x18000d1d6  mov     [rbp+var_18], rax
0x18000d1da  mov     [rbp+TargetHandle], r13
0x18000d1de  mov     [rbp+var_8], 1
0x18000d1e2  call    cs:__imp_GetCurrentProcess
0x18000d1e8  mov     rdi, rax
0x18000d1eb  lea     eax, [r12+r15]
0x18000d1ef  mov     [rbp+var_28], rax
0x18000d1f3  mov     rcx, [rsi+20h]
0x18000d1f7  mov     rdx, [rcx+rax*8]
0x18000d1fb  mov     rbx, [rdx]
0x18000d1fe  call    cs:__imp_GetCurrentProcess
0x18000d204  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x18000d209  mov     [rsp+80h+bInheritHandle], 1; bInheritHandle
0x18000d211  mov     [rsp+80h+dwDesiredAccess], 4; dwDesiredAccess
0x18000d219  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000d21d  mov     r8, rdi; hTargetProcessHandle
0x18000d220  mov     rdx, rbx; hSourceHandle
0x18000d223  mov     rcx, rax; hSourceProcessHandle
0x18000d226  call    cs:__imp_DuplicateHandle
0x18000d22c  mov     rcx, [rbp+38h]; this
0x18000d230  test    eax, eax
0x18000d232  jz      loc_18000D374
0x18000d238  cmp     [rbp+var_8], r13b
0x18000d23c  jz      short loc_18000D27A
0x18000d23e  mov     rax, [rbp+TargetHandle]
0x18000d242  mov     [rbp+var_30], rax
0x18000d246  mov     rdi, [rbp+var_18]
0x18000d24a  mov     r13, [rdi]
0x18000d24d  lea     rax, [r13-1]
0x18000d251  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d255  ja      short loc_18000D270
0x18000d257  call    cs:__imp_GetLastError
0x18000d25d  mov     ebx, eax
0x18000d25f  mov     rcx, r13; hObject
0x18000d262  call    cs:__imp_CloseHandle
0x18000d268  mov     ecx, ebx; dwErrCode
0x18000d26a  call    cs:__imp_SetLastError
0x18000d270  mov     rax, [rbp+var_30]
0x18000d274  mov     [rdi], rax
0x18000d277  xor     r13d, r13d
0x18000d27a  mov     rcx, [rbp+hObject]
0x18000d27e  mov     [rbp+hObject], r13
0x18000d282  mov     edx, r12d
0x18000d285  lea     rax, [rdx+2]
0x18000d289  add     rax, rax
0x18000d28c  mov     [r14+rax*8], rcx
0x18000d290  mov     rax, [rsi+20h]
0x18000d294  mov     rcx, [rbp+var_28]
0x18000d298  mov     rax, [rax+rcx*8]
0x18000d29c  add     rdx, rdx
0x18000d29f  mov     eax, [rax+10h]
0x18000d2a2  mov     [r14+rdx*8+28h], eax
0x18000d2a7  mov     rcx, [rbp+hObject]; hObject
0x18000d2ab  lea     rax, [rcx-1]
0x18000d2af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d2b3  ja      short loc_18000D2BB
0x18000d2b5  call    cs:__imp_CloseHandle
0x18000d2bb  inc     r12d
0x18000d2be  cmp     r12d, [r14+18h]
0x18000d2c2  jb      loc_18000D1CE
0x18000d2c8  lea     rbx, [rsi+48h]
0x18000d2cc  mov     rcx, rbx; SRWLock
0x18000d2cf  call    cs:__imp_AcquireSRWLockExclusive
0x18000d2d5  mov     [rbp+hObject], rbx
0x18000d2d9  mov     rdi, [rsi+38h]
0x18000d2dd  lea     r9, [rbp+arg_8]
0x18000d2e1  mov     r8, [rdi+8]
0x18000d2e5  mov     rdx, rdi
0x18000d2e8  call    ??$_Buynode@AEBK@?$_List_buy@$$CBKV?$allocator@$$CBK@std@@@std@@QEAAPEAU?$_List_node@KPEAX@1@PEAU21@0AEBK@Z; std::_List_buy<ulong const>::_Buynode<ulong const &>(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *,ulong const &)
0x18000d2ed  mov     rdx, rax
0x18000d2f0  mov     rax, [rsi+40h]
0x18000d2f4  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000d2fe  sub     rcx, rax
0x18000d301  cmp     rcx, 1
0x18000d305  jb      loc_18000D3EA
0x18000d30b  inc     rax
0x18000d30e  mov     [rsi+40h], rax
0x18000d312  mov     [rdi+8], rdx
0x18000d316  mov     rax, [rdx+8]
0x18000d31a  mov     [rax], rdx
0x18000d31d  test    rbx, rbx
0x18000d320  jz      short loc_18000D32C
0x18000d322  mov     rcx, rbx; SRWLock
0x18000d325  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d32b  nop
0x18000d32c  mov     rcx, [rbp+var_40]; hObject
0x18000d330  lea     rax, [rcx-1]
0x18000d334  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d338  ja      short loc_18000D341
0x18000d33a  call    cs:__imp_CloseHandle
0x18000d340  nop
0x18000d341  mov     rcx, [rbp+var_38]; hObject
0x18000d345  lea     rax, [rcx-1]
0x18000d349  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d34d  ja      short loc_18000D356
0x18000d34f  call    cs:__imp_CloseHandle
0x18000d355  nop
0x18000d356  mov     rax, r14
0x18000d359  mov     rbx, [rsp+80h+arg_0]
0x18000d361  add     rsp, 80h
0x18000d368  pop     r15
0x18000d36a  pop     r14
0x18000d36c  pop     r13
0x18000d36e  pop     r12
0x18000d370  pop     rdi
0x18000d371  pop     rsi
0x18000d372  pop     rbp
0x18000d373  retn
0x18000d374  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d37b  mov     edx, 86h; void *
0x18000d380  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000d386  mov     r9d, 8007000Eh; char *
0x18000d38c  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d393  mov     edx, 71h ; 'q'; void *
0x18000d398  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d39e  mov     rcx, [rbp+38h]; this
0x18000d3a2  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d3a9  mov     edx, 6Bh ; 'k'; void *
0x18000d3ae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d3b4  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d3bb  mov     edx, 5Eh ; '^'; void *
0x18000d3c0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d3c6  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d3cd  mov     edx, 78h ; 'x'; void *
0x18000d3d2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000d3d8  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d3df  mov     edx, 7Ch ; '|'; void *
0x18000d3e4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000d3ea  lea     rcx, aListTTooLong; "list<T> too long"
0x18000d3f1  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
