# RoutingMgr::SerializeRoutingEntries(std::vector<ExtendedRoutingEntry,std::allocator<ExtendedRoutingEntry>> const &,_AppletIdGroupRegistration * *,ulong *)

- ea: `0x180033900`
- end: `0x180033d4e`
- name: `?SerializeRoutingEntries@RoutingMgr@@AEAAJAEBV?$vector@UExtendedRoutingEntry@@V?$allocator@UExtendedRoutingEntry@@@std@@@std@@PEAPEAU_AppletIdGroupRegistration@@PEAK@Z`
- size: `1102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010ee0`

## callees

- `0x1800049a0`
- `0x1800057c6`
- `0x180005840`
- `0x18000c964`
- `0x180013274`
- `0x18002e634`
- `0x18002e6dc`
- `0x18002ede8`
- `0x18003159c`
- `0x180033900`
- `0x18003806c`
- `0x18007a1a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180033c82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180033c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033b67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033b67`

## string_xrefs

- `0x180033ca6`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180033cd4`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RoutingMgr::SerializeRoutingEntries(RoutingMgr *a1, __int64 *a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v5; // r13d
  __int64 v6; // rbx
  _BYTE *v7; // r14
  __int64 v8; // rsi
  __m128i si128; // xmm6
  __int64 v10; // r15
  __int64 v11; // rcx
  __int16 *v12; // r8
  __int64 v13; // rdx
  _WORD *v14; // rax
  __int16 v15; // r9
  _WORD *v16; // rcx
  unsigned int v17; // ebx
  const WCHAR *v18; // rcx
  unsigned int v19; // eax
  const void *v20; // rdi
  unsigned int v21; // ebx
  void *v22; // rax
  __int64 *unique; // rax
  __int64 v24; // rcx
  void *v25; // rcx
  unsigned int i; // ebx
  __int64 v27; // rcx
  unsigned __int64 v28; // rax
  LPVOID v29; // rax
  __int64 v30; // r8
  unsigned int v31; // r10d
  __int64 v32; // rdx
  _OWORD *v33; // rcx
  int SmartcardInterfaceInfoNameForRegistration; // eax
  const WCHAR *v35; // rcx
  __int64 v36; // rdx
  void *v38; // [rsp+28h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-61h] BYREF
  LPVOID v40; // [rsp+38h] [rbp-59h] BYREF
  __int64 v41; // [rsp+40h] [rbp-51h]
  RoutingMgr *v42; // [rsp+48h] [rbp-49h]
  __int64 v43; // [rsp+50h] [rbp-41h]
  _QWORD *v44; // [rsp+58h] [rbp-39h]
  _DWORD *v45; // [rsp+60h] [rbp-31h]
  PCNZWCH sourceString[2]; // [rsp+68h] [rbp-29h] BYREF
  __m128i v47; // [rsp+78h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v45 = a4;
  v44 = a3;
  v42 = a1;
  v5 = 0;
  v6 = 0x21CFB2B78C13521DLL * ((a2[1] - *a2) >> 3);
  wil::make_unique_cotaskmem<_AppletIdGroupRegistration [0]>(&pv, v6);
  v7 = pv;
  v40 = pv;
  v41 = v6;
  v8 = *a2;
  v43 = a2[1];
  if ( v8 == v43 )
  {
LABEL_37:
    v40 = 0;
    v41 = 0;
    *v44 = v7;
    *v45 = -1944890851 * ((a2[1] - *a2) >> 3);
    v17 = 0;
  }
  else
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v10 = 232LL * v5;
      *(_DWORD *)&v7[v10] = *(_DWORD *)(v8 + 152);
      *(_OWORD *)&v7[v10 + 4] = *(_OWORD *)(v8 + 132);
      *(_DWORD *)&v7[v10 + 24] = *(_DWORD *)(v8 + 148);
      *(_DWORD *)&v7[v10 + 28] = *(_DWORD *)(v8 + 156);
      v7[v10 + 32] = *(_BYTE *)(v8 + 338);
      v7[v10 + 192] = *(_BYTE *)(v8 + 200);
      v11 = 2147483646;
      v12 = (__int16 *)(v8 + 208);
      v13 = 65;
      v14 = &v7[v10 + 34];
      do
      {
        if ( !v11 )
          break;
        v15 = *v12;
        if ( !*v12 )
          break;
        ++v12;
        *v14++ = v15;
        --v11;
        --v13;
      }
      while ( v13 );
      v16 = v14 - 1;
      if ( v13 )
        v16 = v14;
      *v16 = 0;
      v17 = v13 == 0 ? 0x8007007A : 0;
      if ( !v13 )
      {
        v36 = 449;
        goto LABEL_35;
      }
      v18 = (const WCHAR *)(v8 + 344);
      if ( *(_QWORD *)(v8 + 368) > 7u )
        v18 = *(const WCHAR **)v18;
      *(_QWORD *)&v7[v10 + 200] = MakeHSTRING(v18);
      v19 = *(_DWORD *)(v8 + 384) - *(_DWORD *)(v8 + 376);
      *(_DWORD *)&v7[v10 + 176] = v19;
      if ( v19 )
      {
        v20 = *(const void **)(v8 + 376);
        v21 = v19;
        wil::make_unique_cotaskmem<unsigned char [0]>(&v38, v19);
        memcpy_0(v38, v20, v21);
        v22 = v38;
        v38 = 0;
        *(_QWORD *)&v7[v10 + 184] = v22;
      }
      *(_DWORD *)&v7[v10 + 208] = (__int64)(*(_QWORD *)(v8 + 408) - *(_QWORD *)(v8 + 400)) >> 5;
      unique = (__int64 *)wil::make_unique_cotaskmem<HSTRING__ * [0]>(&pv);
      v24 = *unique;
      *unique = 0;
      *(_QWORD *)&v7[v10 + 216] = v24;
      v25 = pv;
      pv = 0;
      if ( v25 )
        CoTaskMemFree(v25);
      for ( i = 0; i < *(_DWORD *)&v7[v10 + 208]; ++i )
      {
        v27 = *(_QWORD *)(v8 + 400) + 32LL * i;
        if ( *(_QWORD *)(v27 + 24) > 7u )
          v27 = *(_QWORD *)v27;
        *(_QWORD *)(*(_QWORD *)&v7[v10 + 216] + 8LL * i) = MakeHSTRING((PCNZWCH)v27);
      }
      v28 = 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(v8 + 168) - *(_QWORD *)(v8 + 160)) >> 2);
      *(_DWORD *)&v7[v10 + 164] = v28;
      v29 = CoTaskMemAlloc((unsigned int)(20 * v28));
      *(_QWORD *)&v7[v10 + 168] = v29;
      if ( !v29 )
      {
        v17 = -2147024882;
        v36 = 467;
        goto LABEL_35;
      }
      v30 = *(_QWORD *)(v8 + 160);
      if ( 0x8E38E38E38E38E39uLL * ((*(_QWORD *)(v8 + 168) - v30) >> 2) )
        break;
LABEL_26:
      *(_OWORD *)sourceString = 0;
      v47 = si128;
      LOWORD(sourceString[0]) = 0;
      SmartcardInterfaceInfoNameForRegistration = RoutingMgr::GetSmartcardInterfaceInfoNameForRegistration(
                                                    v42,
                                                    (const struct _GUID *)(v8 + 132),
                                                    (const unsigned __int16 *)v8,
                                                    (__int64)sourceString);
      v17 = SmartcardInterfaceInfoNameForRegistration;
      if ( SmartcardInterfaceInfoNameForRegistration < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E3,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
          (const char *)(unsigned int)SmartcardInterfaceInfoNameForRegistration,
          (int)v38);
        std::wstring::~wstring(sourceString);
        goto LABEL_38;
      }
      v35 = (const WCHAR *)sourceString;
      if ( v47.m128i_i64[1] > 7uLL )
        v35 = sourceString[0];
      *(_QWORD *)&v7[v10 + 224] = MakeHSTRING(v35);
      std::wstring::~wstring(sourceString);
      v8 += 424;
      if ( v8 == v43 )
        goto LABEL_37;
      ++v5;
    }
    v31 = 0;
    while ( 1 )
    {
      v32 = 5LL * v31;
      *(_DWORD *)(*(_QWORD *)&v7[v10 + 168] + 4 * v32) = *(_DWORD *)(v30 + 36LL * v31 + 16);
      v33 = (_OWORD *)(*(_QWORD *)&v7[v10 + 168] + 4 * (v32 + 1));
      if ( !v33 )
        break;
      v32 = *(_QWORD *)(v8 + 160) + 4 * (9LL * v31 + 5);
      if ( !v32 )
      {
        *v33 = 0;
        break;
      }
      *v33 = *(_OWORD *)v32;
      ++v31;
      v30 = *(_QWORD *)(v8 + 160);
      if ( v31 >= 0x8E38E38E38E38E39uLL * ((*(_QWORD *)(v8 + 168) - v30) >> 2) )
        goto LABEL_26;
    }
    *(_DWORD *)_o__errno(v33, v32, v30) = 22;
    invalid_parameter_noinfo();
    v17 = -2147418113;
    v36 = 478;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
      (const char *)v17,
      (int)v38);
  }
LABEL_38:
  wil::unique_any_array_ptr<_AppletIdGroupRegistration,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (_AppletIdGroupRegistration *),&void FreeAppletIdGroupRegistration(_AppletIdGroupRegistration *)>,unsigned __int64>::~unique_any_array_ptr<_AppletIdGroupRegistration,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (_AppletIdGroupRegistration *),&void FreeAppletIdGroupRegistration(_AppletIdGroupRegistration *)>,unsigned __int64>(&v40);
  return v17;
}

```

