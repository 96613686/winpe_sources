# WsTrustResponseParser::ParsePasswordChangeUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180083b60`
- end: `0x180083ec9`
- name: `?ParsePasswordChangeUrl@WsTrustResponseParser@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c7cc`

## callees

- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x1800090d0`
- `0x18000c7ac`
- `0x180042930`
- `0x18004b1b4`
- `0x18004b8c0`
- `0x180066750`
- `0x180066838`
- `0x180066e24`
- `0x180071e14`
- `0x180083b60`
- `0x180084240`
- `0x1800844ec`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083d26`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180083d26`
- `XmlLite!CreateXmlReader` at `0x180083c36`
- `XmlLite!CreateXmlReader` at `0x180083c36`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WsTrustResponseParser::ParsePasswordChangeUrl(_QWORD *a1, _QWORD *a2)
{
  HRESULT ElementValue; // edi
  __int64 v5; // r14
  int v6; // eax
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r14d
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  int *v14; // rsi
  __int64 v15; // rbx
  int v17; // [rsp+30h] [rbp-40h]
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h] BYREF
  __int64 v21; // [rsp+68h] [rbp-8h] BYREF
  int v22; // [rsp+A0h] [rbp+30h] BYREF
  void *ppvObject; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+48h] BYREF

  ElementValue = 0;
  v22 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v18);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v24);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v21);
  ppvObject = 0;
  v19 = 0;
  v20 = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  if ( !*(_DWORD *)(*a1 - 16LL) )
    goto LABEL_33;
  ElementValue = SequentialStream::FromString(a1, &v20);
  if ( ElementValue < 0 )
  {
    v17 = 171;
LABEL_4:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ElementValue, "wstrustresponseparser.cpp", v17, "HRESULT", &base);
    goto LABEL_33;
  }
  ATL::CComPtrBase<ISequentialStream>::Attach(&v19, v20);
  ElementValue = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( ElementValue < 0 )
  {
    v17 = 175;
    goto LABEL_4;
  }
  ElementValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v19);
  if ( ElementValue < 0 )
  {
    v17 = 176;
    goto LABEL_4;
  }
  ElementValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( ElementValue < 0 )
  {
    v17 = 178;
    goto LABEL_4;
  }
  while ( 1 )
  {
    ElementValue = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v22);
    if ( ElementValue )
      break;
    switch ( v22 )
    {
      case 1:
        WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(ppvObject, &v18, 1);
        if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
          goto LABEL_20;
        break;
      case 3:
        if ( !(unsigned int)_o__wcsicmp(v18, L"/S:Text") )
        {
          ElementValue = WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(ppvObject, &v24);
          if ( ElementValue < 0 )
          {
            v17 = 200;
            goto LABEL_4;
          }
        }
        break;
      case 15:
LABEL_20:
        WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(ppvObject, &v18, 0);
        break;
    }
  }
  v5 = v24;
  if ( *(_DWORD *)(v24 - 16) )
  {
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
           &v24,
           L"https://",
           0);
    v7 = v6;
    if ( v6 > -1 )
    {
      v8 = v6;
      v9 = *(_DWORD *)(v5 - 16);
      if ( v6 < v9 )
      {
        do
        {
          v10 = ATL::CSimpleStringT<unsigned short,0>::operator[](&v24, (unsigned int)v8);
          if ( (unsigned __int16)v10 <= 0x3Bu )
          {
            v11 = 0x800100100000000LL;
            if ( _bittest64(&v11, v10) )
              break;
          }
          ++v8;
        }
        while ( v8 < v9 );
      }
      v12 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                         &v24,
                         &v20,
                         v7,
                         v8 - v7);
      v13 = (_QWORD *)(v12 - 24);
      v14 = (int *)(*a2 - 24LL);
      if ( (int *)(v12 - 24) != v14 )
      {
        if ( v14[4] >= 0 && *v13 == *(_QWORD *)v14 )
        {
          v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
          ATL::CStringData::Release((ATL::CStringData *)v14);
          *a2 = v15 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v12, *(unsigned int *)(v12 - 16));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
    }
  }
LABEL_33:
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>(&v19);
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>((__int64 *)&ppvObject);
  ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  return (unsigned int)ElementValue;
}

```

