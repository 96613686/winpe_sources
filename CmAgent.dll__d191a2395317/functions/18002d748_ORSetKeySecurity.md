# ORSetKeySecurity

- ea: `0x18002d748`
- end: `0x18002d8e1`
- name: `ORSetKeySecurity`
- size: `409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002bbc8`

## callees

- `0x18000301b`
- `0x180003027`
- `0x18002d748`
- `0x18002d8e8`
- `0x1800361a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d7a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d7a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d8ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d855`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18002d845`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18002d845`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002d7c2`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18002d7c2`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap_0; // rax
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
        Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap_0;
        if ( Heap_0 )
        {
          memcpy_0(Heap_0, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
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
0x18002d748  mov     rax, rsp
0x18002d74b  push    rbx
0x18002d74c  push    rbp
0x18002d74d  push    rsi
0x18002d74e  push    rdi
0x18002d74f  push    r12
0x18002d751  push    r13
0x18002d753  push    r14
0x18002d755  push    r15
0x18002d757  sub     rsp, 38h
0x18002d75b  xor     r13d, r13d
0x18002d75e  mov     rbp, r8
0x18002d761  mov     [rax+8], r13
0x18002d765  mov     r12d, edx
0x18002d768  mov     eax, 746Eh
0x18002d76d  mov     rdi, rcx
0x18002d770  cmp     [rcx+1Ch], ax
0x18002d774  jnz     loc_18002D8C8
0x18002d77a  mov     rsi, [rcx+10h]
0x18002d77e  cmp     dword ptr [rsi], 0BEE0BEE0h
0x18002d784  jnz     loc_18002D8C8
0x18002d78a  test    r8, r8
0x18002d78d  jnz     short loc_18002D798
0x18002d78f  lea     ebx, [r8+57h]
0x18002d793  jmp     loc_18002D8CD
0x18002d798  lea     r14, [rsi+88h]
0x18002d79f  mov     rcx, r14; lpCriticalSection
0x18002d7a2  call    cs:__imp_EnterCriticalSection
0x18002d7a9  nop     dword ptr [rax+rax+00h]
0x18002d7ae  cmp     [rdi+1Eh], r13w
0x18002d7b3  jz      short loc_18002D7BF
0x18002d7b5  mov     ebx, 3FAh
0x18002d7ba  jmp     loc_18002D891
0x18002d7bf  mov     rcx, rbp; pSecurityDescriptor
0x18002d7c2  call    cs:__imp_IsValidSecurityDescriptor
0x18002d7c9  nop     dword ptr [rax+rax+00h]
0x18002d7ce  test    eax, eax
0x18002d7d0  jnz     short loc_18002D7DC
0x18002d7d2  mov     ebx, 53Ah
0x18002d7d7  jmp     loc_18002D891
0x18002d7dc  mov     rax, [rdi+60h]
0x18002d7e0  xor     edx, edx; Flags
0x18002d7e2  mov     rcx, gs:60h
0x18002d7eb  mov     ebx, r13d
0x18002d7ee  mov     r15, [rax+10h]
0x18002d7f2  mov     rcx, [rcx+30h]; HeapHandle
0x18002d7f6  mov     r8d, [r15+10h]; Size
0x18002d7fa  call    RtlAllocateHeap_0
0x18002d7ff  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x18002d807  test    rax, rax
0x18002d80a  jz      loc_18002D891
0x18002d810  mov     r8d, [r15+10h]; Size
0x18002d814  lea     rdx, [r15+14h]; Src
0x18002d818  mov     rcx, rax; void *
0x18002d81b  call    memcpy_0
0x18002d820  lea     rax, CmKeyMapping
0x18002d827  mov     [rsp+78h+Token], r13; Token
0x18002d82c  mov     r9d, 8; AutoInheritFlags
0x18002d832  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x18002d837  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18002d83f  mov     rdx, rbp; ModificationDescriptor
0x18002d842  mov     ecx, r12d; SecurityInformation
0x18002d845  call    cs:__imp_SetPrivateObjectSecurityEx
0x18002d84c  nop     dword ptr [rax+rax+00h]
0x18002d851  test    eax, eax
0x18002d853  jnz     short loc_18002D867
0x18002d855  call    cs:__imp_GetLastError
0x18002d85c  nop     dword ptr [rax+rax+00h]
0x18002d861  mov     ebx, eax
0x18002d863  test    eax, eax
0x18002d865  jnz     short loc_18002D891
0x18002d867  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x18002d86f  mov     rcx, rdi
0x18002d872  call    OrpAssignKeySecurityToTreeNode
0x18002d877  mov     ebx, eax
0x18002d879  test    eax, eax
0x18002d87b  jnz     short loc_18002D891
0x18002d87d  inc     qword ptr [rdi+0A8h]
0x18002d884  mov     ebx, r13d
0x18002d887  mov     dword ptr [rsi+0B4h], 1
0x18002d891  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x18002d899  jz      short loc_18002D8B7
0x18002d89b  mov     rcx, gs:60h
0x18002d8a4  xor     edx, edx; Flags
0x18002d8a6  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x18002d8ae  mov     rcx, [rcx+30h]; HeapHandle
0x18002d8b2  call    RtlFreeHeap_0
0x18002d8b7  mov     rcx, r14; lpCriticalSection
0x18002d8ba  call    cs:__imp_LeaveCriticalSection
0x18002d8c1  nop     dword ptr [rax+rax+00h]
0x18002d8c6  jmp     short loc_18002D8CD
0x18002d8c8  mov     ebx, 6
0x18002d8cd  mov     eax, ebx
0x18002d8cf  add     rsp, 38h
0x18002d8d3  pop     r15
0x18002d8d5  pop     r14
0x18002d8d7  pop     r13
0x18002d8d9  pop     r12
0x18002d8db  pop     rdi
0x18002d8dc  pop     rsi
0x18002d8dd  pop     rbp
0x18002d8de  pop     rbx
0x18002d8df  retn
```
