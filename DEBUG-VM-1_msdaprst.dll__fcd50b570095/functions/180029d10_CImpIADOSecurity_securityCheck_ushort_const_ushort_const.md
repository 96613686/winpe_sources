# CImpIADOSecurity::securityCheck(ushort const *,ushort const *)

- ea: `0x180029d10`
- end: `0x180029e7b`
- name: `?securityCheck@CImpIADOSecurity@@AEAAJPEBG0@Z`
- size: `363`
- prototype: `int(CImpIADOSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800295b0`

## callees

- `0x180029a14`
- `0x180029bf8`
- `0x180029d10`
- `0x18002e006`
- `0x18002e060`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::securityCheck(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 result; // rax
  CImpIADOSecurity *v6; // rcx
  unsigned int v7; // edi
  struct IInternetSecurityManager *v8; // rbx
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-C4h] BYREF
  struct IInternetSecurityManager *v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buf2[512]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Buf1[512]; // [rsp+250h] [rbp+150h] BYREF

  v12 = 0;
  Size = 0;
  v10 = 4;
  v11 = 3;
  result = CImpIADOSecurity::getZone(this, a3, &v10, &v12);
  if ( (int)result >= 0 )
  {
    v7 = -2147024891;
    v8 = v12;
    if ( v10 )
    {
      Size = 0x20000000200LL;
      if ( ((int (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, _BYTE *, size_t *, _QWORD))v12->lpVtbl->GetSecurityId)(
             v12,
             a2,
             Buf1,
             &Size,
             0) >= 0
        && ((int (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, _BYTE *, char *, _QWORD))v8->lpVtbl->GetSecurityId)(
             v8,
             a3,
             Buf2,
             (char *)&Size + 4,
             0) >= 0
        && (_DWORD)Size == HIDWORD(Size) )
      {
        v7 = memcmp_0(Buf1, Buf2, (unsigned int)Size) != 0 ? 0x80070005 : 0;
      }
    }
    else if ( (int)CImpIADOSecurity::getPolicy(v6, 0, &v11) >= 0 && !v11 )
    {
      v7 = 0;
    }
    ((void (__fastcall *)(struct IInternetSecurityManager *))v8->lpVtbl->Release)(v8);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180029d10  mov     [rsp-8+arg_0], rbx
0x180029d15  mov     [rsp-8+arg_18], rsi
0x180029d1a  push    rbp
0x180029d1b  push    rdi
0x180029d1c  push    r14
0x180029d1e  lea     rbp, [rsp-360h]
0x180029d26  sub     rsp, 460h
0x180029d2d  mov     rax, cs:__security_cookie
0x180029d34  xor     rax, rsp
0x180029d37  mov     [rbp+370h+var_20], rax
0x180029d3e  mov     rsi, r8
0x180029d41  mov     [rsp+470h+var_430], 0
0x180029d4a  mov     r14, rdx
0x180029d4d  mov     dword ptr [rsp+470h+Size], 0
0x180029d55  mov     rdx, rsi; unsigned __int16 *
0x180029d58  mov     dword ptr [rsp+470h+Size+4], 0
0x180029d60  lea     r9, [rsp+470h+var_430]; struct IInternetSecurityManager **
0x180029d65  mov     [rsp+470h+var_438], 4
0x180029d6d  lea     r8, [rsp+470h+var_438]; unsigned int *
0x180029d72  mov     [rsp+470h+var_434], 3
0x180029d7a  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x180029d7f  test    eax, eax
0x180029d81  js      loc_180029E54
0x180029d87  cmp     [rsp+470h+var_438], 0
0x180029d8c  mov     edi, 80070005h
0x180029d91  mov     rbx, [rsp+470h+var_430]
0x180029d96  jnz     short loc_180029DBE
0x180029d98  lea     r8, [rsp+470h+var_434]; unsigned int *
0x180029d9d  xor     edx, edx; unsigned int
0x180029d9f  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x180029da4  test    eax, eax
0x180029da6  js      loc_180029E43
0x180029dac  cmp     [rsp+470h+var_434], 0
0x180029db1  jnz     loc_180029E43
0x180029db7  xor     edi, edi
0x180029db9  jmp     loc_180029E43
0x180029dbe  mov     eax, 200h
0x180029dc3  mov     [rsp+470h+var_450], 0
0x180029dcc  mov     dword ptr [rsp+470h+Size], eax
0x180029dd0  lea     r9, [rsp+470h+Size]
0x180029dd5  mov     dword ptr [rsp+470h+Size+4], eax
0x180029dd9  lea     r8, [rbp+370h+Buf1]
0x180029de0  mov     rax, [rbx]
0x180029de3  mov     rdx, r14
0x180029de6  mov     rcx, rbx
0x180029de9  mov     rax, [rax+30h]
0x180029ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df2  test    eax, eax
0x180029df4  js      short loc_180029E43
0x180029df6  mov     rax, [rbx]
0x180029df9  lea     r9, [rsp+470h+Size+4]
0x180029dfe  lea     r8, [rsp+470h+Buf2]
0x180029e03  mov     [rsp+470h+var_450], 0
0x180029e0c  mov     rdx, rsi
0x180029e0f  mov     rcx, rbx
0x180029e12  mov     rax, [rax+30h]
0x180029e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e1b  test    eax, eax
0x180029e1d  js      short loc_180029E43
0x180029e1f  mov     eax, dword ptr [rsp+470h+Size]
0x180029e23  cmp     eax, dword ptr [rsp+470h+Size+4]
0x180029e27  jnz     short loc_180029E43
0x180029e29  mov     r8d, eax; Size
0x180029e2c  lea     rdx, [rsp+470h+Buf2]; Buf2
0x180029e31  lea     rcx, [rbp+370h+Buf1]; Buf1
0x180029e38  call    memcmp_0
0x180029e3d  neg     eax
0x180029e3f  sbb     eax, eax
0x180029e41  and     edi, eax
0x180029e43  mov     rdx, [rbx]
0x180029e46  mov     rcx, rbx
0x180029e49  mov     rax, [rdx+10h]
0x180029e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e52  mov     eax, edi
0x180029e54  mov     rcx, [rbp+370h+var_20]
0x180029e5b  xor     rcx, rsp; StackCookie
0x180029e5e  call    __security_check_cookie
0x180029e63  lea     r11, [rsp+470h+var_10]
0x180029e6b  mov     rbx, [r11+20h]
0x180029e6f  mov     rsi, [r11+38h]
0x180029e73  mov     rsp, r11
0x180029e76  pop     r14
0x180029e78  pop     rdi
0x180029e79  pop     rbp
0x180029e7a  retn
```
