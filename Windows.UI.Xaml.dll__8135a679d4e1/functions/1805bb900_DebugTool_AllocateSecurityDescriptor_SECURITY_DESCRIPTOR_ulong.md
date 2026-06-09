# DebugTool::AllocateSecurityDescriptor(_SECURITY_DESCRIPTOR * *,ulong)

- ea: `0x1805bb900`
- end: `0x1805bba85`
- name: `?AllocateSecurityDescriptor@DebugTool@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@K@Z`
- size: `389`
- prototype: `HRESULT __fastcall(_SECURITY_DESCRIPTOR **ppSD, unsigned int ppSD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18030b470`

## callees

- `0x1805bb900`
- `0x18076e110`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1805bb9a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1805bba68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1805bb9a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1805bba68`
- `ntdll!RtlFreeSid` at `0x1805bba60`
- `ntdll!RtlFreeSid` at `0x1805bba60`
- `ntdll!RtlFreeHeap` at `0x1805bba76`
- `ntdll!RtlFreeHeap` at `0x1805bba76`
- `ntdll!RtlAllocateHeap` at `0x1805bb9b7`
- `ntdll!RtlAllocateHeap` at `0x1805bb9b7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1805bb97d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1805bb97d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1805bba25`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1805bba25`
- `ntdll!RtlAddAccessAllowedAce` at `0x1805bba0d`
- `ntdll!RtlAddAccessAllowedAce` at `0x1805bba0d`
- `ntdll!RtlCreateAcl` at `0x1805bb9f1`
- `ntdll!RtlCreateAcl` at `0x1805bb9f1`
- `ntdll!RtlLengthSid` at `0x1805bb998`
- `ntdll!RtlLengthSid` at `0x1805bb998`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1805bb9d1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1805bb9d1`

## pseudocode

```c
__int64 __fastcall DebugTool::AllocateSecurityDescriptor(_SECURITY_DESCRIPTOR **ppSD, unsigned int a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // edi
  ULONG v5; // eax
  ULONG v6; // r14d
  ULONG v7; // ebx
  HANDLE ProcessHeap; // rax
  PVOID Heap; // rax
  PVOID v10; // rbx
  NTSTATUS SecurityDescriptor; // eax
  NTSTATUS Acl; // eax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  HANDLE v16; // rax
  void *psidWindowManager; // [rsp+60h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY NtAuthority; // [rsp+68h] [rbp-1h] BYREF

  *(_WORD *)&NtAuthority.Value[4] = 1280;
  psidWindowManager = 0;
  *(_DWORD *)NtAuthority.Value = 0;
  v3 = RtlAllocateAndInitializeSid(
         &NtAuthority,
         2u,
         0x5Au,
         NtCurrentPeb()->SessionId,
         0,
         0,
         0,
         0,
         0,
         0,
         &psidWindowManager);
  v4 = v3 | 0x10000000;
  if ( v3 >= 0 )
  {
    v5 = RtlLengthSid(psidWindowManager);
    v6 = v5 + 20;
    v7 = v5 + 60;
    ProcessHeap = GetProcessHeap();
    Heap = RtlAllocateHeap(ProcessHeap, 8u, v7);
    v10 = Heap;
    if ( Heap )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(Heap, 1u);
      v4 = SecurityDescriptor | 0x10000000;
      if ( SecurityDescriptor < 0
        || (Acl = RtlCreateAcl((PACL)v10 + 5, v6, 2u), v4 = Acl | 0x10000000, Acl < 0)
        || (v13 = RtlAddAccessAllowedAce((PACL)v10 + 5, 2u, 0x10000000u, psidWindowManager),
            v4 = v13 | 0x10000000,
            v13 < 0)
        || (v14 = RtlSetDaclSecurityDescriptor(v10, 1u, (PACL)v10 + 5, 0), v4 = v14 | 0x10000000, v14 < 0) )
      {
        v16 = GetProcessHeap();
        RtlFreeHeap(v16, 0, v10);
      }
      else
      {
        *ppSD = (_SECURITY_DESCRIPTOR *)v10;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( psidWindowManager )
    RtlFreeSid(psidWindowManager);
  return v4;
}

```

## disassembly

```asm
0x1805bb900  push    rbp
0x1805bb902  push    rbx
0x1805bb903  push    rsi
0x1805bb904  push    rdi
0x1805bb905  push    r12
0x1805bb907  push    r13
0x1805bb909  push    r14
0x1805bb90b  push    r15
0x1805bb90d  lea     rbp, [rsp-1Fh]
0x1805bb912  sub     rsp, 88h
0x1805bb919  mov     rax, cs:__security_cookie
0x1805bb920  xor     rax, rsp
0x1805bb923  mov     [rbp+57h+var_50], rax
0x1805bb927  xor     r12d, r12d
0x1805bb92a  mov     word ptr [rbp+57h+NtAuthority.Value+4], 500h
0x1805bb930  mov     [rbp+57h+psidWindowManager], r12
0x1805bb934  lea     rax, [rbp+57h+psidWindowManager]
0x1805bb938  mov     [rsp+0C0h+Sid], rax; Sid
0x1805bb93d  mov     r15, ppSD
0x1805bb940  mov     [rsp+0C0h+SubAuthority7], r12d; SubAuthority7
0x1805bb945  lea     ppSD, [rbp+57h+NtAuthority]; IdentifierAuthority
0x1805bb949  mov     [rsp+0C0h+SubAuthority6], r12d; SubAuthority6
0x1805bb94e  lea     r8d, [r12+5Ah]; SubAuthority0
0x1805bb953  mov     dword ptr [rbp+57h+NtAuthority.Value], r12d
0x1805bb957  mov     dl, 2; SubAuthorityCount
0x1805bb959  mov     r9, gs:60h
0x1805bb962  mov     [rsp+0C0h+SubAuthority5], r12d; SubAuthority5
0x1805bb967  mov     [rsp+0C0h+SubAuthority4], r12d; SubAuthority4
0x1805bb96c  mov     [rsp+0C0h+SubAuthority3], r12d; SubAuthority3
0x1805bb971  mov     r9d, [r9+2C0h]; SubAuthority1
0x1805bb978  mov     [rsp+0C0h+SubAuthority2], r12d; SubAuthority2
0x1805bb97d  call    cs:__imp_RtlAllocateAndInitializeSid
0x1805bb983  mov     edi, eax
0x1805bb985  mov     r13d, 10000000h
0x1805bb98b  or      edi, r13d
0x1805bb98e  jl      loc_1805BBA35
0x1805bb994  mov     ppSD, [rbp+57h+psidWindowManager]; Sid
0x1805bb998  call    cs:__imp_RtlLengthSid
0x1805bb99e  lea     r14d, [rax+14h]
0x1805bb9a2  lea     ebx, [r14+28h]
0x1805bb9a6  call    cs:__imp_GetProcessHeap
0x1805bb9ac  mov     r8d, ebx; Size
0x1805bb9af  lea     edx, [r12+8]; Flags
0x1805bb9b4  mov     ppSD, rax; HeapHandle
0x1805bb9b7  call    cs:__imp_RtlAllocateHeap
0x1805bb9bd  mov     rbx, rax
0x1805bb9c0  test    rax, rax
0x1805bb9c3  jz      loc_1805BBA7E
0x1805bb9c9  lea     edx, [r12+1]; Revision
0x1805bb9ce  mov     ppSD, rax; SecurityDescriptor
0x1805bb9d1  call    cs:__imp_RtlCreateSecurityDescriptor
0x1805bb9d7  mov     edi, eax
0x1805bb9d9  or      edi, r13d
0x1805bb9dc  jl      loc_1805BBA68
0x1805bb9e2  lea     rsi, [rbx+28h]
0x1805bb9e6  mov     edx, r14d; AclSize
0x1805bb9e9  mov     ppSD, rsi; Acl
0x1805bb9ec  lea     r8d, [r12+2]; AclRevision
0x1805bb9f1  call    cs:__imp_RtlCreateAcl
0x1805bb9f7  mov     edi, eax
0x1805bb9f9  or      edi, r13d
0x1805bb9fc  jl      short loc_1805BBA68
0x1805bb9fe  mov     r9, [rbp+57h+psidWindowManager]; Sid
0x1805bba02  lea     edx, [r12+2]; Revision
0x1805bba07  mov     r8d, r13d; AccessMask
0x1805bba0a  mov     ppSD, rsi; Acl
0x1805bba0d  call    cs:__imp_RtlAddAccessAllowedAce
0x1805bba13  mov     edi, eax
0x1805bba15  or      edi, r13d
0x1805bba18  jl      short loc_1805BBA68
0x1805bba1a  xor     r9d, r9d; DaclDefaulted
0x1805bba1d  mov     r8, rsi; Dacl
0x1805bba20  mov     dl, 1; DaclPresent
0x1805bba22  mov     ppSD, rbx; SecurityDescriptor
0x1805bba25  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1805bba2b  mov     edi, eax
0x1805bba2d  or      edi, r13d
0x1805bba30  jl      short loc_1805BBA68
0x1805bba32  mov     [r15], rbx
0x1805bba35  mov     ppSD, [rbp+57h+psidWindowManager]; Sid
0x1805bba39  test    ppSD, ppSD
0x1805bba3c  jnz     short loc_1805BBA60
0x1805bba3e  mov     eax, edi
0x1805bba40  mov     ppSD, [rbp+57h+var_50]
0x1805bba44  xor     ppSD, rsp; StackCookie
0x1805bba47  call    __security_check_cookie
0x1805bba4c  add     rsp, 88h
0x1805bba53  pop     r15
0x1805bba55  pop     r14
0x1805bba57  pop     r13
0x1805bba59  pop     r12
0x1805bba5b  pop     rdi
0x1805bba5c  pop     rsi
0x1805bba5d  pop     rbx
0x1805bba5e  pop     rbp
0x1805bba5f  retn
0x1805bba60  call    cs:__imp_RtlFreeSid
0x1805bba66  jmp     short loc_1805BBA3E
0x1805bba68  call    cs:__imp_GetProcessHeap
0x1805bba6e  mov     r8, rbx; P
0x1805bba71  xor     edx, edx; Flags
0x1805bba73  mov     ppSD, rax; HeapHandle
0x1805bba76  call    cs:__imp_RtlFreeHeap
0x1805bba7c  jmp     short loc_1805BBA35
0x1805bba7e  mov     edi, 8007000Eh
0x1805bba83  jmp     short loc_1805BBA35
```
