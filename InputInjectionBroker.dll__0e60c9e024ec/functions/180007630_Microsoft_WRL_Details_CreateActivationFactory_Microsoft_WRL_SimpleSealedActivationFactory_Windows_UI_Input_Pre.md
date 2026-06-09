# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180007630`
- end: `0x180007766`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectedInputMouseInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800070b0`
- `0x180007630`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo,0>>(
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
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo,0>::`vftable';
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
0x180007630  push    rbx
0x180007632  push    rbp
0x180007633  push    rsi
0x180007634  push    rdi
0x180007635  push    r14
0x180007637  push    r15
0x180007639  sub     rsp, 28h
0x18000763d  mov     r14, r9
0x180007640  mov     rdi, r8
0x180007643  mov     rbp, rdx
0x180007646  mov     rsi, rcx
0x180007649  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007650  mov     ecx, 28h ; '('; unsigned __int64
0x180007655  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000765a  mov     rbx, rax
0x18000765d  test    rax, rax
0x180007660  jnz     short loc_18000766C
0x180007662  mov     eax, 8007000Eh
0x180007667  jmp     loc_180007759
0x18000766c  mov     dword ptr [rax+0Ch], 1
0x180007673  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x18000767a  mov     [rbx], rax
0x18000767d  mov     qword ptr [rbx+18h], 0
0x180007685  mov     dword ptr [rbx+20h], 4
0x18000768c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007693  test    rcx, rcx
0x180007696  jz      short loc_1800076A5
0x180007698  mov     rax, [rcx]
0x18000769b  mov     rax, [rax+8]
0x18000769f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a4  nop
0x1800076a5  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectedInputMouseInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputMouseInfo,0>::`vftable'
0x1800076ac  mov     [rbx], rax
0x1800076af  mov     r15d, 7FFFFFFFh
0x1800076b5  jmp     short loc_1800076C3
0x1800076b7  lea     ecx, [rdx+1]
0x1800076ba  mov     eax, edx
0x1800076bc  lock cmpxchg [rbx+0Ch], ecx
0x1800076c1  jz      short loc_180007729
0x1800076c3  mov     edx, [rbx+0Ch]
0x1800076c6  cmp     edx, r15d
0x1800076c9  jnz     short loc_1800076B7
0x1800076cb  mov     edx, r15d
0x1800076ce  test    byte ptr [rbx+20h], 4
0x1800076d2  jnz     short loc_1800076F1
0x1800076d4  cmp     edx, 2
0x1800076d7  jnz     short loc_1800076F1
0x1800076d9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800076e0  test    rcx, rcx
0x1800076e3  jz      short loc_1800076F1
0x1800076e5  mov     rax, [rcx]
0x1800076e8  mov     rax, [rax+8]
0x1800076ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f1  mov     rcx, rbx
0x1800076f4  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800076f9  cmp     dword ptr [rdi], 35h ; '5'
0x1800076fc  jnz     short loc_18000774C
0x1800076fe  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180007704  cmp     [rdi+4], eax
0x180007707  jnz     short loc_18000774C
0x180007709  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000770f  cmp     [rdi+8], eax
0x180007712  jnz     short loc_18000774C
0x180007714  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000771a  cmp     [rdi+0Ch], eax
0x18000771d  jnz     short loc_18000774C
0x18000771f  mov     [r14], rbx
0x180007722  test    byte ptr [rsi], 4
0x180007725  jnz     short loc_18000773F
0x180007727  jmp     short loc_180007737
0x180007729  inc     edx
0x18000772b  jmp     short loc_1800076CE
0x18000772d  lea     ecx, [rax+1]
0x180007730  lock cmpxchg [rbx+0Ch], ecx
0x180007735  jz      short loc_18000773F
0x180007737  mov     eax, [rbx+0Ch]
0x18000773a  cmp     eax, r15d
0x18000773d  jnz     short loc_18000772D
0x18000773f  mov     eax, [rsi]
0x180007741  mov     [rbx+20h], eax
0x180007744  mov     [rbx+18h], rbp
0x180007748  xor     eax, eax
0x18000774a  jmp     short loc_180007759
0x18000774c  mov     rcx, rbx
0x18000774f  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007754  mov     eax, 80004002h
0x180007759  add     rsp, 28h
0x18000775d  pop     r15
0x18000775f  pop     r14
0x180007761  pop     rdi
0x180007762  pop     rsi
0x180007763  pop     rbp
0x180007764  pop     rbx
0x180007765  retn
```
