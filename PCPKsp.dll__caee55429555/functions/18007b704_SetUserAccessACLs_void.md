# SetUserAccessACLs(void)

- ea: `0x18007b704`
- end: `0x18007b829`
- name: `?SetUserAccessACLs@@YAJXZ`
- size: `293`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007aa10`

## callees

- `0x180014a60`
- `0x1800157c0`
- `0x180061bac`
- `0x180068a8c`
- `0x1800764d0`
- `0x18007704c`
- `0x18007b704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007b7d1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007b7d1`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b776`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b776`

## string_xrefs

- `0x18007b722`: `SetUserAccessACLs`
- `0x18007b76f`: `PCPKSPTbsAccess`
- `0x18007b7be`: `SecurityDescriptor`
- `0x18007b755`: `Software\Microsoft\Tpm\Access`

## pseudocode

```c
__int64 SetUserAccessACLs(void)
{
  int PersistedStateLocation; // eax
  int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-268h]
  _BYTE v6[24]; // [rsp+48h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v6, L"SetUserAccessACLs", 1);
  memset_0(SubKey, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(L"PCPKSPTbsAccess", 0, L"Software\\Microsoft\\Tpm\\Access", 0);
  if ( PersistedStateLocation >= 0 )
  {
    v2 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           SubKey,
           L"SecurityDescriptor",
           1u,
           L"D:(A;;0x00000001;;;BA)(A;;0x00000001;;;NS)(A;;0x00000001;;;LS)(A;;0x00000001;;;AU)(A;;0x00000001;;;IU)",
           0xCEu);
    if ( !v2 )
    {
      v3 = 0;
      goto LABEL_7;
    }
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x71,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
           (const char *)v2,
           lpData);
  }
  else
  {
    v1 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x6A,
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
0x18007b704  push    rbx
0x18007b706  sub     rsp, 280h
0x18007b70d  mov     rax, cs:__security_cookie
0x18007b714  xor     rax, rsp
0x18007b717  mov     [rsp+288h+var_18], rax
0x18007b71f  mov     r8b, 1; bool
0x18007b722  lea     rdx, aSetuseraccessa; "SetUserAccessACLs"
0x18007b729  lea     rcx, [rsp+288h+var_240]; this
0x18007b72e  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18007b733  mov     ebx, 208h
0x18007b738  lea     rcx, [rsp+288h+SubKey]; void *
0x18007b73d  mov     r8d, ebx; Size
0x18007b740  xor     edx, edx; Val
0x18007b742  call    memset_0
0x18007b747  lea     rax, [rsp+288h+var_248]
0x18007b74c  mov     [rsp+288h+var_248], ebx
0x18007b750  mov     [rsp+288h+var_258], rax
0x18007b755  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Tpm\\Access"
0x18007b75c  lea     rax, [rsp+288h+SubKey]
0x18007b761  mov     [rsp+288h+cbData], ebx
0x18007b765  xor     r9d, r9d
0x18007b768  mov     [rsp+288h+lpData], rax; int
0x18007b76d  xor     edx, edx
0x18007b76f  lea     rcx, aPcpksptbsacces; "PCPKSPTbsAccess"
0x18007b776  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b77d  nop     dword ptr [rax+rax+00h]
0x18007b782  test    eax, eax
0x18007b784  jns     short loc_18007B7A4
0x18007b786  mov     rcx, [rsp+288h]; this
0x18007b78e  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b795  mov     r9d, eax; char *
0x18007b798  mov     edx, 6Ah ; 'j'; void *
0x18007b79d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007b7a2  jmp     short loc_18007B7FD
0x18007b7a4  lea     rax, aDA0x00000001Ba_0; "D:(A;;0x00000001;;;BA)(A;;0x00000001;;;"...
0x18007b7ab  mov     [rsp+288h+cbData], 0CEh; cbData
0x18007b7b3  mov     r9d, 1; dwType
0x18007b7b9  mov     [rsp+288h+lpData], rax; unsigned int
0x18007b7be  lea     r8, aSecuritydescri; "SecurityDescriptor"
0x18007b7c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007b7cc  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18007b7d1  call    cs:__imp_RegSetKeyValueW
0x18007b7d8  nop     dword ptr [rax+rax+00h]
0x18007b7dd  test    eax, eax
0x18007b7df  jz      short loc_18007B801
0x18007b7e1  mov     rcx, [rsp+288h]; this
0x18007b7e9  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b7f0  mov     r9d, eax; char *
0x18007b7f3  mov     edx, 71h ; 'q'; void *
0x18007b7f8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007b7fd  mov     ebx, eax
0x18007b7ff  jmp     short loc_18007B803
0x18007b801  xor     ebx, ebx
0x18007b803  lea     rcx, [rsp+288h+var_240]; this
0x18007b808  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007b80d  mov     eax, ebx
0x18007b80f  mov     rcx, [rsp+288h+var_18]
0x18007b817  xor     rcx, rsp; StackCookie
0x18007b81a  call    __security_check_cookie
0x18007b81f  add     rsp, 280h
0x18007b826  pop     rbx
0x18007b827  retn
```
