# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002a40`
- end: `0x180002af1`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VUsbDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a40`
- `0x180002af8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>,>(&v12);
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
0x180002a40  push    rbx
0x180002a42  push    rbp
0x180002a43  push    rsi
0x180002a44  push    rdi
0x180002a45  sub     rsp, 38h
0x180002a49  mov     rdi, r9
0x180002a4c  mov     rbp, r8
0x180002a4f  mov     rsi, rcx
0x180002a52  mov     [rsp+58h+var_38], 0
0x180002a5b  lea     rcx, [rsp+58h+var_38]
0x180002a60  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VUsbDeviceCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VUsbDeviceCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<UsbDeviceCapabilityHandler,0> * *)
0x180002a65  mov     ebx, eax
0x180002a67  test    eax, eax
0x180002a69  jns     short loc_180002A86
0x180002a6b  mov     rcx, [rsp+58h+var_38]
0x180002a70  test    rcx, rcx
0x180002a73  jz      short loc_180002A82
0x180002a75  mov     rdx, [rcx]
0x180002a78  mov     rax, [rdx+10h]
0x180002a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a81  nop
0x180002a82  mov     eax, ebx
0x180002a84  jmp     short loc_180002AE8
0x180002a86  mov     rbx, [rsp+58h+var_38]
0x180002a8b  mov     eax, [rsi]
0x180002a8d  mov     [rbx+14h], eax
0x180002a90  mov     rax, [rbx]
0x180002a93  mov     r8, rdi
0x180002a96  mov     rdx, rbp
0x180002a99  mov     rcx, rbx
0x180002a9c  mov     rax, [rax]
0x180002a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa4  mov     edi, eax
0x180002aa6  test    byte ptr [rsi], 1
0x180002aa9  jz      short loc_180002AD1
0x180002aab  test    eax, eax
0x180002aad  js      short loc_180002ACD
0x180002aaf  test    byte ptr [rsi], 4
0x180002ab2  jz      short loc_180002AC9
0x180002ab4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002abb  mov     rax, [rcx]
0x180002abe  mov     rax, [rax+8]
0x180002ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac7  jmp     short loc_180002AD1
0x180002ac9  xor     ebx, ebx
0x180002acb  jmp     short loc_180002AD1
0x180002acd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180002ad1  test    rbx, rbx
0x180002ad4  jz      short loc_180002AE6
0x180002ad6  mov     rax, [rbx]
0x180002ad9  mov     rcx, rbx
0x180002adc  mov     rax, [rax+10h]
0x180002ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae5  nop
0x180002ae6  mov     eax, edi
0x180002ae8  add     rsp, 38h
0x180002aec  pop     rdi
0x180002aed  pop     rsi
0x180002aee  pop     rbp
0x180002aef  pop     rbx
0x180002af0  retn
```
