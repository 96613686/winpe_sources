# AiCheckForTcbPrivilege(void *,int *)

- ea: `0x18001ac0c`
- end: `0x18001ad55`
- name: `?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z`
- size: `329`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000bb10`
- `0x18001e424`
- `0x1800249f0`
- `0x18002b828`
- `0x180039960`
- `0x180039a20`

## callees

- `0x18001ac0c`
- `0x18001b8d8`
- `0x18001b948`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001acc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001acc2`
- `ntdll!NtQueryInformationToken` at `0x18001acad`
- `ntdll!NtQueryInformationToken` at `0x18001acf7`
- `ntdll!NtQueryInformationToken` at `0x18001acad`
- `ntdll!NtQueryInformationToken` at `0x18001acf7`

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
  if ( dword_18005BE80 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_18005BE80);
    if ( dword_18005BE80 == -1 )
    {
      v10 = 7;
      qword_18005BE88 = 7;
      Init_thread_footer(&dword_18005BE80);
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
        if ( qword_18005BE88 == *(_QWORD *)&v6[3 * i + 1] )
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
0x18001ac0c  mov     [rsp+arg_0], rbx
0x18001ac11  mov     [rsp+arg_18], rsi
0x18001ac16  push    rdi
0x18001ac17  sub     rsp, 30h
0x18001ac1b  mov     r8d, cs:_tls_index
0x18001ac22  mov     rdi, rcx
0x18001ac25  mov     rax, gs:58h
0x18001ac2e  mov     rsi, rdx
0x18001ac31  and     [rsp+38h+TokenInformationLength], 0
0x18001ac36  mov     ecx, 4
0x18001ac3b  mov     rax, [rax+r8*8]
0x18001ac3f  mov     eax, [rcx+rax]
0x18001ac42  cmp     cs:dword_18005BE80, eax
0x18001ac48  jle     short loc_18001AC84
0x18001ac4a  lea     rcx, dword_18005BE80
0x18001ac51  call    _Init_thread_header
0x18001ac56  cmp     cs:dword_18005BE80, 0FFFFFFFFh
0x18001ac5d  jnz     short loc_18001AC84
0x18001ac5f  and     dword ptr [rsp+38h+arg_10+4], 0
0x18001ac64  lea     rcx, dword_18005BE80
0x18001ac6b  mov     dword ptr [rsp+38h+arg_10], 7
0x18001ac73  mov     rax, [rsp+38h+arg_10]
0x18001ac78  mov     cs:qword_18005BE88, rax
0x18001ac7f  call    _Init_thread_footer
0x18001ac84  test    rsi, rsi
0x18001ac87  jnz     short loc_18001AC93
0x18001ac89  mov     eax, 0C000000Dh
0x18001ac8e  jmp     loc_18001AD44
0x18001ac93  and     dword ptr [rsi], 0
0x18001ac96  lea     rax, [rsp+38h+TokenInformationLength]
0x18001ac9b  xor     r9d, r9d; TokenInformationLength
0x18001ac9e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001aca3  xor     r8d, r8d; TokenInformation
0x18001aca6  mov     rcx, rdi; TokenHandle
0x18001aca9  lea     edx, [r9+3]; TokenInformationClass
0x18001acad  call    cs:__imp_NtQueryInformationToken
0x18001acb4  nop     dword ptr [rax+rax+00h]
0x18001acb9  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18001acbd  mov     ecx, 40h ; '@'; uFlags
0x18001acc2  call    cs:__imp_LocalAlloc
0x18001acc9  nop     dword ptr [rax+rax+00h]
0x18001acce  mov     rbx, rax
0x18001acd1  test    rax, rax
0x18001acd4  jnz     short loc_18001ACDD
0x18001acd6  mov     edi, 0C0000017h
0x18001acdb  jmp     short loc_18001AD33
0x18001acdd  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001ace2  lea     rax, [rsp+38h+TokenInformationLength]
0x18001ace7  mov     r8, rbx; TokenInformation
0x18001acea  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001acef  mov     edx, 3; TokenInformationClass
0x18001acf4  mov     rcx, rdi; TokenHandle
0x18001acf7  call    cs:__imp_NtQueryInformationToken
0x18001acfe  nop     dword ptr [rax+rax+00h]
0x18001ad03  mov     edi, eax
0x18001ad05  test    eax, eax
0x18001ad07  js      short loc_18001AD33
0x18001ad09  xor     edx, edx
0x18001ad0b  cmp     edx, [rbx]
0x18001ad0d  jnb     short loc_18001AD33
0x18001ad0f  mov     rax, cs:qword_18005BE88
0x18001ad16  lea     r8, [rdx+rdx*2]
0x18001ad1a  cmp     rax, [rbx+r8*4+4]
0x18001ad1f  jz      short loc_18001AD25
0x18001ad21  inc     edx
0x18001ad23  jmp     short loc_18001AD0B
0x18001ad25  test    byte ptr [rbx+r8*4+0Ch], 3
0x18001ad2b  jz      short loc_18001AD33
0x18001ad2d  mov     dword ptr [rsi], 1
0x18001ad33  mov     rcx, rbx; hMem
0x18001ad36  call    cs:__imp_LocalFree
0x18001ad3d  nop     dword ptr [rax+rax+00h]
0x18001ad42  mov     eax, edi
0x18001ad44  mov     rbx, [rsp+38h+arg_0]
0x18001ad49  mov     rsi, [rsp+38h+arg_18]
0x18001ad4e  add     rsp, 30h
0x18001ad52  pop     rdi
0x18001ad53  retn
```
