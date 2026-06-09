# AiCheckForTcbPrivilege(void *,int *)

- ea: `0x18001afdc`
- end: `0x18001b125`
- name: `?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z`
- size: `329`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000bb10`
- `0x18001e804`
- `0x1800230e0`
- `0x18002a2a8`
- `0x18003a8e0`
- `0x18003a9a0`

## callees

- `0x18001afdc`
- `0x18001bca8`
- `0x18001bd18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b106`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b092`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b092`
- `ntdll!NtQueryInformationToken` at `0x18001b07d`
- `ntdll!NtQueryInformationToken` at `0x18001b0c7`
- `ntdll!NtQueryInformationToken` at `0x18001b07d`
- `ntdll!NtQueryInformationToken` at `0x18001b0c7`

## pseudocode

```c
__int64 __fastcall AiCheckForTcbPrivilege(HANDLE TokenHandle, int *a2)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  _DWORD *v6; // rbx
  NTSTATUS v7; // edi
  __int64 i; // rdx
  ULONG TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+50h] [rbp+18h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  TokenInformationLength = 0;
  if ( dword_18005DE48 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_18005DE48);
    if ( dword_18005DE48 == -1 )
    {
      v10 = 7;
      qword_18005DE50 = 7;
      Init_thread_footer(&dword_18005DE48);
    }
  }
  if ( !a2 )
    return 3221225485LL;
  *a2 = 0;
  NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength);
  v6 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v6 )
  {
    v7 = NtQueryInformationToken(TokenHandle, TokenPrivileges, v6, TokenInformationLength, &TokenInformationLength);
    if ( v7 >= 0 )
    {
      for ( i = 0; (unsigned int)i < *v6; i = (unsigned int)(i + 1) )
      {
        if ( qword_18005DE50 == *(_QWORD *)&v6[3 * i + 1] )
        {
          if ( (v6[3 * i + 3] & 3) != 0 )
            *a2 = 1;
          break;
        }
      }
    }
  }
  else
  {
    v7 = -1073741801;
  }
  LocalFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001afdc  mov     [rsp+arg_0], rbx
0x18001afe1  mov     [rsp+arg_18], rsi
0x18001afe6  push    rdi
0x18001afe7  sub     rsp, 30h
0x18001afeb  mov     r8d, cs:_tls_index
0x18001aff2  mov     rdi, rcx
0x18001aff5  mov     rax, gs:58h
0x18001affe  mov     rsi, rdx
0x18001b001  and     [rsp+38h+TokenInformationLength], 0
0x18001b006  mov     ecx, 4
0x18001b00b  mov     rax, [rax+r8*8]
0x18001b00f  mov     eax, [rcx+rax]
0x18001b012  cmp     cs:dword_18005DE48, eax
0x18001b018  jle     short loc_18001B054
0x18001b01a  lea     rcx, dword_18005DE48
0x18001b021  call    _Init_thread_header
0x18001b026  cmp     cs:dword_18005DE48, 0FFFFFFFFh
0x18001b02d  jnz     short loc_18001B054
0x18001b02f  and     dword ptr [rsp+38h+arg_10+4], 0
0x18001b034  lea     rcx, dword_18005DE48
0x18001b03b  mov     dword ptr [rsp+38h+arg_10], 7
0x18001b043  mov     rax, [rsp+38h+arg_10]
0x18001b048  mov     cs:qword_18005DE50, rax
0x18001b04f  call    _Init_thread_footer
0x18001b054  test    rsi, rsi
0x18001b057  jnz     short loc_18001B063
0x18001b059  mov     eax, 0C000000Dh
0x18001b05e  jmp     loc_18001B114
0x18001b063  and     dword ptr [rsi], 0
0x18001b066  lea     rax, [rsp+38h+TokenInformationLength]
0x18001b06b  xor     r9d, r9d; TokenInformationLength
0x18001b06e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001b073  xor     r8d, r8d; TokenInformation
0x18001b076  mov     rcx, rdi; TokenHandle
0x18001b079  lea     edx, [r9+3]; TokenInformationClass
0x18001b07d  call    cs:__imp_NtQueryInformationToken
0x18001b084  nop     dword ptr [rax+rax+00h]
0x18001b089  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18001b08d  mov     ecx, 40h ; '@'; uFlags
0x18001b092  call    cs:__imp_LocalAlloc
0x18001b099  nop     dword ptr [rax+rax+00h]
0x18001b09e  mov     rbx, rax
0x18001b0a1  test    rax, rax
0x18001b0a4  jnz     short loc_18001B0AD
0x18001b0a6  mov     edi, 0C0000017h
0x18001b0ab  jmp     short loc_18001B103
0x18001b0ad  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001b0b2  lea     rax, [rsp+38h+TokenInformationLength]
0x18001b0b7  mov     r8, rbx; TokenInformation
0x18001b0ba  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001b0bf  mov     edx, 3; TokenInformationClass
0x18001b0c4  mov     rcx, rdi; TokenHandle
0x18001b0c7  call    cs:__imp_NtQueryInformationToken
0x18001b0ce  nop     dword ptr [rax+rax+00h]
0x18001b0d3  mov     edi, eax
0x18001b0d5  test    eax, eax
0x18001b0d7  js      short loc_18001B103
0x18001b0d9  xor     edx, edx
0x18001b0db  cmp     edx, [rbx]
0x18001b0dd  jnb     short loc_18001B103
0x18001b0df  mov     rax, cs:qword_18005DE50
0x18001b0e6  lea     r8, [rdx+rdx*2]
0x18001b0ea  cmp     rax, [rbx+r8*4+4]
0x18001b0ef  jz      short loc_18001B0F5
0x18001b0f1  inc     edx
0x18001b0f3  jmp     short loc_18001B0DB
0x18001b0f5  test    byte ptr [rbx+r8*4+0Ch], 3
0x18001b0fb  jz      short loc_18001B103
0x18001b0fd  mov     dword ptr [rsi], 1
0x18001b103  mov     rcx, rbx; hMem
0x18001b106  call    cs:__imp_LocalFree
0x18001b10d  nop     dword ptr [rax+rax+00h]
0x18001b112  mov     eax, edi
0x18001b114  mov     rbx, [rsp+38h+arg_0]
0x18001b119  mov     rsi, [rsp+38h+arg_18]
0x18001b11e  add     rsp, 30h
0x18001b122  pop     rdi
0x18001b123  retn
```
