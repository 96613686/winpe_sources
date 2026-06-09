# FilterAgent::GetCharArea(ushort const *,unsigned __int64)

- ea: `0x18000ef78`
- end: `0x18000f1d1`
- name: `?GetCharArea@FilterAgent@@AEBAKPEBG_K@Z`
- size: `601`
- prototype: `__int64 __fastcall(FilterAgent *this, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000dd08`

## callees

- `0x18000ef78`
- `0x18000f64c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f019`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f019`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterAgent::GetCharArea(FilterAgent *this, const unsigned __int16 *a2, __int64 a3)
{
  int v6; // edi
  LPSTR v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // r11d
  __int64 v10; // rdx
  __int64 v11; // r10
  __int16 v12; // r8
  __int16 v13; // r9
  int v14; // ecx
  __int64 v15; // rdx
  unsigned __int64 v16; // rsi
  int v17; // r8d
  int v18; // r9d
  int v19; // r8d
  int cbMultiByte; // [rsp+28h] [rbp-50h]
  LPSTR lpMultiByteStr[7]; // [rsp+40h] [rbp-38h] BYREF
  UINT CodePage; // [rsp+80h] [rbp+8h] BYREF
  WINBOOL UsedDefaultChar; // [rsp+90h] [rbp+18h] BYREF

  v6 = 4 * a3;
  memset(lpMultiByteStr, 0, 24);
  std::vector<unsigned char>::resize(lpMultiByteStr, (unsigned int)(4 * a3));
  UsedDefaultChar = 1;
  CodePage = 0;
  (*(void (__fastcall **)(_QWORD, UINT *))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2), &CodePage);
  cbMultiByte = v6;
  v7 = lpMultiByteStr[0];
  v8 = 1024;
  v9 = WideCharToMultiByte(CodePage, 0x400u, a2, a3, lpMultiByteStr[0], cbMultiByte, 0, &UsedDefaultChar);
  if ( !v9 || UsedDefaultChar )
  {
    if ( a3 )
    {
      v15 = 0;
      v16 = a3 - 1;
      if ( v16 )
      {
        while ( 1 )
        {
          v17 = a2[v15];
          if ( (unsigned __int16)(v17 + 10240) <= 0x3FFu )
          {
            v18 = a2[(unsigned int)(v15 + 1)];
            if ( (unsigned __int16)(v18 + 9216) <= 0x3FFu )
            {
              v8 |= 0x800u;
              v19 = v18 + (v17 << 10);
              if ( (unsigned int)(v19 - 56620043) <= 3
                || (unsigned int)(v19 - 56678912) <= 0xF
                || (unsigned int)(v19 - 57531648) <= 0xEF
                || (unsigned int)(v19 - 56741883) <= 4 )
              {
                break;
              }
            }
          }
          v15 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v15 >= v16 )
            goto LABEL_35;
        }
        v8 |= 0x1000u;
      }
    }
  }
  else
  {
    v8 = 0;
    v10 = 0;
    do
    {
      v11 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v11 >= v9
        || (v12 = (unsigned __int8)v7[v10], (unsigned __int8)(v12 + 127) > 0x1Eu) && (unsigned __int8)(v12 + 32) > 0x1Cu )
      {
        v14 = 1;
        if ( (unsigned __int8)(v7[v10] + 95) <= 0x3Eu )
          v14 = 16;
      }
      else
      {
        v13 = (v12 << 8) + (unsigned __int8)v7[v11];
        if ( (unsigned __int16)(v13 + 30913) > 0x60u )
        {
          if ( (unsigned __int16)(v13 + 4800) > 0x1BCu )
          {
            if ( (unsigned __int16)(v13 + 1472) > 0x20Bu )
            {
              if ( (unsigned __int16)(v13 + 4032) > 0x9BCu )
              {
                if ( (unsigned __int8)(v12 + 127) <= 3u
                  || (unsigned __int8)(v12 + 120) <= 0x17u
                  || (v14 = 512, (unsigned __int8)(v12 + 32) <= 0xAu) )
                {
                  v14 = 1;
                }
              }
              else
              {
                v14 = 256;
              }
            }
            else
            {
              v14 = 8;
            }
          }
          else
          {
            v14 = 4;
          }
        }
        else
        {
          v14 = 2;
        }
        LODWORD(v10) = v10 + 1;
      }
      v8 |= v14;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < v9 );
  }
LABEL_35:
  if ( v7 )
    operator delete(v7);
  return v8;
}

```

