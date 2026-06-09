# ImageDirectoryMappedAddress

- ea: `0x180004db8`
- end: `0x180004e3f`
- name: `ImageDirectoryMappedAddress`
- size: `135`
- prototype: `__int64 __fastcall(__int64, int, unsigned int *, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050bc`
- `0x180005338`
- `0x18000677c`
- `0x180006858`
- `0x180006b98`

## callees

- `0x180004db8`
- `0x180004e98`
- `0x180004ef0`
- `0x180005400`

## pseudocode

```c
__int64 __fastcall ImageDirectoryMappedAddress(__int64 a1, int a2, unsigned int *a3, __int64 a4, unsigned int a5)
{
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r9
  unsigned int v13; // [rsp+30h] [rbp-38h] BYREF

  v13 = 0;
  v8 = ImageDirectoryRvaAndSize(a1, a2, (unsigned int)&v13, a4, a5);
  if ( !v8 )
    return 0;
  v9 = ImageRvaToFileOffset(a1, v8, a4, a5);
  if ( !v9 )
    return 0;
  if ( v9 >= a5 )
    return 0;
  v10 = a4 + v9;
  if ( !v10 )
    return 0;
  v11 = v10 + v13;
  if ( v11 < v10 )
  {
    ThrowPeFmtException();
    JUMPOUT(0x180004E3ELL);
  }
  if ( v11 > a4 + (unsigned __int64)a5 )
    return 0;
  if ( a3 )
    *a3 = v13;
  return a4 + v9;
}

```

## disassembly

```asm
0x180004db8  push    rbx
0x180004dba  push    rbp
0x180004dbb  push    rsi
0x180004dbc  push    rdi
0x180004dbd  sub     rsp, 48h
0x180004dc1  mov     ebx, [rsp+68h+arg_20]
0x180004dc8  mov     rsi, r8
0x180004dcb  lea     r8, [rsp+68h+var_38]
0x180004dd0  mov     [rsp+68h+var_48], ebx
0x180004dd4  mov     rdi, r9
0x180004dd7  mov     [rsp+68h+var_38], 0
0x180004ddf  mov     rbp, rcx
0x180004de2  call    ImageDirectoryRvaAndSize
0x180004de7  test    eax, eax
0x180004de9  jz      short loc_180004E2E
0x180004deb  mov     r9d, ebx
0x180004dee  mov     r8, rdi
0x180004df1  mov     edx, eax
0x180004df3  mov     rcx, rbp
0x180004df6  call    ImageRvaToFileOffset
0x180004dfb  test    eax, eax
0x180004dfd  jz      short loc_180004E2E
0x180004dff  cmp     eax, ebx
0x180004e01  jnb     short loc_180004E2E
0x180004e03  mov     edx, eax
0x180004e05  add     rdx, rdi
0x180004e08  jz      short loc_180004E2E
0x180004e0a  mov     r8d, [rsp+68h+var_38]
0x180004e0f  lea     r9, [rdx+r8]
0x180004e13  cmp     r9, rdx
0x180004e16  jb      short loc_180004E39
0x180004e18  lea     rcx, [rdi+rbx]
0x180004e1c  cmp     r9, rcx
0x180004e1f  ja      short loc_180004E2E
0x180004e21  test    rsi, rsi
0x180004e24  jz      short loc_180004E29
0x180004e26  mov     [rsi], r8d
0x180004e29  mov     rax, rdx
0x180004e2c  jmp     short loc_180004E30
0x180004e2e  xor     eax, eax
0x180004e30  add     rsp, 48h
0x180004e34  pop     rdi
0x180004e35  pop     rsi
0x180004e36  pop     rbp
0x180004e37  pop     rbx
0x180004e38  retn
0x180004e39  call    ThrowPeFmtException
```
