# walTryBeginRead

- ea: `0x180044d28`
- end: `0x1800450c0`
- name: `walTryBeginRead`
- size: `920`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180044ccc`
- `0x180047028`

## callees

- `0x180044d28`
- `0x1800450d0`
- `0x180045440`
- `0x18004643c`
- `0x1800464a4`
- `0x180047294`
- `0x180058a94`
- `0x18006feec`
- `0x1800789c0`
- `0x1800af614`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044ff9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044ff9`

## pseudocode

```c
__int64 __fastcall walTryBeginRead(_QWORD *a1, _DWORD *a2, int a3, int *a4)
{
  int v5; // eax
  unsigned int v8; // edi
  __int64 result; // rax
  __int64 v10; // r13
  unsigned int v11; // r12d
  unsigned int v12; // r15d
  int v13; // ebp
  int i; // esi
  unsigned int v15; // r14d
  int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // ecx
  int j; // esi
  __int64 v20; // rdx
  __int64 v21; // rdx
  ULONG_PTR Arguments[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+40h] [rbp-48h]

  v5 = ++*a4;
  if ( *a4 > 5 )
  {
    if ( v5 > 100 )
      return 15;
    v21 = 1;
    if ( v5 >= 10 )
      v21 = (unsigned int)(39 * (v5 - 9) * (v5 - 9));
    (*(void (__fastcall **)(_QWORD, __int64))(*a1 + 112LL))(*a1, v21);
  }
  v8 = 0;
  if ( !a3 )
  {
    if ( *((_BYTE *)a1 + 70) )
      return walBeginShmUnreliable(a1, a2);
    result = walIndexReadHdr((__int64)a1, a2);
    v8 = result;
    if ( (_DWORD)result == 5 )
    {
      if ( !*(_QWORD *)a1[6] )
        return 0xFFFFFFFFLL;
      result = walLockShared(a1, 2);
      if ( !(_DWORD)result )
      {
        v20 = 2;
LABEL_52:
        walUnlockShared(a1, v20);
        return 0xFFFFFFFFLL;
      }
      if ( (_DWORD)result == 5 )
        return 261;
      return result;
    }
    if ( (_DWORD)result )
      return result;
    if ( *((_BYTE *)a1 + 70) )
      return walBeginShmUnreliable(a1, a2);
  }
  sehInjectFault();
  v10 = *(_QWORD *)a1[6];
  sehInjectFault();
  if ( !a3 && *(_DWORD *)(v10 + 96) == *((_DWORD *)a1 + 22) )
  {
    if ( *((_BYTE *)a1 + 63) )
    {
      v8 = 0;
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)a1[1] + 112LL))(a1[1], 3, 1, 6);
      if ( !v8 )
        *((_DWORD *)a1 + 35) |= 8u;
    }
    if ( *((_BYTE *)a1 + 63) != 2 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)a1[1] + 120LL))(a1[1]);
    if ( !v8 )
    {
      sehInjectFault();
      if ( !memcmp_0(*(const void **)a1[6], a1 + 9, 0x30u) )
      {
        *((_WORD *)a1 + 30) = 0;
        return 0;
      }
      v20 = 3;
      goto LABEL_52;
    }
    if ( v8 != 5 )
      return v8;
  }
  v11 = *((_DWORD *)a1 + 22);
  v12 = 0;
  v13 = 0;
  for ( i = 1; i < 5; ++i )
  {
    v15 = *(_DWORD *)(v10 + 4LL * (unsigned int)i + 100);
    v16 = (int)qword_1800D0A00;
    if ( qword_1800D0A00 )
      v16 = qword_1800D0A00(650);
    if ( v16 )
    {
      v23 = v16;
      *(_OWORD *)Arguments = 0;
      RaiseException(0xC0000006, 0, 3u, Arguments);
    }
    if ( v15 <= v11 && v12 <= v15 )
    {
      v12 = v15;
      v13 = i;
    }
  }
  if ( (*((_BYTE *)a1 + 66) & 2) != 0 )
    goto LABEL_26;
  if ( v12 < v11 || !v13 )
  {
    for ( j = 1; j < 5; ++j )
    {
      result = walLockExclusive(a1, (unsigned int)(j + 3), 1);
      v8 = result;
      if ( !(_DWORD)result )
      {
        v12 = v11;
        v13 = j;
        *(_DWORD *)(v10 + 4LL * j + 100) = v11;
        walUnlockExclusive(a1, (unsigned int)(j + 3), 1);
        break;
      }
      if ( (_DWORD)result != 5 )
        return result;
    }
LABEL_26:
    if ( !v13 )
    {
      result = 0xFFFFFFFFLL;
      if ( v8 != 5 )
        return 1288;
      return result;
    }
  }
  v17 = v13 + 3;
  if ( *((_BYTE *)a1 + 63) )
  {
LABEL_30:
    *((_DWORD *)a1 + 30) = *(_DWORD *)(v10 + 96) + 1;
    sehInjectFault();
    if ( *((_BYTE *)a1 + 63) != 2 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)a1[1] + 120LL))(a1[1]);
    if ( *(_DWORD *)(v10 + 4LL * v13 + 100) == v12 )
    {
      sehInjectFault();
      if ( !memcmp_0(*(const void **)a1[6], a1 + 9, 0x30u) )
      {
        *((_WORD *)a1 + 30) = v13;
        return 0;
      }
    }
    v20 = v17;
    goto LABEL_52;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)a1[1] + 112LL))(a1[1], v17, 1);
  if ( !v18 )
  {
    *((_DWORD *)a1 + 35) |= 1 << v17;
    goto LABEL_30;
  }
  if ( (_BYTE)v18 == 5 )
    return (unsigned int)-1;
  return v18;
}

```

