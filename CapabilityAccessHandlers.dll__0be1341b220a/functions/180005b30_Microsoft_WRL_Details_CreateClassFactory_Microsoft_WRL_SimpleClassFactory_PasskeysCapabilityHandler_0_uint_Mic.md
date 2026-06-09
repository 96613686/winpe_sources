# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005b30`
- end: `0x180005be1`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VPasskeysCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005b30`
- `0x18000601c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>,>(&v12);
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
0x180005b30  push    rbx
0x180005b32  push    rbp
0x180005b33  push    rsi
0x180005b34  push    rdi
0x180005b35  sub     rsp, 38h
0x180005b39  mov     rdi, r9
0x180005b3c  mov     rbp, r8
0x180005b3f  mov     rsi, rcx
0x180005b42  mov     [rsp+58h+var_38], 0
0x180005b4b  lea     rcx, [rsp+58h+var_38]
0x180005b50  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VPasskeysCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VPasskeysCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<PasskeysCapabilityHandler,0> * *)
0x180005b55  mov     ebx, eax
0x180005b57  test    eax, eax
0x180005b59  jns     short loc_180005B76
0x180005b5b  mov     rcx, [rsp+58h+var_38]
0x180005b60  test    rcx, rcx
0x180005b63  jz      short loc_180005B72
0x180005b65  mov     rdx, [rcx]
0x180005b68  mov     rax, [rdx+10h]
0x180005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b71  nop
0x180005b72  mov     eax, ebx
0x180005b74  jmp     short loc_180005BD8
0x180005b76  mov     rbx, [rsp+58h+var_38]
0x180005b7b  mov     eax, [rsi]
0x180005b7d  mov     [rbx+14h], eax
0x180005b80  mov     rax, [rbx]
0x180005b83  mov     r8, rdi
0x180005b86  mov     rdx, rbp
0x180005b89  mov     rcx, rbx
0x180005b8c  mov     rax, [rax]
0x180005b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b94  mov     edi, eax
0x180005b96  test    byte ptr [rsi], 1
0x180005b99  jz      short loc_180005BC1
0x180005b9b  test    eax, eax
0x180005b9d  js      short loc_180005BBD
0x180005b9f  test    byte ptr [rsi], 4
0x180005ba2  jz      short loc_180005BB9
0x180005ba4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005bab  mov     rax, [rcx]
0x180005bae  mov     rax, [rax+8]
0x180005bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb7  jmp     short loc_180005BC1
0x180005bb9  xor     ebx, ebx
0x180005bbb  jmp     short loc_180005BC1
0x180005bbd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005bc1  test    rbx, rbx
0x180005bc4  jz      short loc_180005BD6
0x180005bc6  mov     rax, [rbx]
0x180005bc9  mov     rcx, rbx
0x180005bcc  mov     rax, [rax+10h]
0x180005bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd5  nop
0x180005bd6  mov     eax, edi
0x180005bd8  add     rsp, 38h
0x180005bdc  pop     rdi
0x180005bdd  pop     rsi
0x180005bde  pop     rbp
0x180005bdf  pop     rbx
0x180005be0  retn
```
