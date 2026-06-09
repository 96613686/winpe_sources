# SrpGetAppUniqueIdFromToken

- ea: `0x140006674`
- end: `0x140006756`
- name: `SrpGetAppUniqueIdFromToken`
- size: `226`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c524`

## callees

- `0x140006418`
- `0x140006674`

## string_xrefs

- `0x140006699`: `APPID://PATH`

## pseudocode

```c
__int64 __fastcall SrpGetAppUniqueIdFromToken(int a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD v5[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v7[2]; // [rsp+50h] [rbp-10h] BYREF

  v5[0] = 1703960;
  v5[1] = L"APPID://FQBN";
  v6[1] = L"APPID://PATH";
  v7[1] = L"APPID://SHA256HASH";
  v6[0] = 1703960;
  v7[0] = 2490404;
  if ( !a2 )
    return 3221225485LL;
  result = SrpGetAttributeFromToken(a1, (unsigned int)v5, 1, (_DWORD)a2, 0);
  if ( (int)result >= 0 && !*a2 )
  {
    result = SrpGetAttributeFromToken(a1, (unsigned int)v6, 0, (_DWORD)a2, 0);
    if ( (int)result >= 0 && !*a2 )
    {
      result = SrpGetAttributeFromToken(a1, (unsigned int)v7, 2, (_DWORD)a2, 0);
      if ( (int)result >= 0 && !*a2 )
        return 3221226021LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006674  mov     [rsp-8+arg_0], rbx
0x140006679  mov     [rsp-8+arg_8], rdi
0x14000667e  push    rbp
0x14000667f  mov     rbp, rsp
0x140006682  sub     rsp, 60h
0x140006686  mov     [rbp+var_30], 1A0018h
0x14000668e  lea     rax, aAppidFqbn; "APPID://FQBN"
0x140006695  mov     [rbp+var_28], rax
0x140006699  lea     rax, aAppidPath; "APPID://PATH"
0x1400066a0  mov     [rbp+var_18], rax
0x1400066a4  lea     rax, aAppidSha256has; "APPID://SHA256HASH"
0x1400066ab  mov     [rbp+var_8], rax
0x1400066af  mov     rbx, rdx
0x1400066b2  mov     [rbp+var_20], 1A0018h
0x1400066ba  mov     rdi, rcx
0x1400066bd  mov     [rbp+var_10], 260024h
0x1400066c5  test    rdx, rdx
0x1400066c8  jnz     short loc_1400066D1
0x1400066ca  mov     eax, 0C000000Dh
0x1400066cf  jmp     short loc_140006745
0x1400066d1  mov     r8d, 1
0x1400066d7  mov     [rsp+60h+var_40], 0
0x1400066e0  mov     r9, rbx
0x1400066e3  lea     rdx, [rbp+var_30]
0x1400066e7  call    SrpGetAttributeFromToken
0x1400066ec  test    eax, eax
0x1400066ee  js      short loc_140006745
0x1400066f0  cmp     qword ptr [rbx], 0
0x1400066f4  jnz     short loc_140006745
0x1400066f6  xor     r8d, r8d
0x1400066f9  lea     rdx, [rbp+var_20]
0x1400066fd  mov     r9, rbx
0x140006700  mov     [rsp+60h+var_40], r8
0x140006705  mov     rcx, rdi
0x140006708  call    SrpGetAttributeFromToken
0x14000670d  test    eax, eax
0x14000670f  js      short loc_140006745
0x140006711  cmp     qword ptr [rbx], 0
0x140006715  jnz     short loc_140006745
0x140006717  mov     r8d, 2
0x14000671d  mov     [rsp+60h+var_40], 0
0x140006726  mov     r9, rbx
0x140006729  lea     rdx, [rbp+var_10]
0x14000672d  mov     rcx, rdi
0x140006730  call    SrpGetAttributeFromToken
0x140006735  test    eax, eax
0x140006737  js      short loc_140006745
0x140006739  cmp     qword ptr [rbx], 0
0x14000673d  mov     ecx, 0C0000225h
0x140006742  cmovz   eax, ecx
0x140006745  mov     rbx, [rsp+60h+arg_0]
0x14000674a  mov     rdi, [rsp+60h+arg_8]
0x14000674f  add     rsp, 60h
0x140006753  pop     rbp
0x140006754  retn
```
