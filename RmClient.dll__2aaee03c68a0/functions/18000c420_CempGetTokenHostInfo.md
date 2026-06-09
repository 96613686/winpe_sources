# CempGetTokenHostInfo

- ea: `0x18000c420`
- end: `0x18000c654`
- name: `CempGetTokenHostInfo`
- size: `564`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c340`

## callees

- `0x18000c420`
- `0x18000c9c0`
- `0x18001ae82`
- `0x18001ae8e`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18000c47b`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18000c47b`
- `ntdll!RtlFreeHeap` at `0x18000c5c8`
- `ntdll!RtlFreeHeap` at `0x18000c5c8`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18000c5aa`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18000c5aa`
- `ntdll!NtQueryInformationToken` at `0x18000c4ab`
- `ntdll!NtQueryInformationToken` at `0x18000c50e`
- `ntdll!NtQueryInformationToken` at `0x18000c572`
- `ntdll!NtQueryInformationToken` at `0x18000c4ab`
- `ntdll!NtQueryInformationToken` at `0x18000c50e`
- `ntdll!NtQueryInformationToken` at `0x18000c572`
- `ntdll!RtlLengthSid` at `0x18000c539`
- `ntdll!RtlLengthSid` at `0x18000c539`
- `ntdll!RtlAllocateHeap` at `0x18000c4dd`
- `ntdll!RtlAllocateHeap` at `0x18000c4dd`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x18000c586`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x18000c586`

## pseudocode

```c
NTSTATUS __fastcall CempGetTokenHostInfo(HANDLE TokenHandle, __int64 a2)
{
  NTSTATUS result; // eax
  void **Heap; // r14
  NTSTATUS v6; // ebx
  void *v7; // rbx
  ULONG v8; // eax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-278h] BYREF
  int v10; // [rsp+34h] [rbp-274h] BYREF
  int v11; // [rsp+38h] [rbp-270h] BYREF
  _BYTE v12[464]; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v13[68]; // [rsp+210h] [rbp-98h] BYREF
  unsigned int TokenInformation; // [rsp+254h] [rbp-54h] BYREF
  unsigned int v15; // [rsp+258h] [rbp-50h]
  __int64 v16; // [rsp+260h] [rbp-48h] BYREF

  v10 = 0;
  TokenInformationLength = 0;
  memset_0(v12, 0, 0x228u);
  v11 = 464;
  result = PsmGetKeyFromToken(TokenHandle, v12, &v11, 0);
  if ( result >= 0 )
  {
    result = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( (int)(result + 0x80000000) < 0 || result == -1073741789 )
    {
      Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      if ( Heap )
      {
        v6 = NtQueryInformationToken(TokenHandle, TokenUser, Heap, TokenInformationLength, &TokenInformationLength);
        if ( v6 >= 0 )
        {
          v7 = *Heap;
          memset_0(v13, 0, sizeof(v13));
          v8 = RtlLengthSid(v7);
          memcpy_0(v13, v7, v8);
          v6 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &TokenInformationLength);
          if ( v6 >= 0 )
          {
            v6 = PsmQueryBackgroundActivationType(TokenHandle, &v10);
            if ( v6 >= 0 )
            {
              v15 = 1 << v10;
              v6 = RtlQueryTokenHostIdAsUlong64(TokenHandle, &v16);
              if ( v6 >= 0 )
              {
                CempHostInfoInitialize(v12, v13, TokenInformation, v15, v16, a2);
                v6 = 0;
              }
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return v6;
      }
      else
      {
        return -1073741801;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c420  push    rbp
0x18000c422  push    rdi
0x18000c423  push    r15
0x18000c425  sub     rsp, 290h
0x18000c42c  mov     rax, cs:__security_cookie
0x18000c433  xor     rax, rsp
0x18000c436  mov     [rsp+2A8h+var_38], rax
0x18000c43e  mov     rbp, rdx
0x18000c441  mov     rdi, rcx
0x18000c444  xor     r15d, r15d
0x18000c447  lea     rcx, [rsp+2A8h+var_268]; void *
0x18000c44c  xor     edx, edx; Val
0x18000c44e  mov     [rsp+2A8h+var_274], r15d
0x18000c453  mov     r8d, 228h; Size
0x18000c459  mov     [rsp+2A8h+TokenInformationLength], r15d
0x18000c45e  call    memset_0
0x18000c463  xor     r9d, r9d
0x18000c466  mov     [rsp+2A8h+var_270], 1D0h
0x18000c46e  lea     r8, [rsp+2A8h+var_270]
0x18000c473  mov     rcx, rdi
0x18000c476  lea     rdx, [rsp+2A8h+var_268]
0x18000c47b  call    cs:__imp_PsmGetKeyFromToken
0x18000c481  test    eax, eax
0x18000c483  js      loc_18000C5E8
0x18000c489  lea     rax, [rsp+2A8h+TokenInformationLength]
0x18000c48e  mov     [rsp+2A8h+var_20], rsi
0x18000c496  mov     esi, 1
0x18000c49b  mov     [rsp+2A8h+ReturnLength], rax; ReturnLength
0x18000c4a0  mov     edx, esi; TokenInformationClass
0x18000c4a2  xor     r9d, r9d; TokenInformationLength
0x18000c4a5  xor     r8d, r8d; TokenInformation
0x18000c4a8  mov     rcx, rdi; TokenHandle
0x18000c4ab  call    cs:__imp_NtQueryInformationToken
0x18000c4b1  mov     edx, 80000000h
0x18000c4b6  lea     ecx, [rax+rdx]
0x18000c4b9  test    edx, ecx
0x18000c4bb  jz      loc_18000C604
0x18000c4c1  mov     rcx, gs:60h
0x18000c4ca  xor     edx, edx; Flags
0x18000c4cc  mov     r8d, [rsp+2A8h+TokenInformationLength]; Size
0x18000c4d1  mov     [rsp+2A8h+var_28], r14
0x18000c4d9  mov     rcx, [rcx+30h]; HeapHandle
0x18000c4dd  call    cs:__imp_RtlAllocateHeap
0x18000c4e3  mov     r14, rax
0x18000c4e6  test    rax, rax
0x18000c4e9  jz      loc_18000C64D
0x18000c4ef  mov     r9d, [rsp+2A8h+TokenInformationLength]; TokenInformationLength
0x18000c4f4  lea     rax, [rsp+2A8h+TokenInformationLength]
0x18000c4f9  mov     r8, r14; TokenInformation
0x18000c4fc  mov     [rsp+2A8h+ReturnLength], rax; ReturnLength
0x18000c501  mov     edx, esi; TokenInformationClass
0x18000c503  mov     [rsp+2A8h+arg_10], rbx
0x18000c50b  mov     rcx, rdi; TokenHandle
0x18000c50e  call    cs:__imp_NtQueryInformationToken
0x18000c514  mov     ebx, eax
0x18000c516  test    eax, eax
0x18000c518  js      loc_18000C5B6
0x18000c51e  mov     rbx, [r14]
0x18000c521  lea     rcx, [rsp+2A8h+var_98]; void *
0x18000c529  xor     edx, edx; Val
0x18000c52b  mov     r8d, 44h ; 'D'; Size
0x18000c531  call    memset_0
0x18000c536  mov     rcx, rbx; Sid
0x18000c539  call    cs:__imp_RtlLengthSid
0x18000c53f  mov     r8d, eax; Size
0x18000c542  mov     rdx, rbx; Src
0x18000c545  lea     rcx, [rsp+2A8h+var_98]; void *
0x18000c54d  call    memcpy_0
0x18000c552  lea     rax, [rsp+2A8h+TokenInformationLength]
0x18000c557  mov     r9d, 4; TokenInformationLength
0x18000c55d  lea     r8, [rsp+2A8h+TokenInformation]; TokenInformation
0x18000c565  mov     [rsp+2A8h+ReturnLength], rax; ReturnLength
0x18000c56a  mov     edx, 0Ch; TokenInformationClass
0x18000c56f  mov     rcx, rdi; TokenHandle
0x18000c572  call    cs:__imp_NtQueryInformationToken
0x18000c578  mov     ebx, eax
0x18000c57a  test    eax, eax
0x18000c57c  js      short loc_18000C5B6
0x18000c57e  lea     rdx, [rsp+2A8h+var_274]
0x18000c583  mov     rcx, rdi
0x18000c586  call    cs:__imp_PsmQueryBackgroundActivationType
0x18000c58c  mov     ebx, eax
0x18000c58e  test    eax, eax
0x18000c590  js      short loc_18000C5B6
0x18000c592  mov     ecx, [rsp+2A8h+var_274]
0x18000c596  lea     rdx, [rsp+2A8h+var_48]
0x18000c59e  shl     esi, cl
0x18000c5a0  mov     rcx, rdi
0x18000c5a3  mov     [rsp+2A8h+var_50], esi
0x18000c5aa  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x18000c5b0  mov     ebx, eax
0x18000c5b2  test    eax, eax
0x18000c5b4  jns     short loc_18000C611
0x18000c5b6  mov     rcx, gs:60h
0x18000c5bf  mov     r8, r14; P
0x18000c5c2  xor     edx, edx; Flags
0x18000c5c4  mov     rcx, [rcx+30h]; HeapHandle
0x18000c5c8  call    cs:__imp_RtlFreeHeap
0x18000c5ce  mov     eax, ebx
0x18000c5d0  mov     rbx, [rsp+2A8h+arg_10]
0x18000c5d8  mov     r14, [rsp+2A8h+var_28]
0x18000c5e0  mov     rsi, [rsp+2A8h+var_20]
0x18000c5e8  mov     rcx, [rsp+2A8h+var_38]
0x18000c5f0  xor     rcx, rsp; StackCookie
0x18000c5f3  call    __security_check_cookie
0x18000c5f8  add     rsp, 290h
0x18000c5ff  pop     r15
0x18000c601  pop     rdi
0x18000c602  pop     rbp
0x18000c603  retn
0x18000c604  cmp     eax, 0C0000023h
0x18000c609  jz      loc_18000C4C1
0x18000c60f  jmp     short loc_18000C5E0
0x18000c611  mov     rax, [rsp+2A8h+var_48]
0x18000c619  lea     rdx, [rsp+2A8h+var_98]
0x18000c621  mov     r9d, [rsp+2A8h+var_50]
0x18000c629  lea     rcx, [rsp+2A8h+var_268]
0x18000c62e  mov     r8d, [rsp+2A8h+TokenInformation]
0x18000c636  mov     [rsp+2A8h+var_280], rbp
0x18000c63b  mov     [rsp+2A8h+ReturnLength], rax
0x18000c640  call    CempHostInfoInitialize
0x18000c645  mov     ebx, r15d
0x18000c648  jmp     loc_18000C5B6
0x18000c64d  mov     eax, 0C0000017h
0x18000c652  jmp     short loc_18000C5D8
```
