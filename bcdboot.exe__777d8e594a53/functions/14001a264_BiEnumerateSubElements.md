# BiEnumerateSubElements

- ea: `0x14001a264`
- end: `0x14001a44d`
- name: `BiEnumerateSubElements`
- size: `489`
- prototype: `__int64 __fastcall(__int64, __int64 *, int, int, _QWORD **, unsigned int *, _DWORD *, _QWORD *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140019bb8`
- `0x14001a454`

## callees

- `0x1400133e4`
- `0x140013ee8`
- `0x140019bb8`
- `0x14001a264`
- `0x14001e5e4`
- `0x140020720`
- `0x140026650`

## string_xrefs

- `0x14001a348`: `Failed to open object %ws. Status: %x`

## pseudocode

```c
__int64 __fastcall BiEnumerateSubElements(
        __int64 a1,
        __int64 *a2,
        int a3,
        int a4,
        _QWORD **a5,
        unsigned int *a6,
        _DWORD *a7,
        _QWORD *a8,
        int a9)
{
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  int v14; // eax
  int v15; // edi
  __int64 v16; // rcx
  _QWORD *v17; // rsi
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  unsigned int v21; // [rsp+50h] [rbp-A1h] BYREF
  int v22; // [rsp+54h] [rbp-9Dh] BYREF
  int v23; // [rsp+58h] [rbp-99h]
  HANDLE Handle; // [rsp+60h] [rbp-91h] BYREF
  __int64 v25; // [rsp+68h] [rbp-89h] BYREF
  char *v26; // [rsp+70h] [rbp-81h]
  __int128 v27; // [rsp+78h] [rbp-79h] BYREF
  char v28; // [rsp+90h] [rbp-61h] BYREF

  v23 = a4;
  v25 = 5111808;
  *a7 = 0;
  v12 = a8;
  v26 = &v28;
  Handle = 0;
  v21 = 0;
  v22 = 0;
  v27 = 0;
  if ( a8 )
  {
    while ( 1 )
    {
      v13 = (_QWORD *)v12[1];
      if ( *v13 == *a2 && v13[1] == a2[1] )
        break;
      v12 = (_QWORD *)*v12;
      if ( !v12 )
        goto LABEL_5;
    }
    v15 = 0;
  }
  else
  {
LABEL_5:
    *(_QWORD *)&v27 = a8;
    *((_QWORD *)&v27 + 1) = a2;
    BiStringFromGUID(a2, &v25);
    v14 = BcdOpenObject(a1, a2, &Handle);
    v15 = v14;
    if ( v14 >= 0 )
    {
      v17 = *a5;
      v21 = *a6;
      v15 = BiEnumerateElements(a1, (__int64)Handle, a3, v23, (__int64)v17, &v21, &v22, (__int64)&v27, a9);
      if ( v15 < 0 )
      {
        v18 = 1;
        if ( v15 != -1073741789 )
          v18 = 4;
        BiLogMessage(v18, L"Failed to Enumerate elements from %ws. Status: %x", v26, (unsigned int)v15);
      }
      BiCloseKey(Handle);
      if ( v15 >= 0 && v22 )
      {
        v19 = (_QWORD *)*v17;
        if ( *v17 )
        {
          do
          {
            v17 = v19;
            v19 = (_QWORD *)*v19;
          }
          while ( v19 );
        }
        *a5 = v17;
      }
    }
    else
    {
      v16 = *a2;
      if ( !*a2 )
        v16 = a2[1];
      BiLogMessage(v16 == 0 ? 1 : 4, L"Failed to open object %ws. Status: %x", v26, (unsigned int)v14);
    }
  }
  *a6 = v21;
  *a7 = v22;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14001a264  push    rbp
0x14001a266  push    rbx
0x14001a267  push    rsi
0x14001a268  push    rdi
0x14001a269  push    r12
0x14001a26b  push    r13
0x14001a26d  push    r14
0x14001a26f  push    r15
0x14001a271  lea     rbp, [rsp-7]
0x14001a276  sub     rsp, 0F8h
0x14001a27d  mov     rax, cs:__security_cookie
0x14001a284  xor     rax, rsp
0x14001a287  mov     [rbp+3Fh+var_50], rax
0x14001a28b  mov     r13, [rbp+3Fh+arg_30]
0x14001a28f  lea     rax, [rbp+3Fh+var_A0]
0x14001a293  mov     r14, [rbp+3Fh+arg_20]
0x14001a297  mov     ebx, r8d
0x14001a29a  mov     r8, [rbp+3Fh+arg_38]
0x14001a2a1  xorps   xmm0, xmm0
0x14001a2a4  mov     r12, [rbp+3Fh+arg_28]
0x14001a2a8  mov     r15, rcx
0x14001a2ab  mov     [rsp+130h+var_D8], r9d
0x14001a2b0  mov     rsi, rdx
0x14001a2b3  xor     r9d, r9d
0x14001a2b6  mov     [rsp+130h+var_C8], 4E0000h
0x14001a2bf  mov     [r13+0], r9d
0x14001a2c3  mov     rcx, r8
0x14001a2c6  mov     [rsp+130h+var_C0], rax
0x14001a2cb  mov     [rsp+130h+Handle], r9
0x14001a2d0  mov     [rsp+130h+var_E0], r9d
0x14001a2d5  mov     [rsp+130h+var_DC], r9d
0x14001a2da  movups  [rbp+3Fh+var_B8], xmm0
0x14001a2de  test    r8, r8
0x14001a2e1  jz      short loc_14001A301
0x14001a2e3  mov     rdx, [rcx+8]
0x14001a2e7  mov     rax, [rdx]
0x14001a2ea  cmp     rax, [rsi]
0x14001a2ed  jnz     short loc_14001A2F9
0x14001a2ef  mov     rax, [rdx+8]
0x14001a2f3  cmp     rax, [rsi+8]
0x14001a2f7  jz      short loc_14001A36E
0x14001a2f9  mov     rcx, [rcx]
0x14001a2fc  test    rcx, rcx
0x14001a2ff  jnz     short loc_14001A2E3
0x14001a301  lea     rdx, [rsp+130h+var_C8]
0x14001a306  mov     qword ptr [rbp+3Fh+var_B8], r8
0x14001a30a  mov     rcx, rsi
0x14001a30d  mov     qword ptr [rbp+3Fh+var_B8+8], rsi
0x14001a311  call    BiStringFromGUID
0x14001a316  lea     r8, [rsp+130h+Handle]
0x14001a31b  mov     rdx, rsi
0x14001a31e  mov     rcx, r15
0x14001a321  call    BcdOpenObject
0x14001a326  mov     edi, eax
0x14001a328  test    eax, eax
0x14001a32a  jns     short loc_14001A376
0x14001a32c  mov     rcx, [rsi]
0x14001a32f  sub     rcx, cs:qword_140035318
0x14001a336  jnz     short loc_14001A343
0x14001a338  mov     rcx, [rsi+8]
0x14001a33c  sub     rcx, cs:qword_140035320
0x14001a343  mov     r8, [rsp+130h+var_C0]
0x14001a348  lea     rdx, aFailedToOpenOb_0; "Failed to open object %ws. Status: %x"
0x14001a34f  xor     eax, eax
0x14001a351  mov     r9d, edi
0x14001a354  test    rcx, rcx
0x14001a357  setz    al
0x14001a35a  neg     eax
0x14001a35c  sbb     ecx, ecx
0x14001a35e  and     ecx, 0FFFFFFFDh
0x14001a361  add     ecx, 4
0x14001a364  call    BiLogMessage
0x14001a369  jmp     loc_14001A41B
0x14001a36e  mov     edi, r9d
0x14001a371  jmp     loc_14001A41B
0x14001a376  mov     eax, [r12]
0x14001a37a  mov     r8d, ebx
0x14001a37d  mov     rsi, [r14]
0x14001a380  mov     rcx, r15
0x14001a383  mov     r9d, [rsp+130h+var_D8]
0x14001a388  mov     rdx, [rsp+130h+Handle]
0x14001a38d  mov     [rsp+130h+var_E0], eax
0x14001a391  mov     eax, [rbp+3Fh+arg_40]
0x14001a397  mov     [rsp+130h+var_F0], eax
0x14001a39b  lea     rax, [rbp+3Fh+var_B8]
0x14001a39f  mov     [rsp+130h+var_F8], rax
0x14001a3a4  lea     rax, [rsp+130h+var_DC]
0x14001a3a9  mov     [rsp+130h+var_100], rax
0x14001a3ae  lea     rax, [rsp+130h+var_E0]
0x14001a3b3  mov     [rsp+130h+var_108], rax
0x14001a3b8  mov     [rsp+130h+var_110], rsi
0x14001a3bd  call    BiEnumerateElements
0x14001a3c2  mov     edi, eax
0x14001a3c4  test    eax, eax
0x14001a3c6  jns     short loc_14001A3ED
0x14001a3c8  mov     r8, [rsp+130h+var_C0]
0x14001a3cd  lea     rdx, aFailedToEnumer_3; "Failed to Enumerate elements from %ws. "...
0x14001a3d4  mov     ecx, 1
0x14001a3d9  cmp     edi, 0C0000023h
0x14001a3df  mov     r9d, edi
0x14001a3e2  lea     eax, [rcx+3]
0x14001a3e5  cmovnz  ecx, eax
0x14001a3e8  call    BiLogMessage
0x14001a3ed  mov     rcx, [rsp+130h+Handle]; Handle
0x14001a3f2  call    BiCloseKey
0x14001a3f7  test    edi, edi
0x14001a3f9  js      short loc_14001A41B
0x14001a3fb  cmp     [rsp+130h+var_DC], 0
0x14001a400  jz      short loc_14001A41B
0x14001a402  mov     rcx, [rsi]
0x14001a405  test    rcx, rcx
0x14001a408  jz      short loc_14001A418
0x14001a40a  mov     rax, [rcx]
0x14001a40d  mov     rsi, rcx
0x14001a410  mov     rcx, rax
0x14001a413  test    rax, rax
0x14001a416  jnz     short loc_14001A40A
0x14001a418  mov     [r14], rsi
0x14001a41b  mov     eax, [rsp+130h+var_E0]
0x14001a41f  mov     [r12], eax
0x14001a423  mov     eax, [rsp+130h+var_DC]
0x14001a427  mov     [r13+0], eax
0x14001a42b  mov     eax, edi
0x14001a42d  mov     rcx, [rbp+3Fh+var_50]
0x14001a431  xor     rcx, rsp; StackCookie
0x14001a434  call    __security_check_cookie
0x14001a439  add     rsp, 0F8h
0x14001a440  pop     r15
0x14001a442  pop     r14
0x14001a444  pop     r13
0x14001a446  pop     r12
0x14001a448  pop     rdi
0x14001a449  pop     rsi
0x14001a44a  pop     rbx
0x14001a44b  pop     rbp
0x14001a44c  retn
```