## disassembly

```asm
0x180044d28  mov     [rsp+arg_10], rbx
0x180044d2d  push    rbp
0x180044d2e  push    rsi
0x180044d2f  push    rdi
0x180044d30  push    r12
0x180044d32  push    r13
0x180044d34  push    r14
0x180044d36  push    r15
0x180044d38  sub     rsp, 50h
0x180044d3c  mov     rax, cs:__security_cookie
0x180044d43  xor     rax, rsp
0x180044d46  mov     [rsp+88h+var_40], rax
0x180044d4b  inc     dword ptr [r9]
0x180044d4e  mov     ebp, r8d
0x180044d51  mov     eax, [r9]
0x180044d54  mov     rsi, rdx
0x180044d57  mov     rbx, rcx
0x180044d5a  cmp     eax, 5
0x180044d5d  jg      loc_180045035
0x180044d63  xor     r14d, r14d
0x180044d66  mov     edi, r14d
0x180044d69  test    ebp, ebp
0x180044d6b  jnz     short loc_180044D9F
0x180044d6d  cmp     [rbx+46h], r14b
0x180044d71  jnz     loc_180045025
0x180044d77  mov     rdx, rsi
0x180044d7a  mov     rcx, rbx
0x180044d7d  call    walIndexReadHdr
0x180044d82  mov     edi, eax
0x180044d84  cmp     eax, 5
0x180044d87  jz      loc_180045068
0x180044d8d  test    eax, eax
0x180044d8f  jnz     loc_180044F0E
0x180044d95  cmp     [rbx+46h], r14b
0x180044d99  jnz     loc_180045025
0x180044d9f  call    sehInjectFault
0x180044da4  mov     rax, [rbx+30h]
0x180044da8  mov     r13, [rax]
0x180044dab  call    sehInjectFault
0x180044db0  mov     esi, 3
0x180044db5  test    ebp, ebp
0x180044db7  jnz     short loc_180044E1C
0x180044db9  mov     ecx, [rbx+58h]
0x180044dbc  mov     eax, [r13+60h]
0x180044dc0  cmp     eax, ecx
0x180044dc2  jnz     short loc_180044E1C
0x180044dc4  cmp     [rbx+3Fh], r14b
0x180044dc8  jnz     loc_18004509A
0x180044dce  mov     rcx, [rbx+8]
0x180044dd2  lea     r9d, [rsi+3]
0x180044dd6  lea     r8d, [rsi-2]
0x180044dda  mov     edx, esi
0x180044ddc  mov     rax, [rcx]
0x180044ddf  mov     rax, [rax+70h]
0x180044de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044de8  mov     edi, eax
0x180044dea  test    eax, eax
0x180044dec  jnz     short loc_180044DF5
0x180044dee  or      dword ptr [rbx+8Ch], 8
0x180044df5  cmp     byte ptr [rbx+3Fh], 2
0x180044df9  jz      short loc_180044E0B
0x180044dfb  mov     rcx, [rbx+8]
0x180044dff  mov     rax, [rcx]
0x180044e02  mov     rax, [rax+78h]
0x180044e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e0b  test    edi, edi
0x180044e0d  jz      loc_180044F9A
0x180044e13  cmp     edi, 5
0x180044e16  jnz     loc_1800450A9
0x180044e1c  mov     r12d, [rbx+58h]
0x180044e20  mov     r15d, r14d
0x180044e23  mov     ebp, r14d
0x180044e26  mov     esi, 1
0x180044e2b  mov     eax, esi
0x180044e2d  mov     r14d, [r13+rax*4+64h]
0x180044e32  mov     rax, cs:qword_1800D0A00
0x180044e39  test    rax, rax
0x180044e3c  jnz     loc_180045004
0x180044e42  test    eax, eax
0x180044e44  jnz     loc_180044FDA
0x180044e4a  cmp     r14d, r12d
0x180044e4d  ja      short loc_180044E59
0x180044e4f  cmp     r15d, r14d
0x180044e52  ja      short loc_180044E59
0x180044e54  mov     r15d, r14d
0x180044e57  mov     ebp, esi
0x180044e59  inc     esi
0x180044e5b  cmp     esi, 5
0x180044e5e  jl      short loc_180044E2B
0x180044e60  test    byte ptr [rbx+42h], 2
0x180044e64  jz      loc_180044F33
0x180044e6a  test    ebp, ebp
0x180044e6c  jz      loc_180044FC7
0x180044e72  cmp     byte ptr [rbx+3Fh], 0
0x180044e76  lea     edi, [rbp+3]
0x180044e79  jnz     short loc_180044EB0
0x180044e7b  mov     rcx, [rbx+8]
0x180044e7f  mov     r9d, 6
0x180044e85  mov     edx, edi
0x180044e87  mov     rax, [rcx]
0x180044e8a  lea     r8d, [r9-5]
0x180044e8e  mov     rax, [rax+70h]
0x180044e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e97  mov     ecx, eax
0x180044e99  test    eax, eax
0x180044e9b  jnz     loc_180044F8A
0x180044ea1  mov     ecx, edi
0x180044ea3  mov     eax, 1
0x180044ea8  shl     eax, cl
0x180044eaa  or      [rbx+8Ch], eax
0x180044eb0  mov     eax, [r13+60h]
0x180044eb4  inc     eax
0x180044eb6  mov     [rbx+78h], eax
0x180044eb9  call    sehInjectFault
0x180044ebe  cmp     byte ptr [rbx+3Fh], 2
0x180044ec2  jz      short loc_180044ED4
0x180044ec4  mov     rcx, [rbx+8]
0x180044ec8  mov     rax, [rcx]
0x180044ecb  mov     rax, [rax+78h]
0x180044ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ed4  movsxd  rax, ebp
0x180044ed7  mov     ecx, [r13+rax*4+64h]
0x180044edc  cmp     ecx, r15d
0x180044edf  jnz     loc_180045013
0x180044ee5  call    sehInjectFault
0x180044eea  mov     rcx, [rbx+30h]
0x180044eee  lea     rdx, [rbx+48h]; Buf2
0x180044ef2  mov     r8d, 30h ; '0'; Size
0x180044ef8  mov     rcx, [rcx]; Buf1
0x180044efb  call    memcmp_0
0x180044f00  test    eax, eax
0x180044f02  jnz     loc_180045013
0x180044f08  mov     [rbx+3Ch], bp
0x180044f0c  xor     eax, eax
0x180044f0e  mov     rcx, [rsp+88h+var_40]
0x180044f13  xor     rcx, rsp; StackCookie
0x180044f16  call    __security_check_cookie
0x180044f1b  mov     rbx, [rsp+88h+arg_10]
0x180044f23  add     rsp, 50h
0x180044f27  pop     r15
0x180044f29  pop     r14
0x180044f2b  pop     r13
0x180044f2d  pop     r12
0x180044f2f  pop     rdi
0x180044f30  pop     rsi
0x180044f31  pop     rbp
0x180044f32  retn
0x180044f33  cmp     r15d, r12d
0x180044f36  jb      short loc_180044F40
0x180044f38  test    ebp, ebp
0x180044f3a  jnz     loc_180044E72
0x180044f40  mov     esi, 1
0x180044f45  cmp     esi, 5
0x180044f48  jge     loc_180044E6A
0x180044f4e  mov     r8d, 1
0x180044f54  lea     edx, [rsi+3]
0x180044f57  mov     rcx, rbx
0x180044f5a  call    walLockExclusive
0x180044f5f  mov     edi, eax
0x180044f61  test    eax, eax
0x180044f63  jnz     loc_1800450B0
0x180044f69  movsxd  rax, esi
0x180044f6c  lea     r8d, [rdi+1]
0x180044f70  lea     edx, [rsi+3]
0x180044f73  mov     rcx, rbx
0x180044f76  mov     r15d, r12d
0x180044f79  mov     ebp, esi
0x180044f7b  mov     [r13+rax*4+64h], r12d
0x180044f80  call    walUnlockExclusive
0x180044f85  jmp     loc_180044E6A
0x180044f8a  or      eax, 0FFFFFFFFh
0x180044f8d  cmp     cl, 5
0x180044f90  cmovz   ecx, eax
0x180044f93  mov     eax, ecx
0x180044f95  jmp     loc_180044F0E
0x180044f9a  call    sehInjectFault
0x180044f9f  mov     rcx, [rbx+30h]
0x180044fa3  lea     rdx, [rbx+48h]; Buf2
0x180044fa7  mov     r8d, 30h ; '0'; Size
0x180044fad  mov     rcx, [rcx]; Buf1
0x180044fb0  call    memcmp_0
0x180044fb5  test    eax, eax
0x180044fb7  jnz     loc_1800450A2
0x180044fbd  mov     [rbx+3Ch], r14w
0x180044fc2  jmp     loc_180044F0C
0x180044fc7  or      eax, 0FFFFFFFFh
0x180044fca  mov     ecx, 508h
0x180044fcf  cmp     edi, 5
0x180044fd2  cmovnz  eax, ecx
0x180044fd5  jmp     loc_180044F0E
0x180044fda  xor     edx, edx; dwExceptionFlags
0x180044fdc  cdqe
0x180044fde  xorps   xmm0, xmm0
0x180044fe1  mov     [rsp+88h+var_48], rax
0x180044fe6  lea     r9, [rsp+88h+Arguments]; lpArguments
0x180044feb  mov     ecx, 0C0000006h; dwExceptionCode
0x180044ff0  movups  xmmword ptr [rsp+88h+Arguments], xmm0
0x180044ff5  lea     r8d, [rdx+3]; nNumberOfArguments
0x180044ff9  call    cs:__imp_RaiseException
0x180044fff  jmp     loc_180044E4A
0x180045004  mov     ecx, 28Ah
0x180045009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004500e  jmp     loc_180044E42
0x180045013  mov     edx, edi
0x180045015  mov     rcx, rbx
0x180045018  call    walUnlockShared
0x18004501d  or      eax, 0FFFFFFFFh
0x180045020  jmp     loc_180044F0E
0x180045025  mov     rdx, rsi
0x180045028  mov     rcx, rbx
0x18004502b  call    walBeginShmUnreliable
0x180045030  jmp     loc_180044F0E
0x180045035  cmp     eax, 64h ; 'd'
0x180045038  jle     short loc_180045044
0x18004503a  mov     eax, 0Fh
0x18004503f  jmp     loc_180044F0E
0x180045044  mov     edx, 1
0x180045049  cmp     eax, 0Ah
0x18004504c  jl      short loc_180045057
0x18004504e  add     eax, 0FFFFFFF7h
0x180045051  imul    eax, eax
0x180045054  imul    edx, eax, 27h ; '''
0x180045057  mov     rcx, [rcx]
0x18004505a  mov     rax, [rcx+70h]
0x18004505e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045063  jmp     loc_180044D63
0x180045068  mov     rax, [rbx+30h]
0x18004506c  cmp     [rax], r14
0x18004506f  jz      short loc_18004501D
0x180045071  mov     edx, 2
0x180045076  mov     rcx, rbx
0x180045079  call    walLockShared
0x18004507e  test    eax, eax
0x180045080  jnz     short loc_180045087
0x180045082  lea     edx, [rax+2]
0x180045085  jmp     short loc_180045015
0x180045087  cmp     eax, 5
0x18004508a  jnz     loc_180044F0E
0x180045090  mov     eax, 105h
0x180045095  jmp     loc_180044F0E
0x18004509a  mov     edi, r14d
0x18004509d  jmp     loc_180044DF5
0x1800450a2  mov     edx, esi
0x1800450a4  jmp     loc_180045015
0x1800450a9  mov     eax, edi
0x1800450ab  jmp     loc_180044F0E
0x1800450b0  cmp     eax, 5
0x1800450b3  jnz     loc_180044F0E
0x1800450b9  inc     esi
0x1800450bb  jmp     loc_180044F45
```
