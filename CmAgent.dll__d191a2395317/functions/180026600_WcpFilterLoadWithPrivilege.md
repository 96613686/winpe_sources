# WcpFilterLoadWithPrivilege

- ea: `0x180026600`
- end: `0x180026766`
- name: `WcpFilterLoadWithPrivilege`
- size: `358`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026284`

## callees

- `0x18000edcc`
- `0x180025d04`
- `0x180026600`
- `0x180026828`

## import_xrefs

- `ntdll!NtClose` at `0x180026713`
- `ntdll!NtClose` at `0x180026713`
- `ntdll!RtlImpersonateSelf` at `0x180026686`
- `ntdll!RtlImpersonateSelf` at `0x180026686`
- `ntdll!NtOpenThreadToken` at `0x18002665c`
- `ntdll!NtOpenThreadToken` at `0x1800266a8`
- `ntdll!NtOpenThreadToken` at `0x18002665c`
- `ntdll!NtOpenThreadToken` at `0x1800266a8`
- `ntdll!NtSetInformationThread` at `0x18002673e`
- `ntdll!NtSetInformationThread` at `0x18002673e`

## pseudocode

```c
__int64 __fastcall WcpFilterLoadWithPrivilege(void *Src)
{
  int v1; // edi
  int v3; // eax
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  TokenHandle = (void *)-1LL;
  LODWORD(ThreadInformation) = 0;
  v3 = NtFilterLoad(Src);
  v4 = v3;
  if ( v3 < 0 && (v3 == -2147023582 || v3 == (unsigned int)FilterHResultFromNtStatus(3221225569LL)) )
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
    if ( v5
      && (v5 != -1073741700
       || (v5 = RtlImpersonateSelf(SecurityImpersonation), v5 < 0)
       || (v1 = 1, (v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle)) != 0)) )
    {
      v4 = FilterHResultFromNtStatus((unsigned int)v5);
    }
    else
    {
      v6 = WcpSetPrivilege(TokenHandle, 10, 1, &ThreadInformation);
      if ( v6 )
        v7 = FilterHResultFromNtStatus(v6);
      else
        v7 = NtFilterLoad(Src);
      v4 = v7;
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
  return v4;
}

```

## disassembly

```asm
0x180026600  mov     [rsp+arg_0], rbx
0x180026605  push    rsi
0x180026606  push    rdi
0x180026607  push    r15
0x180026609  sub     rsp, 20h
0x18002660d  xor     edi, edi
0x18002660f  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180026618  mov     dword ptr [rsp+38h+ThreadInformation], edi
0x18002661c  mov     rsi, rcx
0x18002661f  call    NtFilterLoad
0x180026624  lea     r15, [rdi-2]
0x180026628  mov     ebx, eax
0x18002662a  test    eax, eax
0x18002662c  jns     loc_180026708
0x180026632  cmp     eax, 80070522h
0x180026637  jz      short loc_18002664B
0x180026639  mov     ecx, 0C0000061h
0x18002663e  call    FilterHResultFromNtStatus
0x180026643  cmp     ebx, eax
0x180026645  jnz     loc_180026708
0x18002664b  xor     r8d, r8d; OpenAsSelf
0x18002664e  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180026653  mov     rcx, r15; ThreadHandle
0x180026656  lea     ebx, [r8+28h]
0x18002665a  mov     edx, ebx; DesiredAccess
0x18002665c  call    cs:__imp_NtOpenThreadToken
0x180026663  nop     dword ptr [rax+rax+00h]
0x180026668  test    eax, eax
0x18002666a  jz      short loc_1800266B8
0x18002666c  cmp     eax, 0C000007Ch
0x180026671  jz      short loc_180026681
0x180026673  mov     ecx, eax
0x180026675  call    FilterHResultFromNtStatus
0x18002667a  mov     ebx, eax
0x18002667c  jmp     loc_180026708
0x180026681  mov     ecx, 2; ImpersonationLevel
0x180026686  call    cs:__imp_RtlImpersonateSelf
0x18002668d  nop     dword ptr [rax+rax+00h]
0x180026692  test    eax, eax
0x180026694  js      short loc_180026673
0x180026696  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18002669b  xor     r8d, r8d; OpenAsSelf
0x18002669e  mov     edx, ebx; DesiredAccess
0x1800266a0  mov     rcx, r15; ThreadHandle
0x1800266a3  mov     edi, 1
0x1800266a8  call    cs:__imp_NtOpenThreadToken
0x1800266af  nop     dword ptr [rax+rax+00h]
0x1800266b4  test    eax, eax
0x1800266b6  jnz     short loc_180026673
0x1800266b8  mov     rcx, [rsp+38h+TokenHandle]
0x1800266bd  lea     r9, [rsp+38h+ThreadInformation]
0x1800266c2  mov     edx, 0Ah
0x1800266c7  lea     r8d, [rdx-9]
0x1800266cb  call    WcpSetPrivilege
0x1800266d0  test    eax, eax
0x1800266d2  jz      short loc_1800266DD
0x1800266d4  mov     ecx, eax
0x1800266d6  call    FilterHResultFromNtStatus
0x1800266db  jmp     short loc_1800266E5
0x1800266dd  mov     rcx, rsi; Src
0x1800266e0  call    NtFilterLoad
0x1800266e5  mov     ebx, eax
0x1800266e7  test    edi, edi
0x1800266e9  jnz     short loc_180026708
0x1800266eb  cmp     dword ptr [rsp+38h+ThreadInformation], edi
0x1800266ef  jz      short loc_180026708
0x1800266f1  mov     rcx, [rsp+38h+TokenHandle]
0x1800266f6  lea     edx, [rdi+0Ah]
0x1800266f9  xor     r9d, r9d
0x1800266fc  xor     r8d, r8d
0x1800266ff  call    WcpSetPrivilege
0x180026704  test    eax, eax
0x180026706  jnz     short loc_18002674E
0x180026708  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18002670d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026711  jz      short loc_18002671F
0x180026713  call    cs:__imp_NtClose
0x18002671a  nop     dword ptr [rax+rax+00h]
0x18002671f  test    edi, edi
0x180026721  jz      short loc_180026755
0x180026723  mov     r9d, 8; ThreadInformationLength
0x180026729  mov     [rsp+38h+ThreadInformation], 0
0x180026732  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180026737  mov     rcx, r15; ThreadHandle
0x18002673a  lea     edx, [r9-3]; ThreadInformationClass
0x18002673e  call    cs:__imp_NtSetInformationThread
0x180026745  nop     dword ptr [rax+rax+00h]
0x18002674a  test    eax, eax
0x18002674c  jz      short loc_180026755
0x18002674e  mov     ecx, 7
0x180026753  int     29h; Win8: RtlFailFast(ecx)
0x180026755  mov     eax, ebx
0x180026757  mov     rbx, [rsp+38h+arg_0]
0x18002675c  add     rsp, 20h
0x180026760  pop     r15
0x180026762  pop     rdi
0x180026763  pop     rsi
0x180026764  retn
```
