# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800078b0`
- end: `0x1800079e6`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800070b0`
- `0x1800078b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo,0>>(
        _BYTE *a1,
        __int64 a2,
        _DWORD *a3,
        _QWORD *a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  signed __int32 v11; // edx
  __int64 v12; // rdx
  __int64 v13; // rdx
  signed __int32 v14; // eax

  v8 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v8[3] = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *((_QWORD *)v8 + 3) = 0;
  v8[8] = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo,0>::`vftable';
  do
  {
    v11 = v9[3];
    if ( v11 == 0x7FFFFFFF )
    {
      v12 = 0x7FFFFFFF;
      goto LABEL_9;
    }
  }
  while ( v11 != _InterlockedCompareExchange(v9 + 3, v11 + 1, v11) );
  v12 = (unsigned int)(v11 + 1);
LABEL_9:
  if ( (v9[8] & 4) == 0 && (_DWORD)v12 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    v9,
    v12);
  if ( *a3 == 53
    && a3[1] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
    && a3[2] == *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
    && a3[3] == *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
  {
    *a4 = v9;
    if ( (*a1 & 4) == 0 )
    {
      do
        v14 = v9[3];
      while ( v14 != 0x7FFFFFFF && v14 != _InterlockedCompareExchange(v9 + 3, v14 + 1, v14) );
    }
    v9[8] = *(_DWORD *)a1;
    *((_QWORD *)v9 + 3) = a2;
    return 0;
  }
  else
  {
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
      v9,
      v13);
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x1800078b0  push    rbx
0x1800078b2  push    rbp
0x1800078b3  push    rsi
0x1800078b4  push    rdi
0x1800078b5  push    r14
0x1800078b7  push    r15
0x1800078b9  sub     rsp, 28h
0x1800078bd  mov     r14, r9
0x1800078c0  mov     rdi, r8
0x1800078c3  mov     rbp, rdx
0x1800078c6  mov     rsi, rcx
0x1800078c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800078d0  mov     ecx, 28h ; '('; unsigned __int64
0x1800078d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800078da  mov     rbx, rax
0x1800078dd  test    rax, rax
0x1800078e0  jnz     short loc_1800078EC
0x1800078e2  mov     eax, 8007000Eh
0x1800078e7  jmp     loc_1800079D9
0x1800078ec  mov     dword ptr [rax+0Ch], 1
0x1800078f3  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x1800078fa  mov     [rbx], rax
0x1800078fd  mov     qword ptr [rbx+18h], 0
0x180007905  mov     dword ptr [rbx+20h], 4
0x18000790c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007913  test    rcx, rcx
0x180007916  jz      short loc_180007925
0x180007918  mov     rax, [rcx]
0x18000791b  mov     rax, [rax+8]
0x18000791f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007924  nop
0x180007925  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputTouchInfo,0>::`vftable'
0x18000792c  mov     [rbx], rax
0x18000792f  mov     r15d, 7FFFFFFFh
0x180007935  jmp     short loc_180007943
0x180007937  lea     ecx, [rdx+1]
0x18000793a  mov     eax, edx
0x18000793c  lock cmpxchg [rbx+0Ch], ecx
0x180007941  jz      short loc_1800079A9
0x180007943  mov     edx, [rbx+0Ch]
0x180007946  cmp     edx, r15d
0x180007949  jnz     short loc_180007937
0x18000794b  mov     edx, r15d
0x18000794e  test    byte ptr [rbx+20h], 4
0x180007952  jnz     short loc_180007971
0x180007954  cmp     edx, 2
0x180007957  jnz     short loc_180007971
0x180007959  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007960  test    rcx, rcx
0x180007963  jz      short loc_180007971
0x180007965  mov     rax, [rcx]
0x180007968  mov     rax, [rax+8]
0x18000796c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007971  mov     rcx, rbx
0x180007974  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007979  cmp     dword ptr [rdi], 35h ; '5'
0x18000797c  jnz     short loc_1800079CC
0x18000797e  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180007984  cmp     [rdi+4], eax
0x180007987  jnz     short loc_1800079CC
0x180007989  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000798f  cmp     [rdi+8], eax
0x180007992  jnz     short loc_1800079CC
0x180007994  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000799a  cmp     [rdi+0Ch], eax
0x18000799d  jnz     short loc_1800079CC
0x18000799f  mov     [r14], rbx
0x1800079a2  test    byte ptr [rsi], 4
0x1800079a5  jnz     short loc_1800079BF
0x1800079a7  jmp     short loc_1800079B7
0x1800079a9  inc     edx
0x1800079ab  jmp     short loc_18000794E
0x1800079ad  lea     ecx, [rax+1]
0x1800079b0  lock cmpxchg [rbx+0Ch], ecx
0x1800079b5  jz      short loc_1800079BF
0x1800079b7  mov     eax, [rbx+0Ch]
0x1800079ba  cmp     eax, r15d
0x1800079bd  jnz     short loc_1800079AD
0x1800079bf  mov     eax, [rsi]
0x1800079c1  mov     [rbx+20h], eax
0x1800079c4  mov     [rbx+18h], rbp
0x1800079c8  xor     eax, eax
0x1800079ca  jmp     short loc_1800079D9
0x1800079cc  mov     rcx, rbx
0x1800079cf  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800079d4  mov     eax, 80004002h
0x1800079d9  add     rsp, 28h
0x1800079dd  pop     r15
0x1800079df  pop     r14
0x1800079e1  pop     rdi
0x1800079e2  pop     rsi
0x1800079e3  pop     rbp
0x1800079e4  pop     rbx
0x1800079e5  retn
```
