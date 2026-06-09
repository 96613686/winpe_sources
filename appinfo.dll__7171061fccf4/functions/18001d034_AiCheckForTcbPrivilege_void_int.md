# AiCheckForTcbPrivilege(void *,int *)

- ea: `0x18001d034`
- end: `0x18001d166`
- name: `?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z`
- size: `306`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b510`
- `0x180021968`
- `0x180026ba0`
- `0x18002ed98`
- `0x18003cd80`
- `0x18003ce30`

## callees

- `0x18001d034`
- `0x18001efcc`
- `0x18001f03c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d14e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d14e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0e6`
- `ntdll!NtQueryInformationToken` at `0x18001d0d7`
- `ntdll!NtQueryInformationToken` at `0x18001d115`
- `ntdll!NtQueryInformationToken` at `0x18001d0d7`
- `ntdll!NtQueryInformationToken` at `0x18001d115`

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
  if ( dword_180060FD0 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_180060FD0);
    if ( dword_180060FD0 == -1 )
    {
      v10 = 7;
      qword_180060FD8 = 7;
      Init_thread_footer(&dword_180060FD0);
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
        if ( qword_180060FD8 == *(_QWORD *)&v6[3 * i + 1] )
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
0x18001d034  mov     [rsp+arg_0], rbx
0x18001d039  mov     [rsp+arg_18], rsi
0x18001d03e  push    rdi
0x18001d03f  sub     rsp, 30h
0x18001d043  mov     r8d, cs:_tls_index
0x18001d04a  mov     rdi, rcx
0x18001d04d  mov     rax, gs:58h
0x18001d056  mov     rsi, rdx
0x18001d059  mov     ecx, 4
0x18001d05e  mov     [rsp+38h+TokenInformationLength], 0
0x18001d066  mov     rax, [rax+r8*8]
0x18001d06a  mov     eax, [rcx+rax]
0x18001d06d  cmp     cs:dword_180060FD0, eax
0x18001d073  jle     short loc_18001D0AB
0x18001d075  lea     rcx, dword_180060FD0
0x18001d07c  call    _Init_thread_header
0x18001d081  cmp     cs:dword_180060FD0, 0FFFFFFFFh
0x18001d088  jnz     short loc_18001D0AB
0x18001d08a  mov     [rsp+38h+arg_10], 7
0x18001d093  lea     rcx, dword_180060FD0
0x18001d09a  mov     rax, [rsp+38h+arg_10]
0x18001d09f  mov     cs:qword_180060FD8, rax
0x18001d0a6  call    _Init_thread_footer
0x18001d0ab  test    rsi, rsi
0x18001d0ae  jnz     short loc_18001D0BA
0x18001d0b0  mov     eax, 0C000000Dh
0x18001d0b5  jmp     loc_18001D156
0x18001d0ba  xor     r9d, r9d; TokenInformationLength
0x18001d0bd  mov     dword ptr [rsi], 0
0x18001d0c3  lea     rax, [rsp+38h+TokenInformationLength]
0x18001d0c8  xor     r8d, r8d; TokenInformation
0x18001d0cb  mov     rcx, rdi; TokenHandle
0x18001d0ce  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001d0d3  lea     edx, [r9+3]; TokenInformationClass
0x18001d0d7  call    cs:__imp_NtQueryInformationToken
0x18001d0dd  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18001d0e1  mov     ecx, 40h ; '@'; uFlags
0x18001d0e6  call    cs:__imp_LocalAlloc
0x18001d0ec  mov     rbx, rax
0x18001d0ef  test    rax, rax
0x18001d0f2  jnz     short loc_18001D0FB
0x18001d0f4  mov     edi, 0C0000017h
0x18001d0f9  jmp     short loc_18001D14B
0x18001d0fb  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001d100  lea     rax, [rsp+38h+TokenInformationLength]
0x18001d105  mov     r8, rbx; TokenInformation
0x18001d108  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001d10d  mov     edx, 3; TokenInformationClass
0x18001d112  mov     rcx, rdi; TokenHandle
0x18001d115  call    cs:__imp_NtQueryInformationToken
0x18001d11b  mov     edi, eax
0x18001d11d  test    eax, eax
0x18001d11f  js      short loc_18001D14B
0x18001d121  xor     edx, edx
0x18001d123  cmp     edx, [rbx]
0x18001d125  jnb     short loc_18001D14B
0x18001d127  mov     rax, cs:qword_180060FD8
0x18001d12e  lea     r8, [rdx+rdx*2]
0x18001d132  cmp     rax, [rbx+r8*4+4]
0x18001d137  jz      short loc_18001D13D
0x18001d139  inc     edx
0x18001d13b  jmp     short loc_18001D123
0x18001d13d  test    byte ptr [rbx+r8*4+0Ch], 3
0x18001d143  jz      short loc_18001D14B
0x18001d145  mov     dword ptr [rsi], 1
0x18001d14b  mov     rcx, rbx; hMem
0x18001d14e  call    cs:__imp_LocalFree
0x18001d154  mov     eax, edi
0x18001d156  mov     rbx, [rsp+38h+arg_0]
0x18001d15b  mov     rsi, [rsp+38h+arg_18]
0x18001d160  add     rsp, 30h
0x18001d164  pop     rdi
0x18001d165  retn
```
