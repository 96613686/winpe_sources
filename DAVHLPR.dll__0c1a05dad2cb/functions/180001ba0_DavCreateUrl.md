# DavCreateUrl

- ea: `0x180001ba0`
- end: `0x180001e74`
- name: `DavCreateUrl`
- size: `724`
- prototype: `__int64 __fastcall(__int128 *, _WORD *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001460`

## callees

- `0x180001ba0`
- `0x180003550`
- `0x180004120`
- `0x180005d88`
- `0x1800060cd`
- `0x180006100`

## pseudocode

```c
__int64 __fastcall DavCreateUrl(__int128 *a1, _WORD *a2, unsigned __int64 *a3)
{
  DAV_STRING_VIEW *v3; // rdi
  __int64 v7; // rbx
  _QWORD *v8; // r9
  _BYTE *v9; // r10
  __int64 result; // rax
  const wchar_t *v11; // r11
  __int128 *v12; // r9
  __int128 v13; // xmm0
  unsigned __int64 v14; // r15
  _WORD *v15; // r13
  __int128 v16; // xmm1
  __int128 *v17; // r14
  unsigned __int64 v18; // rbp
  __int128 v19; // xmm0
  __int64 v20; // rsi
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // r12
  unsigned __int64 v23; // rcx
  __int128 v25; // [rsp+50h] [rbp-128h] BYREF
  _QWORD v26[4]; // [rsp+60h] [rbp-118h] BYREF
  __int128 v27; // [rsp+80h] [rbp-F8h]
  char v28[16]; // [rsp+90h] [rbp-E8h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-D8h]
  char v30[16]; // [rsp+B0h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-B8h]
  char v32[16]; // [rsp+D0h] [rbp-A8h] BYREF
  wchar_t *v33; // [rsp+E0h] [rbp-98h]
  unsigned __int16 *v34; // [rsp+E8h] [rbp-90h] BYREF
  __int128 v35; // [rsp+F0h] [rbp-88h]
  __int128 v36; // [rsp+100h] [rbp-78h]
  __int128 v37; // [rsp+110h] [rbp-68h]
  wchar_t Buffer[8]; // [rsp+120h] [rbp-58h] BYREF

  v25 = 0;
  v3 = (DAV_STRING_VIEW *)v26;
  v7 = 12;
  do
  {
    DAV_STRING_VIEW::DAV_STRING_VIEW(v3);
    v3 = (DAV_STRING_VIEW *)((char *)v3 + 16);
    --v7;
  }
  while ( v7 );
  if ( *((_QWORD *)a1 + 6) == *((_QWORD *)a1 + 7) )
  {
    if ( *((_QWORD *)a1 + 3) != *((_QWORD *)a1 + 2) )
      return 87;
    v8 = a1 + 2;
    if ( *((_QWORD *)a1 + 5) != *((_QWORD *)a1 + 4) )
      return 87;
    v9 = (char *)a1 + 66;
    if ( *((_BYTE *)a1 + 66) )
      return 87;
  }
  else
  {
    v8 = a1 + 2;
    v9 = (char *)a1 + 66;
  }
  v11 = L":";
  if ( *((_QWORD *)a1 + 1) != *(_QWORD *)a1 )
  {
    v25 = *a1;
    v26[1] = L"";
    v26[0] = L":";
  }
  if ( *((_QWORD *)a1 + 3) != *((_QWORD *)a1 + 2) || v8[1] != *v8 )
  {
    v27 = a1[1];
    DAV_STRING_VIEW::operator=(v28, L":");
    v29 = *v12;
    DAV_STRING_VIEW::operator=(v30, L"@");
  }
  if ( *((_QWORD *)a1 + 7) != *((_QWORD *)a1 + 6) )
  {
    v13 = a1[3];
    v26[2] = L"//";
    v26[3] = L"";
    v31 = v13;
  }
  if ( *v9 )
  {
    v33 = Buffer;
    DAV_STRING_VIEW::operator=(v32, v11);
    StringCchPrintfExW(Buffer, 6u, &v34, 0, 0, L"%d", *((unsigned __int16 *)a1 + 32));
  }
  v14 = *a3;
  v15 = 0;
  v16 = *(__int128 *)((char *)a1 + 88);
  v17 = &v25;
  v18 = 0;
  v35 = *(__int128 *)((char *)a1 + 72);
  v19 = *(__int128 *)((char *)a1 + 104);
  v20 = 13;
  if ( v14 )
    v15 = a2;
  v36 = v16;
  v37 = v19;
  do
  {
    v21 = (__int64)(*((_QWORD *)v17 + 1) - *(_QWORD *)v17) >> 1;
    v22 = v21;
    if ( v14 < v21 )
      v22 = v14;
    memcpy_0(v15, *(const void **)v17, 2 * v22);
    v15 += v22;
    v14 -= v22;
    if ( v22 < v21 )
      goto LABEL_30;
    v18 += v22;
    ++v17;
    --v20;
  }
  while ( v20 );
  if ( v14 )
  {
    *v15 = 0;
    *a3 = v18 + 1;
    return 0;
  }
  else
  {
    while ( v20 )
    {
LABEL_30:
      v23 = v18 + ((__int64)(*((_QWORD *)v17 + 1) - *(_QWORD *)v17) >> 1);
      if ( v23 < v18 )
        return 534;
      ++v17;
      v18 = v23;
      --v20;
    }
    if ( v18 + 1 < v18 )
      return 534;
    if ( v15 )
      *(v15 - 1) = 0;
    result = 122;
    *a3 = v18 + 1;
  }
  return result;
}

```

