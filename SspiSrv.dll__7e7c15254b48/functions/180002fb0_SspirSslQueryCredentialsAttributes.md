# SspirSslQueryCredentialsAttributes

- ea: `0x180002fb0`
- end: `0x1800030c9`
- name: `SspirSslQueryCredentialsAttributes`
- size: `281`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800013d0`
- `0x180001510`
- `0x180002fb0`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslQueryCredentialsAttributes(
        __int64 a1,
        _QWORD *a2,
        __int128 *a3,
        unsigned int a4,
        _QWORD *a5)
{
  size_t v7; // rcx
  void *v8; // rax
  void *v9; // rbx
  int v11; // edi
  _QWORD v12[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 72) )
    return 3221225659LL;
  if ( !a2 || !a3 || !a5 )
    return 3221225485LL;
  v12[0] = *a2;
  v12[1] = a2[1];
  v13 = *a3;
  switch ( a4 )
  {
    case 1u:
      goto LABEL_10;
    case 0x56u:
      v7 = 16;
      goto LABEL_13;
    case 0x57u:
LABEL_10:
      v7 = 8;
      goto LABEL_13;
  }
  if ( a4 != 88 )
    return 3221225485LL;
  v7 = 4;
LABEL_13:
  v8 = MIDL_user_allocate(v7);
  v9 = v8;
  if ( !v8 )
    return 3221225626LL;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD, void *))(gLsapSspiExtension + 72))(
          a1,
          v12,
          &v13,
          a4,
          v8);
  if ( v11 < 0 )
    MIDL_user_free(v9);
  else
    *a5 = v9;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180002fb0  mov     [rsp+arg_10], rbx
0x180002fb5  push    rbp
0x180002fb6  push    rsi
0x180002fb7  push    rdi
0x180002fb8  sub     rsp, 60h
0x180002fbc  mov     rax, cs:__security_cookie
0x180002fc3  xor     rax, rsp
0x180002fc6  mov     [rsp+78h+var_28], rax
0x180002fcb  mov     rax, cs:gLsapSspiExtension
0x180002fd2  mov     edi, r9d
0x180002fd5  mov     rsi, [rsp+78h+arg_20]
0x180002fdd  mov     rbp, rcx
0x180002fe0  test    rax, rax
0x180002fe3  jz      loc_1800030A7
0x180002fe9  cmp     qword ptr [rax+48h], 0
0x180002fee  jz      loc_1800030A7
0x180002ff4  test    rdx, rdx
0x180002ff7  jz      loc_1800030A0
0x180002ffd  test    r8, r8
0x180003000  jz      loc_1800030A0
0x180003006  test    rsi, rsi
0x180003009  jz      loc_1800030A0
0x18000300f  mov     rax, [rdx]
0x180003012  mov     [rsp+78h+var_48], rax
0x180003017  mov     rax, [rdx+8]
0x18000301b  mov     [rsp+78h+var_40], rax
0x180003020  movups  xmm0, xmmword ptr [r8]
0x180003024  movdqu  [rsp+78h+var_38], xmm0
0x18000302a  cmp     r9d, 1
0x18000302e  jz      short loc_180003041
0x180003030  cmp     r9d, 56h ; 'V'
0x180003034  jnz     short loc_18000303C
0x180003036  lea     ecx, [r9-46h]
0x18000303a  jmp     short loc_180003050
0x18000303c  cmp     edi, 57h ; 'W'
0x18000303f  jnz     short loc_180003048
0x180003041  mov     ecx, 8
0x180003046  jmp     short loc_180003050
0x180003048  cmp     edi, 58h ; 'X'
0x18000304b  jnz     short loc_1800030A0
0x18000304d  lea     ecx, [rdi-54h]; size
0x180003050  call    MIDL_user_allocate
0x180003055  mov     rbx, rax
0x180003058  test    rax, rax
0x18000305b  jnz     short loc_180003064
0x18000305d  mov     eax, 0C000009Ah
0x180003062  jmp     short loc_1800030AC
0x180003064  mov     rax, cs:gLsapSspiExtension
0x18000306b  lea     r8, [rsp+78h+var_38]
0x180003070  mov     r9d, edi
0x180003073  mov     [rsp+78h+var_58], rbx
0x180003078  lea     rdx, [rsp+78h+var_48]
0x18000307d  mov     rcx, rbp
0x180003080  mov     rax, [rax+48h]
0x180003084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003089  mov     edi, eax
0x18000308b  test    eax, eax
0x18000308d  js      short loc_180003094
0x18000308f  mov     [rsi], rbx
0x180003092  jmp     short loc_18000309C
0x180003094  mov     rcx, rbx; void *
0x180003097  call    MIDL_user_free
0x18000309c  mov     eax, edi
0x18000309e  jmp     short loc_1800030AC
0x1800030a0  mov     eax, 0C000000Dh
0x1800030a5  jmp     short loc_1800030AC
0x1800030a7  mov     eax, 0C00000BBh
0x1800030ac  mov     rcx, [rsp+78h+var_28]
0x1800030b1  xor     rcx, rsp; StackCookie
0x1800030b4  call    __security_check_cookie
0x1800030b9  mov     rbx, [rsp+78h+arg_10]
0x1800030c1  add     rsp, 60h
0x1800030c5  pop     rdi
0x1800030c6  pop     rsi
0x1800030c7  pop     rbp
0x1800030c8  retn
```
