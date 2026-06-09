# Int_NetworkIsolationInitializeCapabilitySecurityDescriptors(void)

- ea: `0x180049c44`
- end: `0x180049d05`
- name: `?Int_NetworkIsolationInitializeCapabilitySecurityDescriptors@@YAKXZ`
- size: `193`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053e20`
- `0x180053fa0`

## callees

- `0x180005954`
- `0x180049c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cc4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180049c69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180049cba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180049c69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180049cba`

## pseudocode

```c
__int64 Int_NetworkIsolationInitializeCapabilitySecurityDescriptors(void)
{
  DWORD LastError; // ebx
  FwPolicy2 *v1; // rcx
  __int64 v2; // rdx

  if ( g_ListenerCapableSD
    || ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:SYG:SYD:(A;;RCWD;;;S-1-15-3-2)(A;;RCWD;;;S-1-15-3-3)(A;;RCWD;;;S-1-15-3-4214768333-1334025770-122408079-39191"
          "88833)(A;;RCWD;;;WD)(A;;RCWD;;;AN)",
         1u,
         &g_ListenerCapableSD,
         0) )
  {
    LastError = 0;
    if ( !g_SocketCreationCapableSD
      && !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;RCWD;;;S-1-15-3-1)(A;;RCWD;;;S-1-15-3-2)(A;;RCWD;;;S-1-15-3-3)(A;;RCWD;;;S-1-15-3-4214768333-1"
             "334025770-122408079-3919188833)(A;;RCWD;;;WD)(A;;RCWD;;;AN)",
            1u,
            &g_SocketCreationCapableSD,
            0) )
    {
      LastError = GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v2 = 525;
        goto LABEL_11;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 524;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180049c44  push    rbx
0x180049c46  sub     rsp, 20h
0x180049c4a  cmp     cs:?g_ListenerCapableSD@@3PEAXEA, 0; void * g_ListenerCapableSD
0x180049c52  jnz     short loc_180049C9B
0x180049c54  xor     r9d, r9d; SecurityDescriptorSize
0x180049c57  lea     r8, ?g_ListenerCapableSD@@3PEAXEA; SecurityDescriptor
0x180049c5e  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;RCWD;;;S-1-15-3-2)(A;;RCW"...
0x180049c65  lea     edx, [r9+1]; StringSDRevision
0x180049c69  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180049c6f  test    eax, eax
0x180049c71  jnz     short loc_180049C9B
0x180049c73  call    cs:__imp_GetLastError
0x180049c79  mov     ebx, eax
0x180049c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c82  lea     rax, WPP_GLOBAL_Control
0x180049c89  cmp     rcx, rax
0x180049c8c  jz      short loc_180049CFD
0x180049c8e  test    byte ptr [rcx+1Ch], 1
0x180049c92  jz      short loc_180049CFD
0x180049c94  mov     edx, 20Ch
0x180049c99  jmp     short loc_180049CEA
0x180049c9b  xor     ebx, ebx
0x180049c9d  cmp     cs:?g_SocketCreationCapableSD@@3PEAXEA, rbx; void * g_SocketCreationCapableSD
0x180049ca4  jnz     short loc_180049CFD
0x180049ca6  xor     r9d, r9d; SecurityDescriptorSize
0x180049ca9  lea     r8, ?g_SocketCreationCapableSD@@3PEAXEA; SecurityDescriptor
0x180049cb0  lea     edx, [rbx+1]; StringSDRevision
0x180049cb3  lea     rcx, aOSygSydARcwdS1; "O:SYG:SYD:(A;;RCWD;;;S-1-15-3-1)(A;;RCW"...
0x180049cba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180049cc0  test    eax, eax
0x180049cc2  jnz     short loc_180049CFD
0x180049cc4  call    cs:__imp_GetLastError
0x180049cca  mov     ebx, eax
0x180049ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cd3  lea     rax, WPP_GLOBAL_Control
0x180049cda  cmp     rcx, rax
0x180049cdd  jz      short loc_180049CFD
0x180049cdf  test    byte ptr [rcx+1Ch], 1
0x180049ce3  jz      short loc_180049CFD
0x180049ce5  mov     edx, 20Dh
0x180049cea  mov     rcx, [rcx+10h]
0x180049cee  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180049cf5  mov     r9d, ebx
0x180049cf8  call    WPP_SF_d
0x180049cfd  mov     eax, ebx
0x180049cff  add     rsp, 20h
0x180049d03  pop     rbx
0x180049d04  retn
```
