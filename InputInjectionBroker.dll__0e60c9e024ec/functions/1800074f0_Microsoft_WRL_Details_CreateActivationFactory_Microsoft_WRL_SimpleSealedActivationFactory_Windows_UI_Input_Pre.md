# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800074f0`
- end: `0x180007626`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectedInputKeyboardInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800070b0`
- `0x1800074f0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo,0>>(
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
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo,0>::`vftable';
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
0x1800074f0  push    rbx
0x1800074f2  push    rbp
0x1800074f3  push    rsi
0x1800074f4  push    rdi
0x1800074f5  push    r14
0x1800074f7  push    r15
0x1800074f9  sub     rsp, 28h
0x1800074fd  mov     r14, r9
0x180007500  mov     rdi, r8
0x180007503  mov     rbp, rdx
0x180007506  mov     rsi, rcx
0x180007509  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007510  mov     ecx, 28h ; '('; unsigned __int64
0x180007515  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000751a  mov     rbx, rax
0x18000751d  test    rax, rax
0x180007520  jnz     short loc_18000752C
0x180007522  mov     eax, 8007000Eh
0x180007527  jmp     loc_180007619
0x18000752c  mov     dword ptr [rax+0Ch], 1
0x180007533  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x18000753a  mov     [rbx], rax
0x18000753d  mov     qword ptr [rbx+18h], 0
0x180007545  mov     dword ptr [rbx+20h], 4
0x18000754c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007553  test    rcx, rcx
0x180007556  jz      short loc_180007565
0x180007558  mov     rax, [rcx]
0x18000755b  mov     rax, [rax+8]
0x18000755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007564  nop
0x180007565  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectedInputKeyboardInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputKeyboardInfo,0>::`vftable'
0x18000756c  mov     [rbx], rax
0x18000756f  mov     r15d, 7FFFFFFFh
0x180007575  jmp     short loc_180007583
0x180007577  lea     ecx, [rdx+1]
0x18000757a  mov     eax, edx
0x18000757c  lock cmpxchg [rbx+0Ch], ecx
0x180007581  jz      short loc_1800075E9
0x180007583  mov     edx, [rbx+0Ch]
0x180007586  cmp     edx, r15d
0x180007589  jnz     short loc_180007577
0x18000758b  mov     edx, r15d
0x18000758e  test    byte ptr [rbx+20h], 4
0x180007592  jnz     short loc_1800075B1
0x180007594  cmp     edx, 2
0x180007597  jnz     short loc_1800075B1
0x180007599  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800075a0  test    rcx, rcx
0x1800075a3  jz      short loc_1800075B1
0x1800075a5  mov     rax, [rcx]
0x1800075a8  mov     rax, [rax+8]
0x1800075ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b1  mov     rcx, rbx
0x1800075b4  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800075b9  cmp     dword ptr [rdi], 35h ; '5'
0x1800075bc  jnz     short loc_18000760C
0x1800075be  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x1800075c4  cmp     [rdi+4], eax
0x1800075c7  jnz     short loc_18000760C
0x1800075c9  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x1800075cf  cmp     [rdi+8], eax
0x1800075d2  jnz     short loc_18000760C
0x1800075d4  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x1800075da  cmp     [rdi+0Ch], eax
0x1800075dd  jnz     short loc_18000760C
0x1800075df  mov     [r14], rbx
0x1800075e2  test    byte ptr [rsi], 4
0x1800075e5  jnz     short loc_1800075FF
0x1800075e7  jmp     short loc_1800075F7
0x1800075e9  inc     edx
0x1800075eb  jmp     short loc_18000758E
0x1800075ed  lea     ecx, [rax+1]
0x1800075f0  lock cmpxchg [rbx+0Ch], ecx
0x1800075f5  jz      short loc_1800075FF
0x1800075f7  mov     eax, [rbx+0Ch]
0x1800075fa  cmp     eax, r15d
0x1800075fd  jnz     short loc_1800075ED
0x1800075ff  mov     eax, [rsi]
0x180007601  mov     [rbx+20h], eax
0x180007604  mov     [rbx+18h], rbp
0x180007608  xor     eax, eax
0x18000760a  jmp     short loc_180007619
0x18000760c  mov     rcx, rbx
0x18000760f  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007614  mov     eax, 80004002h
0x180007619  add     rsp, 28h
0x18000761d  pop     r15
0x18000761f  pop     r14
0x180007621  pop     rdi
0x180007622  pop     rsi
0x180007623  pop     rbp
0x180007624  pop     rbx
0x180007625  retn
```
