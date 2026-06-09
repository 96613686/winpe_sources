# RemoveUserAccessACLs(void)

- ea: `0x18007b0d0`
- end: `0x18007b1f5`
- name: `?RemoveUserAccessACLs@@YAJXZ`
- size: `293`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007aa90`

## callees

- `0x180014a60`
- `0x1800157c0`
- `0x180061bac`
- `0x180068a8c`
- `0x1800764d0`
- `0x18007704c`
- `0x18007b0d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007b19d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007b19d`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b142`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b142`

## string_xrefs

- `0x18007b13b`: `PCPKSPTbsAccess`
- `0x18007b0ee`: `RemoveUserAccessACLs`
- `0x18007b18a`: `SecurityDescriptor`
- `0x18007b121`: `Software\Microsoft\Tpm\Access`

## pseudocode

```c
__int64 RemoveUserAccessACLs(void)
{
  int PersistedStateLocation; // eax
  int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-268h]
  _BYTE v6[24]; // [rsp+48h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v6, L"RemoveUserAccessACLs", 1);
  memset_0(SubKey, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(L"PCPKSPTbsAccess", 0, L"Software\\Microsoft\\Tpm\\Access", 0);
  if ( PersistedStateLocation >= 0 )
  {
    v2 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           SubKey,
           L"SecurityDescriptor",
           1u,
           L"D:(A;;0x00000001;;;BA)(A;;0x00000001;;;NS)(A;;0x00000001;;;LS)",
           0x7Eu);
    if ( !v2 )
    {
      v3 = 0;
      goto LABEL_7;
    }
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8C,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
           (const char *)v2,
           lpData);
  }
  else
  {
    v1 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x85,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
           (const char *)(unsigned int)PersistedStateLocation,
           (int)SubKey);
  }
  v3 = v1;
LABEL_7:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v6);
  return v3;
}

```

## disassembly

```asm
0x18007b0d0  push    rbx
0x18007b0d2  sub     rsp, 280h
0x18007b0d9  mov     rax, cs:__security_cookie
0x18007b0e0  xor     rax, rsp
0x18007b0e3  mov     [rsp+288h+var_18], rax
0x18007b0eb  mov     r8b, 1; bool
0x18007b0ee  lea     rdx, aRemoveuseracce; "RemoveUserAccessACLs"
0x18007b0f5  lea     rcx, [rsp+288h+var_240]; this
0x18007b0fa  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18007b0ff  mov     ebx, 208h
0x18007b104  lea     rcx, [rsp+288h+SubKey]; void *
0x18007b109  mov     r8d, ebx; Size
0x18007b10c  xor     edx, edx; Val
0x18007b10e  call    memset_0
0x18007b113  lea     rax, [rsp+288h+var_248]
0x18007b118  mov     [rsp+288h+var_248], ebx
0x18007b11c  mov     [rsp+288h+var_258], rax
0x18007b121  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Tpm\\Access"
0x18007b128  lea     rax, [rsp+288h+SubKey]
0x18007b12d  mov     [rsp+288h+cbData], ebx
0x18007b131  xor     r9d, r9d
0x18007b134  mov     [rsp+288h+lpData], rax; int
0x18007b139  xor     edx, edx
0x18007b13b  lea     rcx, aPcpksptbsacces; "PCPKSPTbsAccess"
0x18007b142  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b149  nop     dword ptr [rax+rax+00h]
0x18007b14e  test    eax, eax
0x18007b150  jns     short loc_18007B170
0x18007b152  mov     rcx, [rsp+288h]; this
0x18007b15a  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b161  mov     r9d, eax; char *
0x18007b164  mov     edx, 85h; void *
0x18007b169  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007b16e  jmp     short loc_18007B1C9
0x18007b170  lea     rax, aDA0x00000001Ba; "D:(A;;0x00000001;;;BA)(A;;0x00000001;;;"...
0x18007b177  mov     [rsp+288h+cbData], 7Eh ; '~'; cbData
0x18007b17f  mov     r9d, 1; dwType
0x18007b185  mov     [rsp+288h+lpData], rax; unsigned int
0x18007b18a  lea     r8, aSecuritydescri; "SecurityDescriptor"
0x18007b191  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007b198  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18007b19d  call    cs:__imp_RegSetKeyValueW
0x18007b1a4  nop     dword ptr [rax+rax+00h]
0x18007b1a9  test    eax, eax
0x18007b1ab  jz      short loc_18007B1CD
0x18007b1ad  mov     rcx, [rsp+288h]; this
0x18007b1b5  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b1bc  mov     r9d, eax; char *
0x18007b1bf  mov     edx, 8Ch; void *
0x18007b1c4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007b1c9  mov     ebx, eax
0x18007b1cb  jmp     short loc_18007B1CF
0x18007b1cd  xor     ebx, ebx
0x18007b1cf  lea     rcx, [rsp+288h+var_240]; this
0x18007b1d4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007b1d9  mov     eax, ebx
0x18007b1db  mov     rcx, [rsp+288h+var_18]
0x18007b1e3  xor     rcx, rsp; StackCookie
0x18007b1e6  call    __security_check_cookie
0x18007b1eb  add     rsp, 280h
0x18007b1f2  pop     rbx
0x18007b1f3  retn
```
