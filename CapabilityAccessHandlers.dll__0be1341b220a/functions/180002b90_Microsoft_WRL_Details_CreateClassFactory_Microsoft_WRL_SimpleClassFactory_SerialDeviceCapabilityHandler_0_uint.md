# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002b90`
- end: `0x180002c41`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VSerialDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b90`
- `0x180002c48`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>,>(&v12);
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
0x180002b90  push    rbx
0x180002b92  push    rbp
0x180002b93  push    rsi
0x180002b94  push    rdi
0x180002b95  sub     rsp, 38h
0x180002b99  mov     rdi, r9
0x180002b9c  mov     rbp, r8
0x180002b9f  mov     rsi, rcx
0x180002ba2  mov     [rsp+58h+var_38], 0
0x180002bab  lea     rcx, [rsp+58h+var_38]
0x180002bb0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VSerialDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VSerialDeviceCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<SerialDeviceCapabilityHandler,0> * *)
0x180002bb5  mov     ebx, eax
0x180002bb7  test    eax, eax
0x180002bb9  jns     short loc_180002BD6
0x180002bbb  mov     rcx, [rsp+58h+var_38]
0x180002bc0  test    rcx, rcx
0x180002bc3  jz      short loc_180002BD2
0x180002bc5  mov     rdx, [rcx]
0x180002bc8  mov     rax, [rdx+10h]
0x180002bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd1  nop
0x180002bd2  mov     eax, ebx
0x180002bd4  jmp     short loc_180002C38
0x180002bd6  mov     rbx, [rsp+58h+var_38]
0x180002bdb  mov     eax, [rsi]
0x180002bdd  mov     [rbx+14h], eax
0x180002be0  mov     rax, [rbx]
0x180002be3  mov     r8, rdi
0x180002be6  mov     rdx, rbp
0x180002be9  mov     rcx, rbx
0x180002bec  mov     rax, [rax]
0x180002bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf4  mov     edi, eax
0x180002bf6  test    byte ptr [rsi], 1
0x180002bf9  jz      short loc_180002C21
0x180002bfb  test    eax, eax
0x180002bfd  js      short loc_180002C1D
0x180002bff  test    byte ptr [rsi], 4
0x180002c02  jz      short loc_180002C19
0x180002c04  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002c0b  mov     rax, [rcx]
0x180002c0e  mov     rax, [rax+8]
0x180002c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c17  jmp     short loc_180002C21
0x180002c19  xor     ebx, ebx
0x180002c1b  jmp     short loc_180002C21
0x180002c1d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180002c21  test    rbx, rbx
0x180002c24  jz      short loc_180002C36
0x180002c26  mov     rax, [rbx]
0x180002c29  mov     rcx, rbx
0x180002c2c  mov     rax, [rax+10h]
0x180002c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c35  nop
0x180002c36  mov     eax, edi
0x180002c38  add     rsp, 38h
0x180002c3c  pop     rdi
0x180002c3d  pop     rsi
0x180002c3e  pop     rbp
0x180002c3f  pop     rbx
0x180002c40  retn
```
