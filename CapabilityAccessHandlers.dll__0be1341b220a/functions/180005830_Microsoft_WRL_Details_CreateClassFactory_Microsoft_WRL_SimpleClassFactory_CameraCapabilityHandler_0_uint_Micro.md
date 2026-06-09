# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005830`
- end: `0x1800058e1`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCameraCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003220`
- `0x180005830`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>,>(&v12);
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
0x180005830  push    rbx
0x180005832  push    rbp
0x180005833  push    rsi
0x180005834  push    rdi
0x180005835  sub     rsp, 38h
0x180005839  mov     rdi, r9
0x18000583c  mov     rbp, r8
0x18000583f  mov     rsi, rcx
0x180005842  mov     [rsp+58h+var_38], 0
0x18000584b  lea     rcx, [rsp+58h+var_38]
0x180005850  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VCameraCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VCameraCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<CameraCapabilityHandler,0> * *)
0x180005855  mov     ebx, eax
0x180005857  test    eax, eax
0x180005859  jns     short loc_180005876
0x18000585b  mov     rcx, [rsp+58h+var_38]
0x180005860  test    rcx, rcx
0x180005863  jz      short loc_180005872
0x180005865  mov     rdx, [rcx]
0x180005868  mov     rax, [rdx+10h]
0x18000586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005871  nop
0x180005872  mov     eax, ebx
0x180005874  jmp     short loc_1800058D8
0x180005876  mov     rbx, [rsp+58h+var_38]
0x18000587b  mov     eax, [rsi]
0x18000587d  mov     [rbx+14h], eax
0x180005880  mov     rax, [rbx]
0x180005883  mov     r8, rdi
0x180005886  mov     rdx, rbp
0x180005889  mov     rcx, rbx
0x18000588c  mov     rax, [rax]
0x18000588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005894  mov     edi, eax
0x180005896  test    byte ptr [rsi], 1
0x180005899  jz      short loc_1800058C1
0x18000589b  test    eax, eax
0x18000589d  js      short loc_1800058BD
0x18000589f  test    byte ptr [rsi], 4
0x1800058a2  jz      short loc_1800058B9
0x1800058a4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800058ab  mov     rax, [rcx]
0x1800058ae  mov     rax, [rax+8]
0x1800058b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b7  jmp     short loc_1800058C1
0x1800058b9  xor     ebx, ebx
0x1800058bb  jmp     short loc_1800058C1
0x1800058bd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x1800058c1  test    rbx, rbx
0x1800058c4  jz      short loc_1800058D6
0x1800058c6  mov     rax, [rbx]
0x1800058c9  mov     rcx, rbx
0x1800058cc  mov     rax, [rax+10h]
0x1800058d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d5  nop
0x1800058d6  mov     eax, edi
0x1800058d8  add     rsp, 38h
0x1800058dc  pop     rdi
0x1800058dd  pop     rsi
0x1800058de  pop     rbp
0x1800058df  pop     rbx
0x1800058e0  retn
```
