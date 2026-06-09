# xgc::GDIFont::ReplaceAll(xgc::ByteReader const &,xgc::ByteWriter &,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180020c14`
- end: `0x180020f9c`
- name: `?ReplaceAll@GDIFont@xgc@@AEAAXAEBUByteReader@2@AEAUByteWriter@2@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001f444`

## callees

- `0x180008830`
- `0x18000e5ec`
- `0x18001be7c`
- `0x18001cb1c`
- `0x18001cbe8`
- `0x18001ccc4`
- `0x18001cd84`
- `0x18001cf2c`
- `0x180020c14`
- `0x180022908`
- `0x18002319c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xgc::GDIFont::ReplaceAll(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  int v6; // esi
  __int16 v9; // r13
  int v10; // r9d
  int v11; // ecx
  int v12; // r14d
  int v13; // ebx
  unsigned int v14; // esi
  _BYTE *v15; // rbx
  unsigned __int64 v16; // rax
  int v17; // edx
  int v18; // edx
  __int64 v19; // rbx
  __int64 v20; // rbx
  int v22; // [rsp+20h] [rbp-79h]
  _WORD v23[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 v24; // [rsp+34h] [rbp-65h] BYREF
  _WORD v25[2]; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 v26; // [rsp+3Ch] [rbp-5Dh] BYREF
  unsigned __int16 v27[2]; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int16 v28; // [rsp+44h] [rbp-55h] BYREF
  _WORD v29[2]; // [rsp+48h] [rbp-51h] BYREF
  __int16 v30; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v31; // [rsp+50h] [rbp-49h]
  int v32; // [rsp+54h] [rbp-45h]
  int v33; // [rsp+58h] [rbp-41h]
  __int64 v34; // [rsp+60h] [rbp-39h]
  _BYTE v35[16]; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v36; // [rsp+78h] [rbp-21h]
  _BYTE v37[32]; // [rsp+88h] [rbp-11h] BYREF

  v6 = a4;
  v33 = a4;
  v34 = a5;
  std::wstring::wstring(v35);
  v9 = 0;
  v31 = 0;
  v27[0] = 0;
  xgc::ByteReader::operator()<unsigned short>(a2, v27, (unsigned int)(v10 + 2));
  v29[0] = 0;
  xgc::ByteReader::operator()<unsigned short>(a2, v29, (unsigned int)(v6 + 4));
  LOWORD(v11) = 0;
  v32 = 0;
  if ( v27[0] )
  {
    v12 = v6 + 6;
    do
    {
      v13 = 12 * (unsigned __int16)v11;
      v23[0] = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, v23, (unsigned int)(v13 + v12));
      v24 = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, &v24, (unsigned int)(v13 + v12 + 2));
      v26 = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, &v26, (unsigned int)(v13 + v12 + 4));
      v30 = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, &v30, (unsigned int)(v13 + v12 + 6));
      v25[0] = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, v25, (unsigned int)(v13 + v12 + 8));
      v28 = 0;
      xgc::ByteReader::operator()<unsigned short>(a2, &v28, (unsigned int)(v13 + v12 + 10));
      v14 = v29[0] + v28 + v6;
      if ( v30 == 1 )
      {
        if ( v23[0] == 3 )
        {
          if ( v24 <= 1u )
          {
            v19 = v25[0];
            std::wstring::resize(v35, (unsigned __int64)v25[0] >> 1);
            xgc::readString<wchar_t>(a2, v35, v14);
            v9 = 3;
            v31 = v26;
            if ( 2LL * *(_QWORD *)(a6 + 16) == v19 )
              xgc::writeString<wchar_t>(a3, a6, v14);
          }
        }
        else if ( v23[0] == 1 && !v24 )
        {
          v20 = v25[0];
          std::wstring::resize(v35, (unsigned __int64)v25[0] >> 1);
          xgc::readString<char>(a2, v35, v14);
          v9 = 1;
          v31 = v26;
          if ( *(_QWORD *)(a6 + 16) == v20 )
            xgc::writeString<char>(a3, a6, v14);
        }
        goto LABEL_32;
      }
      if ( v30 == 4 )
      {
        if ( v23[0] == 3 )
        {
          if ( v24 > 1u )
            goto LABEL_32;
          if ( !v36 || v9 != 3 || (v15 = v35, (_WORD)v31 != v26) )
            v15 = (_BYTE *)v34;
          v16 = *((_QWORD *)v15 + 2);
          if ( !v16 || *(_QWORD *)(a6 + 16) > v16 )
            goto LABEL_32;
          std::wstring::wstring(v37);
          std::wstring::resize(v37, (unsigned __int64)v25[0] >> 1);
          xgc::readString<wchar_t>(a2, v37, v14);
          if ( !(unsigned int)std::wstring::compare(
                                (_DWORD)v15,
                                v17,
                                *(_QWORD *)(a6 + 16),
                                (unsigned int)v37,
                                v22,
                                *(_QWORD *)(a6 + 16)) )
            xgc::writeString<wchar_t>(a3, a6, v14);
        }
        else
        {
          if ( v23[0] != 1 || v24 || !v36 || v9 != 1 || *(_QWORD *)(a6 + 16) > v36 )
            goto LABEL_32;
          std::wstring::wstring(v37);
          std::wstring::resize(v37, (unsigned __int64)v25[0] >> 1);
          xgc::readString<char>(a2, v37, v14);
          if ( !(unsigned int)std::wstring::compare(
                                (unsigned int)v35,
                                v18,
                                *(_QWORD *)(a6 + 16),
                                (unsigned int)v37,
                                v22,
                                *(_QWORD *)(a6 + 16)) )
            xgc::writeString<char>(a3, a6, v14);
        }
        std::wstring::~wstring(v37);
      }
LABEL_32:
      HIWORD(v11) = HIWORD(v32);
      LOWORD(v11) = v32 + 1;
      v32 = v11;
      v6 = v33;
    }
    while ( (unsigned __int16)v11 < v27[0] );
  }
  return std::wstring::~wstring(v35);
}

```

