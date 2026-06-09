# CConnection::StartCompositionThread(int)

- ea: `0x1800084f0`
- end: `0x180008652`
- name: `?StartCompositionThread@CConnection@@IEAAJH@Z`
- size: `354`
- prototype: `__int64 __fastcall(CConnection *__hidden this, int nPriority)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18022fde0`

## callees

- `0x1800084f0`
- `0x1800098f8`
- `0x1802004e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000851c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000851c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000862d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000862d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800085e2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800085e2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800085ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800085ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008581`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008638`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800085bd`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1800085bd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000860f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000860f`

## string_xrefs

- `0x1800085b3`: `DWM Compositor Thread`

## pseudocode

```c
__int64 __fastcall CConnection::StartCompositionThread(HANDLE *this, int nPriority)
{
  HANDLE *v3; // r14
  HANDLE EventW; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HANDLE v9; // rax
  char *v10; // rbp
  void *v11; // rsi
  DWORD LastError; // ebx
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  ThreadId = 0;
  v3 = this + 5;
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v3,
    EventW);
  if ( (((unsigned __int64)*v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = 170;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  v9 = CreateThread(0, 0, CConnection::CompositionThreadEntryPoint, this, 4u, &ThreadId);
  v10 = (char *)this[4];
  v11 = v9;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v10);
    SetLastError(LastError);
  }
  this[4] = v11;
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = 179;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  SetThreadDescription(v11, L"DWM Compositor Thread");
  if ( !SetThreadPriority(this[4], nPriority) )
  {
    v7 = 184;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  if ( ResumeThread(this[4]) == -1 )
  {
    v7 = 188;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  Handles[0] = this[4];
  Handles[1] = *v3;
  if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) == -1 )
  {
    v7 = 193;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800084f0  mov     rax, rsp
0x1800084f3  push    rbx
0x1800084f4  push    rbp
0x1800084f5  push    rsi
0x1800084f6  push    rdi
0x1800084f7  push    r14
0x1800084f9  push    r15
0x1800084fb  sub     rsp, 48h
0x1800084ff  xor     r9d, r9d; lpName
0x180008502  mov     dword ptr [rax+8], 0
0x180008509  mov     r15d, edx
0x18000850c  lea     r14, [rcx+28h]
0x180008510  mov     rdi, rcx
0x180008513  xor     r8d, r8d; bInitialState
0x180008516  xor     ecx, ecx; lpEventAttributes
0x180008518  lea     edx, [r9+1]; bManualReset
0x18000851c  call    cs:__imp_CreateEventW
0x180008522  mov     rdx, rax
0x180008525  mov     rcx, r14
0x180008528  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000852d  mov     rax, [r14]
0x180008530  inc     rax
0x180008533  test    rax, 0FFFFFFFFFFFFFFFEh
0x180008539  jnz     short loc_18000855E
0x18000853b  mov     edx, 0AAh; void *
0x180008540  mov     rcx, [rsp+78h]; this
0x180008545  lea     r8, aOnecoreuapWind_59; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18000854c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008551  add     rsp, 48h
0x180008555  pop     r15
0x180008557  pop     r14
0x180008559  pop     rdi
0x18000855a  pop     rsi
0x18000855b  pop     rbp
0x18000855c  pop     rbx
0x18000855d  retn
0x18000855e  lea     rax, [rsp+78h+ThreadId]
0x180008566  mov     r9, rdi; lpParameter
0x180008569  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18000856e  lea     r8, ?CompositionThreadEntryPoint@CConnection@@CAKPEAX@Z; lpStartAddress
0x180008575  xor     edx, edx; dwStackSize
0x180008577  mov     [rsp+78h+dwCreationFlags], 4; dwCreationFlags
0x18000857f  xor     ecx, ecx; lpThreadAttributes
0x180008581  call    cs:__imp_CreateThread
0x180008587  mov     rbp, [rdi+20h]
0x18000858b  mov     rsi, rax
0x18000858e  lea     rdx, [rbp-1]
0x180008592  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180008596  jbe     loc_18000862D
0x18000859c  lea     rax, [rsi+1]
0x1800085a0  mov     [rdi+20h], rsi
0x1800085a4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800085aa  jnz     short loc_1800085B3
0x1800085ac  mov     edx, 0B3h
0x1800085b1  jmp     short loc_180008540
0x1800085b3  lea     rdx, ThreadDescription; "DWM Compositor Thread"
0x1800085ba  mov     rcx, rsi; hThread
0x1800085bd  call    cs:__imp_SetThreadDescription
0x1800085c3  mov     rcx, [rdi+20h]; hThread
0x1800085c7  mov     edx, r15d; nPriority
0x1800085ca  call    cs:__imp_SetThreadPriority
0x1800085d0  test    eax, eax
0x1800085d2  jnz     short loc_1800085DE
0x1800085d4  mov     edx, 0B8h
0x1800085d9  jmp     loc_180008540
0x1800085de  mov     rcx, [rdi+20h]; hThread
0x1800085e2  call    cs:__imp_ResumeThread
0x1800085e8  or      ebx, 0FFFFFFFFh
0x1800085eb  cmp     eax, ebx
0x1800085ed  jz      short loc_180008623
0x1800085ef  mov     rax, [rdi+20h]
0x1800085f3  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800085f8  xor     r8d, r8d; bWaitAll
0x1800085fb  mov     [rsp+78h+Handles], rax
0x180008600  mov     rax, [r14]
0x180008603  mov     r9d, ebx; dwMilliseconds
0x180008606  mov     [rsp+78h+var_40], rax
0x18000860b  lea     ecx, [r8+2]; nCount
0x18000860f  call    cs:__imp_WaitForMultipleObjects
0x180008615  cmp     eax, ebx
0x180008617  jnz     short loc_18000864B
0x180008619  mov     edx, 0C1h
0x18000861e  jmp     loc_180008540
0x180008623  mov     edx, 0BCh
0x180008628  jmp     loc_180008540
0x18000862d  call    cs:__imp_GetLastError
0x180008633  mov     rcx, rbp; hObject
0x180008636  mov     ebx, eax
0x180008638  call    cs:__imp_CloseHandle
0x18000863e  mov     ecx, ebx; dwErrCode
0x180008640  call    cs:__imp_SetLastError
0x180008646  jmp     loc_18000859C
0x18000864b  xor     eax, eax
0x18000864d  jmp     loc_180008551
```
