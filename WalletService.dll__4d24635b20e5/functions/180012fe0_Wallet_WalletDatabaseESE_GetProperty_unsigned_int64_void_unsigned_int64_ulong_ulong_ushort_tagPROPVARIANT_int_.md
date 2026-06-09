# Wallet::WalletDatabaseESE::_GetProperty(unsigned __int64,void *,unsigned __int64,ulong,ulong,ushort,tagPROPVARIANT *,int,int,ulong *,unsigned __int64,ulong,TableMapping const *)

- ea: `0x180012fe0`
- end: `0x1800133dd`
- name: `?_GetProperty@WalletDatabaseESE@Wallet@@AEAAJ_KPEAX0KKGPEAUtagPROPVARIANT@@HHPEAK0KPEBUTableMapping@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(Wallet::WalletDatabaseESE *this, unsigned __int64, void *, __int64, unsigned int, unsigned int, VARTYPE, struct tagPROPVARIANT *, int, int, unsigned int *, unsigned __int64, unsigned int, const struct TableMapping *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000edf0`
- `0x18000f0a0`
- `0x18000f5f0`
- `0x180010904`
- `0x180011924`

## callees

- `0x180002e48`
- `0x180010f60`
- `0x180012fe0`
- `0x18001b760`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800133a9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800133b2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800133a9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800133b2`
- `msvcrt!memcpy_s` at `0x180013353`
- `msvcrt!memcpy_s` at `0x18001339c`
- `msvcrt!memcpy_s` at `0x180013353`
- `msvcrt!memcpy_s` at `0x18001339c`
- `OLEAUT32!__imp_SysAllocString` at `0x180013377`
- `OLEAUT32!__imp_SysAllocString` at `0x180013377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013313`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013333`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::_GetProperty(
        Wallet::WalletDatabaseESE *this,
        unsigned __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        VARTYPE a7,
        struct tagPROPVARIANT *a8,
        int a9,
        int a10,
        unsigned int *a11,
        unsigned __int64 a12,
        unsigned int a13,
        const struct TableMapping *a14)
{
  void *v16; // rbx
  void *v17; // r13
  int v18; // eax
  int v19; // edi
  int v20; // eax
  const OLECHAR *v21; // rsi
  void *v22; // rax
  unsigned int v23; // edx
  int v24; // eax
  LARGE_INTEGER *v25; // rax
  rsize_t v26; // r9
  rsize_t v27; // rdx
  LARGE_INTEGER *p_hVal; // rcx
  BYTE *v29; // rax
  BSTR v30; // rax
  SIZE_T cb; // [rsp+50h] [rbp-B0h] BYREF
  void *v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  struct TableMapping *v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  void *v37; // [rsp+78h] [rbp-88h]
  __int128 v38; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Source[256]; // [rsp+90h] [rbp-70h] BYREF

  v37 = a3;
  v34 = a2;
  v35 = a14;
  v36 = a4;
  memset_0(Source, 0, sizeof(Source));
  v16 = 0;
  v17 = 0;
  cb = 0;
  v33 = 0;
  v38 = 0;
  if ( a5 - 2 <= 1 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, const char *))(**((_QWORD **)this + 13) + 192LL))(
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 3),
            a12,
            "Properties");
    if ( v19 < 0 )
      goto LABEL_48;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, unsigned __int64 *, int, int))(**((_QWORD **)this + 13) + 208LL))(
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 3),
            a12,
            &v34,
            8,
            1);
    if ( v19 < 0 )
      goto LABEL_48;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, void *, _DWORD, _DWORD))(**((_QWORD **)this + 13)
                                                                                              + 208LL))(
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 3),
            a12,
            v37,
            v36,
            0);
    if ( v19 < 0 )
      goto LABEL_48;
    v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64))(**((_QWORD **)this + 13) + 216LL))(
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 3),
            a12,
            1);
  }
  else
  {
    v18 = Wallet::WalletDatabaseESE::MoveToItem(this, a2, v35, 0);
  }
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( a11 )
    {
      DWORD2(v38) = *a11;
      LODWORD(v38) = 16;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, _BYTE *, int, SIZE_T *, _DWORD, unsigned __int64))(**((_QWORD **)this + 13) + 160LL))(
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 3),
            a12,
            a13,
            Source,
            256,
            &cb,
            0,
            (unsigned __int64)&v38 & -(__int64)(a11 != 0));
    v19 = v20;
    if ( v20 == -1047 || v20 == 1006 || v20 == -1038 )
    {
      v22 = operator new[]((unsigned int)cb);
      v17 = v22;
      if ( !v22 )
        goto LABEL_15;
      v21 = (const OLECHAR *)v22;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, void *, _DWORD, SIZE_T *, _DWORD, _QWORD))(**((_QWORD **)this + 13) + 160LL))(
              *((_QWORD *)this + 13),
              *((_QWORD *)this + 3),
              a12,
              a13,
              v22,
              cb,
              &cb,
              0,
              0);
    }
    else
    {
      v21 = (const OLECHAR *)Source;
    }
    if ( v19 == 1004 )
    {
      v19 = -1601;
      goto LABEL_48;
    }
    if ( v19 < 0 )
      goto LABEL_48;
    if ( a9 && *((_DWORD *)this + 24) )
    {
      v23 = cb;
      if ( (_DWORD)cb )
      {
        v24 = WalletEncrypter::Decrypt((char *)this + 56, v34, v21, (unsigned int)cb, &v33, (char *)&cb + 4, a10);
        v16 = v33;
        if ( v24 < 0 )
        {
          v19 = -1316;
          goto LABEL_48;
        }
        v23 = HIDWORD(cb);
        v21 = (const OLECHAR *)v33;
        LODWORD(cb) = HIDWORD(cb);
      }
    }
    else
    {
      v23 = cb;
    }
    if ( a7 != 5 )
    {
      if ( a7 == 8 )
      {
        v30 = SysAllocString(v21);
        a8->hVal.QuadPart = (LONGLONG)v30;
        if ( v30 )
          goto LABEL_47;
        goto LABEL_15;
      }
      if ( a7 == 18 )
      {
        v27 = 2;
        goto LABEL_40;
      }
      if ( a7 != 21 )
      {
        if ( a7 != 22 )
        {
          if ( a7 != 64 )
          {
            if ( a7 != 65 )
            {
              if ( a7 == 72 )
              {
                v25 = (LARGE_INTEGER *)CoTaskMemAlloc(0x10u);
                a8->hVal.QuadPart = (LONGLONG)v25;
                if ( v25 )
                {
                  v26 = 16;
                  v27 = 16;
                  p_hVal = v25;
LABEL_46:
                  memcpy_s(p_hVal, v27, v21, v26);
                  goto LABEL_47;
                }
                goto LABEL_15;
              }
LABEL_47:
              a8->vt = a7;
              goto LABEL_48;
            }
            v29 = (BYTE *)CoTaskMemAlloc(v23);
            a8->bstrblobVal.pData = v29;
            if ( v29 )
            {
              memcpy_s(v29, (unsigned int)cb, v21, (unsigned int)cb);
              a8->lVal = cb;
              goto LABEL_47;
            }
LABEL_15:
            v19 = -1011;
            goto LABEL_48;
          }
          goto LABEL_44;
        }
        v27 = 4;
LABEL_40:
        v26 = v27;
LABEL_45:
        p_hVal = &a8->hVal;
        goto LABEL_46;
      }
    }
