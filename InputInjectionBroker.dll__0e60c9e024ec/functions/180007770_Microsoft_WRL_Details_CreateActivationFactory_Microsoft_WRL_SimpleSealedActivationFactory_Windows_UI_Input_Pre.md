# Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputPenInfo,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180007770`
- end: `0x1800078a6`
- name: `??$CreateActivationFactory@V?$SimpleSealedActivationFactory@VInjectedInputPenInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e68`
- `0x1800070b0`
- `0x180007770`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputPenInfo,0>>(
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
  *(_QWORD *)v9 = &Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputPenInfo,0>::`vftable';
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
0x180007770  push    rbx
0x180007772  push    rbp
0x180007773  push    rsi
0x180007774  push    rdi
0x180007775  push    r14
0x180007777  push    r15
0x180007779  sub     rsp, 28h
0x18000777d  mov     r14, r9
0x180007780  mov     rdi, r8
0x180007783  mov     rbp, rdx
0x180007786  mov     rsi, rcx
0x180007789  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007790  mov     ecx, 28h ; '('; unsigned __int64
0x180007795  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000779a  mov     rbx, rax
0x18000779d  test    rax, rax
0x1800077a0  jnz     short loc_1800077AC
0x1800077a2  mov     eax, 8007000Eh
0x1800077a7  jmp     loc_180007899
0x1800077ac  mov     dword ptr [rax+0Ch], 1
0x1800077b3  lea     rax, ??_7?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x1800077ba  mov     [rbx], rax
0x1800077bd  mov     qword ptr [rbx+18h], 0
0x1800077c5  mov     dword ptr [rbx+20h], 4
0x1800077cc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800077d3  test    rcx, rcx
0x1800077d6  jz      short loc_1800077E5
0x1800077d8  mov     rax, [rcx]
0x1800077db  mov     rax, [rax+8]
0x1800077df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e4  nop
0x1800077e5  lea     rax, ??_7?$SimpleSealedActivationFactory@VInjectedInputPenInfo@Injection@Preview@Input@UI@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleSealedActivationFactory<Windows::UI::Input::Preview::Injection::InjectedInputPenInfo,0>::`vftable'
0x1800077ec  mov     [rbx], rax
0x1800077ef  mov     r15d, 7FFFFFFFh
0x1800077f5  jmp     short loc_180007803
0x1800077f7  lea     ecx, [rdx+1]
0x1800077fa  mov     eax, edx
0x1800077fc  lock cmpxchg [rbx+0Ch], ecx
0x180007801  jz      short loc_180007869
0x180007803  mov     edx, [rbx+0Ch]
0x180007806  cmp     edx, r15d
0x180007809  jnz     short loc_1800077F7
0x18000780b  mov     edx, r15d
0x18000780e  test    byte ptr [rbx+20h], 4
0x180007812  jnz     short loc_180007831
0x180007814  cmp     edx, 2
0x180007817  jnz     short loc_180007831
0x180007819  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007820  test    rcx, rcx
0x180007823  jz      short loc_180007831
0x180007825  mov     rax, [rcx]
0x180007828  mov     rax, [rax+8]
0x18000782c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007831  mov     rcx, rbx
0x180007834  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007839  cmp     dword ptr [rdi], 35h ; '5'
0x18000783c  jnz     short loc_18000788C
0x18000783e  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180007844  cmp     [rdi+4], eax
0x180007847  jnz     short loc_18000788C
0x180007849  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x18000784f  cmp     [rdi+8], eax
0x180007852  jnz     short loc_18000788C
0x180007854  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000785a  cmp     [rdi+0Ch], eax
0x18000785d  jnz     short loc_18000788C
0x18000785f  mov     [r14], rbx
0x180007862  test    byte ptr [rsi], 4
0x180007865  jnz     short loc_18000787F
0x180007867  jmp     short loc_180007877
0x180007869  inc     edx
0x18000786b  jmp     short loc_18000780E
0x18000786d  lea     ecx, [rax+1]
0x180007870  lock cmpxchg [rbx+0Ch], ecx
0x180007875  jz      short loc_18000787F
0x180007877  mov     eax, [rbx+0Ch]
0x18000787a  cmp     eax, r15d
0x18000787d  jnz     short loc_18000786D
0x18000787f  mov     eax, [rsi]
0x180007881  mov     [rbx+20h], eax
0x180007884  mov     [rbx+18h], rbp
0x180007888  xor     eax, eax
0x18000788a  jmp     short loc_180007899
0x18000788c  mov     rcx, rbx
0x18000788f  call    ?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180007894  mov     eax, 80004002h
0x180007899  add     rsp, 28h
0x18000789d  pop     r15
0x18000789f  pop     r14
0x1800078a1  pop     rdi
0x1800078a2  pop     rsi
0x1800078a3  pop     rbp
0x1800078a4  pop     rbx
0x1800078a5  retn
```
