# PluginInitialize(ulong,_GUID *,_CLOUDAP_SECPKG_FUNCTION_TABLE *,ulong *,ushort * const,uchar * const,void * *,void * *,_APPLUGIN_SECPKG_FUNCTION_TABLE *)

- ea: `0x18000a4a0`
- end: `0x18000a7de`
- name: `?PluginInitialize@@YAJKPEAU_GUID@@PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@PEAKQEAGQEAEPEAPEAX5PEAU_APPLUGIN_SECPKG_FUNCTION_TABLE@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(int, struct _GUID *, struct _CLOUDAP_SECPKG_FUNCTION_TABLE *, unsigned int *, unsigned __int16 *const, unsigned __int8 *const, void **, void **, struct _APPLUGIN_SECPKG_FUNCTION_TABLE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007f50`

## callees

- `0x180001010`
- `0x180003160`
- `0x180003b14`
- `0x180007eb8`
- `0x180008260`
- `0x180008900`
- `0x18000a4a0`
- `0x18000c78c`
- `0x18000fd0c`
- `0x180010064`
- `0x1800267c0`
- `0x180026870`
- `0x180027a54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a5b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6e5`
- `CRYPTSP!CryptAcquireContextA` at `0x18000a6c7`
- `CRYPTSP!CryptAcquireContextA` at `0x18000a6c7`

## string_xrefs

- `0x18000a5ed`: `onecoreuap\ds\ext\live\identity\cloudapplugin\msacloudap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PluginInitialize(
        int a1,
        struct _GUID *a2,
        struct _CLOUDAP_SECPKG_FUNCTION_TABLE *a3,
        unsigned int *a4,
        unsigned __int16 *const a5,
        unsigned __int8 *const a6,
        void **a7,
        void **a8,
        struct _APPLUGIN_SECPKG_FUNCTION_TABLE *a9)
{
  unsigned __int16 *v13; // rdi
  _QWORD *v14; // r15
  int v15; // eax
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  __int64 v18; // r8
  wchar_t v19; // dx
  signed int LastError; // ebx
  unsigned __int16 *v21; // rcx
  errno_t v22; // eax
  HCRYPTPROV v23; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  rsize_t SourceSize; // [rsp+30h] [rbp-D0h] BYREF
  void *Destination; // [rsp+38h] [rbp-C8h]
  void **v28; // [rsp+40h] [rbp-C0h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-B8h] BYREF
  void **v30; // [rsp+50h] [rbp-B0h]
  _BYTE v31[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Source[80]; // [rsp+A0h] [rbp-60h] BYREF

  v13 = a5;
  Destination = a6;
  v30 = a8;
  memset_0(Source, 0, 0x44u);
  LODWORD(SourceSize) = 68;
  phProv = 0;
  v28 = &SmartHCRYPTPROV::`vftable';
  if ( a1 == 1 && a2 && a3 && a4 && a7 && (v14 = v30) != 0 && a9 )
  {
    *a4 = 0;
    *(_OWORD *)a5 = 0;
    *((_OWORD *)a5 + 1) = 0;
    *(_OWORD *)(a5 + 13) = 0;
    memset_0(Destination, 0, 0x44u);
    *a7 = 0;
    *v14 = 0;
    g_MSACloudAPPluginLsaFunctions = a3;
    McGenEventRegister_EventRegister();
    dword_18004DD9C = 1;
    if ( !GetModuleFileNameW(0, &Filename, 0x105u) )
      Filename = 0;
    TraceState();
    v15 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18004D048);
    if ( v15 < 0 )
    {
      dwFlags = v15;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\msacloudap.cpp",
        0x6Fu,
        L"TraceLoggingRegister failed with 0x%x, continuing...",
        dwFlags);
    }
    *a4 = 3;
    v16 = 2147483646;
    v17 = L"MicrosoftAccount";
    v18 = 21;
    do
    {
      if ( !v16 )
        break;
      v19 = *v17;
      if ( !*v17 )
        break;
      ++v17;
      *v13++ = v19;
      --v16;
      --v18;
    }
    while ( v18 );
    LastError = v18 == 0 ? 0x80000005 : 0;
    v21 = v13 - 1;
    if ( v18 )
      v21 = v13;
    *v21 = 0;
    if ( v18
      && (LastError = LiveConvertIdentityToSid(0, Source, (unsigned int *)&SourceSize), LastError >= 0)
      && (v22 = memcpy_s_0(Destination, 0x44u, Source, (unsigned int)SourceSize),
          LastError = LiveMapHResultToNtStatus(v22 != 0 ? 0x8000FFFF : 0),
          LastError >= 0)
      && (CryptAcquireContextA(&phProv, 0, "Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000048)
       || ((int)GetLastError() > 0
         ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
         : (LastError = GetLastError()),
           LastError >= 0)) )
    {
      v23 = phProv;
      phProv = 0;
      *v14 = v23;
      *(_OWORD *)a9 = g_MSACloudAPPluginFunctionTable;
      *((_OWORD *)a9 + 1) = xmmword_18004D550;
      *((_OWORD *)a9 + 2) = xmmword_18004D560;
      *((_OWORD *)a9 + 3) = xmmword_18004D570;
      *((_OWORD *)a9 + 4) = *(_OWORD *)byte_18004D580;
      *((_OWORD *)a9 + 5) = xmmword_18004D590;
      *((_OWORD *)a9 + 6) = xmmword_18004D5A0;
      *((_OWORD *)a9 + 7) = xmmword_18004D5B0;
      *((_OWORD *)a9 + 8) = xmmword_18004D5C0;
      *((_OWORD *)a9 + 9) = xmmword_18004D5D0;
      *((_OWORD *)a9 + 10) = xmmword_18004D5E0;
      ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v31);
      CWLIDCCHelper::SetClockReliabilityData((struct IExecutionContextLite *)v31);
    }
    else
    {
      TraceState();
    }
  }
  else
  {
    LastError = -1073741811;
  }
  SmartHCRYPTPROV::~SmartHCRYPTPROV((SmartHCRYPTPROV *)&v28);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000a4a0  push    rbp
