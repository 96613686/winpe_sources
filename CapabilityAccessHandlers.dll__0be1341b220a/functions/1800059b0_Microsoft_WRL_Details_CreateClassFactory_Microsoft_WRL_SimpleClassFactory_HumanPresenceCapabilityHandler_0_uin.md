# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1800059b0`
- end: `0x180005a61`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VHumanPresenceCapabilityHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800059b0`
- `0x180005ee8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>>(
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
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>,>(&v12);
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
0x1800059b0  push    rbx
0x1800059b2  push    rbp
0x1800059b3  push    rsi
0x1800059b4  push    rdi
0x1800059b5  sub     rsp, 38h
0x1800059b9  mov     rdi, r9
0x1800059bc  mov     rbp, r8
0x1800059bf  mov     rsi, rcx
0x1800059c2  mov     [rsp+58h+var_38], 0
0x1800059cb  lea     rcx, [rsp+58h+var_38]
0x1800059d0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VHumanPresenceCapabilityHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VHumanPresenceCapabilityHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>,Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0>,>(Microsoft::WRL::SimpleClassFactory<HumanPresenceCapabilityHandler,0> * *)
0x1800059d5  mov     ebx, eax
0x1800059d7  test    eax, eax
0x1800059d9  jns     short loc_1800059F6
0x1800059db  mov     rcx, [rsp+58h+var_38]
0x1800059e0  test    rcx, rcx
0x1800059e3  jz      short loc_1800059F2
0x1800059e5  mov     rdx, [rcx]
0x1800059e8  mov     rax, [rdx+10h]
0x1800059ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f1  nop
0x1800059f2  mov     eax, ebx
0x1800059f4  jmp     short loc_180005A58
0x1800059f6  mov     rbx, [rsp+58h+var_38]
0x1800059fb  mov     eax, [rsi]
0x1800059fd  mov     [rbx+14h], eax
0x180005a00  mov     rax, [rbx]
0x180005a03  mov     r8, rdi
0x180005a06  mov     rdx, rbp
0x180005a09  mov     rcx, rbx
0x180005a0c  mov     rax, [rax]
0x180005a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a14  mov     edi, eax
0x180005a16  test    byte ptr [rsi], 1
0x180005a19  jz      short loc_180005A41
0x180005a1b  test    eax, eax
0x180005a1d  js      short loc_180005A3D
0x180005a1f  test    byte ptr [rsi], 4
0x180005a22  jz      short loc_180005A39
0x180005a24  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005a2b  mov     rax, [rcx]
0x180005a2e  mov     rax, [rax+8]
0x180005a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a37  jmp     short loc_180005A41
0x180005a39  xor     ebx, ebx
0x180005a3b  jmp     short loc_180005A41
0x180005a3d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180005a41  test    rbx, rbx
0x180005a44  jz      short loc_180005A56
0x180005a46  mov     rax, [rbx]
0x180005a49  mov     rcx, rbx
0x180005a4c  mov     rax, [rax+10h]
0x180005a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a55  nop
0x180005a56  mov     eax, edi
0x180005a58  add     rsp, 38h
0x180005a5c  pop     rdi
0x180005a5d  pop     rsi
0x180005a5e  pop     rbp
0x180005a5f  pop     rbx
0x180005a60  retn
```
