# ADPDatabase::GenerateEncryptionKey(uchar * const,int)

- ea: `0x1800329f8`
- end: `0x180032bce`
- name: `?GenerateEncryptionKey@ADPDatabase@@AEAAXQEAEH@Z`
- size: `470`
- prototype: `void __fastcall(ADPDatabase *this, PUCHAR pbBuffer)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003240c`
- `0x180033814`

## callees

- `0x180001008`
- `0x180002250`
- `0x180002cf8`
- `0x18000771c`
- `0x18000e1d0`
- `0x180025558`
- `0x180032920`
- `0x1800329f8`
- `0x180034160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032b5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032b5c`
- `CRYPT32!CryptProtectData` at `0x180032ac3`
- `CRYPT32!CryptProtectData` at `0x180032ac3`
- `bcrypt!BCryptGenRandom` at `0x180032a7b`
- `bcrypt!BCryptGenRandom` at `0x180032a7b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180032b37`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180032b37`

## string_xrefs

- `0x180032b90`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180032bbc`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
void __fastcall ADPDatabase::GenerateEncryptionKey(ADPDatabase *this, PUCHAR pbBuffer)
{
  char *v2; // rbx
  char *v5; // rdi
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  NTSTATUS v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // eax
  int pPromptStruct; // [rsp+20h] [rbp-E0h]
  unsigned int pPromptStructa; // [rsp+20h] [rbp-E0h]
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-C0h] BYREF
  int v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v2 = (char *)this + 104;
  if ( *((_QWORD *)this + 16) <= 7u )
    v5 = (char *)this + 104;
  else
    v5 = *(char **)v2;
  v6 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    *(_QWORD *)v17 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)v6,
      (unsigned int)byte_1801006D9,
      v7,
      v8,
      (__int64)v17);
  }
  v9 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(retaddr, v10, v11, (const char *)(unsigned int)v9, pPromptStruct);
  *(_QWORD *)&pDataIn.cbData = 32;
  pDataIn.pbData = pbBuffer;
  pDataOut = 0;
  if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      v12);
  memset_0(SubKey, 0, 0x1FEu);
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(char **)v2;
  ADPDatabase::FillEncryptionKeyPath(
    this,
    SubKey,
    255,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\AggregatedDataPlatform\\Keys",
    v2);
  v13 = RegSetKeyValueW(HKEY_CURRENT_USER, SubKey, L"Key", 3u, pDataOut.pbData, pDataOut.cbData);
  if ( v13 )
    wil::details::in1diag3::_FailFast_Win32(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      (const char *)v13,
      pPromptStructa);
  if ( pDataOut.pbData )
  {
    memset_0(pDataOut.pbData, 0, pDataOut.cbData);
    LocalFree(pDataOut.pbData);
  }
}

