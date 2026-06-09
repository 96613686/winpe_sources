# Helpers::IsEnumValue(ushort const *,ushort const *)

- ea: `0x180010624`
- end: `0x180010695`
- name: `?IsEnumValue@Helpers@@SA_NPEBG0@Z`
- size: `113`
- prototype: `bool __fastcall(LPCWCH lpString2, LPCWCH lpString1)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003080`
- `0x180005210`
- `0x180006ec0`

## callees

- `0x180010624`

## import_xrefs

- `msvcrt!wcschr` at `0x180010639`
- `msvcrt!wcschr` at `0x180010639`
- `KERNEL32!CompareStringOrdinal` at `0x18001065a`
- `KERNEL32!CompareStringOrdinal` at `0x18001067e`
- `KERNEL32!CompareStringOrdinal` at `0x18001065a`
- `KERNEL32!CompareStringOrdinal` at `0x18001067e`

## pseudocode

```c
bool __fastcall Helpers::IsEnumValue(LPCWCH lpString2, LPCWCH lpString1)
{
  wchar_t *v4; // rax

  v4 = wcschr(lpString2, 0x5Fu);
  return v4 && CompareStringOrdinal(lpString1, -1, v4 + 1, -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180010624  mov     [rsp+arg_0], rbx
0x180010629  push    rdi
0x18001062a  sub     rsp, 30h
0x18001062e  mov     rbx, rdx
0x180010631  mov     rdi, rcx
0x180010634  mov     edx, 5Fh ; '_'; Ch
0x180010639  call    cs:__imp_wcschr
0x18001063f  test    rax, rax
0x180010642  jz      short loc_180010669
0x180010644  or      r9d, 0FFFFFFFFh; cchCount2
0x180010648  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180010650  or      edx, r9d; cchCount1
0x180010653  lea     r8, [rax+2]; lpString2
0x180010657  mov     rcx, rbx; lpString1
0x18001065a  call    cs:__imp_CompareStringOrdinal
0x180010660  cmp     eax, 2
0x180010663  jnz     short loc_180010669
0x180010665  mov     al, 1
0x180010667  jmp     short loc_18001068A
0x180010669  or      r9d, 0FFFFFFFFh; cchCount2
0x18001066d  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180010675  or      edx, r9d; cchCount1
0x180010678  mov     r8, rdi; lpString2
0x18001067b  mov     rcx, rbx; lpString1
0x18001067e  call    cs:__imp_CompareStringOrdinal
0x180010684  cmp     eax, 2
0x180010687  setz    al
0x18001068a  mov     rbx, [rsp+38h+arg_0]
0x18001068f  add     rsp, 30h
0x180010693  pop     rdi
0x180010694  retn
```
