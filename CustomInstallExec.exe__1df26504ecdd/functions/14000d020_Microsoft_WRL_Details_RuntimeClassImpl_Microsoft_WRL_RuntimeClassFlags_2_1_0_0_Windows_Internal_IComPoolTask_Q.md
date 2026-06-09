# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000d020`
- end: `0x14000d076`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000cdec`
- `0x14000d020`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
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
0x14000d020  push    rbx
0x14000d022  sub     rsp, 20h
0x14000d026  mov     r10, rdx
0x14000d029  mov     r9, rcx
0x14000d02c  xor     ebx, ebx
0x14000d02e  mov     [r8], rbx
0x14000d031  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000d038  mov     rcx, r10; struct _GUID *
0x14000d03b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d040  test    eax, eax
0x14000d042  jnz     short loc_14000D05B
0x14000d044  lea     rdx, _GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4; struct _GUID *
0x14000d04b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d050  test    eax, eax
0x14000d052  jnz     short loc_14000D05B
0x14000d054  mov     ebx, 80004002h
0x14000d059  jmp     short loc_14000D06E
0x14000d05b  mov     [r8], r9
0x14000d05e  mov     rax, [r9]
0x14000d061  mov     rcx, r9
0x14000d064  mov     rax, [rax+8]
0x14000d068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d06d  nop
0x14000d06e  mov     eax, ebx
0x14000d070  add     rsp, 20h
0x14000d074  pop     rbx
0x14000d075  retn
```
