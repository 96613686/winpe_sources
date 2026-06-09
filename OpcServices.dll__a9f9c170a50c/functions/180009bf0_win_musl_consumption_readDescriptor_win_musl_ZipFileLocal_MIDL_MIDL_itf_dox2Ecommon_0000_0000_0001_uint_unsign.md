# win_musl::consumption::readDescriptor(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint,unsigned __int64,unsigned __int64,uint *,uint *)

- ea: `0x180009bf0`
- end: `0x18000a028`
- name: `?readDescriptor@consumption@win_musl@@YA?AW4type_t@ZipHeaderResult@12@PEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@I_K2PEAI3@Z`
- size: `1080`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *, unsigned int, __int64, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800094c0`

## callees

- `0x180009bf0`
- `0x18000a030`
- `0x18000ad70`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x180009ca9`
- `msvcrt!memmove_s` at `0x180009ca9`

## string_xrefs

- `0x180009f69`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180009ff8`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180009fa5`: `win_musl::detail::vector_read`
- `0x180009f5a`: `win_musl::consumption::readDescriptor`
- `0x180009fe9`: `win_musl::consumption::readDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall win_musl::consumption::readDescriptor(
        _QWORD *a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        _DWORD *a7)
{
  __int64 v7; // r15
  __int64 v8; // r12
  _QWORD *v9; // r8
  _DWORD *v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  char v13; // dl
  char *v14; // rcx
  int v15; // ecx
  __int64 result; // rax
  unsigned int v17; // ecx
  bool v18; // cf
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // rax
  _QWORD *v23; // rdx
  char *v24; // rsi
  unsigned int v25; // eax
  unsigned int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r8
  _QWORD *v30; // rdx
  _BYTE v31[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  int Destination; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = *a2;
  v8 = a3;
  v9 = a1;
  *a6 = 8;
  v37 = a4;
  v34 = a1;
  if ( (unsigned int)v7 < 8 )
    goto LABEL_24;
  v10 = (_DWORD *)*((_QWORD *)a2 + 1);
  if ( *v10 == 134695760 )
  {
    if ( !v10 || (v12 = (unsigned __int64)(v10 + 1), v24 = (char *)v10 + v7, (_DWORD *)((char *)v10 + v7) == v10 + 1) )
    {
      v13 = 1;
      v11 = 0;
      DWORD1(v32) = 0;
      v12 = 0;
    }
    else
    {
      if ( (unsigned __int64)v10 > v12 || v12 > (unsigned __int64)v24 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x16Du,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expres"
                                                  "sion (cursor + sizeof(uint32_t))");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v11 = (unsigned int)((_DWORD)v24 - v12);
      DWORD1(v32) = 0;
      v13 = 1;
    }
  }
  else
  {
    if ( !v10 || (_DWORD *)((char *)v10 + v7) == v10 )
    {
      v11 = 0;
      DWORD1(v32) = 0;
      v12 = 0;
    }
    else
    {
      if ( (_DWORD *)((char *)v10 + v7) < v10 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x172u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expression (cursor)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v11 = (unsigned int)v7;
      DWORD1(v32) = 0;
      v12 = (unsigned __int64)v10;
    }
    v13 = 0;
  }
  v31[0] = v13;
  if ( (unsigned int)v11 < 4 )
  {
    v15 = 0;
  }
  else
  {
    Destination = 0;
    memmove_s(&Destination, 4u, (const void *const)v12, 4u);
    if ( v12 )
    {
      v14 = (char *)(v12 + 4);
      v11 += v12;
      if ( v11 == v12 + 4 )
      {
        LODWORD(v11) = 0;
        v12 = 0;
      }
      else
      {
        if ( v12 > (unsigned __int64)v14 || (unsigned __int64)v14 > v11 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0xABu,
            0x80070057,
            (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expr"
                                                    "ession (vector_begin(vector) + sizeof(T))");
          throw (SplException::THResultException *)pExceptionObject;
        }
        LODWORD(v11) = v11 - (_DWORD)v14;
        v12 += 4LL;
      }
    }
    else
    {
      LODWORD(v11) = 0;
      v12 = 0;
    }
    v15 = Destination;
    v13 = v31[0];
    v9 = v34;
    DWORD1(v32) = 0;
  }
  if ( v15 != (_DWORD)v8 )
    goto LABEL_16;
  v17 = 12;
  *a6 = 12;
  if ( v13 )
  {
    v17 = 16;
    *a6 = 16;
  }
  if ( (unsigned int)v7 < v17 )
  {
LABEL_24:
    result = 2;
    goto LABEL_17;
  }
  v18 = *((_BYTE *)v9 + 204) < 0x2Du;
  *(_QWORD *)&v32 = (unsigned int)v11;
  *((_QWORD *)&v32 + 1) = v12;
  if ( v18 )
  {
    *(_QWORD *)&v35 = (unsigned int)v11;
    *((_QWORD *)&v35 + 1) = v12;
    v36 = v35;
    v31[0] = 0;
    v25 = win_musl::detail::vector_read<unsigned int>(&v36, &v35, v31);
    v36 = v35;
    v26 = v25;
    v27 = win_musl::detail::vector_read<unsigned int>(&v36, &v35, v31);
    v28 = v26;
    v19 = v37;
    if ( v28 == v37 )
    {
      v29 = v27;
      if ( v27 == a5 )
      {
        v30 = v34;
        *a7 = v7 - v35;
        v30[21] = 4;
        v30[24] = (v8 << 32) | 4;
        result = 0;
        v30[22] = v28;
        v30[19] = 4;
        v30[20] = v29;
        return result;
      }
    }
  }
  else
  {
    v19 = v37;
  }
  *a6 += 8;
  if ( (unsigned int)v7 < *a6 )
    goto LABEL_24;
  v36 = v32;
  v31[0] = 0;
  v20 = win_musl::detail::vector_read<unsigned __int64>(&v36, &v32, v31);
  v36 = v32;
  v21 = v20;
  v22 = win_musl::detail::vector_read<unsigned __int64>(&v36, &v32, v31);
  if ( v21 != v19 || v22 != a5 )
  {
LABEL_16:
    result = 1;
LABEL_17:
    *a7 = 0;
    return result;
  }
  v23 = v34;
  *a7 = v7 - v32;
  v23[20] = v22;
  v23[24] = (v8 << 32) | 4;
  result = 0;
  v23[21] = 4;
  v23[22] = v21;
  v23[19] = 4;
  return result;
}

```

