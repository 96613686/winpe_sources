# OfflineHive::Initialize(ushort const *,HKEY__ * *)

- ea: `0x18005781c`
- end: `0x180057b10`
- name: `?Initialize@OfflineHive@@QEAAJPEBGPEAPEAUHKEY__@@@Z`
- size: `756`
- prototype: `int(OfflineHive *__hidden this, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180057cd8`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180006828`
- `0x1800074b8`
- `0x180008940`
- `0x1800089d0`
- `0x18000d92c`
- `0x180011e20`
- `0x180011ef4`
- `0x180012968`
- `0x180033b18`
- `0x18003717c`
- `0x180037344`
- `0x18005781c`
- `0x180057ecc`

## import_xrefs

- `ADVAPI32!RegLoadKeyW` at `0x18005792c`
- `ADVAPI32!RegLoadKeyW` at `0x18005792c`
- `ADVAPI32!RegUnLoadKeyW` at `0x180057a0b`
- `ADVAPI32!RegUnLoadKeyW` at `0x180057a0b`
- `ADVAPI32!RegCreateKeyExW` at `0x1800579ec`
- `ADVAPI32!RegCreateKeyExW` at `0x1800579ec`
- `KERNEL32!Sleep` at `0x18005796b`
- `KERNEL32!Sleep` at `0x18005796b`

## string_xrefs

- `0x180057950`: `Registry: Sharing violation on [%s]`
- `0x1800579a4`: `Registry: Successfully loaded [%s] on retry`
- `0x180057a16`: `Failed to open mounted key at [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OfflineHive::Initialize(OfflineHive *this, const unsigned __int16 *a2, HKEY *a3)
{
  int i; // ebx
  __int64 v8; // rax
  unsigned int v9; // edi
  signed int v10; // edi
  unsigned __int64 v11; // r14
  const WCHAR *v12; // rbx
  LSTATUS KeyW; // eax
  LSTATUS v14; // eax
  ATL::CStringData *v15; // rcx
  unsigned int v16; // eax
  ATL::CStringData *v17; // r14
  int *v18; // rsi
  __int64 v19; // rbx
  HKEY v20; // rdx
  HKEY phkResult; // [rsp+50h] [rbp-10h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp+58h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943647LL,
      "OfflineHive::Initialize",
      "base\\reset\\util\\src\\regoffline.cpp",
      235,
      &pszFormat);
    return 2147943647LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v22,
    (__int64)a2);
  for ( i = 0; i < *(_DWORD *)(v22 - 16); ++i )
  {
    if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v22, (unsigned int)i) == 92 )
    {
      if ( i < 0 || (v8 = v22, v9 = *(_DWORD *)(v22 - 16), i >= (int)v9) )
        ATL::AtlThrowImpl(-2147024809);
      if ( *(int *)(v22 - 8) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v22, v9);
        v8 = v22;
      }
      *(_WORD *)(v8 + 2LL * i) = 36;
      ATL::CSimpleStringT<unsigned short,0>::SetLength(&v22, v9);
    }
  }
  v10 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpSubKey);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpSubKey,
    L"$PBR$REG$%s",
    v22);
  v11 = 0;
  v12 = lpSubKey;
  while ( 1 )
  {
    if ( v11 > 0xA )
    {
      if ( v10 >= 0 )
        goto LABEL_25;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v10,
        "OfflineHive::Initialize",
        "base\\reset\\util\\src\\regoffline.cpp",
        279,
        L"Failed to load [%s]",
        a2);
LABEL_29:
      v15 = (ATL::CStringData *)(v12 - 12);
      goto LABEL_38;
    }
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, v12, a2);
    v10 = KeyW;
    if ( KeyW > 0 )
      v10 = (unsigned __int16)KeyW | 0x80070000;
    if ( v10 >= 0 )
      break;
    if ( v10 != -2147024864 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v10,
        "OfflineHive::Initialize",
        "base\\reset\\util\\src\\regoffline.cpp",
        275,
        L"Failed to load [%s]",
        a2);
      goto LABEL_29;
    }
    PushButtonReset::Logging::Trace(1, L"Registry: Sharing violation on [%s]", a2);
    if ( v11 )
      Sleep(0x1388u);
    PbrUnloadOfflineHive((__int64)a2);
    ++v11;
  }
  if ( v11 )
    PushButtonReset::Logging::Trace(0, L"Registry: Successfully loaded [%s] on retry", a2);
LABEL_25:
  phkResult = 0;
  v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 4u, 0xF003Fu, 0, &phkResult, 0);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( v10 < 0 )
  {
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, v12);
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v10,
      "OfflineHive::Initialize",
      "base\\reset\\util\\src\\regoffline.cpp",
      294,
      L"Failed to open mounted key at [%s]",
      v12);
    goto LABEL_29;
  }
  v16 = ATL::CSimpleStringT<unsigned short,0>::StringLength(a2);
  ATL::CSimpleStringT<unsigned short,0>::SetString(this, a2, v16);
  v17 = (ATL::CStringData *)(v12 - 12);
  v18 = (int *)(*((_QWORD *)this + 1) - 24LL);
  if ( v12 - 12 != (const WCHAR *)v18 )
  {
    if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
    {
      v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12 - 12);
      ATL::CStringData::Release((ATL::CStringData *)v18);
      *((_QWORD *)this + 1) = v19 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 8, v12, *((unsigned int *)v12 - 4));
    }
  }
  v20 = phkResult;
  *((_QWORD *)this + 2) = phkResult;
  *a3 = v20;
  v15 = v17;
