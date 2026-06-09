# I_XmlUnmarshallReference(void *,WS_CHARSET,ulong,WS_TYPE_Reference *,_CRYPT_XML_WS_STATE *,_HXML_HANDLE *,_CRYPT_XML_REFERENCE const * *)

- ea: `0x180001010`
- end: `0x180001390`
- name: `?I_XmlUnmarshallReference@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_Reference@@PEAU_CRYPT_XML_WS_STATE@@PEAU_HXML_HANDLE@@PEAPEBU_CRYPT_XML_REFERENCE@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(HANDLE hHeap, enum WS_CHARSET, unsigned int, struct WS_TYPE_Reference *, struct _CRYPT_XML_WS_STATE *, struct _HXML_HANDLE *, const struct _CRYPT_XML_REFERENCE **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001a40`
- `0x1800029b0`

## callees

- `0x180001010`
- `0x180001d00`
- `0x1800049c0`
- `0x1800070d0`
- `0x180014ce0`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800012ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001341`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800012ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001341`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001317`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001317`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001358`

## string_xrefs

- `0x180001095`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000119a`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180001233`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180001274`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000129c`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800012c4`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlUnmarshallReference(
        HANDLE hHeap,
        enum WS_CHARSET a2,
        unsigned int a3,
        struct WS_TYPE_Reference *a4,
        struct _CRYPT_XML_WS_STATE *a5,
        struct _HXML_HANDLE *a6,
        const struct _CRYPT_XML_REFERENCE **a7)
{
  unsigned int v7; // esi
  int EncodedElement; // esi
  const char *v12; // r8
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  int v16; // r9d
  int v17; // r8d
  unsigned int v18; // r9d
  unsigned int v19; // r10d
  unsigned int v20; // edx
  unsigned int v21; // ecx
  __int64 v22; // rdi
  __int64 v23; // rax
  _QWORD *v24; // r9
  __int64 v25; // rcx
  char v26; // al
  HANDLE ProcessHeap; // rax
  unsigned int v28; // edi
  __int64 i; // rbx
  void *v30; // r14
  HANDLE v31; // rax
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  struct _CRYPT_XML_WS_STATE *v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  unsigned int v39; // [rsp+78h] [rbp-88h]
  __int64 v40; // [rsp+80h] [rbp-80h]
  unsigned int v41; // [rsp+88h] [rbp-78h]
  __int64 v42; // [rsp+90h] [rbp-70h]
  unsigned int v43; // [rsp+98h] [rbp-68h]
  _CRYPT_XML_BLOB v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h]
  unsigned int v46; // [rsp+B8h] [rbp-48h]
  unsigned int v47; // [rsp+BCh] [rbp-44h]
  LPVOID v48[82]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a3;
  v35 = a5;
  v34 = 0;
  memset_0(&v36, 0, 0x2E8u);
  if ( *((_DWORD *)a4 + 12) > 0x10u )
  {
    EncodedElement = -2146885374;
    v12 = "";
    while ( 1 )
    {
      v13 = *(v12 - 1);
      v14 = v12--;
      v15 = v13 == 92;
      if ( v13 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v15 = v13 == 92;
        break;
      }
    }
    v16 = 663;
LABEL_34:
    if ( v15 )
      v12 = v14;
    goto LABEL_36;
  }
  v17 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 > 0x100u
    || (v18 = *((_DWORD *)a4 + 4), v18 > 0x2000)
    || (v19 = *((_DWORD *)a4 + 8), v19 > 0x2000)
    || (v20 = *((_DWORD *)a4 + 16), v20 > 0x2000)
    || (v21 = *((_DWORD *)a4 + 22), v21 > 0x80) )
  {
    EncodedElement = -2146885375;
    v12 = "";
    while ( 1 )
    {
      v26 = *(v12 - 1);
      v14 = v12--;
      v15 = v26 == 92;
      if ( v26 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v15 = v26 == 92;
        break;
      }
    }
    v16 = 674;
    goto LABEL_34;
  }
  if ( !v20 || !v21 )
  {
    EncodedElement = -2146885360;
    v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v16 = 683;
    goto LABEL_36;
  }
  v15 = *((_QWORD *)a4 + 10) == 0;
  v36 = *((_QWORD *)a4 + 1);
  v38 = *((_QWORD *)a4 + 3);
  v40 = *((_QWORD *)a4 + 5);
  v42 = *((_QWORD *)a4 + 9);
  v45 = *((_QWORD *)a4 + 12);
  v37 = v17;
  v39 = v18;
  v41 = v19;
  v43 = v20;
  v46 = v21;
  v48[80] = a4;
  if ( !v15 )
  {
    EncodedElement = I_XmlGetEncodedElement(a2, a5, &DigestMethod_ElementDescription, (char *)a4 + 64, 0x18u, v7, &v44);
    if ( EncodedElement < 0 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v16 = 713;
      goto LABEL_36;
    }
    v7 = a3;
  }
  v22 = 0;
  v47 = *((_DWORD *)a4 + 12);
  while ( (unsigned int)v22 < *((_DWORD *)a4 + 12) )
  {
    v23 = *((_QWORD *)a4 + 7);
    v15 = *(_QWORD *)(v23 + 24 * v22 + 16) == 0;
    v24 = (_QWORD *)(v23 + 24 * v22);
    v25 = 5 * v22;
    v48[v25] = (LPVOID)v24[1];
    LODWORD(v48[v25 + 1]) = *(_DWORD *)v24;
    if ( !v15 )
    {
      EncodedElement = I_XmlGetEncodedElement(
                         a2,
                         v35,
                         &Transform_ElementDescription,
                         v24,
                         0x18u,
                         v7,
                         (struct _CRYPT_XML_BLOB *)&v48[v25 + 2]);
      if ( EncodedElement < 0 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v16 = 738;
        goto LABEL_36;
      }
      v7 = a3;
    }
    v22 = (unsigned int)(v22 + 1);
  }
  EncodedElement = I_CryptXmlHandleAllocReference(hHeap, (__int64)a6, (__int64)&v34);
  if ( EncodedElement >= 0 )
  {
    *a7 = *(const struct _CRYPT_XML_REFERENCE **)(v34 + 136);
    goto LABEL_37;
  }
  v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
  v16 = 755;
