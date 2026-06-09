# CtapNfcEnumerateReaders

- ea: `0x18000840c`
- end: `0x18000886b`
- name: `CtapNfcEnumerateReaders`
- size: `1119`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000813c`
- `0x18004d288`
- `0x1800ee278`

## callees

- `0x180007f90`
- `0x18000840c`
- `0x180009600`
- `0x18000acf4`
- `0x180017ad4`
- `0x180017efc`
- `0x180018cf0`
- `0x18005378c`
- `0x1800537a4`
- `0x1800ed990`
- `0x1800f1edc`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008711`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008711`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x18000862b`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x18000862b`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x1800084cd`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x1800084cd`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x1800086e0`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x1800086e0`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetDeviceTypeIdW` at `0x180008521`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetDeviceTypeIdW` at `0x180008521`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x180008476`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x180008476`
- `ext-ms-win-security-winscard-l1-1-1!SCardGetReaderDeviceInstanceIdW` at `0x18000858e`
- `ext-ms-win-security-winscard-l1-1-1!SCardGetReaderDeviceInstanceIdW` at `0x18000858e`

## string_xrefs

- `0x18000859b`: `CtapNfcGetReaderDeviceInstanceId`
- `0x1800084dc`: `CtapNfcListReaders`
- `0x1800084a7`: `CtapNfcEnumerateReaders`
- `0x18000882f`: `CheckReaderType`
- `0x180008646`: `GetReaderStatus`

## pseudocode

```c
__int64 __fastcall CtapNfcEnumerateReaders(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  __int64 v6; // r8
  unsigned int v7; // eax
  const WCHAR *v8; // rbx
  unsigned int ReaderDeviceInstanceIdW; // eax
  unsigned int DeviceInstanceIdDetails; // eax
  int v11; // edx
  int v12; // ecx
  const char *v13; // r9
  void **i; // rax
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  _QWORD *v18; // rax
  __int64 *v19; // rdi
  char *v20; // r14
  __int64 v21; // rcx
  __int64 **v22; // rax
  __int64 v23; // rax
  void *v24; // rcx
  __int64 v25; // rax
  unsigned __int16 v27[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 v28; // [rsp+34h] [rbp-65h] BYREF
  SCARDCONTEXT phContext; // [rsp+38h] [rbp-61h] BYREF
  LPCVOID pvMem; // [rsp+40h] [rbp-59h] BYREF
  int v31; // [rsp+48h] [rbp-51h] BYREF
  int v32; // [rsp+4Ch] [rbp-4Dh] BYREF
  void *v33[2]; // [rsp+50h] [rbp-49h] BYREF
  DWORD pcchReaders; // [rsp+60h] [rbp-39h] BYREF
  int v35; // [rsp+64h] [rbp-35h] BYREF
  WCHAR mszReaders[4]; // [rsp+68h] [rbp-31h] BYREF
  $B80B7D01E79FADDB4AAC58DE22BC823F rgReaderStates; // [rsp+70h] [rbp-29h] BYREF

  pcchReaders = -1;
  phContext = 0;
  v33[1] = v33;
  *(_QWORD *)mszReaders = 0;
  v33[0] = v33;
  CtapHidEnumerateDevices((__int64)v33, a2, 1);
  v4 = SCardEstablishContext(0, 0, 0, &phContext);
  v5 = v4;
  if ( v4 )
  {
    CtapLogMsg(L"Failure in %s at Line %d: 0x%X\n", L"CtapNfcEstablishContext", 160, v4);
    v6 = 1548;
LABEL_3:
    CtapLogMsg(L"Failure in %s at Line %d: 0x%X\n", L"CtapNfcEnumerateReaders", v6, v5);
    goto LABEL_45;
  }
  v7 = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
  v5 = v7;
  if ( v7 )
  {
    CtapLogMsg(L"Failure in %s at Line %d: 0x%X\n", L"CtapNfcListReaders", 193, v7);
    v6 = 1555;
    goto LABEL_3;
  }
  v8 = *(const WCHAR **)mszReaders;
  if ( !**(_WORD **)mszReaders )
    goto LABEL_44;
  do
  {
    v31 = 0;
    if ( (unsigned int)SCardGetDeviceTypeIdW(phContext, v8, &v31) )
    {
      CtapLogMsg(L"Failure in %s at Line %d: 0x%X\n", L"CtapNfcGetDeviceTypeId");
    }
    else if ( v31 == 1024 || v31 == 128 || v31 == 512 )
    {
      CtapLogMsg(L"%s: SCardGetDeviceTypeId: %d. Skipping.\n", v8);
      if ( (byte_1801AEA03 & 1) == 0 )
        goto LABEL_40;
      v13 = "CheckReaderType";
      goto LABEL_20;
    }
    pvMem = 0;
    v35 = -1;
    ReaderDeviceInstanceIdW = SCardGetReaderDeviceInstanceIdW(phContext, v8, &pvMem, &v35);
    if ( ReaderDeviceInstanceIdW )
    {
      CtapLogMsg(L"Failure in %s at Line %d: 0x%X\n", L"CtapNfcGetReaderDeviceInstanceId", 233, ReaderDeviceInstanceIdW);
    }
    else
    {
      v32 = 0;
      v27[0] = 0;
      v28 = 0;
      DeviceInstanceIdDetails = _CtapNfcGetDeviceInstanceIdDetails((unsigned __int16 *)pvMem, v27, &v28, &v32);
      if ( DeviceInstanceIdDetails )
      {
        CtapLogMsg(
          L"%s: %s: _CtapNfcGetDeviceInstanceIdDetails failed: 0x%X. Non fatal.\n",
          v8,
          pvMem,
          DeviceInstanceIdDetails);
      }
      else if ( v32 )
      {
        for ( i = (void **)v33[0]; i != v33; i = (void **)*i )
        {
          if ( i && *((_WORD *)i + 30) == v27[0] && *((_WORD *)i + 31) == v28 )
          {
            if ( (byte_1801AEA03 & 1) != 0 )
            {
              v15 = &dword_18015030C;
              if ( pvMem )
                v15 = (const unsigned __int16 *)pvMem;
              McTemplateU0jszz_EventWriteTransfer(
                (_DWORD)v15,
                v28,
                a1,
                (unsigned int)"IsUsb",
                (__int64)v8,
                (__int64)v15);
            }
            CtapLogMsg(L"%s: Skipping.\n", v8);
            SCardFreeMemory(phContext, pvMem);
            goto LABEL_40;
          }
        }
      }
      CtapNfcFreeMemory(phContext, pvMem);
    }
    memset_0(&rgReaderStates, 0, sizeof(rgReaderStates));
    rgReaderStates.szReader = v8;
    rgReaderStates.dwCurrentState = 0;
    if ( SCardGetStatusChangeW(phContext, 0, &rgReaderStates, 1u) )
    {
      if ( (byte_1801AEA03 & 1) != 0 )
      {
        v13 = "GetReaderStatus";
LABEL_20:
        McTemplateU0jszz_EventWriteTransfer(v12, v11, a1, (_DWORD)v13, (__int64)v8, (__int64)&dword_18015030C);
      }
    }
    else
    {
      v16 = -1;
      do
        ++v16;
      while ( rgReaderStates.szReader[v16] );
      v17 = v16 + 1;
      v18 = LocalAlloc(0x40u, 2LL * (unsigned int)(v16 + 1) + 288);
      v19 = v18;
      if ( v18 )
      {
        v18[1] = v18;
        v20 = (char *)(v18 + 36);
        *v18 = v18;
        *((_DWORD *)v18 + 4) = 1;
        v18[3] = L"Nfc";
        v18[4] = L"MicrosoftCtapNfcProvider";
        memcpy_0(v18 + 36, rgReaderStates.szReader, 2 * v17);
        v19[6] = (__int64)v20;
        if ( (byte_1801AEA03 & 1) != 0 )
          McTemplateU0jz_EventWriteTransfer(v21, EVENT_CTAP_NFC_ADD_READER, a1, v20);
        v22 = *(__int64 ***)(a2 + 8);
        if ( *v22 != (__int64 *)a2 )
LABEL_53:
          __fastfail(3u);
        *v19 = a2;
        v19[1] = (__int64)v22;
        *v22 = v19;
        *(_QWORD *)(a2 + 8) = v19;
      }
    }
LABEL_40:
    v23 = -1;
    do
      ++v23;
    while ( v8[v23] );
    v8 += v23 + 1;
  }
  while ( *v8 );
  v8 = *(const WCHAR **)mszReaders;
LABEL_44:
  CtapNfcFreeMemory(phContext, v8);
LABEL_45:
  if ( phContext )
  {
    CtapNfcReleaseContext();
    phContext = 0;
  }
  while ( 1 )
  {
    v24 = v33[0];
    if ( v33[0] == v33 )
      return v5;
    if ( *((void ***)v33[0] + 1) != v33 )
      goto LABEL_53;
    v25 = *(_QWORD *)v33[0];
    if ( *(void **)(*(_QWORD *)v33[0] + 8LL) != v33[0] )
      goto LABEL_53;
    v33[0] = *(void **)v33[0];
    *(_QWORD *)(v25 + 8) = v33;
    FidoFree(v24);
  }
}

```

## disassembly

```asm
0x18000840c  mov     [rsp-8+arg_10], rbx
0x180008411  push    rbp
0x180008412  push    rsi
0x180008413  push    rdi
0x180008414  push    r12
0x180008416  push    r13
0x180008418  push    r14
0x18000841a  push    r15
0x18000841c  lea     rbp, [rsp-27h]
0x180008421  sub     rsp, 0C0h
0x180008428  mov     rax, cs:__security_cookie
0x18000842f  xor     rax, rsp
0x180008432  mov     [rbp+57h+var_40], rax
0x180008436  xor     r14d, r14d
0x180008439  mov     [rbp+57h+pcchReaders], 0FFFFFFFFh
0x180008440  lea     rax, [rbp+57h+var_A0]
0x180008444  mov     [rbp+57h+phContext], r14
0x180008448  mov     [rbp+57h+var_98], rax
0x18000844c  mov     r12, rcx
0x18000844f  lea     rax, [rbp+57h+var_A0]
0x180008453  mov     qword ptr [rbp+57h+mszReaders], r14
0x180008457  lea     r8d, [r14+1]
0x18000845b  mov     [rbp+57h+var_A0], rax
0x18000845f  lea     rcx, [rbp+57h+var_A0]
0x180008463  mov     r13, rdx
0x180008466  call    CtapHidEnumerateDevices
0x18000846b  lea     r9, [rbp+57h+phContext]; phContext
0x18000846f  xor     r8d, r8d; pvReserved2
0x180008472  xor     edx, edx; pvReserved1
0x180008474  xor     ecx, ecx; dwScope
0x180008476  call    cs:__imp_SCardEstablishContext
0x18000847c  mov     esi, eax
0x18000847e  test    eax, eax
0x180008480  jz      short loc_1800084BF
0x180008482  mov     r9d, eax
0x180008485  lea     rdx, aCtapnfcestabli; "CtapNfcEstablishContext"
0x18000848c  mov     r8d, 0A0h
0x180008492  lea     rcx, aFailureInSAtLi; "Failure in %s at Line %d: 0x%X\n"
0x180008499  call    CtapLogMsg
0x18000849e  mov     r8d, 60Ch
0x1800084a4  mov     r9d, esi
0x1800084a7  lea     rdx, aCtapnfcenumera; "CtapNfcEnumerateReaders"
0x1800084ae  lea     rcx, aFailureInSAtLi; "Failure in %s at Line %d: 0x%X\n"
0x1800084b5  call    CtapLogMsg
0x1800084ba  jmp     loc_1800087CE
0x1800084bf  mov     rcx, [rbp+57h+phContext]; hContext
0x1800084c3  lea     r9, [rbp+57h+pcchReaders]; pcchReaders
0x1800084c7  lea     r8, [rbp+57h+mszReaders]; mszReaders
0x1800084cb  xor     edx, edx; mszGroups
0x1800084cd  call    cs:__imp_SCardListReadersW
0x1800084d3  mov     esi, eax
0x1800084d5  test    eax, eax
0x1800084d7  jz      short loc_1800084FD
0x1800084d9  mov     r9d, eax
0x1800084dc  lea     rdx, aCtapnfclistrea; "CtapNfcListReaders"
0x1800084e3  mov     r8d, 0C1h
0x1800084e9  lea     rcx, aFailureInSAtLi; "Failure in %s at Line %d: 0x%X\n"
0x1800084f0  call    CtapLogMsg
0x1800084f5  mov     r8d, 613h
0x1800084fb  jmp     short loc_1800084A4
0x1800084fd  mov     rbx, qword ptr [rbp+57h+mszReaders]
0x180008501  cmp     [rbx], r14w
0x180008505  jz      loc_1800087C2
0x18000850b  lea     rdi, dword_18015030C
0x180008512  mov     rcx, [rbp+57h+phContext]
0x180008516  lea     r8, [rbp+57h+var_A8]
0x18000851a  mov     rdx, rbx
0x18000851d  mov     [rbp+57h+var_A8], r14d
0x180008521  call    cs:__imp_SCardGetDeviceTypeIdW
0x180008527  test    eax, eax
0x180008529  jz      short loc_180008549
0x18000852b  mov     r9d, eax
0x18000852e  lea     rdx, aCtapnfcgetdevi; "CtapNfcGetDeviceTypeId"
0x180008535  mov     r8d, 0D3h
0x18000853b  lea     rcx, aFailureInSAtLi; "Failure in %s at Line %d: 0x%X\n"
0x180008542  call    CtapLogMsg
0x180008547  jmp     short loc_180008574
0x180008549  mov     r8d, [rbp+57h+var_A8]
0x18000854d  cmp     r8d, 400h
0x180008554  jz      loc_180008813
0x18000855a  cmp     r8d, 80h
0x180008561  jz      loc_180008813
0x180008567  cmp     r8d, 200h
0x18000856e  jz      loc_180008813
0x180008574  mov     rcx, [rbp+57h+phContext]
0x180008578  lea     r9, [rbp+57h+var_8C]
0x18000857c  lea     r8, [rbp+57h+pvMem]
0x180008580  mov     [rbp+57h+pvMem], r14
0x180008584  mov     rdx, rbx
0x180008587  mov     [rbp+57h+var_8C], 0FFFFFFFFh
0x18000858e  call    cs:__imp_SCardGetReaderDeviceInstanceIdW
0x180008594  test    eax, eax
0x180008596  jz      short loc_1800085B6
0x180008598  mov     r9d, eax
0x18000859b  lea     rdx, aCtapnfcgetread; "CtapNfcGetReaderDeviceInstanceId"
0x1800085a2  mov     r8d, 0E9h
0x1800085a8  lea     rcx, aFailureInSAtLi; "Failure in %s at Line %d: 0x%X\n"
0x1800085af  call    CtapLogMsg
0x1800085b4  jmp     short loc_180008604
0x1800085b6  mov     rcx, [rbp+57h+pvMem]; unsigned __int16 *
0x1800085ba  lea     r9, [rbp+57h+var_A4]; int *
0x1800085be  lea     r8, [rbp+57h+var_BC]; unsigned __int16 *
0x1800085c2  mov     [rbp+57h+var_A4], r14d
0x1800085c6  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x1800085ca  mov     [rbp+57h+var_C0], r14w
0x1800085cf  mov     [rbp+57h+var_BC], r14w
0x1800085d4  call    ?_CtapNfcGetDeviceInstanceIdDetails@@YAKPEAG00PEAH@Z; _CtapNfcGetDeviceInstanceIdDetails(ushort *,ushort *,ushort *,int *)
0x1800085d9  test    eax, eax
0x1800085db  jz      loc_180008664
0x1800085e1  mov     r8, [rbp+57h+pvMem]
0x1800085e5  lea     rcx, aSSCtapnfcgetde; "%s: %s: _CtapNfcGetDeviceInstanceIdDeta"...
0x1800085ec  mov     r9d, eax
0x1800085ef  mov     rdx, rbx
0x1800085f2  call    CtapLogMsg
0x1800085f7  mov     rdx, [rbp+57h+pvMem]; void *
0x1800085fb  mov     rcx, [rbp+57h+phContext]; unsigned __int64
0x1800085ff  call    ?CtapNfcFreeMemory@@YAJ_KPEBX@Z; CtapNfcFreeMemory(unsigned __int64,void const *)
0x180008604  xor     edx, edx; Val
0x180008606  lea     rcx, [rbp+57h+rgReaderStates]; void *
0x18000860a  lea     r8d, [rdx+40h]; Size
0x18000860e  call    memset_0
0x180008613  mov     rcx, [rbp+57h+phContext]; hContext
0x180008617  lea     r8, [rbp+57h+rgReaderStates]; rgReaderStates
0x18000861b  mov     r9d, 1; cReaders
0x180008621  mov     [rbp+57h+rgReaderStates.szReader], rbx
0x180008625  xor     edx, edx; dwTimeout
0x180008627  mov     [rbp+57h+rgReaderStates.dwCurrentState], r14d
0x18000862b  call    cs:__imp_SCardGetStatusChangeW
0x180008631  test    eax, eax
0x180008633  jz      loc_1800086EB
0x180008639  test    cs:byte_1801AEA03, 1
0x180008640  jz      loc_18000879E
0x180008646  lea     r9, aGetreaderstatu; "GetReaderStatus"
0x18000864d  mov     [rsp+0F0h+var_C8], rdi
0x180008652  mov     r8, r12
0x180008655  mov     [rsp+0F0h+var_D0], rbx
0x18000865a  call    McTemplateU0jszz_EventWriteTransfer
0x18000865f  jmp     loc_18000879E
0x180008664  cmp     [rbp+57h+var_A4], r14d
0x180008668  jz      short loc_1800085F7
0x18000866a  mov     rax, [rbp+57h+var_A0]
0x18000866e  movzx   ecx, [rbp+57h+var_C0]
0x180008672  movzx   edx, [rbp+57h+var_BC]
0x180008676  lea     r8, [rbp+57h+var_A0]
0x18000867a  cmp     rax, r8
0x18000867d  jz      loc_1800085F7
0x180008683  test    rax, rax
0x180008686  jz      short loc_180008694
0x180008688  cmp     [rax+3Ch], cx
0x18000868c  jnz     short loc_180008694
0x18000868e  cmp     [rax+3Eh], dx
0x180008692  jz      short loc_180008699
0x180008694  mov     rax, [rax]
0x180008697  jmp     short loc_180008676
0x180008699  test    cs:byte_1801AEA03, 1
0x1800086a0  jz      short loc_1800086C9
0x1800086a2  mov     rax, [rbp+57h+pvMem]
0x1800086a6  lea     r9, aIsusb; "IsUsb"
0x1800086ad  test    rax, rax
0x1800086b0  mov     rcx, rdi
0x1800086b3  mov     r8, r12
0x1800086b6  cmovnz  rcx, rax
0x1800086ba  mov     [rsp+0F0h+var_C8], rcx
0x1800086bf  mov     [rsp+0F0h+var_D0], rbx
0x1800086c4  call    McTemplateU0jszz_EventWriteTransfer
0x1800086c9  mov     rdx, rbx
0x1800086cc  lea     rcx, aSSkipping; "%s: Skipping.\n"
0x1800086d3  call    CtapLogMsg
0x1800086d8  mov     rdx, [rbp+57h+pvMem]; pvMem
0x1800086dc  mov     rcx, [rbp+57h+phContext]; hContext
0x1800086e0  call    cs:__imp_SCardFreeMemory
0x1800086e6  jmp     loc_18000879E
0x1800086eb  mov     rcx, [rbp+57h+rgReaderStates.szReader]
0x1800086ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800086f3  inc     rax
0x1800086f6  cmp     [rcx+rax*2], r14w
0x1800086fb  jnz     short loc_1800086F3
0x1800086fd  lea     r15, [rax+1]
0x180008701  mov     ecx, 40h ; '@'; uFlags
0x180008706  mov     edx, r15d
0x180008709  lea     rdx, ds:120h[rdx*2]; uBytes
0x180008711  call    cs:__imp_LocalAlloc
0x180008717  mov     rdi, rax
0x18000871a  test    rax, rax
0x18000871d  jz      short loc_180008797
0x18000871f  mov     [rax+8], rax
0x180008723  lea     r14, [rax+120h]
0x18000872a  mov     [rax], rax
0x18000872d  lea     r8, [r15+r15]; Size
0x180008731  mov     dword ptr [rax+10h], 1
0x180008738  mov     rcx, r14; void *
0x18000873b  lea     rax, aNfc; "Nfc"
0x180008742  mov     [rdi+18h], rax
0x180008746  lea     rax, aMicrosoftctapn; "MicrosoftCtapNfcProvider"
0x18000874d  mov     [rdi+20h], rax
0x180008751  mov     rdx, [rbp+57h+rgReaderStates.szReader]; Src
0x180008755  call    memcpy_0
0x18000875a  mov     [rdi+30h], r14
0x18000875e  test    cs:byte_1801AEA03, 1
0x180008765  jz      short loc_180008779
0x180008767  mov     r9, r14
0x18000876a  lea     rdx, EVENT_CTAP_NFC_ADD_READER
0x180008771  mov     r8, r12
0x180008774  call    McTemplateU0jz_EventWriteTransfer
0x180008779  mov     rax, [r13+8]
0x18000877d  cmp     [rax], r13
0x180008780  jnz     loc_18000883B
0x180008786  mov     [rdi], r13
0x180008789  xor     r14d, r14d
0x18000878c  mov     [rdi+8], rax
0x180008790  mov     [rax], rdi
0x180008793  mov     [r13+8], rdi
0x180008797  lea     rdi, dword_18015030C
0x18000879e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800087a2  inc     rax
0x1800087a5  cmp     [rbx+rax*2], r14w
0x1800087aa  jnz     short loc_1800087A2
0x1800087ac  lea     rbx, [rbx+rax*2]
0x1800087b0  add     rbx, 2
0x1800087b4  cmp     [rbx], r14w
0x1800087b8  jnz     loc_180008512
0x1800087be  mov     rbx, qword ptr [rbp+57h+mszReaders]
0x1800087c2  mov     rcx, [rbp+57h+phContext]; unsigned __int64
0x1800087c6  mov     rdx, rbx; void *
0x1800087c9  call    ?CtapNfcFreeMemory@@YAJ_KPEBX@Z; CtapNfcFreeMemory(unsigned __int64,void const *)
0x1800087ce  mov     rcx, [rbp+57h+phContext]
0x1800087d2  test    rcx, rcx
0x1800087d5  jz      short loc_1800087E0
0x1800087d7  call    CtapNfcReleaseContext
0x1800087dc  mov     [rbp+57h+phContext], r14
0x1800087e0  mov     rcx, [rbp+57h+var_A0]; void *
0x1800087e4  lea     rax, [rbp+57h+var_A0]
0x1800087e8  cmp     rcx, rax
0x1800087eb  jz      short loc_180008842
0x1800087ed  lea     rax, [rbp+57h+var_A0]
0x1800087f1  cmp     [rcx+8], rax
0x1800087f5  jnz     short loc_18000883B
0x1800087f7  mov     rax, [rcx]
0x1800087fa  cmp     [rax+8], rcx
0x1800087fe  jnz     short loc_18000883B
0x180008800  lea     rdx, [rbp+57h+var_A0]
0x180008804  mov     [rbp+57h+var_A0], rax
0x180008808  mov     [rax+8], rdx
0x18000880c  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x180008811  jmp     short loc_1800087E0
0x180008813  mov     rdx, rbx
0x180008816  lea     rcx, aSScardgetdevic; "%s: SCardGetDeviceTypeId: %d. Skipping."...
0x18000881d  call    CtapLogMsg
0x180008822  test    cs:byte_1801AEA03, 1
0x180008829  jz      loc_18000879E
0x18000882f  lea     r9, aCheckreadertyp; "CheckReaderType"
0x180008836  jmp     loc_18000864D
0x18000883b  mov     ecx, 3
0x180008840  int     29h; Win8: RtlFailFast(ecx)
0x180008842  mov     eax, esi
0x180008844  mov     rcx, [rbp+57h+var_40]
0x180008848  xor     rcx, rsp; StackCookie
0x18000884b  call    __security_check_cookie
0x180008850  mov     rbx, [rsp+0F0h+arg_10]
0x180008858  add     rsp, 0C0h
0x18000885f  pop     r15
0x180008861  pop     r14
0x180008863  pop     r13
0x180008865  pop     r12
0x180008867  pop     rdi
0x180008868  pop     rsi
0x180008869  pop     rbp
0x18000886a  retn
```
