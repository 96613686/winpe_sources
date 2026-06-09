# IsKeyProtected

- ea: `0x180010250`
- end: `0x1800103eb`
- name: `IsKeyProtected`
- size: `411`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010250`
- `0x1800105f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800103ac`
- `KERNEL32!LocalFree` at `0x1800103ac`
- `KERNEL32!LocalAlloc` at `0x180010342`
- `KERNEL32!LocalAlloc` at `0x180010342`
- `ntdll!RtlFreeUnicodeString` at `0x1800103c3`
- `ntdll!RtlFreeUnicodeString` at `0x1800103c3`
- `ntdll!RtlCreateUnicodeString` at `0x180010296`
- `ntdll!RtlCreateUnicodeString` at `0x180010296`
- `ADVAPI32!RegOpenKeyExW` at `0x1800102da`
- `ADVAPI32!RegOpenKeyExW` at `0x1800102da`
- `ADVAPI32!RegCloseKey` at `0x180010398`
- `ADVAPI32!RegCloseKey` at `0x180010398`
- `ADVAPI32!RegGetKeySecurity` at `0x180010329`
- `ADVAPI32!RegGetKeySecurity` at `0x180010371`
- `ADVAPI32!RegGetKeySecurity` at `0x180010329`
- `ADVAPI32!RegGetKeySecurity` at `0x180010371`

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
0x180010250  mov     [rsp-28h+arg_0], rbx
0x180010255  mov     [rsp-28h+arg_10], rsi
0x18001025a  push    rbp
0x18001025b  push    rdi
0x18001025c  push    r12
0x18001025e  push    r14
0x180010260  push    r15
0x180010262  mov     rbp, rsp
0x180010265  sub     rsp, 40h
0x180010269  xor     esi, esi
0x18001026b  mov     [rbp+hKey], 0
0x180010273  mov     [rbp+cbSecurityDescriptor], esi
0x180010276  xorps   xmm0, xmm0
0x180010279  mov     [r9], esi
0x18001027c  mov     r12, r9
0x18001027f  mov     r14d, r8d
0x180010282  mov     r15, rcx
0x180010285  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180010289  test    rdx, rdx
0x18001028c  jz      loc_180010319
0x180010292  lea     rcx, [rbp+DestinationString]; DestinationString
0x180010296  call    cs:__imp_RtlCreateUnicodeString
0x18001029d  nop     dword ptr [rax+rax+00h]
0x1800102a2  test    al, al
0x1800102a4  jnz     short loc_1800102B0
0x1800102a6  mov     ebx, 8
0x1800102ab  jmp     loc_18001038F
0x1800102b0  movzx   edi, [rbp+DestinationString.Length]
0x1800102b4  and     r14d, 300h
0x1800102bb  shr     edi, 1
0x1800102bd  or      r14d, 20019h
0x1800102c4  mov     rdx, [rbp+DestinationString.Buffer]; lpSubKey
0x1800102c8  lea     rax, [rbp+hKey]
0x1800102cc  mov     r9d, r14d; samDesired
0x1800102cf  mov     [rsp+40h+phkResult], rax; phkResult
0x1800102d4  xor     r8d, r8d; ulOptions
0x1800102d7  mov     rcx, r15; hKey
0x1800102da  call    cs:__imp_RegOpenKeyExW
0x1800102e1  nop     dword ptr [rax+rax+00h]
0x1800102e6  mov     ebx, eax
0x1800102e8  test    eax, eax
0x1800102ea  jz      short loc_180010310
0x1800102ec  cmp     eax, 2
0x1800102ef  jnz     loc_18001038F
0x1800102f5  mov     rcx, [rbp+DestinationString.Buffer]
0x1800102f9  test    edi, edi
0x1800102fb  jz      short loc_180010310
0x1800102fd  dec     edi
0x1800102ff  cmp     word ptr [rcx+rdi*2], 5Ch ; '\'
0x180010304  jnz     short loc_1800102F9
0x180010306  xor     eax, eax
0x180010308  mov     [rcx+rdi*2], ax
0x18001030c  test    edi, edi
0x18001030e  jnz     short loc_1800102C4
0x180010310  mov     rcx, [rbp+hKey]
0x180010314  test    rcx, rcx
0x180010317  jnz     short loc_18001031C
0x180010319  mov     rcx, r15; hKey
0x18001031c  xor     r8d, r8d; pSecurityDescriptor
0x18001031f  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180010323  lea     edi, [r8+5]
0x180010327  mov     edx, edi; SecurityInformation
0x180010329  call    cs:__imp_RegGetKeySecurity
0x180010330  nop     dword ptr [rax+rax+00h]
0x180010335  mov     ebx, eax
0x180010337  cmp     eax, 7Ah ; 'z'
0x18001033a  jnz     short loc_18001038F
0x18001033c  mov     edx, [rbp+cbSecurityDescriptor]; uBytes
0x18001033f  lea     ecx, [rdi+3Bh]; uFlags
0x180010342  call    cs:__imp_LocalAlloc
0x180010349  nop     dword ptr [rax+rax+00h]
0x18001034e  mov     rsi, rax
0x180010351  test    rax, rax
0x180010354  jz      loc_1800102A6
0x18001035a  mov     rax, [rbp+hKey]
0x18001035e  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180010362  test    rax, rax
0x180010365  mov     r8, rsi; pSecurityDescriptor
0x180010368  mov     edx, edi; SecurityInformation
0x18001036a  cmovnz  r15, rax
0x18001036e  mov     rcx, r15; hKey
0x180010371  call    cs:__imp_RegGetKeySecurity
0x180010378  nop     dword ptr [rax+rax+00h]
0x18001037d  mov     ebx, eax
0x18001037f  test    eax, eax
0x180010381  jnz     short loc_18001038F
0x180010383  mov     rcx, rsi; pSecurityDescriptor
0x180010386  call    IsWrpKeyDescriptor
0x18001038b  mov     [r12], eax
0x18001038f  mov     rcx, [rbp+hKey]; hKey
0x180010393  test    rcx, rcx
0x180010396  jz      short loc_1800103A4
0x180010398  call    cs:__imp_RegCloseKey
0x18001039f  nop     dword ptr [rax+rax+00h]
0x1800103a4  test    rsi, rsi
0x1800103a7  jz      short loc_1800103B8
0x1800103a9  mov     rcx, rsi; hMem
0x1800103ac  call    cs:__imp_LocalFree
0x1800103b3  nop     dword ptr [rax+rax+00h]
0x1800103b8  cmp     [rbp+DestinationString.Buffer], 0
0x1800103bd  jz      short loc_1800103CF
0x1800103bf  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800103c3  call    cs:__imp_RtlFreeUnicodeString
0x1800103ca  nop     dword ptr [rax+rax+00h]
0x1800103cf  lea     r11, [rsp+40h+var_s0]
0x1800103d4  mov     eax, ebx
0x1800103d6  mov     rbx, [r11+30h]
0x1800103da  mov     rsi, [r11+40h]
0x1800103de  mov     rsp, r11
0x1800103e1  pop     r15
0x1800103e3  pop     r14
0x1800103e5  pop     r12
0x1800103e7  pop     rdi
0x1800103e8  pop     rbp
0x1800103e9  retn
```
