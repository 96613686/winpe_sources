# GetCallerLuid

- ea: `0x180002190`
- end: `0x18000223d`
- name: `GetCallerLuid`
- size: `173`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180002020`

## callees

- `0x180002190`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180002209`
- `ntdll!RtlCopyLuid` at `0x180002209`
- `ntdll!NtQueryInformationToken` at `0x1800021ef`
- `ntdll!NtQueryInformationToken` at `0x1800021ef`

## pseudocode

```c
__int64 __fastcall GetCallerLuid(PLUID DestinationLuid)
{
  NTSTATUS v2; // ebx
  ULONG v4; // [rsp+30h] [rbp-58h] BYREF
  struct _LUID SourceLuid[2]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v6; // [rsp+48h] [rbp-40h]
  __int128 v7; // [rsp+58h] [rbp-30h]
  __int64 v8; // [rsp+68h] [rbp-20h]

  v4 = 0;
  *(_OWORD *)&SourceLuid[0].LowPart = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( !DestinationLuid )
    return 3221225485LL;
  v2 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenStatistics, SourceLuid, 0x38u, &v4);
  if ( v2 >= 0 )
    RtlCopyLuid(DestinationLuid, &SourceLuid[1]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002190  mov     r11, rsp
0x180002193  push    rdi
0x180002194  sub     rsp, 80h
0x18000219b  mov     rax, cs:__security_cookie
0x1800021a2  xor     rax, rsp
0x1800021a5  mov     [rsp+88h+var_18], rax
0x1800021aa  xorps   xmm0, xmm0
0x1800021ad  xor     eax, eax
0x1800021af  mov     [rsp+88h+var_58], eax
0x1800021b3  mov     rdi, rcx
0x1800021b6  movups  xmmword ptr [rsp+88h+SourceLuid.LowPart], xmm0
0x1800021bb  movups  [rsp+88h+var_40], xmm0
0x1800021c0  movups  [rsp+88h+var_30], xmm0
0x1800021c5  mov     [r11-20h], rax
0x1800021c9  test    rcx, rcx
0x1800021cc  jz      short loc_180002221
0x1800021ce  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800021d4  mov     [r11+10h], rbx
0x1800021d8  lea     rax, [r11-58h]
0x1800021dc  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800021e3  lea     r8, [r11-50h]; TokenInformation
0x1800021e7  mov     [r11-68h], rax
0x1800021eb  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800021ef  call    cs:__imp_NtQueryInformationToken
0x1800021f6  nop     dword ptr [rax+rax+00h]
0x1800021fb  mov     ebx, eax
0x1800021fd  test    eax, eax
0x1800021ff  js      short loc_180002215
0x180002201  lea     rdx, [rsp+88h+SourceLuid.LowPart+8]; SourceLuid
0x180002206  mov     rcx, rdi; DestinationLuid
0x180002209  call    cs:__imp_RtlCopyLuid
0x180002210  nop     dword ptr [rax+rax+00h]
0x180002215  mov     eax, ebx
0x180002217  mov     rbx, [rsp+88h+arg_8]
0x18000221f  jmp     short loc_180002226
0x180002221  mov     eax, 0C000000Dh
0x180002226  mov     rcx, [rsp+88h+var_18]
0x18000222b  xor     rcx, rsp; StackCookie
0x18000222e  call    __security_check_cookie
0x180002233  add     rsp, 80h
0x18000223a  pop     rdi
0x18000223b  retn
```
