# ORSetKeySecurity

- ea: `0x18017be80`
- end: `0x18017c020`
- name: `ORSetKeySecurity`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180150f70`

## callees

- `0x180003c70`
- `0x18000693e`
- `0x18017be80`
- `0x18017c028`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18017bf32`
- `ntdll!RtlAllocateHeap` at `0x18017bf32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017bf94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017bf94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017bff9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017bff9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017beda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017beda`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18017befa`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18017befa`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18017bf84`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18017bf84`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap; // rax
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+80h] [rbp+8h] BYREF

  ObjectsSecurityDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 && (v6 = *(_QWORD *)(a1 + 16), *(_DWORD *)v6 == -1092567328) )
  {
    if ( a3 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
      if ( *(_WORD *)(a1 + 30) )
      {
        LastError = 1018;
      }
      else if ( IsValidSecurityDescriptor(a3) )
      {
        LastError = 0;
        v8 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap;
        if ( Heap )
        {
          memcpy_0(Heap, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
          if ( SetPrivateObjectSecurityEx(a2, a3, &ObjectsSecurityDescriptor, 8u, &CmKeyMapping, 0)
            || (LastError = GetLastError()) == 0 )
          {
            LastError = OrpAssignKeySecurityToTreeNode(a1, ObjectsSecurityDescriptor);
            if ( !LastError )
            {
              ++*(_QWORD *)(a1 + 168);
              LastError = 0;
              *(_DWORD *)(v6 + 180) = 1;
            }
          }
        }
      }
      else
      {
        LastError = 1338;
      }
      if ( ObjectsSecurityDescriptor )
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, ObjectsSecurityDescriptor);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 6;
  }
  return LastError;
}

```

## disassembly

```asm
0x18017be80  mov     rax, rsp
0x18017be83  push    rbx
0x18017be84  push    rbp
0x18017be85  push    rsi
0x18017be86  push    rdi
0x18017be87  push    r12
0x18017be89  push    r13
0x18017be8b  push    r14
0x18017be8d  push    r15
0x18017be8f  sub     rsp, 38h
0x18017be93  xor     r13d, r13d
0x18017be96  mov     rbp, r8
0x18017be99  mov     [rax+8], r13
0x18017be9d  mov     r12d, edx
0x18017bea0  mov     eax, 746Eh
0x18017bea5  mov     rdi, rcx
0x18017bea8  cmp     [rcx+1Ch], ax
0x18017beac  jnz     loc_18017C007
0x18017beb2  mov     rsi, [rcx+10h]
0x18017beb6  cmp     dword ptr [rsi], 0BEE0BEE0h
0x18017bebc  jnz     loc_18017C007
0x18017bec2  test    r8, r8
0x18017bec5  jnz     short loc_18017BED0
0x18017bec7  lea     ebx, [r8+57h]
0x18017becb  jmp     loc_18017C00C
0x18017bed0  lea     r14, [rsi+88h]
0x18017bed7  mov     rcx, r14; lpCriticalSection
0x18017beda  call    cs:__imp_EnterCriticalSection
0x18017bee1  nop     dword ptr [rax+rax+00h]
0x18017bee6  cmp     [rdi+1Eh], r13w
0x18017beeb  jz      short loc_18017BEF7
0x18017beed  mov     ebx, 3FAh
0x18017bef2  jmp     loc_18017BFD0
0x18017bef7  mov     rcx, rbp; pSecurityDescriptor
0x18017befa  call    cs:__imp_IsValidSecurityDescriptor
0x18017bf01  nop     dword ptr [rax+rax+00h]
0x18017bf06  test    eax, eax
0x18017bf08  jnz     short loc_18017BF14
0x18017bf0a  mov     ebx, 53Ah
0x18017bf0f  jmp     loc_18017BFD0
0x18017bf14  mov     rax, [rdi+60h]
0x18017bf18  xor     edx, edx; Flags
0x18017bf1a  mov     rcx, gs:60h
0x18017bf23  mov     ebx, r13d
0x18017bf26  mov     r15, [rax+10h]
0x18017bf2a  mov     rcx, [rcx+30h]; HeapHandle
0x18017bf2e  mov     r8d, [r15+10h]; Size
0x18017bf32  call    cs:__imp_RtlAllocateHeap
0x18017bf39  nop     dword ptr [rax+rax+00h]
0x18017bf3e  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x18017bf46  test    rax, rax
0x18017bf49  jz      loc_18017BFD0
0x18017bf4f  mov     r8d, [r15+10h]; Size
0x18017bf53  lea     rdx, [r15+14h]; Src
0x18017bf57  mov     rcx, rax; void *
0x18017bf5a  call    memcpy_0
0x18017bf5f  lea     rax, CmKeyMapping
0x18017bf66  mov     [rsp+78h+Token], r13; Token
0x18017bf6b  mov     r9d, 8; AutoInheritFlags
0x18017bf71  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x18017bf76  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18017bf7e  mov     rdx, rbp; ModificationDescriptor
0x18017bf81  mov     ecx, r12d; SecurityInformation
0x18017bf84  call    cs:__imp_SetPrivateObjectSecurityEx
0x18017bf8b  nop     dword ptr [rax+rax+00h]
0x18017bf90  test    eax, eax
0x18017bf92  jnz     short loc_18017BFA6
0x18017bf94  call    cs:__imp_GetLastError
0x18017bf9b  nop     dword ptr [rax+rax+00h]
0x18017bfa0  mov     ebx, eax
0x18017bfa2  test    eax, eax
0x18017bfa4  jnz     short loc_18017BFD0
0x18017bfa6  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x18017bfae  mov     rcx, rdi
0x18017bfb1  call    OrpAssignKeySecurityToTreeNode
0x18017bfb6  mov     ebx, eax
0x18017bfb8  test    eax, eax
0x18017bfba  jnz     short loc_18017BFD0
0x18017bfbc  inc     qword ptr [rdi+0A8h]
0x18017bfc3  mov     ebx, r13d
0x18017bfc6  mov     dword ptr [rsi+0B4h], 1
0x18017bfd0  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x18017bfd8  jz      short loc_18017BFF6
0x18017bfda  mov     rcx, gs:60h
0x18017bfe3  xor     edx, edx; Flags
0x18017bfe5  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x18017bfed  mov     rcx, [rcx+30h]; HeapHandle
0x18017bff1  call    RtlFreeHeap_0
0x18017bff6  mov     rcx, r14; lpCriticalSection
0x18017bff9  call    cs:__imp_LeaveCriticalSection
0x18017c000  nop     dword ptr [rax+rax+00h]
0x18017c005  jmp     short loc_18017C00C
0x18017c007  mov     ebx, 6
0x18017c00c  mov     eax, ebx
0x18017c00e  add     rsp, 38h
0x18017c012  pop     r15
0x18017c014  pop     r14
0x18017c016  pop     r13
0x18017c018  pop     r12
0x18017c01a  pop     rdi
0x18017c01b  pop     rsi
0x18017c01c  pop     rbp
0x18017c01d  pop     rbx
0x18017c01e  retn
```
