# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x140006ff0`
- end: `0x1400070c4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCloudExperienceHostWAMExecuteCommand@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400025d8`
- `0x140006ff0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>::`vftable';
  ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  v8[5] = *a1;
  v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
  v10 = v9;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    if ( v9 < 0 )
    {
      v8[5] &= 0xFFFFFFFA;
    }
    else if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
    else
    {
      v8 = 0;
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x140006ff0  push    rbx
0x140006ff2  push    rbp
0x140006ff3  push    rsi
0x140006ff4  push    rdi
0x140006ff5  sub     rsp, 28h
0x140006ff9  mov     rdi, r9
0x140006ffc  mov     rbp, r8
0x140006fff  mov     rsi, rcx
0x140007002  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007009  mov     ecx, 18h; unsigned __int64
0x14000700e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140007013  mov     rbx, rax
0x140007016  test    rax, rax
0x140007019  jz      loc_1400070B6
0x14000701f  mov     dword ptr [rax+0Ch], 1
0x140007026  mov     dword ptr [rax+14h], 4
0x14000702d  lea     rax, ??_7?$SimpleClassFactory@VCloudExperienceHostWAMExecuteCommand@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CloudExperienceHostWAMExecuteCommand,0>::`vftable'
0x140007034  mov     [rbx], rax
0x140007037  mov     rcx, rbx
0x14000703a  mov     rax, cs:off_140011C68
0x140007041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007046  nop
0x140007047  mov     rax, [rbx]
0x14000704a  mov     rcx, rbx
0x14000704d  mov     rax, [rax+10h]
0x140007051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007056  nop
0x140007057  mov     eax, [rsi]
0x140007059  mov     [rbx+14h], eax
0x14000705c  mov     rax, [rbx]
0x14000705f  mov     r8, rdi
0x140007062  mov     rdx, rbp
0x140007065  mov     rcx, rbx
0x140007068  mov     rax, [rax]
0x14000706b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007070  mov     edi, eax
0x140007072  test    byte ptr [rsi], 1
0x140007075  jz      short loc_14000709D
0x140007077  test    eax, eax
0x140007079  js      short loc_140007099
0x14000707b  test    byte ptr [rsi], 4
0x14000707e  jz      short loc_140007095
0x140007080  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140007087  mov     rax, [rcx]
0x14000708a  mov     rax, [rax+8]
0x14000708e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007093  jmp     short loc_14000709D
0x140007095  xor     ebx, ebx
0x140007097  jmp     short loc_14000709D
0x140007099  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x14000709d  test    rbx, rbx
0x1400070a0  jz      short loc_1400070B2
0x1400070a2  mov     rax, [rbx]
0x1400070a5  mov     rcx, rbx
0x1400070a8  mov     rax, [rax+10h]
0x1400070ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070b1  nop
0x1400070b2  mov     eax, edi
0x1400070b4  jmp     short loc_1400070BB
0x1400070b6  mov     eax, 8007000Eh
0x1400070bb  add     rsp, 28h
0x1400070bf  pop     rdi
0x1400070c0  pop     rsi
0x1400070c1  pop     rbp
0x1400070c2  pop     rbx
0x1400070c3  retn
```