0x18000a4a2  push    rbx
0x18000a4a3  push    rsi
0x18000a4a4  push    rdi
0x18000a4a5  push    r12
0x18000a4a7  push    r13
0x18000a4a9  push    r14
0x18000a4ab  push    r15
0x18000a4ad  lea     rbp, [rsp-8]
0x18000a4b2  sub     rsp, 108h
0x18000a4b9  mov     rax, cs:__security_cookie
0x18000a4c0  xor     rax, rsp
0x18000a4c3  mov     [rbp+40h+var_50], rax
0x18000a4c7  mov     r14, r9
0x18000a4ca  mov     r12, r8
0x18000a4cd  mov     r15, rdx
0x18000a4d0  mov     ebx, ecx
0x18000a4d2  mov     rdi, [rbp+40h+arg_20]
0x18000a4d6  mov     rax, [rbp+40h+arg_28]
0x18000a4da  mov     [rsp+140h+Destination], rax
0x18000a4df  mov     r13, [rbp+40h+arg_30]
0x18000a4e6  mov     rax, [rbp+40h+arg_38]
0x18000a4ed  mov     [rsp+140h+var_F0], rax
0x18000a4f2  mov     rsi, [rbp+40h+arg_40]
0x18000a4f9  xor     edx, edx; Val
0x18000a4fb  lea     r8d, [rdx+44h]; Size
0x18000a4ff  lea     rcx, [rbp+40h+Source]; void *
0x18000a503  call    memset_0
0x18000a508  mov     ecx, 44h ; 'D'
0x18000a50d  mov     dword ptr [rsp+140h+SourceSize], ecx
0x18000a511  xor     eax, eax
0x18000a513  mov     [rsp+140h+phProv], rax
0x18000a518  lea     rax, ??_7SmartHCRYPTPROV@@6B@; const SmartHCRYPTPROV::`vftable'
0x18000a51f  mov     [rsp+140h+var_100], rax
0x18000a524  cmp     ebx, 1
0x18000a527  jnz     loc_18000A7AD
0x18000a52d  xor     ebx, ebx
0x18000a52f  test    r15, r15
0x18000a532  jz      loc_18000A7AD
0x18000a538  test    r12, r12
0x18000a53b  jz      loc_18000A7AD
0x18000a541  test    r14, r14
0x18000a544  jz      loc_18000A7AD
0x18000a54a  test    r13, r13
0x18000a54d  jz      loc_18000A7AD
0x18000a553  mov     r15, [rsp+140h+var_F0]
0x18000a558  test    r15, r15
0x18000a55b  jz      loc_18000A7AD
0x18000a561  test    rsi, rsi
0x18000a564  jz      loc_18000A7AD
0x18000a56a  mov     [r14], ebx
0x18000a56d  xorps   xmm0, xmm0
0x18000a570  movups  xmmword ptr [rdi], xmm0
0x18000a573  movups  xmmword ptr [rdi+10h], xmm0
0x18000a577  movups  xmmword ptr [rdi+1Ah], xmm0
0x18000a57b  mov     r8d, ecx; Size
0x18000a57e  xor     edx, edx; Val
0x18000a580  mov     rcx, [rsp+140h+Destination]; void *
0x18000a585  call    memset_0
0x18000a58a  mov     [r13+0], rbx
0x18000a58e  mov     [r15], rbx
0x18000a591  mov     cs:?g_MSACloudAPPluginLsaFunctions@@3PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@EA, r12; _CLOUDAP_SECPKG_FUNCTION_TABLE * g_MSACloudAPPluginLsaFunctions
0x18000a598  call    McGenEventRegister_EventRegister
0x18000a59d  mov     cs:dword_18004DD9C, 1
0x18000a5a7  mov     r8d, 105h; nSize
0x18000a5ad  lea     rdx, Filename; lpFilename
0x18000a5b4  xor     ecx, ecx; hModule
0x18000a5b6  call    cs:__imp_GetModuleFileNameW
0x18000a5bc  test    eax, eax
0x18000a5be  jnz     short loc_18000A5C7
0x18000a5c0  mov     cs:Filename, bx
0x18000a5c7  call    TraceState
0x18000a5cc  lea     rcx, dword_18004D048; CallbackContext
0x18000a5d3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000a5d8  test    eax, eax
0x18000a5da  jns     short loc_18000A5FD
0x18000a5dc  mov     [rsp+140h+dwFlags], eax
0x18000a5e0  lea     r9, aTraceloggingre; "TraceLoggingRegister failed with 0x%x, "...
0x18000a5e7  mov     r8d, 6Fh ; 'o'; unsigned int
0x18000a5ed  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000a5f4  lea     ecx, [r8-6Dh]; unsigned __int8
0x18000a5f8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000a5fd  mov     dword ptr [r14], 3
0x18000a604  mov     eax, 7FFFFFFEh
0x18000a609  lea     rcx, aMicrosoftaccou_1; "MicrosoftAccount"
0x18000a610  mov     r8d, 15h
0x18000a616  test    rax, rax
0x18000a619  jz      short loc_18000A637
0x18000a61b  movzx   edx, word ptr [rcx]
0x18000a61e  test    dx, dx
0x18000a621  jz      short loc_18000A637
0x18000a623  add     rcx, 2
0x18000a627  mov     [rdi], dx
0x18000a62a  add     rdi, 2
0x18000a62e  dec     rax
0x18000a631  sub     r8, 1
0x18000a635  jnz     short loc_18000A616
0x18000a637  mov     rax, r8
0x18000a63a  neg     rax
0x18000a63d  sbb     ebx, ebx
0x18000a63f  not     ebx
0x18000a641  and     ebx, 80000005h
0x18000a647  lea     rcx, [rdi-2]
0x18000a64b  test    r8, r8
0x18000a64e  cmovnz  rcx, rdi
0x18000a652  xor     eax, eax
0x18000a654  mov     [rcx], ax
0x18000a657  test    r8, r8
0x18000a65a  jz      loc_18000A7A6
0x18000a660  lea     r8, [rsp+140h+SourceSize]; unsigned int *
0x18000a665  lea     rdx, [rbp+40h+Source]; Sid
0x18000a669  xor     ecx, ecx; SourceString
0x18000a66b  call    ?LiveConvertIdentityToSid@@YAJPEBGPEAEPEAK@Z; LiveConvertIdentityToSid(ushort const *,uchar *,ulong *)
0x18000a670  mov     ebx, eax
0x18000a672  test    eax, eax
0x18000a674  js      loc_18000A7A6
0x18000a67a  mov     r9d, dword ptr [rsp+140h+SourceSize]; SourceSize
0x18000a67f  lea     r8, [rbp+40h+Source]; Source
0x18000a683  mov     edx, 44h ; 'D'; DestinationSize
0x18000a688  mov     rcx, [rsp+140h+Destination]; Destination
0x18000a68d  call    memcpy_s_0
0x18000a692  neg     eax
0x18000a694  sbb     ecx, ecx
0x18000a696  and     ecx, 8000FFFFh; int
0x18000a69c  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000a6a1  mov     ebx, eax
0x18000a6a3  test    eax, eax
0x18000a6a5  js      loc_18000A7A6
0x18000a6ab  mov     [rsp+140h+dwFlags], 0F0000048h; dwFlags
0x18000a6b3  mov     r9d, 18h; dwProvType
0x18000a6b9  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18000a6c0  xor     edx, edx; szContainer
0x18000a6c2  lea     rcx, [rsp+140h+phProv]; phProv
0x18000a6c7  call    cs:__imp_CryptAcquireContextA
0x18000a6cd  test    eax, eax
0x18000a6cf  jnz     short loc_18000A6FC
0x18000a6d1  call    cs:__imp_GetLastError
0x18000a6d7  test    eax, eax
0x18000a6d9  jg      short loc_18000A6E5
0x18000a6db  call    cs:__imp_GetLastError
0x18000a6e1  mov     ebx, eax
0x18000a6e3  jmp     short loc_18000A6F4
0x18000a6e5  call    cs:__imp_GetLastError
0x18000a6eb  movzx   ebx, ax
0x18000a6ee  or      ebx, 0C0070000h
0x18000a6f4  test    ebx, ebx
0x18000a6f6  js      loc_18000A7A6
0x18000a6fc  mov     rax, [rsp+140h+phProv]
0x18000a701  mov     [rsp+140h+phProv], 0
0x18000a70a  mov     [r15], rax
0x18000a70d  movaps  xmm0, cs:?g_MSACloudAPPluginFunctionTable@@3U_APPLUGIN_SECPKG_FUNCTION_TABLE@@A; _APPLUGIN_SECPKG_FUNCTION_TABLE g_MSACloudAPPluginFunctionTable
0x18000a714  movups  xmmword ptr [rsi], xmm0
0x18000a717  movaps  xmm1, cs:xmmword_18004D550
0x18000a71e  movups  xmmword ptr [rsi+10h], xmm1
0x18000a722  movaps  xmm0, cs:xmmword_18004D560
0x18000a729  movups  xmmword ptr [rsi+20h], xmm0
0x18000a72d  movaps  xmm1, cs:xmmword_18004D570
0x18000a734  movups  xmmword ptr [rsi+30h], xmm1
0x18000a738  movaps  xmm0, xmmword ptr cs:byte_18004D580
0x18000a73f  movups  xmmword ptr [rsi+40h], xmm0
0x18000a743  movaps  xmm1, cs:xmmword_18004D590
0x18000a74a  movups  xmmword ptr [rsi+50h], xmm1
0x18000a74e  movaps  xmm0, cs:xmmword_18004D5A0
0x18000a755  movups  xmmword ptr [rsi+60h], xmm0
0x18000a759  movaps  xmm1, cs:xmmword_18004D5B0
0x18000a760  movups  xmmword ptr [rsi+70h], xmm1
0x18000a764  movaps  xmm0, cs:xmmword_18004D5C0
0x18000a76b  movups  xmmword ptr [rsi+80h], xmm0
0x18000a772  movaps  xmm1, cs:xmmword_18004D5D0
0x18000a779  movups  xmmword ptr [rsi+90h], xmm1
0x18000a780  movaps  xmm0, cs:xmmword_18004D5E0
0x18000a787  movups  xmmword ptr [rsi+0A0h], xmm0
0x18000a78e  lea     rcx, [rsp+140h+var_E0]; this
0x18000a793  call    ??0ExecutionContextLite@@QEAA@XZ; ExecutionContextLite::ExecutionContextLite(void)
0x18000a798  nop
0x18000a799  lea     rcx, [rsp+140h+var_E0]; struct IExecutionContextLite *
0x18000a79e  call    ?SetClockReliabilityData@CWLIDCCHelper@@SAJPEAVIExecutionContextLite@@@Z; CWLIDCCHelper::SetClockReliabilityData(IExecutionContextLite *)
0x18000a7a3  nop
0x18000a7a4  jmp     short loc_18000A7B2
0x18000a7a6  call    TraceState
0x18000a7ab  jmp     short loc_18000A7B2
0x18000a7ad  mov     ebx, 0C000000Dh
0x18000a7b2  lea     rcx, [rsp+140h+var_100]; this
0x18000a7b7  call    ??1SmartHCRYPTPROV@@UEAA@XZ; SmartHCRYPTPROV::~SmartHCRYPTPROV(void)
0x18000a7bc  mov     eax, ebx
0x18000a7be  mov     rcx, [rbp+40h+var_50]
0x18000a7c2  xor     rcx, rsp; StackCookie
0x18000a7c5  call    __security_check_cookie
0x18000a7ca  add     rsp, 108h
0x18000a7d1  pop     r15
0x18000a7d3  pop     r14
0x18000a7d5  pop     r13
0x18000a7d7  pop     r12
0x18000a7d9  pop     rdi
0x18000a7da  pop     rsi
0x18000a7db  pop     rbx
0x18000a7dc  pop     rbp
0x18000a7dd  retn
```
