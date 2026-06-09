# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005cb0`
- end: `0x180005d61`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VSmsCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cb0`
- `0x1800060b8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>,>(&v12);
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
0x180005cb0  push    rbx
0x180005cb2  push    rbp
0x180005cb3  push    rsi
0x180005cb4  push    rdi
0x180005cb5  sub     rsp, 38h
0x180005cb9  mov     rdi, r9
0x180005cbc  mov     rbp, r8
0x180005cbf  mov     rsi, rcx
0x180005cc2  mov     [rsp+58h+var_38], 0
0x180005ccb  lea     rcx, [rsp+58h+var_38]
0x180005cd0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VSmsCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VSmsCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<SmsCapabilityHandler,0> * *)
0x180005cd5  mov     ebx, eax
0x180005cd7  test    eax, eax
0x180005cd9  jns     short loc_180005CF6
0x180005cdb  mov     rcx, [rsp+58h+var_38]
0x180005ce0  test    rcx, rcx
0x180005ce3  jz      short loc_180005CF2
0x180005ce5  mov     rdx, [rcx]
0x180005ce8  mov     rax, [rdx+10h]
0x180005cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf1  nop
0x180005cf2  mov     eax, ebx
0x180005cf4  jmp     short loc_180005D58
0x180005cf6  mov     rbx, [rsp+58h+var_38]
0x180005cfb  mov     eax, [rsi]
0x180005cfd  mov     [rbx+14h], eax
0x180005d00  mov     rax, [rbx]
0x180005d03  mov     r8, rdi
0x180005d06  mov     rdx, rbp
0x180005d09  mov     rcx, rbx
0x180005d0c  mov     rax, [rax]
0x180005d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d14  mov     edi, eax
0x180005d16  test    byte ptr [rsi], 1
0x180005d19  jz      short loc_180005D41
0x180005d1b  test    eax, eax
0x180005d1d  js      short loc_180005D3D
0x180005d1f  test    byte ptr [rsi], 4
0x180005d22  jz      short loc_180005D39
0x180005d24  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005d2b  mov     rax, [rcx]
0x180005d2e  mov     rax, [rax+8]
0x180005d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d37  jmp     short loc_180005D41
0x180005d39  xor     ebx, ebx
0x180005d3b  jmp     short loc_180005D41
0x180005d3d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005d41  test    rbx, rbx
0x180005d44  jz      short loc_180005D56
0x180005d46  mov     rax, [rbx]
0x180005d49  mov     rcx, rbx
0x180005d4c  mov     rax, [rax+10h]
0x180005d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d55  nop
0x180005d56  mov     eax, edi
0x180005d58  add     rsp, 38h
0x180005d5c  pop     rdi
0x180005d5d  pop     rsi
0x180005d5e  pop     rbp
0x180005d5f  pop     rbx
0x180005d60  retn
```
