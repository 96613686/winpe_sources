# operator>>(CArchive &,COleVariant &)

- ea: `0x18008c1e0`
- end: `0x18008c496`
- name: `??5@YAAEAVCArchive@@AEAV0@AEAVCOleVariant@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(CArchive *this, VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008b940`

## callees

- `0x180024fc0`
- `0x18002d800`
- `0x180031340`
- `0x180036a10`
- `0x180036a60`
- `0x180036ab0`
- `0x180036b00`
- `0x18008c1e0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c384`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c3ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c384`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c3ac`
- `OLEAUT32!__imp_VariantClear` at `0x18008c217`
- `OLEAUT32!__imp_VariantClear` at `0x18008c217`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18008c448`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18008c448`

## pseudocode

```c
CArchive *__fastcall operator>>(CArchive *this, VARIANTARG *pvarg)
{
  unsigned int vt; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v10; // rdx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  GUID *v18; // r14
  GUID *v19; // r9
  HRESULT v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // esi
  BSTR v24; // rax
  UINT len[2]; // [rsp+30h] [rbp-68h] BYREF
  VARIANTARG *v26; // [rsp+38h] [rbp-60h]
  _QWORD v27[2]; // [rsp+40h] [rbp-58h] BYREF
  IID rclsid; // [rsp+50h] [rbp-48h] BYREF
  __int64 v29; // [rsp+60h] [rbp-38h] BYREF

  v26 = pvarg;
  if ( pvarg->vt )
    VariantClear(pvarg);
  CArchive::operator>>(this, pvarg);
  if ( (pvarg->vt & 0x6000) == 0 )
  {
    vt = pvarg->vt;
    if ( vt > 7 )
    {
      v12 = vt - 8;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( !v14 )
            goto LABEL_16;
          v15 = v14 - 1;
          if ( !v15 )
            return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
          v16 = v15 - 2;
          if ( v16 )
          {
            if ( v16 == 4 )
              return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
            return this;
          }
        }
        *(_QWORD *)len = 0;
        v27[0] = &CArchiveStream::`vftable';
        v27[1] = this;
        rclsid = 0;
        CArchive::operator>>(this, &rclsid);
        CArchive::operator>>(this, &rclsid.Data2);
        CArchive::operator>>(this, &rclsid.Data3);
        CArchive::Read(this, rclsid.Data4, 8u);
        p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
        v18 = &IID_IUnknown;
        v19 = &IID_IUnknown;
        if ( pvarg->vt != 13 )
          v19 = &IID_IDispatch;
        v20 = CoCreateInstance(&rclsid, 0, 0x17u, v19, &pvarg->byref);
        if ( v20 == -2147024809 )
        {
          if ( pvarg->vt != 13 )
            v18 = &IID_IDispatch;
          v20 = CoCreateInstance(&rclsid, 0, 7u, v18, &pvarg->byref);
        }
        AfxCheckError(v20);
        try
        {
          v21 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, UINT *))p_llVal->llVal)(
                  p_llVal->llVal,
                  &IID_IPersistStream,
                  len);
          if ( v21 < 0 )
            v21 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, UINT *))p_llVal->llVal)(
                    p_llVal->llVal,
                    &IID_IPersistStreamInit,
                    len);
          AfxCheckError(v21);
          v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)len + 40LL))(*(_QWORD *)len, v27);
          AfxCheckError(v22);
        }
        catch ( CException *v29 )
        {
          if ( *(_QWORD *)len )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)len + 16LL))(*(_QWORD *)len);
          (*(void (__fastcall **)(LONGLONG))(*v26->pllVal + 16))(v26->llVal);
          throw;
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)len + 16LL))(*(_QWORD *)len);
      }
      else
      {
        len[0] = 0;
        CArchive::operator>>(this, len);
        v23 = len[0];
        if ( len[0] )
        {
          v24 = SysAllocStringByteLen(0, len[0]);
          pvarg->llVal = (LONGLONG)v24;
          if ( !v24 )
            AfxThrowMemoryException();
          CArchive::Read(this, v24, v23);
        }
        else
        {
          pvarg->llVal = 0;
        }
      }
    }
    else
    {
      if ( vt == 7 )
        return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
      if ( pvarg->vt )
      {
        v5 = vt - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( !v8 )
                return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
              v9 = v8 - 1;
              if ( v9 )
              {
                if ( v9 == 1 )
                {
                  CArchive::operator>>(this, &pvarg->decVal.Lo32);
                  v10 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)((char *)&pvarg->decVal.Lo64 + 4);
                  return (CArchive *)CArchive::operator>>(this, v10);
                }
                return this;
              }
              return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
            }
