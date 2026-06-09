# CSCardSubcontext::LocateCards(ushort const *,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEW *,ulong)

- ea: `0x180024254`
- end: `0x18002462d`
- name: `?LocateCards@CSCardSubcontext@@QEAAXPEBGPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEW@@K@Z`
- size: `985`
- prototype: `void(CSCardSubcontext *__hidden this, const unsigned __int16 *, struct _SCARD_ATRMASK *, unsigned int, struct SCARD_READERSTATEW *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180024634`

## callees

- `0x180003ee0`
- `0x180003fc0`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000d640`
- `0x18000e3d0`
- `0x18000ff10`
- `0x1800131dc`
- `0x180024254`
- `0x18002e5e8`
- `0x18002ef20`
- `0x18002ef38`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSCardSubcontext::LocateCards(
        CSCardSubcontext *this,
        const unsigned __int16 *a2,
        struct _SCARD_ATRMASK *a3,
        unsigned int a4,
        struct SCARD_READERSTATEW *a5,
        unsigned int pExceptionObject)
{
  const unsigned __int16 *v6; // r15
  int v7; // r12d
  int v8; // edi
  int v9; // r13d
  int v10; // esi
  unsigned int v11; // r14d
  unsigned int v12; // ebx
  const WCHAR *v13; // rax
  __int64 v14; // r13
  unsigned int v15; // r15d
  const unsigned __int16 *String; // rax
  struct CBuffer *v17; // r8
  const unsigned __int16 *v18; // rbx
  const unsigned __int8 *v19; // rdx
  const WCHAR *v20; // rbx
  const WCHAR *v21; // r10
  unsigned int v22; // r15d
  const WCHAR *v23; // rcx
  const WCHAR *v24; // r9
  unsigned int Cards; // eax
  unsigned int v26; // esi
  char *v27; // rdi
  unsigned int v28; // r12d
  struct SCARD_READERSTATEW *v29; // rcx
  unsigned __int64 v30; // r14
  __int64 v31; // r13
  char *v32; // rdi
  BYTE *v33; // rcx
  int v34; // [rsp+60h] [rbp-A8h]
  unsigned __int8 v35[4]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int i; // [rsp+6Ch] [rbp-9Ch]
  __int64 v37; // [rsp+70h] [rbp-98h] BYREF
  int v38[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v39; // [rsp+80h] [rbp-88h]
  __int64 v40; // [rsp+88h] [rbp-80h]
  const int *v41; // [rsp+90h] [rbp-78h] BYREF
  __int64 v42; // [rsp+98h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-68h]
  void *v44; // [rsp+A8h] [rbp-60h] BYREF
  const int *v45; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-48h]
  const int *v48; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-38h]
  int v50[2]; // [rsp+D8h] [rbp-30h]
  const WCHAR *v51; // [rsp+E0h] [rbp-28h]
  const void *v52[2]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned int v53; // [rsp+F8h] [rbp-10h]
  int v54; // [rsp+FCh] [rbp-Ch]

  v6 = a2;
  v48 = &CBuffer::`vftable';
  v49 = 0;
  *(_QWORD *)v50 = 0;
  v45 = &CBuffer::`vftable';
  v46 = 0;
  v47 = 0;
  v41 = &CBuffer::`vftable';
  v7 = 0;
  v42 = 0;
  v8 = 0;
  v43 = 0;
  v9 = 0;
  *(_QWORD *)v38 = &CBuffer::`vftable';
  v39 = 0;
  v10 = 0;
  v40 = 0;
  CBuffer::CBuffer((CBuffer *)v52, 0x24u);
  LODWORD(v37) = 0;
  v44 = 0;
  v11 = pExceptionObject;
  if ( pExceptionObject )
  {
    if ( !*v6 )
    {
      pExceptionObject = -2146435063;
      throw &pExceptionObject;
    }
    v12 = 4 * pExceptionObject;
    CBuffer::Presize((CBuffer *)&v45, 4 * pExceptionObject, 0);
    LODWORD(v47) = v12;
    v13 = &WideCharStr;
    if ( HIDWORD(v47) )
      v13 = (const WCHAR *)v46;
    v51 = v13;
    if ( a4 )
    {
      v14 = 0;
      v15 = 0;
      do
      {
        CBuffer::Presize((CBuffer *)&v41, a3[v14].cbAtr + v8 + 1, 1);
        CBuffer::Presize((CBuffer *)v38, v10 + a3[v14].cbAtr + 1, 1);
        v35[0] = a3[v14].cbAtr;
        CBuffer::Append((CBuffer *)&v41, v35, 1u);
        CBuffer::Append((CBuffer *)&v41, a3[v14].rgbAtr, v35[0]);
        CBuffer::Append((CBuffer *)v38, v35, 1u);
        CBuffer::Append((CBuffer *)v38, a3[v14].rgbMask, v35[0]);
        ++v15;
        ++v14;
        v8 = v43;
        v10 = v40;
      }
      while ( v15 < a4 );
      v9 = HIDWORD(v43);
      v7 = v42;
      v11 = pExceptionObject;
      v6 = a2;
    }
    String = FirstString(v6);
    for ( i = 0; ; ++i )
    {
      v18 = String;
      if ( !String )
        break;
      if ( !(unsigned int)GetReaderInfo(*(_DWORD *)(*((_QWORD *)this + 5) + 28LL), String, v17, v52) )
      {
        pExceptionObject = -2146435063;
        throw &pExceptionObject;
      }
      v19 = (const unsigned __int8 *)&WideCharStr;
      if ( v54 )
        v19 = (const unsigned __int8 *)v52[1];
      CBuffer::Append((CBuffer *)&v48, v19, v53);
      *(_DWORD *)&v51[2 * i] = a5[(unsigned __int64)i].dwCurrentState;
      String = NextString(v18);
    }
    v20 = &WideCharStr;
    CBuffer::Append((CBuffer *)&v48, (const unsigned __int8 *const)&WideCharStr, 2u);
    v21 = &WideCharStr;
    v22 = 0;
    if ( HIDWORD(v47) )
      v21 = (const WCHAR *)v46;
    v23 = &WideCharStr;
    if ( v50[1] )
      v23 = (const WCHAR *)v49;
    v24 = &WideCharStr;
    if ( HIDWORD(v40) )
      LODWORD(v24) = v39;
    if ( v9 )
      LODWORD(v20) = v7;
    Cards = CalRpcLocateCards(
              *((_QWORD *)this + 14),
              (int)v20,
              v8,
              (int)v24,
              v10,
              (__int64)v23,
              v50[0],
              (__int64)v21,
              v11,
              (__int64)&v44,
              (__int64)&v37,
              v34,
              *(int *)v35,
              v37,
              v38[0]);
    v26 = Cards;
    if ( Cards )
    {
      pExceptionObject = Cards;
      throw &pExceptionObject;
    }
    v27 = (char *)v44;
    v28 = v37;
    v29 = a5;
    while ( v22 < v11 )
    {
      v30 = (unsigned __int64)v22 << 6;
      *(DWORD *)((char *)&v29->dwEventState + v30) = *(_DWORD *)&v51[2 * v22];
      v31 = (unsigned __int8)*v27;
      if ( (unsigned int)v31 >= v28 )
      {
        v26 = -2146435053;
        break;
      }
      v32 = v27 + 1;
      v33 = &v29->rgbAtr[v30];
      *(_OWORD *)v33 = 0;
      *((_OWORD *)v33 + 1) = 0;
      *((_DWORD *)v33 + 8) = 0;
      memcpy_0(v33, v32, (unsigned int)v31);
      v29 = a5;
      *(DWORD *)((char *)&a5->cbAtr + v30) = v31;
      v28 += -1 - v31;
      LODWORD(v37) = v28;
      v27 = &v32[v31];
      ++v22;
      v11 = pExceptionObject;
    }
    MIDL_user_free(v44);
    if ( v26 )
    {
      pExceptionObject = v26;
      throw &pExceptionObject;
    }
  }
  v52[0] = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)v52);
  *(_QWORD *)v38 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)v38);
  v41 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v41);
  v45 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v45);
  v48 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v48);
}

```

