# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008c70`
- end: `0x180008cc6`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800017d0`
- `0x180008c70`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9

  v3 = 0;
  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1)
    || (unsigned int)InlineIsEqualGUID(v4, &GUID_c5e24244_3c21_4b41_8b86_7e671a675702, v5, v6) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
    return (unsigned int)-2147467262;
  }
  return v3;
}

```

## disassembly

```asm
0x180008c70  push    rbx
0x180008c72  sub     rsp, 20h
0x180008c76  mov     r10, rdx
0x180008c79  mov     r9, rcx
0x180008c7c  xor     ebx, ebx
0x180008c7e  mov     [r8], rbx
0x180008c81  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008c88  mov     rcx, r10
0x180008c8b  call    InlineIsEqualGUID
0x180008c90  test    eax, eax
0x180008c92  jnz     short loc_180008CAB
0x180008c94  lea     rdx, _GUID_c5e24244_3c21_4b41_8b86_7e671a675702
0x180008c9b  call    InlineIsEqualGUID
0x180008ca0  test    eax, eax
0x180008ca2  jnz     short loc_180008CAB
0x180008ca4  mov     ebx, 80004002h
0x180008ca9  jmp     short loc_180008CBE
0x180008cab  mov     [r8], r9
0x180008cae  mov     rax, [r9]
0x180008cb1  mov     rcx, r9
0x180008cb4  mov     rax, [rax+8]
0x180008cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbd  nop
0x180008cbe  mov     eax, ebx
0x180008cc0  add     rsp, 20h
0x180008cc4  pop     rbx
0x180008cc5  retn
```
