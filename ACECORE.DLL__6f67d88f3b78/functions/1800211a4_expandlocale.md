# _expandlocale

- ea: `0x1800211a4`
- end: `0x180021766`
- name: `_expandlocale`
- size: `1474`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `9`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180009dac`
- `0x1800368e0`
- `0x18013b9c0`
- `0x18013c414`
- `0x18014afe0`
- `0x18016817c`
- `0x180187bc4`
- `0x18018c614`
- `0x18018ce44`

## callees

- `0x1800061d0`
- `0x18001fff8`
- `0x180020364`
- `0x1800211a4`
- `0x1800243bc`
- `0x18002cf88`
- `0x180046400`
- `0x18004b7d0`
- `0x18004b840`
- `0x18004c160`
- `0x18004ce50`
- `0x18004d170`
- `0x18004d6f4`
- `0x1801d4f70`
- `0x1801d6022`
- `0x1801d6c50`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800212f8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180021578`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800212f8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180021578`
- `Mso30Win32Client!Mso30Win32Client_55665` at `0x180021512`
- `Mso30Win32Client!Mso30Win32Client_55665` at `0x180021512`

## string_xrefs

- `0x18002142b`: `ComplexTypeObjectID`
- `0x180021508`: `MSysComplexType_Attachment`

## pseudocode

```c
__int64 __fastcall expandlocale(__int64 a1, int a2, int a3, const wchar_t *a4, int a5, wchar_t *a6, int a7)
{
  unsigned __int64 v10; // rdi
  int v12; // ebx
  int v14; // eax
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, __int64, __int64, int *, int, unsigned int *, __int64 *, _QWORD); // rax
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 (__fastcall *v23)(__int64, __int64, __int64, int *, int, unsigned int *, __int64 *, _QWORD); // rax
  __int64 v24; // rcx
  int v25; // eax
  const wchar_t *v26; // r8
  wchar_t *v27; // rsi
  __int64 v28; // rdi
  __int64 *v29; // r12
  __int64 v30; // r15
  char *v31; // rsi
  int v32; // r12d
  __int128 v33; // xmm0
  __int64 v34; // rcx
  __int64 *v35; // [rsp+30h] [rbp-D0h]
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  int v39; // [rsp+60h] [rbp-A0h] BYREF
  int v40; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v41[2]; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44[14]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Destination[72]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v46[144]; // [rsp+1A0h] [rbp+A0h] BYREF

  v40 = a3;
  v41[0] = a6;
  v38 = -1;
  v43 = -1;
  v10 = -1;
  v36 = 0;
  v39 = 0;
  v37 = 0;
  v12 = 0;
  memset(v44, 0, 0x68u);
  if ( !a6 || !a7 )
    return 4294966293LL;
  if ( a3 )
  {
    if ( a4 )
      return 4294966293LL;
  }
  else if ( !a4 )
  {
    return 4294966293LL;
  }
  *(__int64 *)((char *)v44 + 4) = -1;
  Destination[0] = 0;
  if ( a3 )
  {
    v42 = -1;
    v35 = &v38;
    v14 = sub_18001FFF8(a1, a2, 0, (unsigned int)&v40);
    v10 = v38;
    v12 = v14;
    if ( v14 < 0 )
      goto LABEL_50;
    v12 = sub_180020364(a1, v38, L"FlatTableID", &v42);
    if ( v12 < 0 )
      goto LABEL_50;
    if ( v10 >= 0x1000 || v10 < qword_18025D6E0 )
    {
      v12 = -1310;
    }
    else
    {
      v16 = 4 * v10;
      v17 = qword_18023D6E0[4 * v10 + 3];
      if ( !v17 )
        goto LABEL_23;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *, int, unsigned int *, __int64 *, _QWORD))(v17 + 280);
      if ( !v18 )
        goto LABEL_23;
      LODWORD(v35) = 0;
      v19 = a1;
      if ( qword_18023D6E0[v16] != -1 )
        v19 = qword_18023D6E0[v16];
      v12 = v18(v19, qword_18023D6E0[v16 + 1], v42, &v36, 4, &v37, v35, 0);
    }
    if ( v12 < 0 )
      goto LABEL_50;
    v12 = sub_18004B840(v15, a2, v36, (unsigned int)Destination, 65, 0);
    if ( v12 < 0 )
      goto LABEL_50;
