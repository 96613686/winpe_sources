# CPolicyCheck::UpdateLocalRegPolicyEntry(HKEY__ *,ushort const *,ushort const *,int)

- ea: `0x18000401c`
- end: `0x180004311`
- name: `?UpdateLocalRegPolicyEntry@CPolicyCheck@@QEAAJPEAUHKEY__@@PEBG1H@Z`
- size: `757`
- prototype: `__int64 __fastcall(CPolicyCheck *this, HKEY hKey, const unsigned __int16 *, wchar_t *Buffer, unsigned int Data)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004364`

## callees

- `0x180002224`
- `0x180002e78`
- `0x1800038dc`
- `0x18000401c`
- `0x18000725c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000428c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000428c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000421c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000421c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004226`

## string_xrefs

- `0x1800040c3`: `Policy for url %s is %s. Prompt install for TPS Control is not allowed, will silently install`
- `0x180004251`: `InstallTrustedOCX`
- `0x18000427a`: `InstallSignedOCX`
- `0x1800042a3`: `InstallUnSignedOCX`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::UpdateLocalRegPolicyEntry(
        CPolicyCheck *this,
        HKEY hKey,
        const unsigned __int16 *a3,
        wchar_t *Buffer,
        unsigned int Data)
{
  unsigned int PolicyEntry; // ebx
  unsigned __int16 *v10; // r9
  struct CPolicyEntry *v11; // r9
  int v12; // r8d
  int v13; // edx
  unsigned int v14; // ecx
  signed int LastError; // eax
  REGSAM samDesired[2]; // [rsp+28h] [rbp-50h]
  BYTE v18[4]; // [rsp+50h] [rbp-28h] BYREF
  BYTE v19[4]; // [rsp+54h] [rbp-24h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-20h] BYREF
  struct CPolicyEntry *v21; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+C8h] [rbp+50h] BYREF

  v22 = 0;
  *(_DWORD *)v18 = 0;
  Data = 0;
  *(_DWORD *)v19 = 0;
  hKeya = 0;
  if ( !Buffer || !*Buffer )
  {
    v22 = 1;
    goto LABEL_11;
  }
  if ( swscanf_s(Buffer, L"%u,%u,%u,%i", &Data, &v22, v18, v19) != 4 || Data > 2 || v22 > 2 || *(_DWORD *)v18 > 1u )
  {
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 3u, L"Invalid policy for url %s Value %s", a3, Buffer);
    PolicyEntry = -2147024809;
    goto LABEL_29;
  }
  if ( Data == 1 )
  {
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      8u,
      3u,
      L"Policy for url %s is %s. Prompt install for TPS Control is not allowed, will silently install",
      a3,
      Buffer);
LABEL_11:
    Data = 2;
  }
  v21 = 0;
  PolicyEntry = CPolicyCheck::FindPolicyEntry(this, a3, &v21);
  if ( (int)(PolicyEntry + 0x80000000) >= 0 && PolicyEntry != -2147023728 )
  {
    v10 = L"Invalid url %s. Error 0x%x";
LABEL_15:
    samDesired[0] = PolicyEntry;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v10, a3, *(_QWORD *)samDesired);
    goto LABEL_29;
  }
  v11 = v21;
  if ( v21 )
  {
    if ( !*((_DWORD *)v21 + 11) )
    {
      PolicyEntry = -2147024713;
      v10 = L"Duplicate url %s ignored.Error 0x%x";
      goto LABEL_15;
    }
    *((_DWORD *)v21 + 11) = 0;
    v12 = *(_DWORD *)v19;
    v13 = *(_DWORD *)v18;
    v14 = v22;
    *((_DWORD *)v11 + 8) = Data;
    *((_DWORD *)v11 + 7) = v14;
    *((_DWORD *)v11 + 10) = v13;
    *((_DWORD *)v11 + 9) = v12;
  }
  else
  {
    CPolicyCheck::AddPolicyEntry(this, a3, Data, v22, *(unsigned int *)v18, *(unsigned int *)v19);
  }
  if ( RegCreateKeyExW(hKey, a3, 0, 0, 0, 0x20006u, 0, &hKeya, 0)
    || RegSetValueExW(hKeya, L"InstallTrustedOCX", 0, 4u, (const BYTE *)&Data, 4u)
    || RegSetValueExW(hKeya, L"InstallSignedOCX", 0, 4u, (const BYTE *)&v22, 4u)
    || RegSetValueExW(hKeya, L"InstallUnSignedOCX", 0, 4u, v18, 4u)
    || RegSetValueExW(hKeya, L"VerifyServerCert", 0, 4u, v19, 4u) )
  {
    LastError = GetLastError();
    PolicyEntry = LastError;
    if ( LastError > 0 )
      PolicyEntry = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    PolicyEntry = 0;
  }
LABEL_29:
  if ( hKeya )
    RegCloseKey(hKeya);
  return PolicyEntry;
}

