# GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)

- ea: `0x18000a65c`
- end: `0x18000a6d9`
- name: `?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007818`
- `0x18000b8f8`
- `0x18000dd4c`
- `0x18000e184`

## callees

- `0x18000a65c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall GetXmlAttribute(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  int v7; // eax
  int v8; // edx

  *a4 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, a2, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v7 == 1 )
    {
      v8 = -2147024809;
      if ( !a3 )
        return (unsigned int)-2147023728;
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)a1 + 128LL))(a1, a4, 0);
      if ( v8 >= 0 )
        return 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a65c  mov     [rsp+arg_0], rbx
0x18000a661  mov     [rsp+arg_8], rsi
0x18000a666  push    rdi
0x18000a667  sub     rsp, 20h
0x18000a66b  mov     rsi, r9
0x18000a66e  mov     edi, r8d
0x18000a671  mov     rbx, rcx
0x18000a674  mov     qword ptr [r9], 0
0x18000a67b  mov     rax, [rcx]
0x18000a67e  xor     r8d, r8d
0x18000a681  mov     rax, [rax+50h]
0x18000a685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a68a  mov     edx, eax
0x18000a68c  test    eax, eax
0x18000a68e  js      short loc_18000A6C7
0x18000a690  cmp     eax, 1
0x18000a693  jnz     short loc_18000A6A6
0x18000a695  mov     edx, 80070057h
0x18000a69a  mov     eax, 80070490h
0x18000a69f  test    edi, edi
0x18000a6a1  cmovz   edx, eax
0x18000a6a4  jmp     short loc_18000A6C7
0x18000a6a6  mov     rax, [rbx]
0x18000a6a9  xor     r8d, r8d
0x18000a6ac  mov     rdx, rsi
0x18000a6af  mov     rcx, rbx
0x18000a6b2  mov     rax, [rax+80h]
0x18000a6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6be  mov     edx, eax
0x18000a6c0  xor     eax, eax
0x18000a6c2  test    edx, edx
0x18000a6c4  cmovns  edx, eax
0x18000a6c7  mov     eax, edx
0x18000a6c9  mov     rbx, [rsp+28h+arg_0]
0x18000a6ce  mov     rsi, [rsp+28h+arg_8]
0x18000a6d3  add     rsp, 20h
0x18000a6d7  pop     rdi
0x18000a6d8  retn
```
