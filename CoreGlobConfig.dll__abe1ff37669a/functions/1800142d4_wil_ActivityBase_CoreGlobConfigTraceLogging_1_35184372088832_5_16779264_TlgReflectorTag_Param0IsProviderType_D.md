# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x1800142d4`
- end: `0x180014368`
- name: `?Destroy@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `148`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800118c0`
- `0x180011a6c`
- `0x180011a98`
- `0x180011b4c`
- `0x180011b78`
- `0x180011ba4`
- `0x180011c64`

## callees

- `0x180011488`
- `0x1800142d4`
- `0x18001608c`
- `0x180018470`
- `0x1800194f4`
- `0x18001eb74`

## pseudocode

```c
void __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v1; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_7;
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v6);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  if ( v3 )
  {
LABEL_7:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      LODWORD(v6) = v4[22];
      v5 = 2147942974LL;
      if ( (int)v6 < 0 )
        v5 = (unsigned int)v6;
      wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v4,
        v5,
        &v6);
      wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x1800142d4  mov     [rsp+arg_8], rbx
0x1800142d9  mov     [rsp+arg_10], rsi
0x1800142de  push    rdi
0x1800142df  sub     rsp, 20h
0x1800142e3  lea     rdi, [rcx+118h]
0x1800142ea  mov     rbx, rcx
0x1800142ed  cmp     qword ptr [rdi], 0
0x1800142f1  jz      short loc_180014329
0x1800142f3  lea     rdx, [rsp+28h+arg_0]
0x1800142f8  call    ?LockExclusive@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800142fd  mov     rax, [rdi]
0x180014300  test    rax, rax
0x180014303  jz      short loc_18001430F
0x180014305  cmp     dword ptr [rax], 1
0x180014308  jnz     short loc_18001430F
0x18001430a  mov     sil, 1
0x18001430d  jmp     short loc_18001431A
0x18001430f  xor     sil, sil
0x180014312  mov     rcx, rdi
0x180014315  call    ?reset@?$shared_object@V?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001431a  lea     rcx, [rsp+28h+arg_0]
0x18001431f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014324  test    sil, sil
0x180014327  jz      short loc_180014358
0x180014329  mov     rcx, [rbx+110h]
0x180014330  cmp     dword ptr [rcx], 1
0x180014333  jnz     short loc_180014358
0x180014335  mov     eax, [rcx+58h]
0x180014338  lea     r8, [rsp+28h+arg_0]
0x18001433d  test    eax, eax
0x18001433f  mov     dword ptr [rsp+28h+arg_0], eax
0x180014343  mov     edx, 8007023Eh
0x180014348  cmovs   edx, eax
0x18001434b  call    ?SetStopResult@?$ActivityData@VCoreGlobConfigTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CoreGlobConfigTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180014350  mov     rcx, rbx
0x180014353  call    ?ReportStopActivity@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180014358  mov     rbx, [rsp+28h+arg_8]
0x18001435d  mov     rsi, [rsp+28h+arg_10]
0x180014362  add     rsp, 20h
0x180014366  pop     rdi
0x180014367  retn
```
