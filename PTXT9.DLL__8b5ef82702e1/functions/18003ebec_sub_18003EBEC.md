# sub_18003EBEC

- ea: `0x18003ebec`
- end: `0x18003edba`
- name: `sub_18003EBEC`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003e7f0`

## callees

- `0x18001aee0`
- `0x180036c14`
- `0x18003ebec`
- `0x18004d240`
- `0x18004df30`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003ec5a`
- `KERNEL32!GetTickCount` at `0x18003ec5a`

## string_xrefs

- `0x18003ec60`: `Temp%06d`

## pseudocode

```c
__int64 __fastcall sub_18003EBEC(_QWORD *a1, _WORD *a2)
{
  __int64 v2; // r13
  _QWORD *v3; // r12
  unsigned int v5; // edi
  int v6; // r15d
  __int64 v7; // rsi
  signed int TickCount; // eax
  _WORD *v9; // rcx
  int v10; // edx
  __int16 v11; // ax
  int v12; // eax
  __int64 v13; // r13
  int v14; // ebx
  void (__fastcall *v15)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *); // rax
  __int64 result; // rax
  __int64 v17; // rdx
  int i; // r15d
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v20; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v21; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v22[263]; // [rsp+52h] [rbp-AEh] BYREF
  _BYTE Src[2]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v24[526]; // [rsp+262h] [rbp+162h] BYREF

  v2 = *a1;
  v3 = a1;
  v20 = a1;
  v5 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(v2 + 56);
  v19 = *(_QWORD *)(v2 + 64);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( a2 && *a2 )
  {
    sub_18001AEE0(a2, Src);
  }
  else
  {
    v6 = -1;
    TickCount = GetTickCount();
    v9 = v22;
    v5 = ((TickCount >> 2) & 0xFFF) + 6;
    v10 = 262;
    do
    {
      if ( --v10 <= 0 )
        break;
      v11 = *(_WORD *)((char *)v9 + (char *)L"Temp%06d" - (char *)v22);
      *v9++ = v11;
    }
    while ( v11 );
    v21 = v9 - &v21 - 2;
    v22[v21] = 0;
    sub_180036C14(Src, 262, &v21, v5);
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v7 + 104LL))(v7, v2 + 74, v24);
  v13 = *v3;
  v14 = v12;
  if ( v12 < 0 && v6 )
  {
    for ( i = 0; i < 100; ++i )
    {
      if ( v14 >= 0 )
        break;
      sub_180036C14(Src, 262, &v21, i + v5);
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v7 + 104LL))(v7, v13 + 74, v24);
    }
    v3 = v20;
  }
  v15 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v7 + 32LL);
  if ( v14 < 0 )
  {
    v15(v7, v13 + 74, 0, 18, 0, &v19);
    *(_QWORD *)(*v3 + 64LL) = v19;
    return (unsigned int)v14;
  }
  else
  {
    result = ((__int64 (__fastcall *)(__int64, _BYTE *, _QWORD, __int64, _DWORD, __int64 *))v15)(
               v7,
               v24,
               0,
               18,
               0,
               &v19);
    v17 = *v3;
    if ( (int)result < 0 )
    {
      *(_QWORD *)(v17 + 64) = 0;
    }
    else
    {
      *(_QWORD *)(v17 + 64) = v19;
      sub_18001AEE0(Src, (void *)(v17 + 72));
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003ebec  mov     [rsp-8+arg_10], rbx
0x18003ebf1  push    rbp
0x18003ebf2  push    rsi
0x18003ebf3  push    rdi
0x18003ebf4  push    r12
0x18003ebf6  push    r13
0x18003ebf8  push    r14
0x18003ebfa  push    r15
0x18003ebfc  lea     rbp, [rsp-380h]
0x18003ec04  sub     rsp, 480h
0x18003ec0b  mov     rax, cs:__security_cookie
0x18003ec12  xor     rax, rsp
0x18003ec15  mov     [rbp+3B0h+var_40], rax
0x18003ec1c  mov     r13, [rcx]
0x18003ec1f  mov     r12, rcx
0x18003ec22  mov     [rsp+4B0h+var_468], rcx
0x18003ec27  xor     r14d, r14d
0x18003ec2a  mov     rbx, rdx
0x18003ec2d  mov     edi, r14d
0x18003ec30  mov     r15d, r14d
0x18003ec33  mov     rcx, [r13+40h]
0x18003ec37  mov     rsi, [r13+38h]
0x18003ec3b  mov     [rsp+4B0h+var_470], rcx
0x18003ec40  mov     rax, [rcx]
0x18003ec43  mov     rax, [rax+10h]
0x18003ec47  call    cs:__guard_dispatch_icall_fptr
0x18003ec4d  test    rbx, rbx
0x18003ec50  jnz     loc_18003ED8C
0x18003ec56  or      r15d, 0FFFFFFFFh
0x18003ec5a  call    cs:GetTickCount
0x18003ec60  lea     r8, aTemp06d; "Temp%06d"
0x18003ec67  mov     r14d, 106h
0x18003ec6d  mov     edi, eax
0x18003ec6f  lea     rcx, [rsp+4B0h+var_45E]
0x18003ec74  sar     edi, 2
0x18003ec77  lea     rax, [rsp+4B0h+var_45E]
0x18003ec7c  and     edi, 0FFFh
0x18003ec82  lea     r10d, [r15+3]
0x18003ec86  add     edi, 6
0x18003ec89  sub     r8, rax
0x18003ec8c  xor     r9d, r9d
0x18003ec8f  mov     edx, r14d
0x18003ec92  dec     edx
0x18003ec94  test    edx, edx
0x18003ec96  jle     short loc_18003ECA8
0x18003ec98  movzx   eax, word ptr [rcx+r8]
0x18003ec9d  mov     [rcx], ax
0x18003eca0  add     rcx, r10
0x18003eca3  test    ax, ax
0x18003eca6  jnz     short loc_18003EC92
0x18003eca8  lea     rax, [rsp+4B0h+var_460]
0x18003ecad  mov     edx, r14d
0x18003ecb0  sub     rcx, rax
0x18003ecb3  lea     r8, [rsp+4B0h+var_460]
0x18003ecb8  sar     rcx, 1
0x18003ecbb  sub     cx, r10w
0x18003ecbf  movzx   eax, cx
0x18003ecc2  lea     rcx, [rbp+3B0h+Src]
0x18003ecc9  mov     [rsp+4B0h+var_460], ax
0x18003ecce  mov     [rsp+rax*2+4B0h+var_45E], r9w
0x18003ecd4  mov     r9d, edi
0x18003ecd7  call    sub_180036C14
0x18003ecdc  mov     rax, [rsi]
0x18003ecdf  lea     rdx, [r13+4Ah]
0x18003ece3  lea     r8, [rbp+3B0h+var_24E]
0x18003ecea  mov     rcx, rsi
0x18003eced  mov     rax, [rax+68h]
0x18003ecf1  call    cs:__guard_dispatch_icall_fptr
0x18003ecf7  mov     r13, [r12]
0x18003ecfb  mov     ebx, eax
0x18003ecfd  test    eax, eax
0x18003ecff  js      loc_180051C92
0x18003ed05  mov     rax, [rsi]
0x18003ed08  lea     rcx, [rsp+4B0h+var_470]
0x18003ed0d  xor     edi, edi
0x18003ed0f  mov     [rsp+4B0h+var_488], rcx
0x18003ed14  xor     r8d, r8d
0x18003ed17  mov     [rsp+4B0h+var_490], edi
0x18003ed1b  mov     rcx, rsi
0x18003ed1e  mov     rax, [rax+20h]
0x18003ed22  lea     r9d, [rdi+12h]
0x18003ed26  test    ebx, ebx
0x18003ed28  js      loc_180051CED
0x18003ed2e  lea     rdx, [rbp+3B0h+var_24E]
0x18003ed35  call    cs:__guard_dispatch_icall_fptr
0x18003ed3b  mov     rdx, [r12]
0x18003ed3f  test    eax, eax
0x18003ed41  js      short loc_18003EDB3
0x18003ed43  mov     rax, [rsp+4B0h+var_470]
0x18003ed48  lea     r8d, [rdi+20h]
0x18003ed4c  mov     [rdx+40h], rax
0x18003ed50  lea     rcx, [rbp+3B0h+Src]; Src
0x18003ed57  add     rdx, 48h ; 'H'; void *
0x18003ed5b  call    sub_18001AEE0
0x18003ed60  xor     eax, eax
0x18003ed62  mov     rcx, [rbp+3B0h+var_40]
0x18003ed69  xor     rcx, rsp; StackCookie
0x18003ed6c  call    __security_check_cookie
0x18003ed71  mov     rbx, [rsp+4B0h+arg_10]
0x18003ed79  add     rsp, 480h
0x18003ed80  pop     r15
0x18003ed82  pop     r14
0x18003ed84  pop     r13
0x18003ed86  pop     r12
0x18003ed88  pop     rdi
0x18003ed89  pop     rsi
0x18003ed8a  pop     rbp
0x18003ed8b  retn
0x18003ed8c  cmp     [rbx], r14w
0x18003ed90  jz      loc_18003EC56
0x18003ed96  mov     r14d, 106h
0x18003ed9c  lea     rdx, [rbp+3B0h+Src]; void *
0x18003eda3  mov     r8d, r14d
0x18003eda6  mov     rcx, rbx; Src
0x18003eda9  call    sub_18001AEE0
0x18003edae  jmp     loc_18003ECDC
0x18003edb3  mov     [rdx+40h], rdi
0x18003edb7  jmp     short loc_18003ED62
0x180051c92  test    r15d, r15d
0x180051c95  jz      loc_18003ED05
0x180051c9b  xor     r12d, r12d
0x180051c9e  mov     r15d, r12d
0x180051ca1  test    ebx, ebx
0x180051ca3  jns     short loc_180051CE3
0x180051ca5  lea     r9d, [r15+rdi]
0x180051ca9  mov     edx, r14d
0x180051cac  lea     r8, [rsp+4B0h+var_460]
0x180051cb1  lea     rcx, [rbp+3B0h+Src]
0x180051cb8  call    sub_180036C14
0x180051cbd  mov     rax, [rsi]
0x180051cc0  lea     rdx, [r13+4Ah]
0x180051cc4  lea     r8, [rbp+3B0h+var_24E]
0x180051ccb  mov     rcx, rsi
0x180051cce  mov     rax, [rax+68h]
0x180051cd2  call    cs:__guard_dispatch_icall_fptr
0x180051cd8  inc     r15d
0x180051cdb  mov     ebx, eax
0x180051cdd  cmp     r15d, 64h ; 'd'
0x180051ce1  jl      short loc_180051CA1
0x180051ce3  mov     r12, [rsp+4B0h+var_468]
0x180051ce8  jmp     loc_18003ED05
0x180051ced  lea     rdx, [r13+4Ah]
0x180051cf1  call    cs:__guard_dispatch_icall_fptr
0x180051cf7  mov     rax, [rsp+4B0h+var_470]
0x180051cfc  mov     rcx, [r12]
0x180051d00  mov     [rcx+40h], rax
0x180051d04  mov     eax, ebx
0x180051d06  jmp     loc_18003ED62
```
