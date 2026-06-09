# Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)

- ea: `0x180022f38`
- end: `0x18002306d`
- name: `?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ`
- size: `309`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180023074`
- `0x1800247fc`
- `0x18003484c`
- `0x180034c3c`

## callees

- `0x180003cb0`
- `0x18000aa04`
- `0x18001c330`
- `0x18001c368`
- `0x180020a10`
- `0x18002166c`
- `0x180022f38`
- `0x180023894`
- `0x18002bf2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f59`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(
        __int64 *a1)
{
  _DWORD *v2; // rdi
  volatile signed __int32 *v3; // rax
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rcx
  char *v7; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v8; // [rsp+30h] [rbp-28h]
  RTL_SRWLOCK *v9; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v10; // [rsp+70h] [rbp+18h]

  AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_lock);
  v9 = &Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_lock;
  *a1 = 0;
  a1[1] = 0;
  if ( qword_1800612D0 && std::_Ref_count_base::_Incref_nz(qword_1800612D0) )
  {
    *a1 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_instance;
    a1[1] = (__int64)qword_1800612D0;
  }
  if ( !*a1 )
  {
    v2 = operator new(0x98u);
    v10 = v2;
    *(_OWORD *)v2 = 0;
    v2[2] = 1;
    v2[3] = 1;
    *(_QWORD *)v2 = &std::_Ref_count_obj2<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>::`vftable';
    std::_Construct_in_place<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,>((_QWORD *)v2 + 2);
    v7 = (char *)(v2 + 4);
    v8 = (std::_Ref_count_base *)v2;
    Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::SingletonInitialize((Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore *)(v2 + 4));
    std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(a1, &v7);
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    v3 = (volatile signed __int32 *)a1[1];
    if ( v3 )
    {
      v4 = *a1;
      _InterlockedIncrement(v3 + 3);
    }
    else
    {
      v4 = 0;
    }
    Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_instance = v4;
    v5 = qword_1800612D0;
    qword_1800612D0 = (std::_Ref_count_base *)v3;
    if ( v5 )
      std::_Ref_count_base::_Decwref(v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  return a1;
}

```

## disassembly

```asm
0x180022f38  mov     [rsp+arg_0], rcx
0x180022f3d  push    rbx
0x180022f3e  push    rsi
0x180022f3f  push    rdi
0x180022f40  sub     rsp, 40h
0x180022f44  mov     rsi, rcx
0x180022f47  mov     [rsp+58h+var_38], 0
0x180022f4f  lea     rbx, ?s_lock@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_lock
0x180022f56  mov     rcx, rbx; SRWLock
0x180022f59  call    cs:__imp_AcquireSRWLockExclusive
0x180022f5f  mov     [rsp+58h+arg_8], rbx
0x180022f64  mov     qword ptr [rsi], 0
0x180022f6b  mov     qword ptr [rsi+8], 0
0x180022f73  mov     rcx, cs:qword_1800612D0; this
0x180022f7a  test    rcx, rcx
0x180022f7d  jz      short loc_180022F9D
0x180022f7f  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180022f84  test    al, al
0x180022f86  jz      short loc_180022F9D
0x180022f88  mov     rax, cs:?s_instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@0V?$weak_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@A; std::weak_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore> Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_instance
0x180022f8f  mov     [rsi], rax
0x180022f92  mov     rax, cs:qword_1800612D0
0x180022f99  mov     [rsi+8], rax
0x180022f9d  mov     [rsp+58h+var_38], 1
0x180022fa5  cmp     qword ptr [rsi], 0
0x180022fa9  jnz     loc_180023057
0x180022faf  mov     ecx, 98h; Size
0x180022fb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fb9  mov     rdi, rax
0x180022fbc  mov     [rsp+58h+arg_10], rax
0x180022fc1  xorps   xmm0, xmm0
0x180022fc4  movups  xmmword ptr [rax], xmm0
0x180022fc7  mov     dword ptr [rax+8], 1
0x180022fce  mov     dword ptr [rax+0Ch], 1
0x180022fd5  lea     rax, ??_7?$_Ref_count_obj2@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>::`vftable'
0x180022fdc  mov     [rdi], rax
0x180022fdf  lea     rbx, [rdi+10h]
0x180022fe3  mov     rcx, rbx
0x180022fe6  call    ??$_Construct_in_place@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@$$V@std@@YAXAEAVCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@Z; std::_Construct_in_place<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,>(Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore &)
0x180022feb  nop
0x180022fec  mov     [rsp+58h+var_30], rbx
0x180022ff1  mov     [rsp+58h+var_28], rdi
0x180022ff6  mov     [rsp+58h+var_38], 7
0x180022ffe  mov     rcx, rbx; this
0x180023001  call    ?SingletonInitialize@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::SingletonInitialize(void)
0x180023006  lea     rdx, [rsp+58h+var_30]
0x18002300b  mov     rcx, rsi
0x18002300e  call    ??4?$shared_ptr@VCapabilityHandler@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> &&)
0x180023013  nop
0x180023014  mov     rcx, [rsp+58h+var_28]; this
0x180023019  test    rcx, rcx
0x18002301c  jz      short loc_180023023
0x18002301e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023023  mov     rax, [rsi+8]
0x180023027  test    rax, rax
0x18002302a  jz      short loc_180023035
0x18002302c  mov     rcx, [rsi]
0x18002302f  lock inc dword ptr [rax+0Ch]
0x180023033  jmp     short loc_180023037
0x180023035  xor     ecx, ecx
0x180023037  mov     cs:?s_instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@0V?$weak_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@A, rcx; std::weak_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore> Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::s_instance
0x18002303e  mov     rcx, cs:qword_1800612D0; this
0x180023045  mov     cs:qword_1800612D0, rax
0x18002304c  test    rcx, rcx
0x18002304f  jz      short loc_180023057
0x180023051  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180023056  nop
0x180023057  lea     rcx, [rsp+58h+arg_8]
0x18002305c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180023061  mov     rax, rsi
0x180023064  add     rsp, 40h
0x180023068  pop     rdi
0x180023069  pop     rsi
0x18002306a  pop     rbx
0x18002306b  retn
```
