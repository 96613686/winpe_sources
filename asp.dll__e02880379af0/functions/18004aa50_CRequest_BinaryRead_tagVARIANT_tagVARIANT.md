# CRequest::BinaryRead(tagVARIANT *,tagVARIANT *)

- ea: `0x18004aa50`
- end: `0x18004ad45`
- name: `?BinaryRead@CRequest@@UEAAJPEAUtagVARIANT@@0@Z`
- size: `757`
- prototype: `__int64 __fastcall(CRequestData **this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180023d6e`
- `0x1800406b0`
- `0x18004aa50`
- `0x18004ad4c`
- `0x18004bcb4`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004ad38`
- `OLEAUT32!__imp_VariantClear` at `0x18004ad38`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004ab8b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004ab8b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004abaf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004abaf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ac36`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ad10`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ac36`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ad10`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18004aad3`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18004aad3`

## pseudocode

```c
__int64 __fastcall CRequest::BinaryRead(CRequestData **this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  CRequestData *v7; // r8
  unsigned int v8; // r8d
  HRESULT v9; // eax
  unsigned int v10; // ebx
  GUID *v11; // rcx
  unsigned __int64 lVal; // rax
  CRequestData *v13; // rcx
  unsigned __int64 v14; // rbx
  SAFEARRAY *v15; // rax
  CRequestData *v16; // rax
  CRequestData *v17; // rcx
  size_t v18; // r8
  CRequestData *v19; // rcx
  __int64 v20; // rax
  CRequestData *v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-18h] BYREF
  void *ppvData; // [rsp+88h] [rbp+38h] BYREF

  if ( (int)CRequest::CheckForTombstone((CRequest *)this) < 0 )
    return 2147500037LL;
  a3->vt = 8209;
  a3->llVal = 0;
  v7 = this[7];
  v23 = 0;
  ppvData = 0;
  if ( *((_DWORD *)v7 + 81) == 2 )
  {
    v8 = 6501;
LABEL_38:
    v10 = -2147467259;
    goto LABEL_39;
  }
  v9 = VariantChangeTypeEx(a2, a2, *(_DWORD *)(*((_QWORD *)v7 + 7) + 168LL), 0, 3u);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -2147352571 )
    {
      v8 = 106;
    }
    else if ( v9 == -2147352566 )
    {
      v10 = -2147467259;
      v8 = 6010;
    }
    else
    {
      v8 = (v9 != -2147024882) + 100;
    }
    v11 = &IID_IResponse;
    goto LABEL_40;
  }
  lVal = a2->lVal;
  a2->lVal = 0;
  if ( (lVal & 0x80000000) != 0LL )
  {
    v8 = 6505;
    goto LABEL_38;
  }
  if ( !(_DWORD)lVal )
    return 0;
  v13 = this[7];
  if ( !*((_QWORD *)v13 + 43) )
    return 0;
  rgsabound.lLbound = 0;
  v14 = *((_QWORD *)v13 + 43);
  if ( lVal <= v14 )
    v14 = lVal;
  if ( v14 > CRequestData::GetRequestEntityLimit(v13) )
  {
    v8 = 104;
    goto LABEL_38;
  }
  rgsabound.cElements = v14;
  v15 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  a3->llVal = (LONGLONG)v15;
  if ( v15 )
  {
    if ( SafeArrayAccessData(v15, &ppvData) < 0 )
    {
      v10 = -2147418113;
      v8 = 101;
      goto LABEL_39;
    }
    v16 = this[7];
    if ( !*((_DWORD *)v16 + 81) )
    {
      *((_DWORD *)v16 + 81) = 1;
      *((_DWORD *)this[7] + 80) &= ~1u;
    }
    v17 = this[7];
    v18 = *((_QWORD *)v17 + 42);
    if ( v14 > v18 )
    {
      if ( v18 )
      {
        memcpy_0(ppvData, *((const void **)v17 + 41), v18);
        a2->lVal = *((_DWORD *)this[7] + 84);
        v19 = this[7];
        v20 = *((_QWORD *)v19 + 42);
        *((_QWORD *)v19 + 43) -= v20;
        v14 -= v20;
        v17 = this[7];
        ppvData = (char *)ppvData + *((_QWORD *)v17 + 42);
      }
      *((_QWORD *)v17 + 41) = 0;
      *((_QWORD *)this[7] + 42) = 0;
      if ( v14 )
      {
        while ( 1 )
        {
          v21 = this[7];
          v23 = v14;
          if ( !(*(unsigned int (__fastcall **)(_QWORD, void *, unsigned __int64 *))(*(_QWORD *)(*((_QWORD *)v21 + 6)
                                                                                               + 8LL)
                                                                                   + 176LL))(
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 6) + 8LL) + 8LL),
                  ppvData,
                  &v23) )
            break;
          v22 = v23;
          if ( !v23 )
            break;
          a2->lVal += v23;
          ppvData = (char *)ppvData + v22;
          *((_QWORD *)this[7] + 43) -= v22;
          v14 -= v23;
          if ( !v14 )
            goto LABEL_28;
        }
        SafeArrayUnaccessData(a3->parray);
        v8 = 101;
        goto LABEL_38;
      }
    }
    else
    {
      memcpy_0(ppvData, *((const void **)v17 + 41), v14);
      *((_QWORD *)this[7] + 41) += v14;
      *((_QWORD *)this[7] + 42) -= v14;
      *((_QWORD *)this[7] + 43) -= v14;
      a2->lVal = v14;
    }
