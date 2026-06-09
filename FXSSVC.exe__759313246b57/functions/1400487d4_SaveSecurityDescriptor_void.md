# SaveSecurityDescriptor(void *)

- ea: `0x1400487d4`
- end: `0x140048b1c`
- name: `?SaveSecurityDescriptor@@YAKPEAX@Z`
- size: `840`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140047a48`
- `0x1400491c0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400487d4`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140048aec`
- `ADVAPI32!RegCloseKey` at `0x140048aec`
- `ADVAPI32!RegCreateKeyExW` at `0x14004888a`
- `ADVAPI32!RegCreateKeyExW` at `0x14004888a`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400488de`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400488de`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140048936`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140048936`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140048985`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140048985`
- `ADVAPI32!RegSetValueExW` at `0x1400489bc`
- `ADVAPI32!RegSetValueExW` at `0x140048aa5`
- `ADVAPI32!RegSetValueExW` at `0x1400489bc`
- `ADVAPI32!RegSetValueExW` at `0x140048aa5`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140048a48`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140048a48`
- `KERNEL32!GetLastError` at `0x140048946`
- `KERNEL32!GetLastError` at `0x140048a58`
- `KERNEL32!GetLastError` at `0x140048946`
- `KERNEL32!GetLastError` at `0x140048a58`

## string_xrefs

- `0x14004886a`: `Software\Microsoft\Fax\Security`
- `0x1400489a3`: `Descriptor`
- `0x140048a88`: `Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SaveSecurityDescriptor(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  BYTE *v4; // rdi
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  DWORD SecurityDescriptorLength; // eax
  BYTE *v11; // rax
  DWORD dwRevision; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  WORD pControl; // [rsp+98h] [rbp+38h] BYREF
  DWORD dwBufferLength; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  dwBufferLength = 0;
  pControl = 0x8000;
  hKey = 0;
  dwDisposition = 0;
  dwRevision = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Fax\\Security",
         0,
         (LPWSTR)&Class,
         0,
         0x20006u,
         0,
         &hKey,
         &dwDisposition);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v2);
    }
    return v3;
  }
  v4 = 0;
  if ( !IsValidSecurityDescriptor(pAbsoluteSecurityDescriptor) )
  {
    v3 = 1338;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v6 = 24;
    goto LABEL_15;
  }
  if ( !GetSecurityDescriptorControl(pAbsoluteSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v9 = 25;
    goto LABEL_42;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(pAbsoluteSecurityDescriptor);
  dwBufferLength = SecurityDescriptorLength;
  if ( (pControl & 0x8000u) != 0 )
  {
    LastError = RegSetValueExW(
                  hKey,
                  L"Descriptor",
                  0,
                  3u,
                  (const BYTE *)pAbsoluteSecurityDescriptor,
                  SecurityDescriptorLength);
    v3 = LastError;
    if ( !LastError )
      goto LABEL_43;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v9 = 26;
    goto LABEL_42;
  }
  v11 = (BYTE *)pMemAlloc(SecurityDescriptorLength);
  v4 = v11;
  if ( v11 )
  {
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v11, &dwBufferLength) )
    {
      LastError = RegSetValueExW(hKey, L"Descriptor", 0, 3u, v4, dwBufferLength);
      v3 = LastError;
      if ( !LastError )
        goto LABEL_43;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v9 = 29;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v9 = 28;
    }
LABEL_42:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    goto LABEL_43;
  }
  v3 = 8;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_43;
  }
  v6 = 27;
LABEL_15:
  WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    pMemFree(v4);
  return v3;
}

```

## disassembly

