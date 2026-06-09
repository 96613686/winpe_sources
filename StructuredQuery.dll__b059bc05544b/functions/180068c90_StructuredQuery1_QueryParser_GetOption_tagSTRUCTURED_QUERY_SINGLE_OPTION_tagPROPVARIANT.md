# StructuredQuery1::QueryParser::GetOption(tagSTRUCTURED_QUERY_SINGLE_OPTION,tagPROPVARIANT *)

- ea: `0x180068c90`
- end: `0x180068f15`
- name: `?GetOption@QueryParser@StructuredQuery1@@UEAAJW4tagSTRUCTURED_QUERY_SINGLE_OPTION@@PEAUtagPROPVARIANT@@@Z`
- size: `645`
- prototype: `int(StructuredQuery1::QueryParser *__hidden this, enum tagSTRUCTURED_QUERY_SINGLE_OPTION, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180068c90`
- `0x180069128`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180068cbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180068cbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180068ef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180068ef3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180068dd1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180068dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068e44`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::GetOption(
        StructuredQuery1::QueryParser *this,
        int a2,
        PROPVARIANT *a3)
{
  RTL_SRWLOCK *v6; // r14
  int inited; // ebp
  __int16 v8; // ax
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  IUnknown *v12; // rcx
  HRESULT v13; // eax
  __int64 v14; // rcx
  LONG v15; // eax
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  _OWORD *v20; // rax
  _OWORD *v21; // rcx
  int v23; // [rsp+70h] [rbp+18h] BYREF
  __int64 v24; // [rsp+78h] [rbp+20h] BYREF

  if ( !a3 )
    return (unsigned int)-2147467261;
  v6 = (RTL_SRWLOCK *)((char *)this + 152);
  inited = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 19);
  HIBYTE(v8) = 0;
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  if ( a2 > 5 )
  {
    v16 = a2 - 6;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( !v18 )
        {
          if ( *((_QWORD *)this + 17) )
          {
            v20 = CoTaskMemAlloc(0xACu);
            if ( v20 )
            {
              v21 = (_OWORD *)*((_QWORD *)this + 17);
              *v20 = *v21;
              v20[1] = v21[1];
              v20[2] = v21[2];
              v20[3] = v21[3];
              v20[4] = v21[4];
              v20[5] = v21[5];
              v20[6] = v21[6];
              v20[7] = v21[7];
              v20[8] = v21[8];
              v20[9] = v21[9];
              *(_OWORD *)((char *)v20 + 156) = *(_OWORD *)((char *)v21 + 156);
              *(_WORD *)a3 = 65;
              *((_DWORD *)a3 + 2) = 172;
              a3[2] = v20;
            }
            else
            {
              inited = -2147024882;
            }
          }
          else
          {
            *(_WORD *)a3 = 1;
          }
          goto LABEL_35;
        }
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 != 1 )
            goto LABEL_24;
          *(_WORD *)a3 = 19;
          v15 = *((_DWORD *)this + 20);
        }
        else
        {
          *(_WORD *)a3 = 19;
          v15 = *((_DWORD *)this + 19);
        }
      }
      else
      {
        *(_WORD *)a3 = 19;
        v15 = *((_DWORD *)this + 18);
      }
    }
    else
    {
      *(_WORD *)a3 = 19;
      v15 = *((unsigned __int16 *)this + 24);
    }
LABEL_34:
    *((_DWORD *)a3 + 2) = v15;
    goto LABEL_35;
  }
  if ( a2 == 5 )
  {
    *(_WORD *)a3 = 3;
    v15 = *((_DWORD *)this + 22);
    goto LABEL_34;
  }
  if ( !a2 )
  {
    v13 = PropVariantCopy(a3, (const PROPVARIANT *)this + 3);
LABEL_17:
    inited = v13;
    goto LABEL_35;
  }
  v9 = a2 - 1;
  if ( !v9 )
  {
    *(_WORD *)a3 = 19;
    v15 = *((_DWORD *)this + 13);
    goto LABEL_34;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v12 = (IUnknown *)*((_QWORD *)this + 7);
    if ( !v12 )
    {
      v14 = *((_QWORD *)this + 8);
      v24 = 0;
      v23 = 0;
      inited = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, GUID *, __int64 *, int *))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 *((unsigned int *)this + 12),
                 0,
                 0,
                 &GUID_d53552c8_77e3_101a_b552_08002b33b0e6,
                 &v24,
                 &v23);
      if ( inited >= 0 )
      {
        inited = InitPropVariantFromUnknown(*((IUnknown **)this + 7), (struct tagPROPVARIANT *)a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      goto LABEL_35;
    }
    v13 = InitPropVariantFromUnknown(v12, (struct tagPROPVARIANT *)a3);
    goto LABEL_17;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    *(_WORD *)a3 = 11;
    LOBYTE(v8) = *((_DWORD *)this + 18) != 2;
    *((_WORD *)a3 + 4) = v8 - 1;
    goto LABEL_35;
  }
  if ( v11 != 1 )
  {
LABEL_24:
    inited = -2147024809;
    goto LABEL_35;
  }
  *(_WORD *)a3 = 11;
  *((_WORD *)a3 + 4) = -(*((_BYTE *)this + 84) != 0);
LABEL_35:
  ReleaseSRWLockShared(v6);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180068c90  mov     [rsp+arg_0], rbx
0x180068c95  mov     [rsp+arg_8], rbp
0x180068c9a  push    rsi
0x180068c9b  push    rdi
0x180068c9c  push    r14
0x180068c9e  sub     rsp, 40h
0x180068ca2  mov     rdi, r8
0x180068ca5  mov     ebx, edx
0x180068ca7  mov     rsi, rcx
0x180068caa  test    r8, r8
0x180068cad  jz      loc_180068EFB
0x180068cb3  lea     r14, [rcx+98h]
0x180068cba  xor     ebp, ebp
0x180068cbc  mov     rcx, r14; SRWLock
0x180068cbf  call    cs:__imp_AcquireSRWLockShared
0x180068cc5  xor     eax, eax
0x180068cc7  xorps   xmm0, xmm0
0x180068cca  movups  xmmword ptr [rdi], xmm0
0x180068ccd  mov     [rdi+10h], rax
0x180068cd1  cmp     ebx, 5
0x180068cd4  jg      loc_180068DEB
0x180068cda  jz      loc_180068DDE
0x180068ce0  test    ebx, ebx
0x180068ce2  jz      loc_180068DCA
0x180068ce8  sub     ebx, 1
0x180068ceb  jz      loc_180068DBD
0x180068cf1  sub     ebx, 1
0x180068cf4  jz      short loc_180068D37
0x180068cf6  sub     ebx, 1
0x180068cf9  jz      short loc_180068D1A
0x180068cfb  cmp     ebx, 1
0x180068cfe  jnz     loc_180068E0C
0x180068d04  mov     word ptr [rdi], 0Bh
0x180068d09  mov     al, [rsi+54h]
0x180068d0c  neg     al
0x180068d0e  sbb     cx, cx
0x180068d11  mov     [rdi+8], cx
0x180068d15  jmp     loc_180068EF0
0x180068d1a  mov     word ptr [rdi], 0Bh
0x180068d1f  mov     ecx, 1
0x180068d24  cmp     dword ptr [rsi+48h], 2
0x180068d28  setnz   al
0x180068d2b  sub     ax, cx
0x180068d2e  mov     [rdi+8], ax
0x180068d32  jmp     loc_180068EF0
0x180068d37  mov     rcx, [rsi+38h]; punk
0x180068d3b  test    rcx, rcx
0x180068d3e  jz      short loc_180068D4D
0x180068d40  mov     rdx, rdi; struct tagPROPVARIANT *
0x180068d43  call    ?InitPropVariantFromUnknown@@YAJPEAUIUnknown@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromUnknown(IUnknown *,tagPROPVARIANT *)
0x180068d48  jmp     loc_180068DD7
0x180068d4d  mov     rcx, [rsi+40h]
0x180068d51  lea     rdx, [rsp+58h+arg_10]
0x180068d56  mov     [rsp+58h+var_28], rdx
0x180068d5b  xor     r9d, r9d
0x180068d5e  mov     [rsp+58h+arg_18], rax
0x180068d63  lea     rdx, [rsp+58h+arg_18]
0x180068d68  mov     [rsp+58h+var_30], rdx
0x180068d6d  xor     r8d, r8d
0x180068d70  mov     [rsp+58h+arg_10], eax
0x180068d74  lea     rdx, _GUID_d53552c8_77e3_101a_b552_08002b33b0e6
0x180068d7b  mov     rax, [rcx]
0x180068d7e  mov     [rsp+58h+var_38], rdx
0x180068d83  mov     edx, [rsi+30h]
0x180068d86  mov     rax, [rax+18h]
0x180068d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d8f  mov     ebp, eax
0x180068d91  test    eax, eax
0x180068d93  js      loc_180068EF0
0x180068d99  mov     rcx, [rsi+38h]; punk
0x180068d9d  mov     rdx, rdi; struct tagPROPVARIANT *
0x180068da0  call    ?InitPropVariantFromUnknown@@YAJPEAUIUnknown@@PEAUtagPROPVARIANT@@@Z; InitPropVariantFromUnknown(IUnknown *,tagPROPVARIANT *)
0x180068da5  mov     rcx, [rsp+58h+arg_18]
0x180068daa  mov     ebp, eax
0x180068dac  mov     rax, [rcx]
0x180068daf  mov     rax, [rax+10h]
0x180068db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068db8  jmp     loc_180068EF0
0x180068dbd  mov     word ptr [rdi], 13h
0x180068dc2  mov     eax, [rsi+34h]
0x180068dc5  jmp     loc_180068EED
0x180068dca  lea     rdx, [rsi+18h]; pvarSrc
0x180068dce  mov     rcx, rdi; pvarDest
0x180068dd1  call    cs:__imp_PropVariantCopy
0x180068dd7  mov     ebp, eax
0x180068dd9  jmp     loc_180068EF0
0x180068dde  mov     word ptr [rdi], 3
0x180068de3  mov     eax, [rsi+58h]
0x180068de6  jmp     loc_180068EED
0x180068deb  sub     ebx, 6
0x180068dee  jz      loc_180068EE4
0x180068df4  sub     ebx, 1
0x180068df7  jz      loc_180068EDA
0x180068dfd  sub     ebx, 1
0x180068e00  jz      short loc_180068E30
0x180068e02  sub     ebx, 1
0x180068e05  jz      short loc_180068E23
0x180068e07  cmp     ebx, 1
0x180068e0a  jz      short loc_180068E16
0x180068e0c  mov     ebp, 80070057h
0x180068e11  jmp     loc_180068EF0
0x180068e16  mov     word ptr [rdi], 13h
0x180068e1b  mov     eax, [rsi+50h]
0x180068e1e  jmp     loc_180068EED
0x180068e23  mov     word ptr [rdi], 13h
0x180068e28  mov     eax, [rsi+4Ch]
0x180068e2b  jmp     loc_180068EED
0x180068e30  cmp     [rsi+88h], rax
0x180068e37  jz      loc_180068ED3
0x180068e3d  mov     ebx, 0ACh
0x180068e42  mov     ecx, ebx; cb
0x180068e44  call    cs:__imp_CoTaskMemAlloc
0x180068e4a  test    rax, rax
0x180068e4d  jz      short loc_180068ECC
0x180068e4f  mov     rcx, [rsi+88h]
0x180068e56  movups  xmm0, xmmword ptr [rcx]
0x180068e59  movups  xmmword ptr [rax], xmm0
0x180068e5c  movups  xmm1, xmmword ptr [rcx+10h]
0x180068e60  movups  xmmword ptr [rax+10h], xmm1
0x180068e64  movups  xmm0, xmmword ptr [rcx+20h]
0x180068e68  movups  xmmword ptr [rax+20h], xmm0
0x180068e6c  movups  xmm1, xmmword ptr [rcx+30h]
0x180068e70  movups  xmmword ptr [rax+30h], xmm1
0x180068e74  movups  xmm0, xmmword ptr [rcx+40h]
0x180068e78  movups  xmmword ptr [rax+40h], xmm0
0x180068e7c  movups  xmm1, xmmword ptr [rcx+50h]
0x180068e80  movups  xmmword ptr [rax+50h], xmm1
0x180068e84  movups  xmm0, xmmword ptr [rcx+60h]
0x180068e88  movups  xmmword ptr [rax+60h], xmm0
0x180068e8c  movups  xmm1, xmmword ptr [rcx+70h]
0x180068e90  movups  xmmword ptr [rax+70h], xmm1
0x180068e94  movups  xmm0, xmmword ptr [rcx+80h]
0x180068e9b  movups  xmmword ptr [rax+80h], xmm0
0x180068ea2  movups  xmm1, xmmword ptr [rcx+90h]
0x180068ea9  movups  xmmword ptr [rax+90h], xmm1
0x180068eb0  movups  xmm0, xmmword ptr [rcx+9Ch]
0x180068eb7  movups  xmmword ptr [rax+9Ch], xmm0
0x180068ebe  mov     word ptr [rdi], 41h ; 'A'
0x180068ec3  mov     [rdi+8], ebx
0x180068ec6  mov     [rdi+10h], rax
0x180068eca  jmp     short loc_180068EF0
0x180068ecc  mov     ebp, 8007000Eh
0x180068ed1  jmp     short loc_180068EF0
0x180068ed3  mov     word ptr [rdi], 1
0x180068ed8  jmp     short loc_180068EF0
0x180068eda  mov     word ptr [rdi], 13h
0x180068edf  mov     eax, [rsi+48h]
0x180068ee2  jmp     short loc_180068EED
0x180068ee4  mov     word ptr [rdi], 13h
0x180068ee9  movzx   eax, word ptr [rsi+30h]
0x180068eed  mov     [rdi+8], eax
0x180068ef0  mov     rcx, r14; SRWLock
0x180068ef3  call    cs:__imp_ReleaseSRWLockShared
0x180068ef9  jmp     short loc_180068F00
0x180068efb  mov     ebp, 80004003h
0x180068f00  mov     rbx, [rsp+58h+arg_0]
0x180068f05  mov     eax, ebp
0x180068f07  mov     rbp, [rsp+58h+arg_8]
0x180068f0c  add     rsp, 40h
0x180068f10  pop     r14
0x180068f12  pop     rdi
0x180068f13  pop     rsi
0x180068f14  retn
```
