# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(_GUID const &,void * *)

- ea: `0x140008300`
- end: `0x140008356`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008300`
- `0x140009374`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(
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
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || (unsigned int)InlineIsEqualGUID(v4, &GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4) )
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
0x140008300  push    rbx
0x140008302  sub     rsp, 20h
0x140008306  mov     r10, rdx
0x140008309  mov     r9, rcx
0x14000830c  xor     ebx, ebx
0x14000830e  mov     [r8], rbx
0x140008311  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140008318  mov     rcx, r10
0x14000831b  call    InlineIsEqualGUID
0x140008320  test    eax, eax
0x140008322  jnz     short loc_14000833B
0x140008324  lea     rdx, _GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4
0x14000832b  call    InlineIsEqualGUID
0x140008330  test    eax, eax
0x140008332  jnz     short loc_14000833B
0x140008334  mov     ebx, 80004002h
0x140008339  jmp     short loc_14000834E
0x14000833b  mov     [r8], r9
0x14000833e  mov     rax, [r9]
0x140008341  mov     rcx, r9
0x140008344  mov     rax, [rax+8]
0x140008348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000834d  nop
0x14000834e  mov     eax, ebx
0x140008350  add     rsp, 20h
0x140008354  pop     rbx
0x140008355  retn
```
