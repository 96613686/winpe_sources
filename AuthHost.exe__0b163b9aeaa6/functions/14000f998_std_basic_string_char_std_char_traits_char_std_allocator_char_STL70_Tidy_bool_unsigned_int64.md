# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x14000f998`
- end: `0x14000f9fd`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `101`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d238`
- `0x14000d350`
- `0x14000f208`
- `0x14000f5a8`
- `0x14001370f`

## callees

- `0x14000f998`
- `0x140012d4c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f9ce`
- `msvcrt!memcpy_s` at `0x14000f9ce`

## pseudocode

```c
void __fastcall std::string::_Tidy(__int64 a1, char a2, rsize_t a3)
{
  void **v5; // rcx
  void *v6; // rsi

  if ( a2 && *(_QWORD *)(a1 + 32) >= 0x10u )
  {
    v5 = (void **)(a1 + 8);
    v6 = *v5;
    if ( a3 )
      memcpy_s(v5, 0x10u, *v5, a3);
    Common::GlobalHeap::Free(v6);
  }
  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = a3;
  *(_BYTE *)(a3 + a1 + 8) = 0;
}

```

## disassembly

```asm
0x14000f998  mov     [rsp+arg_0], rbx
0x14000f99d  mov     [rsp+arg_8], rsi
0x14000f9a2  push    rdi
0x14000f9a3  sub     rsp, 20h
0x14000f9a7  mov     rdi, r8
0x14000f9aa  mov     rbx, rcx
0x14000f9ad  test    dl, dl
0x14000f9af  jz      short loc_14000F9DC
0x14000f9b1  mov     edx, 10h; DestinationSize
0x14000f9b6  cmp     [rcx+20h], rdx
0x14000f9ba  jb      short loc_14000F9DC
0x14000f9bc  add     rcx, 8; Destination
0x14000f9c0  mov     rsi, [rcx]
0x14000f9c3  test    r8, r8
0x14000f9c6  jz      short loc_14000F9D4
0x14000f9c8  mov     r9, r8; SourceSize
0x14000f9cb  mov     r8, rsi; Source
0x14000f9ce  call    cs:__imp_memcpy_s
0x14000f9d4  mov     rcx, rsi; P
0x14000f9d7  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x14000f9dc  mov     rsi, [rsp+28h+arg_8]
0x14000f9e1  mov     qword ptr [rbx+20h], 0Fh
0x14000f9e9  mov     [rbx+18h], rdi
0x14000f9ed  mov     byte ptr [rdi+rbx+8], 0
0x14000f9f2  mov     rbx, [rsp+28h+arg_0]
0x14000f9f7  add     rsp, 20h
0x14000f9fb  pop     rdi
0x14000f9fc  retn
```
