# WcpFilterLoadWithPrivilege

- ea: `0x18018f918`
- end: `0x18018fa81`
- name: `WcpFilterLoadWithPrivilege`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018f5b8`

## callees

- `0x18018eca8`
- `0x18018f090`
- `0x18018f918`
- `0x18018fb44`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18018f977`
- `ntdll!NtOpenThreadToken` at `0x18018f9c3`
- `ntdll!NtOpenThreadToken` at `0x18018f977`
- `ntdll!NtOpenThreadToken` at `0x18018f9c3`
- `ntdll!RtlImpersonateSelf` at `0x18018f9a1`
- `ntdll!RtlImpersonateSelf` at `0x18018f9a1`
- `ntdll!NtSetInformationThread` at `0x18018fa56`
- `ntdll!NtSetInformationThread` at `0x18018fa56`
- `ntdll!NtClose` at `0x18018fa2b`
- `ntdll!NtClose` at `0x18018fa2b`

## pseudocode

```c
__int64 __fastcall WcpFilterLoadWithPrivilege(__int64 a1)
{
  int v1; // edi
  int v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 ThreadInformation; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(ThreadInformation) = HIDWORD(a1);
  v1 = 0;
  TokenHandle = (void *)-1LL;
  LODWORD(ThreadInformation) = 0;
  v2 = NtFilterLoad();
  v3 = v2;
  if ( v2 < 0 && (v2 == -2147023582 || v2 == (unsigned int)FilterHResultFromNtStatus(3221225569LL)) )
  {
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
    if ( v4
      && (v4 != -1073741700
       || (v4 = RtlImpersonateSelf(SecurityImpersonation), v4 < 0)
       || (v1 = 1, (v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle)) != 0)) )
    {
      v3 = FilterHResultFromNtStatus((unsigned int)v4);
    }
    else
    {
      v5 = WcpSetPrivilege(TokenHandle, 10, 1, &ThreadInformation);
      if ( v5 )
        v6 = FilterHResultFromNtStatus(v5);
      else
        v6 = NtFilterLoad();
      v3 = v6;
      if ( !v1 && (_DWORD)ThreadInformation && (unsigned int)WcpSetPrivilege(TokenHandle, 10, 0, 0) )
        goto LABEL_19;
    }
  }
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( v1 )
  {
    ThreadInformation = 0;
    if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) )
LABEL_19:
      __fastfail(7u);
  }
  return v3;
}

```

## disassembly

```asm
0x18018f918  mov     rax, rsp
0x18018f91b  mov     [rax+18h], rbx
0x18018f91f  mov     [rax+20h], rdi
0x18018f923  mov     [rax+8], rcx
0x18018f927  push    r14
0x18018f929  sub     rsp, 20h
0x18018f92d  xor     edi, edi
0x18018f92f  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x18018f937  mov     [rax+8], edi
0x18018f93a  call    NtFilterLoad
0x18018f93f  lea     r14, [rdi-2]
0x18018f943  mov     ebx, eax
0x18018f945  test    eax, eax
0x18018f947  jns     loc_18018FA20
0x18018f94d  cmp     eax, 80070522h
0x18018f952  jz      short loc_18018F966
0x18018f954  mov     ecx, 0C0000061h
0x18018f959  call    FilterHResultFromNtStatus
0x18018f95e  cmp     ebx, eax
0x18018f960  jnz     loc_18018FA20
0x18018f966  xor     r8d, r8d; OpenAsSelf
0x18018f969  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18018f96e  mov     rcx, r14; ThreadHandle
0x18018f971  lea     ebx, [r8+28h]
0x18018f975  mov     edx, ebx; DesiredAccess
0x18018f977  call    cs:__imp_NtOpenThreadToken
0x18018f97e  nop     dword ptr [rax+rax+00h]
0x18018f983  test    eax, eax
0x18018f985  jz      short loc_18018F9D3
0x18018f987  cmp     eax, 0C000007Ch
0x18018f98c  jz      short loc_18018F99C
0x18018f98e  mov     ecx, eax
0x18018f990  call    FilterHResultFromNtStatus
0x18018f995  mov     ebx, eax
0x18018f997  jmp     loc_18018FA20
0x18018f99c  mov     ecx, 2; ImpersonationLevel
0x18018f9a1  call    cs:__imp_RtlImpersonateSelf
0x18018f9a8  nop     dword ptr [rax+rax+00h]
0x18018f9ad  test    eax, eax
0x18018f9af  js      short loc_18018F98E
0x18018f9b1  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18018f9b6  xor     r8d, r8d; OpenAsSelf
0x18018f9b9  mov     edx, ebx; DesiredAccess
0x18018f9bb  mov     rcx, r14; ThreadHandle
0x18018f9be  mov     edi, 1
0x18018f9c3  call    cs:__imp_NtOpenThreadToken
0x18018f9ca  nop     dword ptr [rax+rax+00h]
0x18018f9cf  test    eax, eax
0x18018f9d1  jnz     short loc_18018F98E
0x18018f9d3  mov     rcx, [rsp+28h+TokenHandle]
0x18018f9d8  lea     r9, [rsp+28h+ThreadInformation]
0x18018f9dd  mov     edx, 0Ah
0x18018f9e2  lea     r8d, [rdx-9]
0x18018f9e6  call    WcpSetPrivilege
0x18018f9eb  test    eax, eax
0x18018f9ed  jz      short loc_18018F9F8
0x18018f9ef  mov     ecx, eax
0x18018f9f1  call    FilterHResultFromNtStatus
0x18018f9f6  jmp     short loc_18018F9FD
0x18018f9f8  call    NtFilterLoad
0x18018f9fd  mov     ebx, eax
0x18018f9ff  test    edi, edi
0x18018fa01  jnz     short loc_18018FA20
0x18018fa03  cmp     dword ptr [rsp+28h+ThreadInformation], edi
0x18018fa07  jz      short loc_18018FA20
0x18018fa09  mov     rcx, [rsp+28h+TokenHandle]
0x18018fa0e  lea     edx, [rdi+0Ah]
0x18018fa11  xor     r9d, r9d
0x18018fa14  xor     r8d, r8d
0x18018fa17  call    WcpSetPrivilege
0x18018fa1c  test    eax, eax
0x18018fa1e  jnz     short loc_18018FA66
0x18018fa20  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x18018fa25  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018fa29  jz      short loc_18018FA37
0x18018fa2b  call    cs:__imp_NtClose
0x18018fa32  nop     dword ptr [rax+rax+00h]
0x18018fa37  test    edi, edi
0x18018fa39  jz      short loc_18018FA6D
0x18018fa3b  mov     r9d, 8; ThreadInformationLength
0x18018fa41  mov     [rsp+28h+ThreadInformation], 0
0x18018fa4a  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18018fa4f  mov     rcx, r14; ThreadHandle
0x18018fa52  lea     edx, [r9-3]; ThreadInformationClass
0x18018fa56  call    cs:__imp_NtSetInformationThread
0x18018fa5d  nop     dword ptr [rax+rax+00h]
0x18018fa62  test    eax, eax
0x18018fa64  jz      short loc_18018FA6D
0x18018fa66  mov     ecx, 7
0x18018fa6b  int     29h; Win8: RtlFailFast(ecx)
0x18018fa6d  mov     rdi, [rsp+28h+arg_18]
0x18018fa72  mov     eax, ebx
0x18018fa74  mov     rbx, [rsp+28h+arg_10]
0x18018fa79  add     rsp, 20h
0x18018fa7d  pop     r14
0x18018fa7f  retn
```
