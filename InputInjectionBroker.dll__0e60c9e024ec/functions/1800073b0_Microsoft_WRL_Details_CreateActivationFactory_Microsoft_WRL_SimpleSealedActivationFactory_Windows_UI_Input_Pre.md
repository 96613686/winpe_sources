# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800073b0`
- end: `0x1800074e6`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800070b0`
- `0x1800073b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo,0>>(
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
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo,0>::`vftable';
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
0x1800073b0  push    rbx
0x1800073b2  push    rbp
0x1800073b3  push    rsi
0x1800073b4  push    rdi
0x1800073b5  push    r14
0x1800073b7  push    r15
0x1800073b9  sub     rsp, 28h
0x1800073bd  mov     r14, r9
0x1800073c0  mov     rdi, r8
0x1800073c3  mov     rbp, rdx
0x1800073c6  mov     rsi, rcx
0x1800073c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800073d0  mov     ecx, 28h ; '('; unsigned __int64
0x1800073d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800073da  mov     rbx, rax
0x1800073dd  test    rax, rax
0x1800073e0  jnz     short loc_1800073EC
0x1800073e2  mov     eax, 8007000Eh
0x1800073e7  jmp     loc_1800074D9
0x1800073ec  mov     dword ptr [rax+0Ch], 1
0x1800073f3  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x1800073fa  mov     [rbx], rax
0x1800073fd  mov     qword ptr [rbx+18h], 0
0x180007405  mov     dword ptr [rbx+20h], 4
0x18000740c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007413  test    rcx, rcx
0x180007416  jz      short loc_180007425
0x180007418  mov     rax, [rcx]
0x18000741b  mov     rax, [rax+8]
0x18000741f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007424  nop
0x180007425  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputButtonInfo,0>::`vftable'
0x18000742c  mov     [rbx], rax
0x18000742f  mov     r15d, 7FFFFFFFh
0x180007435  jmp     short loc_180007443
0x180007437  lea     ecx, [rdx+1]
0x18000743a  mov     eax, edx
0x18000743c  lock cmpxchg [rbx+0Ch], ecx
0x180007441  jz      short loc_1800074A9
0x180007443  mov     edx, [rbx+0Ch]
0x180007446  cmp     edx, r15d
0x180007449  jnz     short loc_180007437
0x18000744b  mov     edx, r15d
0x18000744e  test    byte ptr [rbx+20h], 4
0x180007452  jnz     short loc_180007471
0x180007454  cmp     edx, 2
0x180007457  jnz     short loc_180007471
0x180007459  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007460  test    rcx, rcx
0x180007463  jz      short loc_180007471
0x180007465  mov     rax, [rcx]
0x180007468  mov     rax, [rax+8]
0x18000746c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007471  mov     rcx, rbx
0x180007474  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007479  cmp     dword ptr [rdi], 35h ; '5'
0x18000747c  jnz     short loc_1800074CC
0x18000747e  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180007484  cmp     [rdi+4], eax
0x180007487  jnz     short loc_1800074CC
0x180007489  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000748f  cmp     [rdi+8], eax
0x180007492  jnz     short loc_1800074CC
0x180007494  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000749a  cmp     [rdi+0Ch], eax
0x18000749d  jnz     short loc_1800074CC
0x18000749f  mov     [r14], rbx
0x1800074a2  test    byte ptr [rsi], 4
0x1800074a5  jnz     short loc_1800074BF
0x1800074a7  jmp     short loc_1800074B7
0x1800074a9  inc     edx
0x1800074ab  jmp     short loc_18000744E
0x1800074ad  lea     ecx, [rax+1]
0x1800074b0  lock cmpxchg [rbx+0Ch], ecx
0x1800074b5  jz      short loc_1800074BF
0x1800074b7  mov     eax, [rbx+0Ch]
0x1800074ba  cmp     eax, r15d
0x1800074bd  jnz     short loc_1800074AD
0x1800074bf  mov     eax, [rsi]
0x1800074c1  mov     [rbx+20h], eax
0x1800074c4  mov     [rbx+18h], rbp
0x1800074c8  xor     eax, eax
0x1800074ca  jmp     short loc_1800074D9
0x1800074cc  mov     rcx, rbx
0x1800074cf  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800074d4  mov     eax, 80004002h
0x1800074d9  add     rsp, 28h
0x1800074dd  pop     r15
0x1800074df  pop     r14
0x1800074e1  pop     rdi
0x1800074e2  pop     rsi
0x1800074e3  pop     rbp
0x1800074e4  pop     rbx
0x1800074e5  retn
```