LABEL_27:
    v12 = sub_180020364(a1, v10, L"ComplexTypeObjectID", &v43);
    if ( v12 < 0 )
      goto LABEL_50;
    if ( v10 >= 0x1000 || v10 < qword_18025D6E0 )
    {
      v12 = -1310;
      goto LABEL_36;
    }
    v21 = 4 * v10;
    v22 = qword_18023D6E0[4 * v10 + 3];
    if ( v22 )
    {
      v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *, int, unsigned int *, __int64 *, _QWORD))(v22 + 280);
      if ( v23 )
      {
        LODWORD(v35) = 0;
        v24 = a1;
        if ( qword_18023D6E0[v21] != -1 )
          v24 = qword_18023D6E0[v21];
        v12 = v23(v24, qword_18023D6E0[v21 + 1], v43, &v39, 4, &v37, v35, 0);
LABEL_36:
        if ( v12 >= 0 )
        {
          v12 = sub_18004B840(v20, a2, v39, (unsigned int)v46, 65, 0);
          if ( v12 >= 0 )
          {
            a4 = (const wchar_t *)v46;
            goto LABEL_39;
          }
        }
        goto LABEL_50;
      }
    }
LABEL_23:
    v12 = -1003;
    goto LABEL_50;
  }
  if ( !a4 || !a5 )
  {
LABEL_39:
    if ( (unsigned int)Mso30Win32Client_55665(a4, L"MSysComplexType_Attachment", 1) )
    {
      v25 = 0;
      LODWORD(v38) = 0;
      if ( Destination[0] )
      {
        sub_18002CF88(a1, a2, (unsigned int)Destination, 0, 0, (__int64)&v38);
        v25 = v38;
      }
      if ( a7 > 0 )
      {
        v26 = L"FileName";
        if ( v25 )
          v26 = L"FileURL";
        wcsncpy_s(v41[0], a7, v26, 0xFFFFFFFFFFFFFFFFuLL);
      }
    }
    else
    {
      v12 = sub_1800061D0(a1, a2, (_DWORD)a4, 0, (__int64)v44, 104, 1);
      if ( v12 >= 0 )
      {
        v12 = sub_18004CE50(a1, *(__int64 *)((char *)v44 + 4), 0x80000000LL, 0);
        if ( v12 >= 0 )
        {
          v27 = v41[0];
          v12 = sub_18004D170(a1, *(unsigned __int64 *)((char *)v44 + 4), v44[3]);
          if ( v12 >= 0 )
            v27[(unsigned __int64)v37 >> 1] = 0;
        }
      }
    }
    goto LABEL_50;
  }
  v12 = sub_18004B7D0(a1, a2, (unsigned int)L"Tables", (_DWORD)a4, (__int64)&v36);
  if ( v12 >= 0 )
  {
    v35 = &v38;
    v12 = sub_18001FFF8(a1, a2, 2, (unsigned int)&v36);
    if ( v12 < 0 )
    {
      v10 = v38;
      goto LABEL_50;
    }
    wcsncpy_s(Destination, 0x41u, a4, 0xFFFFFFFFFFFFFFFFuLL);
    v10 = v38;
    goto LABEL_27;
  }
