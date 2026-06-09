# Dossier::BuildPublishingHistory(UpdatePublishedHistory * &,ulong *)

- ea: `0x18000c990`
- end: `0x18000ccdf`
- name: `?BuildPublishingHistory@Dossier@@UEAAJAEAPEAUUpdatePublishedHistory@@PEAK@Z`
- size: `847`
- prototype: `__int64 __fastcall(Dossier *__hidden this, struct UpdatePublishedHistory **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000b2d8`
- `0x18000c990`
- `0x18000efec`
- `0x180018a50`
- `0x180018c74`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000cb74`
- `msvcrt!wcsncpy_s` at `0x18000cb74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cae5`

## pseudocode

```c
__int64 __fastcall Dossier::BuildPublishingHistory(Dossier *this, struct UpdatePublishedHistory **a2, unsigned int *a3)
{
  unsigned int v3; // r13d
  __int64 v8; // rax
  int v9; // edi
  _QWORD *v10; // rsi
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  unsigned int i; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  bool v17; // zf
  unsigned int v18; // ecx
  struct UpdatePublishedHistory *v19; // rax
  int v20; // r12d
  int v21; // edi
  const wchar_t *v22; // r8
  rsize_t v23; // r9
  __int64 v24; // rbx
  unsigned int v25; // r14d
  int v26; // [rsp+20h] [rbp-30h]
  unsigned int *v27; // [rsp+20h] [rbp-30h]
  __int64 v28; // [rsp+28h] [rbp-28h]
  unsigned int v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v31; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v32; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-Ch] BYREF
  int v35; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v37; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v38; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  *a3 = 0;
  v8 = *(_QWORD *)this;
  v37 = 0;
  v32 = 0;
  v9 = (*(__int64 (__fastcall **)(Dossier *, _QWORD, unsigned int *))(v8 + 8))(this, 0, &v37);
  if ( v9 >= 0 && v37 )
  {
    v10 = CoTaskMemAlloc(16LL * v37);
    if ( v10 )
    {
      v11 = v37;
      v12 = 0;
      for ( i = 0; i < v37; v11 = v37 )
      {
        v14 = (int)i++;
        v14 *= 2;
        v10[v14] = 0;
        v10[v14 + 1] = 0;
      }
      v15 = *(_QWORD *)this;
      v32 = v11;
      v9 = (*(__int64 (__fastcall **)(Dossier *, _QWORD *, unsigned int *))(v15 + 8))(this, v10, &v32);
      v35 = v9;
      v16 = v37;
      if ( v37 )
      {
        do
        {
          if ( v9 < 0 )
            goto LABEL_33;
          v31 = 0;
          v33 = 0;
          v34 = 0;
          v38 = 0;
          v17 = (unsigned int)GetVersionElements((const unsigned __int16 *)v10[2 * (int)v3], &v31, &v33, &v34, &v38) == 4;
          v18 = v12 + 1;
          v16 = v37;
          if ( !v17 )
            v18 = v12;
          ++v3;
          v12 = v18;
        }
        while ( v3 < v37 );
      }
      if ( v9 >= 0 && v12 )
      {
        *a3 = v12;
        v19 = (struct UpdatePublishedHistory *)CoTaskMemAlloc(1056LL * v12);
        *a2 = v19;
        v17 = v19 == 0;
        v16 = v37;
        if ( !v17 )
        {
          v20 = 0;
          if ( !v37 )
            goto LABEL_33;
          v21 = 0;
          while ( 1 )
          {
            v31 = 0;
            v30 = 0;
            v29 = 0;
            v38 = 0;
            if ( (unsigned int)GetVersionElements((const unsigned __int16 *)v10[2 * v20], &v31, &v30, &v29, &v38) == 4 )
              break;
LABEL_30:
            v16 = v37;
            if ( ++v20 >= v37 )
            {
              v9 = v35;
              goto LABEL_33;
            }
          }
          v22 = (const wchar_t *)v10[2 * v20];
          v33 = 0;
          v23 = -1;
          v34 = 0;
          do
            ++v23;
          while ( v22[v23] );
          v24 = 1056LL * v21;
          wcsncpy_s((wchar_t *)((char *)*a2 + v24), 0x104u, v22, v23);
          *(struct _FILETIME *)((char *)*a2 + v24 + 1048) = StringToFileTime((const unsigned __int16 *)v10[2 * v20 + 1]);
          *(_DWORD *)((char *)*a2 + v24 + 1040) = 0;
          *(_DWORD *)((char *)*a2 + v24 + 1044) = 0;
          if ( (*(int (__fastcall **)(Dossier *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)this + 72LL))(
                 this,
                 v31,
                 v30,
                 v29,
                 &v33) < 0 )
          {
            if ( v38 )
              goto LABEL_26;
          }
          else if ( v38 != v33 )
          {
LABEL_26:
            if ( (*(int (__fastcall **)(Dossier *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)this + 104LL))(
                   this,
                   v31,
                   v30,
                   v29,
                   &v34) >= 0
              && v38 == v34 )
            {
              *(_DWORD *)((char *)*a2 + v24 + 1044) = 1;
              *(_DWORD *)((char *)*a2 + v24 + 1040) = 1;
            }
            LODWORD(v28) = v29;
            LODWORD(v27) = v30;
            StringCchPrintfW((unsigned __int16 *)((char *)*a2 + v24 + 520), 0x104u, L"%d.%d.%d", v31, v27, v28);
            ++v21;
            goto LABEL_30;
          }
          *(_DWORD *)((char *)*a2 + v24 + 1040) = 1;
          goto LABEL_26;
        }
        v9 = -2147024882;
      }
LABEL_33:
      v25 = 0;
      if ( v16 )
      {
        do
        {
          CoTaskMemFree((LPVOID)v10[2 * (int)v25]);
          CoTaskMemFree((LPVOID)v10[2 * (int)v25++ + 1]);
        }
        while ( v25 < v37 );
      }
      CoTaskMemFree(v10);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c990  mov     [rsp-38h+arg_0], rbx
0x18000c995  push    rbp
0x18000c996  push    rsi
0x18000c997  push    rdi
0x18000c998  push    r12
0x18000c99a  push    r13
0x18000c99c  push    r14
0x18000c99e  push    r15
0x18000c9a0  mov     rbp, rsp
0x18000c9a3  sub     rsp, 50h
0x18000c9a7  xor     r13d, r13d
0x18000c9aa  mov     r12, r8
0x18000c9ad  mov     r14, rdx
0x18000c9b0  mov     r15, rcx
0x18000c9b3  test    r8, r8
0x18000c9b6  jnz     short loc_18000C9DC
0x18000c9b8  mov     rcx, [rbp+38h]; this
0x18000c9bc  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000c9c3  mov     ebx, 80004003h
0x18000c9c8  mov     edx, 236h; void *
0x18000c9cd  mov     r9d, ebx; char *
0x18000c9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9d5  mov     eax, ebx
0x18000c9d7  jmp     loc_18000CCC7
0x18000c9dc  mov     [r8], r13d
0x18000c9df  xor     edx, edx
0x18000c9e1  mov     rax, [rcx]
0x18000c9e4  lea     r8, [rbp+arg_10]
0x18000c9e8  mov     [rbp+arg_10], r13d
0x18000c9ec  mov     [rbp+var_14], r13d
0x18000c9f0  mov     rax, [rax+8]
0x18000c9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f9  mov     edi, eax
0x18000c9fb  test    eax, eax
0x18000c9fd  js      loc_18000CCC5
0x18000ca03  mov     eax, [rbp+arg_10]
0x18000ca06  test    eax, eax
0x18000ca08  jz      loc_18000CCC5
0x18000ca0e  mov     ecx, eax
0x18000ca10  shl     rcx, 4; cb
0x18000ca14  call    cs:__imp_CoTaskMemAlloc
0x18000ca1a  mov     rsi, rax
0x18000ca1d  test    rax, rax
0x18000ca20  jz      loc_18000CCC0
0x18000ca26  mov     ecx, [rbp+arg_10]
0x18000ca29  mov     ebx, r13d
0x18000ca2c  mov     eax, r13d
0x18000ca2f  test    ecx, ecx
0x18000ca31  jz      short loc_18000CA4B
0x18000ca33  movsxd  rcx, eax
0x18000ca36  inc     eax
0x18000ca38  add     rcx, rcx
0x18000ca3b  mov     [rsi+rcx*8], r13
0x18000ca3f  mov     [rsi+rcx*8+8], r13
0x18000ca44  mov     ecx, [rbp+arg_10]
0x18000ca47  cmp     eax, ecx
0x18000ca49  jb      short loc_18000CA33
0x18000ca4b  mov     rax, [r15]
0x18000ca4e  lea     r8, [rbp+var_14]
0x18000ca52  mov     [rbp+var_14], ecx
0x18000ca55  mov     rdx, rsi
0x18000ca58  mov     rcx, r15
0x18000ca5b  mov     rax, [rax+8]
0x18000ca5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca64  mov     edi, eax
0x18000ca66  mov     [rbp+var_8], eax
0x18000ca69  mov     eax, [rbp+arg_10]
0x18000ca6c  xor     ecx, ecx
0x18000ca6e  test    eax, eax
0x18000ca70  jz      short loc_18000CAC5
0x18000ca72  test    edi, edi
0x18000ca74  js      loc_18000CC87
0x18000ca7a  mov     [rbp+var_18], ecx
0x18000ca7d  lea     rax, [rbp+arg_18]
0x18000ca81  mov     [rbp+var_10], ecx
0x18000ca84  lea     r9, [rbp+var_C]; unsigned int *
0x18000ca88  mov     [rbp+var_C], ecx
0x18000ca8b  lea     r8, [rbp+var_10]; unsigned int *
0x18000ca8f  mov     [rbp+arg_18], ecx
0x18000ca92  lea     rdx, [rbp+var_18]; unsigned int *
0x18000ca96  movsxd  rcx, r13d
0x18000ca99  add     rcx, rcx
0x18000ca9c  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000caa1  mov     rcx, [rsi+rcx*8]; unsigned __int16 *
0x18000caa5  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000caaa  cmp     eax, 4
0x18000caad  lea     ecx, [rbx+1]
0x18000cab0  mov     eax, [rbp+arg_10]
0x18000cab3  cmovnz  ecx, ebx
0x18000cab6  inc     r13d
0x18000cab9  mov     ebx, ecx
0x18000cabb  mov     ecx, 0
0x18000cac0  cmp     r13d, eax
0x18000cac3  jb      short loc_18000CA72
0x18000cac5  xor     r13d, r13d
0x18000cac8  test    edi, edi
0x18000caca  js      loc_18000CC8A
0x18000cad0  test    ebx, ebx
0x18000cad2  jz      loc_18000CC8A
0x18000cad8  mov     eax, ebx
0x18000cada  imul    rcx, rax, 420h; cb
0x18000cae1  mov     [r12], ebx
0x18000cae5  call    cs:__imp_CoTaskMemAlloc
0x18000caeb  mov     [r14], rax
0x18000caee  test    rax, rax
0x18000caf1  mov     eax, [rbp+arg_10]
0x18000caf4  jz      loc_18000CC80
0x18000cafa  mov     r12d, r13d
0x18000cafd  test    eax, eax
0x18000caff  jz      loc_18000CC8A
0x18000cb05  mov     edi, r13d
0x18000cb08  mov     [rbp+var_18], r13d
0x18000cb0c  lea     rax, [rbp+arg_18]
0x18000cb10  mov     [rbp+var_1C], r13d
0x18000cb14  lea     r9, [rbp+var_20]; unsigned int *
0x18000cb18  mov     [rbp+var_20], r13d
0x18000cb1c  lea     r8, [rbp+var_1C]; unsigned int *
0x18000cb20  mov     [rbp+arg_18], r13d
0x18000cb24  lea     rdx, [rbp+var_18]; unsigned int *
0x18000cb28  movsxd  r13, r12d
0x18000cb2b  add     r13, r13
0x18000cb2e  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000cb33  mov     rcx, [rsi+r13*8]; unsigned __int16 *
0x18000cb37  call    ?GetVersionElements@@YAHPEBGAEAK111@Z; GetVersionElements(ushort const *,ulong &,ulong &,ulong &,ulong &)
0x18000cb3c  cmp     eax, 4
0x18000cb3f  jnz     loc_18000CC69
0x18000cb45  mov     r8, [rsi+r13*8]; Source
0x18000cb49  xor     eax, eax
0x18000cb4b  mov     [rbp+var_10], eax
0x18000cb4e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000cb52  mov     [rbp+var_C], eax
0x18000cb55  inc     r9; MaxCount
0x18000cb58  cmp     [r8+r9*2], ax
0x18000cb5d  jnz     short loc_18000CB55
0x18000cb5f  mov     rcx, [r14]
0x18000cb62  mov     edx, 104h; SizeInWords
0x18000cb67  movsxd  rax, edi
0x18000cb6a  imul    rbx, rax, 420h
0x18000cb71  add     rcx, rbx; Destination
0x18000cb74  call    cs:__imp_wcsncpy_s
0x18000cb7a  mov     rcx, [rsi+r13*8+8]; unsigned __int16 *
0x18000cb7f  call    ?StringToFileTime@@YA?AU_FILETIME@@PEBG@Z; StringToFileTime(ushort const *)
0x18000cb84  mov     rcx, [r14]
0x18000cb87  xor     r13d, r13d
0x18000cb8a  mov     [rbx+rcx+418h], rax
0x18000cb92  lea     rcx, [rbp+var_10]
0x18000cb96  mov     rax, [r14]
0x18000cb99  mov     [rsp+50h+var_30], rcx
0x18000cb9e  mov     rcx, r15
0x18000cba1  mov     [rbx+rax+410h], r13d
0x18000cba9  mov     rax, [r14]
0x18000cbac  mov     [rbx+rax+414h], r13d
0x18000cbb4  mov     rax, [r15]
0x18000cbb7  mov     r9d, [rbp+var_20]
0x18000cbbb  mov     r8d, [rbp+var_1C]
0x18000cbbf  mov     edx, [rbp+var_18]
0x18000cbc2  mov     rax, [rax+48h]
0x18000cbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbcb  test    eax, eax
0x18000cbcd  js      short loc_18000CBD9
0x18000cbcf  mov     eax, [rbp+var_10]
0x18000cbd2  cmp     [rbp+arg_18], eax
0x18000cbd5  jz      short loc_18000CBDF
0x18000cbd7  jmp     short loc_18000CBED
0x18000cbd9  cmp     [rbp+arg_18], r13d
0x18000cbdd  jnz     short loc_18000CBED
0x18000cbdf  mov     rax, [r14]
0x18000cbe2  mov     dword ptr [rbx+rax+410h], 1
0x18000cbed  mov     rax, [r15]
0x18000cbf0  lea     rcx, [rbp+var_C]
0x18000cbf4  mov     r9d, [rbp+var_20]
0x18000cbf8  mov     r8d, [rbp+var_1C]
0x18000cbfc  mov     edx, [rbp+var_18]
0x18000cbff  mov     rax, [rax+68h]
0x18000cc03  mov     [rsp+50h+var_30], rcx
0x18000cc08  mov     rcx, r15
0x18000cc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc10  test    eax, eax
0x18000cc12  js      short loc_18000CC35
0x18000cc14  mov     eax, [rbp+var_C]
0x18000cc17  cmp     [rbp+arg_18], eax
0x18000cc1a  jnz     short loc_18000CC35
0x18000cc1c  mov     rax, [r14]
0x18000cc1f  mov     ecx, 1
0x18000cc24  mov     [rbx+rax+414h], ecx
0x18000cc2b  mov     rax, [r14]
0x18000cc2e  mov     [rbx+rax+410h], ecx
0x18000cc35  mov     eax, [rbp+var_20]
0x18000cc38  lea     r8, aDDD; "%d.%d.%d"
0x18000cc3f  mov     rcx, [r14]
0x18000cc42  mov     edx, 104h; unsigned __int64
0x18000cc47  mov     r9d, [rbp+var_18]
0x18000cc4b  add     rcx, 208h
0x18000cc52  mov     dword ptr [rsp+50h+var_28], eax
0x18000cc56  add     rcx, rbx; unsigned __int16 *
0x18000cc59  mov     eax, [rbp+var_1C]
0x18000cc5c  mov     dword ptr [rsp+50h+var_30], eax
0x18000cc60  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cc65  inc     edi
0x18000cc67  jmp     short loc_18000CC6C
0x18000cc69  xor     r13d, r13d
0x18000cc6c  mov     eax, [rbp+arg_10]
0x18000cc6f  inc     r12d
0x18000cc72  cmp     r12d, eax
0x18000cc75  jb      loc_18000CB08
0x18000cc7b  mov     edi, [rbp+var_8]
0x18000cc7e  jmp     short loc_18000CC8A
0x18000cc80  mov     edi, 8007000Eh
0x18000cc85  jmp     short loc_18000CC8A
0x18000cc87  xor     r13d, r13d
0x18000cc8a  mov     r14d, r13d
0x18000cc8d  test    eax, eax
0x18000cc8f  jz      short loc_18000CCB5
0x18000cc91  movsxd  rbx, r14d
0x18000cc94  add     rbx, rbx
0x18000cc97  mov     rcx, [rsi+rbx*8]; pv
0x18000cc9b  call    cs:__imp_CoTaskMemFree
0x18000cca1  mov     rcx, [rsi+rbx*8+8]; pv
0x18000cca6  call    cs:__imp_CoTaskMemFree
0x18000ccac  inc     r14d
0x18000ccaf  cmp     r14d, [rbp+arg_10]
0x18000ccb3  jb      short loc_18000CC91
0x18000ccb5  mov     rcx, rsi; pv
0x18000ccb8  call    cs:__imp_CoTaskMemFree
0x18000ccbe  jmp     short loc_18000CCC5
0x18000ccc0  mov     edi, 8007000Eh
0x18000ccc5  mov     eax, edi
0x18000ccc7  mov     rbx, [rsp+50h+arg_0]
0x18000cccf  add     rsp, 50h
0x18000ccd3  pop     r15
0x18000ccd5  pop     r14
0x18000ccd7  pop     r13
0x18000ccd9  pop     r12
0x18000ccdb  pop     rdi
0x18000ccdc  pop     rsi
0x18000ccdd  pop     rbp
0x18000ccde  retn
```
