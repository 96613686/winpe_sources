# compress2_z

- ea: `0x180004a80`
- end: `0x180004bcd`
- name: `compress2_z`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004a40`

## callees

- `0x180004a80`
- `0x180006de0`
- `0x180007830`
- `0x180007c20`

## pseudocode

```c
__int64 __fastcall compress2_z(__int64 a1, unsigned __int64 *a2, __int64 a3, unsigned __int64 a4, unsigned int a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v9; // rsi
  __int64 result; // rax
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // edi
  __int64 v17; // [rsp+20h] [rbp-78h] BYREF
  int v18; // [rsp+28h] [rbp-70h]
  __int64 v19; // [rsp+30h] [rbp-68h]
  int v20; // [rsp+38h] [rbp-60h]
  __int64 v21; // [rsp+50h] [rbp-48h]
  __int64 v22; // [rsp+58h] [rbp-40h]
  __int64 v23; // [rsp+60h] [rbp-38h]

  v5 = a4;
  if ( a4 && !a3 )
    return 4294967294LL;
  if ( !a2 )
    return 4294967294LL;
  v9 = *a2;
  if ( *a2 )
  {
    if ( !a1 )
      return 4294967294LL;
  }
  *a2 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  result = deflateInit_(&v17, a5, "1.3.2", 88);
  if ( !(_DWORD)result )
  {
    v11 = 0;
    v12 = 0;
    v20 = 0;
    v18 = 0;
    v19 = a1;
    v17 = a3;
    while ( 1 )
    {
      if ( !v11 )
      {
        v13 = (unsigned int)v9;
        if ( v9 > 0xFFFFFFFF )
          v13 = 0xFFFFFFFFLL;
        v20 = v13;
        v9 -= v13;
      }
      if ( !v12 )
      {
        v14 = (unsigned int)v5;
        if ( v5 > 0xFFFFFFFF )
          v14 = 0xFFFFFFFFLL;
        v18 = v14;
        v5 -= v14;
      }
      v15 = 4;
      if ( v5 )
        v15 = 0;
      v16 = deflate(&v17, v15);
      if ( v16 )
        break;
      v11 = v20;
      v12 = v18;
    }
    *a2 = v19 - a1;
    deflateEnd(&v17);
    if ( v16 == 1 )
      return 0;
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x180004a80  mov     [rsp+arg_10], rbx
0x180004a85  mov     [rsp+arg_18], rbp
0x180004a8a  push    rsi
0x180004a8b  push    rdi
0x180004a8c  push    r14
0x180004a8e  sub     rsp, 80h
0x180004a95  mov     rbx, r9
0x180004a98  mov     rdi, r8
0x180004a9b  mov     r14, rdx
0x180004a9e  mov     rbp, rcx
0x180004aa1  test    r9, r9
0x180004aa4  jz      short loc_180004AAF
0x180004aa6  test    r8, r8
0x180004aa9  jz      loc_180004BC6
0x180004aaf  test    r14, r14
0x180004ab2  jz      loc_180004BC6
0x180004ab8  mov     rsi, [rdx]
0x180004abb  test    rsi, rsi
0x180004abe  jz      short loc_180004AC9
0x180004ac0  test    rbp, rbp
0x180004ac3  jz      loc_180004BC6
0x180004ac9  mov     [rsp+98h+arg_0], r12
0x180004ad1  lea     r8, a132; "1.3.2"
0x180004ad8  xor     r12d, r12d
0x180004adb  lea     rcx, [rsp+98h+var_78]
0x180004ae0  mov     [rdx], r12
0x180004ae3  mov     r9d, 58h ; 'X'
0x180004ae9  mov     edx, [rsp+98h+arg_20]
0x180004af0  mov     [rsp+98h+var_48], r12
0x180004af5  mov     [rsp+98h+var_40], r12
0x180004afa  mov     [rsp+98h+var_38], r12
0x180004aff  call    deflateInit_
0x180004b04  test    eax, eax
0x180004b06  jnz     loc_180004BA6
0x180004b0c  mov     eax, r12d
0x180004b0f  mov     [rsp+98h+arg_8], r15
0x180004b17  mov     ecx, r12d
0x180004b1a  mov     [rsp+98h+var_60], eax
0x180004b1e  mov     [rsp+98h+var_70], ecx
0x180004b22  mov     r15d, 0FFFFFFFFh
0x180004b28  mov     [rsp+98h+var_68], rbp
0x180004b2d  mov     [rsp+98h+var_78], rdi
0x180004b32  test    eax, eax
0x180004b34  jnz     short loc_180004B46
0x180004b36  cmp     rsi, r15
0x180004b39  mov     eax, esi
0x180004b3b  cmova   eax, r15d
0x180004b3f  mov     [rsp+98h+var_60], eax
0x180004b43  sub     rsi, rax
0x180004b46  test    ecx, ecx
0x180004b48  jnz     short loc_180004B5A
0x180004b4a  cmp     rbx, r15
0x180004b4d  mov     eax, ebx
0x180004b4f  cmova   eax, r15d
0x180004b53  mov     [rsp+98h+var_70], eax
0x180004b57  sub     rbx, rax
0x180004b5a  mov     edx, 4
0x180004b5f  lea     rcx, [rsp+98h+var_78]
0x180004b64  test    rbx, rbx
0x180004b67  cmovnz  edx, r12d
0x180004b6b  call    deflate
0x180004b70  mov     edi, eax
0x180004b72  test    eax, eax
0x180004b74  jnz     short loc_180004B80
0x180004b76  mov     eax, [rsp+98h+var_60]
0x180004b7a  mov     ecx, [rsp+98h+var_70]
0x180004b7e  jmp     short loc_180004B32
0x180004b80  mov     rax, [rsp+98h+var_68]
0x180004b85  lea     rcx, [rsp+98h+var_78]
0x180004b8a  sub     rax, rbp
0x180004b8d  mov     [r14], rax
0x180004b90  call    deflateEnd
0x180004b95  mov     r15, [rsp+98h+arg_8]
0x180004b9d  cmp     edi, 1
0x180004ba0  cmovz   edi, r12d
0x180004ba4  mov     eax, edi
0x180004ba6  mov     r12, [rsp+98h+arg_0]
0x180004bae  lea     r11, [rsp+98h+var_18]
0x180004bb6  mov     rbx, [r11+30h]
0x180004bba  mov     rbp, [r11+38h]
0x180004bbe  mov     rsp, r11
0x180004bc1  pop     r14
0x180004bc3  pop     rdi
0x180004bc4  pop     rsi
0x180004bc5  retn
0x180004bc6  mov     eax, 0FFFFFFFEh
0x180004bcb  jmp     short loc_180004BAE
```
