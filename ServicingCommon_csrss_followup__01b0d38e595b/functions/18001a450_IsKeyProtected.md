# IsKeyProtected

- ea: `0x18001a450`
- end: `0x18001a5eb`
- name: `IsKeyProtected`
- size: `411`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001a450`
- `0x18001abd8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001a5ac`
- `KERNEL32!LocalFree` at `0x18001a5ac`
- `KERNEL32!LocalAlloc` at `0x18001a542`
- `KERNEL32!LocalAlloc` at `0x18001a542`
- `ntdll!RtlFreeUnicodeString` at `0x18001a5c3`
- `ntdll!RtlFreeUnicodeString` at `0x18001a5c3`
- `ntdll!RtlCreateUnicodeString` at `0x18001a496`
- `ntdll!RtlCreateUnicodeString` at `0x18001a496`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a4da`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a4da`
- `ADVAPI32!RegCloseKey` at `0x18001a598`
- `ADVAPI32!RegCloseKey` at `0x18001a598`
- `ADVAPI32!RegGetKeySecurity` at `0x18001a529`
- `ADVAPI32!RegGetKeySecurity` at `0x18001a571`
- `ADVAPI32!RegGetKeySecurity` at `0x18001a529`
- `ADVAPI32!RegGetKeySecurity` at `0x18001a571`

## pseudocode

```c
__int64 __fastcall IsKeyProtected(HKEY hKey, const WCHAR *a2, __int16 a3, _DWORD *a4)
{
  HLOCAL v4; // rsi
  unsigned int KeySecurity; // ebx
  __int64 v9; // rdi
  REGSAM v10; // r14d
  LSTATUS v11; // eax
  HKEY v12; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  hKeya = 0;
  cbSecurityDescriptor = 0;
  *a4 = 0;
  DestinationString = 0;
  if ( !a2 )
    goto LABEL_11;
  if ( !RtlCreateUnicodeString(&DestinationString, a2) )
  {
LABEL_3:
    KeySecurity = 8;
    goto LABEL_18;
  }
  LODWORD(v9) = DestinationString.Length >> 1;
  v10 = a3 & 0x300 | 0x20019;
LABEL_5:
  v11 = RegOpenKeyExW(hKey, DestinationString.Buffer, 0, v10, &hKeya);
  KeySecurity = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
      goto LABEL_18;
    while ( (_DWORD)v9 )
    {
      v9 = (unsigned int)(v9 - 1);
      if ( DestinationString.Buffer[v9] == 92 )
      {
        DestinationString.Buffer[v9] = 0;
        if ( (_DWORD)v9 )
          goto LABEL_5;
        break;
      }
    }
  }
  v12 = hKeya;
  if ( !hKeya )
LABEL_11:
    v12 = hKey;
  KeySecurity = RegGetKeySecurity(v12, 5u, 0, &cbSecurityDescriptor);
  if ( KeySecurity == 122 )
  {
    v4 = LocalAlloc(0x40u, cbSecurityDescriptor);
    if ( !v4 )
      goto LABEL_3;
    if ( hKeya )
      hKey = hKeya;
    KeySecurity = RegGetKeySecurity(hKey, 5u, v4, &cbSecurityDescriptor);
    if ( !KeySecurity )
      *a4 = IsWrpKeyDescriptor(v4);
  }
LABEL_18:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v4 )
    LocalFree(v4);
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return KeySecurity;
}

