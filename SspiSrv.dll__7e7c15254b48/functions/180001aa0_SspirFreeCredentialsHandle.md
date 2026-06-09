# SspirFreeCredentialsHandle

- ea: `0x180001aa0`
- end: `0x180001b1e`
- name: `SspirFreeCredentialsHandle`
- size: `126`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002a80`

## callees

- `0x180001aa0`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirFreeCredentialsHandle(__int64 a1, _QWORD *a2, __int128 *a3)
{
  __int64 (__fastcall *v3)(__int64, _QWORD *, __int128 *); // rax
  __int128 v4; // xmm0
  _QWORD v6[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 48);
  if ( !v3 )
    return 3221225659LL;
  if ( !a2 || !a3 )
    return 3221225485LL;
  v4 = *a3;
  v6[0] = *a2;
  v6[1] = a2[1];
  v7 = v4;
  return v3(a1, v6, &v7);
}

```

## disassembly

```asm
0x180001aa0  sub     rsp, 68h
0x180001aa4  mov     rax, cs:__security_cookie
0x180001aab  xor     rax, rsp
0x180001aae  mov     [rsp+68h+var_18], rax
0x180001ab3  mov     rax, cs:gLsapSspiExtension
0x180001aba  mov     r10, rdx
0x180001abd  test    rax, rax
0x180001ac0  jz      short loc_180001B10
0x180001ac2  mov     rax, [rax+30h]
0x180001ac6  test    rax, rax
0x180001ac9  jz      short loc_180001B10
0x180001acb  test    rdx, rdx
0x180001ace  jz      short loc_180001B17
0x180001ad0  test    r8, r8
0x180001ad3  jz      short loc_180001B17
0x180001ad5  mov     rdx, [rdx]
0x180001ad8  movups  xmm0, xmmword ptr [r8]
0x180001adc  mov     [rsp+68h+var_38], rdx
0x180001ae1  lea     r8, [rsp+68h+var_28]
0x180001ae6  mov     rdx, [r10+8]
0x180001aea  mov     [rsp+68h+var_30], rdx
0x180001aef  lea     rdx, [rsp+68h+var_38]
0x180001af4  movups  [rsp+68h+var_28], xmm0
0x180001af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001afe  mov     rcx, [rsp+68h+var_18]
0x180001b03  xor     rcx, rsp; StackCookie
0x180001b06  call    __security_check_cookie
0x180001b0b  add     rsp, 68h
0x180001b0f  retn
0x180001b10  mov     eax, 0C00000BBh
0x180001b15  jmp     short loc_180001AFE
0x180001b17  mov     eax, 0C000000Dh
0x180001b1c  jmp     short loc_180001AFE
```
