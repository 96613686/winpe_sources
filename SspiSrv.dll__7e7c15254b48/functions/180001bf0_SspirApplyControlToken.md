# SspirApplyControlToken

- ea: `0x180001bf0`
- end: `0x180001c73`
- name: `SspirApplyControlToken`
- size: `131`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002980`

## callees

- `0x180001bf0`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirApplyControlToken(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4)
{
  __int64 (__fastcall *v4)(__int64, _QWORD *, __int128 *); // rax
  __int128 v5; // xmm0
  _QWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 96);
  if ( !v4 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 )
    return 3221225485LL;
  v5 = *a3;
  v7[0] = *a2;
  v7[1] = a2[1];
  v8 = v5;
  return v4(a1, v7, &v8);
}

```

## disassembly

```asm
0x180001bf0  sub     rsp, 68h
0x180001bf4  mov     rax, cs:__security_cookie
0x180001bfb  xor     rax, rsp
0x180001bfe  mov     [rsp+68h+var_18], rax
0x180001c03  mov     rax, cs:gLsapSspiExtension
0x180001c0a  mov     r10, rdx
0x180001c0d  test    rax, rax
0x180001c10  jz      short loc_180001C65
0x180001c12  mov     rax, [rax+60h]
0x180001c16  test    rax, rax
0x180001c19  jz      short loc_180001C65
0x180001c1b  test    rdx, rdx
0x180001c1e  jz      short loc_180001C6C
0x180001c20  test    r8, r8
0x180001c23  jz      short loc_180001C6C
0x180001c25  test    r9, r9
0x180001c28  jz      short loc_180001C6C
0x180001c2a  mov     rdx, [rdx]
0x180001c2d  movups  xmm0, xmmword ptr [r8]
0x180001c31  mov     [rsp+68h+var_38], rdx
0x180001c36  lea     r8, [rsp+68h+var_28]
0x180001c3b  mov     rdx, [r10+8]
0x180001c3f  mov     [rsp+68h+var_30], rdx
0x180001c44  lea     rdx, [rsp+68h+var_38]
0x180001c49  movups  [rsp+68h+var_28], xmm0
0x180001c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c53  mov     rcx, [rsp+68h+var_18]
0x180001c58  xor     rcx, rsp; StackCookie
0x180001c5b  call    __security_check_cookie
0x180001c60  add     rsp, 68h
0x180001c64  retn
0x180001c65  mov     eax, 0C00000BBh
0x180001c6a  jmp     short loc_180001C53
0x180001c6c  mov     eax, 0C000000Dh
0x180001c71  jmp     short loc_180001C53
```
