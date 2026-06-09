# SIDKeyProtect

- ea: `0x180017850`
- end: `0x180017e0d`
- name: `SIDKeyProtect`
- size: `1469`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const WCHAR *, UCHAR *, ULONG, __int64, __int64, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001f7c`
- `0x180010920`
- `0x180010950`
- `0x180017638`
- `0x180017850`
- `0x180019a6c`
- `0x18001a450`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017dea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017dea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ddc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ddc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017920`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001794e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017977`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017920`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001794e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017977`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800179a0`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017c1f`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017cac`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017d28`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017c1f`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017cac`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180017d28`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180017b79`
- `NTASN1!__imp_RtlAsn1GetModuleHandle` at `0x180017b79`

## string_xrefs

- `0x1800179bb`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x180017a9a`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x180017af1`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x180017ba2`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`
- `0x180017d61`: `onecore\ds\security\keyman\sidkeyprov\rpcclient\sidkeyprotect.cxx`

## pseudocode

```c
__int64 __fastcall SIDKeyProtect(
        PCNZWCH lpString1,
        const WCHAR *a2,
        UCHAR *a3,
        ULONG a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7,
        unsigned int a8)
{
  int v10; // r12d
  unsigned __int8 *v12; // r14
  void *v13; // r15
  unsigned int v14; // r9d
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  __int64 v17; // rdi
  unsigned __int8 *v18; // rax
  UCHAR *v19; // rsi
  signed int LatestSidKey; // eax
  unsigned int v21; // r9d
  UCHAR *v22; // rax
  signed int v23; // eax
  __int64 ModuleHandle; // rax
  unsigned int v25; // r9d
  unsigned int v26; // ecx
  const WCHAR *v27; // rcx
  unsigned int v28; // eax
  unsigned __int64 v29; // xmm0_8
  int v30; // eax
  HANDLE ProcessHeap; // rax
  unsigned int cchCount2; // [rsp+30h] [rbp-D8h]
  unsigned int v34[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int8 *v35; // [rsp+58h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-A0h]
  __int64 v38; // [rsp+70h] [rbp-98h]
  _BYTE v39[24]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v40; // [rsp+90h] [rbp-78h]
  _QWORD v41[3]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+B8h] [rbp-50h]
  __int128 v43; // [rsp+C0h] [rbp-48h]
  _OWORD v44[2]; // [rsp+D0h] [rbp-38h] BYREF
  _OWORD v45[2]; // [rsp+F0h] [rbp-18h] BYREF
  _DWORD v46[6]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int8 *v47; // [rsp+130h] [rbp+28h]
  _QWORD *v48; // [rsp+140h] [rbp+38h]
  int v49; // [rsp+148h] [rbp+40h]
  __int64 *v50; // [rsp+150h] [rbp+48h]
  unsigned int v51; // [rsp+170h] [rbp+68h]
  void *v52; // [rsp+178h] [rbp+70h]

  v10 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  memset_0(v46, 0, 0xA0u);
  memset(v41, 0, sizeof(v41));
  v35 = 0;
  v42 = 0;
  v34[0] = 0;
  lpMem = 0;
  v34[1] = 0;
  v37 = 0;
  v38 = 0;
  v12 = 0;
  v13 = 0;
  v43 = 0;
  memset(v44, 0, sizeof(v44));
  memset(v45, 0, sizeof(v45));
  if ( CompareStringW(0, 1u, lpString1, -1, L"SDDL", -1) == 2
    || CompareStringW(0, 1u, lpString1, -1, L"1.3.6.1.4.1.311.74.1.5", -1) == 2 )
  {
    v10 = 1;
  }
  else if ( CompareStringW(0, 1u, lpString1, -1, L"1.3.6.1.4.1.311.74.1.1", -1) != 2
         && CompareStringW(0, 1u, lpString1, -1, L"SID", -1) != 2 )
  {
    v14 = 449;
LABEL_6:
    v15 = -2146893785;
    v16 = -2146893785;
LABEL_7:
    SidKeyDebugTraceError(v16, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v14);
    goto LABEL_49;
  }
  if ( (a8 & 0xDFFFFFFF) != 0 )
  {
    v15 = -2146893815;
    v14 = 461;
    v16 = -2146893815;
    goto LABEL_7;
  }
  if ( a6 && a7 && a5 && a3 && a4 )
  {
    if ( !a2 || !*a2 )
    {
      v14 = 481;
      goto LABEL_6;
    }
    v17 = 32;
    v18 = (unsigned __int8 *)SIDKeyProvAlloc(0x20u);
    v19 = v18;
    if ( !v18 )
    {
      v15 = -2146893810;
      v14 = 490;
      v16 = -2146893810;
      goto LABEL_7;
    }
    LatestSidKey = GetLatestSidKey(a2, v10, &v35, v34, v18, cchCount2, a8);
    v15 = LatestSidKey;
    if ( LatestSidKey < 0 )
    {
      SidKeyDebugTraceError(
        LatestSidKey,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx",
        0x1FBu);
      v12 = v35;
      v22 = v19;
      goto LABEL_47;
    }
    v23 = CNG_AesKeyWrap(a3, a4, v19, v21, (unsigned __int8 **)&lpMem, &v34[1]);
    v15 = v23;
    if ( v23 < 0 )
    {
      SidKeyDebugTraceError(
        v23,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx",
        0x209u);
      v12 = v35;
      v13 = lpMem;
      goto LABEL_43;
    }
    memset_0(v46, 0, 0xA0u);
    v12 = v35;
    v13 = lpMem;
    v46[4] = v34[0];
    v51 = v34[1];
    v50 = &qword_18001E630;
    ModuleHandle = qword_1800236E8;
    v46[0] = 3;
    v46[2] = 4;
    v47 = v35;
    v52 = lpMem;
    v49 = 11;
    if ( !qword_1800236E8 )
    {
      ModuleHandle = RtlAsn1GetModuleHandle(L"{34e4912d-f770-4f49-b020-96dd74c99d02}");
      qword_1800236E8 = ModuleHandle;
      if ( !ModuleHandle )
      {
        v15 = -2146893792;
        v25 = 551;
        v26 = -2146893792;
LABEL_27:
        SidKeyDebugTraceError(v26, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx", v25);
        goto LABEL_43;
      }
    }
    LODWORD(v43) = 1;
    LODWORD(v44[0]) = 1;
    *((_QWORD *)&v43 + 1) = v44;
    *((_QWORD *)&v44[0] + 1) = v45;
    v27 = L"SDDL";
    if ( !v10 )
      v27 = L"SID";
    *(_QWORD *)&v45[0] = v27;
    *((_QWORD *)&v45[0] + 1) = a2;
    v28 = RtlAsn1EncodeAndAllocate(ModuleHandle, 28);
    v15 = v28;
    if ( v28 )
    {
      v25 = 588;
LABEL_32:
      v26 = v28;
      goto LABEL_27;
    }
    *(_DWORD *)v39 = 12;
    if ( v10 )
    {
      v29 = 0x8001E66000000000uLL;
      v30 = HIDWORD(off_18001C378);
    }
    else
    {
      v29 = 0x8001E65000000000uLL;
      v30 = HIDWORD(off_18001C368);
    }
    *(_DWORD *)&v39[12] = v30;
    *(_QWORD *)&v40 = v38;
    *(_DWORD *)&v39[16] = 0;
    *(_QWORD *)&v39[4] = v29;
    v28 = RtlAsn1EncodeAndAllocate(qword_1800236E8, 1);
    v15 = v28;
    if ( v28 )
    {
      v25 = 615;
      goto LABEL_32;
    }
    *(_QWORD *)((char *)&v41[1] + 4) = HIDWORD(off_18001C358);
    v42 = v37;
    v48 = v41;
    LODWORD(v41[0]) = 11;
    *(_QWORD *)((char *)v41 + 4) = 0x8001E64000000000uLL;
    v28 = RtlAsn1EncodeAndAllocate(qword_1800236E8, 22);
    v15 = v28;
    if ( v28 )
    {
      v25 = 643;
      goto LABEL_32;
    }
    v15 = 0;
    *a7 = 0;
  }
  else
  {
    v19 = 0;
    v15 = -2146893785;
    SidKeyDebugTraceError(
      0x80090027,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\rpcclient\\sidkeyprotect.cxx",
      0x1D8u);
    v17 = 0;
  }
LABEL_43:
  if ( v13 )
    SIDKeyProvFree(v13);
  if ( v19 )
  {
    v22 = v19;
    if ( !v17 )
    {
LABEL_48:
      SIDKeyProvFree(v19);
      goto LABEL_49;
    }
    do
    {
LABEL_47:
      *v22++ = 0;
      --v17;
    }
    while ( v17 );
    goto LABEL_48;
  }
LABEL_49:
  if ( v37 )
    (*(void (**)(void))(a5 + 16))();
  if ( v38 )
    (*(void (**)(void))(a5 + 16))();
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
  }
  return v15;
}

