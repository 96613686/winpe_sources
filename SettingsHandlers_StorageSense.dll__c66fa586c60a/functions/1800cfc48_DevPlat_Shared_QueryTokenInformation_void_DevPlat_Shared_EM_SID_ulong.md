# DevPlat::Shared::QueryTokenInformation(void *,DevPlat::Shared::_EM_SID *,ulong *)

- ea: `0x1800cfc48`
- end: `0x1800cfd10`
- name: `?QueryTokenInformation@Shared@DevPlat@@YAJPEAXPEAU_EM_SID@12@PEAK@Z`
- size: `200`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID Sid, struct DevPlat::Shared::_EM_SID *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800cfb68`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x1800cfc48`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800cfccf`
- `ntdll!RtlCopySid` at `0x1800cfccf`
- `ntdll!NtQueryInformationToken` at `0x1800cfcb2`
- `ntdll!NtQueryInformationToken` at `0x1800cfcb2`
- `ntdll!RtlValidSid` at `0x1800cfcdc`
- `ntdll!RtlValidSid` at `0x1800cfcdc`

## pseudocode

```c
int __fastcall DevPlat::Shared::QueryTokenInformation(
        HANDLE TokenHandle,
        PSID Sid,
        struct DevPlat::Shared::_EM_SID *a3,
        unsigned int *a4)
{
  NTSTATUS InformationToken; // eax
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-78h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  ReturnLength[0] = 0;
  memset_0(TokenInformation, 0, 0x48u);
  if ( !TokenHandle )
    return -2147024809;
  if ( !Sid )
    return 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x48u, ReturnLength);
  if ( InformationToken < 0 )
    return InformationToken | 0x10000000;
  InformationToken = RtlCopySid(0x44u, Sid, TokenInformation[0]);
  if ( InformationToken < 0 )
    return InformationToken | 0x10000000;
  if ( RtlValidSid(Sid) )
    return 0;
  else
    return -805306248;
}

```

## disassembly

```asm
0x1800cfc48  mov     [rsp+arg_10], rbx
0x1800cfc4d  push    rdi
0x1800cfc4e  sub     rsp, 0A0h
0x1800cfc55  mov     rax, cs:__security_cookie
0x1800cfc5c  xor     rax, rsp
0x1800cfc5f  mov     [rsp+0A8h+var_18], rax
0x1800cfc67  mov     rbx, rdx
0x1800cfc6a  mov     [rsp+0A8h+var_78], 0
0x1800cfc72  xor     edx, edx; Val
0x1800cfc74  mov     rdi, rcx
0x1800cfc77  lea     rcx, [rsp+0A8h+TokenInformation]; void *
0x1800cfc7c  lea     r8d, [rdx+48h]; Size
0x1800cfc80  call    memset_0
0x1800cfc85  test    rdi, rdi
0x1800cfc88  jnz     short loc_1800CFC91
0x1800cfc8a  mov     eax, 80070057h
0x1800cfc8f  jmp     short loc_1800CFCEF
0x1800cfc91  test    rbx, rbx
0x1800cfc94  jz      short loc_1800CFCED
0x1800cfc96  mov     r9d, 48h ; 'H'; TokenInformationLength
0x1800cfc9c  lea     rax, [rsp+0A8h+var_78]
0x1800cfca1  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x1800cfca6  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x1800cfcab  mov     rcx, rdi; TokenHandle
0x1800cfcae  lea     edx, [r9-47h]; TokenInformationClass
0x1800cfcb2  call    cs:__imp_NtQueryInformationToken
0x1800cfcb8  test    eax, eax
0x1800cfcba  jns     short loc_1800CFCC2
0x1800cfcbc  bts     eax, 1Ch
0x1800cfcc0  jmp     short loc_1800CFCEF
0x1800cfcc2  mov     r8, [rsp+0A8h+TokenInformation]; SourceSid
0x1800cfcc7  mov     rdx, rbx; DestinationSid
0x1800cfcca  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1800cfccf  call    cs:__imp_RtlCopySid
0x1800cfcd5  test    eax, eax
0x1800cfcd7  js      short loc_1800CFCBC
0x1800cfcd9  mov     rcx, rbx; Sid
0x1800cfcdc  call    cs:__imp_RtlValidSid
0x1800cfce2  test    al, al
0x1800cfce4  jnz     short loc_1800CFCED
0x1800cfce6  mov     eax, 0D0000078h
0x1800cfceb  jmp     short loc_1800CFCEF
0x1800cfced  xor     eax, eax
0x1800cfcef  mov     rcx, [rsp+0A8h+var_18]
0x1800cfcf7  xor     rcx, rsp; StackCookie
0x1800cfcfa  call    __security_check_cookie
0x1800cfcff  mov     rbx, [rsp+0A8h+arg_10]
0x1800cfd07  add     rsp, 0A0h
0x1800cfd0e  pop     rdi
0x1800cfd0f  retn
```