## disassembly

```asm
0x180083b60  mov     [rsp-28h+arg_8], rbx
0x180083b65  push    rbp
0x180083b66  push    rsi
0x180083b67  push    rdi
0x180083b68  push    r14
0x180083b6a  push    r15
0x180083b6c  mov     rbp, rsp
0x180083b6f  sub     rsp, 70h
0x180083b73  mov     r15, rdx
0x180083b76  mov     rbx, rcx
0x180083b79  xor     edi, edi
0x180083b7b  mov     [rbp+arg_0], edi
0x180083b7e  lea     rcx, [rbp+var_20]; void *
0x180083b82  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180083b87  nop
0x180083b88  lea     rcx, [rbp+arg_18]; void *
0x180083b8c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180083b91  nop
0x180083b92  lea     rcx, [rbp+var_8]; void *
0x180083b96  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180083b9b  nop
0x180083b9c  mov     [rbp+ppvObject], rdi
0x180083ba0  mov     [rbp+var_18], rdi
0x180083ba4  mov     [rbp+var_10], rdi
0x180083ba8  mov     rcx, r15
0x180083bab  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180083bb0  mov     rax, [rbx]
0x180083bb3  cmp     [rax-10h], edi
0x180083bb6  jz      loc_180083E76
0x180083bbc  lea     rdx, [rbp+var_10]
0x180083bc0  mov     rcx, rbx
0x180083bc3  call    ?FromString@SequentialStream@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAUISequentialStream@@H@Z; SequentialStream::FromString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ISequentialStream * *,int)
0x180083bc8  mov     edi, eax
0x180083bca  test    eax, eax
0x180083bcc  jns     short loc_180083C1B
0x180083bce  lea     rax, base
0x180083bd5  mov     [rsp+70h+var_30], rax
0x180083bda  lea     rax, aHresult; "HRESULT"
0x180083be1  mov     [rsp+70h+var_38], rax
0x180083be6  mov     [rsp+70h+var_40], 0ABh
0x180083bee  mov     ebx, 2
0x180083bf3  lea     rax, aOnecoreuapDsEx_45+25h; "wstrustresponseparser.cpp"
0x180083bfa  mov     [rsp+70h+var_48], rax
0x180083bff  mov     [rsp+70h+var_50], edi
0x180083c03  mov     r9d, ebx
0x180083c06  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180083c0d  xor     edx, edx
0x180083c0f  mov     ecx, ebx
0x180083c11  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180083c16  jmp     loc_180083E76
0x180083c1b  mov     rdx, [rbp+var_10]
0x180083c1f  lea     rcx, [rbp+var_18]
0x180083c23  call    ?Attach@?$CComPtrBase@UISequentialStream@@@ATL@@QEAAXPEAUISequentialStream@@@Z; ATL::CComPtrBase<ISequentialStream>::Attach(ISequentialStream *)
0x180083c28  xor     r8d, r8d; pMalloc
0x180083c2b  lea     rdx, [rbp+ppvObject]; ppvObject
0x180083c2f  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180083c36  call    cs:__imp_CreateXmlReader
0x180083c3c  mov     edi, eax
0x180083c3e  test    eax, eax
0x180083c40  jns     short loc_180083C64
0x180083c42  lea     rax, base
0x180083c49  mov     [rsp+70h+var_30], rax
0x180083c4e  lea     rax, aHresult; "HRESULT"
0x180083c55  mov     [rsp+70h+var_38], rax
0x180083c5a  mov     [rsp+70h+var_40], 0AFh
0x180083c62  jmp     short loc_180083BEE
0x180083c64  mov     rcx, [rbp+ppvObject]
0x180083c68  mov     rax, [rcx]
0x180083c6b  mov     rdx, [rbp+var_18]
0x180083c6f  mov     rax, [rax+18h]
0x180083c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c78  mov     edi, eax
0x180083c7a  test    eax, eax
0x180083c7c  jns     short loc_180083CA3
0x180083c7e  lea     rax, base
0x180083c85  mov     [rsp+70h+var_30], rax
0x180083c8a  lea     rax, aHresult; "HRESULT"
0x180083c91  mov     [rsp+70h+var_38], rax
0x180083c96  mov     [rsp+70h+var_40], 0B0h
0x180083c9e  jmp     loc_180083BEE
0x180083ca3  mov     rcx, [rbp+ppvObject]
0x180083ca7  mov     rax, [rcx]
0x180083caa  xor     r8d, r8d
0x180083cad  lea     edx, [r8+4]
0x180083cb1  mov     rax, [rax+28h]
0x180083cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083cba  mov     edi, eax
0x180083cbc  mov     ebx, 2
0x180083cc1  test    eax, eax
0x180083cc3  jns     short loc_180083CEA
0x180083cc5  lea     rax, base
0x180083ccc  mov     [rsp+70h+var_30], rax
0x180083cd1  lea     rax, aHresult; "HRESULT"
0x180083cd8  mov     [rsp+70h+var_38], rax
0x180083cdd  mov     [rsp+70h+var_40], 0B2h
0x180083ce5  jmp     loc_180083BF3
0x180083cea  mov     rcx, [rbp+ppvObject]
0x180083cee  mov     rax, [rcx]
0x180083cf1  lea     rdx, [rbp+arg_0]
0x180083cf5  mov     rax, [rax+30h]
0x180083cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083cfe  mov     edi, eax
0x180083d00  test    eax, eax
0x180083d02  jnz     loc_180083DAB
0x180083d08  mov     ecx, [rbp+arg_0]
0x180083d0b  sub     ecx, 1
0x180083d0e  jz      short loc_180083D68
0x180083d10  sub     ecx, ebx
0x180083d12  jz      short loc_180083D1B
0x180083d14  cmp     ecx, 0Ch
0x180083d17  jnz     short loc_180083CEA
0x180083d19  jmp     short loc_180083D96
0x180083d1b  lea     rdx, aSText; "/S:Text"
0x180083d22  mov     rcx, [rbp+var_20]
0x180083d26  call    cs:__imp__o__wcsicmp
0x180083d2c  test    eax, eax
0x180083d2e  jnz     short loc_180083CEA
0x180083d30  lea     rdx, [rbp+arg_18]
0x180083d34  mov     rcx, [rbp+ppvObject]
0x180083d38  call    ?GetElementValue@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180083d3d  mov     edi, eax
0x180083d3f  test    eax, eax
0x180083d41  jns     short loc_180083CEA
0x180083d43  lea     rax, base
0x180083d4a  mov     [rsp+70h+var_30], rax
0x180083d4f  lea     rax, aHresult; "HRESULT"
0x180083d56  mov     [rsp+70h+var_38], rax
0x180083d5b  mov     [rsp+70h+var_40], 0C8h
0x180083d63  jmp     loc_180083BF3
0x180083d68  mov     r8d, 1
0x180083d6e  lea     rdx, [rbp+var_20]
0x180083d72  mov     rcx, [rbp+ppvObject]
0x180083d76  call    ?UpdateCurrentPath@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x180083d7b  mov     rcx, [rbp+ppvObject]
0x180083d7f  mov     rax, [rcx]
0x180083d82  mov     rax, [rax+0A0h]
0x180083d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d8e  test    eax, eax
0x180083d90  jz      loc_180083CEA
0x180083d96  xor     r8d, r8d
0x180083d99  lea     rdx, [rbp+var_20]
0x180083d9d  mov     rcx, [rbp+ppvObject]
0x180083da1  call    ?UpdateCurrentPath@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x180083da6  jmp     loc_180083CEA
0x180083dab  mov     r14, [rbp+arg_18]
0x180083daf  cmp     dword ptr [r14-10h], 0
0x180083db4  jz      loc_180083E76
0x180083dba  xor     r8d, r8d
0x180083dbd  lea     rdx, aHttps; "https://"
0x180083dc4  lea     rcx, [rbp+arg_18]
0x180083dc8  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180083dcd  mov     esi, eax
0x180083dcf  cmp     eax, 0FFFFFFFFh
0x180083dd2  jle     loc_180083E76
0x180083dd8  mov     ebx, eax
0x180083dda  mov     r14d, [r14-10h]
0x180083dde  cmp     eax, r14d
0x180083de1  jge     short loc_180083E0B
0x180083de3  mov     edx, ebx
0x180083de5  lea     rcx, [rbp+arg_18]
0x180083de9  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x180083dee  cmp     ax, 3Bh ; ';'
0x180083df2  ja      short loc_180083E04
0x180083df4  mov     rcx, 800100100000000h
0x180083dfe  bt      rcx, rax
0x180083e02  jb      short loc_180083E0B
0x180083e04  inc     ebx
0x180083e06  cmp     ebx, r14d
0x180083e09  jl      short loc_180083DE3
0x180083e0b  sub     ebx, esi
0x180083e0d  mov     r9d, ebx
0x180083e10  mov     r8d, esi
0x180083e13  lea     rdx, [rbp+var_10]
0x180083e17  lea     rcx, [rbp+arg_18]
0x180083e1b  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180083e20  nop
0x180083e21  mov     rdx, [rax]
0x180083e24  lea     rcx, [rdx-18h]
0x180083e28  mov     rsi, [r15]
0x180083e2b  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180083e2f  cmp     rcx, rsi
0x180083e32  jz      short loc_180083E68
0x180083e34  cmp     dword ptr [rsi+10h], 0
0x180083e38  jl      short loc_180083E5B
0x180083e3a  mov     rax, [rsi]
0x180083e3d  cmp     [rcx], rax
0x180083e40  jnz     short loc_180083E5B
0x180083e42  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180083e47  mov     rbx, rax
0x180083e4a  mov     rcx, rsi; this
0x180083e4d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083e52  lea     rax, [rbx+18h]
0x180083e56  mov     [r15], rax
0x180083e59  jmp     short loc_180083E68
0x180083e5b  mov     r8d, [rdx-10h]
0x180083e5f  mov     rcx, r15
0x180083e62  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180083e67  nop
0x180083e68  mov     rcx, [rbp+var_10]
0x180083e6c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180083e70  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083e75  nop
0x180083e76  lea     rcx, [rbp+var_18]
0x180083e7a  call    ??1?$CComPtrBase@UISequentialStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>(void)
0x180083e7f  nop
0x180083e80  lea     rcx, [rbp+ppvObject]
0x180083e84  call    ??1?$CComPtrBase@UISequentialStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>(void)
0x180083e89  nop
0x180083e8a  mov     rcx, [rbp+var_8]
0x180083e8e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180083e92  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083e97  nop
0x180083e98  mov     rcx, [rbp+arg_18]
0x180083e9c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180083ea0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083ea5  nop
0x180083ea6  mov     rcx, [rbp+var_20]
0x180083eaa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180083eae  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083eb3  mov     eax, edi
0x180083eb5  mov     rbx, [rsp+70h+arg_8]
0x180083ebd  add     rsp, 70h
0x180083ec1  pop     r15
0x180083ec3  pop     r14
0x180083ec5  pop     rdi
0x180083ec6  pop     rsi
0x180083ec7  pop     rbp
0x180083ec8  retn
```
