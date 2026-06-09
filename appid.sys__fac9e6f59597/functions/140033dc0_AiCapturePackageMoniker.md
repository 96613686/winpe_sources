# AiCapturePackageMoniker

- ea: `0x140033dc0`
- end: `0x140033f3c`
- name: `AiCapturePackageMoniker`
- size: `380`
- prototype: `__int64 __fastcall(struct _KPROCESS *, _BYTE *, bool *, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002b5e0`
- `0x14002cd1c`
- `0x1400373b0`

## callees

- `0x140002fc8`
- `0x140006a20`
- `0x140006c40`
- `0x140032a50`
- `0x140033dc0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140033f0d`
- `ntoskrnl!ObfDereferenceObject` at `0x140033f0d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140033e0b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140033e0b`
- `ntoskrnl!RtlQueryPackageClaims` at `0x140033e72`
- `ntoskrnl!RtlQueryPackageClaims` at `0x140033e72`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x140033e37`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x140033e37`

## pseudocode

```c
__int64 __fastcall AiCapturePackageMoniker(struct _KPROCESS *a1, _BYTE *a2, bool *a3, __int64 a4)
{
  int Policy_Internal; // edi
  PACCESS_TOKEN v8; // rbx
  _BYTE *v9; // r8
  _BYTE *v10; // rdx
  int v11; // edx
  void *v12; // rax
  void *v13; // rdi
  __int16 v14; // cx
  _BYTE v16[4]; // [rsp+40h] [rbp-168h] BYREF
  int v17; // [rsp+44h] [rbp-164h] BYREF
  size_t Size; // [rsp+48h] [rbp-160h] BYREF
  __int64 v19; // [rsp+50h] [rbp-158h] BYREF
  __int64 v20; // [rsp+58h] [rbp-150h] BYREF
  _BYTE Src[256]; // [rsp+60h] [rbp-148h] BYREF

  Size = 256;
  Policy_Internal = 0;
  v17 = 0;
  *a2 = 0;
  *(_OWORD *)a4 = 0;
  v16[0] = 0;
  v8 = PsReferencePrimaryToken(a1);
  if ( AiUseSystemAppIdentityOnly )
  {
    v9 = 0;
    v10 = v16;
  }
  else
  {
    v9 = v16;
    v10 = 0;
  }
  PsQueryProcessAttributesByToken(v8, v10, v9);
  if ( v16[0] )
  {
    Policy_Internal = RtlQueryPackageClaims(v8, Src, &Size, 0, 0, 0, 0, 0);
    if ( Policy_Internal >= 0 )
    {
      v19 = 0;
      v20 = 0;
      Policy_Internal = AppModelPolicy_GetPolicy_Internal(
                          (_DWORD)v8,
                          v11,
                          (unsigned int)&v17,
                          (unsigned int)&v20,
                          (__int64)&v19);
      if ( Policy_Internal >= 0 )
      {
        v12 = (void *)AiAlloc((unsigned int)Size);
        v13 = v12;
        if ( v12 )
        {
          memmove(v12, Src, Size);
          v14 = Size;
          *(_QWORD *)(a4 + 8) = v13;
          *(_WORD *)(a4 + 2) = v14;
          *(_WORD *)a4 = v14 - 2;
          if ( a3 )
            *a3 = v17 == 3473409;
          Policy_Internal = 0;
          *a2 = 1;
        }
        else
        {
          Policy_Internal = -1073741801;
        }
      }
    }
  }
  ObfDereferenceObject(v8);
  return (unsigned int)Policy_Internal;
}

```

## disassembly

