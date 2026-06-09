# GetCallerLuid

- ea: `0x180002180`
- end: `0x18000222e`
- name: `GetCallerLuid`
- size: `174`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180002010`

## callees

- `0x180002180`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x1800021fa`
- `ntdll!RtlCopyLuid` at `0x1800021fa`
- `ntdll!NtQueryInformationToken` at `0x1800021e0`
- `ntdll!NtQueryInformationToken` at `0x1800021e0`

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
0x180002180  mov     r11, rsp
0x180002183  push    rdi
0x180002184  sub     rsp, 80h
0x18000218b  mov     rax, cs:__security_cookie
0x180002192  xor     rax, rsp
0x180002195  mov     [rsp+88h+var_18], rax
0x18000219a  xorps   xmm0, xmm0
0x18000219d  xor     eax, eax
0x18000219f  mov     [rsp+88h+var_58], eax
0x1800021a3  mov     rdi, rcx
0x1800021a6  movups  xmmword ptr [rsp+88h+SourceLuid.LowPart], xmm0
0x1800021ab  movups  [rsp+88h+var_40], xmm0
0x1800021b0  movups  [rsp+88h+var_30], xmm0
0x1800021b5  mov     [r11-20h], rax
0x1800021b9  test    rcx, rcx
0x1800021bc  jz      short loc_180002212
0x1800021be  lea     rax, [r11-58h]
0x1800021c2  mov     [r11+10h], rbx
0x1800021c6  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800021cc  mov     [r11-68h], rax
0x1800021d0  lea     r8, [r11-50h]; TokenInformation
0x1800021d4  mov     edx, 0Ah; TokenInformationClass
0x1800021d9  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800021e0  call    cs:__imp_NtQueryInformationToken
0x1800021e7  nop     dword ptr [rax+rax+00h]
0x1800021ec  mov     ebx, eax
0x1800021ee  test    eax, eax
0x1800021f0  js      short loc_180002206
0x1800021f2  lea     rdx, [rsp+88h+SourceLuid.LowPart+8]; SourceLuid
0x1800021f7  mov     rcx, rdi; DestinationLuid
0x1800021fa  call    cs:__imp_RtlCopyLuid
0x180002201  nop     dword ptr [rax+rax+00h]
0x180002206  mov     eax, ebx
0x180002208  mov     rbx, [rsp+88h+arg_8]
0x180002210  jmp     short loc_180002217
0x180002212  mov     eax, 0C000000Dh
0x180002217  mov     rcx, [rsp+88h+var_18]
0x18000221c  xor     rcx, rsp; StackCookie
0x18000221f  call    __security_check_cookie
0x180002224  add     rsp, 80h
0x18000222b  pop     rdi
0x18000222c  retn
```
