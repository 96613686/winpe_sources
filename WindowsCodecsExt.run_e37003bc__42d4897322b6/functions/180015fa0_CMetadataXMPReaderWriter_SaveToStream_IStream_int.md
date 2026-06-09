# CMetadataXMPReaderWriter::SaveToStream(IStream *,int)

- ea: `0x180015fa0`
- end: `0x1800162b8`
- name: `?SaveToStream@CMetadataXMPReaderWriter@@MEAAJPEAUIStream@@H@Z`
- size: `792`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012afc`
- `0x180015684`
- `0x180015fa0`
- `0x1800171c4`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::SaveToStream(
        CMetadataXMPReaderWriter *this,
        struct IStream *a2,
        unsigned int a3)
{
  ULONG v5; // r14d
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  HRESULT v12; // eax
  __int64 v13; // rax
  __int64 (__fastcall *v14)(struct IStream *, _QWORD, __int64, ULONGLONG *); // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // ecx
  ULONG v18; // r9d
  ULONG v20; // [rsp+30h] [rbp-39h] BYREF
  int v21; // [rsp+34h] [rbp-35h] BYREF
  ULONG v22; // [rsp+38h] [rbp-31h] BYREF
  ULONG v23; // [rsp+3Ch] [rbp-2Dh] BYREF
  ULONGLONG ullOperand; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h]
  ULONGLONG v26[2]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v27; // [rsp+60h] [rbp-9h] BYREF
  __int64 v28; // [rsp+70h] [rbp+7h]
  __int64 v29; // [rsp+80h] [rbp+17h]
  ULONG pulResult; // [rsp+D0h] [rbp+67h] BYREF
  ULONG ulMinuend; // [rsp+E8h] [rbp+7Fh] BYREF

  v29 = 0;
  v27 = 0;
  v20 = 0;
  v22 = 0;
  if ( *((_DWORD *)this + 65) )
    v5 = *((_DWORD *)this + 64);
  else
    v5 = 0;
  v6 = *(_QWORD *)this;
  v23 = v5;
  if ( *((_QWORD *)this + 23) )
    v7 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, _QWORD))(v6 + 352))(this, a3);
  else
    v7 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, _QWORD))(v6 + 296))(this, a3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64))(*(_QWORD *)this + 400LL))(this, 1);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v10 = operator new(0x38u);
      v11 = v10;
      if ( v10 )
      {
        v10[2] = 0;
        *(_QWORD *)v10 = &CMILCOMBase::`vftable';
        _InterlockedAdd(&g_cActiveObjects, 1u);
        *((_QWORD *)v10 + 4) = 0;
        *(_QWORD *)v10 = &CEncodingStream::`vftable'{for `CMILCOMBase'};
        *((_QWORD *)v10 + 2) = &CEncodingStream::`vftable'{for `IStream'};
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 5) = 0;
        *((_QWORD *)v10 + 6) = 0;
        CEncodingStream::AddRef((CEncodingStream *)v10);
        v12 = (*(__int64 (__fastcall **)(_DWORD *, struct IStream *, __int64, __int64, _DWORD))(*(_QWORD *)v11 + 40LL))(
                v11,
                a2,
                1,
                1,
                0);
        v8 = v12;
        if ( v12 >= 0 )
        {
          v13 = *(_QWORD *)a2;
          v25 = 0;
          pulResult = 0;
          ulMinuend = 0;
          v14 = *(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(v13 + 40);
          v21 = 0;
          ullOperand = 0;
          v26[0] = 0;
          v12 = v14(a2, 0, 1, &ullOperand);
          v8 = v12;
          if ( v12 >= 0 )
          {
            v12 = ULongLongToULong(ullOperand, &pulResult);
            v8 = v12;
            if ( v12 >= 0 )
            {
              v15 = (__int64 *)*((_QWORD *)this + 23);
              LOWORD(v27) = 13;
              *((_QWORD *)&v27 + 1) = v11 + 4;
              v16 = *v15;
              v28 = v29;
              v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v16 + 528))(v15, &v27);
              v8 = v12;
              if ( v12 >= 0 )
              {
                if ( v12 )
                {
                  v8 = -2147467259;
                  goto LABEL_18;
                }
                if ( *((_DWORD *)this + 65) )
                  goto LABEL_31;
                v12 = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                        a2,
                        v25,
                        1,
                        v26);
                v8 = v12;
                if ( v12 >= 0 )
                {
                  v12 = ULongLongToULong(v26[0], &ulMinuend);
                  v8 = v12;
                  if ( v12 >= 0 )
                  {
                    v12 = (*(__int64 (__fastcall **)(_DWORD *, int *, __int64))(*(_QWORD *)v11 + 64LL))(v11, &v21, 1);
                    v8 = v12;
                    if ( v12 >= 0 )
                    {
                      v12 = ULongSub(ulMinuend, pulResult, &v20);
                      v8 = v12;
                      if ( v12 >= 0 )
                      {
                        if ( v20 + v21 < v20 )
                        {
                          v8 = -2147024362;
LABEL_18:
                          if ( g_doStackCaptures )
                          {
                            v17 = v8;
LABEL_34:
                            DoStackCapture(v17);
                            goto LABEL_35;
                          }
                          goto LABEL_35;
                        }
                        v12 = ULongLongToULong(*((_QWORD *)this + 22), &v22);
                        v8 = v12;
                        if ( v12 >= 0 )
                        {
                          if ( v22 <= v18 )
                            goto LABEL_31;
                          v12 = ULongSub(v22, v18, &v23);
                          v8 = v12;
                          if ( v12 >= 0 )
                          {
                            v5 = v23;
LABEL_31:
                            v12 = (*(__int64 (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)v11 + 48LL))(v11, v5);
                            v8 = v12;
                            if ( v12 >= 0 )
                              goto LABEL_35;
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
        if ( g_doStackCaptures )
        {
          v17 = v12;
          goto LABEL_34;
        }
LABEL_35:
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
        return v8;
      }
      v8 = -2147024882;
      if ( !g_doStackCaptures )
        return v8;
      v9 = -2147024882;
LABEL_38:
      DoStackCapture(v9);
      return v8;
    }
  }
  if ( g_doStackCaptures )
  {
    v9 = v7;
    goto LABEL_38;
  }
  return v8;
}

```

## disassembly

```asm
0x180015fa0  mov     [rsp-8+arg_8], rbx
0x180015fa5  push    rbp
0x180015fa6  push    rsi
0x180015fa7  push    rdi
0x180015fa8  push    r12
0x180015faa  push    r13
0x180015fac  push    r14
0x180015fae  push    r15
0x180015fb0  lea     rbp, [rsp-27h]
0x180015fb5  sub     rsp, 90h
0x180015fbc  xor     r12d, r12d
0x180015fbf  xor     eax, eax
0x180015fc1  xorps   xmm0, xmm0
0x180015fc4  mov     r15, rdx
0x180015fc7  mov     rdi, rcx
0x180015fca  mov     [rbp+57h+var_40], rax
0x180015fce  movups  [rbp+57h+var_60], xmm0
0x180015fd2  mov     [rbp+57h+var_90], r12d
0x180015fd6  mov     [rbp+57h+var_88], r12d
0x180015fda  cmp     [rcx+104h], r12d
0x180015fe1  jz      short loc_180015FEC
0x180015fe3  mov     r14d, [rcx+100h]
0x180015fea  jmp     short loc_180015FEF
0x180015fec  mov     r14d, r12d
0x180015fef  mov     edx, r8d
0x180015ff2  mov     rax, [rcx]
0x180015ff5  mov     [rbp+57h+var_84], r14d
0x180015ff9  cmp     [rcx+0B8h], r12
0x180016000  jz      short loc_180016028
0x180016002  mov     rax, [rax+160h]
0x180016009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600e  mov     ebx, eax
0x180016010  test    eax, eax
0x180016012  jns     short loc_180016031
0x180016014  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001601b  jz      loc_18001629B
0x180016021  mov     ecx, eax
0x180016023  jmp     loc_180016296
0x180016028  mov     rax, [rax+128h]
0x18001602f  jmp     short loc_180016009
0x180016031  mov     rax, [rdi]
0x180016034  mov     r13d, 1
0x18001603a  mov     edx, r13d
0x18001603d  mov     rcx, rdi
0x180016040  mov     rax, [rax+190h]
0x180016047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604c  mov     ebx, eax
0x18001604e  test    eax, eax
0x180016050  js      short loc_180016014
0x180016052  lea     ecx, [r13+37h]; Size
0x180016056  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001605b  mov     rsi, rax
0x18001605e  test    rax, rax
0x180016061  jz      loc_180016286
0x180016067  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18001606e  mov     [rsi+8], r12d
0x180016072  mov     [rsi], rax
0x180016075  lock add cs:?g_cActiveObjects@@3JC, r13d; long volatile g_cActiveObjects
0x18001607d  lea     rdx, ??_7CEncodingStream@@6BCMILCOMBase@@@; const CEncodingStream::`vftable'{for `CMILCOMBase'}
0x180016084  mov     [rsi+20h], r12
0x180016088  lea     rax, ??_7CEncodingStream@@6BIStream@@@; const CEncodingStream::`vftable'{for `IStream'}
0x18001608f  mov     [rsi], rdx
0x180016092  mov     [rsi+10h], rax
0x180016096  mov     rcx, rsi
0x180016099  mov     rax, [rdx+8]
0x18001609d  mov     [rsi+18h], r12
0x1800160a1  mov     [rsi+28h], r12
0x1800160a5  mov     [rsi+30h], r12
0x1800160a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ae  mov     rax, [rsi]
0x1800160b1  mov     r9d, r13d
0x1800160b4  mov     r8d, r13d
0x1800160b7  mov     [rsp+0C0h+var_A0], r12d
0x1800160bc  mov     rdx, r15
0x1800160bf  mov     rcx, rsi
0x1800160c2  mov     rax, [rax+28h]
0x1800160c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160cb  mov     ebx, eax
0x1800160cd  test    eax, eax
0x1800160cf  js      loc_180016265
0x1800160d5  mov     rax, [r15]
0x1800160d8  lea     r9, [rbp+57h+ullOperand]
0x1800160dc  mov     r8d, r13d
0x1800160df  mov     [rbp+57h+var_78], r12
0x1800160e3  mov     rdx, r12
0x1800160e6  mov     [rbp+57h+pulResult], r12d
0x1800160ea  mov     rcx, r15
0x1800160ed  mov     [rbp+57h+ulMinuend], r12d
0x1800160f1  mov     rax, [rax+28h]
0x1800160f5  mov     [rbp+57h+var_8C], r12d
0x1800160f9  mov     [rbp+57h+ullOperand], r12
0x1800160fd  mov     [rbp+57h+var_70], r12
0x180016101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016106  mov     ebx, eax
0x180016108  test    eax, eax
0x18001610a  js      loc_180016265
0x180016110  mov     rcx, [rbp+57h+ullOperand]; ullOperand
0x180016114  lea     rdx, [rbp+57h+pulResult]; pulResult
0x180016118  call    ULongLongToULong
0x18001611d  mov     ebx, eax
0x18001611f  test    eax, eax
0x180016121  js      loc_180016265
0x180016127  mov     rcx, [rdi+0B8h]
0x18001612e  lea     eax, [r13+0Ch]
0x180016132  movsd   xmm1, [rbp+57h+var_40]
0x180016137  lea     rdx, [rbp+57h+var_60]
0x18001613b  mov     word ptr [rbp+57h+var_60], ax
0x18001613f  lea     rax, [rsi+10h]
0x180016143  mov     qword ptr [rbp+57h+var_60+8], rax
0x180016147  mov     rax, [rcx]
0x18001614a  movups  xmm0, [rbp+57h+var_60]
0x18001614e  movsd   [rbp+57h+var_50], xmm1
0x180016153  mov     rax, [rax+210h]
0x18001615a  movaps  [rbp+57h+var_60], xmm0
0x18001615e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016163  mov     ebx, eax
0x180016165  test    eax, eax
0x180016167  js      loc_180016265
0x18001616d  jz      short loc_180016188
0x18001616f  mov     ebx, 80004005h
0x180016174  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001617b  jz      loc_180016275
0x180016181  mov     ecx, ebx
0x180016183  jmp     loc_180016270
0x180016188  cmp     [rdi+104h], r12d
0x18001618f  jnz     loc_18001624D
0x180016195  mov     rax, [r15]
0x180016198  lea     r9, [rbp+57h+var_70]
0x18001619c  mov     rdx, [rbp+57h+var_78]
0x1800161a0  mov     r8d, r13d
0x1800161a3  mov     rcx, r15
0x1800161a6  mov     rax, [rax+28h]
0x1800161aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161af  mov     ebx, eax
0x1800161b1  test    eax, eax
0x1800161b3  js      loc_180016265
0x1800161b9  mov     rcx, [rbp+57h+var_70]; ullOperand
0x1800161bd  lea     rdx, [rbp+57h+ulMinuend]; pulResult
0x1800161c1  call    ULongLongToULong
0x1800161c6  mov     ebx, eax
0x1800161c8  test    eax, eax
0x1800161ca  js      loc_180016265
0x1800161d0  mov     rax, [rsi]
0x1800161d3  lea     rdx, [rbp+57h+var_8C]
0x1800161d7  mov     r8d, r13d
0x1800161da  mov     rcx, rsi
0x1800161dd  mov     rax, [rax+40h]
0x1800161e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e6  mov     ebx, eax
0x1800161e8  test    eax, eax
0x1800161ea  js      short loc_180016265
0x1800161ec  mov     edx, [rbp+57h+pulResult]; ulSubtrahend
0x1800161ef  lea     r8, [rbp+57h+var_90]; pulResult
0x1800161f3  mov     ecx, [rbp+57h+ulMinuend]; ulMinuend
0x1800161f6  call    ULongSub
0x1800161fb  mov     ebx, eax
0x1800161fd  test    eax, eax
0x1800161ff  js      short loc_180016265
0x180016201  mov     r9d, [rbp+57h+var_8C]
0x180016205  add     r9d, [rbp+57h+var_90]
0x180016209  cmp     r9d, [rbp+57h+var_90]
0x18001620d  jnb     short loc_180016219
0x18001620f  mov     ebx, 80070216h
0x180016214  jmp     loc_180016174
0x180016219  mov     rcx, [rdi+0B0h]; ullOperand
0x180016220  lea     rdx, [rbp+57h+var_88]; pulResult
0x180016224  call    ULongLongToULong
0x180016229  mov     ebx, eax
0x18001622b  test    eax, eax
0x18001622d  js      short loc_180016265
0x18001622f  mov     ecx, [rbp+57h+var_88]; ulMinuend
0x180016232  cmp     ecx, r9d
0x180016235  jbe     short loc_18001624D
0x180016237  lea     r8, [rbp+57h+var_84]; pulResult
0x18001623b  mov     edx, r9d; ulSubtrahend
0x18001623e  call    ULongSub
0x180016243  mov     ebx, eax
0x180016245  test    eax, eax
0x180016247  js      short loc_180016265
0x180016249  mov     r14d, [rbp+57h+var_84]
0x18001624d  mov     rax, [rsi]
0x180016250  mov     edx, r14d
0x180016253  mov     rcx, rsi
0x180016256  mov     rax, [rax+30h]
0x18001625a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001625f  mov     ebx, eax
0x180016261  test    eax, eax
0x180016263  jns     short loc_180016275
0x180016265  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001626c  jz      short loc_180016275
0x18001626e  mov     ecx, eax; int
0x180016270  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180016275  mov     rax, [rsi]
0x180016278  mov     rcx, rsi
0x18001627b  mov     rax, [rax+10h]
0x18001627f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016284  jmp     short loc_18001629B
0x180016286  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001628d  mov     ebx, 8007000Eh
0x180016292  jz      short loc_18001629B
0x180016294  mov     ecx, ebx; int
0x180016296  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001629b  mov     eax, ebx
0x18001629d  mov     rbx, [rsp+0C0h+arg_8]
0x1800162a5  add     rsp, 90h
0x1800162ac  pop     r15
0x1800162ae  pop     r14
0x1800162b0  pop     r13
0x1800162b2  pop     r12
0x1800162b4  pop     rdi
0x1800162b5  pop     rsi
0x1800162b6  pop     rbp
0x1800162b7  retn
```
