# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Tidy(void)

- ea: `0x140003a0c`
- end: `0x140003a8a`
- name: `?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003cd4`
- `0x1400059ac`
- `0x140006b70`
- `0x14000ac60`
- `0x14000ad18`
- `0x14000e405`
- `0x14000eb59`
- `0x14000eb91`
- `0x14000f000`

## callees

- `0x140003a0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003a36`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003a5d`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003a36`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003a5d`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::_Tidy(__int64 a1)
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
0x140003a0c  mov     [rsp+arg_0], rbx
0x140003a11  mov     [rsp+arg_8], rsi
0x140003a16  push    rdi
0x140003a17  sub     rsp, 20h
0x140003a1b  mov     rbx, [rcx]
0x140003a1e  mov     rdi, rcx
0x140003a21  test    rbx, rbx
0x140003a24  jz      short loc_140003A7A
0x140003a26  mov     rsi, [rcx+8]
0x140003a2a  jmp     short loc_140003A55
0x140003a2c  cmp     qword ptr [rbx+18h], 8
0x140003a31  jb      short loc_140003A3C
0x140003a33  mov     rcx, [rbx]
0x140003a36  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003a3c  xor     eax, eax
0x140003a3e  mov     qword ptr [rbx+18h], 7
0x140003a46  mov     qword ptr [rbx+10h], 0
0x140003a4e  mov     [rbx], ax
0x140003a51  add     rbx, 20h ; ' '
0x140003a55  cmp     rbx, rsi
0x140003a58  jnz     short loc_140003A2C
0x140003a5a  mov     rcx, [rdi]
0x140003a5d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003a63  mov     qword ptr [rdi], 0
0x140003a6a  mov     qword ptr [rdi+8], 0
0x140003a72  mov     qword ptr [rdi+10h], 0
0x140003a7a  mov     rbx, [rsp+28h+arg_0]
0x140003a7f  mov     rsi, [rsp+28h+arg_8]
0x140003a84  add     rsp, 20h
0x140003a88  pop     rdi
0x140003a89  retn
```