LABEL_16:
            v10 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg->llVal;
            return (CArchive *)CArchive::operator>>(this, v10);
          }
          return (CArchive *)CArchive::operator>>(this, &pvarg->decVal.Lo32);
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18008c1e0  mov     [rsp+arg_10], rbx
0x18008c1e5  push    rsi
0x18008c1e6  push    rdi
0x18008c1e7  push    r12
0x18008c1e9  push    r14
0x18008c1eb  push    r15
0x18008c1ed  sub     rsp, 70h
0x18008c1f1  mov     rax, cs:__security_cookie
0x18008c1f8  xor     rax, rsp
0x18008c1fb  mov     [rsp+98h+var_30], rax
0x18008c200  mov     rbx, rdx
0x18008c203  mov     rdi, rcx
0x18008c206  mov     [rsp+98h+var_60], rdx
0x18008c20b  xor     r15d, r15d
0x18008c20e  cmp     [rdx], r15w
0x18008c212  jz      short loc_18008C21D
0x18008c214  mov     rcx, rdx; pvarg
0x18008c217  call    cs:__imp_VariantClear
0x18008c21d  mov     rdx, rbx
0x18008c220  mov     rcx, rdi
0x18008c223  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x18008c228  mov     eax, 6000h
0x18008c22d  test    [rbx], ax
0x18008c230  jnz     loc_18008C46B
0x18008c236  movzx   edx, word ptr [rbx]
0x18008c239  cmp     edx, 7
0x18008c23c  ja      short loc_18008C2B7
0x18008c23e  jz      short loc_18008C284
0x18008c240  test    edx, edx
0x18008c242  jz      loc_18008C46B
0x18008c248  sub     edx, 1
0x18008c24b  jz      loc_18008C46B
0x18008c251  sub     edx, 1
0x18008c254  jz      loc_18008C2EE
0x18008c25a  sub     edx, 1
0x18008c25d  jz      short loc_18008C2A6
0x18008c25f  sub     edx, 1
0x18008c262  jz      short loc_18008C295
0x18008c264  sub     edx, 1
0x18008c267  jz      short loc_18008C284
0x18008c269  cmp     edx, 1
0x18008c26c  jnz     loc_18008C46B
0x18008c272  lea     rdx, [rbx+8]
0x18008c276  mov     rcx, rdi
0x18008c279  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x18008c27e  lea     rdx, [rbx+0Ch]
0x18008c282  jmp     short loc_18008C2AA
0x18008c284  lea     rdx, [rbx+8]
0x18008c288  mov     rcx, rdi
0x18008c28b  call    ??5CArchive@@QEAAAEAV0@AEAN@Z; CArchive::operator>>(double &)
0x18008c290  jmp     loc_18008C46E
0x18008c295  lea     rdx, [rbx+8]
0x18008c299  mov     rcx, rdi
0x18008c29c  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x18008c2a1  jmp     loc_18008C46E
0x18008c2a6  lea     rdx, [rbx+8]
0x18008c2aa  mov     rcx, rdi
0x18008c2ad  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x18008c2b2  jmp     loc_18008C46E
0x18008c2b7  sub     edx, 8
0x18008c2ba  jz      loc_18008C42A
0x18008c2c0  sub     edx, 1
0x18008c2c3  jz      short loc_18008C2FF
0x18008c2c5  sub     edx, 1
0x18008c2c8  jz      short loc_18008C2A6
0x18008c2ca  sub     edx, 1
0x18008c2cd  jz      short loc_18008C2EE
0x18008c2cf  sub     edx, 2
0x18008c2d2  jz      short loc_18008C2FF
0x18008c2d4  cmp     edx, 4
0x18008c2d7  jnz     loc_18008C46B
0x18008c2dd  lea     rdx, [rbx+8]
0x18008c2e1  mov     rcx, rdi
0x18008c2e4  call    ??5CArchive@@QEAAAEAV0@AEAE@Z; CArchive::operator>>(uchar &)
0x18008c2e9  jmp     loc_18008C46E
0x18008c2ee  lea     rdx, [rbx+8]
0x18008c2f2  mov     rcx, rdi
0x18008c2f5  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x18008c2fa  jmp     loc_18008C46E
0x18008c2ff  mov     qword ptr [rsp+98h+len], r15
0x18008c304  lea     rax, ??_7CArchiveStream@@6B@; const CArchiveStream::`vftable'
0x18008c30b  mov     [rsp+98h+var_58], rax
0x18008c310  mov     [rsp+98h+var_50], rdi
0x18008c315  xorps   xmm0, xmm0
0x18008c318  movups  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18008c31d  lea     rdx, [rsp+98h+rclsid]
0x18008c322  mov     rcx, rdi
0x18008c325  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x18008c32a  lea     rdx, [rsp+98h+rclsid.Data2]
0x18008c32f  mov     rcx, rdi
0x18008c332  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x18008c337  lea     rdx, [rsp+98h+rclsid.Data3]
0x18008c33c  mov     rcx, rdi
0x18008c33f  call    ??5CArchive@@QEAAAEAV0@AEAG@Z; CArchive::operator>>(ushort &)
0x18008c344  mov     r8d, 8; unsigned int
0x18008c34a  lea     rdx, [rsp+98h+rclsid.Data4]; void *
0x18008c34f  mov     rcx, rdi; this
0x18008c352  call    ?Read@CArchive@@QEAAIPEAXI@Z; CArchive::Read(void *,uint)
0x18008c357  lea     rsi, [rbx+8]
0x18008c35b  lea     r12, IID_IDispatch
0x18008c362  lea     r14, IID_IUnknown
0x18008c369  mov     r9, r14
0x18008c36c  cmp     word ptr [rbx], 0Dh
0x18008c370  cmovnz  r9, r12; riid
0x18008c374  mov     [rsp+98h+ppv], rsi; ppv
0x18008c379  xor     edx, edx; pUnkOuter
0x18008c37b  lea     r8d, [rdx+17h]; dwClsContext
0x18008c37f  lea     rcx, [rsp+98h+rclsid]; rclsid
0x18008c384  call    cs:__imp_CoCreateInstance
0x18008c38a  cmp     eax, 80070057h
0x18008c38f  jnz     short loc_18008C3B2
0x18008c391  cmp     word ptr [rbx], 0Dh
0x18008c395  cmovnz  r14, r12
0x18008c399  mov     [rsp+98h+ppv], rsi; ppv
0x18008c39e  mov     r9, r14; riid
0x18008c3a1  xor     edx, edx; pUnkOuter
0x18008c3a3  lea     r8d, [rdx+7]; dwClsContext
0x18008c3a7  lea     rcx, [rsp+98h+rclsid]; rclsid
0x18008c3ac  call    cs:__imp_CoCreateInstance
0x18008c3b2  mov     ecx, eax; int
0x18008c3b4  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008c3b9  nop
0x18008c3ba  mov     rcx, [rsi]
0x18008c3bd  mov     rax, [rcx]
0x18008c3c0  lea     r8, [rsp+98h+len]
0x18008c3c5  lea     rdx, IID_IPersistStream
0x18008c3cc  mov     rax, [rax]
0x18008c3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3d4  test    eax, eax
0x18008c3d6  jns     short loc_18008C3F2
0x18008c3d8  mov     rcx, [rsi]
0x18008c3db  mov     rax, [rcx]
0x18008c3de  lea     r8, [rsp+98h+len]
0x18008c3e3  lea     rdx, IID_IPersistStreamInit
0x18008c3ea  mov     rax, [rax]
0x18008c3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3f2  mov     ecx, eax; int
0x18008c3f4  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008c3f9  mov     rcx, qword ptr [rsp+98h+len]
0x18008c3fe  mov     rax, [rcx]
0x18008c401  lea     rdx, [rsp+98h+var_58]
0x18008c406  mov     rax, [rax+28h]
0x18008c40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c40f  mov     ecx, eax; int
0x18008c411  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18008c416  nop
0x18008c417  mov     rcx, qword ptr [rsp+98h+len]
0x18008c41c  mov     rax, [rcx]
0x18008c41f  mov     rax, [rax+10h]
0x18008c423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c428  jmp     short loc_18008C46B
0x18008c42a  mov     [rsp+98h+len], r15d
0x18008c42f  lea     rdx, [rsp+98h+len]
0x18008c434  mov     rcx, rdi
0x18008c437  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x18008c43c  mov     esi, [rsp+98h+len]
0x18008c440  test    esi, esi
0x18008c442  jz      short loc_18008C467
0x18008c444  mov     edx, esi; len
0x18008c446  xor     ecx, ecx; psz
0x18008c448  call    cs:__imp_SysAllocStringByteLen
0x18008c44e  mov     [rbx+8], rax
0x18008c452  test    rax, rax
0x18008c455  jz      short loc_18008C490
0x18008c457  mov     r8d, esi; unsigned int
0x18008c45a  mov     rdx, rax; void *
0x18008c45d  mov     rcx, rdi; this
0x18008c460  call    ?Read@CArchive@@QEAAIPEAXI@Z; CArchive::Read(void *,uint)
0x18008c465  jmp     short loc_18008C46B
0x18008c467  mov     [rbx+8], r15
0x18008c46b  mov     rax, rdi
0x18008c46e  mov     rcx, [rsp+98h+var_30]
0x18008c473  xor     rcx, rsp; StackCookie
0x18008c476  call    __security_check_cookie
0x18008c47b  mov     rbx, [rsp+98h+arg_10]
0x18008c483  add     rsp, 70h
0x18008c487  pop     r15
0x18008c489  pop     r14
0x18008c48b  pop     r12
0x18008c48d  pop     rdi
0x18008c48e  pop     rsi
0x18008c48f  retn
0x18008c490  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
```
