# NcbPolicyIsPackageSidAllowed

- ea: `0x18000dda4`
- end: `0x18000de98`
- name: `NcbPolicyIsPackageSidAllowed`
- size: `244`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, PSID Sid1@<rdx>, PSID@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000be70`

## callees

- `0x18000a0a0`
- `0x18000dda4`
- `0x18000e1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dde4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dde4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de3e`

## string_xrefs

- `0x18000de7b`: `NcbPolicy: NcbPolicyIsPackageSidAllowed returned with result - `

## pseudocode

```c
unsigned __int8 __fastcall NcbPolicyIsPackageSidAllowed(
        __int64 a1,
        unsigned __int8 *Sid1,
        PSID a3,
        char a4,
        _DWORD *a5,
        _DWORD *a6)
{
  char v10; // si
  bool v11; // di
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int8 v14; // bl

  *a5 = 0;
  *a6 = 0;
  EnterCriticalSection(&g_NcbPolicyLock);
  if ( NcbPolicyFindMatchingPolicyUnderLock(Sid1, a3, 0, 1, a1, 1) )
  {
    v10 = 1;
    v11 = 1;
  }
  else
  {
    v10 = 0;
    v11 = NcbPolicyFindMatchingPolicyUnderLock(Sid1, a3, 0, 1, a1, 0) != 0;
  }
  LeaveCriticalSection(&g_NcbPolicyLock);
  v14 = v10;
  if ( !a4 )
    v14 = v11;
  if ( v10 )
    *a5 = g_NcbPolicyMaxHardwareSlotsAllowed;
  if ( v11 )
  {
    v13 = (unsigned int)g_NcbPolicyMaxSoftwareSlotsAllowed;
    *a6 = g_NcbPolicyMaxSoftwareSlotsAllowed;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v13, v12, L"NcbPolicy: NcbPolicyIsPackageSidAllowed returned with result - ", v14);
  return v14;
}

```

## disassembly

```asm
0x18000dda4  push    rbx
0x18000dda6  push    rbp
0x18000dda7  push    rsi
0x18000dda8  push    rdi
0x18000dda9  push    r12
0x18000ddab  push    r14
0x18000ddad  push    r15
0x18000ddaf  sub     rsp, 30h
0x18000ddb3  mov     r15, [rsp+68h+arg_20]
0x18000ddbb  mov     rbp, rcx
0x18000ddbe  mov     r14, [rsp+68h+arg_28]
0x18000ddc6  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x18000ddcd  mov     r12b, r9b
0x18000ddd0  mov     rbx, r8
0x18000ddd3  mov     rdi, rdx
0x18000ddd6  mov     dword ptr [r15], 0
0x18000dddd  mov     dword ptr [r14], 0
0x18000dde4  call    cs:__imp_EnterCriticalSection
0x18000ddea  mov     r9b, 1
0x18000dded  mov     [rsp+68h+var_40], 1; char
0x18000ddf2  xor     r8d, r8d
0x18000ddf5  mov     [rsp+68h+var_48], rbp; __int64
0x18000ddfa  mov     rdx, rbx; PSID
0x18000ddfd  mov     rcx, rdi; Sid1
0x18000de00  call    NcbPolicyFindMatchingPolicyUnderLock
0x18000de05  test    rax, rax
0x18000de08  jz      short loc_18000DE12
0x18000de0a  mov     sil, 1
0x18000de0d  mov     dil, sil
0x18000de10  jmp     short loc_18000DE37
0x18000de12  xor     sil, sil
0x18000de15  mov     r9b, 1
0x18000de18  mov     [rsp+68h+var_40], sil; char
0x18000de1d  xor     r8d, r8d
0x18000de20  mov     rdx, rbx; PSID
0x18000de23  mov     [rsp+68h+var_48], rbp; __int64
0x18000de28  mov     rcx, rdi; Sid1
0x18000de2b  call    NcbPolicyFindMatchingPolicyUnderLock
0x18000de30  test    rax, rax
0x18000de33  setnz   dil
0x18000de37  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x18000de3e  call    cs:__imp_LeaveCriticalSection
0x18000de44  test    r12b, r12b
0x18000de47  movzx   ebx, sil
0x18000de4b  movzx   eax, dil
0x18000de4f  cmovz   ebx, eax
0x18000de52  test    sil, sil
0x18000de55  jz      short loc_18000DE60
0x18000de57  mov     eax, cs:g_NcbPolicyMaxHardwareSlotsAllowed
0x18000de5d  mov     [r15], eax
0x18000de60  test    dil, dil
0x18000de63  jz      short loc_18000DE6E
0x18000de65  mov     ecx, cs:g_NcbPolicyMaxSoftwareSlotsAllowed
0x18000de6b  mov     [r14], ecx
0x18000de6e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000de75  jz      short loc_18000DE87
0x18000de77  movzx   r9d, bl
0x18000de7b  lea     r8, aNcbpolicyNcbpo_8; "NcbPolicy: NcbPolicyIsPackageSidAllowed"...
0x18000de82  call    McTemplateU0zq_EventWriteTransfer
0x18000de87  mov     al, bl
0x18000de89  add     rsp, 30h
0x18000de8d  pop     r15
0x18000de8f  pop     r14
0x18000de91  pop     r12
0x18000de93  pop     rdi
0x18000de94  pop     rsi
0x18000de95  pop     rbp
0x18000de96  pop     rbx
0x18000de97  retn
```
