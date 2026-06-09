# CMetadataXMPReaderWriter::InitializeFromRDFXMLNode(IXMLDOMNode *)

- ea: `0x18000e930`
- end: `0x18000efb8`
- name: `?InitializeFromRDFXMLNode@CMetadataXMPReaderWriter@@MEAAJPEAUIXMLDOMNode@@@Z`
- size: `1672`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000e930`
- `0x18000efc0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::InitializeFromRDFXMLNode(
        CMetadataXMPReaderWriter *this,
        struct IXMLDOMNode *a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_firstChild)(IXMLDOMNode *, IXMLDOMNode **); // rax
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  unsigned int i; // edi
  int v9; // eax
  int v11; // ecx
  int v12; // ecx
  unsigned int j; // edi
  int v14; // ecx
  __int64 v15; // [rsp+48h] [rbp-9h] BYREF
  __int64 v16; // [rsp+50h] [rbp-1h] BYREF
  __int64 v17; // [rsp+58h] [rbp+7h] BYREF
  __int64 v18; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+68h] [rbp+17h] BYREF
  __int64 v20; // [rsp+70h] [rbp+1Fh] BYREF
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+78h] [rbp+27h] BYREF
  unsigned int v22; // [rsp+C0h] [rbp+6Fh] BYREF
  int v23; // [rsp+C8h] [rbp+77h] BYREF
  int v24; // [rsp+D0h] [rbp+7Fh] BYREF

  lpVtbl = a2->lpVtbl;
  v22 = 0;
  v17 = 0;
  v20 = 0;
  get_firstChild = lpVtbl->get_firstChild;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v16 = 0;
  v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))get_firstChild)(a2, &v17);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v5);
    goto LABEL_25;
  }
LABEL_4:
  if ( v6 )
  {
    v6 = 0;
    goto LABEL_25;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 136LL))(v17, &v18);
  v7 = g_doStackCaptures;
  if ( v6 < 0 )
  {
    if ( g_doStackCaptures )
      goto LABEL_79;
    goto LABEL_25;
  }
  if ( v6 )
    goto LABEL_99;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 88LL))(v18, &v22);
  v7 = g_doStackCaptures;
  if ( v6 < 0 )
  {
    if ( g_doStackCaptures )
      goto LABEL_79;
    goto LABEL_25;
  }
  if ( v6 )
  {
LABEL_99:
    v6 = -2147467259;
    if ( v7 )
      goto LABEL_79;
    goto LABEL_25;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v22 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 96LL))(v17, &v19);
      v7 = g_doStackCaptures;
      if ( v6 >= 0 )
      {
        if ( v6 )
          goto LABEL_99;
        v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 64LL))(v19, &v22);
        v7 = g_doStackCaptures;
        if ( v6 >= 0 )
        {
          if ( v6 )
            goto LABEL_99;
          for ( j = 0; j < v22; ++j )
          {
            v23 = 0;
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 56LL))(v19, j, &v15);
            v6 = v9;
            if ( v9 < 0 )
            {
              if ( g_doStackCaptures )
                goto LABEL_80;
              goto LABEL_25;
            }
            if ( v9 )
              goto LABEL_97;
            v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 80LL))(v15, &v23);
            v6 = v9;
            if ( v9 < 0 )
            {
              if ( g_doStackCaptures )
                goto LABEL_80;
              goto LABEL_25;
            }
            if ( v9 )
            {
LABEL_97:
              v6 = -2147467259;
              if ( g_doStackCaptures )
                DoStackCapture(-2147467259);
              goto LABEL_25;
            }
            if ( v23 == 1 )
            {
              v9 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64 *))(*(_QWORD *)this + 384LL))(
                     this,
                     &v16);
              v6 = v9;
              if ( v9 < 0 )
              {
                if ( g_doStackCaptures )
                  goto LABEL_80;
                goto LABEL_25;
              }
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, v15);
              v6 = v9;
              if ( v9 < 0 )
              {
                if ( g_doStackCaptures )
                  goto LABEL_80;
                goto LABEL_25;
              }
              v9 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64))(*(_QWORD *)this + 336LL))(this, v16);
              v6 = v9;
              if ( v9 < 0 )
              {
                if ( g_doStackCaptures )
                  goto LABEL_80;
                goto LABEL_25;
              }
              v6 = DynArrayImpl<0>::Grow((int)this + 208, 8, 1, 0, 0);
              if ( v6 < 0 )
              {
                if ( !g_doStackCaptures )
                  goto LABEL_25;
                goto LABEL_77;
              }
              v14 = *((_DWORD *)this + 58);
              *((_DWORD *)this + 58) = v14 + 1;
              *(_QWORD *)((unsigned int)(8 * v14) + *((_QWORD *)this + 26)) = v16;
              ++*((_DWORD *)this + 43);
              v16 = 0;
            }
            if ( v15 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              v15 = 0;
            }
          }
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 128LL))(v17, &v20);
          v6 = v9;
          if ( v9 >= 0 )
          {
            if ( v18 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              v18 = 0;
            }
            if ( v19 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              v19 = 0;
            }
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v17 = v20;
            v20 = 0;
            goto LABEL_4;
          }
          if ( g_doStackCaptures )
            goto LABEL_80;
        }
        else if ( g_doStackCaptures )
        {
          goto LABEL_79;
        }
      }
      else if ( g_doStackCaptures )
      {
        goto LABEL_79;
      }
      goto LABEL_25;
    }
    v23 = 0;
    v24 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 80LL))(v18, i, &v15);
    v7 = g_doStackCaptures;
    if ( v6 < 0 )
    {
      if ( g_doStackCaptures )
        goto LABEL_79;
      goto LABEL_25;
    }
    if ( v6 )
      goto LABEL_99;
    v9 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64, __int64, __int64 *, int *, void (__fastcall ****)(_QWORD, __int64), int *))(*(_QWORD *)this + 344LL))(
           this,
           v15,
           v17,
           &v16,
           &v23,
           &v21,
           &v24);
    v6 = v9;
    if ( v9 < 0 )
    {
      if ( g_doStackCaptures )
LABEL_80:
        DoStackCapture(v9);
      goto LABEL_25;
    }
    if ( !v23 )
      break;
    v6 = DynArrayImpl<0>::Grow((int)this + 208, 8, 1, 0, 0);
    if ( v6 < 0 )
      goto LABEL_24;
    v12 = *((_DWORD *)this + 58);
    *((_DWORD *)this + 58) = v12 + 1;
    *(_QWORD *)((unsigned int)(8 * v12) + *((_QWORD *)this + 26)) = v16;
    ++*((_DWORD *)this + 43);
    v16 = 0;
