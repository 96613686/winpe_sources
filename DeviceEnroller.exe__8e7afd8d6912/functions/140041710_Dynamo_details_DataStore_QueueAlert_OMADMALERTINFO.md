# Dynamo::details::DataStore::QueueAlert(OMADMALERTINFO *)

- ea: `0x140041710`
- end: `0x1400418d2`
- name: `?QueueAlert@DataStore@details@Dynamo@@UEAAXPEAUOMADMALERTINFO@@@Z`
- size: `450`
- prototype: `void __fastcall(Dynamo::details::DataStore *__hidden this, struct OMADMALERTINFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000a6e4`
- `0x14003e278`
- `0x140041710`
- `0x1400419a4`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetString` at `0x140041816`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x140041816`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14004183c`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14004183c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041863`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140041863`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004179e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004179e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Dynamo::details::DataStore::QueueAlert(
        Dynamo::details::DataStore *this,
        struct OMADMALERTINFO *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  int DynamicManagementRegistryKey; // eax
  unsigned int v6; // eax
  unsigned int i; // ebx
  const unsigned __int16 *v8; // r9
  int v9; // eax
  int v10; // eax
  DWORD dwOptions; // [rsp+28h] [rbp-19h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-19h]
  HKEY *samDesired; // [rsp+30h] [rbp-11h]
  _QWORD v14[4]; // [rsp+58h] [rbp+17h]
  _QWORD v15[4]; // [rsp+78h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]
  HKEY phkResult; // [rsp+A8h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+77h] BYREF

  hKey = 0;
  LOBYTE(a4) = 1;
  DynamicManagementRegistryKey = dmstd::GetDynamicManagementRegistryKey(
                                   *((dmstd **)this + 1),
                                   *((const unsigned __int16 **)this + 2),
                                   L"Alerts",
                                   a4,
                                   (bool)&hKey,
                                   samDesired);
  if ( DynamicManagementRegistryKey < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF1,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)(unsigned int)DynamicManagementRegistryKey,
      dwOptions);
  phkResult = 0;
  v6 = RegCreateKeyExW(hKey, *((LPCWSTR *)a2 + 3), 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xF6,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)v6,
      dwOptionsa);
  v15[0] = L"AlertData";
  v15[1] = L"Source";
  v15[2] = L"Target";
  v15[3] = L"AlertType";
  v14[0] = *((_QWORD *)a2 + 3);
  v14[1] = *((_QWORD *)a2 + 2);
  v14[2] = *((_QWORD *)a2 + 7);
  v14[3] = *((_QWORD *)a2 + 1);
  for ( i = 0; i < 4; ++i )
  {
    v8 = (const unsigned __int16 *)v14[i];
    if ( v8 )
    {
      v9 = OmaDmRegistrySetString(phkResult, 0, (const unsigned __int16 *)v15[i], v8);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x101,
          (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
          (const char *)(unsigned int)v9,
          dwOptionsa);
    }
  }
  v10 = OmaDmRegistrySetDWORD(phkResult, 0, L"EventType", *((_DWORD *)a2 + 1));
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x105,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsa);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x140041710  mov     r11, rsp
0x140041713  mov     [r11+10h], rbx
0x140041717  mov     [r11+20h], rdi
0x14004171b  push    rbp
0x14004171c  lea     rbp, [r11-5Fh]
0x140041720  sub     rsp, 90h
0x140041727  mov     rdi, rdx
0x14004172a  mov     [rbp+57h+hKey], 0
0x140041732  lea     rax, [rbp+57h+hKey]
0x140041736  mov     [r11-78h], rax
0x14004173a  mov     r9b, 1; unsigned __int16 *
0x14004173d  lea     r8, aAlerts; "Alerts"
0x140041744  mov     rdx, [rcx+10h]; unsigned __int16 *
0x140041748  mov     rcx, [rcx+8]; this
0x14004174c  call    ?GetDynamicManagementRegistryKey@dmstd@@YAJPEBG00_NPEAPEAUHKEY__@@@Z; dmstd::GetDynamicManagementRegistryKey(ushort const *,ushort const *,ushort const *,bool,HKEY__ * *)
0x140041751  mov     rcx, [rbp+5Fh]; this
0x140041755  test    eax, eax
0x140041757  js      loc_140041893
0x14004175d  mov     [rbp+57h+arg_0], 0
0x140041765  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x14004176e  lea     rax, [rbp+57h+arg_0]
0x140041772  mov     [rsp+90h+phkResult], rax; phkResult
0x140041777  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140041780  mov     [rsp+90h+samDesired], 2001Fh; samDesired
0x140041788  mov     [rsp+90h+dwOptions], 0; int
0x140041790  xor     r9d, r9d; lpClass
0x140041793  xor     r8d, r8d; Reserved
0x140041796  mov     rdx, [rdi+18h]; lpSubKey
0x14004179a  mov     rcx, [rbp+57h+hKey]; hKey
0x14004179e  call    cs:__imp_RegCreateKeyExW
0x1400417a4  mov     rcx, [rbp+5Fh]; this
0x1400417a8  test    eax, eax
0x1400417aa  jnz     loc_1400418A8
0x1400417b0  lea     rax, aAlertdata; "AlertData"
0x1400417b7  mov     [rbp+57h+var_20], rax
0x1400417bb  lea     rax, aSource; "Source"
0x1400417c2  mov     [rbp+57h+var_18], rax
0x1400417c6  lea     rax, aTarget; "Target"
0x1400417cd  mov     [rbp+57h+var_10], rax
0x1400417d1  lea     rax, aAlerttype; "AlertType"
0x1400417d8  mov     [rbp+57h+var_8], rax
0x1400417dc  mov     rax, [rdi+18h]
0x1400417e0  mov     [rbp+57h+var_40], rax
0x1400417e4  mov     rax, [rdi+10h]
0x1400417e8  mov     [rbp+57h+var_38], rax
0x1400417ec  mov     rax, [rdi+38h]
0x1400417f0  mov     [rbp+57h+var_30], rax
0x1400417f4  mov     rax, [rdi+8]
0x1400417f8  mov     [rbp+57h+var_28], rax
0x1400417fc  xor     ebx, ebx
0x1400417fe  movsxd  r8, ebx
0x140041801  mov     r9, [rbp+r8*8+57h+var_40]
0x140041806  test    r9, r9
0x140041809  jz      short loc_140041824
0x14004180b  mov     r8, [rbp+r8*8+57h+var_20]
0x140041810  xor     edx, edx
0x140041812  mov     rcx, [rbp+57h+arg_0]
0x140041816  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14004181c  mov     rcx, [rbp+5Fh]; this
0x140041820  test    eax, eax
0x140041822  js      short loc_14004187E
0x140041824  inc     ebx
0x140041826  cmp     ebx, 4
0x140041829  jb      short loc_1400417FE
0x14004182b  mov     r9d, [rdi+4]
0x14004182f  lea     r8, aEventtype; "EventType"
0x140041836  xor     edx, edx
0x140041838  mov     rcx, [rbp+57h+arg_0]
0x14004183c  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140041842  mov     rcx, [rbp+5Fh]; this
0x140041846  test    eax, eax
0x140041848  js      short loc_1400418BD
0x14004184a  mov     rcx, [rbp+57h+arg_0]; hKey
0x14004184e  test    rcx, rcx
0x140041851  jz      short loc_14004185A
0x140041853  call    cs:__imp_RegCloseKey
0x140041859  nop
0x14004185a  mov     rcx, [rbp+57h+hKey]; hKey
0x14004185e  test    rcx, rcx
0x140041861  jz      short loc_140041869
0x140041863  call    cs:__imp_RegCloseKey
0x140041869  lea     r11, [rsp+90h+var_s0]
0x140041871  mov     rbx, [r11+18h]
0x140041875  mov     rdi, [r11+28h]
0x140041879  mov     rsp, r11
0x14004187c  pop     rbp
0x14004187d  retn
0x14004187e  mov     r9d, eax; char *
0x140041881  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140041888  mov     edx, 101h; void *
0x14004188d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140041893  mov     r9d, eax; char *
0x140041896  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004189d  mov     edx, 0F1h; void *
0x1400418a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400418a8  mov     r9d, eax; char *
0x1400418ab  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400418b2  mov     edx, 0F6h; void *
0x1400418b7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1400418bd  mov     r9d, eax; char *
0x1400418c0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400418c7  mov     edx, 105h; void *
0x1400418cc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