## disassembly

```asm
0x18000ef78  mov     rax, rsp
0x18000ef7b  mov     [rax+10h], rbx
0x18000ef7f  push    rsi
0x18000ef80  push    rdi
0x18000ef81  push    r14
0x18000ef83  sub     rsp, 60h
0x18000ef87  mov     rsi, r8
0x18000ef8a  mov     r14, rdx
0x18000ef8d  mov     rbx, rcx
0x18000ef90  lea     edi, ds:0[r8*4]
0x18000ef98  xorps   xmm0, xmm0
0x18000ef9b  movdqu  xmmword ptr [rax-38h], xmm0
0x18000efa0  mov     qword ptr [rax-28h], 0
0x18000efa8  mov     edx, edi
0x18000efaa  lea     rcx, [rax-38h]
0x18000efae  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000efb3  mov     [rsp+78h+UsedDefaultChar], 1
0x18000efbe  mov     [rsp+78h+CodePage], 0
0x18000efc9  mov     rcx, [rbx+10h]
0x18000efcd  mov     rax, [rcx]
0x18000efd0  lea     rdx, [rsp+78h+CodePage]
0x18000efd8  mov     rax, [rax+40h]
0x18000efdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efe1  lea     rax, [rsp+78h+UsedDefaultChar]
0x18000efe9  mov     [rsp+78h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000efee  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18000eff7  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18000effb  mov     rdi, [rsp+78h+var_38]
0x18000f000  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000f005  mov     r9d, esi; cchWideChar
0x18000f008  mov     r8, r14; lpWideCharStr
0x18000f00b  mov     ebx, 400h
0x18000f010  mov     edx, ebx; dwFlags
0x18000f012  mov     ecx, [rsp+78h+CodePage]; CodePage
0x18000f019  call    cs:__imp_WideCharToMultiByte
0x18000f01f  mov     r11d, eax
0x18000f022  test    eax, eax
0x18000f024  jz      loc_18000F124
0x18000f02a  cmp     [rsp+78h+UsedDefaultChar], 0
0x18000f032  jnz     loc_18000F124
0x18000f038  xor     ebx, ebx
0x18000f03a  xor     edx, edx
0x18000f03c  mov     esi, 100h
0x18000f041  lea     r10d, [rdx+1]
0x18000f045  cmp     r10d, r11d
0x18000f048  jnb     loc_18000F0FE
0x18000f04e  movzx   r8d, byte ptr [rdx+rdi]
0x18000f053  lea     eax, [r8+7Fh]
0x18000f057  cmp     al, 1Eh
0x18000f059  jbe     short loc_18000F067
0x18000f05b  lea     eax, [r8+20h]
0x18000f05f  cmp     al, 1Ch
0x18000f061  ja      loc_18000F0FE
0x18000f067  movzx   r9d, byte ptr [r10+rdi]
0x18000f06c  mov     edx, r8d
0x18000f06f  imul    edx, esi
0x18000f072  add     r9w, dx
0x18000f076  mov     eax, 78C1h
0x18000f07b  add     eax, r9d
0x18000f07e  cmp     ax, 60h ; '`'
0x18000f082  ja      short loc_18000F08B
0x18000f084  mov     ecx, 2
0x18000f089  jmp     short loc_18000F0F9
0x18000f08b  mov     eax, 12C0h
0x18000f090  add     eax, r9d
0x18000f093  mov     ecx, 1BCh
0x18000f098  cmp     ax, cx
0x18000f09b  ja      short loc_18000F0A4
0x18000f09d  mov     ecx, 4
0x18000f0a2  jmp     short loc_18000F0F9
0x18000f0a4  mov     eax, 5C0h
0x18000f0a9  add     eax, r9d
0x18000f0ac  mov     ecx, 20Bh
0x18000f0b1  cmp     ax, cx
0x18000f0b4  ja      short loc_18000F0BD
0x18000f0b6  mov     ecx, 8
0x18000f0bb  jmp     short loc_18000F0F9
0x18000f0bd  mov     eax, 0FC0h
0x18000f0c2  add     r9w, ax
0x18000f0c6  mov     eax, 9BCh
0x18000f0cb  cmp     r9w, ax
0x18000f0cf  ja      short loc_18000F0D5
0x18000f0d1  mov     ecx, esi
0x18000f0d3  jmp     short loc_18000F0F9
0x18000f0d5  lea     eax, [r8+7Fh]
0x18000f0d9  cmp     al, 3
0x18000f0db  jbe     short loc_18000F0F4
0x18000f0dd  lea     eax, [r8+78h]
0x18000f0e1  cmp     al, 17h
0x18000f0e3  jbe     short loc_18000F0F4
0x18000f0e5  add     r8b, 20h ; ' '
0x18000f0e9  cmp     r8b, 0Ah
0x18000f0ed  mov     ecx, 200h
0x18000f0f2  ja      short loc_18000F0F9
0x18000f0f4  mov     ecx, 1
0x18000f0f9  mov     edx, r10d
0x18000f0fc  jmp     short loc_18000F112
0x18000f0fe  mov     al, [rdx+rdi]
0x18000f101  add     al, 5Fh ; '_'
0x18000f103  mov     ecx, 1
0x18000f108  lea     r8d, [rcx+0Fh]
0x18000f10c  cmp     al, 3Eh ; '>'
0x18000f10e  cmovbe  ecx, r8d
0x18000f112  or      ebx, ecx
0x18000f114  inc     edx
0x18000f116  cmp     edx, r11d
0x18000f119  jb      loc_18000F041
0x18000f11f  jmp     loc_18000F1B0
0x18000f124  test    rsi, rsi
0x18000f127  jz      loc_18000F1B0
0x18000f12d  xor     edx, edx
0x18000f12f  sub     rsi, 1
0x18000f133  jz      short loc_18000F1B0
0x18000f135  mov     r10d, 3FFh
0x18000f13b  movzx   r8d, word ptr [r14+rdx*2]
0x18000f140  mov     eax, 2800h
0x18000f145  add     eax, r8d
0x18000f148  cmp     ax, r10w
0x18000f14c  ja      short loc_18000F1A1
0x18000f14e  lea     eax, [rdx+1]
0x18000f151  movzx   r9d, word ptr [r14+rax*2]
0x18000f156  mov     eax, 2400h
0x18000f15b  add     eax, r9d
0x18000f15e  cmp     ax, r10w
0x18000f162  ja      short loc_18000F1A1
0x18000f164  bts     ebx, 0Bh
0x18000f168  shl     r8d, 0Ah
0x18000f16c  add     r8d, r9d
0x18000f16f  lea     eax, [r8-35FF40Bh]
0x18000f176  cmp     eax, 3
0x18000f179  jbe     short loc_18000F1AC
0x18000f17b  lea     eax, [r8-360DA00h]
0x18000f182  cmp     eax, 0Fh
0x18000f185  jbe     short loc_18000F1AC
0x18000f187  lea     eax, [r8-36DDD00h]
0x18000f18e  cmp     eax, 0EFh
0x18000f193  jbe     short loc_18000F1AC
0x18000f195  lea     eax, [r8-361CFFBh]
0x18000f19c  cmp     eax, 4
0x18000f19f  jbe     short loc_18000F1AC
0x18000f1a1  inc     edx
0x18000f1a3  mov     eax, edx
0x18000f1a5  cmp     rax, rsi
0x18000f1a8  jb      short loc_18000F13B
0x18000f1aa  jmp     short loc_18000F1B0
0x18000f1ac  bts     ebx, 0Ch
0x18000f1b0  test    rdi, rdi
0x18000f1b3  jz      short loc_18000F1BE
0x18000f1b5  mov     rcx, rdi
0x18000f1b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f1be  mov     eax, ebx
0x18000f1c0  mov     rbx, [rsp+78h+arg_8]
0x18000f1c8  add     rsp, 60h
0x18000f1cc  pop     r14
0x18000f1ce  pop     rdi
0x18000f1cf  pop     rsi
0x18000f1d0  retn
```