```asm
0x140033dc0  push    rbx
0x140033dc2  push    rbp
0x140033dc3  push    rsi
0x140033dc4  push    rdi
0x140033dc5  push    r14
0x140033dc7  push    r15
0x140033dc9  sub     rsp, 178h
0x140033dd0  mov     rax, cs:__security_cookie
0x140033dd7  xor     rax, rsp
0x140033dda  mov     [rsp+1A8h+var_48], rax
0x140033de2  xor     ebp, ebp
0x140033de4  mov     [rsp+1A8h+Size], 100h
0x140033ded  mov     edi, ebp
0x140033def  mov     [rsp+1A8h+var_164], ebp
0x140033df3  xorps   xmm0, xmm0
0x140033df6  mov     [rdx], dil
0x140033df9  movups  xmmword ptr [r9], xmm0
0x140033dfd  mov     rsi, r9
0x140033e00  mov     [rsp+1A8h+var_168], dil
0x140033e05  mov     r15, r8
0x140033e08  mov     r14, rdx
0x140033e0b  call    cs:__imp_PsReferencePrimaryToken
0x140033e12  nop     dword ptr [rax+rax+00h]
0x140033e17  cmp     cs:AiUseSystemAppIdentityOnly, dil
0x140033e1e  mov     rbx, rax
0x140033e21  mov     rcx, rax
0x140033e24  jnz     short loc_140033E2F
0x140033e26  lea     r8, [rsp+1A8h+var_168]
0x140033e2b  xor     edx, edx
0x140033e2d  jmp     short loc_140033E37
0x140033e2f  xor     r8d, r8d
0x140033e32  lea     rdx, [rsp+1A8h+var_168]
0x140033e37  call    cs:__imp_PsQueryProcessAttributesByToken
0x140033e3e  nop     dword ptr [rax+rax+00h]
0x140033e43  cmp     [rsp+1A8h+var_168], dil
0x140033e48  jz      loc_140033F0A
0x140033e4e  mov     [rsp+1A8h+var_170], rbp
0x140033e53  lea     r8, [rsp+1A8h+Size]
0x140033e58  mov     [rsp+1A8h+var_178], rbp
0x140033e5d  lea     rdx, [rsp+1A8h+Src]
0x140033e62  mov     [rsp+1A8h+var_180], rbp
0x140033e67  xor     r9d, r9d
0x140033e6a  mov     rcx, rbx
0x140033e6d  mov     [rsp+1A8h+var_188], rbp
0x140033e72  call    cs:__imp_RtlQueryPackageClaims
0x140033e79  nop     dword ptr [rax+rax+00h]
0x140033e7e  mov     edi, eax
0x140033e80  test    eax, eax
0x140033e82  js      loc_140033F0A
0x140033e88  lea     rax, [rsp+1A8h+var_158]
0x140033e8d  mov     [rsp+1A8h+var_158], rbp
0x140033e92  lea     r9, [rsp+1A8h+var_150]
0x140033e97  mov     [rsp+1A8h+var_188], rax
0x140033e9c  lea     r8, [rsp+1A8h+var_164]
0x140033ea1  mov     [rsp+1A8h+var_150], rbp
0x140033ea6  mov     rcx, rbx
0x140033ea9  call    AppModelPolicy_GetPolicy_Internal
0x140033eae  mov     edi, eax
0x140033eb0  test    eax, eax
0x140033eb2  js      short loc_140033F0A
0x140033eb4  mov     ecx, dword ptr [rsp+1A8h+Size]
0x140033eb8  call    AiAlloc
0x140033ebd  mov     rdi, rax
0x140033ec0  test    rax, rax
0x140033ec3  jnz     short loc_140033ECC
0x140033ec5  mov     edi, 0C0000017h
0x140033eca  jmp     short loc_140033F0A
0x140033ecc  mov     r8, [rsp+1A8h+Size]; Size
0x140033ed1  lea     rdx, [rsp+1A8h+Src]; Src
0x140033ed6  mov     rcx, rdi; void *
0x140033ed9  call    memmove
0x140033ede  mov     rcx, [rsp+1A8h+Size]
0x140033ee3  mov     [rsi+8], rdi
0x140033ee7  mov     [rsi+2], cx
0x140033eeb  lea     eax, [rcx-2]
0x140033eee  mov     [rsi], ax
0x140033ef1  test    r15, r15
0x140033ef4  jz      short loc_140033F04
0x140033ef6  cmp     [rsp+1A8h+var_164], 350001h
0x140033efe  setz    al
0x140033f01  mov     [r15], al
0x140033f04  mov     edi, ebp
0x140033f06  mov     byte ptr [r14], 1
0x140033f0a  mov     rcx, rbx; Object
0x140033f0d  call    cs:__imp_ObfDereferenceObject
0x140033f14  nop     dword ptr [rax+rax+00h]
0x140033f19  mov     eax, edi
0x140033f1b  mov     rcx, [rsp+1A8h+var_48]
0x140033f23  xor     rcx, rsp; StackCookie
0x140033f26  call    __security_check_cookie
0x140033f2b  add     rsp, 178h
0x140033f32  pop     r15
0x140033f34  pop     r14
0x140033f36  pop     rdi
0x140033f37  pop     rsi
0x140033f38  pop     rbp
0x140033f39  pop     rbx
0x140033f3a  retn
```
