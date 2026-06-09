# std::call_once<void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *>(std::once_flag &,void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*&&)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager * &&)

- ea: `0x18002b418`
- end: `0x18002b4a1`
- name: `??$call_once@P8PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@EAAXXZPEAV1234@@std@@YAXAEAUonce_flag@0@$$QEAP8PackagingResultManager@StandardCollector@DiagnosticsHub@Microsoft@@EAAXXZ$$QEAPEAV2345@@Z`
- size: `137`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a794`
- `0x18002a80c`

## callees

- `0x18002b418`
- `0x180049b50`
- `0x18004ae00`
- `0x18004b640`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18002b442`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002b442`
- `KERNEL32!InitOnceComplete` at `0x18002b47c`
- `KERNEL32!InitOnceComplete` at `0x18002b47c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002b44c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18002b44c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall std::call_once<void (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::*)(void),Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *>(
        LPINIT_ONCE lpInitOnce,
        void (__fastcall **a2)(_QWORD),
        _QWORD *a3)
{
  BOOL result; // eax
  BOOL fPending; // [rsp+30h] [rbp-28h] BYREF

  result = __std_init_once_begin_initialize(lpInitOnce, 0, &fPending, 0);
  if ( !result )
    abort();
  if ( fPending )
  {
    (*a2)(*a3);
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      _std_init_once_link_alternate_names_and_abort();
  }
  return result;
}

```

## disassembly

```asm
0x18002b418  push    rbx
0x18002b41a  push    rsi
0x18002b41b  push    rdi
0x18002b41c  sub     rsp, 40h
0x18002b420  mov     rax, cs:__security_cookie
0x18002b427  xor     rax, rsp
0x18002b42a  mov     [rsp+58h+var_20], rax
0x18002b42f  mov     rsi, r8
0x18002b432  mov     rdi, rdx
0x18002b435  mov     rbx, rcx
0x18002b438  xor     r9d, r9d; lpContext
0x18002b43b  lea     r8, [rsp+58h+fPending]; fPending
0x18002b440  xor     edx, edx; dwFlags
0x18002b442  call    cs:__imp___std_init_once_begin_initialize
0x18002b448  test    eax, eax
0x18002b44a  jnz     short loc_18002B453
0x18002b44c  call    cs:__imp_abort
0x18002b453  cmp     [rsp+58h+fPending], 0
0x18002b458  jz      short loc_18002B486
0x18002b45a  mov     [rsp+58h+var_38], rbx
0x18002b45f  mov     [rsp+58h+var_30], 4
0x18002b467  mov     rcx, [rsi]
0x18002b46a  mov     rax, [rdi]
0x18002b46d  call    cs:__guard_dispatch_icall_fptr
0x18002b473  nop
0x18002b474  xor     r8d, r8d; lpContext
0x18002b477  xor     edx, edx; dwFlags
0x18002b479  mov     rcx, rbx; lpInitOnce
0x18002b47c  call    cs:__imp_InitOnceComplete
0x18002b482  test    eax, eax
0x18002b484  jz      short loc_18002B49B
0x18002b486  mov     rcx, [rsp+58h+var_20]
0x18002b48b  xor     rcx, rsp; StackCookie
0x18002b48e  call    __security_check_cookie
0x18002b493  add     rsp, 40h
0x18002b497  pop     rdi
0x18002b498  pop     rsi
0x18002b499  pop     rbx
0x18002b49a  retn
0x18002b49b  call    __std_init_once_link_alternate_names_and_abort
```
