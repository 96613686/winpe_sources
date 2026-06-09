# IoCopy_ImageReg(_CRYPT_IMAGE_REG *,ulong,ulong *,uchar *)

- ea: `0x180019cbc`
- end: `0x180019da6`
- name: `?IoCopy_ImageReg@@YAKPEAU_CRYPT_IMAGE_REG@@KPEAKPEAE@Z`
- size: `234`
- prototype: `unsigned int __fastcall(struct _CRYPT_IMAGE_REG *, unsigned int, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019dac`

## callees

- `0x180003d20`
- `0x180019cbc`
- `0x180019f40`

## pseudocode

```c
unsigned int __fastcall IoCopy_ImageReg(struct _CRYPT_IMAGE_REG *a1, __int64 a2, unsigned int *a3, unsigned __int8 *a4)
{
  PWSTR pszImage; // rcx
  unsigned __int8 *v8; // rbp
  unsigned int result; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r15d
  unsigned __int8 *v12; // rsi
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = 0;
  v13 = 0;
  if ( a3 )
    *a3 = 0;
  pszImage = a1->pszImage;
  if ( !pszImage || !*pszImage || !a1->rgpInterfaces || !a1->cInterfaces )
    return 87;
  v8 = (unsigned __int8 *)((unsigned __int64)(a4 + 24) & -(__int64)(a4 != 0));
  result = IoCopy_SzString(pszImage, &v14, v8);
  if ( !result )
  {
    v11 = v14 + 24;
    if ( a4 )
      v12 = &a4[v11];
    else
      v12 = 0;
    IoCopy_InterfaceRegArray(a1->rgpInterfaces, a1->cInterfaces, v10, &v13, v12);
    if ( a4 )
    {
      *(_QWORD *)a4 = v8;
      *((_QWORD *)a4 + 2) = v12;
      *((_DWORD *)a4 + 2) = a1->cInterfaces;
    }
    if ( a3 )
      *a3 = v11 + v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019cbc  mov     rax, rsp
0x180019cbf  mov     [rax+18h], rbx
0x180019cc3  mov     [rax+20h], rbp
0x180019cc7  mov     [rax+10h], edx
0x180019cca  push    rsi
0x180019ccb  push    rdi
0x180019ccc  push    r12
0x180019cce  push    r14
0x180019cd0  push    r15
0x180019cd2  sub     rsp, 30h
0x180019cd6  xor     r12d, r12d
0x180019cd9  mov     rbx, r9
0x180019cdc  mov     [rax+10h], r12d
0x180019ce0  mov     r14, r8
0x180019ce3  mov     [rax+8], r12d
0x180019ce7  mov     rdi, rcx
0x180019cea  test    r8, r8
0x180019ced  jz      short loc_180019CF2
0x180019cef  mov     [r8], r12d
0x180019cf2  mov     rcx, [rcx]; Src
0x180019cf5  test    rcx, rcx
0x180019cf8  jz      loc_180019D89
0x180019cfe  cmp     [rcx], r12w
0x180019d02  jz      loc_180019D89
0x180019d08  cmp     [rdi+10h], r12
0x180019d0c  jz      short loc_180019D89
0x180019d0e  cmp     [rdi+8], r12d
0x180019d12  jz      short loc_180019D89
0x180019d14  lea     rdx, [r9+18h]
0x180019d18  mov     rax, rbx
0x180019d1b  neg     rax
0x180019d1e  sbb     rbp, rbp
0x180019d21  and     rbp, rdx
0x180019d24  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x180019d29  mov     r8, rbp; unsigned __int8 *
0x180019d2c  call    ?IoCopy_SzString@@YAKPEAGPEAKPEAE@Z; IoCopy_SzString(ushort *,ulong *,uchar *)
0x180019d31  test    eax, eax
0x180019d33  jnz     short loc_180019D8E
0x180019d35  mov     r15d, [rsp+58h+arg_8]
0x180019d3a  add     r15d, 18h
0x180019d3e  test    rbx, rbx
0x180019d41  jz      short loc_180019D4B
0x180019d43  mov     esi, r15d
0x180019d46  add     rsi, rbx
0x180019d49  jmp     short loc_180019D4E
0x180019d4b  mov     rsi, r12
0x180019d4e  mov     edx, [rdi+8]; unsigned int
0x180019d51  lea     r9, [rsp+58h+arg_0]; unsigned int *
0x180019d56  mov     rcx, [rdi+10h]; struct _CRYPT_INTERFACE_REG **
0x180019d5a  mov     [rsp+58h+var_38], rsi; unsigned __int8 *
0x180019d5f  call    ?IoCopy_InterfaceRegArray@@YAKPEAPEAU_CRYPT_INTERFACE_REG@@KKPEAKPEAE@Z; IoCopy_InterfaceRegArray(_CRYPT_INTERFACE_REG * *,ulong,ulong,ulong *,uchar *)
0x180019d64  test    rbx, rbx
0x180019d67  jz      short loc_180019D76
0x180019d69  mov     [rbx], rbp
0x180019d6c  mov     [rbx+10h], rsi
0x180019d70  mov     eax, [rdi+8]
0x180019d73  mov     [rbx+8], eax
0x180019d76  test    r14, r14
0x180019d79  jz      short loc_180019D85
0x180019d7b  mov     ecx, [rsp+58h+arg_0]
0x180019d7f  add     ecx, r15d
0x180019d82  mov     [r14], ecx
0x180019d85  xor     eax, eax
0x180019d87  jmp     short loc_180019D8E
0x180019d89  mov     eax, 57h ; 'W'
0x180019d8e  mov     rbx, [rsp+58h+arg_10]
0x180019d93  mov     rbp, [rsp+58h+arg_18]
0x180019d98  add     rsp, 30h
0x180019d9c  pop     r15
0x180019d9e  pop     r14
0x180019da0  pop     r12
0x180019da2  pop     rdi
0x180019da3  pop     rsi
0x180019da4  retn
```
