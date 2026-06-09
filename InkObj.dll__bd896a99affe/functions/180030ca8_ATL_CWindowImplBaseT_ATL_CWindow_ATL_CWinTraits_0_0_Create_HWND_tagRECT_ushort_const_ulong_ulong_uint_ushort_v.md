# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<0,0>>::Create(HWND__ *,tagRECT &,ushort const *,ulong,ulong,uint,ushort,void *)

- ea: `0x180030ca8`
- end: `0x180030def`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0A@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@AEAUtagRECT@@PEBGKKIGPEAX@Z`
- size: `327`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwStyle, DWORD dwExStyle, int, __int16)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180030c50`
- `0x1800ad420`
- `0x1800dbdf0`
- `0x1800eb5f0`

## callees

- `0x180030ca8`
- `0x180031f8c`
- `0x180079658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030cd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030cd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030de8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030de8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030d28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030d28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030d18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030d18`
- `USER32!CreateWindowExW` at `0x180030dce`
- `USER32!CreateWindowExW` at `0x180030dce`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<0,0>>::Create(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        int a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  unsigned __int32 v11; // edi

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
    JUMPOUT(0x180030DEELL);
  }
  v11 = 0;
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&stru_18016D180);
  *(_QWORD *)(a1 + 32) = qword_18016D1D8;
  qword_18016D1D8 = a1 + 16;
  LeaveCriticalSection(&stru_18016D180);
  if ( (dwStyle & 0x40000000) != 0 )
    v11 = _InterlockedIncrement(&dword_18016D210);
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           0,
           dwStyle,
           ATL::CWindow::rcDefault,
           Y,
           dword_18016C218 - ATL::CWindow::rcDefault,
           dword_18016C21C - Y,
           0,
           (HMENU)v11,
           hInstance,
           0);
}

```

## disassembly

```asm
0x180030ca8  push    rbx
0x180030caa  push    rsi
0x180030cab  push    rdi
0x180030cac  push    r14
0x180030cae  sub     rsp, 68h
0x180030cb2  mov     rax, [rcx+28h]
0x180030cb6  xor     r14d, r14d
0x180030cb9  mov     rbx, rcx
0x180030cbc  test    rax, rax
0x180030cbf  jnz     short loc_180030CE4
0x180030cc1  call    AtlThunk_AllocateData
0x180030cc6  mov     [rbx+28h], rax
0x180030cca  test    rax, rax
0x180030ccd  jnz     short loc_180030CE4
0x180030ccf  lea     ecx, [rax+0Eh]; dwErrCode
0x180030cd2  call    cs:__imp_SetLastError
0x180030cd8  xor     eax, eax
0x180030cda  add     rsp, 68h
0x180030cde  pop     r14
0x180030ce0  pop     rdi
0x180030ce1  pop     rsi
0x180030ce2  pop     rbx
0x180030ce3  retn
0x180030ce4  xor     r8d, r8d; FirstParameter
0x180030ce7  xor     edx, edx; Proc
0x180030ce9  mov     rcx, rax; Thunk
0x180030cec  call    AtlThunk_InitData
0x180030cf1  cmp     [rsp+88h+arg_38], r14w
0x180030cfa  jz      short loc_180030CD8
0x180030cfc  lea     rsi, [rbx+10h]
0x180030d00  test    rsi, rsi
0x180030d03  jz      loc_180030DD9
0x180030d09  test    rbx, rbx
0x180030d0c  jz      loc_180030DD9
0x180030d12  mov     edi, r14d
0x180030d15  mov     [rsi], rbx
0x180030d18  call    cs:__imp_GetCurrentThreadId
0x180030d1e  lea     rcx, stru_18016D180; lpCriticalSection
0x180030d25  mov     [rsi+8], eax
0x180030d28  call    cs:__imp_EnterCriticalSection
0x180030d2e  mov     rax, cs:qword_18016D1D8
0x180030d35  lea     rcx, stru_18016D180; lpCriticalSection
0x180030d3c  mov     [rsi+10h], rax
0x180030d40  mov     cs:qword_18016D1D8, rsi
0x180030d47  call    cs:__imp_LeaveCriticalSection
0x180030d4d  mov     r9d, [rsp+88h+dwStyle]; dwStyle
0x180030d55  bt      r9d, 1Eh
0x180030d5a  jnb     short loc_180030D6B
0x180030d5c  mov     edi, 1
0x180030d61  lock xadd cs:dword_18016D210, edi
0x180030d69  inc     edi
0x180030d6b  mov     r11d, cs:Y
0x180030d72  mov     r8d, cs:dword_18016C218
0x180030d79  mov     ebx, cs:?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x180030d7f  sub     r8d, ebx
0x180030d82  mov     rax, cs:hInstance
0x180030d89  mov     r10d, cs:dword_18016C21C
0x180030d90  movzx   edx, [rsp+88h+arg_38]; lpClassName
0x180030d98  sub     r10d, r11d
0x180030d9b  mov     [rsp+88h+lpParam], r14; lpParam
0x180030da0  mov     [rsp+88h+hInstance], rax; hInstance
0x180030da5  mov     ecx, edi
0x180030da7  mov     [rsp+88h+hMenu], rcx; hMenu
0x180030dac  mov     ecx, [rsp+88h+dwExStyle]; dwExStyle
0x180030db3  mov     [rsp+88h+hWndParent], r14; hWndParent
0x180030db8  mov     [rsp+88h+nHeight], r10d; nHeight
0x180030dbd  mov     [rsp+88h+nWidth], r8d; nWidth
0x180030dc2  xor     r8d, r8d; lpWindowName
0x180030dc5  mov     [rsp+88h+Y], r11d; Y
0x180030dca  mov     [rsp+88h+X], ebx; X
0x180030dce  call    cs:__imp_CreateWindowExW
0x180030dd4  jmp     loc_180030CDA
0x180030dd9  xor     r9d, r9d; lpArguments
0x180030ddc  xor     r8d, r8d; nNumberOfArguments
0x180030ddf  mov     ecx, 0C0000005h; dwExceptionCode
0x180030de4  lea     edx, [r9+1]; dwExceptionFlags
0x180030de8  call    cs:__imp_RaiseException
```
