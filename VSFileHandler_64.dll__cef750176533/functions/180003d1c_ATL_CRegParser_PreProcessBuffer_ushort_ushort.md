# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003d1c`
- end: `0x180004125`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `1033`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180005394`

## callees

- `0x180002238`
- `0x180003be8`
- `0x180003d1c`
- `0x180007700`
- `0x180008e2c`
- `0x18000bb9c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003fff`
- `KERNEL32!lstrcmpiW` at `0x180003fff`
- `USER32!CharNextW` at `0x180003e19`
- `USER32!CharNextW` at `0x180003e25`
- `USER32!CharNextW` at `0x180003e31`
- `USER32!CharNextW` at `0x180003e3d`
- `USER32!CharNextW` at `0x180003e8c`
- `USER32!CharNextW` at `0x180003ea2`
- `USER32!CharNextW` at `0x180003f1f`
- `USER32!CharNextW` at `0x180003f6b`
- `USER32!CharNextW` at `0x180004077`
- `USER32!CharNextW` at `0x180004090`
- `USER32!CharNextW` at `0x180003e19`
- `USER32!CharNextW` at `0x180003e25`
- `USER32!CharNextW` at `0x180003e31`
- `USER32!CharNextW` at `0x180003e3d`
- `USER32!CharNextW` at `0x180003e8c`
- `USER32!CharNextW` at `0x180003ea2`
- `USER32!CharNextW` at `0x180003f1f`
- `USER32!CharNextW` at `0x180003f6b`
- `USER32!CharNextW` at `0x180004077`
- `USER32!CharNextW` at `0x180004090`
- `ole32!CoTaskMemFree` at `0x1800040c3`
- `ole32!CoTaskMemFree` at `0x1800040c3`
- `ole32!CoTaskMemAlloc` at `0x180003dab`
- `ole32!CoTaskMemAlloc` at `0x180003dab`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  const wchar_t *v3; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  bool v10; // al
  int v11; // r13d
  char v12; // r12
  char v13; // r15
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rdx
  LPWSTR v20; // rax
  WCHAR v21; // cx
  const WCHAR *v22; // r12
  errno_t v23; // eax
  LPCWSTR v24; // r14
  int v25; // r15d
  __int64 v26; // rsi
  const unsigned __int16 *v27; // rdx
  __int64 v28; // r8
  const WCHAR *i; // rax
  unsigned __int16 *v30; // rcx
  char v32; // [rsp+20h] [rbp-59h]
  char v33; // [rsp+21h] [rbp-58h]
  bool v34; // [rsp+22h] [rbp-57h]
  LPVOID pv[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v37; // [rsp+40h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+50h] [rbp-29h] BYREF

  v3 = a2;
  v5 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
  }
  if ( !v9 )
  {
LABEL_12:
    v5 = -2147024882;
    goto LABEL_73;
  }
  *this = v3;
  v10 = ATL::_AtlRegisterPerUser;
  v34 = ATL::_AtlRegisterPerUser;
  v11 = 0;
  v12 = 0;
  v33 = 0;
  v13 = 0;
  v32 = 0;
  if ( *v3 )
  {
    while ( 1 )
    {
      if ( !v10 )
        goto LABEL_35;
      if ( !v11 )
      {
        v14 = wcsstr(v3, L"HKCR");
        if ( v14 )
        {
          if ( v14 == *this )
          {
            v15 = CharNextW(*this);
            *this = v15;
            v16 = CharNextW(v15);
            *this = v16;
            v17 = CharNextW(v16);
            *this = v17;
            *this = CharNextW(v17);
            v37 = 0;
            if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append(
                                  (ATL::CRegParser::CParseBuffer *)pv,
                                  L"HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClasses",
                                  31) )
              goto LABEL_12;
            v12 = 1;
            v33 = 1;
          }
        }
      }
      if ( **this == 39 )
      {
        if ( !v13 )
        {
          v13 = 1;
          v32 = 1;
          goto LABEL_35;
        }
        if ( *CharNextW(*this) == 39 )
        {
          v18 = CharNextW(*this);
          *this = v18;
          if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v18, 1) )
            goto LABEL_12;
          goto LABEL_35;
        }
        v13 = 0;
        v32 = 0;
      }
      else if ( v13 )
      {
        goto LABEL_35;
      }
      if ( **this == 123 )
      {
        ++v11;
      }
      else if ( **this == 125 && !--v11 && v12 == 1 )
      {
        v37 = 0;
        if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append(
                              (ATL::CRegParser::CParseBuffer *)pv,
                              L"\r\n\t}\r\n}\r\n",
                              9) )
          goto LABEL_12;
        v12 = 0;
        v33 = 0;
      }
LABEL_35:
      v19 = *this;
      if ( **this != 37 )
        goto LABEL_38;
      v20 = CharNextW(*this);
      *this = v20;
      v21 = *v20;
      if ( *v20 == 37 )
      {
        v19 = v20;
LABEL_38:
        if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v19, 1) )
          goto LABEL_12;
        goto LABEL_69;
      }
      v22 = 0;
      if ( !v20 )
        goto LABEL_41;
      while ( v21 )
      {
        if ( v21 == 37 )
        {
          v22 = v20;
          break;
        }
        v20 = CharNextW(v20);
        v21 = *v20;
      }
      if ( !v22 )
      {
LABEL_41:
        v5 = -2147352567;
        goto LABEL_73;
      }
      if ( (__int64)(((char *)v22 - (char *)*this) & 0xFFFFFFFFFFFFFFFEuLL) > 62 )
      {
        v5 = -2147467259;
        goto LABEL_73;
      }
      _mm_lfence();
      v23 = wcsncpy_s(Destination, 0x20u, *this, (int)(v22 - *this));
      if ( v23 )
      {
        if ( v23 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v23 == 22 || v23 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v23 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v24 = this[1];
      v25 = 0;
      v26 = 0;
      if ( *((int *)v24 + 6) <= 0 )
        goto LABEL_41;
      while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v24 + 1) + 8 * v26), Destination) )
      {
        ++v25;
        ++v26;
        if ( v25 >= *((_DWORD *)v24 + 6) )
          goto LABEL_41;
      }
      if ( v26 == -1 )
        goto LABEL_41;
      if ( v26 < 0 || v25 >= *((_DWORD *)v24 + 6) )
        ATL::AtlThrowImpl(-2147483637);
      _mm_lfence();
      v27 = *(const unsigned __int16 **)(*((_QWORD *)v24 + 2) + 8 * v26);
      if ( !v27 )
        goto LABEL_41;
      v37 = 0;
      v28 = -1;
      do
        ++v28;
      while ( v27[v28] );
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v27, v28) )
        goto LABEL_12;
      for ( i = *this; i != v22; *this = i )
        i = CharNextW(i);
      v12 = v33;
      v13 = v32;
LABEL_69:
      v3 = CharNextW(*this);
      *this = v3;
      if ( !*v3 )
        break;
      v10 = v34;
    }
  }
  v30 = (unsigned __int16 *)pv[1];
  pv[1] = 0;
  *a3 = v30;
LABEL_73:
  CoTaskMemFree(pv[1]);
  return v5;
}

```

