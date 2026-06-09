# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x14000fa04`
- end: `0x14000fa6d`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `105`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d248`
- `0x14000d258`
- `0x14000db74`
- `0x14000f2ec`
- `0x140013774`

## callees

- `0x14000fa04`
- `0x140012d4c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000fa3c`
- `msvcrt!memcpy_s` at `0x14000fa3c`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(__int64 a1, char a2, __int64 a3)
{
  void **v5; // rcx
  void *v6; // rsi
  __int64 result; // rax

  if ( a2 && *(_QWORD *)(a1 + 32) >= 8u )
  {
    v5 = (void **)(a1 + 8);
    v6 = *v5;
    if ( a3 )
      memcpy_s(v5, 0x10u, *v5, 2 * a3);
    Common::GlobalHeap::Free(v6);
  }
  result = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_QWORD *)(a1 + 24) = a3;
  *(_WORD *)(a1 + 2 * a3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x14000fa04  mov     [rsp+arg_0], rbx
0x14000fa09  mov     [rsp+arg_8], rsi
0x14000fa0e  push    rdi
0x14000fa0f  sub     rsp, 20h
0x14000fa13  mov     rdi, r8
0x14000fa16  mov     rbx, rcx
0x14000fa19  test    dl, dl
0x14000fa1b  jz      short loc_14000FA4A
0x14000fa1d  cmp     qword ptr [rcx+20h], 8
0x14000fa22  jb      short loc_14000FA4A
0x14000fa24  add     rcx, 8; Destination
0x14000fa28  mov     rsi, [rcx]
0x14000fa2b  test    r8, r8
0x14000fa2e  jz      short loc_14000FA42
0x14000fa30  lea     r9, [r8+r8]; SourceSize
0x14000fa34  mov     edx, 10h; DestinationSize
0x14000fa39  mov     r8, rsi; Source
0x14000fa3c  call    cs:__imp_memcpy_s
0x14000fa42  mov     rcx, rsi; P
0x14000fa45  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x14000fa4a  mov     rsi, [rsp+28h+arg_8]
0x14000fa4f  xor     eax, eax
0x14000fa51  mov     qword ptr [rbx+20h], 7
0x14000fa59  mov     [rbx+18h], rdi
0x14000fa5d  mov     [rbx+rdi*2+8], ax
0x14000fa62  mov     rbx, [rsp+28h+arg_0]
0x14000fa67  add     rsp, 20h
0x14000fa6b  pop     rdi
0x14000fa6c  retn
```
