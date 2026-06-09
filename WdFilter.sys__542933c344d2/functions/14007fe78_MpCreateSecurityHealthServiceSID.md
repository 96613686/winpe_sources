# MpCreateSecurityHealthServiceSID

- ea: `0x14007fe78`
- end: `0x14008006e`
- name: `MpCreateSecurityHealthServiceSID`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400907b8`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x14007fe78`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14007ff3c`
- `ntoskrnl!RtlInitializeSid` at `0x14007ff3c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffb5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffcf`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffe9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080003`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14008001d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080037`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffb5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffcf`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007ffe9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080003`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14008001d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140080037`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14007feb4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14007feb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ff9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ff9c`

## pseudocode

```c
__int64 __fastcall MpCreateSecurityHealthServiceSID(_QWORD *a1)
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
      *RtlSubAuthoritySid(v4, 1u) = 259296475;
      *RtlSubAuthoritySid(v4, 2u) = -210537790;
      *RtlSubAuthoritySid(v4, 3u) = 1152984619;
      *RtlSubAuthoritySid(v4, 4u) = 38739575;
      v5 = 0;
      *RtlSubAuthoritySid(v4, 5u) = 565535606;
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v5);
      }
      ExFreePoolWithTag(v4, 0x6473504Du);
    }
  }
  else
  {
    v5 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14007fe78  mov     [rsp+arg_8], rbx
0x14007fe7d  mov     [rsp+arg_10], rsi
0x14007fe82  push    rdi
0x14007fe83  sub     rsp, 40h
0x14007fe87  mov     rax, cs:__security_cookie
0x14007fe8e  xor     rax, rsp
0x14007fe91  mov     [rsp+48h+var_10], rax
0x14007fe96  mov     rsi, rcx
0x14007fe99  mov     qword ptr [rcx], 0
0x14007fea0  mov     ecx, 6; SubAuthorityCount
0x14007fea5  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x14007fead  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x14007feb4  call    cs:__imp_RtlLengthRequiredSid
0x14007febb  nop     dword ptr [rax+rax+00h]
0x14007fec0  mov     edx, eax
0x14007fec2  mov     ecx, 1
0x14007fec7  mov     r8d, 6473504Dh
0x14007fecd  call    MpAllocatePoolWithTag
0x14007fed2  mov     rdi, rax
0x14007fed5  test    rax, rax
0x14007fed8  jnz     short loc_14007FF31
0x14007feda  mov     ebx, 0C000009Ah
0x14007fedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fee6  lea     rax, WPP_GLOBAL_Control
0x14007feed  cmp     rcx, rax
0x14007fef0  jz      loc_14008004E
0x14007fef6  mov     eax, [rcx+2Ch]
0x14007fef9  test    al, 1
0x14007fefb  jz      loc_14008004E
0x14007ff01  mov     r9, gs:188h
0x14007ff0a  lea     edx, [rdi+13h]
0x14007ff0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff14  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14007ff1b  mov     [rsp+48h+var_28], 0C000009Ah
0x14007ff23  mov     rcx, [rcx+18h]
0x14007ff27  call    WPP_SF_qD
0x14007ff2c  jmp     loc_14008004E
0x14007ff31  mov     r8b, 6; SubAuthorityCount
0x14007ff34  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x14007ff39  mov     rcx, rdi; Sid
0x14007ff3c  call    cs:__imp_RtlInitializeSid
0x14007ff43  nop     dword ptr [rax+rax+00h]
0x14007ff48  mov     ebx, eax
0x14007ff4a  test    eax, eax
0x14007ff4c  jns     short loc_14007FFAD
0x14007ff4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff55  lea     rax, WPP_GLOBAL_Control
0x14007ff5c  cmp     rcx, rax
0x14007ff5f  jz      short loc_14007FF94
0x14007ff61  mov     eax, [rcx+2Ch]
0x14007ff64  test    al, 1
0x14007ff66  jz      short loc_14007FF94
0x14007ff68  lfence
0x14007ff6b  mov     r9, gs:188h
0x14007ff74  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14007ff7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ff82  mov     edx, 14h
0x14007ff87  mov     [rsp+48h+var_28], ebx
0x14007ff8b  mov     rcx, [rcx+18h]
0x14007ff8f  call    WPP_SF_qD
0x14007ff94  mov     edx, 6473504Dh; Tag
0x14007ff99  mov     rcx, rdi; P
0x14007ff9c  call    cs:__imp_ExFreePoolWithTag
0x14007ffa3  nop     dword ptr [rax+rax+00h]
0x14007ffa8  jmp     loc_14008004E
0x14007ffad  lfence
0x14007ffb0  xor     edx, edx; SubAuthority
0x14007ffb2  mov     rcx, rdi; Sid
0x14007ffb5  call    cs:__imp_RtlSubAuthoritySid
0x14007ffbc  nop     dword ptr [rax+rax+00h]
0x14007ffc1  mov     edx, 1; SubAuthority
0x14007ffc6  mov     rcx, rdi; Sid
0x14007ffc9  mov     dword ptr [rax], 50h ; 'P'
0x14007ffcf  call    cs:__imp_RtlSubAuthoritySid
0x14007ffd6  nop     dword ptr [rax+rax+00h]
0x14007ffdb  mov     edx, 2; SubAuthority
0x14007ffe0  mov     rcx, rdi; Sid
0x14007ffe3  mov     dword ptr [rax], 0F748CDBh
0x14007ffe9  call    cs:__imp_RtlSubAuthoritySid
0x14007fff0  nop     dword ptr [rax+rax+00h]
0x14007fff5  mov     edx, 3; SubAuthority
0x14007fffa  mov     rcx, rdi; Sid
0x14007fffd  mov     dword ptr [rax], 0F37372C2h
0x140080003  call    cs:__imp_RtlSubAuthoritySid
0x14008000a  nop     dword ptr [rax+rax+00h]
0x14008000f  mov     edx, 4; SubAuthority
0x140080014  mov     rcx, rdi; Sid
0x140080017  mov     dword ptr [rax], 44B9262Bh
0x14008001d  call    cs:__imp_RtlSubAuthoritySid
0x140080024  nop     dword ptr [rax+rax+00h]
0x140080029  mov     edx, 5; SubAuthority
0x14008002e  mov     rcx, rdi; Sid
0x140080031  mov     dword ptr [rax], 24F1E77h
0x140080037  call    cs:__imp_RtlSubAuthoritySid
0x14008003e  nop     dword ptr [rax+rax+00h]
0x140080043  xor     ebx, ebx
0x140080045  mov     dword ptr [rax], 21B56376h
0x14008004b  mov     [rsi], rdi
0x14008004e  mov     eax, ebx
0x140080050  mov     rcx, [rsp+48h+var_10]
0x140080055  xor     rcx, rsp; StackCookie
0x140080058  call    __security_check_cookie
0x14008005d  mov     rbx, [rsp+48h+arg_8]
0x140080062  mov     rsi, [rsp+48h+arg_10]
0x140080067  add     rsp, 40h
0x14008006b  pop     rdi
0x14008006c  retn
```