```

## disassembly

```asm
0x180017850  mov     rax, rsp
0x180017853  mov     [rax+8], rbx
0x180017857  mov     [rax+20h], r9d
0x18001785b  mov     [rax+18h], r8
0x18001785f  mov     [rax+10h], rdx
0x180017863  push    rbp
0x180017864  push    rsi
0x180017865  push    rdi
0x180017866  push    r12
0x180017868  push    r13
0x18001786a  push    r14
0x18001786c  push    r15
0x18001786e  lea     rbp, [rax-0E8h]
0x180017875  sub     rsp, 1B0h
0x18001787c  mov     r13, [rbp+0E0h+arg_20]
0x180017883  xorps   xmm0, xmm0
0x180017886  mov     rdi, rdx
0x180017889  mov     rbx, rcx
0x18001788c  xor     r12d, r12d
0x18001788f  lea     rcx, [rbp+0E0h+var_D0]; void *
0x180017893  xor     edx, edx; Val
0x180017895  mov     qword ptr [rsp+1E0h+var_170], r12
0x18001789a  mov     r8d, 0A0h; Size
0x1800178a0  mov     esi, r9d
0x1800178a3  movups  [rsp+1E0h+var_170+8], xmm0
0x1800178a8  movups  [rbp+0E0h+var_158], xmm0
0x1800178ac  call    memset_0
0x1800178b1  or      ecx, 0FFFFFFFFh
0x1800178b4  mov     [rbp+0E0h+var_148], r12
0x1800178b8  xorps   xmm0, xmm0
0x1800178bb  mov     [rsp+1E0h+cchCount2], ecx; unsigned int
0x1800178bf  xor     eax, eax
0x1800178c1  mov     [rsp+1E0h+var_190], r12
0x1800178c6  xorps   xmm1, xmm1
0x1800178c9  mov     [rbp+0E0h+var_130], rax
0x1800178cd  lea     edx, [rcx+2]; dwCmpFlags
0x1800178d0  mov     [rsp+1E0h+var_198], r12d
0x1800178d5  lea     rax, aSddl; "SDDL"
0x1800178dc  mov     [rsp+1E0h+lpMem], r12
0x1800178e1  mov     r9d, ecx; cchCount1
0x1800178e4  mov     [rsp+1E0h+var_198+4], r12d
0x1800178e9  xor     ecx, ecx; Locale
0x1800178eb  mov     [rsp+1E0h+var_180], r12
0x1800178f0  mov     r8, rbx; lpString1
0x1800178f3  mov     [rsp+1E0h+var_178], r12
0x1800178f8  movups  [rbp+0E0h+var_140], xmm0
0x1800178fc  mov     r14d, r12d
0x1800178ff  mov     qword ptr [rsp+1E0h+var_1A0], r12
0x180017904  mov     r15d, r12d
0x180017907  mov     [rsp+1E0h+lpString2], rax; lpString2
0x18001790c  movups  [rbp+0E0h+var_128], xmm0
0x180017910  movups  [rbp+0E0h+var_118], xmm1
0x180017914  movups  [rbp+0E0h+var_108], xmm1
0x180017918  movups  [rbp+0E0h+var_F8], xmm0
0x18001791c  movups  [rbp+0E0h+var_E8], xmm0
0x180017920  call    cs:__imp_CompareStringW
0x180017926  cmp     eax, 2
0x180017929  jz      loc_1800179D3
0x18001792f  or      r9d, 0FFFFFFFFh; cchCount1
0x180017933  lea     rax, a1361413117415; "1.3.6.1.4.1.311.74.1.5"
0x18001793a  mov     [rsp+1E0h+cchCount2], r9d; cchCount2
0x18001793f  lea     edx, [r12+1]; dwCmpFlags
0x180017944  mov     r8, rbx; lpString1
0x180017947  mov     [rsp+1E0h+lpString2], rax; lpString2
0x18001794c  xor     ecx, ecx; Locale
0x18001794e  call    cs:__imp_CompareStringW
0x180017954  cmp     eax, 2
0x180017957  jz      short loc_1800179D3
0x180017959  or      ecx, 0FFFFFFFFh
0x18001795c  lea     rax, a1361413117411; "1.3.6.1.4.1.311.74.1.1"
0x180017963  mov     [rsp+1E0h+cchCount2], ecx; cchCount2
0x180017967  mov     r9d, ecx; cchCount1
0x18001796a  mov     r8, rbx; lpString1
0x18001796d  mov     [rsp+1E0h+lpString2], rax; lpString2
0x180017972  lea     edx, [rcx+2]; dwCmpFlags
0x180017975  xor     ecx, ecx; Locale
0x180017977  call    cs:__imp_CompareStringW
0x18001797d  cmp     eax, 2
0x180017980  jz      short loc_1800179D9
0x180017982  or      eax, 0FFFFFFFFh
0x180017985  lea     rcx, aSid; "SID"
0x18001798c  mov     [rsp+1E0h+cchCount2], eax; cchCount2
0x180017990  mov     r9d, eax; cchCount1
0x180017993  mov     [rsp+1E0h+lpString2], rcx; lpString2
0x180017998  mov     r8, rbx; lpString1
0x18001799b  xor     ecx, ecx; Locale
0x18001799d  lea     edx, [rax+2]; dwCmpFlags
0x1800179a0  call    cs:__imp_CompareStringW
0x1800179a6  cmp     eax, 2
0x1800179a9  jz      short loc_1800179D9
0x1800179ab  mov     r9d, 1C1h; unsigned int
0x1800179b1  mov     ebx, 80090027h
0x1800179b6  mov     ecx, 80090027h; unsigned int
0x1800179bb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800179c2  lea     rdx, aHr; "hr"
0x1800179c9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800179ce  jmp     loc_180017DB1
0x1800179d3  mov     r12d, 1
0x1800179d9  mov     ebx, [rbp+0E0h+arg_38]
0x1800179df  test    ebx, 0DFFFFFFFh
0x1800179e5  jz      short loc_1800179F9
0x1800179e7  mov     ebx, 80090009h
0x1800179ec  mov     r9d, 1CDh
0x1800179f2  mov     ecx, 80090009h
0x1800179f7  jmp     short loc_1800179BB
0x1800179f9  xor     eax, eax
0x1800179fb  cmp     [rbp+0E0h+arg_28], rax
0x180017a02  jz      loc_180017D5B
0x180017a08  cmp     [rbp+0E0h+arg_30], rax
0x180017a0f  jz      loc_180017D5B
0x180017a15  test    r13, r13
0x180017a18  jz      loc_180017D5B
0x180017a1e  cmp     [rbp+0E0h+pbSecret], rax
0x180017a25  jz      loc_180017D5B
0x180017a2b  test    esi, esi
0x180017a2d  jz      loc_180017D5B
0x180017a33  test    rdi, rdi
0x180017a36  jz      loc_180017D50
0x180017a3c  cmp     ax, [rdi]
0x180017a3f  jz      loc_180017D50
0x180017a45  lea     edi, [rax+20h]
0x180017a48  mov     ecx, edi; unsigned __int64
0x180017a4a  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180017a4f  mov     rsi, rax
0x180017a52  test    rax, rax
0x180017a55  jnz     short loc_180017A6C
0x180017a57  mov     ebx, 8009000Eh
0x180017a5c  mov     r9d, 1EAh
0x180017a62  mov     ecx, 8009000Eh
0x180017a67  jmp     loc_1800179BB
0x180017a6c  mov     rcx, [rbp+0E0h+StringSid]; StringSid
0x180017a73  lea     r9, [rsp+1E0h+var_198]; unsigned int *
0x180017a78  mov     [rsp+1E0h+cchCount2+8], ebx; unsigned int
0x180017a7c  lea     r8, [rsp+1E0h+var_190]; unsigned __int8 **
0x180017a81  mov     edx, r12d; int
0x180017a84  mov     [rsp+1E0h+lpString2], rsi; unsigned __int8 *
0x180017a89  call    ?GetLatestSidKey@@YAJPEBGHPEAPEAEPEAKPEAEKK@Z; GetLatestSidKey(ushort const *,int,uchar * *,ulong *,uchar *,ulong,ulong)
0x180017a8e  mov     ebx, eax
0x180017a90  test    eax, eax
0x180017a92  jns     short loc_180017ABC
0x180017a94  mov     r9d, 1FBh; unsigned int
0x180017a9a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017aa1  lea     rdx, aHr; "hr"
0x180017aa8  mov     ecx, eax; unsigned int
0x180017aaa  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017aaf  mov     r14, [rsp+1E0h+var_190]
0x180017ab4  mov     rax, rsi
0x180017ab7  jmp     loc_180017D9D
0x180017abc  mov     edx, [rbp+0E0h+cbSecret]; cbSecret
0x180017ac2  lea     rax, [rsp+1E0h+var_198+4]
0x180017ac7  mov     rcx, [rbp+0E0h+pbSecret]; pbSecret
0x180017ace  mov     r8, rsi; PUCHAR
0x180017ad1  mov     qword ptr [rsp+1E0h+cchCount2], rax; unsigned int *
0x180017ad6  lea     rax, [rsp+1E0h+lpMem]
0x180017adb  mov     [rsp+1E0h+lpString2], rax; unsigned __int8 **
0x180017ae0  call    ?CNG_AesKeyWrap@@YAJPEAEK0KPEAPEAEPEAK@Z; CNG_AesKeyWrap(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180017ae5  mov     ebx, eax
0x180017ae7  test    eax, eax
0x180017ae9  jns     short loc_180017B15
0x180017aeb  mov     r9d, 209h; unsigned int
0x180017af1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017af8  lea     rdx, aHr; "hr"
0x180017aff  mov     ecx, eax; unsigned int
0x180017b01  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017b06  mov     r14, [rsp+1E0h+var_190]
0x180017b0b  mov     r15, [rsp+1E0h+lpMem]
0x180017b10  jmp     loc_180017D83
0x180017b15  xor     edx, edx; Val
0x180017b17  lea     rcx, [rbp+0E0h+var_D0]; void *
0x180017b1b  mov     r8d, 0A0h; Size
0x180017b21  call    memset_0
0x180017b26  mov     eax, [rsp+1E0h+var_198]
0x180017b2a  mov     r14, [rsp+1E0h+var_190]
0x180017b2f  mov     r15, [rsp+1E0h+lpMem]
0x180017b34  mov     [rbp+0E0h+var_C0], eax
0x180017b37  mov     eax, [rsp+1E0h+var_198+4]
0x180017b3b  mov     [rbp+0E0h+var_78], eax
0x180017b3e  lea     rax, qword_18001E630
0x180017b45  mov     [rbp+0E0h+var_98], rax
0x180017b49  mov     rax, cs:qword_1800236E8
0x180017b50  mov     [rbp+0E0h+var_D0], 3
0x180017b57  mov     [rbp+0E0h+var_C8], 4
0x180017b5e  mov     [rbp+0E0h+var_B8], r14
0x180017b62  mov     [rbp+0E0h+var_70], r15
0x180017b66  mov     [rbp+0E0h+var_A0], 0Bh
0x180017b6d  test    rax, rax
0x180017b70  jnz     short loc_180017BB3
0x180017b72  lea     rcx, a34e4912dF7704f; "{34e4912d-f770-4f49-b020-96dd74c99d02}"
0x180017b79  call    cs:__imp_RtlAsn1GetModuleHandle
0x180017b7f  mov     cs:qword_1800236E8, rax
0x180017b86  test    rax, rax
0x180017b89  jnz     short loc_180017BB3
0x180017b8b  mov     ebx, 80090020h
0x180017b90  mov     r9d, 227h; unsigned int
0x180017b96  mov     ecx, 80090020h; unsigned int
0x180017b9b  lea     rdx, aHr; "hr"
0x180017ba2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017ba9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180017bae  jmp     loc_180017D83
0x180017bb3  lea     rdx, aSid; "SID"
0x180017bba  mov     dword ptr [rbp+0E0h+var_128], 1
0x180017bc1  lea     rcx, [rbp+0E0h+var_118]
0x180017bc5  mov     dword ptr [rbp+0E0h+var_118], 1
0x180017bcc  mov     qword ptr [rbp+0E0h+var_128+8], rcx
0x180017bd0  test    r12d, r12d
0x180017bd3  lea     rcx, [rbp+0E0h+var_F8]
0x180017bd7  mov     r9, r13
0x180017bda  mov     qword ptr [rbp+0E0h+var_118+8], rcx
0x180017bde  lea     rcx, aSddl; "SDDL"
0x180017be5  cmovz   rcx, rdx
0x180017be9  xor     r8d, r8d
0x180017bec  mov     qword ptr [rbp+0E0h+var_F8], rcx
0x180017bf0  mov     rcx, [rbp+0E0h+StringSid]
0x180017bf7  mov     qword ptr [rbp+0E0h+var_F8+8], rcx
0x180017bfb  lea     rcx, [rbp+0E0h+var_128]
0x180017bff  mov     qword ptr [rsp+1E0h+cchCount2+8], rcx
0x180017c04  lea     edx, [r8+1Ch]
0x180017c08  lea     rcx, [rsp+1E0h+var_1A0]
0x180017c0d  mov     qword ptr [rsp+1E0h+cchCount2], rcx
0x180017c12  lea     rcx, [rsp+1E0h+var_178]
0x180017c17  mov     [rsp+1E0h+lpString2], rcx
0x180017c1c  mov     rcx, rax
0x180017c1f  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180017c25  mov     ebx, eax
0x180017c27  test    eax, eax
0x180017c29  jz      short loc_180017C38
0x180017c2b  mov     r9d, 24Ch
0x180017c31  mov     ecx, eax
0x180017c33  jmp     loc_180017B9B
0x180017c38  mov     dword ptr [rsp+1E0h+var_170], 0Ch
0x180017c40  test    r12d, r12d
0x180017c43  jz      short loc_180017C55
0x180017c45  movsd   xmm0, qword ptr cs:dword_18001C374
0x180017c4d  mov     eax, dword ptr cs:off_18001C378+4
0x180017c53  jmp     short loc_180017C63
0x180017c55  movsd   xmm0, qword ptr cs:dword_18001C364
0x180017c5d  mov     eax, dword ptr cs:off_18001C368+4
0x180017c63  mov     rcx, cs:qword_1800236E8
0x180017c6a  xor     r8d, r8d
0x180017c6d  mov     dword ptr [rsp+1E0h+var_170+0Ch], eax
0x180017c71  mov     r9, r13
0x180017c74  mov     rax, [rsp+1E0h+var_178]
0x180017c79  mov     qword ptr [rbp+0E0h+var_158], rax
0x180017c7d  mov     eax, [rsp+1E0h+var_1A0]
0x180017c81  lea     edx, [r8+1]
0x180017c85  mov     [rbp+0E0h+var_160], eax
0x180017c88  lea     rax, [rsp+1E0h+var_170]
0x180017c8d  mov     qword ptr [rsp+1E0h+cchCount2+8], rax
0x180017c92  lea     rax, [rsp+1E0h+var_1A0]
0x180017c97  mov     qword ptr [rsp+1E0h+cchCount2], rax
0x180017c9c  lea     rax, [rsp+1E0h+var_180]
0x180017ca1  mov     [rsp+1E0h+lpString2], rax
0x180017ca6  movsd   qword ptr [rsp+1E0h+var_170+4], xmm0
0x180017cac  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180017cb2  mov     ebx, eax
0x180017cb4  test    eax, eax
0x180017cb6  jz      short loc_180017CC3
0x180017cb8  mov     r9d, 267h
0x180017cbe  jmp     loc_180017C31
0x180017cc3  mov     eax, dword ptr cs:off_18001C358+4
0x180017cc9  xor     r8d, r8d
0x180017ccc  movsd   xmm0, qword ptr cs:dword_18001C354
0x180017cd4  mov     r9, r13
0x180017cd7  mov     rcx, cs:qword_1800236E8
0x180017cde  mov     dword ptr [rbp+0E0h+var_140+4], eax
0x180017ce1  mov     rax, [rsp+1E0h+var_180]
0x180017ce6  lea     edx, [r8+16h]
0x180017cea  mov     [rbp+0E0h+var_130], rax
0x180017cee  mov     eax, [rsp+1E0h+var_1A0]
0x180017cf2  mov     dword ptr [rbp+0E0h+var_140+8], eax
0x180017cf5  lea     rax, [rbp+0E0h+var_148]
0x180017cf9  mov     [rbp+0E0h+var_A8], rax
0x180017cfd  lea     rax, [rbp+0E0h+var_D0]
0x180017d01  mov     qword ptr [rsp+1E0h+cchCount2+8], rax
0x180017d06  lea     rax, [rsp+1E0h+var_1A0]
0x180017d0b  mov     qword ptr [rsp+1E0h+cchCount2], rax
0x180017d10  mov     rax, [rbp+0E0h+arg_28]
0x180017d17  mov     [rsp+1E0h+lpString2], rax
0x180017d1c  mov     dword ptr [rbp+0E0h+var_148], 0Bh
0x180017d23  movsd   [rbp+0E0h+var_148+4], xmm0
0x180017d28  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180017d2e  mov     ebx, eax
0x180017d30  test    eax, eax
0x180017d32  jz      short loc_180017D3F
0x180017d34  mov     r9d, 283h
0x180017d3a  jmp     loc_180017C31
0x180017d3f  mov     rcx, [rbp+0E0h+arg_30]
0x180017d46  xor     ebx, ebx
0x180017d48  mov     eax, [rsp+1E0h+var_1A0]
0x180017d4c  mov     [rcx], eax
0x180017d4e  jmp     short loc_180017D83
0x180017d50  mov     r9d, 1E1h
0x180017d56  jmp     loc_1800179B1
0x180017d5b  mov     r9d, 1D8h; unsigned int
0x180017d61  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180017d68  lea     rdx, aHr; "hr"
0x180017d6f  mov     ecx, 80090027h; unsigned int
0x180017d74  mov     rsi, rax
0x180017d77  mov     ebx, 80090027h
0x180017d7c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
  ... truncated ...
```