LABEL_38:
  ATL::CStringData::Release(v15);
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005781c  mov     [rsp-38h+arg_8], rbx
0x180057821  push    rbp
0x180057822  push    rsi
0x180057823  push    rdi
0x180057824  push    r12
0x180057826  push    r13
0x180057828  push    r14
0x18005782a  push    r15
0x18005782c  mov     rbp, rsp
0x18005782f  sub     rsp, 60h
0x180057833  mov     r12, r8
0x180057836  mov     rsi, rdx
0x180057839  mov     r13, rcx
0x18005783c  xor     r15d, r15d
0x18005783f  cmp     [rcx+18h], r15d
0x180057843  jz      short loc_18005787F
0x180057845  lea     rax, pszFormat
0x18005784c  mov     qword ptr [rsp+60h+samDesired], rax
0x180057851  mov     [rsp+60h+dwOptions], 0EBh
0x180057859  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057860  lea     r8, aOfflinehiveIni; "OfflineHive::Initialize"
0x180057867  mov     edx, 800704DFh
0x18005786c  lea     ecx, [r15+2]
0x180057870  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057875  mov     eax, 800704DFh
0x18005787a  jmp     loc_180057AF8
0x18005787f  lea     rcx, [rbp+arg_0]
0x180057883  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180057888  nop
0x180057889  mov     ebx, r15d
0x18005788c  mov     rax, [rbp+arg_0]
0x180057890  cmp     ebx, [rax-10h]
0x180057893  jge     short loc_1800578ED
0x180057895  mov     edx, ebx
0x180057897  lea     rcx, [rbp+arg_0]
0x18005789b  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x1800578a0  cmp     ax, 5Ch ; '\'
0x1800578a4  jnz     short loc_1800578DE
0x1800578a6  test    ebx, ebx
0x1800578a8  js      short loc_1800578E2
0x1800578aa  mov     rax, [rbp+arg_0]
0x1800578ae  mov     edi, [rax-10h]
0x1800578b1  cmp     ebx, edi
0x1800578b3  jge     short loc_1800578E2
0x1800578b5  cmp     dword ptr [rax-8], 1
0x1800578b9  jle     short loc_1800578CA
0x1800578bb  mov     edx, edi
0x1800578bd  lea     rcx, [rbp+arg_0]
0x1800578c1  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800578c6  mov     rax, [rbp+arg_0]
0x1800578ca  movsxd  rcx, ebx
0x1800578cd  mov     word ptr [rax+rcx*2], 24h ; '$'
0x1800578d3  mov     edx, edi
0x1800578d5  lea     rcx, [rbp+arg_0]
0x1800578d9  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800578de  inc     ebx
0x1800578e0  jmp     short loc_18005788C
0x1800578e2  mov     ecx, 80070057h; int
0x1800578e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800578ed  mov     edi, r15d
0x1800578f0  lea     rcx, [rbp+lpSubKey]
0x1800578f4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800578f9  nop
0x1800578fa  mov     r8, [rbp+arg_0]
0x1800578fe  lea     rdx, aPbrRegS; "$PBR$REG$%s"
0x180057905  lea     rcx, [rbp+lpSubKey]
0x180057909  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18005790e  mov     r14, r15
0x180057911  mov     rbx, [rbp+lpSubKey]
0x180057915  cmp     r14, 0Ah
0x180057919  ja      loc_180057A4E
0x18005791f  mov     r8, rsi; lpFile
0x180057922  mov     rdx, rbx; lpSubKey
0x180057925  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005792c  call    cs:__imp_RegLoadKeyW
0x180057932  mov     edi, eax
0x180057934  test    eax, eax
0x180057936  jle     short loc_180057941
0x180057938  movzx   edi, ax
0x18005793b  or      edi, 80070000h
0x180057941  test    edi, edi
0x180057943  jns     short loc_18005799C
0x180057945  cmp     edi, 80070020h
0x18005794b  jnz     short loc_18005797E
0x18005794d  mov     r8, rsi
0x180057950  lea     rdx, aRegistrySharin; "Registry: Sharing violation on [%s]"
0x180057957  mov     ecx, 1
0x18005795c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180057961  test    r14, r14
0x180057964  jz      short loc_180057971
0x180057966  mov     ecx, 1388h; dwMilliseconds
0x18005796b  call    cs:__imp_Sleep
0x180057971  mov     rcx, rsi
0x180057974  call    PbrUnloadOfflineHive
0x180057979  inc     r14
0x18005797c  jmp     short loc_180057915
0x18005797e  mov     [rsp+60h+lpSecurityAttributes], rsi
0x180057983  lea     rax, aFailedToLoadS; "Failed to load [%s]"
0x18005798a  mov     qword ptr [rsp+60h+samDesired], rax
0x18005798f  mov     [rsp+60h+dwOptions], 113h
0x180057997  jmp     loc_180057A2A
0x18005799c  test    r14, r14
0x18005799f  jz      short loc_1800579B2
0x1800579a1  mov     r8, rsi
0x1800579a4  lea     rdx, aRegistrySucces_0; "Registry: Successfully loaded [%s] on r"...
0x1800579ab  xor     ecx, ecx
0x1800579ad  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800579b2  mov     [rbp+var_10], r15
0x1800579b6  mov     [rsp+60h+lpdwDisposition], r15; lpdwDisposition
0x1800579bb  lea     rax, [rbp+var_10]
0x1800579bf  mov     [rsp+60h+phkResult], rax; phkResult
0x1800579c4  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800579c9  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800579d1  mov     [rsp+60h+dwOptions], 4; dwOptions
0x1800579d9  xor     r9d, r9d; lpClass
0x1800579dc  xor     r8d, r8d; Reserved
0x1800579df  mov     rdx, rbx; lpSubKey
0x1800579e2  mov     r14, 0FFFFFFFF80000002h
0x1800579e9  mov     rcx, r14; hKey
0x1800579ec  call    cs:__imp_RegCreateKeyExW
0x1800579f2  mov     edi, eax
0x1800579f4  test    eax, eax
0x1800579f6  jle     short loc_180057A01
0x1800579f8  movzx   edi, ax
0x1800579fb  or      edi, 80070000h
0x180057a01  test    edi, edi
0x180057a03  jns     short loc_180057A71
0x180057a05  mov     rdx, rbx; lpSubKey
0x180057a08  mov     rcx, r14; hKey
0x180057a0b  call    cs:__imp_RegUnLoadKeyW
0x180057a11  mov     [rsp+60h+lpSecurityAttributes], rbx
0x180057a16  lea     rax, aFailedToOpenMo; "Failed to open mounted key at [%s]"
0x180057a1d  mov     qword ptr [rsp+60h+samDesired], rax
0x180057a22  mov     [rsp+60h+dwOptions], 126h
0x180057a2a  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057a31  lea     r8, aOfflinehiveIni; "OfflineHive::Initialize"
0x180057a38  mov     edx, edi
0x180057a3a  mov     ecx, 2
0x180057a3f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057a44  nop
0x180057a45  lea     rcx, [rbx-18h]
0x180057a49  jmp     loc_180057AE3
0x180057a4e  test    edi, edi
0x180057a50  jns     loc_1800579B2
0x180057a56  mov     [rsp+60h+lpSecurityAttributes], rsi
0x180057a5b  lea     rax, aFailedToLoadS; "Failed to load [%s]"
0x180057a62  mov     qword ptr [rsp+60h+samDesired], rax
0x180057a67  mov     [rsp+60h+dwOptions], 117h
0x180057a6f  jmp     short loc_180057A2A
0x180057a71  mov     rcx, rsi
0x180057a74  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180057a79  mov     r8d, eax
0x180057a7c  mov     rdx, rsi
0x180057a7f  mov     rcx, r13
0x180057a82  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180057a87  lea     r15, [r13+8]
0x180057a8b  lea     r14, [rbx-18h]
0x180057a8f  mov     rsi, [r15]
0x180057a92  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180057a96  cmp     r14, rsi
0x180057a99  jz      short loc_180057AD4
0x180057a9b  cmp     dword ptr [rsi+10h], 0
0x180057a9f  jl      short loc_180057AC5
0x180057aa1  mov     rax, [rsi]
0x180057aa4  cmp     [r14], rax
0x180057aa7  jnz     short loc_180057AC5
0x180057aa9  mov     rcx, r14
0x180057aac  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180057ab1  mov     rbx, rax
0x180057ab4  mov     rcx, rsi; this
0x180057ab7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057abc  lea     rax, [rbx+18h]
0x180057ac0  mov     [r15], rax
0x180057ac3  jmp     short loc_180057AD4
0x180057ac5  mov     r8d, [rbx-10h]
0x180057ac9  mov     rdx, rbx
0x180057acc  mov     rcx, r15
0x180057acf  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180057ad4  mov     rdx, [rbp+var_10]
0x180057ad8  mov     [r13+10h], rdx
0x180057adc  mov     [r12], rdx
0x180057ae0  mov     rcx, r14; this
0x180057ae3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057ae8  nop
0x180057ae9  mov     rcx, [rbp+arg_0]
0x180057aed  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180057af1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057af6  mov     eax, edi
0x180057af8  mov     rbx, [rsp+60h+arg_8]
0x180057b00  add     rsp, 60h
0x180057b04  pop     r15
0x180057b06  pop     r14
0x180057b08  pop     r13
0x180057b0a  pop     r12
0x180057b0c  pop     rdi
0x180057b0d  pop     rsi
0x180057b0e  pop     rbp
0x180057b0f  retn
```
