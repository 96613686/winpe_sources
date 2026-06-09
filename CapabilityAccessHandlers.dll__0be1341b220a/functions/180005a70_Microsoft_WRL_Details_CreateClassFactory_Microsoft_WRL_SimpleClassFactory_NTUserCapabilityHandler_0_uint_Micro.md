# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005a70`
- end: `0x180005b21`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VNTUserCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005a70`
- `0x180005f80`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>,>(&v12);
  if ( v7 >= 0 )
  {
    v9 = v12;
    v12[5] = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180005a70  push    rbx
0x180005a72  push    rbp
0x180005a73  push    rsi
0x180005a74  push    rdi
0x180005a75  sub     rsp, 38h
0x180005a79  mov     rdi, r9
0x180005a7c  mov     rbp, r8
0x180005a7f  mov     rsi, rcx
0x180005a82  mov     [rsp+58h+var_38], 0
0x180005a8b  lea     rcx, [rsp+58h+var_38]
0x180005a90  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VNTUserCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VNTUserCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<NTUserCapabilityHandler,0> * *)
0x180005a95  mov     ebx, eax
0x180005a97  test    eax, eax
0x180005a99  jns     short loc_180005AB6
0x180005a9b  mov     rcx, [rsp+58h+var_38]
0x180005aa0  test    rcx, rcx
0x180005aa3  jz      short loc_180005AB2
0x180005aa5  mov     rdx, [rcx]
0x180005aa8  mov     rax, [rdx+10h]
0x180005aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab1  nop
0x180005ab2  mov     eax, ebx
0x180005ab4  jmp     short loc_180005B18
0x180005ab6  mov     rbx, [rsp+58h+var_38]
0x180005abb  mov     eax, [rsi]
0x180005abd  mov     [rbx+14h], eax
0x180005ac0  mov     rax, [rbx]
0x180005ac3  mov     r8, rdi
0x180005ac6  mov     rdx, rbp
0x180005ac9  mov     rcx, rbx
0x180005acc  mov     rax, [rax]
0x180005acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad4  mov     edi, eax
0x180005ad6  test    byte ptr [rsi], 1
0x180005ad9  jz      short loc_180005B01
0x180005adb  test    eax, eax
0x180005add  js      short loc_180005AFD
0x180005adf  test    byte ptr [rsi], 4
0x180005ae2  jz      short loc_180005AF9
0x180005ae4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005aeb  mov     rax, [rcx]
0x180005aee  mov     rax, [rax+8]
0x180005af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af7  jmp     short loc_180005B01
0x180005af9  xor     ebx, ebx
0x180005afb  jmp     short loc_180005B01
0x180005afd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005b01  test    rbx, rbx
0x180005b04  jz      short loc_180005B16
0x180005b06  mov     rax, [rbx]
0x180005b09  mov     rcx, rbx
0x180005b0c  mov     rax, [rax+10h]
0x180005b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b15  nop
0x180005b16  mov     eax, edi
0x180005b18  add     rsp, 38h
0x180005b1c  pop     rdi
0x180005b1d  pop     rsi
0x180005b1e  pop     rbp
0x180005b1f  pop     rbx
0x180005b20  retn
```