LABEL_28:
    SafeArrayUnaccessData(a3->parray);
    return 0;
  }
  v10 = -2147024882;
  v8 = 100;
LABEL_39:
  v11 = &IID_IRequestDictionary;
LABEL_40:
  ExceptionId(v11, 0x1964u, v8, 0);
  VariantClear(a3);
  return v10;
}

```

## disassembly

```asm
0x18004aa50  mov     [rsp-18h+arg_0], rbx
0x18004aa55  mov     [rsp-18h+arg_8], rsi
0x18004aa5a  push    rbp
0x18004aa5b  push    rdi
0x18004aa5c  push    r14
0x18004aa5e  mov     rbp, rsp
0x18004aa61  sub     rsp, 50h
0x18004aa65  mov     r14, r8
0x18004aa68  mov     rsi, rdx
0x18004aa6b  mov     rdi, rcx
0x18004aa6e  call    ?CheckForTombstone@CRequest@@QEAAJXZ; CRequest::CheckForTombstone(void)
0x18004aa73  test    eax, eax
0x18004aa75  jns     short loc_18004AA81
0x18004aa77  mov     eax, 80004005h
0x18004aa7c  jmp     loc_18004AC3E
0x18004aa81  mov     word ptr [r14], 2011h
0x18004aa87  mov     qword ptr [r14+8], 0
0x18004aa8f  mov     r8, [rdi+38h]
0x18004aa93  mov     [rbp+var_20], 0
0x18004aa9b  mov     [rbp+ppvData], 0
0x18004aaa3  cmp     dword ptr [r8+144h], 2
0x18004aaab  jnz     short loc_18004AAB8
0x18004aaad  mov     r8d, 1965h
0x18004aab3  jmp     loc_18004AD1C
0x18004aab8  mov     r8, [r8+38h]
0x18004aabc  xor     r9d, r9d; wFlags
0x18004aabf  mov     rdx, rsi; pvarSrc
0x18004aac2  mov     [rsp+50h+vt], 3; vt
0x18004aac9  mov     rcx, rsi; pvargDest
0x18004aacc  mov     r8d, [r8+0A8h]; lcid
0x18004aad3  call    cs:__imp_VariantChangeTypeEx
0x18004aad9  mov     ebx, eax
0x18004aadb  test    eax, eax
0x18004aadd  jns     short loc_18004AB1E
0x18004aadf  cmp     eax, 80020005h
0x18004aae4  jz      short loc_18004AB0C
0x18004aae6  cmp     eax, 8002000Ah
0x18004aaeb  jz      short loc_18004AAFF
0x18004aaed  xor     r8d, r8d
0x18004aaf0  cmp     eax, 8007000Eh
0x18004aaf5  setnz   r8b
0x18004aaf9  add     r8d, 64h ; 'd'
0x18004aafd  jmp     short loc_18004AB12
0x18004aaff  mov     ebx, 80004005h
0x18004ab04  mov     r8d, 177Ah
0x18004ab0a  jmp     short loc_18004AB12
0x18004ab0c  mov     r8d, 6Ah ; 'j'
0x18004ab12  lea     rcx, IID_IResponse
0x18004ab19  jmp     loc_18004AD28
0x18004ab1e  movsxd  rax, dword ptr [rsi+8]
0x18004ab22  mov     dword ptr [rsi+8], 0
0x18004ab29  test    eax, eax
0x18004ab2b  jns     short loc_18004AB38
0x18004ab2d  mov     r8d, 1969h
0x18004ab33  jmp     loc_18004AD1C
0x18004ab38  jz      loc_18004AC3C
0x18004ab3e  mov     rcx, [rdi+38h]; this
0x18004ab42  cmp     qword ptr [rcx+158h], 0
0x18004ab4a  jz      loc_18004AC3C
0x18004ab50  mov     [rbp+rgsabound.lLbound], 0
0x18004ab57  mov     rbx, [rcx+158h]
0x18004ab5e  cmp     rax, rbx
0x18004ab61  cmovbe  rbx, rax
0x18004ab65  call    ?GetRequestEntityLimit@CRequestData@@QEAAKXZ; CRequestData::GetRequestEntityLimit(void)
0x18004ab6a  mov     ecx, eax
0x18004ab6c  cmp     rbx, rcx
0x18004ab6f  jbe     short loc_18004AB7C
0x18004ab71  mov     r8d, 68h ; 'h'
0x18004ab77  jmp     loc_18004AD1C
0x18004ab7c  mov     ecx, 11h; vt
0x18004ab81  mov     [rbp+rgsabound.cElements], ebx
0x18004ab84  lea     r8, [rbp+rgsabound]; rgsabound
0x18004ab88  lea     edx, [rcx-10h]; cDims
0x18004ab8b  call    cs:__imp_SafeArrayCreate
0x18004ab91  mov     [r14+8], rax
0x18004ab95  test    rax, rax
0x18004ab98  jnz     short loc_18004ABA8
0x18004ab9a  mov     ebx, 8007000Eh
0x18004ab9f  lea     r8d, [rax+64h]
0x18004aba3  jmp     loc_18004AD21
0x18004aba8  lea     rdx, [rbp+ppvData]; ppvData
0x18004abac  mov     rcx, rax; psa
0x18004abaf  call    cs:__imp_SafeArrayAccessData
0x18004abb5  test    eax, eax
0x18004abb7  jns     short loc_18004ABC9
0x18004abb9  mov     ebx, 8000FFFFh
0x18004abbe  mov     r8d, 65h ; 'e'
0x18004abc4  jmp     loc_18004AD21
0x18004abc9  mov     rax, [rdi+38h]
0x18004abcd  cmp     dword ptr [rax+144h], 0
0x18004abd4  jnz     short loc_18004ABEB
0x18004abd6  mov     dword ptr [rax+144h], 1
0x18004abe0  mov     rax, [rdi+38h]
0x18004abe4  and     dword ptr [rax+140h], 0FFFFFFFEh
0x18004abeb  mov     rcx, [rdi+38h]
0x18004abef  mov     r8, [rcx+150h]; Size
0x18004abf6  cmp     rbx, r8
0x18004abf9  ja      short loc_18004AC51
0x18004abfb  mov     rdx, [rcx+148h]; Src
0x18004ac02  mov     r8, rbx; Size
0x18004ac05  mov     rcx, [rbp+ppvData]; void *
0x18004ac09  call    memcpy_0
0x18004ac0e  mov     rax, [rdi+38h]
0x18004ac12  add     [rax+148h], rbx
0x18004ac19  mov     rax, [rdi+38h]
0x18004ac1d  sub     [rax+150h], rbx
0x18004ac24  mov     rax, [rdi+38h]
0x18004ac28  sub     [rax+158h], rbx
0x18004ac2f  mov     [rsi+8], ebx
0x18004ac32  mov     rcx, [r14+8]; psa
0x18004ac36  call    cs:__imp_SafeArrayUnaccessData
0x18004ac3c  xor     eax, eax
0x18004ac3e  mov     rbx, [rsp+50h+arg_0]
0x18004ac43  mov     rsi, [rsp+50h+arg_8]
0x18004ac48  add     rsp, 50h
0x18004ac4c  pop     r14
0x18004ac4e  pop     rdi
0x18004ac4f  pop     rbp
0x18004ac50  retn
0x18004ac51  test    r8, r8
0x18004ac54  jz      short loc_18004AC97
0x18004ac56  mov     rdx, [rcx+148h]; Src
0x18004ac5d  mov     rcx, [rbp+ppvData]; void *
0x18004ac61  call    memcpy_0
0x18004ac66  mov     rax, [rdi+38h]
0x18004ac6a  mov     ecx, [rax+150h]
0x18004ac70  mov     [rsi+8], ecx
0x18004ac73  mov     rcx, [rdi+38h]
0x18004ac77  mov     rax, [rcx+150h]
0x18004ac7e  sub     [rcx+158h], rax
0x18004ac85  sub     rbx, rax
0x18004ac88  mov     rcx, [rdi+38h]
0x18004ac8c  mov     rax, [rcx+150h]
0x18004ac93  add     [rbp+ppvData], rax
0x18004ac97  mov     qword ptr [rcx+148h], 0
0x18004aca2  mov     rax, [rdi+38h]
0x18004aca6  mov     qword ptr [rax+150h], 0
0x18004acb1  test    rbx, rbx
0x18004acb4  jz      loc_18004AC32
0x18004acba  mov     rax, [rdi+38h]
0x18004acbe  lea     r8, [rbp+var_20]
0x18004acc2  mov     rdx, [rbp+ppvData]
0x18004acc6  mov     [rbp+var_20], rbx
0x18004acca  mov     rcx, [rax+30h]
0x18004acce  mov     rcx, [rcx+8]
0x18004acd2  mov     rax, [rcx+0B0h]
0x18004acd9  mov     rcx, [rcx+8]
0x18004acdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ace2  test    eax, eax
0x18004ace4  jz      short loc_18004AD0C
0x18004ace6  mov     rcx, [rbp+var_20]
0x18004acea  test    rcx, rcx
0x18004aced  jz      short loc_18004AD0C
0x18004acef  add     [rsi+8], ecx
0x18004acf2  add     [rbp+ppvData], rcx
0x18004acf6  mov     rax, [rdi+38h]
0x18004acfa  sub     [rax+158h], rcx
0x18004ad01  sub     rbx, [rbp+var_20]
0x18004ad05  jnz     short loc_18004ACBA
0x18004ad07  jmp     loc_18004AC32
0x18004ad0c  mov     rcx, [r14+8]; psa
0x18004ad10  call    cs:__imp_SafeArrayUnaccessData
0x18004ad16  mov     r8d, 65h ; 'e'; unsigned int
0x18004ad1c  mov     ebx, 80004005h
0x18004ad21  lea     rcx, IID_IRequestDictionary; struct _GUID *
0x18004ad28  xor     r9d, r9d; int
0x18004ad2b  mov     edx, 1964h; unsigned int
0x18004ad30  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x18004ad35  mov     rcx, r14; pvarg
0x18004ad38  call    cs:__imp_VariantClear
0x18004ad3e  mov     eax, ebx
0x18004ad40  jmp     loc_18004AC3E
```
