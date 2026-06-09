# ATL::CContainedWindowT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,tagRECT *,ushort const *,ulong,ulong,uint,void *)

- ea: `0x1800d7d88`
- end: `0x1800d7eae`
- name: `?Create@?$CContainedWindowT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@PEAUtagRECT@@PEBGKKIPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(HMENU hMenu, HWND hWndParent)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800e2b0c`

## callees

- `0x180031f8c`
- `0x180079658`
- `0x1800d7d88`
- `0x1800dd1d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7dd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7dd7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7ea7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d7ea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7e34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7e34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7e05`
- `USER32!CreateWindowExW` at `0x1800d7e8d`
- `USER32!CreateWindowExW` at `0x1800d7e8d`

## pseudocode

```c
HWND __fastcall ATL::CContainedWindowT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU hMenu,
        HWND hWndParent,
        int *a3)
{
  unsigned __int16 v6; // ax
  const WCHAR *v7; // rsi
  AtlThunkData_t *Data; // rax

  v6 = ATL::CContainedWindowT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::RegisterWndSuperclass();
  v7 = (const WCHAR *)v6;
  if ( !v6 )
    return 0;
  Data = (AtlThunkData_t *)*((_QWORD *)hMenu + 4);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)hMenu + 4) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( hMenu == (HMENU)-8LL || !hMenu )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x1800D7EADLL);
  }
  *((_QWORD *)hMenu + 1) = hMenu;
  *((_DWORD *)hMenu + 4) = GetCurrentThreadId();
  EnterCriticalSection(&stru_18016D180);
  *((_QWORD *)hMenu + 3) = qword_18016D1D8;
  qword_18016D1D8 = (__int64)(hMenu + 2);
  LeaveCriticalSection(&stru_18016D180);
  return CreateWindowExW(
           0x20u,
           v7,
           0,
           0x54000000u,
           *a3,
           a3[1],
           a3[2] - *a3,
           a3[3] - a3[1],
           hWndParent,
           hMenu,
           hInstance,
           0);
}

```

## disassembly

```asm
0x1800d7d88  push    rbx
0x1800d7d8a  push    rbp
0x1800d7d8b  push    rsi
0x1800d7d8c  push    rdi
0x1800d7d8d  push    r14
0x1800d7d8f  push    r15
0x1800d7d91  sub     rsp, 68h
0x1800d7d95  mov     r14, r8
0x1800d7d98  mov     rbp, rdx
0x1800d7d9b  mov     rbx, rcx
0x1800d7d9e  call    ?RegisterWndSuperclass@?$CContainedWindowT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAGXZ; ATL::CContainedWindowT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::RegisterWndSuperclass(void)
0x1800d7da3  movzx   esi, ax
0x1800d7da6  xor     r15d, r15d
0x1800d7da9  test    si, si
0x1800d7dac  jnz     short loc_1800D7DBD
0x1800d7dae  xor     eax, eax
0x1800d7db0  add     rsp, 68h
0x1800d7db4  pop     r15
0x1800d7db6  pop     r14
0x1800d7db8  pop     rdi
0x1800d7db9  pop     rsi
0x1800d7dba  pop     rbp
0x1800d7dbb  pop     rbx
0x1800d7dbc  retn
0x1800d7dbd  mov     rax, [rbx+20h]
0x1800d7dc1  test    rax, rax
0x1800d7dc4  jnz     short loc_1800D7DDF
0x1800d7dc6  call    AtlThunk_AllocateData
0x1800d7dcb  mov     [rbx+20h], rax
0x1800d7dcf  test    rax, rax
0x1800d7dd2  jnz     short loc_1800D7DDF
0x1800d7dd4  lea     ecx, [rax+0Eh]; dwErrCode
0x1800d7dd7  call    cs:__imp_SetLastError
0x1800d7ddd  jmp     short loc_1800D7DAE
0x1800d7ddf  xor     r8d, r8d; FirstParameter
0x1800d7de2  xor     edx, edx; Proc
0x1800d7de4  mov     rcx, rax; Thunk
0x1800d7de7  call    AtlThunk_InitData
0x1800d7dec  lea     rdi, [rbx+8]
0x1800d7df0  test    rdi, rdi
0x1800d7df3  jz      loc_1800D7E98
0x1800d7df9  test    rbx, rbx
0x1800d7dfc  jz      loc_1800D7E98
0x1800d7e02  mov     [rdi], rbx
0x1800d7e05  call    cs:__imp_GetCurrentThreadId
0x1800d7e0b  lea     rcx, stru_18016D180; lpCriticalSection
0x1800d7e12  mov     [rdi+8], eax
0x1800d7e15  call    cs:__imp_EnterCriticalSection
0x1800d7e1b  mov     rax, cs:qword_18016D1D8
0x1800d7e22  lea     rcx, stru_18016D180; lpCriticalSection
0x1800d7e29  mov     [rdi+10h], rax
0x1800d7e2d  mov     cs:qword_18016D1D8, rdi
0x1800d7e34  call    cs:__imp_LeaveCriticalSection
0x1800d7e3a  mov     r9d, [r14+4]
0x1800d7e3e  mov     rdx, rsi; lpClassName
0x1800d7e41  mov     r8d, [r14+0Ch]
0x1800d7e45  mov     r10d, [r14]
0x1800d7e48  sub     r8d, r9d
0x1800d7e4b  mov     rax, cs:hInstance
0x1800d7e52  mov     ecx, [r14+8]
0x1800d7e56  mov     [rsp+98h+lpParam], r15; lpParam
0x1800d7e5b  sub     ecx, r10d
0x1800d7e5e  mov     [rsp+98h+hInstance], rax; hInstance
0x1800d7e63  mov     [rsp+98h+hMenu], rbx; hMenu
0x1800d7e68  mov     [rsp+98h+hWndParent], rbp; hWndParent
0x1800d7e6d  mov     [rsp+98h+nHeight], r8d; nHeight
0x1800d7e72  xor     r8d, r8d; lpWindowName
0x1800d7e75  mov     [rsp+98h+nWidth], ecx; nWidth
0x1800d7e79  mov     [rsp+98h+Y], r9d; Y
0x1800d7e7e  mov     r9d, 54000000h; dwStyle
0x1800d7e84  mov     [rsp+98h+X], r10d; X
0x1800d7e89  lea     ecx, [r8+20h]; dwExStyle
0x1800d7e8d  call    cs:__imp_CreateWindowExW
0x1800d7e93  jmp     loc_1800D7DB0
0x1800d7e98  xor     r9d, r9d; lpArguments
0x1800d7e9b  xor     r8d, r8d; nNumberOfArguments
0x1800d7e9e  mov     ecx, 0C0000005h; dwExceptionCode
0x1800d7ea3  lea     edx, [r9+1]; dwExceptionFlags
0x1800d7ea7  call    cs:__imp_RaiseException
```
