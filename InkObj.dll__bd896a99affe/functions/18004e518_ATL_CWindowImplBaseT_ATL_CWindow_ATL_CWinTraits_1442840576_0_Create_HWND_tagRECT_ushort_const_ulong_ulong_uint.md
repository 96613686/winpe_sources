# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,tagRECT &,ushort const *,ulong,ulong,uint,ushort,void *)

- ea: `0x18004e518`
- end: `0x18004e661`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@PEBGKKIGPEAX@Z`
- size: `329`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18004e6a0`
- `0x18004e730`
- `0x1800e61c0`

## callees

- `0x180031f8c`
- `0x18004e518`
- `0x180079658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e54c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e54c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e65a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e65a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e5a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e5a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e5c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e596`
- `USER32!CreateWindowExW` at `0x18004e640`
- `USER32!CreateWindowExW` at `0x18004e640`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        __int64 a1,
        HWND a2,
        int *a3,
        __int64 a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        __int64 a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned __int32 v13; // edi

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *(_QWORD *)(a1 + 40) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == -16 || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x18004E660LL);
  }
  v13 = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&stru_18016D180);
  *(_QWORD *)(a1 + 32) = qword_18016D1D8;
  qword_18016D1D8 = a1 + 16;
  LeaveCriticalSection(&stru_18016D180);
  if ( (dwStyle & 0x40000000) != 0 )
    v13 = _InterlockedIncrement(&dword_18016D210);
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           0,
           dwStyle,
           *a3,
           a3[1],
           a3[2] - *a3,
           a3[3] - a3[1],
           a2,
           (HMENU)v13,
           hInstance,
           0);
}

```

## disassembly

```asm
0x18004e518  push    rbx
0x18004e51a  push    rsi
0x18004e51b  push    rdi
0x18004e51c  push    r12
0x18004e51e  push    r14
0x18004e520  push    r15
0x18004e522  sub     rsp, 68h
0x18004e526  mov     rax, [rcx+28h]
0x18004e52a  xor     r12d, r12d
0x18004e52d  mov     r14, r8
0x18004e530  mov     r15, rdx
0x18004e533  mov     rbx, rcx
0x18004e536  test    rax, rax
0x18004e539  jnz     short loc_18004E562
0x18004e53b  call    AtlThunk_AllocateData
0x18004e540  mov     [rbx+28h], rax
0x18004e544  test    rax, rax
0x18004e547  jnz     short loc_18004E562
0x18004e549  lea     ecx, [rax+0Eh]; dwErrCode
0x18004e54c  call    cs:__imp_SetLastError
0x18004e552  xor     eax, eax
0x18004e554  add     rsp, 68h
0x18004e558  pop     r15
0x18004e55a  pop     r14
0x18004e55c  pop     r12
0x18004e55e  pop     rdi
0x18004e55f  pop     rsi
0x18004e560  pop     rbx
0x18004e561  retn
0x18004e562  xor     r8d, r8d; FirstParameter
0x18004e565  xor     edx, edx; Proc
0x18004e567  mov     rcx, rax; Thunk
0x18004e56a  call    AtlThunk_InitData
0x18004e56f  cmp     [rsp+98h+arg_38], r12w
0x18004e578  jz      short loc_18004E552
0x18004e57a  lea     rsi, [rbx+10h]
0x18004e57e  test    rsi, rsi
0x18004e581  jz      loc_18004E64B
0x18004e587  test    rbx, rbx
0x18004e58a  jz      loc_18004E64B
0x18004e590  mov     edi, r12d
0x18004e593  mov     [rsi], rbx
0x18004e596  call    cs:__imp_GetCurrentThreadId
0x18004e59c  lea     rcx, stru_18016D180; lpCriticalSection
0x18004e5a3  mov     [rsi+8], eax
0x18004e5a6  call    cs:__imp_EnterCriticalSection
0x18004e5ac  mov     rax, cs:qword_18016D1D8
0x18004e5b3  lea     rcx, stru_18016D180; lpCriticalSection
0x18004e5ba  mov     [rsi+10h], rax
0x18004e5be  mov     cs:qword_18016D1D8, rsi
0x18004e5c5  call    cs:__imp_LeaveCriticalSection
0x18004e5cb  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x18004e5d3  bt      r9d, 1Eh
0x18004e5d8  jnb     short loc_18004E5E9
0x18004e5da  mov     edi, 1
0x18004e5df  lock xadd cs:dword_18016D210, edi
0x18004e5e7  inc     edi
0x18004e5e9  mov     r11d, [r14+4]
0x18004e5ed  mov     r8d, [r14+8]
0x18004e5f1  mov     ebx, [r14]
0x18004e5f4  sub     r8d, ebx
0x18004e5f7  mov     rax, cs:hInstance
0x18004e5fe  mov     r10d, [r14+0Ch]
0x18004e602  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x18004e60a  sub     r10d, r11d
0x18004e60d  mov     [rsp+98h+lpParam], r12; lpParam
0x18004e612  mov     [rsp+98h+hInstance], rax; hInstance
0x18004e617  mov     ecx, edi
0x18004e619  mov     [rsp+98h+hMenu], rcx; hMenu
0x18004e61e  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x18004e625  mov     [rsp+98h+hWndParent], r15; hWndParent
0x18004e62a  mov     [rsp+98h+nHeight], r10d; nHeight
0x18004e62f  mov     [rsp+98h+nWidth], r8d; nWidth
0x18004e634  xor     r8d, r8d; lpWindowName
0x18004e637  mov     [rsp+98h+Y], r11d; Y
0x18004e63c  mov     [rsp+98h+X], ebx; X
0x18004e640  call    cs:__imp_CreateWindowExW
0x18004e646  jmp     loc_18004E554
0x18004e64b  xor     r9d, r9d; lpArguments
0x18004e64e  xor     r8d, r8d; nNumberOfArguments
0x18004e651  mov     ecx, 0C0000005h; dwExceptionCode
0x18004e656  lea     edx, [r9+1]; dwExceptionFlags
0x18004e65a  call    cs:__imp_RaiseException
```
