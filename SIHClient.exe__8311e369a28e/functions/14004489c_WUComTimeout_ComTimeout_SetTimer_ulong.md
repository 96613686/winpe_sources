# WUComTimeout::ComTimeout::SetTimer(ulong)

- ea: `0x14004489c`
- end: `0x140044933`
- name: `?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z`
- size: `151`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003e598`
- `0x14003eb78`
- `0x14003ed44`
- `0x14003eeec`

## callees

- `0x140008e08`
- `0x14004489c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044918`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044918`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400448da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400448da`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1400448b6`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1400448b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400448c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400448c4`

## string_xrefs

- `0x1400448ed`: `C:\__w\1\s\src\Client\lib\util\ComTimeout.cpp`

## pseudocode

```c
__int64 __fastcall WUComTimeout::ComTimeout::SetTimer(_BYTE *pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  const char *v3; // r9
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( CoEnableCallCancellation(0) >= 0 )
  {
    pv[12] = 1;
    *((_DWORD *)pv + 2) = GetCurrentThreadId();
    ThreadpoolTimer = CreateThreadpoolTimer(WUComTimeout::ComTimeout::s_TimerCallback, pv, 0);
    *(_QWORD *)pv = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2B,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\ComTimeout.cpp",
               v3);
    pftDueTime = (struct _FILETIME)-150000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x3E8u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14004489c  push    rbx
0x14004489e  sub     rsp, 30h
0x1400448a2  mov     rax, cs:__security_cookie
0x1400448a9  xor     rax, rsp
0x1400448ac  mov     [rsp+38h+var_10], rax
0x1400448b1  mov     rbx, rcx
0x1400448b4  xor     ecx, ecx; pReserved
0x1400448b6  call    cs:__imp_CoEnableCallCancellation
0x1400448bc  test    eax, eax
0x1400448be  js      short loc_14004491E
0x1400448c0  mov     byte ptr [rbx+0Ch], 1
0x1400448c4  call    cs:__imp_GetCurrentThreadId
0x1400448ca  xor     r8d, r8d; pcbe
0x1400448cd  lea     rcx, ?s_TimerCallback@ComTimeout@WUComTimeout@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400448d4  mov     rdx, rbx; pv
0x1400448d7  mov     [rbx+8], eax
0x1400448da  call    cs:__imp_CreateThreadpoolTimer
0x1400448e0  mov     [rbx], rax
0x1400448e3  test    rax, rax
0x1400448e6  jnz     short loc_1400448FE
0x1400448e8  mov     rcx, [rsp+38h]; this
0x1400448ed  lea     r8, aCW1SSrcClientL_7; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400448f4  lea     edx, [rax+2Bh]; void *
0x1400448f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400448fc  jmp     short loc_140044920
0x1400448fe  xor     r9d, r9d; msWindowLength
0x140044901  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFF70F2E80h
0x14004490a  mov     r8d, 3E8h; msPeriod
0x140044910  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140044915  mov     rcx, rax; pti
0x140044918  call    cs:__imp_SetThreadpoolTimer
0x14004491e  xor     eax, eax
0x140044920  mov     rcx, [rsp+38h+var_10]
0x140044925  xor     rcx, rsp; StackCookie
0x140044928  call    __security_check_cookie
0x14004492d  add     rsp, 30h
0x140044931  pop     rbx
0x140044932  retn
```