```asm
0x1400487d4  mov     [rsp-28h+arg_0], rbx
0x1400487d9  push    rbp
0x1400487da  push    rsi
0x1400487db  push    rdi
0x1400487dc  push    r12
0x1400487de  push    r13
0x1400487e0  mov     rbp, rsp
0x1400487e3  sub     rsp, 60h
0x1400487e7  mov     eax, 8000h
0x1400487ec  mov     [rbp+dwBufferLength], 0
0x1400487f3  mov     [rbp+pControl], ax
0x1400487f7  mov     rsi, rcx
0x1400487fa  mov     [rbp+hKey], 0
0x140048802  mov     [rbp+dwDisposition], 0
0x140048809  mov     [rbp+dwRevision], 0
0x140048810  mov     rcx, cs:WPP_GLOBAL_Control
0x140048817  lea     r12, WPP_GLOBAL_Control
0x14004881e  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140048825  cmp     rcx, r12
0x140048828  jz      short loc_140048847
0x14004882a  test    byte ptr [rcx+1Ch], 4
0x14004882e  jz      short loc_140048847
0x140048830  cmp     byte ptr [rcx+19h], 5
0x140048834  jb      short loc_140048847
0x140048836  mov     rcx, [rcx+10h]
0x14004883a  mov     edx, 16h
0x14004883f  mov     r8, r13
0x140048842  call    WPP_SF_
0x140048847  lea     rax, [rbp+dwDisposition]
0x14004884b  xor     r8d, r8d; Reserved
0x14004884e  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x140048853  lea     r9, Class; lpClass
0x14004885a  lea     rax, [rbp+hKey]
0x14004885e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140048865  mov     [rsp+60h+phkResult], rax; phkResult
0x14004886a  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Fax\\Security"
0x140048871  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004887a  mov     [rsp+60h+samDesired], 20006h; samDesired
0x140048882  mov     [rsp+60h+dwOptions], 0; dwOptions
0x14004888a  call    cs:__imp_RegCreateKeyExW
0x140048891  nop     dword ptr [rax+rax+00h]
0x140048896  mov     ebx, eax
0x140048898  test    eax, eax
0x14004889a  jz      short loc_1400488D9
0x14004889c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488a3  cmp     rcx, r12
0x1400488a6  jz      loc_140048B05
0x1400488ac  test    byte ptr [rcx+1Ch], 4
0x1400488b0  jz      loc_140048B05
0x1400488b6  cmp     byte ptr [rcx+19h], 2
0x1400488ba  jb      loc_140048B05
0x1400488c0  mov     rcx, [rcx+10h]
0x1400488c4  mov     edx, 17h
0x1400488c9  mov     r9d, eax
0x1400488cc  mov     r8, r13
0x1400488cf  call    WPP_SF_d
0x1400488d4  jmp     loc_140048B05
0x1400488d9  mov     rcx, rsi; pSecurityDescriptor
0x1400488dc  xor     edi, edi
0x1400488de  call    cs:__imp_IsValidSecurityDescriptor
0x1400488e5  nop     dword ptr [rax+rax+00h]
0x1400488ea  test    eax, eax
0x1400488ec  jnz     short loc_14004892B
0x1400488ee  mov     ebx, 53Ah
0x1400488f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488fa  cmp     rcx, r12
0x1400488fd  jz      loc_140048AE3
0x140048903  test    byte ptr [rcx+1Ch], 4
0x140048907  jz      loc_140048AE3
0x14004890d  cmp     byte ptr [rcx+19h], 2
0x140048911  jb      loc_140048AE3
0x140048917  lea     edx, [rdi+18h]
0x14004891a  mov     rcx, [rcx+10h]
0x14004891e  mov     r8, r13
0x140048921  call    WPP_SF_
0x140048926  jmp     loc_140048AE3
0x14004892b  lea     r8, [rbp+dwRevision]; lpdwRevision
0x14004892f  mov     rcx, rsi; pSecurityDescriptor
0x140048932  lea     rdx, [rbp+pControl]; pControl
0x140048936  call    cs:__imp_GetSecurityDescriptorControl
0x14004893d  nop     dword ptr [rax+rax+00h]
0x140048942  test    eax, eax
0x140048944  jnz     short loc_140048982
0x140048946  call    cs:__imp_GetLastError
0x14004894d  nop     dword ptr [rax+rax+00h]
0x140048952  mov     ebx, eax
0x140048954  mov     rcx, cs:WPP_GLOBAL_Control
0x14004895b  cmp     rcx, r12
0x14004895e  jz      loc_140048AE3
0x140048964  test    byte ptr [rcx+1Ch], 4
0x140048968  jz      loc_140048AE3
0x14004896e  cmp     byte ptr [rcx+19h], 2
0x140048972  jb      loc_140048AE3
0x140048978  mov     edx, 19h
0x14004897d  jmp     loc_140048AD4
0x140048982  mov     rcx, rsi; pSecurityDescriptor
0x140048985  call    cs:__imp_GetSecurityDescriptorLength
0x14004898c  nop     dword ptr [rax+rax+00h]
0x140048991  mov     ecx, 8000h
0x140048996  mov     [rbp+dwBufferLength], eax
0x140048999  test    [rbp+pControl], cx
0x14004899d  jz      short loc_140048A00
0x14004899f  mov     rcx, [rbp+hKey]; hKey
0x1400489a3  lea     rdx, aDescriptor; "Descriptor"
0x1400489aa  mov     [rsp+60h+samDesired], eax; cbData
0x1400489ae  mov     r9d, 3; dwType
0x1400489b4  xor     r8d, r8d; Reserved
0x1400489b7  mov     qword ptr [rsp+60h+dwOptions], rsi; lpData
0x1400489bc  call    cs:__imp_RegSetValueExW
0x1400489c3  nop     dword ptr [rax+rax+00h]
0x1400489c8  mov     ebx, eax
0x1400489ca  test    eax, eax
0x1400489cc  jz      loc_140048AE3
0x1400489d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400489d9  cmp     rcx, r12
0x1400489dc  jz      loc_140048AE3
0x1400489e2  test    byte ptr [rcx+1Ch], 4
0x1400489e6  jz      loc_140048AE3
0x1400489ec  cmp     byte ptr [rcx+19h], 2
0x1400489f0  jb      loc_140048AE3
0x1400489f6  mov     edx, 1Ah
0x1400489fb  jmp     loc_140048AD4
0x140048a00  mov     ecx, eax; dwBytes
0x140048a02  call    pMemAlloc
0x140048a07  mov     rdi, rax
0x140048a0a  test    rax, rax
0x140048a0d  jnz     short loc_140048A3E
0x140048a0f  lea     ebx, [rax+8]
0x140048a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a19  cmp     rcx, r12
0x140048a1c  jz      loc_140048AE3
0x140048a22  test    byte ptr [rcx+1Ch], 4
0x140048a26  jz      loc_140048AE3
0x140048a2c  cmp     byte ptr [rcx+19h], 2
0x140048a30  jb      loc_140048AE3
0x140048a36  lea     edx, [rax+1Bh]
0x140048a39  jmp     loc_14004891A
0x140048a3e  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x140048a42  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x140048a45  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x140048a48  call    cs:__imp_MakeSelfRelativeSD
0x140048a4f  nop     dword ptr [rax+rax+00h]
0x140048a54  test    eax, eax
0x140048a56  jnz     short loc_140048A85
0x140048a58  call    cs:__imp_GetLastError
0x140048a5f  nop     dword ptr [rax+rax+00h]
0x140048a64  mov     ebx, eax
0x140048a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a6d  cmp     rcx, r12
0x140048a70  jz      short loc_140048AE3
0x140048a72  test    byte ptr [rcx+1Ch], 4
0x140048a76  jz      short loc_140048AE3
0x140048a78  cmp     byte ptr [rcx+19h], 2
0x140048a7c  jb      short loc_140048AE3
0x140048a7e  mov     edx, 1Ch
0x140048a83  jmp     short loc_140048AD4
0x140048a85  mov     eax, [rbp+dwBufferLength]
0x140048a88  lea     rdx, aDescriptor; "Descriptor"
0x140048a8f  mov     rcx, [rbp+hKey]; hKey
0x140048a93  mov     r9d, 3; dwType
0x140048a99  mov     [rsp+60h+samDesired], eax; cbData
0x140048a9d  xor     r8d, r8d; Reserved
0x140048aa0  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x140048aa5  call    cs:__imp_RegSetValueExW
0x140048aac  nop     dword ptr [rax+rax+00h]
0x140048ab1  mov     ebx, eax
0x140048ab3  test    eax, eax
0x140048ab5  jz      short loc_140048AE3
0x140048ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140048abe  cmp     rcx, r12
0x140048ac1  jz      short loc_140048AE3
0x140048ac3  test    byte ptr [rcx+1Ch], 4
0x140048ac7  jz      short loc_140048AE3
0x140048ac9  cmp     byte ptr [rcx+19h], 2
0x140048acd  jb      short loc_140048AE3
0x140048acf  mov     edx, 1Dh
0x140048ad4  mov     rcx, [rcx+10h]
0x140048ad8  mov     r9d, eax
0x140048adb  mov     r8, r13
0x140048ade  call    WPP_SF_d
0x140048ae3  mov     rcx, [rbp+hKey]; hKey
0x140048ae7  test    rcx, rcx
0x140048aea  jz      short loc_140048AF8
0x140048aec  call    cs:__imp_RegCloseKey
0x140048af3  nop     dword ptr [rax+rax+00h]
0x140048af8  test    rdi, rdi
0x140048afb  jz      short loc_140048B05
0x140048afd  mov     rcx, rdi; lpMem
0x140048b00  call    pMemFree
0x140048b05  mov     eax, ebx
0x140048b07  mov     rbx, [rsp+60h+arg_0]
0x140048b0f  add     rsp, 60h
0x140048b13  pop     r13
0x140048b15  pop     r12
0x140048b17  pop     rdi
0x140048b18  pop     rsi
0x140048b19  pop     rbp
0x140048b1a  retn
```
