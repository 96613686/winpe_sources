# UbpmpInitBrokers(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002d0b0`
- end: `0x18002d164`
- name: `?UbpmpInitBrokers@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `180`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002d0b0`
- `0x1800351ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d105`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d0dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d0dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d14f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d14f`

## pseudocode

```c
__int64 __fastcall UbpmpInitBrokers(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  unsigned int v3; // ebx
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v5; // rcx
  PSECURITY_DESCRIPTOR v7; // [rsp+20h] [rbp-18h] BYREF
  ULONG v8; // [rsp+58h] [rbp+20h] BYREF

  v3 = 1;
  v7 = 0;
  v8 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &v7, &v8) )
  {
    g_pSecurityDescriptor = v7;
    v5 = 0;
    v7 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, LastError);
    }
    v5 = v7;
    v3 = 0;
  }
  if ( v5 )
    LocalFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18002d0b0  mov     rax, rsp
0x18002d0b3  push    rbx
0x18002d0b4  sub     rsp, 30h
0x18002d0b8  mov     ebx, 1
0x18002d0bd  mov     qword ptr [rax-18h], 0
0x18002d0c5  mov     edx, ebx; StringSDRevision
0x18002d0c7  mov     dword ptr [rax+20h], 0
0x18002d0ce  lea     r9, [rax+20h]; SecurityDescriptorSize
0x18002d0d2  lea     r8, [rax-18h]; SecurityDescriptor
0x18002d0d6  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x18002d0dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002d0e4  nop     dword ptr [rax+rax+00h]
0x18002d0e9  test    eax, eax
0x18002d0eb  jnz     short loc_18002D137
0x18002d0ed  mov     rax, cs:WPP_GLOBAL_Control
0x18002d0f4  lea     rcx, WPP_GLOBAL_Control
0x18002d0fb  cmp     rax, rcx
0x18002d0fe  jz      short loc_18002D12E
0x18002d100  test    [rax+1Ch], bl
0x18002d103  jz      short loc_18002D12E
0x18002d105  call    cs:__imp_GetLastError
0x18002d10c  nop     dword ptr [rax+rax+00h]
0x18002d111  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d118  lea     edx, [rbx+1Bh]
0x18002d11b  mov     r9d, eax
0x18002d11e  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002d125  mov     rcx, [rcx+10h]
0x18002d129  call    WPP_SF_d
0x18002d12e  mov     rcx, [rsp+38h+var_18]
0x18002d133  xor     ebx, ebx
0x18002d135  jmp     short loc_18002D14A
0x18002d137  mov     rcx, [rsp+38h+var_18]
0x18002d13c  mov     cs:?g_pSecurityDescriptor@@3PEAXEA, rcx; void * g_pSecurityDescriptor
0x18002d143  xor     ecx, ecx; hMem
0x18002d145  mov     [rsp+38h+var_18], rcx
0x18002d14a  test    rcx, rcx
0x18002d14d  jz      short loc_18002D15B
0x18002d14f  call    cs:__imp_LocalFree
0x18002d156  nop     dword ptr [rax+rax+00h]
0x18002d15b  mov     eax, ebx
0x18002d15d  add     rsp, 30h
0x18002d161  pop     rbx
0x18002d162  retn
```