```

## disassembly

```asm
0x1800329f8  mov     [rsp-8+arg_10], rbx
0x1800329fd  mov     [rsp-8+arg_18], rsi
0x180032a02  push    rbp
0x180032a03  push    rdi
0x180032a04  push    r14
0x180032a06  lea     rbp, [rsp-180h]
0x180032a0e  sub     rsp, 280h
0x180032a15  mov     rax, cs:__security_cookie
0x180032a1c  xor     rax, rsp
0x180032a1f  mov     [rbp+190h+var_20], rax
0x180032a26  lea     rbx, [rcx+68h]
0x180032a2a  mov     rsi, rdx
0x180032a2d  cmp     qword ptr [rbx+18h], 7
0x180032a32  mov     r14, rcx
0x180032a35  jbe     short loc_180032A3C
0x180032a37  mov     rdi, [rbx]
0x180032a3a  jmp     short loc_180032A3F
0x180032a3c  mov     rdi, rbx
0x180032a3f  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180032a44  mov     rcx, [rax+8]
0x180032a48  mov     eax, [rcx]
0x180032a4a  cmp     eax, 4
0x180032a4d  jbe     short loc_180032A6A
0x180032a4f  lea     rax, [rsp+290h+var_240]
0x180032a54  mov     qword ptr [rsp+290h+var_240], rdi
0x180032a59  lea     rdx, byte_1801006D9
0x180032a60  mov     [rsp+290h+pPromptStruct], rax; int
0x180032a65  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180032a6a  mov     edi, 20h ; ' '
0x180032a6f  mov     rdx, rsi; pbBuffer
0x180032a72  mov     r8d, edi; cbBuffer
0x180032a75  xor     ecx, ecx; hAlgorithm
0x180032a77  lea     r9d, [rdi-1Eh]; dwFlags
0x180032a7b  call    cs:__imp_BCryptGenRandom
0x180032a81  test    eax, eax
0x180032a83  js      loc_180032BA5
0x180032a89  lea     rax, [rsp+290h+var_250]
0x180032a8e  mov     qword ptr [rsp+290h+pDataIn.cbData], rdi
0x180032a93  mov     [rsp+290h+pDataOut], rax; pDataOut
0x180032a98  lea     rcx, [rsp+290h+pDataIn]; pDataIn
0x180032a9d  xorps   xmm0, xmm0
0x180032aa0  mov     [rsp+290h+dwFlags], 1; dwFlags
0x180032aa8  xor     r9d, r9d; pvReserved
0x180032aab  mov     [rsp+290h+pPromptStruct], 0; pPromptStruct
0x180032ab4  xor     r8d, r8d; pOptionalEntropy
0x180032ab7  mov     [rsp+290h+pDataIn.pbData], rsi
0x180032abc  xor     edx, edx; szDataDescr
0x180032abe  movups  xmmword ptr [rsp+290h+var_250.cbData], xmm0
0x180032ac3  call    cs:__imp_CryptProtectData
0x180032ac9  test    eax, eax
0x180032acb  jz      loc_180032BB5
0x180032ad1  xor     edx, edx; Val
0x180032ad3  lea     rcx, [rsp+290h+SubKey]; void *
0x180032ad8  mov     r8d, 1FEh; Size
0x180032ade  call    memset_0
0x180032ae3  cmp     qword ptr [rbx+18h], 7
0x180032ae8  jbe     short loc_180032AED
0x180032aea  mov     rbx, [rbx]
0x180032aed  mov     r9, cs:off_1800CC760; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032af4  lea     rdx, [rsp+290h+SubKey]; wchar_t *
0x180032af9  mov     r8d, 0FFh; int
0x180032aff  mov     [rsp+290h+pPromptStruct], rbx
0x180032b04  mov     rcx, r14; this
0x180032b07  call    ?FillEncryptionKeyPath@ADPDatabase@@AEAAXPEB_WHZZ; ADPDatabase::FillEncryptionKeyPath(wchar_t const *,int,...)
0x180032b0c  mov     eax, [rsp+290h+var_250.cbData]
0x180032b10  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180032b15  mov     r8, cs:lpValueName; lpValueName
0x180032b1c  mov     r9d, 3; dwType
0x180032b22  mov     [rsp+290h+dwFlags], eax; cbData
0x180032b26  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180032b2d  mov     rax, [rsp+290h+var_250.pbData]
0x180032b32  mov     [rsp+290h+pPromptStruct], rax; unsigned int
0x180032b37  call    cs:__imp_RegSetKeyValueW
0x180032b3d  test    eax, eax
0x180032b3f  jnz     short loc_180032B89
0x180032b41  mov     rcx, [rsp+290h+var_250.pbData]; void *
0x180032b46  test    rcx, rcx
0x180032b49  jz      short loc_180032B62
0x180032b4b  mov     r8d, [rsp+290h+var_250.cbData]; Size
0x180032b50  xor     edx, edx; Val
0x180032b52  call    memset_0
0x180032b57  mov     rcx, [rsp+290h+var_250.pbData]; hMem
0x180032b5c  call    cs:__imp_LocalFree
0x180032b62  mov     rcx, [rbp+190h+var_20]
0x180032b69  xor     rcx, rsp; StackCookie
0x180032b6c  call    __security_check_cookie
0x180032b71  lea     r11, [rsp+290h+var_10]
0x180032b79  mov     rbx, [r11+30h]
0x180032b7d  mov     rsi, [r11+38h]
0x180032b81  mov     rsp, r11
0x180032b84  pop     r14
0x180032b86  pop     rdi
0x180032b87  pop     rbp
0x180032b88  retn
0x180032b89  mov     rcx, [rbp+198h]; this
0x180032b90  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180032b97  mov     r9d, eax; char *
0x180032b9a  mov     edx, 0CBh; void *
0x180032b9f  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x180032ba5  mov     rcx, [rbp+198h]; this
0x180032bac  mov     r9d, eax; char *
0x180032baf  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x180032bb5  mov     rcx, [rbp+198h]; this
0x180032bbc  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180032bc3  mov     edx, 0B9h; void *
0x180032bc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
