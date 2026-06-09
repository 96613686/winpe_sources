# VidSidInitializeVmCompute

- ea: `0x14009b92c`
- end: `0x14009b9e6`
- name: `VidSidInitializeVmCompute`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400769d8`
- `0x1400a9ad8`

## callees

- `0x140021c60`
- `0x14009b92c`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14009b969`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14009b969`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009b9be`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009b9be`

## pseudocode

```c
__int64 __fastcall VidSidInitializeVmCompute(__int64 a1, ULONG *a2)
{
  __int64 result; // rax
  ULONG v5; // ecx
  int v6; // [rsp+50h] [rbp-18h] BYREF
  __int16 v7; // [rsp+54h] [rbp-14h]

  v7 = 1280;
  v6 = 0;
  if ( !a2 )
    return 3221225485LL;
  v5 = RtlLengthRequiredSid(6u);
  if ( *a2 >= v5 )
    return RtlInitializeSidEx(a1, &v6, 6, 80, -427641928);
  result = 3221225507LL;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x14009b92c  mov     [rsp+arg_10], rbx
0x14009b931  push    rdi
0x14009b932  sub     rsp, 60h
0x14009b936  mov     rax, cs:__security_cookie
0x14009b93d  xor     rax, rsp
0x14009b940  mov     [rsp+68h+var_10], rax
0x14009b945  xor     eax, eax
0x14009b947  mov     [rsp+68h+var_14], 500h
0x14009b94e  mov     [rsp+68h+var_18], eax
0x14009b952  mov     rbx, rdx
0x14009b955  mov     rdi, rcx
0x14009b958  test    rdx, rdx
0x14009b95b  jnz     short loc_14009B964
0x14009b95d  mov     eax, 0C000000Dh
0x14009b962  jmp     short loc_14009B9CA
0x14009b964  mov     ecx, 6; SubAuthorityCount
0x14009b969  call    cs:__imp_RtlLengthRequiredSid
0x14009b970  nop     dword ptr [rax+rax+00h]
0x14009b975  mov     ecx, eax
0x14009b977  cmp     [rbx], eax
0x14009b979  jnb     short loc_14009B984
0x14009b97b  mov     eax, 0C0000023h
0x14009b980  mov     [rbx], ecx
0x14009b982  jmp     short loc_14009B9CA
0x14009b984  mov     [rsp+68h+var_28], 3D66EE0Fh
0x14009b98c  lea     rdx, [rsp+68h+var_18]
0x14009b991  mov     [rsp+68h+var_30], 0F9BCB43Ch
0x14009b999  mov     r9d, 50h ; 'P'
0x14009b99f  mov     [rsp+68h+var_38], 0B1F45B9Bh
0x14009b9a7  mov     rcx, rdi
0x14009b9aa  mov     [rsp+68h+var_40], 0CE815B35h
0x14009b9b2  mov     [rsp+68h+var_48], 0E682B3B8h
0x14009b9ba  lea     r8d, [r9-4Ah]
0x14009b9be  call    cs:__imp_RtlInitializeSidEx
0x14009b9c5  nop     dword ptr [rax+rax+00h]
0x14009b9ca  mov     rcx, [rsp+68h+var_10]
0x14009b9cf  xor     rcx, rsp; StackCookie
0x14009b9d2  call    __security_check_cookie
0x14009b9d7  mov     rbx, [rsp+68h+arg_10]
0x14009b9df  add     rsp, 60h
0x14009b9e3  pop     rdi
0x14009b9e4  retn
```
