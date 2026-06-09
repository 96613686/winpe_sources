# wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x140009fdc`
- end: `0x14000a05d`
- name: `?LockExclusive@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140008a1c`
- `0x14000a070`
- `0x14000ba4c`
- `0x14000babc`

## callees

- `0x140008414`
- `0x140009fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a004`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a004`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK **v5; // rax
  int v6; // ecx
  int v7; // esi
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v2 )
  {
    v4 = v2 + 33;
    AcquireSRWLockExclusive(v4);
    v5 = &v10;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v4 = 0;
    v5 = &v9;
    v7 = 0;
    v6 = 2;
  }
  *a2 = v4;
  *v5 = 0;
  if ( v6 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v7 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x140009fdc  mov     [rsp+arg_10], rbx
0x140009fe1  mov     [rsp+arg_18], rsi
0x140009fe6  push    rdi
0x140009fe7  sub     rsp, 20h
0x140009feb  mov     rbx, [rcx+118h]
0x140009ff2  mov     rdi, rdx
0x140009ff5  test    rbx, rbx
0x140009ff8  jz      short loc_14000A018
0x140009ffa  add     rbx, 108h
0x14000a001  mov     rcx, rbx; SRWLock
0x14000a004  call    cs:__imp_AcquireSRWLockExclusive
0x14000a00a  lea     rax, [rsp+28h+arg_8]
0x14000a00f  xor     ecx, ecx
0x14000a011  mov     esi, 1
0x14000a016  jmp     short loc_14000A024
0x14000a018  xor     ebx, ebx
0x14000a01a  lea     rax, [rsp+28h+arg_0]
0x14000a01f  xor     esi, esi
0x14000a021  lea     ecx, [rbx+2]
0x14000a024  mov     [rdi], rbx
0x14000a027  mov     qword ptr [rax], 0
0x14000a02e  test    ecx, ecx
0x14000a030  jz      short loc_14000A03C
0x14000a032  lea     rcx, [rsp+28h+arg_0]
0x14000a037  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a03c  test    esi, esi
0x14000a03e  jz      short loc_14000A04A
0x14000a040  lea     rcx, [rsp+28h+arg_8]
0x14000a045  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a04a  mov     rbx, [rsp+28h+arg_10]
0x14000a04f  mov     rax, rdi
0x14000a052  mov     rsi, [rsp+28h+arg_18]
0x14000a057  add     rsp, 20h
0x14000a05b  pop     rdi
0x14000a05c  retn
```
