# IsCallerAdminsOrSystem

- ea: `0x18000cbc0`
- end: `0x18000cc87`
- name: `IsCallerAdminsOrSystem`
- size: `199`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cb40`

## callees

- `0x18000cbc0`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlInitializeSidEx` at `0x18000cc06`
- `ntdll!RtlInitializeSidEx` at `0x18000cc49`
- `ntdll!RtlInitializeSidEx` at `0x18000cc06`
- `ntdll!RtlInitializeSidEx` at `0x18000cc49`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000cc21`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000cc64`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000cc21`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000cc64`

## pseudocode

```c
__int64 IsCallerAdminsOrSystem()
{
  _BYTE v1[4]; // [rsp+30h] [rbp-30h] BYREF
  int v2; // [rsp+34h] [rbp-2Ch] BYREF
  __int16 v3; // [rsp+38h] [rbp-28h]
  __int128 v4; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  v1[0] = 0;
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
0x18000cbc0  push    rbp
0x18000cbc2  mov     rbp, rsp
0x18000cbc5  sub     rsp, 60h
0x18000cbc9  mov     rax, cs:__security_cookie
0x18000cbd0  xor     rax, rsp
0x18000cbd3  mov     [rbp+var_10], rax
0x18000cbd7  and     [rbp+var_2C], 0
0x18000cbdb  lea     rdx, [rbp+var_2C]
0x18000cbdf  mov     r9d, 20h ; ' '
0x18000cbe5  mov     [rbp+var_30], 0
0x18000cbe9  xorps   xmm0, xmm0
0x18000cbec  mov     [rbp+var_28], 500h
0x18000cbf2  lea     rcx, [rbp+var_20]
0x18000cbf6  mov     [rsp+60h+var_40], 220h
0x18000cbfe  movups  [rbp+var_20], xmm0
0x18000cc02  lea     r8d, [r9-1Eh]
0x18000cc06  call    cs:__imp_RtlInitializeSidEx
0x18000cc0d  nop     dword ptr [rax+rax+00h]
0x18000cc12  xor     r8d, r8d
0x18000cc15  lea     r9, [rbp+var_30]
0x18000cc19  lea     rdx, [rbp+var_20]
0x18000cc1d  lea     rcx, [r8-5]
0x18000cc21  call    cs:__imp_RtlCheckTokenMembershipEx
0x18000cc28  nop     dword ptr [rax+rax+00h]
0x18000cc2d  test    eax, eax
0x18000cc2f  js      short loc_18000CC70
0x18000cc31  cmp     [rbp+var_30], 0
0x18000cc35  jnz     short loc_18000CC70
0x18000cc37  mov     r9d, 12h
0x18000cc3d  lea     rdx, [rbp+var_2C]
0x18000cc41  lea     rcx, [rbp+var_20]
0x18000cc45  lea     r8d, [r9-11h]
0x18000cc49  call    cs:__imp_RtlInitializeSidEx
0x18000cc50  nop     dword ptr [rax+rax+00h]
0x18000cc55  xor     r8d, r8d
0x18000cc58  lea     r9, [rbp+var_30]
0x18000cc5c  lea     rdx, [rbp+var_20]
0x18000cc60  lea     rcx, [r8-5]
0x18000cc64  call    cs:__imp_RtlCheckTokenMembershipEx
0x18000cc6b  nop     dword ptr [rax+rax+00h]
0x18000cc70  movzx   eax, [rbp+var_30]
0x18000cc74  mov     rcx, [rbp+var_10]
0x18000cc78  xor     rcx, rsp; StackCookie
0x18000cc7b  call    __security_check_cookie
0x18000cc80  add     rsp, 60h
0x18000cc84  pop     rbp
0x18000cc85  retn
```