LABEL_44:
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
  }
  if ( !v24 )
    goto LABEL_44;
  v6 = DynArrayImpl<0>::Grow((int)this + 264, 8, 1, 0, 0);
  if ( v6 >= 0 )
  {
    v11 = *((_DWORD *)this + 72);
    *((_DWORD *)this + 72) = v11 + 1;
    *(_QWORD *)((unsigned int)(8 * v11) + *((_QWORD *)this + 33)) = v21;
    v21 = 0;
    goto LABEL_44;
  }
LABEL_24:
  if ( !g_doStackCaptures )
    goto LABEL_25;
LABEL_77:
  DoStackCapture(v6);
  if ( !g_doStackCaptures )
    goto LABEL_25;
  DoStackCapture(v6);
  if ( !g_doStackCaptures )
    goto LABEL_25;
LABEL_79:
  DoStackCapture(v6);
LABEL_25:
  if ( v16 )
    (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
  if ( v21 )
    (**v21)(v21, 1);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e930  mov     rax, rsp
0x18000e933  push    rbp
0x18000e934  push    rbx
0x18000e935  lea     rbp, [rax-5Fh]
0x18000e939  sub     rsp, 98h
0x18000e940  mov     [rax+8], rsi
0x18000e944  mov     r8, rdx
0x18000e947  mov     [rax-28h], r15
0x18000e94b  mov     rsi, rcx
0x18000e94e  mov     rax, [rdx]
0x18000e951  xor     r15d, r15d
0x18000e954  lea     rdx, [rbp+57h+var_50]
0x18000e958  mov     [rbp+57h+arg_8], r15d
0x18000e95c  mov     rcx, r8
0x18000e95f  mov     [rbp+57h+var_50], r15
0x18000e963  mov     [rbp+57h+var_38], r15
0x18000e967  mov     rax, [rax+68h]
0x18000e96b  mov     [rbp+57h+var_60], r15
0x18000e96f  mov     [rbp+57h+var_48], r15
0x18000e973  mov     [rbp+57h+var_40], r15
0x18000e977  mov     [rbp+57h+var_30], r15
0x18000e97b  mov     [rbp+57h+var_58], r15
0x18000e97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e984  mov     ebx, eax
0x18000e986  test    eax, eax
0x18000e988  jns     short loc_18000E99F
0x18000e98a  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e991  jnz     loc_18000EF4B
0x18000e997  test    eax, eax
0x18000e999  js      loc_18000EB1A
0x18000e99f  mov     [rsp+90h], rdi
0x18000e9a7  mov     [rsp+0A0h+var_18], r14
0x18000e9af  test    ebx, ebx
0x18000e9b1  jnz     loc_18000EEF4
0x18000e9b7  mov     rcx, [rbp+57h+var_50]
0x18000e9bb  lea     rdx, [rbp+57h+var_48]
0x18000e9bf  mov     rax, [rcx]
0x18000e9c2  mov     rax, [rax+88h]
0x18000e9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ce  mov     ebx, eax
0x18000e9d0  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000e9d6  test    ebx, ebx
0x18000e9d8  jns     short loc_18000E9EA
0x18000e9da  test    eax, eax
0x18000e9dc  jnz     loc_18000EF82
0x18000e9e2  test    ebx, ebx
0x18000e9e4  js      loc_18000EB0A
0x18000e9ea  jnz     loc_18000EF75
0x18000e9f0  mov     rcx, [rbp+57h+var_48]
0x18000e9f4  lea     rdx, [rbp+57h+arg_8]
0x18000e9f8  mov     rax, [rcx]
0x18000e9fb  mov     rax, [rax+58h]
0x18000e9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea04  mov     ebx, eax
0x18000ea06  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000ea0c  test    ebx, ebx
0x18000ea0e  jns     short loc_18000EA20
0x18000ea10  test    eax, eax
0x18000ea12  jnz     loc_18000EF82
0x18000ea18  test    ebx, ebx
0x18000ea1a  js      loc_18000EB0A
0x18000ea20  jnz     loc_18000EF75
0x18000ea26  mov     edi, r15d
0x18000ea29  nop     dword ptr [rax+00000000h]
0x18000ea30  cmp     edi, [rbp+57h+arg_8]
0x18000ea33  jnb     loc_18000EC76
0x18000ea39  mov     rcx, [rbp+57h+var_48]
0x18000ea3d  lea     r8, [rbp+57h+var_60]
0x18000ea41  mov     [rbp+57h+arg_10], r15d
0x18000ea45  mov     edx, edi
0x18000ea47  mov     [rbp+57h+arg_18], r15d
0x18000ea4b  mov     rax, [rcx]
0x18000ea4e  mov     rax, [rax+50h]
0x18000ea52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea57  mov     ebx, eax
0x18000ea59  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000ea5f  test    ebx, ebx
0x18000ea61  jns     short loc_18000EA73
0x18000ea63  test    eax, eax
0x18000ea65  jnz     loc_18000EF82
0x18000ea6b  test    ebx, ebx
0x18000ea6d  js      loc_18000EB0A
0x18000ea73  jnz     loc_18000EF75
0x18000ea79  mov     rax, [rsi]
0x18000ea7c  lea     rcx, [rbp+57h+arg_18]
0x18000ea80  mov     r8, [rbp+57h+var_50]
0x18000ea84  lea     r9, [rbp+57h+var_58]
0x18000ea88  mov     rdx, [rbp+57h+var_60]
0x18000ea8c  mov     [rsp+30h], rcx
0x18000ea91  lea     rcx, [rbp+57h+var_30]
0x18000ea95  mov     rax, [rax+158h]
0x18000ea9c  mov     [rsp+0A0h+var_78], rcx
0x18000eaa1  lea     rcx, [rbp+57h+arg_10]
0x18000eaa5  mov     [rsp+0A0h+var_80], rcx
0x18000eaaa  mov     rcx, rsi
0x18000eaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab2  mov     ebx, eax
0x18000eab4  test    eax, eax
0x18000eab6  jns     short loc_18000EAC9
0x18000eab8  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000eabf  jnz     loc_18000EE62
0x18000eac5  test    eax, eax
0x18000eac7  js      short loc_18000EB0A
0x18000eac9  cmp     [rbp+57h+arg_10], r15d
0x18000eacd  jz      loc_18000EBC9
0x18000ead3  xor     r9d, r9d
0x18000ead6  mov     [rsp+0A0h+var_80], r15
0x18000eadb  mov     edx, 8
0x18000eae0  lea     rcx, [rsi+0D0h]
0x18000eae7  mov     r8d, 1
0x18000eaed  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x18000eaf2  mov     ebx, eax
0x18000eaf4  test    eax, eax
0x18000eaf6  jns     loc_18000EC27
0x18000eafc  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000eb02  test    eax, eax
0x18000eb04  jnz     loc_18000EE2C
0x18000eb0a  mov     rdi, [rsp+90h]
0x18000eb12  mov     r14, [rsp+0A0h+var_18]
0x18000eb1a  mov     rcx, [rbp+57h+var_58]
0x18000eb1e  mov     rsi, [rsp+0A0h+arg_0]
0x18000eb26  test    rcx, rcx
0x18000eb29  jnz     loc_18000EF8E
0x18000eb2f  mov     rcx, [rbp+57h+var_30]
0x18000eb33  test    rcx, rcx
0x18000eb36  jnz     loc_18000EFA3
0x18000eb3c  mov     rcx, [rbp+57h+var_50]
0x18000eb40  test    rcx, rcx
0x18000eb43  jz      short loc_18000EB55
0x18000eb45  mov     rax, [rcx]
0x18000eb48  mov     rax, [rax+10h]
0x18000eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb51  mov     [rbp+57h+var_50], r15
0x18000eb55  mov     rcx, [rbp+57h+var_38]
0x18000eb59  test    rcx, rcx
0x18000eb5c  jz      short loc_18000EB6E
0x18000eb5e  mov     rax, [rcx]
0x18000eb61  mov     rax, [rax+10h]
0x18000eb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb6a  mov     [rbp+57h+var_38], r15
0x18000eb6e  mov     rcx, [rbp+57h+var_60]
0x18000eb72  test    rcx, rcx
0x18000eb75  jz      short loc_18000EB87
0x18000eb77  mov     rax, [rcx]
0x18000eb7a  mov     rax, [rax+10h]
0x18000eb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb83  mov     [rbp+57h+var_60], r15
0x18000eb87  mov     rcx, [rbp+57h+var_48]
0x18000eb8b  test    rcx, rcx
0x18000eb8e  jz      short loc_18000EBA0
0x18000eb90  mov     rax, [rcx]
0x18000eb93  mov     rax, [rax+10h]
0x18000eb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb9c  mov     [rbp+57h+var_48], r15
0x18000eba0  mov     rcx, [rbp+57h+var_40]
0x18000eba4  mov     r15, [rsp+0A0h+var_20]
0x18000ebac  test    rcx, rcx
0x18000ebaf  jz      short loc_18000EBBD
0x18000ebb1  mov     rax, [rcx]
0x18000ebb4  mov     rax, [rax+10h]
0x18000ebb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebbd  mov     eax, ebx
0x18000ebbf  add     rsp, 98h
0x18000ebc6  pop     rbx
0x18000ebc7  pop     rbp
0x18000ebc8  retn
0x18000ebc9  cmp     [rbp+57h+arg_18], r15d
0x18000ebcd  jz      loc_18000EC56
0x18000ebd3  xor     r9d, r9d
0x18000ebd6  mov     [rsp+0A0h+var_80], r15
0x18000ebdb  mov     edx, 8
0x18000ebe0  lea     rcx, [rsi+108h]
0x18000ebe7  mov     r8d, 1
0x18000ebed  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x18000ebf2  mov     ebx, eax
0x18000ebf4  test    eax, eax
0x18000ebf6  js      loc_18000EAFC
0x18000ebfc  mov     ecx, [rsi+120h]
0x18000ec02  lea     eax, [rcx+1]
0x18000ec05  mov     [rsi+120h], eax
0x18000ec0b  mov     rax, [rbp+57h+var_30]
0x18000ec0f  lea     edx, ds:0[rcx*8]
0x18000ec16  mov     rcx, [rsi+108h]
0x18000ec1d  mov     [rdx+rcx], rax
0x18000ec21  mov     [rbp+57h+var_30], r15
0x18000ec25  jmp     short loc_18000EC56
0x18000ec27  mov     ecx, [rsi+0E8h]
0x18000ec2d  lea     eax, [rcx+1]
0x18000ec30  mov     [rsi+0E8h], eax
0x18000ec36  mov     rax, [rbp+57h+var_58]
0x18000ec3a  lea     edx, ds:0[rcx*8]
0x18000ec41  mov     rcx, [rsi+0D0h]
0x18000ec48  mov     [rdx+rcx], rax
0x18000ec4c  inc     dword ptr [rsi+0ACh]
0x18000ec52  mov     [rbp+57h+var_58], r15
0x18000ec56  mov     rcx, [rbp+57h+var_60]
0x18000ec5a  test    rcx, rcx
0x18000ec5d  jz      short loc_18000EC6F
0x18000ec5f  mov     rax, [rcx]
0x18000ec62  mov     rax, [rax+10h]
0x18000ec66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec6b  mov     [rbp+57h+var_60], r15
0x18000ec6f  inc     edi
0x18000ec71  jmp     loc_18000EA30
0x18000ec76  mov     rcx, [rbp+57h+var_50]
0x18000ec7a  lea     rdx, [rbp+57h+var_40]
0x18000ec7e  mov     rax, [rcx]
0x18000ec81  mov     rax, [rax+60h]
0x18000ec85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8a  mov     ebx, eax
0x18000ec8c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000ec92  test    ebx, ebx
0x18000ec94  jns     short loc_18000ECA6
0x18000ec96  test    eax, eax
0x18000ec98  jnz     loc_18000EF82
0x18000ec9e  test    ebx, ebx
0x18000eca0  js      loc_18000EB0A
0x18000eca6  jnz     loc_18000EF75
0x18000ecac  mov     rcx, [rbp+57h+var_40]
0x18000ecb0  lea     rdx, [rbp+57h+arg_8]
0x18000ecb4  mov     rax, [rcx]
0x18000ecb7  mov     rax, [rax+40h]
0x18000ecbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc0  mov     ebx, eax
0x18000ecc2  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000ecc8  test    ebx, ebx
0x18000ecca  jns     short loc_18000ECDC
0x18000eccc  test    eax, eax
0x18000ecce  jnz     loc_18000EF82
0x18000ecd4  test    ebx, ebx
0x18000ecd6  js      loc_18000EB0A
0x18000ecdc  jnz     loc_18000EF75
0x18000ece2  mov     edi, r15d
0x18000ece5  cmp     edi, [rbp+57h+arg_8]
0x18000ece8  jnb     loc_18000EE6E
0x18000ecee  mov     rcx, [rbp+57h+var_40]
0x18000ecf2  lea     r8, [rbp+57h+var_60]
0x18000ecf6  mov     [rbp+57h+arg_10], r15d
0x18000ecfa  mov     edx, edi
0x18000ecfc  mov     rax, [rcx]
0x18000ecff  mov     rax, [rax+38h]
0x18000ed03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed08  mov     ebx, eax
0x18000ed0a  test    eax, eax
0x18000ed0c  jns     short loc_18000ED23
0x18000ed0e  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000ed15  jnz     loc_18000EE62
0x18000ed1b  test    eax, eax
0x18000ed1d  js      loc_18000EB0A
0x18000ed23  jnz     loc_18000EF57
0x18000ed29  mov     rcx, [rbp+57h+var_60]
0x18000ed2d  lea     rdx, [rbp+57h+arg_10]
0x18000ed31  mov     rax, [rcx]
0x18000ed34  mov     rax, [rax+50h]
0x18000ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed3d  mov     ebx, eax
0x18000ed3f  test    eax, eax
0x18000ed41  jns     short loc_18000ED58
0x18000ed43  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000ed4a  jnz     loc_18000EE62
0x18000ed50  test    eax, eax
0x18000ed52  js      loc_18000EB0A
0x18000ed58  jnz     loc_18000EF57
0x18000ed5e  cmp     [rbp+57h+arg_10], 1
0x18000ed62  jnz     loc_18000EF2B
0x18000ed68  mov     rax, [rsi]
0x18000ed6b  lea     rdx, [rbp+57h+var_58]
0x18000ed6f  mov     rcx, rsi
0x18000ed72  mov     rax, [rax+180h]
0x18000ed79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed7e  mov     ebx, eax
0x18000ed80  test    eax, eax
0x18000ed82  jns     short loc_18000ED99
0x18000ed84  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000ed8b  jnz     loc_18000EE62
0x18000ed91  test    eax, eax
0x18000ed93  js      loc_18000EB0A
0x18000ed99  mov     rcx, [rbp+57h+var_58]
0x18000ed9d  mov     rdx, [rbp+57h+var_60]
0x18000eda1  mov     rax, [rcx]
0x18000eda4  mov     rax, [rax+8]
0x18000eda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edad  mov     ebx, eax
0x18000edaf  test    eax, eax
0x18000edb1  jns     short loc_18000EDC8
0x18000edb3  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000edba  jnz     loc_18000EE62
0x18000edc0  test    eax, eax
0x18000edc2  js      loc_18000EB0A
0x18000edc8  mov     rax, [rsi]
0x18000edcb  mov     rcx, rsi
0x18000edce  mov     rdx, [rbp+57h+var_58]
0x18000edd2  mov     rax, [rax+150h]
0x18000edd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edde  mov     ebx, eax
0x18000ede0  test    eax, eax
0x18000ede2  jns     short loc_18000EDF5
0x18000ede4  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000edeb  jnz     short loc_18000EE62
0x18000eded  test    eax, eax
  ... truncated ...
```
