# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008d70`
- end: `0x180008de2`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008df0`

## callees

- `0x1800017d0`
- `0x180008d70`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9

  v3 = 0;
  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1) )
  {
    *v5 = v6;
    goto LABEL_8;
  }
  if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_c5e24244_3c21_4b41_8b86_7e671a675702, v5, v6) )
  {
LABEL_5:
    *v8 = v6;
LABEL_8:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return v3;
  }
  if ( (unsigned int)InlineIsEqualGUID(v7, &GUID_8d540bdd_316f_4204_ac18_799fffd29f12, v8, v6) )
  {
    v6 = v9 + 8;
    goto LABEL_5;
  }
  return (unsigned int)-2147467262;
}

```

## disassembly

```asm
0x180008d70  push    rbx
0x180008d72  sub     rsp, 20h
0x180008d76  mov     r10, rdx
0x180008d79  mov     r9, rcx
0x180008d7c  xor     ebx, ebx
0x180008d7e  mov     [r8], rbx
0x180008d81  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008d88  mov     rcx, r10
0x180008d8b  call    InlineIsEqualGUID
0x180008d90  test    eax, eax
0x180008d92  jnz     short loc_180008DC7
0x180008d94  lea     rdx, _GUID_c5e24244_3c21_4b41_8b86_7e671a675702
0x180008d9b  call    InlineIsEqualGUID
0x180008da0  test    eax, eax
0x180008da2  jnz     short loc_180008DB8
0x180008da4  lea     rdx, _GUID_8d540bdd_316f_4204_ac18_799fffd29f12
0x180008dab  call    InlineIsEqualGUID
0x180008db0  test    eax, eax
0x180008db2  jz      short loc_180008DC0
0x180008db4  add     r9, 8
0x180008db8  mov     rax, r9
0x180008dbb  mov     [r8], rax
0x180008dbe  jmp     short loc_180008DCA
0x180008dc0  mov     ebx, 80004002h
0x180008dc5  jmp     short loc_180008DDA
0x180008dc7  mov     [r8], r9
0x180008dca  mov     rax, [r9]
0x180008dcd  mov     rcx, r9
0x180008dd0  mov     rax, [rax+8]
0x180008dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd9  nop
0x180008dda  mov     eax, ebx
0x180008ddc  add     rsp, 20h
0x180008de0  pop     rbx
0x180008de1  retn
```