## disassembly

```asm
0x180001ba0  push    rbx
0x180001ba2  push    rsi
0x180001ba3  push    rdi
0x180001ba4  push    r12
0x180001ba6  push    r15
0x180001ba8  sub     rsp, 150h
0x180001baf  mov     rax, cs:__security_cookie
0x180001bb6  xor     rax, rsp
0x180001bb9  mov     [rsp+178h+var_48], rax
0x180001bc1  xorps   xmm0, xmm0
0x180001bc4  mov     [rsp+178h+var_138], r8
0x180001bc9  movdqa  [rsp+178h+var_128], xmm0
0x180001bcf  lea     rdi, [rsp+178h+var_118]
0x180001bd4  mov     r15, r8
0x180001bd7  mov     r12, rdx
0x180001bda  mov     rsi, rcx
0x180001bdd  mov     ebx, 0Ch
0x180001be2  mov     rcx, rdi; this
0x180001be5  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x180001bea  add     rdi, 10h
0x180001bee  sub     rbx, 1
0x180001bf2  jnz     short loc_180001BE2
0x180001bf4  mov     rax, [rsi+38h]
0x180001bf8  cmp     [rsi+30h], rax
0x180001bfc  jnz     short loc_180001C28
0x180001bfe  mov     rax, [rsi+18h]
0x180001c02  cmp     rax, [rsi+10h]
0x180001c06  jnz     short loc_180001C1E
0x180001c08  mov     rax, [rsi+28h]
0x180001c0c  lea     r9, [rsi+20h]
0x180001c10  cmp     rax, [r9]
0x180001c13  jnz     short loc_180001C1E
0x180001c15  cmp     [rsi+42h], bl
0x180001c18  lea     r10, [rsi+42h]
0x180001c1c  jz      short loc_180001C30
0x180001c1e  mov     eax, 57h ; 'W'
0x180001c23  jmp     loc_180001E55
0x180001c28  lea     r9, [rsi+20h]
0x180001c2c  lea     r10, [rsi+42h]
0x180001c30  mov     rcx, [rsi+8]
0x180001c34  lea     r11, asc_1800073F8; ":"
0x180001c3b  mov     rdx, [rsi]
0x180001c3e  mov     [rsp+178h+arg_18], rbp
0x180001c46  mov     [rsp+178h+var_30], r13
0x180001c4e  mov     [rsp+178h+var_38], r14
0x180001c56  cmp     rcx, rdx
0x180001c59  jz      short loc_180001C76
0x180001c5b  lea     rax, asc_1800073F8+2; ""
0x180001c62  mov     qword ptr [rsp+178h+var_128], rdx
0x180001c67  mov     [rsp+178h+var_110], rax
0x180001c6c  mov     qword ptr [rsp+178h+var_128+8], rcx
0x180001c71  mov     [rsp+178h+var_118], r11
0x180001c76  mov     rax, [rsi+18h]
0x180001c7a  cmp     rax, [rsi+10h]
0x180001c7e  jnz     short loc_180001C89
0x180001c80  mov     rax, [r9+8]
0x180001c84  cmp     rax, [r9]
0x180001c87  jz      short loc_180001CC5
0x180001c89  movups  xmm0, xmmword ptr [rsi+10h]
0x180001c8d  mov     rdx, r11
0x180001c90  lea     rcx, [rsp+178h+var_E8]
0x180001c98  movaps  [rsp+178h+var_F8], xmm0
0x180001ca0  call    ??4DAV_STRING_VIEW@@QEAAAEAU0@PEBG@Z; DAV_STRING_VIEW::operator=(ushort const *)
0x180001ca5  movups  xmm0, xmmword ptr [r9]
0x180001ca9  lea     rdx, asc_1800076D4; "@"
0x180001cb0  lea     rcx, [rsp+178h+var_C8]
0x180001cb8  movaps  [rsp+178h+var_D8], xmm0
0x180001cc0  call    ??4DAV_STRING_VIEW@@QEAAAEAU0@PEBG@Z; DAV_STRING_VIEW::operator=(ushort const *)
0x180001cc5  mov     rax, [rsi+38h]
0x180001cc9  cmp     rax, [rsi+30h]
0x180001ccd  jz      short loc_180001CF3
0x180001ccf  movups  xmm0, xmmword ptr [rsi+30h]
0x180001cd3  lea     rax, asc_1800073FC; "//"
0x180001cda  mov     [rsp+178h+var_108], rax
0x180001cdf  lea     rax, asc_1800073FC+4; ""
0x180001ce6  mov     [rsp+178h+var_100], rax
0x180001ceb  movaps  [rsp+178h+var_B8], xmm0
0x180001cf3  cmp     byte ptr [r10], 0
0x180001cf7  jz      short loc_180001D53
0x180001cf9  lea     rax, [rsp+178h+Buffer]
0x180001d01  mov     rdx, r11
0x180001d04  lea     rcx, [rsp+178h+var_A8]
0x180001d0c  mov     [rsp+178h+var_98], rax
0x180001d14  call    ??4DAV_STRING_VIEW@@QEAAAEAU0@PEBG@Z; DAV_STRING_VIEW::operator=(ushort const *)
0x180001d19  movzx   edx, word ptr [rsi+40h]
0x180001d1d  lea     rax, aD; "%d"
0x180001d24  mov     [rsp+178h+var_148], edx
0x180001d28  lea     r8, [rsp+178h+var_90]; unsigned __int16 **
0x180001d30  mov     [rsp+178h+var_150], rax; unsigned __int16 *
0x180001d35  lea     rcx, [rsp+178h+Buffer]; Buffer
0x180001d3d  mov     edx, 6; unsigned __int64
0x180001d42  mov     qword ptr [rsp+178h+var_158], 0; unsigned int
0x180001d4b  xor     r9d, r9d; unsigned __int64 *
0x180001d4e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180001d53  movups  xmm0, xmmword ptr [rsi+48h]
0x180001d57  mov     r15, [r15]
0x180001d5a  xor     r13d, r13d
0x180001d5d  movups  xmm1, xmmword ptr [rsi+58h]
0x180001d61  lea     r14, [rsp+178h+var_128]
0x180001d66  xor     ebp, ebp
0x180001d68  movaps  [rsp+178h+var_88], xmm0
0x180001d70  test    r15, r15
0x180001d73  movups  xmm0, xmmword ptr [rsi+68h]
0x180001d77  mov     esi, 0Dh
0x180001d7c  cmovnz  r13, r12
0x180001d80  movaps  [rsp+178h+var_78], xmm1
0x180001d88  movaps  [rsp+178h+var_68], xmm0
0x180001d90  mov     rdx, [r14]; Src
0x180001d93  mov     rcx, r13; void *
0x180001d96  mov     rdi, [r14+8]
0x180001d9a  sub     rdi, rdx
0x180001d9d  sar     rdi, 1
0x180001da0  cmp     r15, rdi
0x180001da3  mov     r12, rdi
0x180001da6  cmovb   r12, r15
0x180001daa  lea     rbx, [r12+r12]
0x180001dae  mov     r8, rbx; Size
0x180001db1  call    memcpy_0
0x180001db6  add     r13, rbx
0x180001db9  sub     r15, r12
0x180001dbc  cmp     r12, rdi
0x180001dbf  jb      short loc_180001DD0
0x180001dc1  add     rbp, r12
0x180001dc4  add     r14, 10h
0x180001dc8  sub     rsi, 1
0x180001dcc  jnz     short loc_180001D90
0x180001dce  jmp     short loc_180001DD5
0x180001dd0  test    rsi, rsi
0x180001dd3  jnz     short loc_180001DF6
0x180001dd5  test    r15, r15
0x180001dd8  jz      short loc_180001DF1
0x180001dda  mov     rdx, [rsp+178h+var_138]
0x180001ddf  xor     eax, eax
0x180001de1  mov     [r13+0], ax
0x180001de6  lea     rax, [rbp+1]
0x180001dea  mov     [rdx], rax
0x180001ded  xor     eax, eax
0x180001def  jmp     short loc_180001E3D
0x180001df1  test    rsi, rsi
0x180001df4  jz      short loc_180001E14
0x180001df6  mov     rcx, [r14+8]
0x180001dfa  sub     rcx, [r14]
0x180001dfd  sar     rcx, 1
0x180001e00  add     rcx, rbp
0x180001e03  cmp     rcx, rbp
0x180001e06  jb      short loc_180001E38
0x180001e08  add     r14, 10h
0x180001e0c  mov     rbp, rcx
0x180001e0f  dec     rsi
0x180001e12  jmp     short loc_180001DF1
0x180001e14  lea     rcx, [rbp+1]
0x180001e18  cmp     rcx, rbp
0x180001e1b  jb      short loc_180001E38
0x180001e1d  test    r13, r13
0x180001e20  jz      short loc_180001E29
0x180001e22  xor     eax, eax
0x180001e24  mov     [r13-2], ax
0x180001e29  mov     rdx, [rsp+178h+var_138]
0x180001e2e  mov     eax, 7Ah ; 'z'
0x180001e33  mov     [rdx], rcx
0x180001e36  jmp     short loc_180001E3D
0x180001e38  mov     eax, 216h
0x180001e3d  mov     r14, [rsp+178h+var_38]
0x180001e45  mov     r13, [rsp+178h+var_30]
0x180001e4d  mov     rbp, [rsp+178h+arg_18]
0x180001e55  mov     rcx, [rsp+178h+var_48]
0x180001e5d  xor     rcx, rsp; StackCookie
0x180001e60  call    __security_check_cookie
0x180001e65  add     rsp, 150h
0x180001e6c  pop     r15
0x180001e6e  pop     r12
0x180001e70  pop     rdi
0x180001e71  pop     rsi
0x180001e72  pop     rbx
0x180001e73  retn
```