## disassembly

```asm
0x180003d1c  mov     [rsp-8+arg_8], rbx
0x180003d21  push    rbp
0x180003d22  push    rsi
0x180003d23  push    rdi
0x180003d24  push    r12
0x180003d26  push    r13
0x180003d28  push    r14
0x180003d2a  push    r15
0x180003d2c  lea     rbp, [rsp-27h]
0x180003d31  sub     rsp, 0A0h
0x180003d38  mov     rax, cs:__security_cookie
0x180003d3f  xor     rax, rsp
0x180003d42  mov     [rbp+57h+var_40], rax
0x180003d46  mov     rax, r8
0x180003d49  mov     [rbp+57h+var_A8], rax
0x180003d4d  mov     rsi, rdx
0x180003d50  mov     rdi, rcx
0x180003d53  xor     ebx, ebx
0x180003d55  test    rdx, rdx
0x180003d58  jz      loc_1800040CD
0x180003d5e  test    rax, rax
0x180003d61  jz      loc_1800040CD
0x180003d67  mov     [r8], rbx
0x180003d6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d6e  inc     rax
0x180003d71  cmp     [rdx+rax*2], bx
0x180003d75  jnz     short loc_180003D6E
0x180003d77  add     eax, eax
0x180003d79  xorps   xmm0, xmm0
0x180003d7c  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180003d80  mov     ecx, 3E8h
0x180003d85  cmp     eax, 64h ; 'd'
0x180003d88  cmovl   eax, ecx
0x180003d8b  mov     dword ptr [rbp+57h+pv], ebx
0x180003d8e  mov     dword ptr [rbp+57h+pv+4], eax
0x180003d91  mov     ecx, eax
0x180003d93  add     rcx, rcx
0x180003d96  mov     eax, 0FFFFFFFFh
0x180003d9b  cmp     rcx, rax
0x180003d9e  jbe     short loc_180003DA9
0x180003da0  mov     rax, rbx
0x180003da3  mov     [rbp+57h+pv+8], rbx
0x180003da7  jmp     short loc_180003DBD
0x180003da9  mov     ecx, ecx; cb
0x180003dab  call    cs:__imp_CoTaskMemAlloc
0x180003db1  mov     [rbp+57h+pv+8], rax
0x180003db5  test    rax, rax
0x180003db8  jz      short loc_180003DBD
0x180003dba  mov     [rax], bx
0x180003dbd  test    rax, rax
0x180003dc0  jnz     short loc_180003DCC
0x180003dc2  mov     ebx, 8007000Eh
0x180003dc7  jmp     loc_1800040BF
0x180003dcc  mov     [rdi], rsi
0x180003dcf  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA; bool ATL::_AtlRegisterPerUser
0x180003dd5  mov     [rbp+57h+var_AE], al
0x180003dd8  mov     r13d, ebx
0x180003ddb  mov     r12b, bl
0x180003dde  mov     [rbp+57h+var_AF], bl
0x180003de1  mov     r15b, bl
0x180003de4  mov     [rbp+57h+var_B0], bl
0x180003de7  cmp     [rsi], bx
0x180003dea  jz      loc_1800040B0
0x180003df0  cmp     al, 1
0x180003df2  jnz     loc_180003F13
0x180003df8  test    r13d, r13d
0x180003dfb  jnz     short loc_180003E6E
0x180003dfd  lea     rdx, aHkcr; "HKCR"
0x180003e04  mov     rcx, rsi; Str
0x180003e07  call    wcsstr
0x180003e0c  test    rax, rax
0x180003e0f  jz      short loc_180003E6E
0x180003e11  cmp     rax, [rdi]
0x180003e14  jnz     short loc_180003E6E
0x180003e16  mov     rcx, [rdi]; lpsz
0x180003e19  call    cs:__imp_CharNextW
0x180003e1f  mov     [rdi], rax
0x180003e22  mov     rcx, rax; lpsz
0x180003e25  call    cs:__imp_CharNextW
0x180003e2b  mov     [rdi], rax
0x180003e2e  mov     rcx, rax; lpsz
0x180003e31  call    cs:__imp_CharNextW
0x180003e37  mov     [rdi], rax
0x180003e3a  mov     rcx, rax; lpsz
0x180003e3d  call    cs:__imp_CharNextW
0x180003e43  mov     [rdi], rax
0x180003e46  mov     [rbp+57h+var_90], rbx
0x180003e4a  lea     r8d, [r13+1Fh]; int
0x180003e4e  lea     rdx, aHkcuSoftwareCl; "HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClass"...
0x180003e55  lea     rcx, [rbp+57h+pv]; this
0x180003e59  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003e5e  nop
0x180003e5f  test    eax, eax
0x180003e61  jz      loc_180003DC2
0x180003e67  mov     r12b, 1
0x180003e6a  mov     [rbp+57h+var_AF], r12b
0x180003e6e  mov     rcx, [rdi]; lpsz
0x180003e71  mov     esi, 27h ; '''
0x180003e76  cmp     si, [rcx]
0x180003e79  jnz     short loc_180003EC7
0x180003e7b  test    r15b, r15b
0x180003e7e  jnz     short loc_180003E8C
0x180003e80  mov     r15b, 1
0x180003e83  mov     [rbp+57h+var_B0], r15b
0x180003e87  jmp     loc_180003F13
0x180003e8c  call    cs:__imp_CharNextW
0x180003e92  cmp     si, [rax]
0x180003e95  jz      short loc_180003E9F
0x180003e97  mov     r15b, bl
0x180003e9a  mov     [rbp+57h+var_B0], bl
0x180003e9d  jmp     short loc_180003ECC
0x180003e9f  mov     rcx, [rdi]; lpsz
0x180003ea2  call    cs:__imp_CharNextW
0x180003ea8  mov     [rdi], rax
0x180003eab  mov     r8d, 1; int
0x180003eb1  mov     rdx, rax; unsigned __int16 *
0x180003eb4  lea     rcx, [rbp+57h+pv]; this
0x180003eb8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003ebd  test    eax, eax
0x180003ebf  jz      loc_180003DC2
0x180003ec5  jmp     short loc_180003F13
0x180003ec7  test    r15b, r15b
0x180003eca  jnz     short loc_180003F13
0x180003ecc  mov     rax, [rdi]
0x180003ecf  cmp     word ptr [rax], 7Bh ; '{'
0x180003ed3  jnz     short loc_180003EDA
0x180003ed5  inc     r13d
0x180003ed8  jmp     short loc_180003F13
0x180003eda  cmp     word ptr [rax], 7Dh ; '}'
0x180003ede  jnz     short loc_180003F13
0x180003ee0  sub     r13d, 1
0x180003ee4  jnz     short loc_180003F13
0x180003ee6  cmp     r12b, 1
0x180003eea  jnz     short loc_180003F13
0x180003eec  mov     [rbp+57h+var_90], rbx
0x180003ef0  lea     r8d, [r13+9]; int
0x180003ef4  lea     rdx, asc_180034D80; "\r\n\t}\r\n}\r\n"
0x180003efb  lea     rcx, [rbp+57h+pv]; this
0x180003eff  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003f04  nop
0x180003f05  test    eax, eax
0x180003f07  jz      loc_180003DC2
0x180003f0d  mov     r12b, bl
0x180003f10  mov     [rbp+57h+var_AF], bl
0x180003f13  mov     rdx, [rdi]
0x180003f16  cmp     word ptr [rdx], 25h ; '%'
0x180003f1a  jnz     short loc_180003F34
0x180003f1c  mov     rcx, rdx; lpsz
0x180003f1f  call    cs:__imp_CharNextW
0x180003f25  mov     [rdi], rax
0x180003f28  movzx   ecx, word ptr [rax]
0x180003f2b  cmp     cx, 25h ; '%'
0x180003f2f  jnz     short loc_180003F50
0x180003f31  mov     rdx, rax; unsigned __int16 *
0x180003f34  mov     r8d, 1; int
0x180003f3a  lea     rcx, [rbp+57h+pv]; this
0x180003f3e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003f43  test    eax, eax
0x180003f45  jz      loc_180003DC2
0x180003f4b  jmp     loc_18000408D
0x180003f50  mov     r12, rbx
0x180003f53  test    rax, rax
0x180003f56  jnz     short loc_180003F74
0x180003f58  mov     ebx, 80020009h
0x180003f5d  jmp     loc_1800040BF
0x180003f62  cmp     cx, 25h ; '%'
0x180003f66  jz      short loc_180003F7B
0x180003f68  mov     rcx, rax; lpsz
0x180003f6b  call    cs:__imp_CharNextW
0x180003f71  movzx   ecx, word ptr [rax]
0x180003f74  test    cx, cx
0x180003f77  jnz     short loc_180003F62
0x180003f79  jmp     short loc_180003F7E
0x180003f7b  mov     r12, rax
0x180003f7e  test    r12, r12
0x180003f81  jz      short loc_180003F58
0x180003f83  mov     rax, r12
0x180003f86  sub     rax, [rdi]
0x180003f89  and     rax, 0FFFFFFFFFFFFFFFEh
0x180003f8d  cmp     rax, 3Eh ; '>'
0x180003f91  jg      loc_1800040A9
0x180003f97  lfence
0x180003f9a  mov     rax, r12
0x180003f9d  sub     rax, [rdi]
0x180003fa0  sar     rax, 1
0x180003fa3  movsxd  r9, eax; MaxCount
0x180003fa6  mov     r8, [rdi]; Source
0x180003fa9  mov     edx, 20h ; ' '; SizeInWords
0x180003fae  lea     rcx, [rbp+57h+Destination]; Destination
0x180003fb2  call    wcsncpy_s
0x180003fb7  test    eax, eax
0x180003fb9  jz      short loc_180003FDF
0x180003fbb  cmp     eax, 0Ch
0x180003fbe  jz      loc_18000411A
0x180003fc4  cmp     eax, 16h
0x180003fc7  jz      loc_18000410F
0x180003fcd  cmp     eax, 22h ; '"'
0x180003fd0  jz      loc_18000410F
0x180003fd6  cmp     eax, 50h ; 'P'
0x180003fd9  jnz     loc_180004104
0x180003fdf  mov     r14, [rdi+8]
0x180003fe3  mov     r15d, ebx
0x180003fe6  mov     rsi, rbx
0x180003fe9  cmp     [r14+18h], ebx
0x180003fed  jle     loc_180003F58
0x180003ff3  mov     rax, [r14+8]
0x180003ff7  lea     rdx, [rbp+57h+Destination]; lpString2
0x180003ffb  mov     rcx, [rax+rsi*8]; lpString1
0x180003fff  call    cs:__imp_lstrcmpiW
0x180004005  test    eax, eax
0x180004007  jz      short loc_18000401A
0x180004009  inc     r15d
0x18000400c  inc     rsi
0x18000400f  cmp     r15d, [r14+18h]
0x180004013  jl      short loc_180003FF3
0x180004015  jmp     loc_180003F58
0x18000401a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000401e  jz      loc_180003F58
0x180004024  test    rsi, rsi
0x180004027  js      loc_1800040F9
0x18000402d  cmp     r15d, [r14+18h]
0x180004031  jge     loc_1800040F9
0x180004037  lfence
0x18000403a  mov     rax, [r14+10h]
0x18000403e  mov     rdx, [rax+rsi*8]; unsigned __int16 *
0x180004042  test    rdx, rdx
0x180004045  jz      loc_180003F58
0x18000404b  mov     [rbp+57h+var_90], rbx
0x18000404f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004053  inc     r8; int
0x180004056  cmp     [rdx+r8*2], bx
0x18000405b  jnz     short loc_180004053
0x18000405d  lea     rcx, [rbp+57h+pv]; this
0x180004061  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004066  nop
0x180004067  test    eax, eax
0x180004069  jz      loc_180003DC2
0x18000406f  mov     rax, [rdi]
0x180004072  jmp     short loc_180004080
0x180004074  mov     rcx, rax; lpsz
0x180004077  call    cs:__imp_CharNextW
0x18000407d  mov     [rdi], rax
0x180004080  cmp     rax, r12
0x180004083  jnz     short loc_180004074
0x180004085  mov     r12b, [rbp+57h+var_AF]
0x180004089  mov     r15b, [rbp+57h+var_B0]
0x18000408d  mov     rcx, [rdi]; lpsz
0x180004090  call    cs:__imp_CharNextW
0x180004096  mov     rsi, rax
0x180004099  mov     [rdi], rax
0x18000409c  cmp     [rax], bx
0x18000409f  jz      short loc_1800040B0
0x1800040a1  mov     al, [rbp+57h+var_AE]
0x1800040a4  jmp     loc_180003DF0
0x1800040a9  mov     ebx, 80004005h
0x1800040ae  jmp     short loc_1800040BF
0x1800040b0  mov     rcx, [rbp+57h+pv+8]
0x1800040b4  mov     [rbp+57h+pv+8], rbx
0x1800040b8  mov     rax, [rbp+57h+var_A8]
0x1800040bc  mov     [rax], rcx
0x1800040bf  mov     rcx, [rbp+57h+pv+8]; pv
0x1800040c3  call    cs:__imp_CoTaskMemFree
0x1800040c9  mov     eax, ebx
0x1800040cb  jmp     short loc_1800040D2
0x1800040cd  mov     eax, 80004003h
0x1800040d2  mov     rcx, [rbp+57h+var_40]
0x1800040d6  xor     rcx, rsp; StackCookie
0x1800040d9  call    __security_check_cookie
0x1800040de  mov     rbx, [rsp+0D0h+arg_8]
0x1800040e6  add     rsp, 0A0h
0x1800040ed  pop     r15
0x1800040ef  pop     r14
0x1800040f1  pop     r13
0x1800040f3  pop     r12
0x1800040f5  pop     rdi
0x1800040f6  pop     rsi
0x1800040f7  pop     rbp
0x1800040f8  retn
0x1800040f9  mov     ecx, 8000000Bh; int
0x1800040fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004104  mov     ecx, 80004005h; int
0x180004109  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000410f  mov     ecx, 80070057h; int
0x180004114  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000411a  mov     ecx, 8007000Eh; int
0x18000411f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
