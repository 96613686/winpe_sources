# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Grow(unsigned __int64,bool)

- ea: `0x180005b50`
- end: `0x180005bad`
- name: `?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z`
- size: `93`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180005d60`
- `0x180005e18`
- `0x1800060cc`
- `0x1800061f0`

## callees

- `0x1800059a4`
- `0x180005b50`
- `0x180005cc8`

## pseudocode

```c
bool __fastcall std::wstring::_Grow(_QWORD *a1, unsigned __int64 a2)
{
  bool v3; // zf
  _WORD *v4; // rdx

  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( a1[3] < a2 )
  {
    std::wstring::_Copy((__int64)a1, a2, a1[2]);
LABEL_10:
    v3 = a2 == 0;
    return !v3;
  }
  v3 = a2 == 0;
  if ( !a2 )
  {
    if ( a1[3] < 8u )
      v4 = a1;
    else
      v4 = (_WORD *)*a1;
    a1[2] = 0;
    *v4 = 0;
    goto LABEL_10;
  }
  return !v3;
}

```

## disassembly

```asm
0x180005b50  push    rbx
0x180005b52  sub     rsp, 20h
0x180005b56  mov     rax, 7FFFFFFFFFFFFFFEh
0x180005b60  mov     rbx, rdx
0x180005b63  cmp     rdx, rax
0x180005b66  jbe     short loc_180005B6E
0x180005b68  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x180005b6e  cmp     [rcx+18h], rbx
0x180005b72  jnb     short loc_180005B7F
0x180005b74  mov     r8, [rcx+10h]
0x180005b78  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180005b7d  jmp     short loc_180005BA0
0x180005b7f  test    rbx, rbx
0x180005b82  jnz     short loc_180005BA3
0x180005b84  cmp     qword ptr [rcx+18h], 8
0x180005b89  jb      short loc_180005B90
0x180005b8b  mov     rdx, [rcx]
0x180005b8e  jmp     short loc_180005B93
0x180005b90  mov     rdx, rcx
0x180005b93  xor     eax, eax
0x180005b95  mov     qword ptr [rcx+10h], 0
0x180005b9d  mov     [rdx], ax
0x180005ba0  test    rbx, rbx
0x180005ba3  setnz   al
0x180005ba6  add     rsp, 20h
0x180005baa  pop     rbx
0x180005bab  retn
```