LABEL_44:
    v26 = 8;
    v27 = 8;
    goto LABEL_45;
  }
LABEL_48:
  operator delete[](v17);
  operator delete[](v16);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180012fe0  push    rbp
0x180012fe2  push    rbx
0x180012fe3  push    rsi
0x180012fe4  push    rdi
0x180012fe5  push    r12
0x180012fe7  push    r13
0x180012fe9  push    r14
0x180012feb  push    r15
0x180012fed  lea     rbp, [rsp-0A8h]
0x180012ff5  sub     rsp, 1A8h
0x180012ffc  mov     rax, cs:__security_cookie
0x180013003  xor     rax, rsp
0x180013006  mov     [rbp+0E0h+var_50], rax
0x18001300d  mov     rax, [rbp+0E0h+arg_68]
0x180013014  mov     rdi, rdx
0x180013017  mov     r14, [rbp+0E0h+arg_38]
0x18001301e  mov     r15, rcx
0x180013021  mov     rsi, [rbp+0E0h+arg_50]
0x180013028  lea     rcx, [rbp+0E0h+Source]; void *
0x18001302c  mov     [rsp+1E0h+var_168], r8
0x180013031  mov     r8d, 100h; Size
0x180013037  mov     [rsp+1E0h+var_180], rdx
0x18001303c  xor     edx, edx; Val
0x18001303e  mov     [rsp+1E0h+var_178], rax
0x180013043  mov     [rsp+1E0h+var_170], r9
0x180013048  call    memset_0
0x18001304d  mov     eax, [rbp+0E0h+arg_20]
0x180013053  xor     ebx, ebx
0x180013055  mov     r12, [rbp+0E0h+arg_58]
0x18001305c  xor     r13d, r13d
0x18001305f  add     eax, 0FFFFFFFEh
0x180013062  mov     dword ptr [rsp+1E0h+cb], r13d
0x180013067  mov     [rsp+1E0h+var_188], rbx
0x18001306c  xorps   xmm0, xmm0
0x18001306f  mov     dword ptr [rsp+1E0h+cb+4], ebx
0x180013073  movups  [rbp+0E0h+var_160], xmm0
0x180013077  cmp     eax, 1
0x18001307a  jbe     short loc_180013094
0x18001307c  mov     r8, [rsp+1E0h+var_178]; struct TableMapping *
0x180013081  xor     r9d, r9d; struct Wallet::ItemDBInfo *
0x180013084  mov     rdx, rdi; unsigned __int64
0x180013087  mov     rcx, r15; this
0x18001308a  call    ?MoveToItem@WalletDatabaseESE@Wallet@@AEAAJ_KPEBUTableMapping@@PEAUItemDBInfo@2@@Z; Wallet::WalletDatabaseESE::MoveToItem(unsigned __int64,TableMapping const *,Wallet::ItemDBInfo *)
0x18001308f  jmp     loc_18001314E
0x180013094  mov     rcx, [r15+68h]
0x180013098  lea     r9, aProperties; "Properties"
0x18001309f  mov     rdx, [r15+18h]
0x1800130a3  mov     r8, r12
0x1800130a6  mov     rax, [rcx]
0x1800130a9  mov     rax, [rax+0C0h]
0x1800130b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b5  mov     edi, eax
0x1800130b7  test    eax, eax
0x1800130b9  js      loc_1800133A6
0x1800130bf  mov     rcx, [r15+68h]
0x1800130c3  lea     r9, [rsp+1E0h+var_180]
0x1800130c8  mov     rdx, [r15+18h]
0x1800130cc  mov     r8, r12
0x1800130cf  mov     dword ptr [rsp+1E0h+var_1B8], 1
0x1800130d7  mov     dword ptr [rsp+1E0h+var_1C0], 8
0x1800130df  mov     rax, [rcx]
0x1800130e2  mov     rax, [rax+0D0h]
0x1800130e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130ee  mov     edi, eax
0x1800130f0  test    eax, eax
0x1800130f2  js      loc_1800133A6
0x1800130f8  mov     rcx, [r15+68h]
0x1800130fc  mov     r8, r12
0x1800130ff  mov     rdx, [rsp+1E0h+var_170]
0x180013104  mov     r9, [rsp+1E0h+var_168]
0x180013109  mov     dword ptr [rsp+1E0h+var_1B8], ebx
0x18001310d  mov     rax, [rcx]
0x180013110  mov     dword ptr [rsp+1E0h+var_1C0], edx
0x180013114  mov     rdx, [r15+18h]
0x180013118  mov     rax, [rax+0D0h]
0x18001311f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013124  mov     edi, eax
0x180013126  test    eax, eax
0x180013128  js      loc_1800133A6
0x18001312e  mov     rcx, [r15+68h]
0x180013132  mov     r9d, 1
0x180013138  mov     rdx, [r15+18h]
0x18001313c  mov     r8, r12
0x18001313f  mov     rax, [rcx]
0x180013142  mov     rax, [rax+0D8h]
0x180013149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314e  mov     edi, eax
0x180013150  test    eax, eax
0x180013152  js      loc_1800133A6
0x180013158  test    rsi, rsi
0x18001315b  jz      short loc_180013169
0x18001315d  mov     eax, [rsi]
0x18001315f  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x180013162  mov     dword ptr [rbp+0E0h+var_160], 10h
0x180013169  mov     rcx, [r15+68h]
0x18001316d  lea     r8, [rbp+0E0h+var_160]
0x180013171  mov     r9d, [rbp+0E0h+arg_60]
0x180013178  neg     rsi
0x18001317b  sbb     rax, rax
0x18001317e  mov     rdx, [rcx]
0x180013181  and     rax, r8
0x180013184  mov     [rsp+1E0h+var_1A0], rax
0x180013189  mov     r8, r12
0x18001318c  mov     [rsp+1E0h+var_1A8], ebx
0x180013190  lea     rax, [rsp+1E0h+cb]
0x180013195  mov     [rsp+1E0h+var_1B0], rax
0x18001319a  lea     rax, [rbp+0E0h+Source]
0x18001319e  mov     r10, [rdx+0A0h]
0x1800131a5  mov     rdx, [r15+18h]
0x1800131a9  mov     dword ptr [rsp+1E0h+var_1B8], 100h
0x1800131b1  mov     [rsp+1E0h+var_1C0], rax
0x1800131b6  mov     rax, r10
0x1800131b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131be  mov     edi, eax
0x1800131c0  cmp     eax, 0FFFFFBE9h
0x1800131c5  jz      short loc_1800131DB
0x1800131c7  cmp     eax, 3EEh
0x1800131cc  jz      short loc_1800131DB
0x1800131ce  cmp     eax, 0FFFFFBF2h
0x1800131d3  jz      short loc_1800131DB
0x1800131d5  lea     rsi, [rbp+0E0h+Source]
0x1800131d9  jmp     short loc_18001323C
0x1800131db  mov     ecx, dword ptr [rsp+1E0h+cb]; unsigned __int64
0x1800131df  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800131e4  mov     r13, rax
0x1800131e7  test    rax, rax
0x1800131ea  jnz     short loc_1800131F6
0x1800131ec  mov     edi, 0FFFFFC0Dh
0x1800131f1  jmp     loc_1800133A6
0x1800131f6  mov     edx, dword ptr [rsp+1E0h+cb]
0x1800131fa  lea     r8, [rsp+1E0h+cb]
0x1800131ff  mov     rcx, [r15+68h]
0x180013203  mov     rsi, r13
0x180013206  mov     r9d, [rbp+0E0h+arg_60]
0x18001320d  mov     [rsp+1E0h+var_1A0], rbx
0x180013212  mov     [rsp+1E0h+var_1A8], ebx
0x180013216  mov     rax, [rcx]
0x180013219  mov     [rsp+1E0h+var_1B0], r8
0x18001321e  mov     r8, r12
0x180013221  mov     dword ptr [rsp+1E0h+var_1B8], edx
0x180013225  mov     rdx, [r15+18h]
0x180013229  mov     rax, [rax+0A0h]
0x180013230  mov     [rsp+1E0h+var_1C0], r13
0x180013235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001323a  mov     edi, eax
0x18001323c  cmp     edi, 3ECh
0x180013242  jnz     short loc_18001324E
0x180013244  mov     edi, 0FFFFF9BFh
0x180013249  jmp     loc_1800133A6
0x18001324e  test    edi, edi
0x180013250  js      loc_1800133A6
0x180013256  cmp     [rbp+0E0h+arg_40], ebx
0x18001325c  jz      short loc_1800132BD
0x18001325e  lea     rcx, [r15+38h]
0x180013262  cmp     [rcx+28h], ebx
0x180013265  jz      short loc_1800132BD
0x180013267  mov     edx, dword ptr [rsp+1E0h+cb]
0x18001326b  test    edx, edx
0x18001326d  jz      short loc_1800132C1
0x18001326f  mov     eax, [rbp+0E0h+arg_48]
0x180013275  mov     r9d, edx
0x180013278  mov     rdx, [rsp+1E0h+var_180]
0x18001327d  mov     r8, rsi
0x180013280  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x180013284  lea     rax, [rsp+1E0h+cb+4]
0x180013289  mov     [rsp+1E0h+var_1B8], rax
0x18001328e  lea     rax, [rsp+1E0h+var_188]
0x180013293  mov     [rsp+1E0h+var_1C0], rax
0x180013298  call    ?Decrypt@WalletEncrypter@@QEAAJ_KPEAEKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAKH@Z; WalletEncrypter::Decrypt(unsigned __int64,uchar *,ulong,std::unique_ptr<uchar [0]> &,ulong &,int)
0x18001329d  mov     rbx, [rsp+1E0h+var_188]
0x1800132a2  test    eax, eax
0x1800132a4  jns     short loc_1800132B0
0x1800132a6  mov     edi, 0FFFFFADCh
0x1800132ab  jmp     loc_1800133A6
0x1800132b0  mov     edx, dword ptr [rsp+1E0h+cb+4]
0x1800132b4  mov     rsi, rbx
0x1800132b7  mov     dword ptr [rsp+1E0h+cb], edx
0x1800132bb  jmp     short loc_1800132C1
0x1800132bd  mov     edx, dword ptr [rsp+1E0h+cb]
0x1800132c1  movzx   r15d, [rbp+0E0h+arg_30]
0x1800132c9  mov     ecx, r15d
0x1800132cc  sub     ecx, 5
0x1800132cf  jz      loc_18001338B
0x1800132d5  sub     ecx, 3
0x1800132d8  jz      loc_180013374
0x1800132de  sub     ecx, 0Ah
0x1800132e1  jz      loc_18001336D
0x1800132e7  sub     ecx, 3
0x1800132ea  jz      loc_18001338B
0x1800132f0  sub     ecx, 1
0x1800132f3  jz      short loc_180013363
0x1800132f5  sub     ecx, 2Ah ; '*'
0x1800132f8  jz      loc_18001338B
0x1800132fe  sub     ecx, 1
0x180013301  jz      short loc_180013331
0x180013303  cmp     ecx, 7
0x180013306  jnz     loc_1800133A2
0x18001330c  lea     r12d, [rcx+9]
0x180013310  mov     ecx, r12d; cb
0x180013313  call    cs:__imp_CoTaskMemAlloc
0x180013319  mov     [r14+8], rax
0x18001331d  test    rax, rax
0x180013320  jz      loc_1800131EC
0x180013326  mov     r9d, r12d
0x180013329  mov     edx, r12d
0x18001332c  mov     rcx, rax
0x18001332f  jmp     short loc_180013399
0x180013331  mov     ecx, edx; cb
0x180013333  call    cs:__imp_CoTaskMemAlloc
0x180013339  mov     [r14+10h], rax
0x18001333d  test    rax, rax
0x180013340  jz      loc_1800131EC
0x180013346  mov     edx, dword ptr [rsp+1E0h+cb]; DestinationSize
0x18001334a  mov     r8, rsi; Source
0x18001334d  mov     r9d, edx; SourceSize
0x180013350  mov     rcx, rax; Destination
0x180013353  call    cs:__imp_memcpy_s
0x180013359  mov     eax, dword ptr [rsp+1E0h+cb]
0x18001335d  mov     [r14+8], eax
0x180013361  jmp     short loc_1800133A2
0x180013363  mov     edx, 4
0x180013368  mov     r9, rdx
0x18001336b  jmp     short loc_180013395
0x18001336d  mov     edx, 2
0x180013372  jmp     short loc_180013368
0x180013374  mov     rcx, rsi; psz
0x180013377  call    cs:__imp_SysAllocString
0x18001337d  mov     [r14+8], rax
0x180013381  test    rax, rax
0x180013384  jnz     short loc_1800133A2
0x180013386  jmp     loc_1800131EC
0x18001338b  mov     eax, 8
0x180013390  mov     r9d, eax; SourceSize
0x180013393  mov     edx, eax; DestinationSize
0x180013395  lea     rcx, [r14+8]; Destination
0x180013399  mov     r8, rsi; Source
0x18001339c  call    cs:__imp_memcpy_s
0x1800133a2  mov     [r14], r15w
0x1800133a6  mov     rcx, r13
0x1800133a9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800133af  mov     rcx, rbx
0x1800133b2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800133b8  mov     eax, edi
0x1800133ba  mov     rcx, [rbp+0E0h+var_50]
0x1800133c1  xor     rcx, rsp; StackCookie
0x1800133c4  call    __security_check_cookie
0x1800133c9  add     rsp, 1A8h
0x1800133d0  pop     r15
0x1800133d2  pop     r14
0x1800133d4  pop     r13
0x1800133d6  pop     r12
0x1800133d8  pop     rdi
0x1800133d9  pop     rsi
0x1800133da  pop     rbx
0x1800133db  pop     rbp
0x1800133dc  retn
```