## disassembly

```asm
0x180024254  mov     rax, rsp
0x180024257  mov     [rax+20h], r9d
0x18002425b  mov     [rax+18h], r8
0x18002425f  mov     [rax+10h], rdx
0x180024263  mov     [rax+8], rcx
0x180024267  push    rbp
0x180024268  push    rbx
0x180024269  push    rsi
0x18002426a  push    rdi
0x18002426b  push    r12
0x18002426d  push    r13
0x18002426f  push    r14
0x180024271  push    r15
0x180024273  lea     rbp, [rax-48h]
0x180024277  sub     rsp, 108h
0x18002427e  mov     r15, rdx
0x180024281  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180024288  mov     [rbp+40h+var_80], rax
0x18002428c  xor     ebx, ebx
0x18002428e  mov     [rbp+40h+var_78], rbx
0x180024292  mov     qword ptr [rbp+40h+var_70], rbx
0x180024296  mov     [rbp+40h+var_98], rax
0x18002429a  mov     [rbp+40h+var_90], rbx
0x18002429e  mov     [rbp+40h+var_88], rbx
0x1800242a2  mov     [rbp+40h+var_B8], rax
0x1800242a6  mov     r12d, ebx
0x1800242a9  mov     [rbp+40h+var_B0], rbx
0x1800242ad  mov     edi, ebx
0x1800242af  mov     [rbp+40h+var_A8], rbx
0x1800242b3  mov     r13d, ebx
0x1800242b6  mov     qword ptr [rsp+140h+var_D0], rax; pExceptionObject
0x1800242bb  mov     [rsp+140h+var_C8], rbx
0x1800242c0  mov     esi, ebx
0x1800242c2  mov     [rbp+40h+var_C0], rbx
0x1800242c6  lea     edx, [rbx+24h]; unsigned int
0x1800242c9  lea     rcx, [rbp+40h+var_60]; this
0x1800242cd  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x1800242d2  nop
0x1800242d3  mov     dword ptr [rsp+140h+var_D8], ebx; int
0x1800242d7  mov     [rbp+40h+var_A0], rbx
0x1800242db  mov     r14d, [rbp+40h+pExceptionObject]
0x1800242df  test    r14d, r14d
0x1800242e2  jz      loc_1800245CB
0x1800242e8  cmp     bx, [r15]
0x1800242ec  jnz     short loc_180024306
0x1800242ee  mov     [rbp+40h+pExceptionObject], 80100009h
0x1800242f5  lea     rdx, _TI1K; pThrowInfo
0x1800242fc  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180024300  call    _CxxThrowException_0
0x180024306  lea     ebx, ds:0[r14*4]
0x18002430e  xor     r8d, r8d; int
0x180024311  mov     edx, ebx; unsigned int
0x180024313  lea     rcx, [rbp+40h+var_98]; this
0x180024317  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18002431c  mov     dword ptr [rbp+40h+var_88], ebx
0x18002431f  lea     rax, WideCharStr
0x180024326  xor     ecx, ecx
0x180024328  cmp     dword ptr [rbp+40h+var_88+4], ecx
0x18002432b  cmova   rax, [rbp+40h+var_90]
0x180024330  mov     [rbp+40h+var_68], rax
0x180024334  cmp     [rbp+40h+arg_18], ecx
0x180024337  jbe     loc_1800243FB
0x18002433d  mov     r13d, ecx
0x180024340  mov     r14d, [rbp+40h+arg_18]
0x180024344  mov     r12, [rbp+40h+arg_10]
0x180024348  mov     r15d, ecx
0x18002434b  imul    rbx, r13, 4Ch ; 'L'
0x18002434f  lea     edx, [rdi+1]
0x180024352  add     edx, [rbx+r12]; unsigned int
0x180024356  mov     edi, 1
0x18002435b  mov     r8d, edi; int
0x18002435e  lea     rcx, [rbp+40h+var_B8]; this
0x180024362  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x180024367  mov     edx, [rbx+r12]
0x18002436b  inc     edx
0x18002436d  add     edx, esi; unsigned int
0x18002436f  mov     r8d, edi; int
0x180024372  lea     rcx, [rsp+140h+var_D0]; this
0x180024377  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18002437c  mov     al, [rbx+r12]
0x180024380  mov     [rsp+140h+var_E0], al; int
0x180024384  mov     r8d, edi; unsigned int
0x180024387  lea     rdx, [rsp+140h+var_E0]; unsigned __int8 *
0x18002438c  lea     rcx, [rbp+40h+var_B8]; this
0x180024390  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x180024395  movzx   r8d, [rsp+140h+var_E0]; unsigned int
0x18002439b  lea     rdx, [r12+4]
0x1800243a0  add     rdx, rbx; unsigned __int8 *
0x1800243a3  lea     rcx, [rbp+40h+var_B8]; this
0x1800243a7  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x1800243ac  mov     r8d, edi; unsigned int
0x1800243af  lea     rdx, [rsp+140h+var_E0]; unsigned __int8 *
0x1800243b4  lea     rcx, [rsp+140h+var_D0]; this
0x1800243b9  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x1800243be  movzx   r8d, [rsp+140h+var_E0]; unsigned int
0x1800243c4  lea     rdx, [r12+28h]
0x1800243c9  add     rdx, rbx; unsigned __int8 *
0x1800243cc  lea     rcx, [rsp+140h+var_D0]; this
0x1800243d1  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x1800243d6  add     r15d, edi
0x1800243d9  add     r13, rdi
0x1800243dc  mov     edi, dword ptr [rbp+40h+var_A8]
0x1800243df  mov     esi, dword ptr [rbp+40h+var_C0]
0x1800243e2  cmp     r15d, r14d
0x1800243e5  jb      loc_18002434B
0x1800243eb  mov     r13d, dword ptr [rbp+40h+var_A8+4]
0x1800243ef  mov     r12, [rbp+40h+var_B0]
0x1800243f3  mov     r14d, [rbp+40h+pExceptionObject]
0x1800243f7  mov     r15, [rbp+40h+arg_8]
0x1800243fb  mov     rcx, r15; unsigned __int16 *
0x1800243fe  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x180024403  mov     [rsp+140h+var_DC], 0
0x18002440b  mov     r15, [rbp+40h+arg_20]
0x18002440f  mov     rbx, rax
0x180024412  test    rax, rax
0x180024415  jz      short loc_18002448B
0x180024417  mov     rax, [rbp+40h+arg_0]
0x18002441b  mov     rcx, [rax+28h]
0x18002441f  lea     r9, [rbp+40h+var_60]; struct CBuffer *
0x180024423  mov     rdx, rbx; unsigned __int16 *
0x180024426  mov     ecx, [rcx+1Ch]; unsigned int
0x180024429  call    ?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z; GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)
0x18002442e  test    eax, eax
0x180024430  jz      short loc_180024473
0x180024432  lea     rdx, WideCharStr
0x180024439  cmp     [rbp+40h+var_4C], 0
0x18002443d  cmova   rdx, [rbp+40h+var_58]; unsigned __int8 *
0x180024442  mov     r8d, [rbp+40h+var_50]; unsigned int
0x180024446  lea     rcx, [rbp+40h+var_80]; this
0x18002444a  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x18002444f  mov     ecx, [rsp+140h+var_DC]
0x180024453  mov     eax, ecx
0x180024455  shl     rax, 6
0x180024459  mov     eax, [rax+r15+10h]
0x18002445e  mov     rdx, [rbp+40h+var_68]
0x180024462  mov     [rdx+rcx*4], eax
0x180024465  mov     rcx, rbx; unsigned __int16 *
0x180024468  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002446d  inc     [rsp+140h+var_DC]
0x180024471  jmp     short loc_18002440F
0x180024473  mov     [rbp+40h+pExceptionObject], 80100009h
0x18002447a  lea     rdx, _TI1K; pThrowInfo
0x180024481  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180024485  call    _CxxThrowException_0
0x18002448b  mov     r8d, 2; unsigned int
0x180024491  lea     rbx, WideCharStr
0x180024498  mov     rdx, rbx; unsigned __int8 *
0x18002449b  lea     rcx, [rbp+40h+var_80]; this
0x18002449f  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x1800244a4  mov     r10, rbx
0x1800244a7  xor     r15d, r15d
0x1800244aa  cmp     dword ptr [rbp+40h+var_88+4], r15d
0x1800244ae  cmova   r10, [rbp+40h+var_90]
0x1800244b3  mov     eax, [rbp+40h+var_70]
0x1800244b6  mov     rcx, rbx
0x1800244b9  cmp     [rbp+40h+var_70+4], r15d
0x1800244bd  cmova   rcx, [rbp+40h+var_78]
0x1800244c2  mov     r9, rbx
0x1800244c5  cmp     dword ptr [rbp+40h+var_C0+4], r15d
0x1800244c9  cmova   r9, [rsp+140h+var_C8]; int
0x1800244cf  test    r13d, r13d
0x1800244d2  cmovnz  rbx, r12
0x1800244d6  lea     rdx, [rsp+140h+var_D8]
0x1800244db  mov     [rsp+50h], rdx; __int64
0x1800244e0  lea     rdx, [rbp+40h+var_A0]
0x1800244e4  mov     [rsp+140h+var_F8], rdx; __int64
0x1800244e9  mov     [rsp+140h+var_100], r14d; int
0x1800244ee  mov     [rsp+140h+var_108], r10; __int64
0x1800244f3  mov     [rsp+140h+var_110], eax; int
0x1800244f7  mov     [rsp+140h+var_118], rcx; __int64
0x1800244fc  mov     [rsp+140h+var_120], esi; int
0x180024500  mov     r8d, edi; int
0x180024503  mov     rdx, rbx; int
0x180024506  mov     rax, [rbp+40h+arg_0]
0x18002450a  mov     rcx, [rax+70h]; int
0x18002450e  call    CalRpcLocateCards
0x180024513  mov     esi, eax
0x180024515  test    eax, eax
0x180024517  jz      short loc_18002452D
0x180024519  mov     [rbp+40h+pExceptionObject], eax
0x18002451c  lea     rdx, _TI1K; pThrowInfo
0x180024523  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180024527  call    _CxxThrowException_0
0x18002452d  mov     rdi, [rbp+40h+var_A0]
0x180024531  mov     r12d, dword ptr [rsp+140h+var_D8]
0x180024536  mov     rcx, [rbp+40h+arg_20]
0x18002453a  cmp     r15d, r14d
0x18002453d  jnb     short loc_1800245AA
0x18002453f  mov     eax, r15d
0x180024542  mov     r14d, r15d
0x180024545  shl     r14, 6
0x180024549  mov     rdx, [rbp+40h+var_68]
0x18002454d  mov     eax, [rdx+rax*4]
0x180024550  mov     [r14+rcx+14h], eax
0x180024555  movzx   r13d, byte ptr [rdi]
0x180024559  cmp     r13d, r12d
0x18002455c  jnb     short loc_1800245A5
0x18002455e  inc     rdi
0x180024561  add     rcx, 1Ch
0x180024565  add     rcx, r14; void *
0x180024568  xorps   xmm0, xmm0
0x18002456b  xor     eax, eax
0x18002456d  movups  xmmword ptr [rcx], xmm0
0x180024570  movups  xmmword ptr [rcx+10h], xmm0
0x180024574  mov     [rcx+20h], eax
0x180024577  mov     r8d, r13d; Size
0x18002457a  mov     rdx, rdi; Src
0x18002457d  call    memcpy_0
0x180024582  mov     rcx, [rbp+40h+arg_20]
0x180024586  mov     [r14+rcx+18h], r13d
0x18002458b  or      eax, 0FFFFFFFFh
0x18002458e  sub     eax, r13d
0x180024591  add     r12d, eax
0x180024594  mov     dword ptr [rsp+140h+var_D8], r12d
0x180024599  add     rdi, r13
0x18002459c  inc     r15d
0x18002459f  mov     r14d, [rbp+40h+pExceptionObject]
0x1800245a3  jmp     short loc_18002453A
0x1800245a5  mov     esi, 80100013h
0x1800245aa  mov     rcx, [rbp+40h+var_A0]; void *
0x1800245ae  call    MIDL_user_free
0x1800245b3  test    esi, esi
0x1800245b5  jz      short loc_1800245CB
0x1800245b7  mov     [rbp+40h+pExceptionObject], esi
0x1800245ba  lea     rdx, _TI1K; pThrowInfo
0x1800245c1  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800245c5  call    _CxxThrowException_0
0x1800245cb  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800245d2  mov     [rbp+40h+var_60], rbx
0x1800245d6  lea     rcx, [rbp+40h+var_60]; this
0x1800245da  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800245df  nop
0x1800245e0  mov     qword ptr [rsp+140h+var_D0], rbx
0x1800245e5  lea     rcx, [rsp+140h+var_D0]; this
0x1800245ea  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800245ef  nop
0x1800245f0  mov     [rbp+40h+var_B8], rbx
0x1800245f4  lea     rcx, [rbp+40h+var_B8]; this
0x1800245f8  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800245fd  nop
0x1800245fe  mov     [rbp+40h+var_98], rbx
0x180024602  lea     rcx, [rbp+40h+var_98]; this
0x180024606  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002460b  nop
0x18002460c  mov     [rbp+40h+var_80], rbx
0x180024610  lea     rcx, [rbp+40h+var_80]; this
0x180024614  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x180024619  add     rsp, 108h
0x180024620  pop     r15
0x180024622  pop     r14
0x180024624  pop     r13
0x180024626  pop     r12
0x180024628  pop     rdi
0x180024629  pop     rsi
0x18002462a  pop     rbx
0x18002462b  pop     rbp
0x18002462c  retn
```