```

## disassembly

```asm
0x18001a450  mov     [rsp-28h+arg_0], rbx
0x18001a455  mov     [rsp-28h+arg_10], rsi
0x18001a45a  push    rbp
0x18001a45b  push    rdi
0x18001a45c  push    r12
0x18001a45e  push    r14
0x18001a460  push    r15
0x18001a462  mov     rbp, rsp
0x18001a465  sub     rsp, 40h
0x18001a469  xor     esi, esi
0x18001a46b  mov     [rbp+hKey], 0
0x18001a473  mov     [rbp+cbSecurityDescriptor], esi
0x18001a476  xorps   xmm0, xmm0
0x18001a479  mov     [r9], esi
0x18001a47c  mov     r12, r9
0x18001a47f  mov     r14d, r8d
0x18001a482  mov     r15, rcx
0x18001a485  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a489  test    rdx, rdx
0x18001a48c  jz      loc_18001A519
0x18001a492  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001a496  call    cs:__imp_RtlCreateUnicodeString
0x18001a49d  nop     dword ptr [rax+rax+00h]
0x18001a4a2  test    al, al
0x18001a4a4  jnz     short loc_18001A4B0
0x18001a4a6  mov     ebx, 8
0x18001a4ab  jmp     loc_18001A58F
0x18001a4b0  movzx   edi, [rbp+DestinationString.Length]
0x18001a4b4  and     r14d, 300h
0x18001a4bb  shr     edi, 1
0x18001a4bd  or      r14d, 20019h
0x18001a4c4  mov     rdx, [rbp+DestinationString.Buffer]; lpSubKey
0x18001a4c8  lea     rax, [rbp+hKey]
0x18001a4cc  mov     r9d, r14d; samDesired
0x18001a4cf  mov     [rsp+40h+phkResult], rax; phkResult
0x18001a4d4  xor     r8d, r8d; ulOptions
0x18001a4d7  mov     rcx, r15; hKey
0x18001a4da  call    cs:__imp_RegOpenKeyExW
0x18001a4e1  nop     dword ptr [rax+rax+00h]
0x18001a4e6  mov     ebx, eax
0x18001a4e8  test    eax, eax
0x18001a4ea  jz      short loc_18001A510
0x18001a4ec  cmp     eax, 2
0x18001a4ef  jnz     loc_18001A58F
0x18001a4f5  mov     rcx, [rbp+DestinationString.Buffer]
0x18001a4f9  test    edi, edi
0x18001a4fb  jz      short loc_18001A510
0x18001a4fd  dec     edi
0x18001a4ff  cmp     word ptr [rcx+rdi*2], 5Ch ; '\'
0x18001a504  jnz     short loc_18001A4F9
0x18001a506  xor     eax, eax
0x18001a508  mov     [rcx+rdi*2], ax
0x18001a50c  test    edi, edi
0x18001a50e  jnz     short loc_18001A4C4
0x18001a510  mov     rcx, [rbp+hKey]
0x18001a514  test    rcx, rcx
0x18001a517  jnz     short loc_18001A51C
0x18001a519  mov     rcx, r15; hKey
0x18001a51c  xor     r8d, r8d; pSecurityDescriptor
0x18001a51f  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18001a523  lea     edi, [r8+5]
0x18001a527  mov     edx, edi; SecurityInformation
0x18001a529  call    cs:__imp_RegGetKeySecurity
0x18001a530  nop     dword ptr [rax+rax+00h]
0x18001a535  mov     ebx, eax
0x18001a537  cmp     eax, 7Ah ; 'z'
0x18001a53a  jnz     short loc_18001A58F
0x18001a53c  mov     edx, [rbp+cbSecurityDescriptor]; uBytes
0x18001a53f  lea     ecx, [rdi+3Bh]; uFlags
0x18001a542  call    cs:__imp_LocalAlloc
0x18001a549  nop     dword ptr [rax+rax+00h]
0x18001a54e  mov     rsi, rax
0x18001a551  test    rax, rax
0x18001a554  jz      loc_18001A4A6
0x18001a55a  mov     rax, [rbp+hKey]
0x18001a55e  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18001a562  test    rax, rax
0x18001a565  mov     r8, rsi; pSecurityDescriptor
0x18001a568  mov     edx, edi; SecurityInformation
0x18001a56a  cmovnz  r15, rax
0x18001a56e  mov     rcx, r15; hKey
0x18001a571  call    cs:__imp_RegGetKeySecurity
0x18001a578  nop     dword ptr [rax+rax+00h]
0x18001a57d  mov     ebx, eax
0x18001a57f  test    eax, eax
0x18001a581  jnz     short loc_18001A58F
0x18001a583  mov     rcx, rsi; pSecurityDescriptor
0x18001a586  call    IsWrpKeyDescriptor
0x18001a58b  mov     [r12], eax
0x18001a58f  mov     rcx, [rbp+hKey]; hKey
0x18001a593  test    rcx, rcx
0x18001a596  jz      short loc_18001A5A4
0x18001a598  call    cs:__imp_RegCloseKey
0x18001a59f  nop     dword ptr [rax+rax+00h]
0x18001a5a4  test    rsi, rsi
0x18001a5a7  jz      short loc_18001A5B8
0x18001a5a9  mov     rcx, rsi; hMem
0x18001a5ac  call    cs:__imp_LocalFree
0x18001a5b3  nop     dword ptr [rax+rax+00h]
0x18001a5b8  cmp     [rbp+DestinationString.Buffer], 0
0x18001a5bd  jz      short loc_18001A5CF
0x18001a5bf  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18001a5c3  call    cs:__imp_RtlFreeUnicodeString
0x18001a5ca  nop     dword ptr [rax+rax+00h]
0x18001a5cf  lea     r11, [rsp+40h+var_s0]
0x18001a5d4  mov     eax, ebx
0x18001a5d6  mov     rbx, [r11+30h]
0x18001a5da  mov     rsi, [r11+40h]
0x18001a5de  mov     rsp, r11
0x18001a5e1  pop     r15
0x18001a5e3  pop     r14
0x18001a5e5  pop     r12
0x18001a5e7  pop     rdi
0x18001a5e8  pop     rbp
0x18001a5e9  retn
```
