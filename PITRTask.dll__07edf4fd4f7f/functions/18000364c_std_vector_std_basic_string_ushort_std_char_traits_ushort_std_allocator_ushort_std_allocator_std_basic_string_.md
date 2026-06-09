# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x18000364c`
- end: `0x1800036ca`
- name: `??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a4f0`
- `0x180010cba`
- `0x180010ccc`

## callees

- `0x18000364c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003676`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000369d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003676`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000369d`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::~vector<std::wstring>(__int64 a1)
{
  void **v1; // rbx
  void **v3; // rsi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( (unsigned __int64)v1[3] >= 8 )
        operator delete(*v1);
      v1[3] = (void *)7;
      v1[2] = 0;
      *(_WORD *)v1 = 0;
      v1 += 4;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000364c  mov     [rsp+arg_0], rbx
0x180003651  mov     [rsp+arg_8], rsi
0x180003656  push    rdi
0x180003657  sub     rsp, 20h
0x18000365b  mov     rbx, [rcx]
0x18000365e  mov     rdi, rcx
0x180003661  test    rbx, rbx
0x180003664  jz      short loc_1800036BA
0x180003666  mov     rsi, [rcx+8]
0x18000366a  jmp     short loc_180003695
0x18000366c  cmp     qword ptr [rbx+18h], 8
0x180003671  jb      short loc_18000367C
0x180003673  mov     rcx, [rbx]
0x180003676  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000367c  xor     eax, eax
0x18000367e  mov     qword ptr [rbx+18h], 7
0x180003686  mov     qword ptr [rbx+10h], 0
0x18000368e  mov     [rbx], ax
0x180003691  add     rbx, 20h ; ' '
0x180003695  cmp     rbx, rsi
0x180003698  jnz     short loc_18000366C
0x18000369a  mov     rcx, [rdi]
0x18000369d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800036a3  mov     qword ptr [rdi], 0
0x1800036aa  mov     qword ptr [rdi+8], 0
0x1800036b2  mov     qword ptr [rdi+10h], 0
0x1800036ba  mov     rbx, [rsp+28h+arg_0]
0x1800036bf  mov     rsi, [rsp+28h+arg_8]
0x1800036c4  add     rsp, 20h
0x1800036c8  pop     rdi
0x1800036c9  retn
```
