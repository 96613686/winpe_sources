# Windows::Networking::UX::Internal::CWiFiProfile::GetSsid(HSTRING__ * *)

- ea: `0x18005c820`
- end: `0x18005c909`
- name: `?GetSsid@CWiFiProfile@Internal@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `233`
- prototype: `int(Windows::Networking::UX::Internal::CWiFiProfile *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800097b4`
- `0x18001668c`
- `0x18005c820`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c8d0`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18005c89c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x18005c89c`

## pseudocode

```c
HRESULT __fastcall Windows::Networking::UX::Internal::CWiFiProfile::GetSsid(
        Windows::Networking::UX::Internal::CWiFiProfile *this,
        HSTRING *a2)
{
  HRESULT String; // ebx
  __int64 v5; // rdx
  unsigned int v7; // eax
  UINT32 length[4]; // [rsp+20h] [rbp-228h] BYREF
  WCHAR sourceString[256]; // [rsp+30h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( !a2 )
  {
    String = -2147024809;
    v5 = 691;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
      (const char *)(unsigned int)String,
      length[0]);
    return String;
  }
  length[0] = 256;
  memset_0(sourceString, 0, sizeof(sourceString));
  v7 = WlanUtf8SsidToDisplayName((char *)this + 80, 1, sourceString, length);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2B8,
             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
             (const char *)v7,
             length[0]);
  String = WindowsCreateString(sourceString, length[0], a2);
  if ( String < 0 )
  {
    v5 = 698;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18005c820  mov     [rsp+arg_10], rbx
0x18005c825  push    rdi
0x18005c826  sub     rsp, 240h
0x18005c82d  mov     rax, cs:__security_cookie
0x18005c834  xor     rax, rsp
0x18005c837  mov     [rsp+248h+var_18], rax
0x18005c83f  mov     rbx, rdx
0x18005c842  mov     rdi, rcx
0x18005c845  test    rdx, rdx
0x18005c848  jnz     short loc_18005C86F
0x18005c84a  mov     ebx, 80070057h
0x18005c84f  mov     edx, 2B3h; void *
0x18005c854  mov     rcx, [rsp+248h]; this
0x18005c85c  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005c863  mov     r9d, ebx; char *
0x18005c866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c86b  mov     eax, ebx
0x18005c86d  jmp     short loc_18005C8E8
0x18005c86f  xor     edx, edx; Val
0x18005c871  mov     [rsp+248h+length], 100h; unsigned int
0x18005c879  mov     r8d, 200h; Size
0x18005c87f  lea     rcx, [rsp+248h+sourceString]; void *
0x18005c884  call    memset_0
0x18005c889  lea     rcx, [rdi+50h]
0x18005c88d  mov     edx, 1
0x18005c892  lea     r9, [rsp+248h+length]
0x18005c897  lea     r8, [rsp+248h+sourceString]
0x18005c89c  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18005c8a2  test    eax, eax
0x18005c8a4  jz      short loc_18005C8C4
0x18005c8a6  mov     rcx, [rsp+248h]; this
0x18005c8ae  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005c8b5  mov     r9d, eax; char *
0x18005c8b8  mov     edx, 2B8h; void *
0x18005c8bd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005c8c2  jmp     short loc_18005C8E8
0x18005c8c4  mov     edx, [rsp+248h+length]; length
0x18005c8c8  lea     rcx, [rsp+248h+sourceString]; sourceString
0x18005c8cd  mov     r8, rbx; string
0x18005c8d0  call    cs:__imp_WindowsCreateString
0x18005c8d6  mov     ebx, eax
0x18005c8d8  test    eax, eax
0x18005c8da  jns     short loc_18005C8E6
0x18005c8dc  mov     edx, 2BAh
0x18005c8e1  jmp     loc_18005C854
0x18005c8e6  xor     eax, eax
0x18005c8e8  mov     rcx, [rsp+248h+var_18]
0x18005c8f0  xor     rcx, rsp; StackCookie
0x18005c8f3  call    __security_check_cookie
0x18005c8f8  mov     rbx, [rsp+248h+arg_10]
0x18005c900  add     rsp, 240h
0x18005c907  pop     rdi
0x18005c908  retn
```
