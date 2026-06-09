# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800026e0`
- end: `0x1800027b4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCBatteryNotificationManager@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001c0c`
- `0x1800026e0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>::`vftable';
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
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
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
0x1800026e0  push    rbx
0x1800026e2  push    rbp
0x1800026e3  push    rsi
0x1800026e4  push    rdi
0x1800026e5  sub     rsp, 28h
0x1800026e9  mov     rdi, r9
0x1800026ec  mov     rbp, r8
0x1800026ef  mov     rsi, rcx
0x1800026f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800026f9  mov     ecx, 18h; unsigned __int64
0x1800026fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002703  mov     rbx, rax
0x180002706  test    rax, rax
0x180002709  jz      loc_1800027A6
0x18000270f  mov     dword ptr [rax+0Ch], 1
0x180002716  mov     dword ptr [rax+14h], 4
0x18000271d  lea     rax, ??_7?$SimpleClassFactory@VCBatteryNotificationManager@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CBatteryNotificationManager,0>::`vftable'
0x180002724  mov     [rbx], rax
0x180002727  mov     rcx, rbx
0x18000272a  mov     rax, cs:off_18000E0C0
0x180002731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002736  nop
0x180002737  mov     rax, [rbx]
0x18000273a  mov     rcx, rbx
0x18000273d  mov     rax, [rax+10h]
0x180002741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002746  nop
0x180002747  mov     eax, [rsi]
0x180002749  mov     [rbx+14h], eax
0x18000274c  mov     rax, [rbx]
0x18000274f  mov     r8, rdi
0x180002752  mov     rdx, rbp
0x180002755  mov     rcx, rbx
0x180002758  mov     rax, [rax]
0x18000275b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002760  mov     edi, eax
0x180002762  test    byte ptr [rsi], 1
0x180002765  jz      short loc_18000278D
0x180002767  test    eax, eax
0x180002769  js      short loc_180002789
0x18000276b  test    byte ptr [rsi], 4
0x18000276e  jz      short loc_180002785
0x180002770  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002777  mov     rax, [rcx]
0x18000277a  mov     rax, [rax+8]
0x18000277e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002783  jmp     short loc_18000278D
0x180002785  xor     ebx, ebx
0x180002787  jmp     short loc_18000278D
0x180002789  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000278d  test    rbx, rbx
0x180002790  jz      short loc_1800027A2
0x180002792  mov     rax, [rbx]
0x180002795  mov     rcx, rbx
0x180002798  mov     rax, [rax+10h]
0x18000279c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a1  nop
0x1800027a2  mov     eax, edi
0x1800027a4  jmp     short loc_1800027AB
0x1800027a6  mov     eax, 8007000Eh
0x1800027ab  add     rsp, 28h
0x1800027af  pop     rdi
0x1800027b0  pop     rsi
0x1800027b1  pop     rbp
0x1800027b2  pop     rbx
0x1800027b3  retn
```
