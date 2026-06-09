# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18001608c`
- end: `0x18001610d`
- name: `?LockExclusive@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800142d4`
- `0x180016730`
- `0x180019f30`
- `0x18001effc`
- `0x18001f06c`

## callees

- `0x180011488`
- `0x18001608c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800160b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800160b4`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18001608c  mov     [rsp+arg_10], rbx
0x180016091  mov     [rsp+arg_18], rsi
0x180016096  push    rdi
0x180016097  sub     rsp, 20h
0x18001609b  mov     rbx, [rcx+118h]
0x1800160a2  mov     rdi, rdx
0x1800160a5  test    rbx, rbx
0x1800160a8  jz      short loc_1800160C8
0x1800160aa  add     rbx, 108h
0x1800160b1  mov     rcx, rbx; SRWLock
0x1800160b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800160ba  lea     rax, [rsp+28h+arg_8]
0x1800160bf  xor     ecx, ecx
0x1800160c1  mov     esi, 1
0x1800160c6  jmp     short loc_1800160D4
0x1800160c8  xor     ebx, ebx
0x1800160ca  lea     rax, [rsp+28h+arg_0]
0x1800160cf  xor     esi, esi
0x1800160d1  lea     ecx, [rbx+2]
0x1800160d4  mov     [rdi], rbx
0x1800160d7  mov     qword ptr [rax], 0
0x1800160de  test    ecx, ecx
0x1800160e0  jz      short loc_1800160EC
0x1800160e2  lea     rcx, [rsp+28h+arg_0]
0x1800160e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800160ec  test    esi, esi
0x1800160ee  jz      short loc_1800160FA
0x1800160f0  lea     rcx, [rsp+28h+arg_8]
0x1800160f5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800160fa  mov     rbx, [rsp+28h+arg_10]
0x1800160ff  mov     rax, rdi
0x180016102  mov     rsi, [rsp+28h+arg_18]
0x180016107  add     rsp, 20h
0x18001610b  pop     rdi
0x18001610c  retn
```
