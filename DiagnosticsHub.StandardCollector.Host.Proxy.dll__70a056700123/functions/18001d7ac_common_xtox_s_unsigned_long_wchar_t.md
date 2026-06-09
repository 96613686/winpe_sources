# common_xtox_s_unsigned_long_wchar_t_

- ea: `0x18001d7ac`
- end: `0x18001d815`
- name: `common_xtox_s_unsigned_long_wchar_t_`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001da1c`
- `0x18001dabc`
- `0x18001dba8`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d4cc`
- `0x18001d7ac`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned_long_wchar_t_(
        unsigned int a1,
        __int16 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned __int8 a5)
{
  int *v5; // rax
  unsigned int v6; // ebx

  if ( !a2 || !a3 )
    goto LABEL_2;
  *a2 = 0;
  if ( a3 <= (unsigned __int64)a5 + 1 )
  {
    v5 = errno();
    v6 = 34;
    goto LABEL_3;
  }
  if ( a4 - 2 > 0x22 )
  {
LABEL_2:
    v5 = errno();
    v6 = 22;
LABEL_3:
    *v5 = v6;
    invalid_parameter_noinfo();
    return v6;
  }
  return common_xtox_unsigned_long_wchar_t_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001d7ac  push    rbx
0x18001d7ae  sub     rsp, 30h
0x18001d7b2  xor     eax, eax
0x18001d7b4  mov     r10d, ecx
0x18001d7b7  test    rdx, rdx
0x18001d7ba  jnz     short loc_18001D7D5
0x18001d7bc  call    _errno
0x18001d7c1  mov     ebx, 16h
0x18001d7c6  mov     [rax], ebx
0x18001d7c8  call    _invalid_parameter_noinfo
0x18001d7cd  mov     eax, ebx
0x18001d7cf  add     rsp, 30h
0x18001d7d3  pop     rbx
0x18001d7d4  retn
0x18001d7d5  test    r8, r8
0x18001d7d8  jz      short loc_18001D7BC
0x18001d7da  movzx   ecx, [rsp+38h+arg_20]
0x18001d7df  mov     [rdx], ax
0x18001d7e2  lea     rax, [rcx+1]
0x18001d7e6  cmp     r8, rax
0x18001d7e9  ja      short loc_18001D7F7
0x18001d7eb  call    _errno
0x18001d7f0  mov     ebx, 22h ; '"'
0x18001d7f5  jmp     short loc_18001D7C6
0x18001d7f7  lea     eax, [r9-2]
0x18001d7fb  mov     ebx, 22h ; '"'
0x18001d800  cmp     eax, ebx
0x18001d802  ja      short loc_18001D7BC
0x18001d804  mov     [rsp+38h+arg_20], cl
0x18001d808  mov     ecx, r10d
0x18001d80b  add     rsp, 30h
0x18001d80f  pop     rbx
0x18001d810  jmp     common_xtox_unsigned_long_wchar_t_
```