## disassembly

```asm
0x180009bf0  push    rbp
0x180009bf2  push    rbx
0x180009bf3  push    rsi
0x180009bf4  push    rdi
0x180009bf5  push    r12
0x180009bf7  push    r13
0x180009bf9  push    r14
0x180009bfb  push    r15
0x180009bfd  lea     rbp, [rsp-58h]
0x180009c02  sub     rsp, 158h
0x180009c09  mov     rax, cs:__security_cookie
0x180009c10  xor     rax, rsp
0x180009c13  mov     [rbp+90h+var_50], rax
0x180009c17  mov     r14, [rbp+90h+arg_28]
0x180009c1e  mov     r15d, [rdx]
0x180009c21  mov     r13, [rbp+90h+arg_30]
0x180009c28  mov     r12d, r8d
0x180009c2b  mov     r8, rcx
0x180009c2e  mov     dword ptr [r14], 8
0x180009c35  mov     [rbp+90h+var_100], r9
0x180009c39  mov     [rsp+190h+var_128], rcx
0x180009c3e  cmp     r15d, 8
0x180009c42  jb      loc_18000A021
0x180009c48  mov     rax, [rdx+8]
0x180009c4c  mov     edx, cs:dword_180138C98
0x180009c52  cmp     edx, [rax]
0x180009c54  jz      loc_180009E29
0x180009c5a  test    rax, rax
0x180009c5d  jz      loc_180009D6B
0x180009c63  lea     rsi, [rax+r15]
0x180009c67  cmp     rsi, rax
0x180009c6a  jz      loc_180009D6B
0x180009c70  jb      loc_180009FDD
0x180009c76  sub     esi, eax
0x180009c78  xor     ecx, ecx
0x180009c7a  xor     edi, edi
0x180009c7c  mov     dword ptr [rsp+190h+var_140+4], ecx
0x180009c80  mov     rbx, rax
0x180009c83  mov     eax, edi
0x180009c85  xor     dl, dl
0x180009c87  mov     [rsp+190h+var_150], dl
0x180009c8b  cmp     esi, 4
0x180009c8e  jb      loc_180009F92
0x180009c94  mov     r9d, 4; SourceSize
0x180009c9a  mov     [rsp+190h+Destination], edi
0x180009c9e  mov     edx, r9d; DestinationSize
0x180009ca1  lea     rcx, [rsp+190h+Destination]; Destination
0x180009ca6  mov     r8, rbx; Source
0x180009ca9  call    cs:__imp_memmove_s
0x180009caf  test    rbx, rbx
0x180009cb2  jz      loc_180009D7C
0x180009cb8  lea     rcx, [rbx+4]
0x180009cbc  add     rsi, rbx
0x180009cbf  cmp     rsi, rcx
0x180009cc2  jz      loc_180009E66
0x180009cc8  cmp     rbx, rcx
0x180009ccb  ja      loc_180009F99
0x180009cd1  cmp     rcx, rsi
0x180009cd4  ja      loc_180009F99
0x180009cda  sub     esi, ecx
0x180009cdc  mov     rbx, rcx
0x180009cdf  mov     ecx, [rsp+190h+Destination]
0x180009ce3  xor     eax, eax
0x180009ce5  movzx   edx, [rsp+190h+var_150]
0x180009cea  mov     r8, [rsp+190h+var_128]
0x180009cef  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009cf3  mov     eax, edi
0x180009cf5  cmp     ecx, r12d
0x180009cf8  jz      short loc_180009D23
0x180009cfa  mov     eax, 1
0x180009cff  mov     [r13+0], edi
0x180009d03  mov     rcx, [rbp+90h+var_50]
0x180009d07  xor     rcx, rsp; StackCookie
0x180009d0a  call    __security_check_cookie
0x180009d0f  add     rsp, 158h
0x180009d16  pop     r15
0x180009d18  pop     r14
0x180009d1a  pop     r13
0x180009d1c  pop     r12
0x180009d1e  pop     rdi
0x180009d1f  pop     rsi
0x180009d20  pop     rbx
0x180009d21  pop     rbp
0x180009d22  retn
0x180009d23  mov     ecx, 0Ch
0x180009d28  mov     [r14], ecx
0x180009d2b  test    dl, dl
0x180009d2d  jz      short loc_180009D37
0x180009d2f  mov     ecx, 10h
0x180009d34  mov     [r14], ecx
0x180009d37  cmp     r15d, ecx
0x180009d3a  jb      short loc_180009D64
0x180009d3c  cmp     byte ptr [r8+0CCh], 2Dh ; '-'
0x180009d44  mov     dword ptr [rsp+190h+var_140], esi
0x180009d48  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009d4c  mov     qword ptr [rsp+190h+var_140+8], rbx
0x180009d51  jb      loc_180009E70
0x180009d57  mov     rbx, [rbp+90h+var_100]
0x180009d5b  add     dword ptr [r14], 8
0x180009d5f  cmp     r15d, [r14]
0x180009d62  jnb     short loc_180009D86
0x180009d64  mov     eax, 2
0x180009d69  jmp     short loc_180009CFF
0x180009d6b  xor     edi, edi
0x180009d6d  xor     eax, eax
0x180009d6f  mov     esi, edi
0x180009d71  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009d75  mov     ebx, edi
0x180009d77  jmp     loc_180009C85
0x180009d7c  mov     esi, edi
0x180009d7e  mov     rbx, rdi
0x180009d81  jmp     loc_180009CDF
0x180009d86  movaps  xmm0, [rsp+190h+var_140]
0x180009d8b  lea     r8, [rsp+190h+var_150]
0x180009d90  lea     rdx, [rsp+190h+var_140]
0x180009d95  movdqa  [rbp+90h+var_110], xmm0
0x180009d9a  lea     rcx, [rbp+90h+var_110]
0x180009d9e  mov     [rsp+190h+var_150], 0
0x180009da3  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180009da8  movaps  xmm0, [rsp+190h+var_140]
0x180009dad  lea     r8, [rsp+190h+var_150]
0x180009db2  lea     rdx, [rsp+190h+var_140]
0x180009db7  movdqa  [rbp+90h+var_110], xmm0
0x180009dbc  lea     rcx, [rbp+90h+var_110]
0x180009dc0  mov     rsi, rax
0x180009dc3  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180009dc8  cmp     rsi, rbx
0x180009dcb  jnz     loc_180009CFA
0x180009dd1  cmp     rax, [rbp+90h+arg_20]
0x180009dd8  jnz     loc_180009CFA
0x180009dde  mov     rdx, [rsp+190h+var_128]
0x180009de3  mov     rcx, r12
0x180009de6  sub     r15d, dword ptr [rsp+190h+var_140]
0x180009deb  mov     [r13+0], r15d
0x180009def  shl     rcx, 20h
0x180009df3  or      rcx, 4
0x180009df7  mov     [rdx+0A0h], rax
0x180009dfe  mov     [rdx+0C0h], rcx
0x180009e05  xor     eax, eax
0x180009e07  mov     qword ptr [rdx+0A8h], 4
0x180009e12  mov     [rdx+0B0h], rsi
0x180009e19  mov     qword ptr [rdx+98h], 4
0x180009e24  jmp     loc_180009D03
0x180009e29  test    rax, rax
0x180009e2c  jz      loc_180009F28
0x180009e32  lea     rbx, [rax+4]
0x180009e36  lea     rsi, [rax+r15]
0x180009e3a  cmp     rsi, rbx
0x180009e3d  jz      loc_180009F3B
0x180009e43  cmp     rax, rbx
0x180009e46  ja      loc_180009F4E
0x180009e4c  cmp     rbx, rsi
0x180009e4f  ja      loc_180009F4E
0x180009e55  xor     eax, eax
0x180009e57  sub     esi, ebx
0x180009e59  xor     edi, edi
0x180009e5b  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009e5f  mov     dl, 1
0x180009e61  jmp     loc_180009C87
0x180009e66  mov     esi, edi
0x180009e68  mov     rbx, rdi
0x180009e6b  jmp     loc_180009CDF
0x180009e70  mov     dword ptr [rsp+190h+var_120], esi
0x180009e74  lea     r8, [rsp+190h+var_150]
0x180009e79  mov     dword ptr [rsp+190h+var_120+4], eax
0x180009e7d  lea     rdx, [rsp+190h+var_120]
0x180009e82  mov     qword ptr [rsp+190h+var_120+8], rbx
0x180009e87  lea     rcx, [rbp+90h+var_110]
0x180009e8b  movaps  xmm0, [rsp+190h+var_120]
0x180009e90  movdqa  [rbp+90h+var_110], xmm0
0x180009e95  mov     [rsp+190h+var_150], 0
0x180009e9a  call    ??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180009e9f  movaps  xmm0, [rsp+190h+var_120]
0x180009ea4  lea     r8, [rsp+190h+var_150]
0x180009ea9  lea     rdx, [rsp+190h+var_120]
0x180009eae  movdqa  [rbp+90h+var_110], xmm0
0x180009eb3  lea     rcx, [rbp+90h+var_110]
0x180009eb7  mov     ebx, eax
0x180009eb9  call    ??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180009ebe  mov     ecx, ebx
0x180009ec0  mov     rbx, [rbp+90h+var_100]
0x180009ec4  cmp     rcx, rbx
0x180009ec7  jnz     loc_180009D5B
0x180009ecd  mov     r8d, eax
0x180009ed0  cmp     r8, [rbp+90h+arg_20]
0x180009ed7  jnz     loc_180009D5B
0x180009edd  mov     rdx, [rsp+190h+var_128]
0x180009ee2  mov     rax, r12
0x180009ee5  sub     r15d, dword ptr [rsp+190h+var_120]
0x180009eea  mov     [r13+0], r15d
0x180009eee  shl     rax, 20h
0x180009ef2  or      rax, 4
0x180009ef6  mov     qword ptr [rdx+0A8h], 4
0x180009f01  mov     [rdx+0C0h], rax
0x180009f08  xor     eax, eax
0x180009f0a  mov     [rdx+0B0h], rcx
0x180009f11  mov     qword ptr [rdx+98h], 4
0x180009f1c  mov     [rdx+0A0h], r8
0x180009f23  jmp     loc_180009D03
0x180009f28  xor     edi, edi
0x180009f2a  mov     dl, 1
0x180009f2c  xor     eax, eax
0x180009f2e  mov     esi, edi
0x180009f30  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009f34  mov     ebx, edi
0x180009f36  jmp     loc_180009C87
0x180009f3b  xor     edi, edi
0x180009f3d  mov     dl, 1
0x180009f3f  xor     eax, eax
0x180009f41  mov     esi, edi
0x180009f43  mov     dword ptr [rsp+190h+var_140+4], eax
0x180009f47  mov     ebx, edi
0x180009f49  jmp     loc_180009C87
0x180009f4e  lea     rax, aNewBeginIsOutO; "new_begin is out-of-range: vector expre"...
0x180009f55  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x180009f5a  lea     r9, aWinMuslConsump_0; "win_musl::consumption::readDescriptor"
0x180009f61  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x180009f69  lea     r8, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180009f70  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180009f74  mov     [rsp+190h+var_170], 16Dh; unsigned int
0x180009f7c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180009f81  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180009f88  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180009f8c  call    _CxxThrowException_0
0x180009f92  mov     ecx, edi
0x180009f94  jmp     loc_180009CF5
0x180009f99  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x180009fa0  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x180009fa5  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x180009fac  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x180009fb4  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x180009fbb  lea     rcx, [rbp+90h+pExceptionObject]; this
0x180009fbf  mov     [rsp+190h+var_170], 0ABh; unsigned int
0x180009fc7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180009fcc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180009fd3  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x180009fd7  call    _CxxThrowException_0
0x180009fdd  lea     rax, aNewBeginIsOutO_9; "new_begin is out-of-range: vector expre"...
0x180009fe4  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x180009fe9  lea     r9, aWinMuslConsump_0; "win_musl::consumption::readDescriptor"
0x180009ff0  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x180009ff8  lea     r8, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180009fff  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18000a003  mov     [rsp+190h+var_170], 172h; unsigned int
0x18000a00b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000a010  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000a017  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18000a01b  call    _CxxThrowException_0
0x18000a021  xor     edi, edi
0x18000a023  jmp     loc_180009D64
```
