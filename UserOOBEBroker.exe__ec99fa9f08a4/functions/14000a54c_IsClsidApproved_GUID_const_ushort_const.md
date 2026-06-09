# IsClsidApproved(_GUID const &,ushort const *)

- ea: `0x14000a54c`
- end: `0x14000a65a`
- name: `?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z`
- size: `270`
- prototype: `bool __fastcall(const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000d4a0`

## callees

- `0x14000295f`
- `0x140005ca4`
- `0x14000a54c`
- `0x14000d78c`
- `0x14000e1c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000a5f7`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a5f7`
- `ADVAPI32!RegCloseKey` at `0x14000a60c`
- `ADVAPI32!RegCloseKey` at `0x14000a60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a61d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a61d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000a578`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x14000a578`

## pseudocode

```c
bool __fastcall IsClsidApproved(const struct _GUID *a1, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // r8d
  int v5; // eax
  unsigned int v6; // r8d
  bool v7; // bl
  int phkResult; // [rsp+20h] [rbp-248h]
  int phkResulta; // [rsp+20h] [rbp-248h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  lpsz = 0;
  v3 = StringFromCLSID(a1, &lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0xE, v4, (const char *)(unsigned int)v3, phkResult);
  memset_0(SubKey, 0, 0x208u);
  phkResulta = (int)lpsz;
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a2);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x10, v6, (const char *)(unsigned int)v5, phkResulta);
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) == 0;
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v7;
}

```

## disassembly

```asm
0x14000a54c  push    rbx
0x14000a54e  sub     rsp, 260h
0x14000a555  mov     rax, cs:__security_cookie
0x14000a55c  xor     rax, rsp
0x14000a55f  mov     [rsp+268h+var_18], rax
0x14000a567  mov     rbx, rdx
0x14000a56a  mov     [rsp+268h+lpsz], 0
0x14000a573  lea     rdx, [rsp+268h+lpsz]; lplpsz
0x14000a578  call    cs:__imp_StringFromCLSID
0x14000a57e  mov     rcx, [rsp+268h]; this
0x14000a586  test    eax, eax
0x14000a588  js      loc_14000A64C
0x14000a58e  xor     edx, edx; Val
0x14000a590  mov     r8d, 208h; Size
0x14000a596  lea     rcx, [rsp+268h+SubKey]; void *
0x14000a59b  call    memset_0
0x14000a5a0  mov     rax, [rsp+268h+lpsz]
0x14000a5a5  mov     qword ptr [rsp+268h+phkResult], rax; int
0x14000a5aa  mov     r9, rbx
0x14000a5ad  lea     r8, aSS; "%s\\%s"
0x14000a5b4  mov     edx, 104h; unsigned __int64
0x14000a5b9  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x14000a5be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a5c3  mov     rcx, [rsp+268h]; this
0x14000a5cb  test    eax, eax
0x14000a5cd  js      short loc_14000A63E
0x14000a5cf  mov     [rsp+268h+hKey], 0
0x14000a5d8  lea     rax, [rsp+268h+hKey]
0x14000a5dd  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x14000a5e2  mov     r9d, 20019h; samDesired
0x14000a5e8  xor     r8d, r8d; ulOptions
0x14000a5eb  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x14000a5f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a5f7  call    cs:__imp_RegOpenKeyExW
0x14000a5fd  test    eax, eax
0x14000a5ff  setz    bl
0x14000a602  mov     rcx, [rsp+268h+hKey]; hKey
0x14000a607  test    rcx, rcx
0x14000a60a  jz      short loc_14000A613
0x14000a60c  call    cs:__imp_RegCloseKey
0x14000a612  nop
0x14000a613  mov     rcx, [rsp+268h+lpsz]; pv
0x14000a618  test    rcx, rcx
0x14000a61b  jz      short loc_14000A623
0x14000a61d  call    cs:__imp_CoTaskMemFree
0x14000a623  mov     al, bl
0x14000a625  mov     rcx, [rsp+268h+var_18]
0x14000a62d  xor     rcx, rsp; StackCookie
0x14000a630  call    __security_check_cookie
0x14000a635  add     rsp, 260h
0x14000a63c  pop     rbx
0x14000a63d  retn
0x14000a63e  mov     r9d, eax; char *
0x14000a641  mov     edx, 10h; void *
0x14000a646  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a64c  mov     r9d, eax; char *
0x14000a64f  mov     edx, 0Eh; void *
0x14000a654  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
