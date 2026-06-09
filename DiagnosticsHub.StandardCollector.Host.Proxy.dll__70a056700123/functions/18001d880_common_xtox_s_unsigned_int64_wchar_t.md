# common_xtox_s_unsigned___int64_wchar_t_

- ea: `0x18001d880`
- end: `0x18001d8e9`
- name: `common_xtox_s_unsigned___int64_wchar_t_`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d978`
- `0x18001db38`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d66c`
- `0x18001d880`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned___int64_wchar_t_(
        unsigned __int64 a1,
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
  return common_xtox_unsigned___int64_wchar_t_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001d880  push    rbx
0x18001d882  sub     rsp, 30h
0x18001d886  xor     eax, eax
0x18001d888  mov     r10, rcx
0x18001d88b  test    rdx, rdx
0x18001d88e  jnz     short loc_18001D8A9
0x18001d890  call    _errno
0x18001d895  mov     ebx, 16h
0x18001d89a  mov     [rax], ebx
0x18001d89c  call    _invalid_parameter_noinfo
0x18001d8a1  mov     eax, ebx
0x18001d8a3  add     rsp, 30h
0x18001d8a7  pop     rbx
0x18001d8a8  retn
0x18001d8a9  test    r8, r8
0x18001d8ac  jz      short loc_18001D890
0x18001d8ae  movzx   ecx, [rsp+38h+arg_20]
0x18001d8b3  mov     [rdx], ax
0x18001d8b6  lea     rax, [rcx+1]
0x18001d8ba  cmp     r8, rax
0x18001d8bd  ja      short loc_18001D8CB
0x18001d8bf  call    _errno
0x18001d8c4  mov     ebx, 22h ; '"'
0x18001d8c9  jmp     short loc_18001D89A
0x18001d8cb  lea     eax, [r9-2]
0x18001d8cf  mov     ebx, 22h ; '"'
0x18001d8d4  cmp     eax, ebx
0x18001d8d6  ja      short loc_18001D890
0x18001d8d8  mov     [rsp+38h+arg_20], cl
0x18001d8dc  mov     rcx, r10
0x18001d8df  add     rsp, 30h
0x18001d8e3  pop     rbx
0x18001d8e4  jmp     common_xtox_unsigned___int64_wchar_t_
```
