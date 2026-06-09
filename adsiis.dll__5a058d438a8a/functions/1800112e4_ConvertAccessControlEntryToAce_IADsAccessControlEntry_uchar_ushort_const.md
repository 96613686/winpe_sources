# ConvertAccessControlEntryToAce(IADsAccessControlEntry *,uchar * *,ushort const *)

- ea: `0x1800112e4`
- end: `0x180011628`
- name: `?ConvertAccessControlEntryToAce@@YAJPEAUIADsAccessControlEntry@@PEAPEAEPEBG@Z`
- size: `836`
- prototype: `int(struct IADsAccessControlEntry *, unsigned __int8 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011630`

## callees

- `0x1800112e4`
- `0x180011b9c`
- `0x18001d652`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800114a3`
- `ole32!CLSIDFromString` at `0x1800114db`
- `ole32!CLSIDFromString` at `0x1800114a3`
- `ole32!CLSIDFromString` at `0x1800114db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800115eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800115eb`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800114f0`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011556`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001158d`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800114f0`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011556`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001158d`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800115f9`
- `ACTIVEDS!__imp_FreeADsMem` at `0x1800115f9`

## pseudocode

```c
__int64 __fastcall ConvertAccessControlEntryToAce(
        struct IADsAccessControlEntry *a1,
        unsigned __int8 **a2,
        const unsigned __int16 *a3)
{
  void *v4; // r14
  struct IADsAccessControlEntryVtbl *lpVtbl; // rax
  HRESULT v8; // ebx
  size_t v9; // r13
  unsigned __int8 *v10; // rdi
  int v11; // r15d
  int v12; // eax
  int v13; // edi
  __int16 v14; // si
  char *v15; // rax
  CLSID *v16; // rcx
  char v17; // al
  DWORD v18; // r15d
  char *v19; // rax
  DWORD v20; // r15d
  char *v21; // rax
  int v23; // [rsp+20h] [rbp-60h] BYREF
  int v24; // [rsp+24h] [rbp-5Ch] BYREF
  int v25; // [rsp+28h] [rbp-58h] BYREF
  int v26; // [rsp+2Ch] [rbp-54h] BYREF
  size_t Size; // [rsp+30h] [rbp-50h] BYREF
  void *Src; // [rsp+38h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
  LPCOLESTR lpsz; // [rsp+48h] [rbp-38h] BYREF
  LPCOLESTR v31; // [rsp+50h] [rbp-30h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-28h] BYREF
  CLSID v33; // [rsp+68h] [rbp-18h] BYREF

  v23 = 0;
  bstrString = 0;
  v4 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v24 = 0;
  v25 = 0;
  lpsz = 0;
  v31 = 0;
  v26 = 0;
  lpVtbl = a1->lpVtbl;
  pclsid = 0;
  v33 = 0;
  v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, int *))lpVtbl->get_AceType)(a1, &v23);
  if ( v8 < 0 )
    goto LABEL_40;
  v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, BSTR *))a1->lpVtbl->get_Trustee)(a1, &bstrString);
  if ( v8 < 0 )
    goto LABEL_40;
  v8 = ConvertTrusteeToSid(bstrString, &Src, (unsigned int *)&Size, a3);
  if ( v8 < 0
    || (v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, int *))a1->lpVtbl->get_AceFlags)(a1, &v24), v8 < 0)
    || (v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, int *))a1->lpVtbl->get_AccessMask)(a1, &v25),
        v8 < 0) )
  {
    v4 = Src;
    goto LABEL_40;
  }
  v9 = (unsigned int)Size;
  v10 = 0;
  v4 = Src;
  v11 = Size - 4;
  switch ( v23 )
  {
    case 0:
      v20 = v11 + 12;
      if ( v20 > 0xFFFF )
      {
        v8 = -2147024362;
        goto LABEL_40;
      }
      goto LABEL_33;
    case 1:
    case 2:
    case 3:
      v20 = v11 + 12;
LABEL_33:
      v21 = (char *)AllocADsMem(v20);
      v10 = (unsigned __int8 *)v21;
      if ( !v21 )
        goto LABEL_25;
      v16 = (CLSID *)(v21 + 8);
      *v21 = v23;
      v21[1] = v24;
      *((_WORD *)v21 + 1) = v20;
      *((_DWORD *)v21 + 1) = v25;
LABEL_35:
      memcpy_0(v16, v4, v9);
LABEL_36:
      *a2 = v10;
      goto LABEL_40;
    case 4:
      v18 = v11 + 16;
      v19 = (char *)AllocADsMem(v18);
      v10 = (unsigned __int8 *)v19;
      if ( !v19 )
        goto LABEL_25;
      v16 = (CLSID *)(v19 + 12);
      *v19 = v23;
      v19[1] = v24;
      *((_WORD *)v19 + 1) = v18;
      *((_DWORD *)v19 + 1) = v25;
      *((_WORD *)v19 + 4) = 0;
      goto LABEL_35;
  }
  if ( v23 != 5 && v23 != 6 && (unsigned int)(v23 - 7) > 1 )
    goto LABEL_36;
  v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, int *))a1->lpVtbl->get_AceFlags)(a1, &v24);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, int *))a1->lpVtbl->get_Flags)(a1, &v26);
    if ( v8 >= 0 )
    {
      v12 = v11 + 16;
      if ( (v26 & 1) == 0 )
        v12 = v11;
      v13 = v12 + 16;
      if ( (v26 & 2) == 0 )
        v13 = v12;
      v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, LPCOLESTR *))a1->lpVtbl->get_ObjectType)(a1, &lpsz);
      if ( v8 >= 0 )
      {
        v8 = CLSIDFromString(lpsz, &pclsid);
        if ( v8 >= 0 )
        {
          v8 = ((__int64 (__fastcall *)(struct IADsAccessControlEntry *, LPCOLESTR *))a1->lpVtbl->get_InheritedObjectType)(
                 a1,
                 &v31);
          if ( v8 >= 0 )
          {
            v8 = CLSIDFromString(v31, &v33);
            if ( v8 >= 0 )
            {
              v14 = v13 + 48;
              v15 = (char *)AllocADsMem(v13 + 48);
              v10 = (unsigned __int8 *)v15;
              if ( !v15 )
              {
LABEL_25:
                v8 = -2147024882;
                goto LABEL_40;
              }
              v16 = (CLSID *)(v15 + 12);
              *v15 = v23;
              v15[1] = v24;
              *((_WORD *)v15 + 1) = v14;
              *((_DWORD *)v15 + 1) = v25;
              *((_DWORD *)v15 + 2) = v26;
              v17 = v26;
              if ( (v26 & 1) != 0 )
              {
                *v16 = pclsid;
                v17 = v26;
                v16 = (CLSID *)(v10 + 28);
              }
              if ( (v17 & 2) != 0 )
                *v16++ = v33;
              goto LABEL_35;
            }
          }
        }
      }
    }
  }
LABEL_40:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v4 )
    FreeADsMem(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800112e4  mov     [rsp-38h+arg_18], rbx
0x1800112e9  push    rbp
0x1800112ea  push    rsi
0x1800112eb  push    rdi
0x1800112ec  push    r12
0x1800112ee  push    r13
0x1800112f0  push    r14
0x1800112f2  push    r15
0x1800112f4  mov     rbp, rsp
0x1800112f7  sub     rsp, 80h
0x1800112fe  mov     rax, cs:__security_cookie
0x180011305  xor     rax, rsp
0x180011308  mov     [rbp+var_8], rax
0x18001130c  xor     eax, eax
0x18001130e  mov     r12, rdx
0x180011311  mov     [rbp+var_60], eax
0x180011314  lea     rdx, [rbp+var_60]
0x180011318  mov     [rbp+bstrString], rax
0x18001131c  mov     r14d, eax
0x18001131f  mov     [rbp+Src], rax
0x180011323  xorps   xmm0, xmm0
0x180011326  mov     dword ptr [rbp+Size], eax
0x180011329  xorps   xmm1, xmm1
0x18001132c  mov     [rbp+var_5C], eax
0x18001132f  mov     rdi, r8
0x180011332  mov     [rbp+var_58], eax
0x180011335  mov     rsi, rcx
0x180011338  mov     [rbp+lpsz], rax
0x18001133c  mov     [rbp+var_30], rax
0x180011340  mov     [rbp+var_54], eax
0x180011343  mov     rax, [rcx]
0x180011346  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18001134a  movups  xmmword ptr [rbp+var_18.Data1], xmm1
0x18001134e  mov     rax, [rax+48h]
0x180011352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011357  mov     ebx, eax
0x180011359  test    eax, eax
0x18001135b  js      loc_1800115E2
0x180011361  mov     rax, [rsi]
0x180011364  lea     rdx, [rbp+bstrString]
0x180011368  mov     rcx, rsi
0x18001136b  mov     rax, [rax+98h]
0x180011372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011377  mov     ebx, eax
0x180011379  test    eax, eax
0x18001137b  js      loc_1800115E2
0x180011381  mov     rcx, [rbp+bstrString]; lpAccountName
0x180011385  lea     r8, [rbp+Size]; unsigned int *
0x180011389  mov     r9, rdi; unsigned __int16 *
0x18001138c  lea     rdx, [rbp+Src]; void **
0x180011390  call    ?ConvertTrusteeToSid@@YAJPEAGPEAPEAXPEAKPEBG@Z; ConvertTrusteeToSid(ushort *,void * *,ulong *,ushort const *)
0x180011395  mov     ebx, eax
0x180011397  test    eax, eax
0x180011399  js      loc_1800115DE
0x18001139f  mov     rax, [rsi]
0x1800113a2  lea     rdx, [rbp+var_5C]
0x1800113a6  mov     rcx, rsi
0x1800113a9  mov     rax, [rax+58h]
0x1800113ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b2  mov     ebx, eax
0x1800113b4  test    eax, eax
0x1800113b6  js      loc_1800115DE
0x1800113bc  mov     rax, [rsi]
0x1800113bf  lea     rdx, [rbp+var_58]
0x1800113c3  mov     rcx, rsi
0x1800113c6  mov     rax, [rax+38h]
0x1800113ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113cf  mov     ebx, eax
0x1800113d1  test    eax, eax
0x1800113d3  js      loc_1800115DE
0x1800113d9  mov     r13d, dword ptr [rbp+Size]
0x1800113dd  xor     edi, edi
0x1800113df  mov     eax, [rbp+var_60]
0x1800113e2  mov     r14, [rbp+Src]
0x1800113e6  lea     r15d, [r13-4]
0x1800113ea  test    eax, eax
0x1800113ec  jz      loc_1800115CA
0x1800113f2  sub     eax, 1
0x1800113f5  jz      loc_180011586
0x1800113fb  sub     eax, 1
0x1800113fe  jz      loc_180011586
0x180011404  sub     eax, 1
0x180011407  jz      loc_180011586
0x18001140d  sub     eax, 1
0x180011410  jz      loc_18001154F
0x180011416  sub     eax, 1
0x180011419  jz      short loc_18001142E
0x18001141b  sub     eax, 1
0x18001141e  jz      short loc_18001142E
0x180011420  sub     eax, 1
0x180011423  jz      short loc_18001142E
0x180011425  cmp     eax, 1
0x180011428  jnz     loc_1800115C4
0x18001142e  mov     rax, [rsi]
0x180011431  lea     rdx, [rbp+var_5C]
0x180011435  mov     rcx, rsi
0x180011438  mov     rax, [rax+58h]
0x18001143c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011441  mov     ebx, eax
0x180011443  test    eax, eax
0x180011445  js      loc_1800115E2
0x18001144b  mov     rax, [rsi]
0x18001144e  lea     rdx, [rbp+var_54]
0x180011452  mov     rcx, rsi
0x180011455  mov     rax, [rax+68h]
0x180011459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145e  mov     ebx, eax
0x180011460  test    eax, eax
0x180011462  js      loc_1800115E2
0x180011468  test    byte ptr [rbp+var_54], 1
0x18001146c  lea     eax, [r15+10h]
0x180011470  lea     rdx, [rbp+lpsz]
0x180011474  mov     rcx, rsi
0x180011477  cmovz   eax, r15d
0x18001147b  test    byte ptr [rbp+var_54], 2
0x18001147f  lea     edi, [rax+10h]
0x180011482  cmovz   edi, eax
0x180011485  mov     rax, [rsi]
0x180011488  mov     rax, [rax+78h]
0x18001148c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011491  mov     ebx, eax
0x180011493  test    eax, eax
0x180011495  js      loc_1800115E2
0x18001149b  mov     rcx, [rbp+lpsz]; lpsz
0x18001149f  lea     rdx, [rbp+pclsid]; pclsid
0x1800114a3  call    cs:__imp_CLSIDFromString
0x1800114a9  mov     ebx, eax
0x1800114ab  test    eax, eax
0x1800114ad  js      loc_1800115E2
0x1800114b3  mov     rax, [rsi]
0x1800114b6  lea     rdx, [rbp+var_30]
0x1800114ba  mov     rcx, rsi
0x1800114bd  mov     rax, [rax+88h]
0x1800114c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114c9  mov     ebx, eax
0x1800114cb  test    eax, eax
0x1800114cd  js      loc_1800115E2
0x1800114d3  mov     rcx, [rbp+var_30]; lpsz
0x1800114d7  lea     rdx, [rbp+var_18]; pclsid
0x1800114db  call    cs:__imp_CLSIDFromString
0x1800114e1  mov     ebx, eax
0x1800114e3  test    eax, eax
0x1800114e5  js      loc_1800115E2
0x1800114eb  lea     esi, [rdi+30h]
0x1800114ee  mov     ecx, esi; cb
0x1800114f0  call    cs:__imp_AllocADsMem
0x1800114f6  mov     rdi, rax
0x1800114f9  test    rax, rax
0x1800114fc  jnz     short loc_180011508
0x1800114fe  mov     ebx, 8007000Eh
0x180011503  jmp     loc_1800115E2
0x180011508  mov     al, byte ptr [rbp+var_60]
0x18001150b  lea     rcx, [rdi+0Ch]
0x18001150f  mov     [rdi], al
0x180011511  mov     al, byte ptr [rbp+var_5C]
0x180011514  mov     [rdi+1], al
0x180011517  mov     [rdi+2], si
0x18001151b  mov     eax, [rbp+var_58]
0x18001151e  mov     [rdi+4], eax
0x180011521  mov     eax, [rbp+var_54]
0x180011524  mov     [rdi+8], eax
0x180011527  mov     eax, [rbp+var_54]
0x18001152a  test    al, 1
0x18001152c  jz      short loc_18001153D
0x18001152e  movups  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x180011532  movdqu  xmmword ptr [rcx], xmm0
0x180011536  mov     eax, [rbp+var_54]
0x180011539  add     rcx, 10h
0x18001153d  test    al, 2
0x18001153f  jz      short loc_1800115B9
0x180011541  movups  xmm0, xmmword ptr [rbp+var_18.Data1]
0x180011545  movdqu  xmmword ptr [rcx], xmm0
0x180011549  add     rcx, 10h
0x18001154d  jmp     short loc_1800115B9
0x18001154f  add     r15d, 10h
0x180011553  mov     ecx, r15d; cb
0x180011556  call    cs:__imp_AllocADsMem
0x18001155c  mov     rdi, rax
0x18001155f  test    rax, rax
0x180011562  jz      short loc_1800114FE
0x180011564  mov     al, byte ptr [rbp+var_60]
0x180011567  lea     rcx, [rdi+0Ch]
0x18001156b  mov     [rdi], al
0x18001156d  mov     al, byte ptr [rbp+var_5C]
0x180011570  mov     [rdi+1], al
0x180011573  mov     [rdi+2], r15w
0x180011578  mov     eax, [rbp+var_58]
0x18001157b  mov     [rdi+4], eax
0x18001157e  xor     eax, eax
0x180011580  mov     [rdi+8], ax
0x180011584  jmp     short loc_1800115B9
0x180011586  add     r15d, 0Ch
0x18001158a  mov     ecx, r15d; cb
0x18001158d  call    cs:__imp_AllocADsMem
0x180011593  mov     rdi, rax
0x180011596  test    rax, rax
0x180011599  jz      loc_1800114FE
0x18001159f  mov     al, byte ptr [rbp+var_60]
0x1800115a2  lea     rcx, [rdi+8]; void *
0x1800115a6  mov     [rdi], al
0x1800115a8  mov     al, byte ptr [rbp+var_5C]
0x1800115ab  mov     [rdi+1], al
0x1800115ae  mov     [rdi+2], r15w
0x1800115b3  mov     eax, [rbp+var_58]
0x1800115b6  mov     [rdi+4], eax
0x1800115b9  mov     r8, r13; Size
0x1800115bc  mov     rdx, r14; Src
0x1800115bf  call    memcpy_0
0x1800115c4  mov     [r12], rdi
0x1800115c8  jmp     short loc_1800115E2
0x1800115ca  add     r15d, 0Ch
0x1800115ce  cmp     r15d, 0FFFFh
0x1800115d5  jbe     short loc_18001158A
0x1800115d7  mov     ebx, 80070216h
0x1800115dc  jmp     short loc_1800115E2
0x1800115de  mov     r14, [rbp+Src]
0x1800115e2  mov     rcx, [rbp+bstrString]; bstrString
0x1800115e6  test    rcx, rcx
0x1800115e9  jz      short loc_1800115F1
0x1800115eb  call    cs:__imp_SysFreeString
0x1800115f1  test    r14, r14
0x1800115f4  jz      short loc_1800115FF
0x1800115f6  mov     rcx, r14; pMem
0x1800115f9  call    cs:__imp_FreeADsMem
0x1800115ff  mov     eax, ebx
0x180011601  mov     rcx, [rbp+var_8]
0x180011605  xor     rcx, rsp; StackCookie
0x180011608  call    __security_check_cookie
0x18001160d  mov     rbx, [rsp+80h+arg_18]
0x180011615  add     rsp, 80h
0x18001161c  pop     r15
0x18001161e  pop     r14
0x180011620  pop     r13
0x180011622  pop     r12
0x180011624  pop     rdi
0x180011625  pop     rsi
0x180011626  pop     rbp
0x180011627  retn
```
