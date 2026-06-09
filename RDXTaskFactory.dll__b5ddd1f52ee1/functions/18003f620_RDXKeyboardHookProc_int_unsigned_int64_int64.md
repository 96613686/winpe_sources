# RDXKeyboardHookProc(int,unsigned __int64,__int64)

- ea: `0x18003f620`
- end: `0x18003f703`
- name: `?RDXKeyboardHookProc@@YA_JH_K_J@Z`
- size: `227`
- prototype: `LRESULT __stdcall(int code, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000e354`
- `0x1800109a8`
- `0x180014d04`
- `0x180023f68`
- `0x18003f620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003f694`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003f694`
- `USER32!CallNextHookEx` at `0x18003f6e5`
- `USER32!GetKeyState` at `0x18003f654`
- `USER32!GetKeyState` at `0x18003f662`
- `USER32!GetKeyState` at `0x18003f672`
- `USER32!GetKeyState` at `0x18003f654`
- `USER32!GetKeyState` at `0x18003f662`
- `USER32!GetKeyState` at `0x18003f672`

## string_xrefs

- `0x18003f6f1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LRESULT __fastcall RDXKeyboardHookProc(int code, WPARAM wParam, LPARAM lParam)
{
  HANDLE v6; // rax
  const char *v7; // r9
  void *v8; // rdx
  wil::details *v9; // rcx
  _OWORD v11[3]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (lParam & 0x80000000LL) == 0
    && !code
    && wParam == 67
    && (GetKeyState(91) || GetKeyState(wParam + 25))
    && GetKeyState(18) )
  {
    v11[0] = 0;
    v6 = OpenEventW(0x100002u, 0, L"Global\\RDX-ManualCleanup");
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CC8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        v7);
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      v11,
      v6);
    if ( *(_QWORD *)&v11[0] )
      v9 = **(wil::details ***)&v11[0];
    else
      v9 = 0;
    wil::details::SetEvent(v9, v8);
    std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(v11);
  }
  return CallNextHookEx(g_nextKeyboardHook, code, wParam, lParam);
}

```

## disassembly

```asm
0x18003f620  push    rbx
0x18003f622  push    rbp
0x18003f623  push    rsi
0x18003f624  push    rdi
0x18003f625  sub     rsp, 38h
0x18003f629  mov     rsi, r8
0x18003f62c  mov     rbx, rdx
0x18003f62f  mov     edi, ecx
0x18003f631  mov     rax, r8
0x18003f634  shr     rax, 10h
0x18003f638  xor     ebp, ebp
0x18003f63a  test    ax, ax
0x18003f63d  js      loc_18003F6CE
0x18003f643  test    ecx, ecx
0x18003f645  jnz     loc_18003F6CE
0x18003f64b  cmp     rdx, 43h ; 'C'
0x18003f64f  jnz     short loc_18003F6CE
0x18003f651  lea     ecx, [rdx+18h]; nVirtKey
0x18003f654  call    cs:__imp_GetKeyState
0x18003f65a  test    ax, ax
0x18003f65d  jnz     short loc_18003F66D
0x18003f65f  lea     ecx, [rbx+19h]; nVirtKey
0x18003f662  call    cs:__imp_GetKeyState
0x18003f668  test    ax, ax
0x18003f66b  jz      short loc_18003F6CE
0x18003f66d  mov     ecx, 12h; nVirtKey
0x18003f672  call    cs:__imp_GetKeyState
0x18003f678  test    ax, ax
0x18003f67b  jz      short loc_18003F6CE
0x18003f67d  xorps   xmm1, xmm1
0x18003f680  movdqu  [rsp+58h+var_38], xmm1
0x18003f686  lea     r8, aGlobalRdxManua; "Global\\RDX-ManualCleanup"
0x18003f68d  xor     edx, edx; bInheritHandle
0x18003f68f  mov     ecx, 100002h; dwDesiredAccess
0x18003f694  call    cs:__imp_OpenEventW
0x18003f69a  test    rax, rax
0x18003f69d  jz      short loc_18003F6EC
0x18003f69f  mov     rdx, rax
0x18003f6a2  lea     rcx, [rsp+58h+var_38]
0x18003f6a7  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18003f6ac  mov     rcx, qword ptr [rsp+58h+var_38]
0x18003f6b1  test    rcx, rcx
0x18003f6b4  jz      short loc_18003F6BB
0x18003f6b6  mov     rcx, [rcx]
0x18003f6b9  jmp     short loc_18003F6BE
0x18003f6bb  mov     rcx, rbp; this
0x18003f6be  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18003f6c3  nop
0x18003f6c4  lea     rcx, [rsp+58h+var_38]
0x18003f6c9  call    ??1?$shared_ptr@UConfigureIdleBehavior@@@std@@QEAA@XZ; std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(void)
0x18003f6ce  mov     r9, rsi
0x18003f6d1  mov     r8, rbx
0x18003f6d4  mov     edx, edi
0x18003f6d6  mov     rcx, cs:?g_nextKeyboardHook@@3PEAUHHOOK__@@EA; HHOOK__ * g_nextKeyboardHook
0x18003f6dd  add     rsp, 38h
0x18003f6e1  pop     rdi
0x18003f6e2  pop     rsi
0x18003f6e3  pop     rbp
0x18003f6e4  pop     rbx
0x18003f6e5  jmp     cs:__imp_CallNextHookEx
0x18003f6ec  mov     rcx, [rsp+58h]; this
0x18003f6f1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f6f8  mov     edx, 1CC8h; void *
0x18003f6fd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