```

## disassembly

```asm
0x18000401c  push    rbp
0x18000401e  push    rbx
0x18000401f  push    rsi
0x180004020  push    r13
0x180004022  push    r14
0x180004024  push    r15
0x180004026  mov     rbp, rsp
0x180004029  sub     rsp, 78h
0x18000402d  mov     [rbp+arg_18], 0
0x180004034  mov     rbx, r9
0x180004037  mov     dword ptr [rbp+var_28], 0
0x18000403e  mov     rsi, r8
0x180004041  mov     [rbp+Data], 0
0x180004048  mov     r15, rdx
0x18000404b  mov     dword ptr [rbp+var_24], 0
0x180004052  mov     r14, rcx
0x180004055  mov     [rbp+hKey], 0
0x18000405d  mov     r13d, 4
0x180004063  test    r9, r9
0x180004066  jz      loc_180004115
0x18000406c  xor     eax, eax
0x18000406e  cmp     ax, [r9]
0x180004072  jz      loc_180004115
0x180004078  lea     rax, [rbp+var_24]
0x18000407c  mov     rcx, rbx; Buffer
0x18000407f  mov     qword ptr [rsp+78h+samDesired], rax
0x180004084  lea     r9, [rbp+arg_18]
0x180004088  lea     rax, [rbp+var_28]
0x18000408c  lea     r8, [rbp+Data]
0x180004090  mov     qword ptr [rsp+78h+dwOptions], rax
0x180004095  lea     rdx, aUUUI; "%u,%u,%u,%i"
0x18000409c  call    swscanf_s
0x1800040a1  cmp     eax, r13d
0x1800040a4  jnz     short loc_1800040E5
0x1800040a6  cmp     [rbp+Data], 2
0x1800040aa  ja      short loc_1800040E5
0x1800040ac  cmp     [rbp+arg_18], 2
0x1800040b0  ja      short loc_1800040E5
0x1800040b2  cmp     dword ptr [rbp+var_28], 1
0x1800040b6  ja      short loc_1800040E5
0x1800040b8  cmp     [rbp+Data], 1
0x1800040bc  jnz     short loc_180004123
0x1800040be  mov     qword ptr [rsp+78h+samDesired], rbx
0x1800040c3  lea     r9, aPolicyForUrlSI; "Policy for url %s is %s. Prompt install"...
0x1800040ca  lea     edx, [r13+4]; unsigned int
0x1800040ce  mov     qword ptr [rsp+78h+dwOptions], rsi
0x1800040d3  lea     r8d, [r13-1]; unsigned __int8
0x1800040d7  lea     rcx, qword_180021AD8; this
0x1800040de  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800040e3  jmp     short loc_18000411C
0x1800040e5  mov     edx, 8; unsigned int
0x1800040ea  mov     qword ptr [rsp+78h+samDesired], rbx
0x1800040ef  lea     r9, aInvalidPolicyF; "Invalid policy for url %s Value %s"
0x1800040f6  mov     qword ptr [rsp+78h+dwOptions], rsi
0x1800040fb  lea     rcx, qword_180021AD8; this
0x180004102  lea     r8d, [rdx-5]; unsigned __int8
0x180004106  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000410b  mov     ebx, 80070057h
0x180004110  jmp     loc_1800042F2
0x180004115  mov     [rbp+arg_18], 1
0x18000411c  mov     [rbp+Data], 2
0x180004123  lea     r8, [rbp+var_18]; struct CPolicyEntry **
0x180004127  mov     [rbp+var_18], 0
0x18000412f  mov     rdx, rsi; unsigned __int16 *
0x180004132  mov     rcx, r14; this
0x180004135  call    ?FindPolicyEntry@CPolicyCheck@@QEAAJPEBGPEAPEAVCPolicyEntry@@@Z; CPolicyCheck::FindPolicyEntry(ushort const *,CPolicyEntry * *)
0x18000413a  mov     ebx, eax
0x18000413c  mov     eax, 80000000h
0x180004141  lea     ecx, [rbx+rax]
0x180004144  test    eax, ecx
0x180004146  jnz     short loc_18000417A
0x180004148  cmp     ebx, 80070490h
0x18000414e  jz      short loc_18000417A
0x180004150  lea     r9, aInvalidUrlSErr_0; "Invalid url %s. Error 0x%x"
0x180004157  mov     edx, 8; unsigned int
0x18000415c  mov     [rsp+78h+samDesired], ebx
0x180004160  lea     rcx, qword_180021AD8; this
0x180004167  mov     qword ptr [rsp+78h+dwOptions], rsi
0x18000416c  lea     r8d, [rdx-6]; unsigned __int8
0x180004170  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180004175  jmp     loc_1800042F2
0x18000417a  mov     r9, [rbp+var_18]
0x18000417e  test    r9, r9
0x180004181  jz      short loc_1800041C4
0x180004183  cmp     dword ptr [r9+2Ch], 0
0x180004188  jnz     short loc_180004198
0x18000418a  mov     ebx, 800700B7h
0x18000418f  lea     r9, aDuplicateUrlSI; "Duplicate url %s ignored.Error 0x%x"
0x180004196  jmp     short loc_180004157
0x180004198  test    r9, r9
0x18000419b  jz      short loc_1800041C4
0x18000419d  mov     dword ptr [r9+2Ch], 0
0x1800041a5  mov     r8d, dword ptr [rbp+var_24]
0x1800041a9  mov     edx, dword ptr [rbp+var_28]
0x1800041ac  mov     ecx, [rbp+arg_18]
0x1800041af  mov     eax, [rbp+Data]
0x1800041b2  mov     [r9+20h], eax
0x1800041b6  mov     [r9+1Ch], ecx
0x1800041ba  mov     [r9+28h], edx
0x1800041be  mov     [r9+24h], r8d
0x1800041c2  jmp     short loc_1800041E5
0x1800041c4  mov     eax, dword ptr [rbp+var_24]
0x1800041c7  mov     rdx, rsi; unsigned __int16 *
0x1800041ca  mov     r9d, [rbp+arg_18]; unsigned int
0x1800041ce  mov     rcx, r14; this
0x1800041d1  mov     r8d, [rbp+Data]; unsigned int
0x1800041d5  mov     [rsp+78h+samDesired], eax; unsigned int
0x1800041d9  mov     eax, dword ptr [rbp+var_28]
0x1800041dc  mov     [rsp+78h+dwOptions], eax; unsigned int
0x1800041e0  call    ?AddPolicyEntry@CPolicyCheck@@QEAAJPEBGKKKK@Z; CPolicyCheck::AddPolicyEntry(ushort const *,ulong,ulong,ulong,ulong)
0x1800041e5  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800041ee  lea     rax, [rbp+hKey]
0x1800041f2  mov     [rsp+78h+phkResult], rax; phkResult
0x1800041f7  xor     r9d, r9d; lpClass
0x1800041fa  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004203  xor     r8d, r8d; Reserved
0x180004206  mov     [rsp+78h+samDesired], 20006h; samDesired
0x18000420e  mov     rdx, rsi; lpSubKey
0x180004211  mov     rcx, r15; hKey
0x180004214  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000421c  call    cs:__imp_RegCreateKeyExW
0x180004222  test    eax, eax
0x180004224  jz      short loc_180004244
0x180004226  call    cs:__imp_GetLastError
0x18000422c  mov     ebx, eax
0x18000422e  test    eax, eax
0x180004230  jle     loc_1800042F2
0x180004236  movzx   ebx, ax
0x180004239  or      ebx, 80070000h
0x18000423f  jmp     loc_1800042F2
0x180004244  mov     rcx, [rbp+hKey]; hKey
0x180004248  lea     rax, [rbp+Data]
0x18000424c  mov     [rsp+78h+samDesired], r13d; cbData
0x180004251  lea     rdx, ValueName; "InstallTrustedOCX"
0x180004258  mov     r9d, r13d; dwType
0x18000425b  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180004260  xor     r8d, r8d; Reserved
0x180004263  call    cs:__imp_RegSetValueExW
0x180004269  test    eax, eax
0x18000426b  jnz     short loc_180004226
0x18000426d  mov     rcx, [rbp+hKey]; hKey
0x180004271  lea     rax, [rbp+arg_18]
0x180004275  mov     [rsp+78h+samDesired], r13d; cbData
0x18000427a  lea     rdx, aInstallsignedo; "InstallSignedOCX"
0x180004281  mov     r9d, r13d; dwType
0x180004284  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180004289  xor     r8d, r8d; Reserved
0x18000428c  call    cs:__imp_RegSetValueExW
0x180004292  test    eax, eax
0x180004294  jnz     short loc_180004226
0x180004296  mov     rcx, [rbp+hKey]; hKey
0x18000429a  lea     rax, [rbp+var_28]
0x18000429e  mov     [rsp+78h+samDesired], r13d; cbData
0x1800042a3  lea     rdx, aInstallunsigne; "InstallUnSignedOCX"
0x1800042aa  mov     r9d, r13d; dwType
0x1800042ad  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800042b2  xor     r8d, r8d; Reserved
0x1800042b5  call    cs:__imp_RegSetValueExW
0x1800042bb  test    eax, eax
0x1800042bd  jnz     loc_180004226
0x1800042c3  mov     rcx, [rbp+hKey]; hKey
0x1800042c7  lea     rax, [rbp+var_24]
0x1800042cb  mov     [rsp+78h+samDesired], r13d; cbData
0x1800042d0  lea     rdx, aVerifyserverce; "VerifyServerCert"
0x1800042d7  mov     r9d, r13d; dwType
0x1800042da  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800042df  xor     r8d, r8d; Reserved
0x1800042e2  call    cs:__imp_RegSetValueExW
0x1800042e8  test    eax, eax
0x1800042ea  jnz     loc_180004226
0x1800042f0  xor     ebx, ebx
0x1800042f2  mov     rcx, [rbp+hKey]; hKey
0x1800042f6  test    rcx, rcx
0x1800042f9  jz      short loc_180004301
0x1800042fb  call    cs:__imp_RegCloseKey
0x180004301  mov     eax, ebx
0x180004303  add     rsp, 78h
0x180004307  pop     r15
0x180004309  pop     r14
0x18000430b  pop     r13
0x18000430d  pop     rsi
0x18000430e  pop     rbx
0x18000430f  pop     rbp
0x180004310  retn
```
