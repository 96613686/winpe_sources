# GenericTypeLibOLE::Write(STREAM *)

- ea: `0x180056004`
- end: `0x1800564ce`
- name: `?Write@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(GenericTypeLibOLE *__hidden this, struct STREAM *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180054ee0`

## callees

- `0x18004d900`
- `0x180053770`
- `0x180056004`
- `0x1800565b0`
- `0x18005b030`
- `0x18005bfa0`
- `0x18005ce68`
- `0x18005e128`
- `0x180064fb4`
- `0x180064fe0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180056254`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180056254`

## pseudocode

```c
int __fastcall GenericTypeLibOLE::Write(GenericTypeLibOLE *this, struct STREAM *a2)
{
  int result; // eax
  unsigned int i; // r15d
  __int64 v6; // r14
  __int64 v7; // rsi
  const WCHAR *v8; // rax
  _WORD v9[2]; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v11; // [rsp+48h] [rbp-28h] BYREF
  CHAR MultiByteStr[16]; // [rsp+50h] [rbp-20h] BYREF

  ++*((_DWORD *)this + 26);
  v9[0] = 0;
  v10 = 0;
  v11 = 0;
  result = STREAM::WriteUShort(a2, 0x51CCu);
  if ( result >= 0 )
  {
    result = STREAM::WriteUShort(a2, *((_WORD *)this + 136));
    if ( result >= 0 )
    {
      result = STREAM::WriteUShort(a2, *((_WORD *)this + 118));
      if ( result >= 0 )
      {
        result = GenericTypeLibOLE::WriteString(this, a2, *((_DWORD *)this + 61));
        if ( result >= 0 )
        {
          result = GenericTypeLibOLE::WriteString(this, a2, *((_DWORD *)this + 62));
          if ( result >= 0 )
          {
            result = GenericTypeLibOLE::WriteString(this, a2, *((_DWORD *)this + 64));
            if ( result >= 0 )
            {
              result = STREAM::WriteULong(a2, *((_DWORD *)this + 63));
              if ( result >= 0 )
              {
                result = STREAM::WriteUShort(a2, *((_WORD *)this + 130));
                if ( result >= 0 )
                {
                  result = STREAM::WriteULong(a2, *((_DWORD *)this + 66));
                  if ( result >= 0 )
                  {
                    result = STREAM::WriteUShort(a2, *((_WORD *)this + 134));
                    if ( result < 0 )
                      return result;
                    result = STREAM::WriteUShort(a2, *((_WORD *)this + 137));
                    if ( result >= 0 )
                    {
                      result = STREAM::WriteUShort(a2, *((_WORD *)this + 138));
                      if ( result >= 0 )
                      {
                        result = STREAM::WriteUShort(a2, *((_WORD *)this + 139));
                        if ( result >= 0 )
                        {
                          result = (*(__int64 (__fastcall **)(struct STREAM *, char *, __int64))(*(_QWORD *)a2 + 16LL))(
                                     a2,
                                     (char *)this + 280,
                                     16);
                          if ( result >= 0 )
                          {
                            result = (*(__int64 (__fastcall **)(struct STREAM *, char *, __int64))(*(_QWORD *)a2 + 16LL))(
                                       a2,
                                       (char *)this + 172,
                                       64);
                            if ( result >= 0 )
                            {
                              result = STREAM::WriteUShort(a2, *((_WORD *)this + 120));
                              if ( result >= 0 )
                              {
                                for ( i = 0; i < *((unsigned __int16 *)this + 120); ++i )
                                {
                                  v6 = *((_QWORD *)this + 4);
                                  v7 = 80LL * (unsigned __int16)i;
                                  result = GenericTypeLibOLE::WriteString(this, a2, *(_DWORD *)(v7 + v6 + 24));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = STREAM::WriteUShort(a2, 0xAu);
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  v8 = GenericTypeLibOLE::QszOfHsz(this, *(_DWORD *)(v7 + v6 + 28));
                                  WideCharToMultiByte(0, 0, v8, 10, MultiByteStr, 10, 0, 0);
                                  result = (*(__int64 (__fastcall **)(struct STREAM *, CHAR *, __int64))(*(_QWORD *)a2 + 16LL))(
                                             a2,
                                             MultiByteStr,
                                             10);
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = GenericTypeLibOLE::WriteString(this, a2, *(_DWORD *)(v7 + v6 + 36));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = STREAM::WriteUShort(a2, *(_WORD *)(v7 + v6 + 32));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = STREAM::WriteUShort(a2, *(_WORD *)(v7 + v6 + 40));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  if ( *(_WORD *)(v7 + v6 + 40) )
                                    (*(void (__fastcall **)(struct STREAM *, _QWORD, _QWORD))(*(_QWORD *)a2 + 16LL))(
                                      a2,
                                      *((_QWORD *)this + 9) + *(unsigned int *)(v7 + v6 + 44),
                                      *(unsigned __int16 *)(v7 + v6 + 40));
                                  result = GenericTypeLibOLE::WriteString(this, a2, *(_DWORD *)(v7 + v6 + 52));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = STREAM::WriteULong(a2, *(_DWORD *)(v7 + v6 + 48));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  result = STREAM::WriteUShort(a2, *(_WORD *)(v7 + v6));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                  (*(void (__fastcall **)(struct STREAM *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
                                    a2,
                                    v7 + v6 + 56,
                                    16);
                                  result = STREAM::WriteUShort(a2, *(_WORD *)(v7 + v6 + 72));
                                  if ( result < 0 )
                                    goto LABEL_47;
                                }
                                result = (*(__int64 (__fastcall **)(struct STREAM *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
                                           a2,
                                           &v11);
                                if ( result >= 0 )
                                {
                                  result = STREAM::WriteULong(a2, v10);
                                  if ( result >= 0 )
                                  {
                                    result = DOCSTR_MGR::Write((GenericTypeLibOLE *)((char *)this + 1720), a2);
                                    if ( result >= 0 )
                                    {
                                      result = (*(__int64 (__fastcall **)(struct STREAM *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
                                                 a2,
                                                 &v10);
                                      if ( result >= 0 )
                                      {
                                        result = (*(__int64 (__fastcall **)(struct STREAM *, _QWORD))(*(_QWORD *)a2 + 32LL))(
                                                   a2,
                                                   v11);
                                        if ( result >= 0 )
                                        {
                                          result = STREAM::WriteULong(a2, v10);
                                          if ( result >= 0 )
                                          {
                                            result = (*(__int64 (__fastcall **)(struct STREAM *, _QWORD))(*(_QWORD *)a2 + 32LL))(
                                                       a2,
                                                       v10);
                                            if ( result >= 0 )
                                            {
                                              result = BLK_MGR::Write((GenericTypeLibOLE *)((char *)this + 536), a2);
                                              if ( result >= 0 )
                                              {
                                                result = STREAM::WriteUShort(a2, *((_WORD *)this + 308));
                                                if ( result >= 0 )
                                                {
                                                  result = BLK_MGR::Write(*((BLK_MGR **)this + 76), a2);
                                                  if ( result >= 0 )
                                                  {
                                                    result = GENPROJ_TYPEBIND::Write(
                                                               (GenericTypeLibOLE *)((char *)this + 312),
                                                               a2);
                                                    if ( result >= 0 )
                                                    {
                                                      v9[0] = *((_QWORD *)this + 208) != 0;
                                                      result = (*(__int64 (__fastcall **)(struct STREAM *, _WORD *, __int64))(*(_QWORD *)a2 + 16LL))(
                                                                 a2,
                                                                 v9,
                                                                 2);
                                                      if ( result >= 0 )
                                                      {
                                                        if ( !v9[0]
                                                          || (result = BLK_DESC::Write(
                                                                         (GenericTypeLibOLE *)((char *)this + 1664),
                                                                         a2),
                                                              result >= 0) )
                                                        {
                                                          *((_DWORD *)this + 414) = -1;
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_47:
  --*((_DWORD *)this + 26);
  return result;
}

```

## disassembly

```asm
0x180056004  mov     [rsp-28h+arg_10], rbx
0x180056009  mov     [rsp-28h+arg_18], rsi
0x18005600e  push    rbp
0x18005600f  push    rdi
0x180056010  push    r12
0x180056012  push    r14
0x180056014  push    r15
0x180056016  mov     rbp, rsp
0x180056019  sub     rsp, 70h
0x18005601d  mov     rax, cs:__security_cookie
0x180056024  xor     rax, rsp
0x180056027  mov     [rbp+var_10], rax
0x18005602b  inc     dword ptr [rcx+68h]
0x18005602e  mov     rbx, rdx
0x180056031  xor     r12d, r12d
0x180056034  mov     rdi, rcx
0x180056037  mov     rcx, rbx; this
0x18005603a  mov     [rbp+var_30], r12w
0x18005603f  mov     edx, 51CCh; unsigned __int16
0x180056044  mov     [rbp+var_2C], r12d
0x180056048  mov     [rbp+var_28], r12d
0x18005604c  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056051  test    eax, eax
0x180056053  js      loc_1800564A6
0x180056059  movzx   edx, word ptr [rdi+110h]; unsigned __int16
0x180056060  mov     rcx, rbx; this
0x180056063  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056068  test    eax, eax
0x18005606a  js      loc_1800564A6
0x180056070  movzx   edx, word ptr [rdi+0ECh]; unsigned __int16
0x180056077  mov     rcx, rbx; this
0x18005607a  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x18005607f  test    eax, eax
0x180056081  js      loc_1800564A6
0x180056087  mov     r8d, [rdi+0F4h]; unsigned int
0x18005608e  mov     rdx, rbx; struct STREAM *
0x180056091  mov     rcx, rdi; this
0x180056094  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x180056099  test    eax, eax
0x18005609b  js      loc_1800564A6
0x1800560a1  mov     r8d, [rdi+0F8h]; unsigned int
0x1800560a8  mov     rdx, rbx; struct STREAM *
0x1800560ab  mov     rcx, rdi; this
0x1800560ae  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x1800560b3  test    eax, eax
0x1800560b5  js      loc_1800564A6
0x1800560bb  mov     r8d, [rdi+100h]; unsigned int
0x1800560c2  mov     rdx, rbx; struct STREAM *
0x1800560c5  mov     rcx, rdi; this
0x1800560c8  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x1800560cd  test    eax, eax
0x1800560cf  js      loc_1800564A6
0x1800560d5  mov     edx, [rdi+0FCh]; unsigned int
0x1800560db  mov     rcx, rbx; this
0x1800560de  call    ?WriteULong@STREAM@@QEAAJK@Z; STREAM::WriteULong(ulong)
0x1800560e3  test    eax, eax
0x1800560e5  js      loc_1800564A6
0x1800560eb  movzx   edx, word ptr [rdi+104h]; unsigned __int16
0x1800560f2  mov     rcx, rbx; this
0x1800560f5  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x1800560fa  test    eax, eax
0x1800560fc  js      loc_1800564A6
0x180056102  mov     edx, [rdi+108h]; unsigned int
0x180056108  mov     rcx, rbx; this
0x18005610b  call    ?WriteULong@STREAM@@QEAAJK@Z; STREAM::WriteULong(ulong)
0x180056110  test    eax, eax
0x180056112  js      loc_1800564A6
0x180056118  movzx   edx, word ptr [rdi+10Ch]; unsigned __int16
0x18005611f  mov     rcx, rbx; this
0x180056122  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056127  test    eax, eax
0x180056129  js      loc_1800564A9
0x18005612f  movzx   edx, word ptr [rdi+112h]; unsigned __int16
0x180056136  mov     rcx, rbx; this
0x180056139  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x18005613e  test    eax, eax
0x180056140  js      loc_1800564A6
0x180056146  movzx   edx, word ptr [rdi+114h]; unsigned __int16
0x18005614d  mov     rcx, rbx; this
0x180056150  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056155  test    eax, eax
0x180056157  js      loc_1800564A6
0x18005615d  movzx   edx, word ptr [rdi+116h]; unsigned __int16
0x180056164  mov     rcx, rbx; this
0x180056167  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x18005616c  test    eax, eax
0x18005616e  js      loc_1800564A6
0x180056174  mov     rax, [rbx]
0x180056177  lea     rdx, [rdi+118h]
0x18005617e  lea     r8d, [r12+10h]
0x180056183  mov     rcx, rbx
0x180056186  mov     rax, [rax+10h]
0x18005618a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005618f  test    eax, eax
0x180056191  js      loc_1800564A6
0x180056197  mov     rax, [rbx]
0x18005619a  lea     rdx, [rdi+0ACh]
0x1800561a1  lea     r8d, [r12+40h]
0x1800561a6  mov     rcx, rbx
0x1800561a9  mov     rax, [rax+10h]
0x1800561ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561b2  test    eax, eax
0x1800561b4  js      loc_1800564A6
0x1800561ba  movzx   edx, word ptr [rdi+0F0h]; unsigned __int16
0x1800561c1  mov     rcx, rbx; this
0x1800561c4  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x1800561c9  test    eax, eax
0x1800561cb  js      loc_1800564A6
0x1800561d1  mov     r15d, r12d
0x1800561d4  movzx   eax, word ptr [rdi+0F0h]
0x1800561db  cmp     r15d, eax
0x1800561de  jnb     loc_180056361
0x1800561e4  mov     r14, [rdi+20h]
0x1800561e8  mov     rdx, rbx; struct STREAM *
0x1800561eb  movzx   eax, r15w
0x1800561ef  mov     rcx, rdi; this
0x1800561f2  lea     rsi, [rax+rax*4]
0x1800561f6  shl     rsi, 4
0x1800561fa  mov     r8d, [rsi+r14+18h]; unsigned int
0x1800561ff  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x180056204  test    eax, eax
0x180056206  js      loc_1800564A6
0x18005620c  mov     edx, 0Ah; unsigned __int16
0x180056211  mov     rcx, rbx; this
0x180056214  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056219  test    eax, eax
0x18005621b  js      loc_1800564A6
0x180056221  mov     edx, [rsi+r14+1Ch]; unsigned int
0x180056226  mov     rcx, rdi; this
0x180056229  call    ?QszOfHsz@GenericTypeLibOLE@@IEAAPEAGI@Z; GenericTypeLibOLE::QszOfHsz(uint)
0x18005622e  mov     [rsp+70h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180056233  xor     edx, edx; dwFlags
0x180056235  mov     r8, rax; lpWideCharStr
0x180056238  mov     [rsp+70h+lpDefaultChar], r12; lpDefaultChar
0x18005623d  lea     rax, [rbp+MultiByteStr]
0x180056241  mov     [rsp+70h+cbMultiByte], 0Ah; cbMultiByte
0x180056249  xor     ecx, ecx; CodePage
0x18005624b  mov     [rsp+70h+lpMultiByteStr], rax; lpMultiByteStr
0x180056250  lea     r9d, [rdx+0Ah]; cchWideChar
0x180056254  call    cs:__imp_WideCharToMultiByte
0x18005625a  mov     rax, [rbx]
0x18005625d  lea     rdx, [rbp+MultiByteStr]
0x180056261  mov     r8d, 0Ah
0x180056267  mov     rcx, rbx
0x18005626a  mov     rax, [rax+10h]
0x18005626e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056273  test    eax, eax
0x180056275  js      loc_1800564A6
0x18005627b  mov     r8d, [rsi+r14+24h]; unsigned int
0x180056280  mov     rdx, rbx; struct STREAM *
0x180056283  mov     rcx, rdi; this
0x180056286  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x18005628b  test    eax, eax
0x18005628d  js      loc_1800564A6
0x180056293  movzx   edx, word ptr [rsi+r14+20h]; unsigned __int16
0x180056299  mov     rcx, rbx; this
0x18005629c  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x1800562a1  test    eax, eax
0x1800562a3  js      loc_1800564A6
0x1800562a9  movzx   edx, word ptr [rsi+r14+28h]; unsigned __int16
0x1800562af  mov     rcx, rbx; this
0x1800562b2  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x1800562b7  test    eax, eax
0x1800562b9  js      loc_1800564A6
0x1800562bf  movzx   ecx, word ptr [rsi+r14+28h]
0x1800562c5  test    cx, cx
0x1800562c8  jz      short loc_1800562E5
0x1800562ca  mov     rax, [rbx]
0x1800562cd  mov     r8d, ecx
0x1800562d0  mov     edx, [rsi+r14+2Ch]
0x1800562d5  mov     rcx, rbx
0x1800562d8  add     rdx, [rdi+48h]
0x1800562dc  mov     rax, [rax+10h]
0x1800562e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562e5  mov     r8d, [rsi+r14+34h]; unsigned int
0x1800562ea  mov     rdx, rbx; struct STREAM *
0x1800562ed  mov     rcx, rdi; this
0x1800562f0  call    ?WriteString@GenericTypeLibOLE@@IEAAJPEAVSTREAM@@I@Z; GenericTypeLibOLE::WriteString(STREAM *,uint)
0x1800562f5  test    eax, eax
0x1800562f7  js      loc_1800564A6
0x1800562fd  mov     edx, [rsi+r14+30h]; unsigned int
0x180056302  mov     rcx, rbx; this
0x180056305  call    ?WriteULong@STREAM@@QEAAJK@Z; STREAM::WriteULong(ulong)
0x18005630a  test    eax, eax
0x18005630c  js      loc_1800564A6
0x180056312  movzx   edx, word ptr [rsi+r14]; unsigned __int16
0x180056317  mov     rcx, rbx; this
0x18005631a  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x18005631f  test    eax, eax
0x180056321  js      loc_1800564A6
0x180056327  mov     rax, [rbx]
0x18005632a  lea     rdx, [r14+38h]
0x18005632e  add     rdx, rsi
0x180056331  mov     r8d, 10h
0x180056337  mov     rcx, rbx
0x18005633a  mov     rax, [rax+10h]
0x18005633e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056343  movzx   edx, word ptr [rsi+r14+48h]; unsigned __int16
0x180056349  mov     rcx, rbx; this
0x18005634c  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x180056351  test    eax, eax
0x180056353  js      loc_1800564A6
0x180056359  inc     r15d
0x18005635c  jmp     loc_1800561D4
0x180056361  mov     rax, [rbx]
0x180056364  lea     rdx, [rbp+var_28]
0x180056368  mov     rcx, rbx
0x18005636b  mov     rax, [rax+18h]
0x18005636f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056374  test    eax, eax
0x180056376  js      loc_1800564A6
0x18005637c  mov     edx, [rbp+var_2C]; unsigned int
0x18005637f  mov     rcx, rbx; this
0x180056382  call    ?WriteULong@STREAM@@QEAAJK@Z; STREAM::WriteULong(ulong)
0x180056387  test    eax, eax
0x180056389  js      loc_1800564A6
0x18005638f  lea     rcx, [rdi+6B8h]; this
0x180056396  mov     rdx, rbx; struct STREAM *
0x180056399  call    ?Write@DOCSTR_MGR@@QEAAJPEAVSTREAM@@@Z; DOCSTR_MGR::Write(STREAM *)
0x18005639e  test    eax, eax
0x1800563a0  js      loc_1800564A6
0x1800563a6  mov     rax, [rbx]
0x1800563a9  lea     rdx, [rbp+var_2C]
0x1800563ad  mov     rcx, rbx
0x1800563b0  mov     rax, [rax+18h]
0x1800563b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563b9  test    eax, eax
0x1800563bb  js      loc_1800564A6
0x1800563c1  mov     rax, [rbx]
0x1800563c4  mov     rcx, rbx
0x1800563c7  mov     edx, [rbp+var_28]
0x1800563ca  mov     rax, [rax+20h]
0x1800563ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563d3  test    eax, eax
0x1800563d5  js      loc_1800564A6
0x1800563db  mov     edx, [rbp+var_2C]; unsigned int
0x1800563de  mov     rcx, rbx; this
0x1800563e1  call    ?WriteULong@STREAM@@QEAAJK@Z; STREAM::WriteULong(ulong)
0x1800563e6  test    eax, eax
0x1800563e8  js      loc_1800564A6
0x1800563ee  mov     rax, [rbx]
0x1800563f1  mov     rcx, rbx
0x1800563f4  mov     edx, [rbp+var_2C]
0x1800563f7  mov     rax, [rax+20h]
0x1800563fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056400  test    eax, eax
0x180056402  js      loc_1800564A6
0x180056408  lea     rsi, [rdi+218h]
0x18005640f  mov     rdx, rbx; struct STREAM *
0x180056412  mov     rcx, rsi; this
0x180056415  call    ?Write@BLK_MGR@@QEAAJPEAVSTREAM@@@Z; BLK_MGR::Write(STREAM *)
0x18005641a  test    eax, eax
0x18005641c  js      loc_1800564A6
0x180056422  movzx   edx, word ptr [rsi+50h]; unsigned __int16
0x180056426  mov     rcx, rbx; this
0x180056429  call    ?WriteUShort@STREAM@@QEAAJG@Z; STREAM::WriteUShort(ushort)
0x18005642e  test    eax, eax
0x180056430  js      short loc_1800564A6
0x180056432  mov     rcx, [rsi+48h]; this
0x180056436  mov     rdx, rbx; struct STREAM *
0x180056439  call    ?Write@BLK_MGR@@QEAAJPEAVSTREAM@@@Z; BLK_MGR::Write(STREAM *)
0x18005643e  test    eax, eax
0x180056440  js      short loc_1800564A6
0x180056442  lea     rcx, [rdi+138h]; this
0x180056449  mov     rdx, rbx; struct STREAM *
0x18005644c  call    ?Write@GENPROJ_TYPEBIND@@QEAAJPEAVSTREAM@@@Z; GENPROJ_TYPEBIND::Write(STREAM *)
0x180056451  test    eax, eax
0x180056453  js      short loc_1800564A6
0x180056455  mov     eax, r12d
0x180056458  lea     rsi, [rdi+680h]
0x18005645f  cmp     [rsi], r12
0x180056462  lea     rdx, [rbp+var_30]
0x180056466  mov     r8d, 2
0x18005646c  mov     rcx, rbx
0x18005646f  setnz   al
0x180056472  mov     [rbp+var_30], ax
0x180056476  mov     rax, [rbx]
0x180056479  mov     rax, [rax+10h]
0x18005647d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056482  test    eax, eax
0x180056484  js      short loc_1800564A6
0x180056486  cmp     [rbp+var_30], r12w
0x18005648b  jz      short loc_18005649C
0x18005648d  mov     rdx, rbx; struct STREAM *
0x180056490  mov     rcx, rsi; this
0x180056493  call    ?Write@BLK_DESC@@QEAAJPEAVSTREAM@@@Z; BLK_DESC::Write(STREAM *)
0x180056498  test    eax, eax
0x18005649a  js      short loc_1800564A6
0x18005649c  mov     dword ptr [rdi+678h], 0FFFFFFFFh
0x1800564a6  dec     dword ptr [rdi+68h]
0x1800564a9  mov     rcx, [rbp+var_10]
0x1800564ad  xor     rcx, rsp; StackCookie
0x1800564b0  call    __security_check_cookie
0x1800564b5  lea     r11, [rsp+70h+var_s0]
0x1800564ba  mov     rbx, [r11+40h]
0x1800564be  mov     rsi, [r11+48h]
0x1800564c2  mov     rsp, r11
0x1800564c5  pop     r15
0x1800564c7  pop     r14
0x1800564c9  pop     r12
  ... truncated ...
```
