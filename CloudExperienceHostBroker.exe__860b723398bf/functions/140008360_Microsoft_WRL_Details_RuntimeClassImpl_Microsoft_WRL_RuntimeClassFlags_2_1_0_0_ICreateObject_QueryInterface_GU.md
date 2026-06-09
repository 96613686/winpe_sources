# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(_GUID const &,void * *)

- ea: `0x140008360`
- end: `0x1400083b6`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008360`
- `0x140009374`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::QueryInterface(
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
    || (unsigned int)InlineIsEqualGUID(v4, &GUID_75121952_e0d0_43e5_9380_1d80483acf72) )
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
0x140008360  push    rbx
0x140008362  sub     rsp, 20h
0x140008366  mov     r10, rdx
0x140008369  mov     r9, rcx
0x14000836c  xor     ebx, ebx
0x14000836e  mov     [r8], rbx
0x140008371  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140008378  mov     rcx, r10
0x14000837b  call    InlineIsEqualGUID
0x140008380  test    eax, eax
0x140008382  jnz     short loc_14000839B
0x140008384  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x14000838b  call    InlineIsEqualGUID
0x140008390  test    eax, eax
0x140008392  jnz     short loc_14000839B
0x140008394  mov     ebx, 80004002h
0x140008399  jmp     short loc_1400083AE
0x14000839b  mov     [r8], r9
0x14000839e  mov     rax, [r9]
0x1400083a1  mov     rcx, r9
0x1400083a4  mov     rax, [rax+8]
0x1400083a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083ad  nop
0x1400083ae  mov     eax, ebx
0x1400083b0  add     rsp, 20h
0x1400083b4  pop     rbx
0x1400083b5  retn
```
