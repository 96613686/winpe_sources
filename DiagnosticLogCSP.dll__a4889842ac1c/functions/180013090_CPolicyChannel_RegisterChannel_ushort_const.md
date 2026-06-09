# CPolicyChannel::RegisterChannel(ushort const *)

- ea: `0x180013090`
- end: `0x18001328d`
- name: `?RegisterChannel@CPolicyChannel@@SAJPEBG@Z`
- size: `509`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x180010de0`
- `0x18001107c`
- `0x180013090`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800130ee`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800130ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013228`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800131e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800131e1`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::RegisterChannel(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, __int64 a4)
{
  const unsigned __int16 *v4; // rdi
  signed int Key; // ebx
  __int64 v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rdx
  signed int v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult[3]; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v12; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v14[1024]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[512]; // [rsp+490h] [rbp+390h] BYREF

  v4 = a1;
  if ( a1 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v14, 1024, 0) >= 0 )
      goto LABEL_11;
    v6 = 2147483646;
    v7 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v8 = 512;
    a3 = (unsigned __int16 *)v14;
    do
    {
      if ( !v6 )
        break;
      a4 = *v7;
      if ( !(_WORD)a4 )
        break;
      *a3 = a4;
      ++v7;
      ++a3;
      --v6;
      --v8;
    }
    while ( v8 );
    a1 = a3 - 1;
    Key = v8 == 0 ? 0x8007007A : 0;
    if ( v8 )
      a1 = a3;
    *a1 = 0;
    if ( v8 )
    {
LABEL_11:
      Key = StringCchPrintfW(SubKey, 0x200u, L"%s\\%s", v14, L"Policies");
      if ( Key >= 0 )
      {
        memset(phkResult, 0, sizeof(phkResult));
        if ( !(unsigned int)CRegUtils::OpenKey(SubKey, phkResult)
          || (Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, phkResult, 0), Key >= 0) )
        {
          memset(hKey, 0, sizeof(hKey));
          Key = CRegUtils::CreateKey(phkResult, hKey, v4);
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
        }
        a1 = (unsigned __int16 *)phkResult[0];
        if ( phkResult[0] )
          RegCloseKey(phkResult[0]);
      }
    }
  }
  else
  {
    Key = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v10 = Key;
    if ( !v4 )
      v4 = &String2;
    v12 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&byte_18003FF8F,
      (__int64)a3,
      a4,
      &v12,
      (__int64)&v10);
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180013090  push    rbp
0x180013092  push    rbx
0x180013093  push    rsi
0x180013094  push    rdi
0x180013095  lea     rbp, [rsp-7A8h]
0x18001309d  sub     rsp, 8A8h
0x1800130a4  mov     rax, cs:__security_cookie
0x1800130ab  xor     rax, rsp
0x1800130ae  mov     [rbp+7C0h+var_30], rax
0x1800130b5  xor     esi, esi
0x1800130b7  mov     rdi, rcx
0x1800130ba  test    rcx, rcx
0x1800130bd  jnz     short loc_1800130C9
0x1800130bf  mov     ebx, 80070057h
0x1800130c4  jmp     loc_18001322E
0x1800130c9  mov     [rsp+8C0h+lpSecurityAttributes], rsi
0x1800130ce  lea     rax, [rbp+7C0h+var_830]
0x1800130d2  mov     [rsp+8C0h+samDesired], 400h
0x1800130da  lea     rcx, aWinevt; "WINEVT"
0x1800130e1  xor     r9d, r9d
0x1800130e4  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x1800130e9  xor     r8d, r8d
0x1800130ec  xor     edx, edx
0x1800130ee  call    cs:__imp_RtlGetPersistedStateLocation
0x1800130f4  mov     r10d, 200h
0x1800130fa  test    eax, eax
0x1800130fc  jns     short loc_180013159
0x1800130fe  mov     eax, 7FFFFFFEh
0x180013103  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001310a  mov     edx, r10d
0x18001310d  lea     r8, [rbp+7C0h+var_830]
0x180013111  test    rax, rax
0x180013114  jz      short loc_180013135
0x180013116  movzx   r9d, word ptr [rcx]
0x18001311a  test    r9w, r9w
0x18001311e  jz      short loc_180013135
0x180013120  mov     [r8], r9w
0x180013124  add     rcx, 2
0x180013128  add     r8, 2
0x18001312c  dec     rax
0x18001312f  sub     rdx, 1
0x180013133  jnz     short loc_180013111
0x180013135  mov     rax, rdx
0x180013138  lea     rcx, [r8-2]
0x18001313c  neg     rax
0x18001313f  sbb     ebx, ebx
0x180013141  not     ebx
0x180013143  and     ebx, 8007007Ah
0x180013149  test    rdx, rdx
0x18001314c  cmovnz  rcx, r8
0x180013150  mov     [rcx], si
0x180013153  jz      loc_18001322E
0x180013159  lea     rax, aPolicies; "Policies"
0x180013160  mov     rdx, r10; unsigned __int64
0x180013163  lea     r9, [rbp+7C0h+var_830]
0x180013167  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x18001316c  lea     r8, aSS_0; "%s\\%s"
0x180013173  lea     rcx, [rbp+7C0h+SubKey]; unsigned __int16 *
0x18001317a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001317f  mov     ebx, eax
0x180013181  test    eax, eax
0x180013183  js      loc_18001322E
0x180013189  lea     rdx, [rsp+8C0h+var_868]; struct ATL::CRegKey *
0x18001318e  mov     [rsp+8C0h+var_868], rsi
0x180013193  lea     rcx, [rbp+7C0h+SubKey]; lpSubKey
0x18001319a  mov     [rsp+8C0h+var_860], rsi
0x18001319f  mov     [rsp+8C0h+var_858], rsi
0x1800131a4  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x1800131a9  test    eax, eax
0x1800131ab  jz      short loc_1800131ED
0x1800131ad  mov     [rsp+8C0h+lpdwDisposition], rsi; lpdwDisposition
0x1800131b2  lea     rax, [rsp+8C0h+var_868]
0x1800131b7  mov     [rsp+8C0h+phkResult], rax; phkResult
0x1800131bc  lea     rdx, [rbp+7C0h+SubKey]; lpSubKey
0x1800131c3  mov     [rsp+8C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800131c8  xor     r9d, r9d; lpClass
0x1800131cb  mov     [rsp+8C0h+samDesired], 20006h; samDesired
0x1800131d3  xor     r8d, r8d; Reserved
0x1800131d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800131dd  mov     [rsp+8C0h+dwOptions], esi; dwOptions
0x1800131e1  call    cs:__imp_RegCreateKeyExW
0x1800131e7  mov     ebx, eax
0x1800131e9  test    eax, eax
0x1800131eb  js      short loc_18001321E
0x1800131ed  mov     r8, rdi; unsigned __int16 *
0x1800131f0  mov     [rsp+8C0h+hKey], rsi
0x1800131f5  lea     rdx, [rsp+8C0h+hKey]; struct ATL::CRegKey *
0x1800131fa  mov     [rbp+7C0h+var_840], rsi
0x1800131fe  lea     rcx, [rsp+8C0h+var_868]; struct ATL::CRegKey *
0x180013203  mov     [rbp+7C0h+var_838], rsi
0x180013207  call    ?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z; CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)
0x18001320c  mov     rcx, [rsp+8C0h+hKey]; hKey
0x180013211  mov     ebx, eax
0x180013213  test    rcx, rcx
0x180013216  jz      short loc_18001321E
0x180013218  call    cs:__imp_RegCloseKey
0x18001321e  mov     rcx, [rsp+8C0h+var_868]; hKey
0x180013223  test    rcx, rcx
0x180013226  jz      short loc_18001322E
0x180013228  call    cs:__imp_RegCloseKey
0x18001322e  mov     eax, cs:dword_180048E90
0x180013234  cmp     eax, 5
0x180013237  jbe     short loc_180013270
0x180013239  test    rdi, rdi
0x18001323c  mov     [rsp+8C0h+var_870], ebx
0x180013240  lea     rax, String2
0x180013247  cmovz   rdi, rax
0x18001324b  lea     rdx, byte_18003FF8F
0x180013252  lea     rax, [rsp+8C0h+var_870]
0x180013257  mov     [rsp+8C0h+var_850], rdi
0x18001325c  mov     qword ptr [rsp+8C0h+samDesired], rax
0x180013261  lea     rax, [rsp+8C0h+var_850]
0x180013266  mov     qword ptr [rsp+8C0h+dwOptions], rax
0x18001326b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013270  mov     eax, ebx
0x180013272  mov     rcx, [rbp+7C0h+var_30]
0x180013279  xor     rcx, rsp; StackCookie
0x18001327c  call    __security_check_cookie
0x180013281  add     rsp, 8A8h
0x180013288  pop     rdi
0x180013289  pop     rsi
0x18001328a  pop     rbx
0x18001328b  pop     rbp
0x18001328c  retn
```