LABEL_50:
  if ( v12 == -1601 || v12 == -1811 )
  {
    v12 = -1305;
    *(__int64 *)((char *)v44 + 4) = -1;
  }
  if ( v10 <= 0xFFF && v10 >= qword_18025D6E0 )
  {
    v28 = 4 * v10;
    v29 = (__int64 *)qword_18023D6E0[v28 + 3];
    if ( v29 != qword_1801DBF50 )
    {
      v30 = (int)sub_180046400(a1);
      v31 = 0;
      if ( v29 )
      {
        if ( v29[3] )
        {
          v32 = 0;
          v41[0] = (wchar_t *)-1LL;
          v41[1] = (wchar_t *)-1LL;
          if ( (unsigned int)v30 <= 0x3F && qword_18025EA80 )
            v31 = (char *)qword_18025EA80 + 3592 * v30;
          if ( (int)v30 >= 0 && v31 )
          {
            v33 = *((_OWORD *)v31 + 218);
            v32 = *((_DWORD *)v31 + 876);
            *((_QWORD *)v31 + 436) = a1;
            *(_OWORD *)v41 = v33;
            *((_QWORD *)v31 + 437) = sub_1800243BC(a1);
          }
          v34 = a1;
          if ( qword_18023D6E0[v28] != -1 )
            v34 = qword_18023D6E0[v28];
          (*(void (__fastcall **)(__int64, __int64))(qword_18023D6E0[v28 + 3] + 24))(v34, qword_18023D6E0[v28 + 1]);
          if ( (int)v30 >= 0 && v31 )
          {
            *((_OWORD *)v31 + 218) = *(_OWORD *)v41;
            *((_DWORD *)v31 + 876) = v32;
          }
        }
      }
    }
  }
  if ( (unsigned int)sub_18004D6F4(*(__int64 *)((char *)v44 + 4)) )
    sub_18004C160(a1, *(__int64 *)((char *)v44 + 4));
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800211a4  push    rbp
0x1800211a6  push    rbx
0x1800211a7  push    rsi
0x1800211a8  push    rdi
0x1800211a9  push    r12
0x1800211ab  push    r13
0x1800211ad  push    r14
0x1800211af  push    r15
0x1800211b1  lea     rbp, [rsp-148h]
0x1800211b9  sub     rsp, 248h
0x1800211c0  mov     rax, cs:__security_cookie
0x1800211c7  xor     rax, rsp
0x1800211ca  mov     [rbp+180h+var_50], rax
0x1800211d1  mov     r13, [rbp+180h+arg_28]
0x1800211d8  xor     eax, eax
0x1800211da  mov     r14, rcx
0x1800211dd  mov     [rsp+280h+var_218], r8d
0x1800211e2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800211e6  mov     [rsp+280h+var_210], r13
0x1800211eb  mov     r12d, r8d
0x1800211ee  mov     [rsp+280h+var_228], rcx
0x1800211f3  mov     r15, rdx
0x1800211f6  mov     [rbp+180h+var_1F0], rcx
0x1800211fa  mov     rdi, rcx
0x1800211fd  mov     [rsp+280h+var_230], eax
0x180021201  lea     r8d, [rax+68h]; Size
0x180021205  mov     [rsp+280h+var_220], eax
0x180021209  xor     edx, edx; Val
0x18002120b  mov     [rsp+280h+var_22C], eax
0x18002120f  lea     rcx, [rbp+180h+var_1E0]; void *
0x180021213  mov     rsi, r9
0x180021216  mov     ebx, eax
0x180021218  call    memset
0x18002121d  xor     eax, eax
0x18002121f  test    r13, r13
0x180021222  jz      short loc_18002123A
0x180021224  movsxd  r13, [rbp+180h+arg_30]
0x18002122b  test    r13d, r13d
0x18002122e  jz      short loc_18002123A
0x180021230  test    r12d, r12d
0x180021233  jz      short loc_180021262
0x180021235  test    rsi, rsi
0x180021238  jz      short loc_180021267
0x18002123a  mov     eax, 0FFFFFC15h
0x18002123f  mov     rcx, [rbp+180h+var_50]
0x180021246  xor     rcx, rsp; StackCookie
0x180021249  call    __security_check_cookie
0x18002124e  add     rsp, 248h
0x180021255  pop     r15
0x180021257  pop     r14
0x180021259  pop     r13
0x18002125b  pop     r12
0x18002125d  pop     rdi
0x18002125e  pop     rsi
0x18002125f  pop     rbx
0x180021260  pop     rbp
0x180021261  retn
0x180021262  test    rsi, rsi
0x180021265  jz      short loc_18002123A
0x180021267  mov     [rbp+180h+var_1DC], 0FFFFFFFFFFFFFFFFh
0x18002126f  mov     [rbp+180h+Destination], ax
0x180021273  test    r12d, r12d
0x180021276  jnz     loc_180021312
0x18002127c  xor     r12d, r12d
0x18002127f  test    rsi, rsi
0x180021282  jz      loc_180021502
0x180021288  cmp     [rbp+180h+arg_20], r12d
0x18002128f  jz      loc_180021502
0x180021295  lea     rax, [rsp+280h+var_230]
0x18002129a  mov     r9, rsi
0x18002129d  lea     r8, aTables
0x1800212a4  mov     [rsp+280h+var_260], rax
0x1800212a9  mov     rdx, r15
0x1800212ac  mov     rcx, r14
0x1800212af  call    sub_18004B7D0
0x1800212b4  mov     ebx, eax
0x1800212b6  test    eax, eax
0x1800212b8  js      loc_180021618
0x1800212be  lea     rax, [rsp+280h+var_228]
0x1800212c3  mov     rdx, r15
0x1800212c6  mov     [rsp+280h+var_250], rax
0x1800212cb  lea     r9, [rsp+280h+var_230]
0x1800212d0  lea     r8d, [r12+2]
0x1800212d5  mov     dword ptr [rsp+280h+var_258], r12d
0x1800212da  mov     rcx, r14
0x1800212dd  call    sub_18001FFF8
0x1800212e2  mov     ebx, eax
0x1800212e4  test    eax, eax
0x1800212e6  js      short loc_180021308
0x1800212e8  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800212ec  lea     edx, [r12+41h]; SizeInWords
0x1800212f1  mov     r8, rsi; Source
0x1800212f4  lea     rcx, [rbp+180h+Destination]; Destination
0x1800212f8  call    cs:wcsncpy_s
0x1800212fe  mov     rdi, [rsp+280h+var_228]
0x180021303  jmp     loc_180021424
0x180021308  mov     rdi, [rsp+280h+var_228]
0x18002130d  jmp     loc_180021618
0x180021312  lea     rax, [rsp+280h+var_228]
0x180021317  mov     [rbp+180h+var_1F8], 0FFFFFFFFFFFFFFFFh
0x18002131f  mov     [rsp+280h+var_250], rax
0x180021324  lea     r9, [rsp+280h+var_218]
0x180021329  xor     r12d, r12d
0x18002132c  xor     r8d, r8d
0x18002132f  mov     rdx, r15
0x180021332  mov     dword ptr [rsp+280h+var_258], r12d
0x180021337  mov     rcx, r14
0x18002133a  call    sub_18001FFF8
0x18002133f  mov     rdi, [rsp+280h+var_228]
0x180021344  mov     ebx, eax
0x180021346  test    eax, eax
0x180021348  js      loc_180021618
0x18002134e  lea     r9, [rbp+180h+var_1F8]
0x180021352  mov     rdx, rdi
0x180021355  lea     r8, aFlattableid
0x18002135c  mov     rcx, r14
0x18002135f  call    sub_180020364
0x180021364  mov     ebx, eax
0x180021366  test    eax, eax
0x180021368  js      loc_180021618
0x18002136e  cmp     rdi, 1000h
0x180021375  jnb     short loc_1800213EF
0x180021377  cmp     rdi, cs:qword_18025D6E0
0x18002137e  jb      short loc_1800213EF
0x180021380  mov     rdx, rdi
0x180021383  lea     r10, qword_18023D6E0
0x18002138a  shl     rdx, 5
0x18002138e  mov     rax, [rdx+r10+18h]
0x180021393  test    rax, rax
0x180021396  jz      short loc_1800213E5
0x180021398  mov     rax, [rax+118h]
0x18002139f  test    rax, rax
0x1800213a2  jz      short loc_1800213E5
0x1800213a4  cmp     qword ptr [rdx+r10], 0FFFFFFFFFFFFFFFFh
0x1800213a9  lea     r8, [rsp+280h+var_22C]
0x1800213ae  mov     [rsp+280h+var_248], r12
0x1800213b3  lea     r9, [rsp+280h+var_230]
0x1800213b8  mov     dword ptr [rsp+280h+var_250], r12d
0x1800213bd  mov     rcx, r14
0x1800213c0  cmovnz  rcx, [rdx+r10]
0x1800213c5  mov     rdx, [rdx+r10+8]
0x1800213ca  mov     [rsp+280h+var_258], r8
0x1800213cf  mov     r8, [rbp+180h+var_1F8]
0x1800213d3  mov     dword ptr [rsp+280h+var_260], 4
0x1800213db  call    cs:__guard_dispatch_icall_fptr
0x1800213e1  mov     ebx, eax
0x1800213e3  jmp     short loc_1800213F4
0x1800213e5  mov     ebx, 0FFFFFC15h
0x1800213ea  jmp     loc_18002161F
0x1800213ef  mov     ebx, 0FFFFFAE2h
0x1800213f4  test    ebx, ebx
0x1800213f6  js      loc_180021618
0x1800213fc  mov     r8d, [rsp+280h+var_230]
0x180021401  lea     r9, [rbp+180h+Destination]
0x180021405  mov     [rsp+280h+var_258], r12
0x18002140a  mov     rdx, r15
0x18002140d  mov     dword ptr [rsp+280h+var_260], 41h ; 'A'
0x180021415  call    sub_18004B840
0x18002141a  mov     ebx, eax
0x18002141c  test    eax, eax
0x18002141e  js      loc_180021618
0x180021424  lea     r9, [rbp+180h+var_1F0]
0x180021428  mov     rdx, rdi
0x18002142b  lea     r8, aComplextypeobj
0x180021432  mov     rcx, r14
0x180021435  call    sub_180020364
0x18002143a  mov     ebx, eax
0x18002143c  test    eax, eax
0x18002143e  js      loc_180021618
0x180021444  cmp     rdi, 1000h
0x18002144b  jnb     short loc_1800214C3
0x18002144d  cmp     rdi, cs:qword_18025D6E0
0x180021454  jb      short loc_1800214C3
0x180021456  mov     rdx, rdi
0x180021459  lea     r10, qword_18023D6E0
0x180021460  shl     rdx, 5
0x180021464  mov     rax, [rdx+r10+18h]
0x180021469  test    rax, rax
0x18002146c  jz      loc_1800213E5
0x180021472  mov     rax, [rax+118h]
0x180021479  test    rax, rax
0x18002147c  jz      loc_1800213E5
0x180021482  cmp     qword ptr [rdx+r10], 0FFFFFFFFFFFFFFFFh
0x180021487  lea     r8, [rsp+280h+var_22C]
0x18002148c  mov     [rsp+280h+var_248], r12
0x180021491  lea     r9, [rsp+280h+var_220]
0x180021496  mov     dword ptr [rsp+280h+var_250], r12d
0x18002149b  mov     rcx, r14
0x18002149e  cmovnz  rcx, [rdx+r10]
0x1800214a3  mov     rdx, [rdx+r10+8]
0x1800214a8  mov     [rsp+280h+var_258], r8
0x1800214ad  mov     r8, [rbp+180h+var_1F0]
0x1800214b1  mov     dword ptr [rsp+280h+var_260], 4
0x1800214b9  call    cs:__guard_dispatch_icall_fptr
0x1800214bf  mov     ebx, eax
0x1800214c1  jmp     short loc_1800214C8
0x1800214c3  mov     ebx, 0FFFFFAE2h
0x1800214c8  test    ebx, ebx
0x1800214ca  js      loc_180021618
0x1800214d0  mov     r8d, [rsp+280h+var_220]
0x1800214d5  lea     r9, [rbp+180h+var_E0]
0x1800214dc  mov     [rsp+280h+var_258], r12
0x1800214e1  mov     rdx, r15
0x1800214e4  mov     dword ptr [rsp+280h+var_260], 41h ; 'A'
0x1800214ec  call    sub_18004B840
0x1800214f1  mov     ebx, eax
0x1800214f3  test    eax, eax
0x1800214f5  js      loc_180021618
0x1800214fb  lea     rsi, [rbp+180h+var_E0]
0x180021502  mov     r8d, 1
0x180021508  lea     rdx, aMsyscomplextyp_8
0x18002150f  mov     rcx, rsi
0x180021512  call    cs:Mso30Win32Client_55665
0x180021518  test    eax, eax
0x18002151a  jz      short loc_180021583
0x18002151c  mov     eax, r12d
0x18002151f  mov     dword ptr [rsp+280h+var_228], eax
0x180021523  cmp     [rbp+180h+Destination], r12w
0x180021528  jz      short loc_18002154F
0x18002152a  lea     rax, [rsp+280h+var_228]
0x18002152f  xor     r9d, r9d
0x180021532  mov     [rsp+280h+var_258], rax
0x180021537  lea     r8, [rbp+180h+Destination]
0x18002153b  mov     rdx, r15
0x18002153e  mov     [rsp+280h+var_260], r12
0x180021543  mov     rcx, r14
0x180021546  call    sub_18002CF88
0x18002154b  mov     eax, dword ptr [rsp+280h+var_228]
0x18002154f  test    r13d, r13d
0x180021552  jle     loc_180021618
0x180021558  test    eax, eax
0x18002155a  lea     rcx, aFileurl
0x180021561  lea     r8, aFilename
0x180021568  mov     rdx, r13; SizeInWords
0x18002156b  cmovnz  r8, rcx; Source
0x18002156f  mov     rcx, [rsp+280h+var_210]; Destination
0x180021574  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180021578  call    cs:wcsncpy_s
0x18002157e  jmp     loc_180021618
0x180021583  mov     dword ptr [rsp+280h+var_250], 1
0x18002158b  lea     rax, [rbp+180h+var_1E0]
0x18002158f  mov     dword ptr [rsp+280h+var_258], 68h ; 'h'
0x180021597  xor     r9d, r9d
0x18002159a  mov     r8, rsi
0x18002159d  mov     [rsp+280h+var_260], rax
0x1800215a2  mov     rdx, r15
0x1800215a5  mov     rcx, r14
0x1800215a8  call    sub_1800061D0
0x1800215ad  mov     ebx, eax
0x1800215af  test    eax, eax
0x1800215b1  js      short loc_180021618
0x1800215b3  mov     rdx, [rbp+180h+var_1DC]
0x1800215b7  xor     r9d, r9d
0x1800215ba  mov     r8d, 80000000h
0x1800215c0  mov     rcx, r14
0x1800215c3  call    sub_18004CE50
0x1800215c8  mov     ebx, eax
0x1800215ca  test    eax, eax
0x1800215cc  js      short loc_180021618
0x1800215ce  mov     rsi, [rsp+280h+var_210]
0x1800215d3  lea     rcx, [rsp+280h+var_22C]
0x1800215d8  mov     r8, [rbp+180h+var_1C8]
0x1800215dc  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r13*2]
0x1800215e4  mov     rdx, [rbp+180h+var_1DC]
0x1800215e8  mov     r9, rsi
0x1800215eb  mov     [rsp+280h+var_248], r12
0x1800215f0  mov     dword ptr [rsp+280h+var_250], r12d
0x1800215f5  mov     [rsp+280h+var_258], rcx
0x1800215fa  mov     rcx, r14
0x1800215fd  mov     dword ptr [rsp+280h+var_260], eax
0x180021601  call    sub_18004D170
0x180021606  mov     ebx, eax
0x180021608  test    eax, eax
0x18002160a  js      short loc_180021618
0x18002160c  mov     eax, [rsp+280h+var_22C]
0x180021610  shr     rax, 1
0x180021613  mov     [rsi+rax*2], r12w
0x180021618  lea     r10, qword_18023D6E0
0x18002161f  cmp     ebx, 0FFFFF9BFh
0x180021625  jz      short loc_18002162F
0x180021627  cmp     ebx, 0FFFFF8EDh
0x18002162d  jnz     short loc_18002163C
0x18002162f  mov     ebx, 0FFFFFAE7h
0x180021634  mov     [rbp+180h+var_1DC], 0FFFFFFFFFFFFFFFFh
0x18002163c  cmp     rdi, 0FFFh
0x180021643  ja      loc_180021745
0x180021649  cmp     rdi, cs:qword_18025D6E0
0x180021650  jb      loc_180021745
0x180021656  shl     rdi, 5
0x18002165a  lea     rax, qword_1801DBF50
0x180021661  mov     r12, [rdi+r10+18h]
0x180021666  cmp     r12, rax
0x180021669  jz      loc_180021745
0x18002166f  mov     rcx, r14
0x180021672  call    sub_180046400
0x180021677  xor     r13d, r13d
0x18002167a  movsxd  r15, eax
0x18002167d  mov     esi, r13d
0x180021680  test    r12, r12
0x180021683  jz      loc_180021745
  ... truncated ...
```
