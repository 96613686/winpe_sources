# IsCallerAdminsOrSystem

- ea: `0x18000cfa0`
- end: `0x18000d06a`
- name: `IsCallerAdminsOrSystem`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cf20`

## callees

- `0x18000cfa0`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlInitializeSidEx` at `0x18000cfe9`
- `ntdll!RtlInitializeSidEx` at `0x18000d02c`
- `ntdll!RtlInitializeSidEx` at `0x18000cfe9`
- `ntdll!RtlInitializeSidEx` at `0x18000d02c`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000d004`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000d047`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000d004`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000d047`

## pseudocode

```c
__int64 IsCallerAdminsOrSystem()
{
  _BYTE v1[4]; // [rsp+30h] [rbp-30h] BYREF
  int v2; // [rsp+34h] [rbp-2Ch] BYREF
  __int16 v3; // [rsp+38h] [rbp-28h]
  __int128 v4; // [rsp+40h] [rbp-20h] BYREF

  v1[0] = 0;
  v2 = 0;
  v3 = 1280;
  v4 = 0;
  RtlInitializeSidEx(&v4, &v2, 2);
  if ( (int)RtlCheckTokenMembershipEx(-5, &v4, 0, v1) >= 0 && !v1[0] )
  {
    RtlInitializeSidEx(&v4, &v2, 1);
    RtlCheckTokenMembershipEx(-5, &v4, 0, v1);
  }
  return v1[0];
}

```

## disassembly

```asm
0x18000cfa0  push    rbp
0x18000cfa2  mov     rbp, rsp
0x18000cfa5  sub     rsp, 60h
0x18000cfa9  mov     rax, cs:__security_cookie
0x18000cfb0  xor     rax, rsp
0x18000cfb3  mov     [rbp+var_10], rax
0x18000cfb7  mov     r9d, 20h ; ' '
0x18000cfbd  mov     [rbp+var_30], 0
0x18000cfc1  xorps   xmm0, xmm0
0x18000cfc4  mov     [rbp+var_2C], 0
0x18000cfcb  lea     rdx, [rbp+var_2C]
0x18000cfcf  mov     [rbp+var_28], 500h
0x18000cfd5  lea     rcx, [rbp+var_20]
0x18000cfd9  mov     [rsp+60h+var_40], 220h
0x18000cfe1  lea     r8d, [r9-1Eh]
0x18000cfe5  movups  [rbp+var_20], xmm0
0x18000cfe9  call    cs:__imp_RtlInitializeSidEx
0x18000cff0  nop     dword ptr [rax+rax+00h]
0x18000cff5  xor     r8d, r8d
0x18000cff8  lea     r9, [rbp+var_30]
0x18000cffc  lea     rdx, [rbp+var_20]
0x18000d000  lea     rcx, [r8-5]
0x18000d004  call    cs:__imp_RtlCheckTokenMembershipEx
0x18000d00b  nop     dword ptr [rax+rax+00h]
0x18000d010  test    eax, eax
0x18000d012  js      short loc_18000D053
0x18000d014  cmp     [rbp+var_30], 0
0x18000d018  jnz     short loc_18000D053
0x18000d01a  mov     r9d, 12h
0x18000d020  lea     rdx, [rbp+var_2C]
0x18000d024  lea     rcx, [rbp+var_20]
0x18000d028  lea     r8d, [r9-11h]
0x18000d02c  call    cs:__imp_RtlInitializeSidEx
0x18000d033  nop     dword ptr [rax+rax+00h]
0x18000d038  xor     r8d, r8d
0x18000d03b  lea     r9, [rbp+var_30]
0x18000d03f  lea     rdx, [rbp+var_20]
0x18000d043  lea     rcx, [r8-5]
0x18000d047  call    cs:__imp_RtlCheckTokenMembershipEx
0x18000d04e  nop     dword ptr [rax+rax+00h]
0x18000d053  movzx   eax, [rbp+var_30]
0x18000d057  mov     rcx, [rbp+var_10]
0x18000d05b  xor     rcx, rsp; StackCookie
0x18000d05e  call    __security_check_cookie
0x18000d063  add     rsp, 60h
0x18000d067  pop     rbp
0x18000d068  retn
```
