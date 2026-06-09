# std::vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>::_Tidy(void)

- ea: `0x18002114c`
- end: `0x1800211a0`
- name: `?_Tidy@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@IEAAXXZ`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800203f0`

## callees

- `0x1800200a0`
- `0x18002114c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002117a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002117a`

## pseudocode

```c
void __fastcall std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Tidy(__int64 a1)
{
  char *v1; // rdi
  char *v3; // rbp

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char **)(a1 + 8);
    while ( v1 != v3 )
    {
      std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(
        a1,
        (__int64)v1);
      v1 += 16;
    }
    operator delete(*(void **)a1);
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18002114c  push    rbx
0x18002114e  push    rbp
0x18002114f  push    rsi
0x180021150  push    rdi
0x180021151  sub     rsp, 28h
0x180021155  mov     rdi, [rcx]
0x180021158  mov     rbx, rcx
0x18002115b  test    rdi, rdi
0x18002115e  jz      short loc_180021180
0x180021160  mov     rbp, [rcx+8]
0x180021164  jmp     short loc_180021172
0x180021166  mov     rdx, rdi
0x180021169  call    ??$_Dest_val@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@std@@V?$shared_ptr@VIRegistryKey@@@tr1@2@@std@@YAXAEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@PEAV?$shared_ptr@VIRegistryKey@@@tr1@0@@Z; std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *)
0x18002116e  add     rdi, 10h
0x180021172  cmp     rdi, rbp
0x180021175  jnz     short loc_180021166
0x180021177  mov     rcx, [rbx]
0x18002117a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021180  mov     qword ptr [rbx], 0
0x180021187  mov     qword ptr [rbx+8], 0
0x18002118f  mov     qword ptr [rbx+10h], 0
0x180021197  add     rsp, 28h
0x18002119b  pop     rdi
0x18002119c  pop     rsi
0x18002119d  pop     rbp
0x18002119e  pop     rbx
0x18002119f  retn
```
