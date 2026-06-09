# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180003070`
- end: `0x180003121`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VLocationCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003070`
- `0x180003128`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>,>(&v12);
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
0x180003070  push    rbx
0x180003072  push    rbp
0x180003073  push    rsi
0x180003074  push    rdi
0x180003075  sub     rsp, 38h
0x180003079  mov     rdi, r9
0x18000307c  mov     rbp, r8
0x18000307f  mov     rsi, rcx
0x180003082  mov     [rsp+58h+var_38], 0
0x18000308b  lea     rcx, [rsp+58h+var_38]
0x180003090  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VLocationCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VLocationCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<LocationCapabilityHandler,0> * *)
0x180003095  mov     ebx, eax
0x180003097  test    eax, eax
0x180003099  jns     short loc_1800030B6
0x18000309b  mov     rcx, [rsp+58h+var_38]
0x1800030a0  test    rcx, rcx
0x1800030a3  jz      short loc_1800030B2
0x1800030a5  mov     rdx, [rcx]
0x1800030a8  mov     rax, [rdx+10h]
0x1800030ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b1  nop
0x1800030b2  mov     eax, ebx
0x1800030b4  jmp     short loc_180003118
0x1800030b6  mov     rbx, [rsp+58h+var_38]
0x1800030bb  mov     eax, [rsi]
0x1800030bd  mov     [rbx+14h], eax
0x1800030c0  mov     rax, [rbx]
0x1800030c3  mov     r8, rdi
0x1800030c6  mov     rdx, rbp
0x1800030c9  mov     rcx, rbx
0x1800030cc  mov     rax, [rax]
0x1800030cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d4  mov     edi, eax
0x1800030d6  test    byte ptr [rsi], 1
0x1800030d9  jz      short loc_180003101
0x1800030db  test    eax, eax
0x1800030dd  js      short loc_1800030FD
0x1800030df  test    byte ptr [rsi], 4
0x1800030e2  jz      short loc_1800030F9
0x1800030e4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800030eb  mov     rax, [rcx]
0x1800030ee  mov     rax, [rax+8]
0x1800030f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f7  jmp     short loc_180003101
0x1800030f9  xor     ebx, ebx
0x1800030fb  jmp     short loc_180003101
0x1800030fd  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180003101  test    rbx, rbx
0x180003104  jz      short loc_180003116
0x180003106  mov     rax, [rbx]
0x180003109  mov     rcx, rbx
0x18000310c  mov     rax, [rax+10h]
0x180003110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003115  nop
0x180003116  mov     eax, edi
0x180003118  add     rsp, 38h
0x18000311c  pop     rdi
0x18000311d  pop     rsi
0x18000311e  pop     rbp
0x18000311f  pop     rbx
0x180003120  retn
```