LABEL_36:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v12, v16);
LABEL_37:
  if ( v44.cbData )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, v44.pbData);
  }
  v28 = v47;
  for ( i = 0; (unsigned int)i < v28; i = (unsigned int)(i + 1) )
  {
    if ( HIDWORD(v48[5 * i + 2]) )
    {
      v30 = v48[5 * i + 3];
      if ( v30 )
      {
        v31 = GetProcessHeap();
        HeapFree(v31, 8u, v30);
      }
    }
  }
  return (unsigned int)EncodedElement;
}

```

## disassembly

```asm
0x180001010  push    rbp
0x180001012  push    rbx
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r12
0x180001017  push    r13
0x180001019  push    r14
0x18000101b  push    r15
0x18000101d  lea     rbp, [rsp-268h]
0x180001025  sub     rsp, 368h
0x18000102c  mov     rax, cs:__security_cookie
0x180001033  xor     rax, rsp
0x180001036  mov     [rbp+2A0h+var_50], rax
0x18000103d  mov     rdi, [rbp+2A0h+arg_20]
0x180001044  mov     esi, r8d
0x180001047  mov     r12, [rbp+2A0h+arg_28]
0x18000104e  mov     r13d, edx
0x180001051  mov     r14, [rbp+2A0h+arg_30]
0x180001058  mov     r15, rcx
0x18000105b  mov     [rsp+3A0h+var_360], r8d
0x180001060  lea     rcx, [rsp+3A0h+var_340]; void *
0x180001065  xor     edx, edx; Val
0x180001067  mov     [rsp+3A0h+var_350], rdi
0x18000106c  mov     r8d, 2E8h; Size
0x180001072  mov     [rsp+3A0h+var_358], 0
0x18000107b  mov     rbx, r9
0x18000107e  call    memset_0
0x180001083  cmp     dword ptr [rbx+30h], 10h
0x180001087  jbe     short loc_1800010BD
0x180001089  mov     esi, 80092102h
0x18000108e  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180001095  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000109c  movzx   eax, byte ptr [r8-1]
0x1800010a1  mov     rdx, r8
0x1800010a4  dec     r8
0x1800010a7  cmp     al, 5Ch ; '\'
0x1800010a9  jz      short loc_1800010B2
0x1800010ab  cmp     r8, rcx
0x1800010ae  ja      short loc_18000109C
0x1800010b0  cmp     al, 5Ch ; '\'
0x1800010b2  mov     r9d, 297h
0x1800010b8  jmp     loc_1800012E7
0x1800010bd  mov     r8d, [rbx]
0x1800010c0  cmp     r8d, 100h
0x1800010c7  ja      loc_1800012B8
0x1800010cd  mov     r9d, [rbx+10h]
0x1800010d1  cmp     r9d, 2000h
0x1800010d8  ja      loc_1800012B8
0x1800010de  mov     r10d, [rbx+20h]
0x1800010e2  cmp     r10d, 2000h
0x1800010e9  ja      loc_1800012B8
0x1800010ef  mov     edx, [rbx+40h]
0x1800010f2  cmp     edx, 2000h
0x1800010f8  ja      loc_1800012B8
0x1800010fe  mov     ecx, [rbx+58h]
0x180001101  cmp     ecx, 80h
0x180001107  ja      loc_1800012B8
0x18000110d  test    edx, edx
0x18000110f  jz      loc_18000129C
0x180001115  test    ecx, ecx
0x180001117  jz      loc_18000129C
0x18000111d  cmp     qword ptr [rbx+50h], 0
0x180001122  mov     rax, [rbx+8]
0x180001126  mov     [rsp+3A0h+var_340], rax
0x18000112b  mov     rax, [rbx+18h]
0x18000112f  mov     [rsp+3A0h+var_330], rax
0x180001134  mov     rax, [rbx+28h]
0x180001138  mov     [rbp+2A0h+var_320], rax
0x18000113c  mov     rax, [rbx+48h]
0x180001140  mov     [rbp+2A0h+var_310], rax
0x180001144  mov     rax, [rbx+60h]
0x180001148  mov     [rbp+2A0h+var_2F0], rax
0x18000114c  mov     [rsp+3A0h+var_338], r8d
0x180001151  mov     [rsp+3A0h+var_328], r9d
0x180001156  mov     [rbp+2A0h+var_318], r10d
0x18000115a  mov     [rbp+2A0h+var_308], edx
0x18000115d  mov     [rbp+2A0h+var_2E8], ecx
0x180001160  mov     [rbp+2A0h+var_60], rbx
0x180001167  jz      short loc_1800011B8
0x180001169  lea     rax, [rbp+2A0h+var_300]
0x18000116d  mov     rdx, rdi; struct _CRYPT_XML_WS_STATE *
0x180001170  mov     [rsp+3A0h+var_370], rax; struct _CRYPT_XML_BLOB *
0x180001175  lea     r9, [rbx+40h]; void *
0x180001179  mov     [rsp+3A0h+var_378], esi; unsigned int
0x18000117d  lea     r8, ?DigestMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x180001184  mov     ecx, r13d; enum WS_CHARSET
0x180001187  mov     [rsp+3A0h+var_380], 18h; unsigned int
0x18000118f  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180001194  mov     esi, eax
0x180001196  test    eax, eax
0x180001198  jns     short loc_1800011B4
0x18000119a  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800011a1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800011a6  mov     r8, rax
0x1800011a9  mov     r9d, 2C9h
0x1800011af  jmp     loc_1800012EB
0x1800011b4  mov     esi, [rsp+3A0h+var_360]
0x1800011b8  mov     eax, [rbx+30h]
0x1800011bb  xor     edi, edi
0x1800011bd  mov     [rbp+2A0h+var_2E4], eax
0x1800011c0  cmp     edi, [rbx+30h]
0x1800011c3  jnb     loc_18000124D
0x1800011c9  mov     rax, [rbx+38h]
0x1800011cd  lea     rcx, [rdi+rdi*2]
0x1800011d1  cmp     qword ptr [rax+rcx*8+10h], 0
0x1800011d7  lea     r9, [rax+rcx*8]; void *
0x1800011db  lea     rax, [rdi+rdi*4]
0x1800011df  lea     rcx, ds:0[rax*8]
0x1800011e7  mov     rax, [r9+8]
0x1800011eb  mov     [rbp+rcx+2A0h+var_2E0], rax
0x1800011f0  mov     eax, [r9]
0x1800011f3  mov     [rbp+rcx+2A0h+var_2D8], eax
0x1800011f7  jz      short loc_18000122F
0x1800011f9  mov     rdx, [rsp+3A0h+var_350]; struct _CRYPT_XML_WS_STATE *
0x1800011fe  lea     rax, [rbp+2A0h+var_2D0]
0x180001202  add     rax, rcx
0x180001205  lea     r8, ?Transform_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x18000120c  mov     [rsp+3A0h+var_370], rax; struct _CRYPT_XML_BLOB *
0x180001211  mov     ecx, r13d; enum WS_CHARSET
0x180001214  mov     [rsp+3A0h+var_378], esi; unsigned int
0x180001218  mov     [rsp+3A0h+var_380], 18h; unsigned int
0x180001220  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180001225  mov     esi, eax
0x180001227  test    eax, eax
0x180001229  js      short loc_180001233
0x18000122b  mov     esi, [rsp+3A0h+var_360]
0x18000122f  inc     edi
0x180001231  jmp     short loc_1800011C0
0x180001233  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000123a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000123f  mov     r8, rax
0x180001242  mov     r9d, 2E2h
0x180001248  jmp     loc_1800012EB
0x18000124d  lea     rax, [rsp+3A0h+var_358]
0x180001252  xor     r8d, r8d
0x180001255  mov     qword ptr [rsp+3A0h+var_378], rax; __int64
0x18000125a  lea     r9, [rsp+3A0h+var_340]
0x18000125f  xor     edx, edx
0x180001261  mov     qword ptr [rsp+3A0h+var_380], r12; __int64
0x180001266  mov     rcx, r15; hHeap
0x180001269  call    I_CryptXmlHandleAllocReference
0x18000126e  mov     esi, eax
0x180001270  test    eax, eax
0x180001272  jns     short loc_18000128B
0x180001274  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000127b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001280  mov     r8, rax
0x180001283  mov     r9d, 2F3h
0x180001289  jmp     short loc_1800012EB
0x18000128b  mov     rax, [rsp+3A0h+var_358]
0x180001290  mov     rcx, [rax+88h]
0x180001297  mov     [r14], rcx
0x18000129a  jmp     short loc_1800012F9
0x18000129c  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800012a3  mov     esi, 80092110h
0x1800012a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800012ad  mov     r8, rax
0x1800012b0  mov     r9d, 2ABh
0x1800012b6  jmp     short loc_1800012EB
0x1800012b8  mov     esi, 80092101h
0x1800012bd  lea     r8, aOnecoreDsSecur_1+35h; ""
0x1800012c4  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800012cb  movzx   eax, byte ptr [r8-1]
0x1800012d0  mov     rdx, r8
0x1800012d3  dec     r8
0x1800012d6  cmp     al, 5Ch ; '\'
0x1800012d8  jz      short loc_1800012E1
0x1800012da  cmp     r8, rcx
0x1800012dd  ja      short loc_1800012CB
0x1800012df  cmp     al, 5Ch ; '\'
0x1800012e1  mov     r9d, 2A2h
0x1800012e7  cmovz   r8, rdx
0x1800012eb  mov     edx, esi
0x1800012ed  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800012f4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800012f9  cmp     [rbp+2A0h+var_300.cbData], 0
0x1800012fd  jbe     short loc_180001323
0x1800012ff  call    cs:__imp_GetProcessHeap
0x180001306  nop     dword ptr [rax+rax+00h]
0x18000130b  mov     r8, [rbp+2A0h+var_300.pbData]; lpMem
0x18000130f  mov     edx, 8; dwFlags
0x180001314  mov     rcx, rax; hHeap
0x180001317  call    cs:__imp_HeapFree
0x18000131e  nop     dword ptr [rax+rax+00h]
0x180001323  mov     edi, [rbp+2A0h+var_2E4]
0x180001326  xor     ebx, ebx
0x180001328  test    edi, edi
0x18000132a  jz      short loc_18000136A
0x18000132c  lea     rcx, [rbx+rbx*4]
0x180001330  cmp     [rbp+rcx*8+2A0h+var_2CC], 0
0x180001335  jbe     short loc_180001364
0x180001337  mov     r14, [rbp+rcx*8+2A0h+var_2C8]
0x18000133c  test    r14, r14
0x18000133f  jz      short loc_180001364
0x180001341  call    cs:__imp_GetProcessHeap
0x180001348  nop     dword ptr [rax+rax+00h]
0x18000134d  mov     r8, r14; lpMem
0x180001350  mov     edx, 8; dwFlags
0x180001355  mov     rcx, rax; hHeap
0x180001358  call    cs:__imp_HeapFree
0x18000135f  nop     dword ptr [rax+rax+00h]
0x180001364  inc     ebx
0x180001366  cmp     ebx, edi
0x180001368  jb      short loc_18000132C
0x18000136a  mov     eax, esi
0x18000136c  mov     rcx, [rbp+2A0h+var_50]
0x180001373  xor     rcx, rsp; StackCookie
0x180001376  call    __security_check_cookie
0x18000137b  add     rsp, 368h
0x180001382  pop     r15
0x180001384  pop     r14
0x180001386  pop     r13
0x180001388  pop     r12
0x18000138a  pop     rdi
0x18000138b  pop     rsi
0x18000138c  pop     rbx
0x18000138d  pop     rbp
0x18000138e  retn
```
