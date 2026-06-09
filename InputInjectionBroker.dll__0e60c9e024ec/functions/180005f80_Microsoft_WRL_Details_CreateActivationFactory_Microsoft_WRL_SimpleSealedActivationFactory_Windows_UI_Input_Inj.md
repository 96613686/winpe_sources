# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005f80`
- end: `0x1800060b6`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectionBrokerImpl@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x180005f80`
- `0x1800070b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>>(
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
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>::`vftable';
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
0x180005f80  push    rbx
0x180005f82  push    rbp
0x180005f83  push    rsi
0x180005f84  push    rdi
0x180005f85  push    r14
0x180005f87  push    r15
0x180005f89  sub     rsp, 28h
0x180005f8d  mov     r14, r9
0x180005f90  mov     rdi, r8
0x180005f93  mov     rbp, rdx
0x180005f96  mov     rsi, rcx
0x180005f99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005fa0  mov     ecx, 28h ; '('; unsigned __int64
0x180005fa5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005faa  mov     rbx, rax
0x180005fad  test    rax, rax
0x180005fb0  jnz     short loc_180005FBC
0x180005fb2  mov     eax, 8007000Eh
0x180005fb7  jmp     loc_1800060A9
0x180005fbc  mov     dword ptr [rax+0Ch], 1
0x180005fc3  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180005fca  mov     [rbx], rax
0x180005fcd  mov     qword ptr [rbx+18h], 0
0x180005fd5  mov     dword ptr [rbx+20h], 4
0x180005fdc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005fe3  test    rcx, rcx
0x180005fe6  jz      short loc_180005FF5
0x180005fe8  mov     rax, [rcx]
0x180005feb  mov     rax, [rax+8]
0x180005fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff4  nop
0x180005ff5  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectionBrokerImpl@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::InjectionBrokerImpl,0>::`vftable'
0x180005ffc  mov     [rbx], rax
0x180005fff  mov     r15d, 7FFFFFFFh
0x180006005  jmp     short loc_180006013
0x180006007  lea     ecx, [rdx+1]
0x18000600a  mov     eax, edx
0x18000600c  lock cmpxchg [rbx+0Ch], ecx
0x180006011  jz      short loc_180006079
0x180006013  mov     edx, [rbx+0Ch]
0x180006016  cmp     edx, r15d
0x180006019  jnz     short loc_180006007
0x18000601b  mov     edx, r15d
0x18000601e  test    byte ptr [rbx+20h], 4
0x180006022  jnz     short loc_180006041
0x180006024  cmp     edx, 2
0x180006027  jnz     short loc_180006041
0x180006029  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006030  test    rcx, rcx
0x180006033  jz      short loc_180006041
0x180006035  mov     rax, [rcx]
0x180006038  mov     rax, [rax+8]
0x18000603c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006041  mov     rcx, rbx
0x180006044  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180006049  cmp     dword ptr [rdi], 35h ; '5'
0x18000604c  jnz     short loc_18000609C
0x18000604e  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180006054  cmp     [rdi+4], eax
0x180006057  jnz     short loc_18000609C
0x180006059  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000605f  cmp     [rdi+8], eax
0x180006062  jnz     short loc_18000609C
0x180006064  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000606a  cmp     [rdi+0Ch], eax
0x18000606d  jnz     short loc_18000609C
0x18000606f  mov     [r14], rbx
0x180006072  test    byte ptr [rsi], 4
0x180006075  jnz     short loc_18000608F
0x180006077  jmp     short loc_180006087
0x180006079  inc     edx
0x18000607b  jmp     short loc_18000601E
0x18000607d  lea     ecx, [rax+1]
0x180006080  lock cmpxchg [rbx+0Ch], ecx
0x180006085  jz      short loc_18000608F
0x180006087  mov     eax, [rbx+0Ch]
0x18000608a  cmp     eax, r15d
0x18000608d  jnz     short loc_18000607D
0x18000608f  mov     eax, [rsi]
0x180006091  mov     [rbx+20h], eax
0x180006094  mov     [rbx+18h], rbp
0x180006098  xor     eax, eax
0x18000609a  jmp     short loc_1800060A9
0x18000609c  mov     rcx, rbx
0x18000609f  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800060a4  mov     eax, 80004002h
0x1800060a9  add     rsp, 28h
0x1800060ad  pop     r15
0x1800060af  pop     r14
0x1800060b1  pop     rdi
0x1800060b2  pop     rsi
0x1800060b3  pop     rbp
0x1800060b4  pop     rbx
0x1800060b5  retn
```
