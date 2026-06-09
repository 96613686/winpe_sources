# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005bf0`
- end: `0x180005ca1`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VSensorsCustomCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004084`
- `0x180005bf0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>,>(&v12);
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
0x180005bf0  push    rbx
0x180005bf2  push    rbp
0x180005bf3  push    rsi
0x180005bf4  push    rdi
0x180005bf5  sub     rsp, 38h
0x180005bf9  mov     rdi, r9
0x180005bfc  mov     rbp, r8
0x180005bff  mov     rsi, rcx
0x180005c02  mov     [rsp+58h+var_38], 0
0x180005c0b  lea     rcx, [rsp+58h+var_38]
0x180005c10  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VSensorsCustomCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VSensorsCustomCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<SensorsCustomCapabilityHandler,0> * *)
0x180005c15  mov     ebx, eax
0x180005c17  test    eax, eax
0x180005c19  jns     short loc_180005C36
0x180005c1b  mov     rcx, [rsp+58h+var_38]
0x180005c20  test    rcx, rcx
0x180005c23  jz      short loc_180005C32
0x180005c25  mov     rdx, [rcx]
0x180005c28  mov     rax, [rdx+10h]
0x180005c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c31  nop
0x180005c32  mov     eax, ebx
0x180005c34  jmp     short loc_180005C98
0x180005c36  mov     rbx, [rsp+58h+var_38]
0x180005c3b  mov     eax, [rsi]
0x180005c3d  mov     [rbx+14h], eax
0x180005c40  mov     rax, [rbx]
0x180005c43  mov     r8, rdi
0x180005c46  mov     rdx, rbp
0x180005c49  mov     rcx, rbx
0x180005c4c  mov     rax, [rax]
0x180005c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c54  mov     edi, eax
0x180005c56  test    byte ptr [rsi], 1
0x180005c59  jz      short loc_180005C81
0x180005c5b  test    eax, eax
0x180005c5d  js      short loc_180005C7D
0x180005c5f  test    byte ptr [rsi], 4
0x180005c62  jz      short loc_180005C79
0x180005c64  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005c6b  mov     rax, [rcx]
0x180005c6e  mov     rax, [rax+8]
0x180005c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c77  jmp     short loc_180005C81
0x180005c79  xor     ebx, ebx
0x180005c7b  jmp     short loc_180005C81
0x180005c7d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005c81  test    rbx, rbx
0x180005c84  jz      short loc_180005C96
0x180005c86  mov     rax, [rbx]
0x180005c89  mov     rcx, rbx
0x180005c8c  mov     rax, [rax+10h]
0x180005c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c95  nop
0x180005c96  mov     eax, edi
0x180005c98  add     rsp, 38h
0x180005c9c  pop     rdi
0x180005c9d  pop     rsi
0x180005c9e  pop     rbp
0x180005c9f  pop     rbx
0x180005ca0  retn
```
