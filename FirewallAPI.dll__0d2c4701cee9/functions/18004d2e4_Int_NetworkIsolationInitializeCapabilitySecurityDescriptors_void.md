# Int_NetworkIsolationInitializeCapabilitySecurityDescriptors(void)

- ea: `0x18004d2e4`
- end: `0x18004d3be`
- name: `?Int_NetworkIsolationInitializeCapabilitySecurityDescriptors@@YAKXZ`
- size: `218`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057760`
- `0x1800578e0`

## callees

- `0x180005e0c`
- `0x18004d2e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d376`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d309`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d366`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d309`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d366`

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
        v2 = 524;
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
      v2 = 523;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18004d2e4  push    rbx
0x18004d2e6  sub     rsp, 20h
0x18004d2ea  cmp     cs:?g_ListenerCapableSD@@3PEAXEA, 0; void * g_ListenerCapableSD
0x18004d2f2  jnz     short loc_18004D347
0x18004d2f4  xor     r9d, r9d; SecurityDescriptorSize
0x18004d2f7  lea     r8, ?g_ListenerCapableSD@@3PEAXEA; SecurityDescriptor
0x18004d2fe  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;RCWD;;;S-1-15-3-2)(A;;RCW"...
0x18004d305  lea     edx, [r9+1]; StringSDRevision
0x18004d309  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d310  nop     dword ptr [rax+rax+00h]
0x18004d315  test    eax, eax
0x18004d317  jnz     short loc_18004D347
0x18004d319  call    cs:__imp_GetLastError
0x18004d320  nop     dword ptr [rax+rax+00h]
0x18004d325  mov     ebx, eax
0x18004d327  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d32e  lea     rax, WPP_GLOBAL_Control
0x18004d335  cmp     rcx, rax
0x18004d338  jz      short loc_18004D3B5
0x18004d33a  test    byte ptr [rcx+1Ch], 1
0x18004d33e  jz      short loc_18004D3B5
0x18004d340  mov     edx, 20Bh
0x18004d345  jmp     short loc_18004D3A2
0x18004d347  xor     ebx, ebx
0x18004d349  cmp     cs:?g_SocketCreationCapableSD@@3PEAXEA, rbx; void * g_SocketCreationCapableSD
0x18004d350  jnz     short loc_18004D3B5
0x18004d352  xor     r9d, r9d; SecurityDescriptorSize
0x18004d355  lea     r8, ?g_SocketCreationCapableSD@@3PEAXEA; SecurityDescriptor
0x18004d35c  lea     edx, [rbx+1]; StringSDRevision
0x18004d35f  lea     rcx, aOSygSydARcwdS1; "O:SYG:SYD:(A;;RCWD;;;S-1-15-3-1)(A;;RCW"...
0x18004d366  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d36d  nop     dword ptr [rax+rax+00h]
0x18004d372  test    eax, eax
0x18004d374  jnz     short loc_18004D3B5
0x18004d376  call    cs:__imp_GetLastError
0x18004d37d  nop     dword ptr [rax+rax+00h]
0x18004d382  mov     ebx, eax
0x18004d384  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d38b  lea     rax, WPP_GLOBAL_Control
0x18004d392  cmp     rcx, rax
0x18004d395  jz      short loc_18004D3B5
0x18004d397  test    byte ptr [rcx+1Ch], 1
0x18004d39b  jz      short loc_18004D3B5
0x18004d39d  mov     edx, 20Ch
0x18004d3a2  mov     rcx, [rcx+10h]
0x18004d3a6  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004d3ad  mov     r9d, ebx
0x18004d3b0  call    WPP_SF_d
0x18004d3b5  mov     eax, ebx
0x18004d3b7  add     rsp, 20h
0x18004d3bb  pop     rbx
0x18004d3bc  retn
```
