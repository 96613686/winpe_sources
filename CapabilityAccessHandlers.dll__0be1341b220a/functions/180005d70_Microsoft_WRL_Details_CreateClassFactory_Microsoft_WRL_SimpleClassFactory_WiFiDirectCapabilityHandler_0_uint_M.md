# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005d70`
- end: `0x180005e21`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VWiFiDirectCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004134`
- `0x180005d70`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>,>(&v12);
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
0x180005d70  push    rbx
0x180005d72  push    rbp
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  sub     rsp, 38h
0x180005d79  mov     rdi, r9
0x180005d7c  mov     rbp, r8
0x180005d7f  mov     rsi, rcx
0x180005d82  mov     [rsp+58h+var_38], 0
0x180005d8b  lea     rcx, [rsp+58h+var_38]
0x180005d90  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VWiFiDirectCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VWiFiDirectCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<WiFiDirectCapabilityHandler,0> * *)
0x180005d95  mov     ebx, eax
0x180005d97  test    eax, eax
0x180005d99  jns     short loc_180005DB6
0x180005d9b  mov     rcx, [rsp+58h+var_38]
0x180005da0  test    rcx, rcx
0x180005da3  jz      short loc_180005DB2
0x180005da5  mov     rdx, [rcx]
0x180005da8  mov     rax, [rdx+10h]
0x180005dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db1  nop
0x180005db2  mov     eax, ebx
0x180005db4  jmp     short loc_180005E18
0x180005db6  mov     rbx, [rsp+58h+var_38]
0x180005dbb  mov     eax, [rsi]
0x180005dbd  mov     [rbx+14h], eax
0x180005dc0  mov     rax, [rbx]
0x180005dc3  mov     r8, rdi
0x180005dc6  mov     rdx, rbp
0x180005dc9  mov     rcx, rbx
0x180005dcc  mov     rax, [rax]
0x180005dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd4  mov     edi, eax
0x180005dd6  test    byte ptr [rsi], 1
0x180005dd9  jz      short loc_180005E01
0x180005ddb  test    eax, eax
0x180005ddd  js      short loc_180005DFD
0x180005ddf  test    byte ptr [rsi], 4
0x180005de2  jz      short loc_180005DF9
0x180005de4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005deb  mov     rax, [rcx]
0x180005dee  mov     rax, [rax+8]
0x180005df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df7  jmp     short loc_180005E01
0x180005df9  xor     ebx, ebx
0x180005dfb  jmp     short loc_180005E01
0x180005dfd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005e01  test    rbx, rbx
0x180005e04  jz      short loc_180005E16
0x180005e06  mov     rax, [rbx]
0x180005e09  mov     rcx, rbx
0x180005e0c  mov     rax, [rax+10h]
0x180005e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e15  nop
0x180005e16  mov     eax, edi
0x180005e18  add     rsp, 38h
0x180005e1c  pop     rdi
0x180005e1d  pop     rsi
0x180005e1e  pop     rbp
0x180005e1f  pop     rbx
0x180005e20  retn
```
