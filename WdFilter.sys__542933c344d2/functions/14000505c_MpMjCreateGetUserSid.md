# MpMjCreateGetUserSid

- ea: `0x14000505c`
- end: `0x1400051ba`
- name: `MpMjCreateGetUserSid`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14003c990`

## callees

- `0x14000505c`
- `0x1400051bc`
- `0x1400118d0`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1400050e4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400050e4`
- `ntoskrnl!RtlCopySid` at `0x140005128`
- `ntoskrnl!RtlCopySid` at `0x140005128`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000518c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000518c`

## pseudocode

```c
__int64 __fastcall MpMjCreateGetUserSid(__int64 a1, void *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  void *v6; // rcx
  NTSTATUS v7; // ebx
  __int64 v8; // rdx
  PVOID TokenInformation; // [rsp+30h] [rbp-18h] BYREF

  TokenInformation = 0;
  if ( !a1 )
    return 3221225485LL;
  if ( !a2 )
    return 3221225485LL;
  v3 = *(_QWORD *)(a1 + 16);
  if ( *(_BYTE *)(v3 + 4) )
    return 3221225485LL;
  if ( !v3 )
    return 3221225485LL;
  v4 = *(_QWORD *)(v3 + 24);
  if ( !v4 )
    return 3221225485LL;
  v5 = *(_QWORD *)(v4 + 8);
  if ( !v5 )
    return 3221225485LL;
  v6 = *(void **)(v5 + 32);
  if ( !v6 )
  {
    v6 = *(void **)(v5 + 48);
    if ( !v6 )
      return 3221225485LL;
  }
  v7 = SeQueryInformationToken(v6, TokenUser, &TokenInformation);
  if ( v7 >= 0 )
  {
    v7 = RtlCopySid(0x50u, a2, *(PSID *)TokenInformation);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v8 = 40;
      goto LABEL_17;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v8 = 39;
LABEL_17:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
      KeGetCurrentThread(),
      v7);
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000505c  mov     [rsp+arg_10], rbx
0x140005061  push    rdi
0x140005062  sub     rsp, 40h
0x140005066  mov     rax, cs:__security_cookie
0x14000506d  xor     rax, rsp
0x140005070  mov     [rsp+48h+var_10], rax
0x140005075  mov     [rsp+48h+TokenInformation], 0
0x14000507e  mov     rdi, rdx
0x140005081  test    rcx, rcx
0x140005084  jz      loc_14000519C
0x14000508a  test    rdx, rdx
0x14000508d  jz      loc_14000519C
0x140005093  mov     rax, [rcx+10h]
0x140005097  cmp     byte ptr [rax+4], 0
0x14000509b  jnz     loc_14000519C
0x1400050a1  test    rax, rax
0x1400050a4  jz      loc_14000519C
0x1400050aa  mov     rax, [rax+18h]
0x1400050ae  test    rax, rax
0x1400050b1  jz      loc_14000519C
0x1400050b7  mov     rax, [rax+8]
0x1400050bb  test    rax, rax
0x1400050be  jz      loc_14000519C
0x1400050c4  mov     rcx, [rax+20h]
0x1400050c8  test    rcx, rcx
0x1400050cb  jnz     short loc_1400050DA
0x1400050cd  mov     rcx, [rax+30h]; Token
0x1400050d1  test    rcx, rcx
0x1400050d4  jz      loc_14000519C
0x1400050da  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1400050df  mov     edx, 1; TokenInformationClass
0x1400050e4  call    cs:__imp_SeQueryInformationToken
0x1400050eb  nop     dword ptr [rax+rax+00h]
0x1400050f0  mov     ebx, eax
0x1400050f2  test    eax, eax
0x1400050f4  jns     short loc_140005118
0x1400050f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050fd  lea     rax, WPP_GLOBAL_Control
0x140005104  cmp     rcx, rax
0x140005107  jz      short loc_140005180
0x140005109  mov     ecx, [rcx+2Ch]
0x14000510c  test    cl, 1
0x14000510f  jz      short loc_140005180
0x140005111  mov     edx, 27h ; '''
0x140005116  jmp     short loc_140005159
0x140005118  mov     r8, [rsp+48h+TokenInformation]
0x14000511d  mov     rdx, rdi; DestinationSid
0x140005120  mov     ecx, 50h ; 'P'; DestinationSidLength
0x140005125  mov     r8, [r8]; SourceSid
0x140005128  call    cs:__imp_RtlCopySid
0x14000512f  nop     dword ptr [rax+rax+00h]
0x140005134  mov     ebx, eax
0x140005136  test    eax, eax
0x140005138  jns     short loc_140005180
0x14000513a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005141  lea     rax, WPP_GLOBAL_Control
0x140005148  cmp     rcx, rax
0x14000514b  jz      short loc_140005180
0x14000514d  mov     eax, [rcx+2Ch]
0x140005150  test    al, 1
0x140005152  jz      short loc_140005180
0x140005154  mov     edx, 28h ; '('
0x140005159  lfence
0x14000515c  mov     r9, gs:188h
0x140005165  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x14000516c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005173  mov     [rsp+48h+var_28], ebx
0x140005177  mov     rcx, [rcx+18h]
0x14000517b  call    WPP_SF_qD
0x140005180  mov     rcx, [rsp+48h+TokenInformation]; P
0x140005185  test    rcx, rcx
0x140005188  jz      short loc_140005198
0x14000518a  xor     edx, edx; Tag
0x14000518c  call    cs:__imp_ExFreePoolWithTag
0x140005193  nop     dword ptr [rax+rax+00h]
0x140005198  mov     eax, ebx
0x14000519a  jmp     short loc_1400051A1
0x14000519c  mov     eax, 0C000000Dh
0x1400051a1  mov     rcx, [rsp+48h+var_10]
0x1400051a6  xor     rcx, rsp; StackCookie
0x1400051a9  call    __security_check_cookie
0x1400051ae  mov     rbx, [rsp+48h+arg_10]
0x1400051b3  add     rsp, 40h
0x1400051b7  pop     rdi
0x1400051b8  retn
```
