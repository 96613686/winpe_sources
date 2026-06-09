# MpCreateMpDlpServiceSID

- ea: `0x140092d90`
- end: `0x140092f7a`
- name: `MpCreateMpDlpServiceSID`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140080070`
- `0x140092d90`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x140092e54`
- `ntoskrnl!RtlInitializeSid` at `0x140092e54`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ec1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092edb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ef5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f0f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f29`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f43`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ec1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092edb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092ef5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f0f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f29`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140092f43`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092dcc`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140092dcc`

## pseudocode

```c
__int64 __fastcall MpCreateMpDlpServiceSID(_QWORD *a1)
{
  ULONG v2; // eax
  void *PoolWithTag; // rax
  void *v4; // rdi
  NTSTATUS v5; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  *a1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v2 = RtlLengthRequiredSid(6u);
  PoolWithTag = (void *)MpAllocatePoolWithTag(1, v2, 1685278797);
  v4 = PoolWithTag;
  if ( PoolWithTag )
  {
    v5 = RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 6u);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      *RtlSubAuthoritySid(v4, 0) = 80;
      *RtlSubAuthoritySid(v4, 1u) = 1643833996;
      *RtlSubAuthoritySid(v4, 2u) = -2044745462;
      *RtlSubAuthoritySid(v4, 3u) = -264584570;
      *RtlSubAuthoritySid(v4, 4u) = 1771290504;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = 1710830024;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v5);
      }
      MpFreeServiceSID(v4);
    }
  }
  else
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140092d90  mov     [rsp+arg_8], rbx
0x140092d95  mov     [rsp+arg_10], rsi
0x140092d9a  push    rdi
0x140092d9b  sub     rsp, 40h
0x140092d9f  mov     rax, cs:__security_cookie
0x140092da6  xor     rax, rsp
0x140092da9  mov     [rsp+48h+var_10], rax
0x140092dae  mov     rsi, rcx
0x140092db1  mov     qword ptr [rcx], 0
0x140092db8  mov     ecx, 6; SubAuthorityCount
0x140092dbd  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x140092dc5  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x140092dcc  call    cs:__imp_RtlLengthRequiredSid
0x140092dd3  nop     dword ptr [rax+rax+00h]
0x140092dd8  mov     edx, eax
0x140092dda  mov     ecx, 1
0x140092ddf  mov     r8d, 6473504Dh
0x140092de5  call    MpAllocatePoolWithTag
0x140092dea  mov     rdi, rax
0x140092ded  test    rax, rax
0x140092df0  jnz     short loc_140092E49
0x140092df2  mov     ebx, 0C000009Ah
0x140092df7  mov     rcx, cs:WPP_GLOBAL_Control
0x140092dfe  lea     rax, WPP_GLOBAL_Control
0x140092e05  cmp     rcx, rax
0x140092e08  jz      loc_140092F5A
0x140092e0e  mov     eax, [rcx+2Ch]
0x140092e11  test    al, 1
0x140092e13  jz      loc_140092F5A
0x140092e19  mov     r9, gs:188h
0x140092e22  lea     edx, [rdi+17h]
0x140092e25  mov     rcx, cs:WPP_GLOBAL_Control
0x140092e2c  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092e33  mov     [rsp+48h+var_28], 0C000009Ah
0x140092e3b  mov     rcx, [rcx+18h]
0x140092e3f  call    WPP_SF_qD
0x140092e44  jmp     loc_140092F5A
0x140092e49  mov     r8b, 6; SubAuthorityCount
0x140092e4c  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x140092e51  mov     rcx, rdi; Sid
0x140092e54  call    cs:__imp_RtlInitializeSid
0x140092e5b  nop     dword ptr [rax+rax+00h]
0x140092e60  mov     ebx, eax
0x140092e62  test    eax, eax
0x140092e64  jns     short loc_140092EB9
0x140092e66  mov     rcx, cs:WPP_GLOBAL_Control
0x140092e6d  lea     rax, WPP_GLOBAL_Control
0x140092e74  cmp     rcx, rax
0x140092e77  jz      short loc_140092EAC
0x140092e79  mov     eax, [rcx+2Ch]
0x140092e7c  test    al, 1
0x140092e7e  jz      short loc_140092EAC
0x140092e80  lfence
0x140092e83  mov     r9, gs:188h
0x140092e8c  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140092e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140092e9a  mov     edx, 18h
0x140092e9f  mov     [rsp+48h+var_28], ebx
0x140092ea3  mov     rcx, [rcx+18h]
0x140092ea7  call    WPP_SF_qD
0x140092eac  mov     rcx, rdi
0x140092eaf  call    MpFreeServiceSID
0x140092eb4  jmp     loc_140092F5A
0x140092eb9  lfence
0x140092ebc  xor     edx, edx; SubAuthority
0x140092ebe  mov     rcx, rdi; Sid
0x140092ec1  call    cs:__imp_RtlSubAuthoritySid
0x140092ec8  nop     dword ptr [rax+rax+00h]
0x140092ecd  mov     edx, 1; SubAuthority
0x140092ed2  mov     rcx, rdi; Sid
0x140092ed5  mov     dword ptr [rax], 50h ; 'P'
0x140092edb  call    cs:__imp_RtlSubAuthoritySid
0x140092ee2  nop     dword ptr [rax+rax+00h]
0x140092ee7  mov     edx, 2; SubAuthority
0x140092eec  mov     rcx, rdi; Sid
0x140092eef  mov     dword ptr [rax], 61FAEA8Ch
0x140092ef5  call    cs:__imp_RtlSubAuthoritySid
0x140092efc  nop     dword ptr [rax+rax+00h]
0x140092f01  mov     edx, 3; SubAuthority
0x140092f06  mov     rcx, rdi; Sid
0x140092f09  mov     dword ptr [rax], 861FA90Ah
0x140092f0f  call    cs:__imp_RtlSubAuthoritySid
0x140092f16  nop     dword ptr [rax+rax+00h]
0x140092f1b  mov     edx, 4; SubAuthority
0x140092f20  mov     rcx, rdi; Sid
0x140092f23  mov     dword ptr [rax], 0F03AC286h
0x140092f29  call    cs:__imp_RtlSubAuthoritySid
0x140092f30  nop     dword ptr [rax+rax+00h]
0x140092f35  mov     edx, 5; SubAuthority
0x140092f3a  mov     rcx, rdi; Sid
0x140092f3d  mov     dword ptr [rax], 6993BF88h
0x140092f43  call    cs:__imp_RtlSubAuthoritySid
0x140092f4a  nop     dword ptr [rax+rax+00h]
0x140092f4f  xor     ebx, ebx
0x140092f51  mov     dword ptr [rax], 65F931C8h
0x140092f57  mov     [rsi], rdi
0x140092f5a  mov     eax, ebx
0x140092f5c  mov     rcx, [rsp+48h+var_10]
0x140092f61  xor     rcx, rsp; StackCookie
0x140092f64  call    __security_check_cookie
0x140092f69  mov     rbx, [rsp+48h+arg_8]
0x140092f6e  mov     rsi, [rsp+48h+arg_10]
0x140092f73  add     rsp, 40h
0x140092f77  pop     rdi
0x140092f78  retn
```