## disassembly

```asm
0x180020c14  mov     [rsp-8+arg_0], rbx
0x180020c19  push    rbp
0x180020c1a  push    rsi
0x180020c1b  push    rdi
0x180020c1c  push    r12
0x180020c1e  push    r13
0x180020c20  push    r14
0x180020c22  push    r15
0x180020c24  lea     rbp, [rsp-17h]
0x180020c29  sub     rsp, 0B0h
0x180020c30  mov     rax, cs:__security_cookie
0x180020c37  xor     rax, rsp
0x180020c3a  mov     [rbp+47h+var_38], rax
0x180020c3e  mov     esi, r9d
0x180020c41  mov     [rbp+47h+var_88], r9d
0x180020c45  mov     r12, r8
0x180020c48  mov     r15, rdx
0x180020c4b  mov     rax, [rbp+47h+arg_20]
0x180020c4f  mov     [rbp+47h+var_80], rax
0x180020c53  lea     rcx, [rbp+47h+var_78]
0x180020c57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020c5c  nop
0x180020c5d  xor     ebx, ebx
0x180020c5f  mov     r13d, ebx
0x180020c62  mov     [rbp+47h+var_90], ebx
0x180020c65  mov     [rbp+47h+var_A0], bx
0x180020c69  lea     r8d, [r9+2]
0x180020c6d  lea     rdx, [rbp+47h+var_A0]
0x180020c71  mov     rcx, r15
0x180020c74  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020c79  mov     [rbp+47h+var_98], bx
0x180020c7d  lea     r8d, [rsi+4]
0x180020c81  lea     rdx, [rbp+47h+var_98]
0x180020c85  mov     rcx, r15
0x180020c88  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020c8d  mov     ecx, ebx
0x180020c8f  mov     [rbp+47h+var_8C], ebx
0x180020c92  cmp     bx, [rbp+47h+var_A0]
0x180020c96  jnb     loc_180020F6C
0x180020c9c  lea     r14d, [rsi+6]
0x180020ca0  mov     rdi, [rbp+47h+arg_28]
0x180020ca4  xor     edx, edx
0x180020ca6  movzx   eax, cx
0x180020ca9  lea     ecx, [rax+rax*2]
0x180020cac  lea     ebx, ds:0[rcx*4]
0x180020cb3  mov     [rbp+47h+var_B0], dx
0x180020cb7  lea     r8d, [rbx+r14]
0x180020cbb  lea     rdx, [rbp+47h+var_B0]
0x180020cbf  mov     rcx, r15
0x180020cc2  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020cc7  xor     eax, eax
0x180020cc9  mov     [rbp+47h+var_AC], ax
0x180020ccd  lea     r8d, [r14+2]
0x180020cd1  add     r8d, ebx
0x180020cd4  lea     rdx, [rbp+47h+var_AC]
0x180020cd8  mov     rcx, r15
0x180020cdb  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020ce0  xor     eax, eax
0x180020ce2  mov     [rbp+47h+var_A4], ax
0x180020ce6  lea     r8d, [r14+4]
0x180020cea  add     r8d, ebx
0x180020ced  lea     rdx, [rbp+47h+var_A4]
0x180020cf1  mov     rcx, r15
0x180020cf4  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020cf9  xor     eax, eax
0x180020cfb  mov     [rbp+47h+var_94], ax
0x180020cff  lea     r8d, [r14+6]
0x180020d03  add     r8d, ebx
0x180020d06  lea     rdx, [rbp+47h+var_94]
0x180020d0a  mov     rcx, r15
0x180020d0d  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020d12  xor     eax, eax
0x180020d14  mov     [rbp+47h+var_A8], ax
0x180020d18  lea     r8d, [r14+8]
0x180020d1c  add     r8d, ebx
0x180020d1f  lea     rdx, [rbp+47h+var_A8]
0x180020d23  mov     rcx, r15
0x180020d26  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020d2b  xor     eax, eax
0x180020d2d  mov     [rbp+47h+var_9C], ax
0x180020d31  lea     r8d, [r14+0Ah]
0x180020d35  add     r8d, ebx
0x180020d38  lea     rdx, [rbp+47h+var_9C]
0x180020d3c  mov     rcx, r15
0x180020d3f  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x180020d44  movzx   eax, [rbp+47h+var_9C]
0x180020d48  movzx   ecx, [rbp+47h+var_98]
0x180020d4c  add     esi, eax
0x180020d4e  add     esi, ecx
0x180020d50  movzx   ecx, [rbp+47h+var_94]
0x180020d54  sub     ecx, 1
0x180020d57  mov     eax, 3
0x180020d5c  jz      loc_180020EA2
0x180020d62  cmp     ecx, eax
0x180020d64  jnz     loc_180020F54
0x180020d6a  lea     ecx, [rax-2]
0x180020d6d  xor     edx, edx
0x180020d6f  cmp     [rbp+47h+var_B0], ax
0x180020d73  jnz     loc_180020E16
0x180020d79  cmp     [rbp+47h+var_AC], cx
0x180020d7d  ja      loc_180020F56
0x180020d83  cmp     [rbp+47h+var_68], rdx
0x180020d87  jz      short loc_180020D9C
0x180020d89  cmp     r13w, ax
0x180020d8d  jnz     short loc_180020D9C
0x180020d8f  mov     eax, [rbp+47h+var_90]
0x180020d92  cmp     ax, [rbp+47h+var_A4]
0x180020d96  lea     rbx, [rbp+47h+var_78]
0x180020d9a  jz      short loc_180020DA0
0x180020d9c  mov     rbx, [rbp+47h+var_80]
0x180020da0  mov     rax, [rbx+10h]
0x180020da4  test    rax, rax
0x180020da7  jz      loc_180020F56
0x180020dad  cmp     [rdi+10h], rax
0x180020db1  ja      loc_180020F56
0x180020db7  lea     rcx, [rbp+47h+var_58]
0x180020dbb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020dc0  nop
0x180020dc1  movzx   edx, [rbp+47h+var_A8]
0x180020dc5  shr     rdx, 1
0x180020dc8  lea     rcx, [rbp+47h+var_58]
0x180020dcc  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180020dd1  mov     r8d, esi
0x180020dd4  lea     rdx, [rbp+47h+var_58]
0x180020dd8  mov     rcx, r15
0x180020ddb  call    ??$readString@_W@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<wchar_t>(xgc::ByteReader const &,std::wstring &,uint)
0x180020de0  mov     r8, [rdi+10h]
0x180020de4  mov     [rsp+0E0h+var_B8], r8
0x180020de9  lea     r9, [rbp+47h+var_58]
0x180020ded  mov     rcx, rbx
0x180020df0  call    ?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAH_K0AEBV12@00@Z; std::wstring::compare(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180020df5  test    eax, eax
0x180020df7  jnz     short loc_180020E08
0x180020df9  mov     r8d, esi
0x180020dfc  mov     rdx, rdi
0x180020dff  mov     rcx, r12
0x180020e02  call    ??$writeString@_W@xgc@@YAXAEBUByteWriter@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::writeString<wchar_t>(xgc::ByteWriter const &,std::wstring const &,uint)
0x180020e07  nop
0x180020e08  lea     rcx, [rbp+47h+var_58]
0x180020e0c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020e11  jmp     loc_180020F54
0x180020e16  cmp     [rbp+47h+var_B0], cx
0x180020e1a  jnz     loc_180020F56
0x180020e20  cmp     [rbp+47h+var_AC], dx
0x180020e24  jnz     loc_180020F56
0x180020e2a  mov     rax, [rbp+47h+var_68]
0x180020e2e  test    rax, rax
0x180020e31  jz      loc_180020F56
0x180020e37  cmp     r13w, cx
0x180020e3b  jnz     loc_180020F56
0x180020e41  cmp     [rdi+10h], rax
0x180020e45  ja      loc_180020F56
0x180020e4b  lea     rcx, [rbp+47h+var_58]
0x180020e4f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020e54  nop
0x180020e55  movzx   edx, [rbp+47h+var_A8]
0x180020e59  shr     rdx, 1
0x180020e5c  lea     rcx, [rbp+47h+var_58]
0x180020e60  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180020e65  mov     r8d, esi
0x180020e68  lea     rdx, [rbp+47h+var_58]
0x180020e6c  mov     rcx, r15
0x180020e6f  call    ??$readString@D@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<char>(xgc::ByteReader const &,std::wstring &,uint)
0x180020e74  mov     r8, [rdi+10h]
0x180020e78  mov     [rsp+0E0h+var_B8], r8
0x180020e7d  lea     r9, [rbp+47h+var_58]
0x180020e81  lea     rcx, [rbp+47h+var_78]
0x180020e85  call    ?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAH_K0AEBV12@00@Z; std::wstring::compare(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180020e8a  test    eax, eax
0x180020e8c  jnz     short loc_180020E9D
0x180020e8e  mov     r8d, esi
0x180020e91  mov     rdx, rdi
0x180020e94  mov     rcx, r12
0x180020e97  call    ??$writeString@D@xgc@@YAXAEBUByteWriter@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::writeString<char>(xgc::ByteWriter const &,std::wstring const &,uint)
0x180020e9c  nop
0x180020e9d  jmp     loc_180020E08
0x180020ea2  mov     ecx, 1
0x180020ea7  cmp     [rbp+47h+var_B0], ax
0x180020eab  jnz     short loc_180020F01
0x180020ead  cmp     [rbp+47h+var_AC], cx
0x180020eb1  ja      loc_180020F54
0x180020eb7  movzx   ebx, [rbp+47h+var_A8]
0x180020ebb  mov     edx, ebx
0x180020ebd  shr     rdx, 1
0x180020ec0  lea     rcx, [rbp+47h+var_78]
0x180020ec4  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180020ec9  mov     r8d, esi
0x180020ecc  lea     rdx, [rbp+47h+var_78]
0x180020ed0  mov     rcx, r15
0x180020ed3  call    ??$readString@_W@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<wchar_t>(xgc::ByteReader const &,std::wstring &,uint)
0x180020ed8  mov     r13d, 3
0x180020ede  movzx   edx, [rbp+47h+var_A4]
0x180020ee2  mov     [rbp+47h+var_90], edx
0x180020ee5  mov     rax, [rdi+10h]
0x180020ee9  add     rax, rax
0x180020eec  cmp     rax, rbx
0x180020eef  jnz     short loc_180020F54
0x180020ef1  mov     r8d, esi
0x180020ef4  mov     rdx, rdi
0x180020ef7  mov     rcx, r12
0x180020efa  call    ??$writeString@_W@xgc@@YAXAEBUByteWriter@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::writeString<wchar_t>(xgc::ByteWriter const &,std::wstring const &,uint)
0x180020eff  jmp     short loc_180020F54
0x180020f01  cmp     [rbp+47h+var_B0], cx
0x180020f05  jnz     short loc_180020F54
0x180020f07  xor     edx, edx
0x180020f09  cmp     [rbp+47h+var_AC], dx
0x180020f0d  jnz     short loc_180020F56
0x180020f0f  movzx   ebx, [rbp+47h+var_A8]
0x180020f13  mov     edx, ebx
0x180020f15  shr     rdx, 1
0x180020f18  lea     rcx, [rbp+47h+var_78]
0x180020f1c  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180020f21  mov     r8d, esi
0x180020f24  lea     rdx, [rbp+47h+var_78]
0x180020f28  mov     rcx, r15
0x180020f2b  call    ??$readString@D@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<char>(xgc::ByteReader const &,std::wstring &,uint)
0x180020f30  mov     eax, 1
0x180020f35  movzx   r13d, ax
0x180020f39  movzx   eax, [rbp+47h+var_A4]
0x180020f3d  mov     [rbp+47h+var_90], eax
0x180020f40  cmp     [rdi+10h], rbx
0x180020f44  jnz     short loc_180020F54
0x180020f46  mov     r8d, esi
0x180020f49  mov     rdx, rdi
0x180020f4c  mov     rcx, r12
0x180020f4f  call    ??$writeString@D@xgc@@YAXAEBUByteWriter@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::writeString<char>(xgc::ByteWriter const &,std::wstring const &,uint)
0x180020f54  xor     edx, edx
0x180020f56  mov     ecx, [rbp+47h+var_8C]
0x180020f59  inc     cx
0x180020f5c  mov     [rbp+47h+var_8C], ecx
0x180020f5f  cmp     cx, [rbp+47h+var_A0]
0x180020f63  mov     esi, [rbp+47h+var_88]
0x180020f66  jb      loc_180020CA6
0x180020f6c  lea     rcx, [rbp+47h+var_78]
0x180020f70  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020f75  mov     rcx, [rbp+47h+var_38]
0x180020f79  xor     rcx, rsp; StackCookie
0x180020f7c  call    __security_check_cookie
0x180020f81  mov     rbx, [rsp+0E0h+arg_0]
0x180020f89  add     rsp, 0B0h
0x180020f90  pop     r15
0x180020f92  pop     r14
0x180020f94  pop     r13
0x180020f96  pop     r12
0x180020f98  pop     rdi
0x180020f99  pop     rsi
0x180020f9a  pop     rbp
0x180020f9b  retn
```
