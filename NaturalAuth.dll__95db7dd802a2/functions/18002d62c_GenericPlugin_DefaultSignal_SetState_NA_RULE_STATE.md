# GenericPlugin::DefaultSignal::SetState(NA_RULE_STATE)

- ea: `0x18002d62c`
- end: `0x18002d6cc`
- name: `?SetState@DefaultSignal@GenericPlugin@@QEAAXW4NA_RULE_STATE@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a01c`
- `0x18002c98c`
- `0x18003a7a4`
- `0x18003cea4`
- `0x18003eea0`
- `0x18003f794`

## callees

- `0x18000b5d0`
- `0x1800289d0`
- `0x18002d62c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d648`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d648`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GenericPlugin::DefaultSignal::SetState(__int64 a1, int a2)
{
  RTL_SRWLOCK *v3; // rbx
  __int64 ***v4; // rdi
  __int64 **i; // rbx
  RTL_SRWLOCK *v6; // [rsp+40h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 16) = a2;
  v3 = (RTL_SRWLOCK *)(a1 + 24);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 24));
  v6 = v3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_1313e11ac9f43f31e5324403d3fcf239_Traceguids,
      *(unsigned int *)(a1 + 40),
      *(_DWORD *)(a1 + 16));
  v4 = *(__int64 ****)(a1 + 32);
  for ( i = *v4; i != (__int64 **)v4; i = (__int64 **)*i )
    ((void (__fastcall *)(__int64 *, _QWORD, _QWORD))i[3])(i[2], *(_QWORD *)(a1 + 8), *(unsigned int *)(a1 + 16));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x18002d62c  mov     [rsp+arg_8], rbx
0x18002d631  mov     [rsp+arg_10], rsi
0x18002d636  push    rdi
0x18002d637  sub     rsp, 30h
0x18002d63b  mov     rsi, rcx
0x18002d63e  mov     [rcx+10h], edx
0x18002d641  lea     rbx, [rcx+18h]
0x18002d645  mov     rcx, rbx; SRWLock
0x18002d648  call    cs:__imp_AcquireSRWLockShared
0x18002d64e  mov     [rsp+38h+arg_0], rbx
0x18002d653  lea     rax, WPP_GLOBAL_Control
0x18002d65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d661  cmp     rcx, rax
0x18002d664  jz      short loc_18002D68C
0x18002d666  test    byte ptr [rcx+1Ch], 4
0x18002d66a  jz      short loc_18002D68C
0x18002d66c  mov     edx, 0Dh
0x18002d671  mov     eax, [rsi+10h]
0x18002d674  mov     [rsp+38h+var_18], eax
0x18002d678  mov     r9d, [rsi+28h]
0x18002d67c  lea     r8, WPP_1313e11ac9f43f31e5324403d3fcf239_Traceguids
0x18002d683  mov     rcx, [rcx+10h]
0x18002d687  call    WPP_SF_dd
0x18002d68c  mov     rdi, [rsi+20h]
0x18002d690  mov     rbx, [rdi]
0x18002d693  cmp     rbx, rdi
0x18002d696  jz      short loc_18002D6B2
0x18002d698  mov     r8d, [rsi+10h]
0x18002d69c  mov     rdx, [rsi+8]
0x18002d6a0  mov     rcx, [rbx+10h]
0x18002d6a4  mov     rax, [rbx+18h]
0x18002d6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6ad  mov     rbx, [rbx]
0x18002d6b0  jmp     short loc_18002D693
0x18002d6b2  lea     rcx, [rsp+38h+arg_0]
0x18002d6b7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002d6bc  mov     rbx, [rsp+38h+arg_8]
0x18002d6c1  mov     rsi, [rsp+38h+arg_10]
0x18002d6c6  add     rsp, 30h
0x18002d6ca  pop     rdi
0x18002d6cb  retn
```
