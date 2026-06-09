# AddDomainMapping(ulong *)

- ea: `0x1800076e0`
- end: `0x1800077e2`
- name: `?AddDomainMapping@@YAJPEAK@Z`
- size: `258`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005c3c`

## callees

- `0x1800076e0`
- `0x180008c50`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x18000779b`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x18000779b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007733`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007733`
- `ntdll!RtlInitializeSid` at `0x180007754`
- `ntdll!RtlInitializeSid` at `0x180007754`
- `ntdll!RtlSubAuthoritySid` at `0x18000775f`
- `ntdll!RtlSubAuthoritySid` at `0x18000775f`
- `ntdll!RtlInitUnicodeString` at `0x180007776`
- `ntdll!RtlInitUnicodeString` at `0x180007787`
- `ntdll!RtlInitUnicodeString` at `0x180007776`
- `ntdll!RtlInitUnicodeString` at `0x180007787`
- `ntdll!RtlLengthRequiredSid` at `0x180007729`
- `ntdll!RtlLengthRequiredSid` at `0x180007729`

## pseudocode

```c
__int64 __fastcall AddDomainMapping(unsigned int *a1)
{
  ULONG v1; // eax
  HLOCAL v2; // rax
  void *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  _DWORD *v7; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString[3]; // [rsp+28h] [rbp-48h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+58h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(DestinationString, 0, sizeof(DestinationString));
  v7 = 0;
  v1 = RtlLengthRequiredSid(6u);
  v2 = LocalAlloc(0, v1);
  v3 = v2;
  if ( v2 )
  {
    v4 = 0;
    RtlInitializeSid(v2, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(v3, 0) = 82;
    RtlInitUnicodeString(&DestinationString[1], &word_18000C2BC);
    RtlInitUnicodeString(DestinationString, L"IIS APPPOOL");
    *(_QWORD *)&DestinationString[2].Length = v3;
    v5 = LsaManageSidNameMapping(0, DestinationString, &v7);
    if ( v5 < 0 && (!v7 || *v7 != 2) )
      v4 = v5 | 0x10000000;
    LocalFree(v3);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x1800076e0  mov     [rsp-8+arg_0], rbx
0x1800076e5  mov     [rsp-8+arg_8], rdi
0x1800076ea  push    rbp
0x1800076eb  mov     rbp, rsp
0x1800076ee  sub     rsp, 70h
0x1800076f2  mov     rax, cs:__security_cookie
0x1800076f9  xor     rax, rsp
0x1800076fc  mov     [rbp+var_10], rax
0x180007700  xor     eax, eax
0x180007702  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180007709  xorps   xmm0, xmm0
0x18000770c  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180007712  movups  xmmword ptr [rbp+var_36], xmm0
0x180007716  mov     word ptr [rbp+DestinationString], ax
0x18000771a  lea     ecx, [rax+6]; SubAuthorityCount
0x18000771d  mov     [rbp+var_50], rax
0x180007721  movups  xmmword ptr [rbp+DestinationString+2], xmm0
0x180007725  movups  xmmword ptr [rbp+var_36+0Eh], xmm0
0x180007729  call    cs:__imp_RtlLengthRequiredSid
0x18000772f  mov     edx, eax; uBytes
0x180007731  xor     ecx, ecx; uFlags
0x180007733  call    cs:__imp_LocalAlloc
0x180007739  mov     rdi, rax
0x18000773c  test    rax, rax
0x18000773f  jnz     short loc_180007748
0x180007741  mov     ebx, 8007000Eh
0x180007746  jmp     short loc_1800077C2
0x180007748  mov     r8b, 1; SubAuthorityCount
0x18000774b  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18000774f  mov     rcx, rdi; Sid
0x180007752  xor     ebx, ebx
0x180007754  call    cs:__imp_RtlInitializeSid
0x18000775a  xor     edx, edx; SubAuthority
0x18000775c  mov     rcx, rdi; Sid
0x18000775f  call    cs:__imp_RtlSubAuthoritySid
0x180007765  lea     rdx, word_18000C2BC; SourceString
0x18000776c  lea     rcx, [rbp+DestinationString+10h]; DestinationString
0x180007770  mov     dword ptr [rax], 52h ; 'R'
0x180007776  call    cs:__imp_RtlInitUnicodeString
0x18000777c  lea     rdx, SourceString; "IIS APPPOOL"
0x180007783  lea     rcx, [rbp+DestinationString]; DestinationString
0x180007787  call    cs:__imp_RtlInitUnicodeString
0x18000778d  lea     r8, [rbp+var_50]
0x180007791  mov     qword ptr [rbp+var_36+0Eh], rdi
0x180007795  lea     rdx, [rbp+DestinationString]
0x180007799  xor     ecx, ecx
0x18000779b  call    cs:__imp_LsaManageSidNameMapping
0x1800077a1  test    eax, eax
0x1800077a3  jns     short loc_1800077B9
0x1800077a5  mov     rcx, [rbp+var_50]
0x1800077a9  test    rcx, rcx
0x1800077ac  jz      short loc_1800077B3
0x1800077ae  cmp     dword ptr [rcx], 2
0x1800077b1  jz      short loc_1800077B9
0x1800077b3  mov     ebx, eax
0x1800077b5  bts     ebx, 1Ch
0x1800077b9  mov     rcx, rdi; hMem
0x1800077bc  call    cs:__imp_LocalFree
0x1800077c2  mov     eax, ebx
0x1800077c4  mov     rcx, [rbp+var_10]
0x1800077c8  xor     rcx, rsp; StackCookie
0x1800077cb  call    __security_check_cookie
0x1800077d0  lea     r11, [rsp+70h+var_s0]
0x1800077d5  mov     rbx, [r11+10h]
0x1800077d9  mov     rdi, [r11+18h]
0x1800077dd  mov     rsp, r11
0x1800077e0  pop     rbp
0x1800077e1  retn
```