## disassembly

```asm
0x180033900  mov     rax, rsp
0x180033903  push    rbp
0x180033904  push    rbx
0x180033905  push    rsi
0x180033906  push    rdi
0x180033907  push    r12
0x180033909  push    r13
0x18003390b  push    r14
0x18003390d  push    r15
0x18003390f  lea     rbp, [rax-5Fh]
0x180033913  sub     rsp, 0A8h
0x18003391a  movaps  xmmword ptr [rax-58h], xmm6
0x18003391e  mov     rax, cs:__security_cookie
0x180033925  xor     rax, rsp
0x180033928  mov     [rbp+57h+var_60], rax
0x18003392c  mov     [rbp+57h+var_88], r9
0x180033930  mov     [rbp+57h+var_90], r8
0x180033934  mov     r12, rdx
0x180033937  mov     [rbp+57h+var_A0], rcx
0x18003393b  xor     edi, edi
0x18003393d  mov     r13d, edi
0x180033940  mov     rbx, [rdx+8]
0x180033944  sub     rbx, [rdx]
0x180033947  sar     rbx, 3
0x18003394b  mov     rax, 21CFB2B78C13521Dh
0x180033955  imul    rbx, rax
0x180033959  mov     rdx, rbx
0x18003395c  lea     rcx, [rbp+57h+pv]
0x180033960  call    ??$make_unique_cotaskmem@$$BY0A@U_AppletIdGroupRegistration@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_AppletIdGroupRegistration@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_AppletIdGroupRegistration [0]>(unsigned __int64)
0x180033965  mov     r14, [rbp+57h+pv]
0x180033969  mov     [rbp+57h+var_B0], r14
0x18003396d  mov     [rbp+57h+var_A8], rbx
0x180033971  mov     rsi, [r12]
0x180033975  mov     rax, [r12+8]
0x18003397a  mov     [rbp+57h+var_98], rax
0x18003397e  cmp     rsi, rax
0x180033981  jz      loc_180033CE9
0x180033987  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003398f  mov     eax, r13d
0x180033992  imul    r15, rax, 0E8h
0x180033999  mov     eax, [rsi+98h]
0x18003399f  mov     [r15+r14], eax
0x1800339a3  movups  xmm0, xmmword ptr [rsi+84h]
0x1800339aa  movdqu  xmmword ptr [r15+r14+4], xmm0
0x1800339b1  mov     eax, [rsi+94h]
0x1800339b7  mov     [r15+r14+18h], eax
0x1800339bc  mov     eax, [rsi+9Ch]
0x1800339c2  mov     [r15+r14+1Ch], eax
0x1800339c7  mov     al, [rsi+152h]
0x1800339cd  mov     [r15+r14+20h], al
0x1800339d2  mov     al, [rsi+0C8h]
0x1800339d8  mov     [r15+r14+0C0h], al
0x1800339e0  mov     ecx, 7FFFFFFEh
0x1800339e5  lea     r8, [rsi+0D0h]
0x1800339ec  mov     edx, 41h ; 'A'
0x1800339f1  lea     rax, [r14+22h]
0x1800339f5  add     rax, r15
0x1800339f8  test    rcx, rcx
0x1800339fb  jz      short loc_180033A1C
0x1800339fd  movzx   r9d, word ptr [r8]
0x180033a01  test    r9w, r9w
0x180033a05  jz      short loc_180033A1C
0x180033a07  add     r8, 2
0x180033a0b  mov     [rax], r9w
0x180033a0f  add     rax, 2
0x180033a13  dec     rcx
0x180033a16  sub     rdx, 1
0x180033a1a  jnz     short loc_1800339F8
0x180033a1c  lea     rcx, [rax-2]
0x180033a20  test    rdx, rdx
0x180033a23  cmovnz  rcx, rax
0x180033a27  mov     [rcx], di
0x180033a2a  mov     rax, rdx
0x180033a2d  neg     rax
0x180033a30  sbb     ebx, ebx
0x180033a32  not     ebx
0x180033a34  and     ebx, 8007007Ah
0x180033a3a  test    rdx, rdx
0x180033a3d  jz      loc_180033CE2
0x180033a43  lea     rcx, [rsi+158h]
0x180033a4a  cmp     qword ptr [rsi+170h], 7
0x180033a52  jbe     short loc_180033A57
0x180033a54  mov     rcx, [rcx]; sourceString
0x180033a57  call    ?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z; MakeHSTRING(ushort const *)
0x180033a5c  mov     [r15+r14+0C8h], rax
0x180033a64  mov     eax, [rsi+180h]
0x180033a6a  sub     eax, [rsi+178h]
0x180033a70  mov     [r15+r14+0B0h], eax
0x180033a78  jz      short loc_180033AAF
0x180033a7a  mov     rdi, [rsi+178h]
0x180033a81  mov     ebx, eax
0x180033a83  mov     edx, eax
0x180033a85  lea     rcx, [rbp+57h+var_C0]
0x180033a89  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x180033a8e  mov     r8d, ebx; Size
0x180033a91  mov     rdx, rdi; Src
0x180033a94  mov     rcx, [rbp+57h+var_C0]; void *
0x180033a98  call    memcpy_0
0x180033a9d  mov     rax, [rbp+57h+var_C0]
0x180033aa1  xor     edi, edi
0x180033aa3  mov     [rbp+57h+var_C0], rdi
0x180033aa7  mov     [r15+r14+0B8h], rax
0x180033aaf  mov     rdx, [rsi+198h]
0x180033ab6  sub     rdx, [rsi+190h]
0x180033abd  sar     rdx, 5
0x180033ac1  mov     edx, edx
0x180033ac3  mov     [r15+r14+0D0h], edx
0x180033acb  lea     rcx, [rbp+57h+pv]
0x180033acf  call    ??$make_unique_cotaskmem@$$BY0A@PEAUHSTRING__@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAUHSTRING__@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<HSTRING__ * [0]>(unsigned __int64)
0x180033ad4  mov     rcx, [rax]
0x180033ad7  mov     [rax], rdi
0x180033ada  mov     [r15+r14+0D8h], rcx
0x180033ae2  mov     rcx, [rbp+57h+pv]; pv
0x180033ae6  mov     [rbp+57h+pv], rdi
0x180033aea  test    rcx, rcx
0x180033aed  jz      short loc_180033AF5
0x180033aef  call    cs:__imp_CoTaskMemFree
0x180033af5  mov     ebx, edi
0x180033af7  cmp     [r15+r14+0D0h], edi
0x180033aff  jbe     short loc_180033B39
0x180033b01  mov     edi, ebx
0x180033b03  mov     ecx, ebx
0x180033b05  shl     rcx, 5
0x180033b09  add     rcx, [rsi+190h]
0x180033b10  cmp     qword ptr [rcx+18h], 7
0x180033b15  jbe     short loc_180033B1A
0x180033b17  mov     rcx, [rcx]; sourceString
0x180033b1a  call    ?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z; MakeHSTRING(ushort const *)
0x180033b1f  mov     rcx, [r15+r14+0D8h]
0x180033b27  mov     [rcx+rdi*8], rax
0x180033b2b  inc     ebx
0x180033b2d  cmp     ebx, [r15+r14+0D0h]
0x180033b35  jb      short loc_180033B01
0x180033b37  xor     edi, edi
0x180033b39  mov     rax, [rsi+0A8h]
0x180033b40  sub     rax, [rsi+0A0h]
0x180033b47  sar     rax, 2
0x180033b4b  mov     rbx, 8E38E38E38E38E39h
0x180033b55  imul    rax, rbx
0x180033b59  mov     [r15+r14+0A4h], eax
0x180033b61  lea     ecx, [rax+rax*4]
0x180033b64  shl     ecx, 2; cb
0x180033b67  call    cs:__imp_CoTaskMemAlloc
0x180033b6d  mov     [r15+r14+0A8h], rax
0x180033b75  test    rax, rax
0x180033b78  jz      loc_180033CC3
0x180033b7e  mov     r8, [rsi+0A0h]
0x180033b85  mov     rax, [rsi+0A8h]
0x180033b8c  sub     rax, r8
0x180033b8f  sar     rax, 2
0x180033b93  imul    rax, rbx
0x180033b97  test    rax, rax
0x180033b9a  jz      short loc_180033C16
0x180033b9c  mov     r10d, edi
0x180033b9f  mov     eax, r10d
0x180033ba2  lea     r9, [rax+rax*8]
0x180033ba6  lea     rdx, [rax+rax*4]
0x180033baa  mov     rcx, [r15+r14+0A8h]
0x180033bb2  mov     eax, [r8+r9*4+10h]
0x180033bb7  mov     [rcx+rdx*4], eax
0x180033bba  mov     rax, [r15+r14+0A8h]
0x180033bc2  lea     rcx, [rdx+1]
0x180033bc6  lea     rcx, [rax+rcx*4]
0x180033bca  test    rcx, rcx
0x180033bcd  jz      loc_180033C82
0x180033bd3  mov     rax, [rsi+0A0h]
0x180033bda  lea     rdx, [r9+5]
0x180033bde  lea     rdx, [rax+rdx*4]
0x180033be2  test    rdx, rdx
0x180033be5  jz      loc_180033C7C
0x180033beb  movups  xmm0, xmmword ptr [rdx]
0x180033bee  movdqu  xmmword ptr [rcx], xmm0
0x180033bf2  inc     r10d
0x180033bf5  mov     r8, [rsi+0A0h]
0x180033bfc  mov     rcx, [rsi+0A8h]
0x180033c03  sub     rcx, r8
0x180033c06  sar     rcx, 2
0x180033c0a  imul    rcx, rbx
0x180033c0e  mov     eax, r10d
0x180033c11  cmp     rax, rcx
0x180033c14  jb      short loc_180033B9F
0x180033c16  xorps   xmm0, xmm0
0x180033c19  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180033c1d  movdqu  [rbp+57h+var_70], xmm6
0x180033c22  mov     word ptr [rbp+57h+sourceString], di
0x180033c26  lea     r9, [rbp+57h+sourceString]
0x180033c2a  mov     r8, rsi
0x180033c2d  lea     rdx, [rsi+84h]
0x180033c34  mov     rcx, [rbp+57h+var_A0]
0x180033c38  call    ?GetSmartcardInterfaceInfoNameForRegistration@RoutingMgr@@AEAAJAEBU_GUID@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RoutingMgr::GetSmartcardInterfaceInfoNameForRegistration(_GUID const &,ushort const *,std::wstring *)
0x180033c3d  mov     ebx, eax
0x180033c3f  test    eax, eax
0x180033c41  js      short loc_180033C9F
0x180033c43  lea     rcx, [rbp+57h+sourceString]
0x180033c47  cmp     qword ptr [rbp+57h+var_70+8], 7
0x180033c4c  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x180033c51  call    ?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z; MakeHSTRING(ushort const *)
0x180033c56  mov     [r15+r14+0E0h], rax
0x180033c5e  lea     rcx, [rbp+57h+sourceString]
0x180033c62  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033c67  add     rsi, 1A8h
0x180033c6e  cmp     rsi, [rbp+57h+var_98]
0x180033c72  jz      short loc_180033CE9
0x180033c74  inc     r13d
0x180033c77  jmp     loc_18003398F
0x180033c7c  xorps   xmm0, xmm0
0x180033c7f  movups  xmmword ptr [rcx], xmm0
0x180033c82  call    cs:__imp__o__errno
0x180033c88  mov     dword ptr [rax], 16h
0x180033c8e  call    _invalid_parameter_noinfo
0x180033c93  mov     ebx, 8000FFFFh
0x180033c98  mov     edx, 1DEh
0x180033c9d  jmp     short loc_180033CCD
0x180033c9f  mov     rcx, [rbp+5Fh]; this
0x180033ca3  mov     r9d, eax; char *
0x180033ca6  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180033cad  mov     edx, 1E3h; void *
0x180033cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033cb7  nop
0x180033cb8  lea     rcx, [rbp+57h+sourceString]
0x180033cbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033cc1  jmp     short loc_180033D1B
0x180033cc3  mov     ebx, 8007000Eh
0x180033cc8  mov     edx, 1D3h; void *
0x180033ccd  mov     rcx, [rbp+5Fh]; this
0x180033cd1  mov     r9d, ebx; char *
0x180033cd4  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180033cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ce0  jmp     short loc_180033D1B
0x180033ce2  mov     edx, 1C1h
0x180033ce7  jmp     short loc_180033CCD
0x180033ce9  mov     [rbp+57h+var_B0], rdi
0x180033ced  mov     [rbp+57h+var_A8], rdi
0x180033cf1  mov     rax, [rbp+57h+var_90]
0x180033cf5  mov     [rax], r14
0x180033cf8  mov     rax, [r12+8]
0x180033cfd  sub     rax, [r12]
0x180033d01  sar     rax, 3
0x180033d05  mov     rcx, 21CFB2B78C13521Dh
0x180033d0f  imul    rax, rcx
0x180033d13  mov     rcx, [rbp+57h+var_88]
0x180033d17  mov     [rcx], eax
0x180033d19  mov     ebx, edi
0x180033d1b  lea     rcx, [rbp+57h+var_B0]
0x180033d1f  call    ??1?$unique_any_array_ptr@U_AppletIdGroupRegistration@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@$$A6AXPEAU_AppletIdGroupRegistration@@@Z$1?FreeAppletIdGroupRegistration@@YAX0@Z@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_AppletIdGroupRegistration,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (_AppletIdGroupRegistration *),&FreeAppletIdGroupRegistration(_AppletIdGroupRegistration *)>,unsigned __int64>::~unique_any_array_ptr<_AppletIdGroupRegistration,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (_AppletIdGroupRegistration *),&FreeAppletIdGroupRegistration(_AppletIdGroupRegistration *)>,unsigned __int64>(void)
0x180033d24  mov     eax, ebx
0x180033d26  mov     rcx, [rbp+57h+var_60]
0x180033d2a  xor     rcx, rsp; StackCookie
0x180033d2d  call    __security_check_cookie
0x180033d32  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180033d3a  add     rsp, 0A8h
0x180033d41  pop     r15
0x180033d43  pop     r14
0x180033d45  pop     r13
0x180033d47  pop     r12
0x180033d49  pop     rdi
0x180033d4a  pop     rsi
0x180033d4b  pop     rbx
0x180033d4c  pop     rbp
0x180033d4d  retn
```
