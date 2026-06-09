# InitializeDirScanArgs(DIRECTORY_SCAN_FUNC_ARGS *,SCAN_ID,PRIVATE_SCAN_SETTINGS &,ulong)

- ea: `0x1800222a8`
- end: `0x18002267b`
- name: `?InitializeDirScanArgs@@YAJPEAUDIRECTORY_SCAN_FUNC_ARGS@@W4SCAN_ID@@AEAUPRIVATE_SCAN_SETTINGS@@K@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1800227a4`

## callees

- `0x180005114`
- `0x1800152d4`
- `0x180016e60`
- `0x180017ac8`
- `0x18001f788`
- `0x18001f7f0`
- `0x180020e04`
- `0x1800222a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800225ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800225ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800225e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800225e8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180022562`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180022562`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800224bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800224bd`
- `bcrypt!BCryptGetProperty` at `0x1800224fc`
- `bcrypt!BCryptGetProperty` at `0x1800224fc`

## pseudocode

```c
__int64 __fastcall InitializeDirScanArgs(__int64 a1, int a2, __int64 a3, int a4)
{
  int v7; // esi
  __int64 v8; // rdx
  int v10; // edi
  int v11; // edi
  int v12; // edi
  NTSTATUS Property; // edi
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int TempPath2W; // eax
  HANDLE FileW; // rax
  int pcbResult; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void *v21; // [rsp+70h] [rbp+8h]
  ULONG v22; // [rsp+78h] [rbp+10h] BYREF

  *(_DWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = a4;
  *(_DWORD *)(a1 + 4) = 33;
  if ( (unsigned int)EnablePrivilege((const unsigned __int16 *)a1) )
    *(_DWORD *)(a1 + 4) |= 0x4000u;
  v7 = AllocateMemory<unsigned short>(a1 + 104);
  if ( v7 < 0 )
  {
    v8 = 495;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v7,
      pcbResult);
    return (unsigned int)v7;
  }
  *(_DWORD *)(a1 + 96) = 0x80000000;
  v7 = AllocateMemory<unsigned __int64>(a1 + 112, 1000);
  if ( v7 < 0 )
  {
    v8 = 503;
    goto LABEL_5;
  }
  *(_WORD *)(a1 + 88) = 0;
  v7 = AllocateMemory<unsigned short>(a1 + 136);
  if ( v7 < 0 )
  {
    v8 = 512;
    goto LABEL_5;
  }
  *(_DWORD *)(a1 + 128) = 0x80000000;
  v7 = AllocateMemory<unsigned __int64>(a1 + 144, 1000);
  if ( v7 < 0 )
  {
    v8 = 521;
    goto LABEL_5;
  }
  *(_WORD *)(a1 + 120) = 0;
  v7 = AllocateMemory<unsigned short>(a1 + 720);
  if ( v7 < 0 )
  {
    v8 = 534;
    goto LABEL_5;
  }
  *(_DWORD *)(a1 + 712) = 0x80000000;
  v7 = AllocateMemory<enum SCAN_ID>(a1 + 728, 1000);
  if ( v7 < 0 )
  {
    v8 = 538;
    goto LABEL_5;
  }
  v7 = AllocateMemory<enum SCAN_ID>(a1 + 736, 1000);
  if ( v7 < 0 )
  {
    v8 = 540;
    goto LABEL_5;
  }
  v7 = AllocateMemory<enum SCAN_ID>(a1 + 744, 1000);
  if ( v7 < 0 )
  {
    v8 = 542;
    goto LABEL_5;
  }
  *(_WORD *)(a1 + 704) = 0;
  *(_WORD *)(a1 + 80) = 0;
  v10 = a2 - 3;
  if ( !v10 )
  {
    if ( *(_BYTE *)(a3 + 8) )
    {
      TempPath2W = GetTempPath2W(260, a1 + 176);
      if ( !TempPath2W )
        return 3;
      if ( 2 * (unsigned __int64)TempPath2W + 36 >= 0x208 )
        return 111;
      if ( (unsigned int)_o_wcsncpy_s(a1 + 2 * (TempPath2W + 88LL), 260 - TempPath2W, L"GrovTelemetry.txt", 18) )
        return 266;
      FileW = CreateFileW((LPCWSTR)(a1 + 176), 4u, 0, 0, 2u, 0x8000080u, 0);
      *(_QWORD *)(a1 + 168) = FileW;
      if ( FileW == (HANDLE)-1LL )
        return 1631;
    }
    *(_BYTE *)(a1 + 700) = *(_BYTE *)(a3 + 8);
    goto LABEL_47;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
LABEL_47:
    Property = AllocateMemory<unsigned __int64>(a1 + 152, 1000);
    if ( Property < 0 )
    {
      v14 = 591;
      goto LABEL_49;
    }
    v21 = operator new(0x10u);
    *(_QWORD *)(a1 + 160) = std::map<unsigned long,unsigned __int64>::map<unsigned long,unsigned __int64>(v21);
    *(_DWORD *)(a1 + 696) = *(_DWORD *)(a3 + 4);
    return 0;
  }
  v12 = v11 - 3;
  if ( v12 )
  {
    if ( v12 == 2 )
    {
      Property = AllocateMemory<unsigned short>(a1 + 168);
      if ( Property < 0 )
      {
        v14 = 608;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
          (const char *)(unsigned int)Property,
          pcbResult);
        return (unsigned int)Property;
      }
      *(_DWORD *)(a1 + 160) = 0x80000000;
      Property = AllocateMemory<unsigned __int64>(a1 + 176, 2000);
      if ( Property < 0 )
      {
        v14 = 612;
        goto LABEL_49;
      }
      *(_DWORD *)(a1 + 152) = 0;
    }
  }
  else
  {
    Property = AllocateMemory<unsigned short>(a1 + 176);
    if ( Property < 0 )
    {
      v14 = 620;
      goto LABEL_49;
    }
    v22 = 0;
    Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 152), L"SHA1", 0, 0);
    if ( Property < 0 )
    {
      v14 = 635;
      goto LABEL_49;
    }
    Property = BCryptGetProperty(*(BCRYPT_HANDLE *)(a1 + 152), L"HashDigestLength", (PUCHAR)(a1 + 160), 4u, &v22, 0);
    if ( Property < 0 )
    {
      v14 = 643;
      goto LABEL_49;
    }
    v15 = AllocateMemory<unsigned short>(a1 + 184);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
        (const char *)(unsigned int)v15,
        pcbResult);
      return v16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800222a8  mov     [rsp+arg_10], rbx
0x1800222ad  push    rbp
0x1800222ae  push    rsi
0x1800222af  push    rdi
0x1800222b0  push    r12
0x1800222b2  push    r15
0x1800222b4  sub     rsp, 40h
0x1800222b8  mov     rbp, r8
0x1800222bb  mov     edi, edx
0x1800222bd  mov     rbx, rcx
0x1800222c0  mov     [rcx], edx
0x1800222c2  mov     [rcx+8], r9d
0x1800222c6  mov     dword ptr [rcx+4], 21h ; '!'
0x1800222cd  call    ?EnablePrivilege@@YAHPEBG@Z; EnablePrivilege(ushort const *)
0x1800222d2  test    eax, eax
0x1800222d4  jz      short loc_1800222DB
0x1800222d6  bts     dword ptr [rbx+4], 0Eh
0x1800222db  lea     rcx, [rbx+68h]
0x1800222df  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x1800222e4  mov     esi, eax
0x1800222e6  test    eax, eax
0x1800222e8  jns     short loc_18002230A
0x1800222ea  mov     edx, 1EFh; void *
0x1800222ef  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800222f6  mov     r9d, esi; char *
0x1800222f9  mov     rcx, [rsp+68h]; this
0x1800222fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022303  mov     eax, esi
0x180022305  jmp     loc_180022667
0x18002230a  mov     dword ptr [rbx+60h], 80000000h
0x180022311  lea     rcx, [rbx+70h]
0x180022315  mov     r15d, 3E8h
0x18002231b  mov     edx, r15d
0x18002231e  call    ??$AllocateMemory@_K@@YAJPEAPEA_K_K@Z; AllocateMemory<unsigned __int64>(unsigned __int64 * *,unsigned __int64)
0x180022323  mov     esi, eax
0x180022325  test    eax, eax
0x180022327  jns     short loc_180022330
0x180022329  mov     edx, 1F7h
0x18002232e  jmp     short loc_1800222EF
0x180022330  xor     eax, eax
0x180022332  mov     [rbx+58h], ax
0x180022336  lea     rcx, [rbx+88h]
0x18002233d  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x180022342  mov     esi, eax
0x180022344  test    eax, eax
0x180022346  jns     short loc_18002234F
0x180022348  mov     edx, 200h
0x18002234d  jmp     short loc_1800222EF
0x18002234f  mov     dword ptr [rbx+80h], 80000000h
0x180022359  lea     rcx, [rbx+90h]
0x180022360  mov     rdx, r15
0x180022363  call    ??$AllocateMemory@_K@@YAJPEAPEA_K_K@Z; AllocateMemory<unsigned __int64>(unsigned __int64 * *,unsigned __int64)
0x180022368  mov     esi, eax
0x18002236a  test    eax, eax
0x18002236c  jns     short loc_180022378
0x18002236e  mov     edx, 209h
0x180022373  jmp     loc_1800222EF
0x180022378  xor     eax, eax
0x18002237a  mov     [rbx+78h], ax
0x18002237e  lea     rcx, [rbx+2D0h]
0x180022385  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x18002238a  mov     esi, eax
0x18002238c  test    eax, eax
0x18002238e  jns     short loc_18002239A
0x180022390  mov     edx, 216h
0x180022395  jmp     loc_1800222EF
0x18002239a  mov     dword ptr [rbx+2C8h], 80000000h
0x1800223a4  lea     rcx, [rbx+2D8h]
0x1800223ab  mov     rdx, r15
0x1800223ae  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x1800223b3  mov     esi, eax
0x1800223b5  test    eax, eax
0x1800223b7  jns     short loc_1800223C3
0x1800223b9  mov     edx, 21Ah
0x1800223be  jmp     loc_1800222EF
0x1800223c3  lea     rcx, [rbx+2E0h]
0x1800223ca  mov     rdx, r15
0x1800223cd  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x1800223d2  mov     esi, eax
0x1800223d4  test    eax, eax
0x1800223d6  jns     short loc_1800223E2
0x1800223d8  mov     edx, 21Ch
0x1800223dd  jmp     loc_1800222EF
0x1800223e2  lea     rcx, [rbx+2E8h]
0x1800223e9  mov     rdx, r15
0x1800223ec  call    ??$AllocateMemory@W4SCAN_ID@@@@YAJPEAPEAW4SCAN_ID@@_K@Z; AllocateMemory<SCAN_ID>(SCAN_ID * *,unsigned __int64)
0x1800223f1  mov     esi, eax
0x1800223f3  test    eax, eax
0x1800223f5  jns     short loc_180022401
0x1800223f7  mov     edx, 21Eh
0x1800223fc  jmp     loc_1800222EF
0x180022401  xor     eax, eax
0x180022403  mov     [rbx+2C0h], ax
0x18002240a  mov     [rbx+50h], ax
0x18002240e  sub     edi, 3
0x180022411  jz      loc_180022548
0x180022417  sub     edi, 1
0x18002241a  jz      loc_18002260B
0x180022420  sub     edi, 3
0x180022423  jz      short loc_180022482
0x180022425  cmp     edi, 2
0x180022428  jnz     loc_180022665
0x18002242e  lea     rcx, [rbx+0A8h]
0x180022435  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x18002243a  mov     edi, eax
0x18002243c  test    eax, eax
0x18002243e  jns     short loc_18002244A
0x180022440  mov     edx, 260h
0x180022445  jmp     loc_180022625
0x18002244a  mov     dword ptr [rbx+0A0h], 80000000h
0x180022454  lea     rcx, [rbx+0B0h]
0x18002245b  mov     edx, 7D0h
0x180022460  call    ??$AllocateMemory@_K@@YAJPEAPEA_K_K@Z; AllocateMemory<unsigned __int64>(unsigned __int64 * *,unsigned __int64)
0x180022465  mov     edi, eax
0x180022467  test    eax, eax
0x180022469  jns     short loc_180022475
0x18002246b  mov     edx, 264h
0x180022470  jmp     loc_180022625
0x180022475  xor     eax, eax
0x180022477  mov     [rbx+98h], eax
0x18002247d  jmp     loc_180022665
0x180022482  lea     rcx, [rbx+0B0h]
0x180022489  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x18002248e  mov     edi, eax
0x180022490  test    eax, eax
0x180022492  jns     short loc_18002249E
0x180022494  mov     edx, 26Ch
0x180022499  jmp     loc_180022625
0x18002249e  mov     [rsp+68h+arg_8], 0
0x1800224a6  lea     rsi, [rbx+98h]
0x1800224ad  xor     r9d, r9d; dwFlags
0x1800224b0  xor     r8d, r8d; pszImplementation
0x1800224b3  lea     rdx, pszAlgId; "SHA1"
0x1800224ba  mov     rcx, rsi; phAlgorithm
0x1800224bd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800224c3  mov     edi, eax
0x1800224c5  test    eax, eax
0x1800224c7  jns     short loc_1800224D3
0x1800224c9  mov     edx, 27Bh
0x1800224ce  jmp     loc_180022625
0x1800224d3  lea     r8, [rbx+0A0h]; pbOutput
0x1800224da  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800224e2  lea     rax, [rsp+68h+arg_8]
0x1800224e7  mov     [rsp+68h+pcbResult], rax; int
0x1800224ec  mov     r9d, 4; cbOutput
0x1800224f2  lea     rdx, pszProperty; "HashDigestLength"
0x1800224f9  mov     rcx, [rsi]; hObject
0x1800224fc  call    cs:__imp_BCryptGetProperty
0x180022502  mov     edi, eax
0x180022504  test    eax, eax
0x180022506  jns     short loc_180022512
0x180022508  mov     edx, 283h
0x18002250d  jmp     loc_180022625
0x180022512  lea     rcx, [rbx+0B8h]
0x180022519  call    ??$AllocateMemory@G@@YAJPEAPEAG_K@Z; AllocateMemory<ushort>(ushort * *,unsigned __int64)
0x18002251e  mov     ebx, eax
0x180022520  test    eax, eax
0x180022522  jns     loc_180022665
0x180022528  mov     rcx, [rsp+68h]; this
0x18002252d  mov     r9d, eax; char *
0x180022530  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180022537  mov     edx, 285h; void *
0x18002253c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022541  mov     eax, ebx
0x180022543  jmp     loc_180022667
0x180022548  cmp     [rbp+8], al
0x18002254b  jz      loc_180022602
0x180022551  lea     rsi, [rbx+0B0h]
0x180022558  mov     rdx, rsi
0x18002255b  mov     edi, 104h
0x180022560  mov     ecx, edi
0x180022562  call    cs:__imp_GetTempPath2W
0x180022568  mov     ecx, eax
0x18002256a  test    eax, eax
0x18002256c  jnz     short loc_180022578
0x18002256e  mov     eax, 3
0x180022573  jmp     loc_180022667
0x180022578  mov     r8, rcx
0x18002257b  lea     rax, ds:24h[rcx*2]
0x180022583  cmp     rax, 208h
0x180022589  jb      short loc_180022595
0x18002258b  mov     eax, 6Fh ; 'o'
0x180022590  jmp     loc_180022667
0x180022595  sub     edi, ecx
0x180022597  mov     edx, edi
0x180022599  add     r8, 58h ; 'X'
0x18002259d  lea     rcx, [rbx+r8*2]
0x1800225a1  mov     r9d, 12h
0x1800225a7  lea     r8, aGrovtelemetryT; "GrovTelemetry.txt"
0x1800225ae  call    cs:__imp__o_wcsncpy_s
0x1800225b4  test    eax, eax
0x1800225b6  jz      short loc_1800225C2
0x1800225b8  mov     eax, 10Ah
0x1800225bd  jmp     loc_180022667
0x1800225c2  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800225cb  mov     [rsp+68h+dwFlags], 8000080h; dwFlagsAndAttributes
0x1800225d3  mov     dword ptr [rsp+68h+pcbResult], 2; dwCreationDisposition
0x1800225db  xor     r9d, r9d; lpSecurityAttributes
0x1800225de  xor     r8d, r8d; dwShareMode
0x1800225e1  lea     edx, [r9+4]; dwDesiredAccess
0x1800225e5  mov     rcx, rsi; lpFileName
0x1800225e8  call    cs:__imp_CreateFileW
0x1800225ee  mov     [rbx+0A8h], rax
0x1800225f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800225f9  jnz     short loc_180022602
0x1800225fb  mov     eax, 65Fh
0x180022600  jmp     short loc_180022667
0x180022602  mov     al, [rbp+8]
0x180022605  mov     [rbx+2BCh], al
0x18002260b  lea     rcx, [rbx+98h]
0x180022612  mov     rdx, r15
0x180022615  call    ??$AllocateMemory@_K@@YAJPEAPEA_K_K@Z; AllocateMemory<unsigned __int64>(unsigned __int64 * *,unsigned __int64)
0x18002261a  mov     edi, eax
0x18002261c  test    eax, eax
0x18002261e  jns     short loc_18002263D
0x180022620  mov     edx, 24Fh; void *
0x180022625  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002262c  mov     r9d, edi; char *
0x18002262f  mov     rcx, [rsp+68h]; this
0x180022634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022639  mov     eax, edi
0x18002263b  jmp     short loc_180022667
0x18002263d  mov     ecx, 10h; Size
0x180022642  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022647  mov     [rsp+68h+arg_0], rax
0x18002264c  mov     rcx, rax
0x18002264f  call    ??0?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAA@XZ; std::map<ulong,unsigned __int64>::map<ulong,unsigned __int64>(void)
0x180022654  nop
0x180022655  mov     [rbx+0A0h], rax
0x18002265c  mov     eax, [rbp+4]
0x18002265f  mov     [rbx+2B8h], eax
0x180022665  xor     eax, eax
0x180022667  mov     rbx, [rsp+68h+arg_10]
0x18002266f  add     rsp, 40h
0x180022673  pop     r15
0x180022675  pop     r12
0x180022677  pop     rdi
0x180022678  pop     rsi
0x180022679  pop     rbp
0x18002267a  retn
```
