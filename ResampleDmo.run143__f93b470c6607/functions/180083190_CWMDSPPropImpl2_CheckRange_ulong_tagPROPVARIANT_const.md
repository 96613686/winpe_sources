# CWMDSPPropImpl2::CheckRange(ulong,tagPROPVARIANT const &)

- ea: `0x180083190`
- end: `0x1800833bf`
- name: `?CheckRange@CWMDSPPropImpl2@@MEAAHKAEBUtagPROPVARIANT@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(CWMDSPPropImpl2 *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180083190`
- `0x1800833d0`
- `0x1800836a8`
- `0x180083994`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008320d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008320d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180083266`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180083266`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180083243`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180083243`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800832aa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800832aa`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl2::CheckRange(CWMDSPPropImpl2 *this, unsigned int a2, const struct tagPROPVARIANT *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  __int64 v8; // rsi
  signed int Dim; // r13d
  __int64 v10; // rax
  signed int i; // esi
  SAFEARRAY *parray; // rcx
  __int64 v13; // rcx
  _DWORD *v14; // rbx
  __int64 v15; // r11
  __int64 v16; // r15
  __int64 v17; // rsi
  unsigned __int16 v18; // r14
  int v19; // r11d
  void *ppvData; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+28h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+90h] [rbp+50h] BYREF
  int v24; // [rsp+98h] [rbp+58h] BYREF

  if ( a3->vt == 8 )
    return 1;
  if ( (a3->vt & 0x2000) == 0 )
    return CWMDSPPropImpl::CheckRange(this, a2, a3);
  v6 = *((_QWORD *)this + 2);
  v7 = 96LL * a2;
  ppvData = 0;
  v24 = 0;
  v8 = *(int *)(v6 + v7 + 92);
  plLbound = 0;
  if ( *((_QWORD *)this + 12) )
  {
    if ( (int)v8 >= 0 && (int)v8 < *((_DWORD *)this + 22) )
    {
      _mm_lfence();
      Dim = SafeArrayGetDim(a3->parray);
      v10 = *((_QWORD *)this + 12);
      v22[0] = 3 * v8;
      if ( Dim == *(_DWORD *)(v10 + 24 * v8 + 4) )
      {
        for ( i = 0; ; ++i )
        {
          parray = a3->parray;
          if ( i >= Dim )
            break;
          if ( SafeArrayGetLBound(parray, i + 1, &plLbound) < 0 )
            return 0;
          if ( plLbound != 1 )
            return 0;
          if ( SafeArrayGetUBound(a3->parray, i + 1, &plLbound) < 0 )
            return 0;
          v13 = *((_QWORD *)this + 12);
          if ( plLbound < *(_DWORD *)(*(_QWORD *)(v13 + 8LL * v22[0] + 8) + 4LL * i)
            || plLbound > *(_DWORD *)(*(_QWORD *)(v13 + 8LL * v22[0] + 16) + 4LL * i) )
          {
            return 0;
          }
        }
        if ( SafeArrayAccessData(parray, &ppvData) >= 0
          && (int)CWMDSPPropImpl2::SizeFromPropVar(this, a2, a3, &v24) >= 0 )
        {
          v14 = ppvData;
          v15 = 0;
          v16 = v22[0];
          while ( 1 )
          {
            if ( (int)v15 >= v24 )
              return 1;
            if ( (unsigned int)v15 >= v24 )
              goto LABEL_20;
            switch ( *(_WORD *)(*((_QWORD *)this + 12) + 8 * v16) )
            {
              case 3:
                goto LABEL_31;
              case 4:
                LODWORD(v22[0]) = v14[v15];
                break;
              case 5:
                v22[0] = *(_QWORD *)&v14[2 * v15];
                break;
              case 0xB:
                LOWORD(v22[0]) = *((_WORD *)v14 + v15);
                break;
              case 0x13:
LABEL_31:
                LODWORD(v22[0]) = v14[v15];
                break;
              case 0x14:
                v22[0] = *(_QWORD *)&v14[2 * v15];
                break;
              default:
LABEL_20:
                LODWORD(v22[0]) = 0;
                break;
            }
            v17 = *((_QWORD *)this + 2);
            v18 = *(_WORD *)(*((_QWORD *)this + 12) + 8 * v16);
            if ( !(unsigned int)WMDSPPropValLessOrEqual(v18, v7 + v17 + 56, v22)
              || !(unsigned int)WMDSPPropValLessOrEqual(v18, v22, v7 + v17 + 72) )
            {
              return 0;
            }
            v15 = (unsigned int)(v19 + 1);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180083190  mov     [rsp-38h+arg_0], rbx
0x180083195  push    rbp
0x180083196  push    rsi
0x180083197  push    rdi
0x180083198  push    r12
0x18008319a  push    r13
0x18008319c  push    r14
0x18008319e  push    r15
0x1800831a0  mov     rbp, rsp
0x1800831a3  sub     rsp, 40h
0x1800831a7  mov     eax, 8
0x1800831ac  mov     r14d, edx
0x1800831af  mov     rbx, r8
0x1800831b2  mov     rdi, rcx
0x1800831b5  cmp     [r8], ax
0x1800831b9  jz      loc_1800833A2
0x1800831bf  mov     eax, 2000h
0x1800831c4  test    [r8], ax
0x1800831c8  jz      loc_180083398
0x1800831ce  mov     rax, [rdi+10h]
0x1800831d2  lea     r12, [r14+r14*2]
0x1800831d6  xor     ecx, ecx
0x1800831d8  shl     r12, 5
0x1800831dc  mov     [rbp+ppvData], rcx
0x1800831e0  mov     [rbp+arg_18], ecx
0x1800831e3  movsxd  rsi, dword ptr [rax+r12+5Ch]
0x1800831e8  mov     [rbp+plLbound], ecx
0x1800831eb  cmp     [rdi+60h], rcx
0x1800831ef  jz      loc_180083394
0x1800831f5  test    esi, esi
0x1800831f7  js      loc_180083394
0x1800831fd  cmp     esi, [rdi+58h]
0x180083200  jge     loc_180083394
0x180083206  lfence
0x180083209  mov     rcx, [r8+8]; psa
0x18008320d  call    cs:__imp_SafeArrayGetDim
0x180083213  mov     r13d, eax
0x180083216  lea     r15, [rsi+rsi*2]
0x18008321a  mov     rax, [rdi+60h]
0x18008321e  mov     [rbp+var_18], r15
0x180083222  cmp     r13d, [rax+r15*8+4]
0x180083227  jnz     loc_180083394
0x18008322d  xor     esi, esi
0x18008322f  mov     rcx, [rbx+8]; psa
0x180083233  cmp     esi, r13d
0x180083236  jge     short loc_1800832A6
0x180083238  lea     r15d, [rsi+1]
0x18008323c  mov     edx, r15d; nDim
0x18008323f  lea     r8, [rbp+plLbound]; plLbound
0x180083243  call    cs:__imp_SafeArrayGetLBound
0x180083249  test    eax, eax
0x18008324b  js      loc_180083394
0x180083251  cmp     [rbp+plLbound], 1
0x180083255  jnz     loc_180083394
0x18008325b  mov     rcx, [rbx+8]; psa
0x18008325f  lea     r8, [rbp+plLbound]; plUbound
0x180083263  mov     edx, r15d; nDim
0x180083266  call    cs:__imp_SafeArrayGetUBound
0x18008326c  test    eax, eax
0x18008326e  js      loc_180083394
0x180083274  mov     rcx, [rdi+60h]
0x180083278  mov     r9, [rbp+var_18]
0x18008327c  mov     r8d, [rbp+plLbound]
0x180083280  movsxd  rdx, esi
0x180083283  mov     rax, [rcx+r9*8+8]
0x180083288  cmp     r8d, [rax+rdx*4]
0x18008328c  jl      loc_180083394
0x180083292  mov     rax, [rcx+r9*8+10h]
0x180083297  cmp     r8d, [rax+rdx*4]
0x18008329b  jg      loc_180083394
0x1800832a1  mov     esi, r15d
0x1800832a4  jmp     short loc_18008322F
0x1800832a6  lea     rdx, [rbp+ppvData]; ppvData
0x1800832aa  call    cs:__imp_SafeArrayAccessData
0x1800832b0  test    eax, eax
0x1800832b2  js      loc_180083394
0x1800832b8  lea     r9, [rbp+arg_18]; int *
0x1800832bc  mov     r8, rbx; struct tagPROPVARIANT *
0x1800832bf  mov     edx, r14d; unsigned int
0x1800832c2  mov     rcx, rdi; this
0x1800832c5  call    ?SizeFromPropVar@CWMDSPPropImpl2@@IEAAJKPEBUtagPROPVARIANT@@PEAJ@Z; CWMDSPPropImpl2::SizeFromPropVar(ulong,tagPROPVARIANT const *,long *)
0x1800832ca  test    eax, eax
0x1800832cc  js      loc_180083394
0x1800832d2  mov     rbx, [rbp+ppvData]
0x1800832d6  xor     r11d, r11d
0x1800832d9  mov     r15, [rbp+var_18]
0x1800832dd  cmp     r11d, [rbp+arg_18]
0x1800832e1  jge     loc_1800833A2
0x1800832e7  jb      short loc_1800832F2
0x1800832e9  mov     dword ptr [rbp+var_18], 0
0x1800832f0  jmp     short loc_18008334F
0x1800832f2  mov     rax, [rdi+60h]
0x1800832f6  movzx   ecx, word ptr [rax+r15*8]
0x1800832fb  sub     ecx, 3
0x1800832fe  jz      short loc_180083348
0x180083300  sub     ecx, 1
0x180083303  jz      short loc_18008333B
0x180083305  sub     ecx, 1
0x180083308  jz      short loc_18008332E
0x18008330a  sub     ecx, 6
0x18008330d  jz      short loc_180083323
0x18008330f  sub     ecx, 8
0x180083312  jz      short loc_180083348
0x180083314  cmp     ecx, 1
0x180083317  jnz     short loc_1800832E9
0x180083319  mov     rcx, [rbx+r11*8]
0x18008331d  mov     [rbp+var_18], rcx
0x180083321  jmp     short loc_18008334F
0x180083323  movzx   ecx, word ptr [rbx+r11*2]
0x180083328  mov     word ptr [rbp+var_18], cx
0x18008332c  jmp     short loc_18008334F
0x18008332e  movsd   xmm0, qword ptr [rbx+r11*8]
0x180083334  movsd   [rbp+var_18], xmm0
0x180083339  jmp     short loc_18008334F
0x18008333b  movss   xmm0, dword ptr [rbx+r11*4]
0x180083341  movss   dword ptr [rbp+var_18], xmm0
0x180083346  jmp     short loc_18008334F
0x180083348  mov     ecx, [rbx+r11*4]
0x18008334c  mov     dword ptr [rbp+var_18], ecx
0x18008334f  mov     rax, [rdi+60h]
0x180083353  lea     r8, [rbp+var_18]
0x180083357  mov     rsi, [rdi+10h]
0x18008335b  movzx   r14d, word ptr [rax+r15*8]
0x180083360  lea     rdx, [rsi+38h]
0x180083364  movzx   ecx, r14w
0x180083368  add     rdx, r12
0x18008336b  call    WMDSPPropValLessOrEqual
0x180083370  test    eax, eax
0x180083372  jz      short loc_180083394
0x180083374  lea     r8, [rsi+48h]
0x180083378  movzx   ecx, r14w
0x18008337c  add     r8, r12
0x18008337f  lea     rdx, [rbp+var_18]
0x180083383  call    WMDSPPropValLessOrEqual
0x180083388  test    eax, eax
0x18008338a  jz      short loc_180083394
0x18008338c  inc     r11d
0x18008338f  jmp     loc_1800832DD
0x180083394  xor     eax, eax
0x180083396  jmp     short loc_1800833A7
0x180083398  mov     edx, r14d; unsigned int
0x18008339b  call    ?CheckRange@CWMDSPPropImpl@@MEAAHKAEBUtagPROPVARIANT@@@Z; CWMDSPPropImpl::CheckRange(ulong,tagPROPVARIANT const &)
0x1800833a0  jmp     short loc_1800833A7
0x1800833a2  mov     eax, 1
0x1800833a7  mov     rbx, [rsp+40h+arg_0]
0x1800833af  add     rsp, 40h
0x1800833b3  pop     r15
0x1800833b5  pop     r14
0x1800833b7  pop     r13
0x1800833b9  pop     r12
0x1800833bb  pop     rdi
0x1800833bc  pop     rsi
0x1800833bd  pop     rbp
0x1800833be  retn
```
