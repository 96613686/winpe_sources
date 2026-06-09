# LibRaw::parse_fuji_thumbnail(int)

- ea: `0x180082010`
- end: `0x1800821fd`
- name: `?parse_fuji_thumbnail@LibRaw@@IEAAXH@Z`
- size: `493`
- prototype: `void __fastcall(LibRaw *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800546b0`

## callees

- `0x180002a00`
- `0x180008f30`
- `0x180044d60`
- `0x180082010`
- `0x1800b0ea0`
- `0x1800b4010`

## string_xrefs

- `0x180082038`: `http://ns.adobe.com/xap/1.0/`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LibRaw::parse_fuji_thumbnail(LibRaw *this, int a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rbp
  __int16 v7; // r14
  unsigned __int16 v8; // ax
  __int64 v9; // rsi
  __int64 v10; // rdi
  void *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  _OWORD Buf2[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE Buf1[32]; // [rsp+50h] [rbp-48h] BYREF

  v3 = (__int64 *)*((_QWORD *)this + 47659);
  v4 = *v3;
  strcpy((char *)Buf2, "http://ns.adobe.com/xap/1.0/");
  v5 = a2;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(v4 + 32))(v3);
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
    *((_QWORD *)this + 47659),
    v5,
    0);
  v7 = *((_WORD *)this + 190704);
  *((_WORD *)this + 190704) = 19018;
  if ( LibRaw::get2(this) == 0xFFD8 )
  {
    while ( 1 )
    {
      v8 = LibRaw::get2(this);
      if ( v8 != 0xFFE1 && v8 != 0xFFE2 )
        break;
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 32LL))(*((_QWORD *)this + 47659));
      v10 = LibRaw::get2(this);
      if ( (unsigned int)v10 > 0x1F
        && (*(unsigned int (__fastcall **)(_QWORD, _BYTE *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
             *((_QWORD *)this + 47659),
             Buf1,
             1,
             29) == 29
        && !memcmp(Buf1, Buf2, 0x1Du) )
      {
        *((_DWORD *)this + 157) = v10 - 31;
        v11 = LibRaw::calloc(this, (unsigned int)(v10 - 31 + 1), 1u);
        v12 = *((_QWORD *)this + 47659);
        v13 = *((unsigned int *)this + 157);
        *((_QWORD *)this + 79) = v11;
        *(_BYTE *)((*(unsigned int (__fastcall **)(__int64, void *, __int64, __int64))(*(_QWORD *)v12 + 16LL))(
                     v12,
                     v11,
                     1,
                     v13)
                 + *((_QWORD *)this + 79)) = 0;
        break;
      }
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
        *((_QWORD *)this + 47659),
        v9 + v10,
        0);
    }
  }
  v14 = *((_QWORD *)this + 47659);
  *((_WORD *)this + 190704) = v7;
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, v6, 0);
}

```

## disassembly

```asm
0x180082010  mov     [rsp+arg_18], rbx
0x180082015  push    rbp
0x180082016  push    rdi
0x180082017  push    r14
0x180082019  sub     rsp, 80h
0x180082020  mov     rax, cs:__security_cookie
0x180082027  xor     rax, rsp
0x18008202a  mov     [rsp+98h+var_28], rax
0x18008202f  mov     eax, dword ptr cs:aHttpNsAdobeCom+18h; "1.0/"
0x180082035  mov     rbx, rcx
0x180082038  movups  xmm0, xmmword ptr cs:aHttpNsAdobeCom; "http://ns.adobe.com/xap/1.0/"
0x18008203f  mov     rcx, [rcx+5D158h]
0x180082046  mov     dword ptr [rsp+98h+var_50], eax
0x18008204a  movzx   eax, byte ptr cs:aHttpNsAdobeCom+1Ch; ""
0x180082051  mov     [rsp+98h+var_50+4], al
0x180082055  mov     rax, [rcx]
0x180082058  movups  [rsp+98h+Buf2], xmm0
0x18008205d  movsxd  rdi, edx
0x180082060  movsd   xmm0, qword ptr cs:aHttpNsAdobeCom+10h; "com/xap/1.0/"
0x180082068  mov     rax, [rax+20h]
0x18008206c  movsd   [rsp+98h+var_58], xmm0
0x180082072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082077  mov     rcx, [rbx+5D158h]
0x18008207e  mov     rbp, rax
0x180082081  mov     rdx, rdi
0x180082084  mov     r8, [rcx]
0x180082087  mov     rax, [r8+18h]
0x18008208b  xor     r8d, r8d
0x18008208e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082093  movzx   r14d, word ptr [rbx+5D1E0h]
0x18008209b  mov     rcx, rbx; this
0x18008209e  mov     word ptr [rbx+5D1E0h], 4A4Ah
0x1800820a7  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x1800820ac  mov     ecx, 0FFD8h
0x1800820b1  cmp     ax, cx
0x1800820b4  jnz     loc_1800821BB
0x1800820ba  mov     [rsp+98h+arg_10], rsi
0x1800820c2  mov     rcx, rbx; this
0x1800820c5  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x1800820ca  add     ax, 1Fh
0x1800820ce  cmp     ax, 1
0x1800820d2  ja      loc_1800821B3
0x1800820d8  mov     rcx, [rbx+5D158h]
0x1800820df  mov     rax, [rcx]
0x1800820e2  mov     rax, [rax+20h]
0x1800820e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820eb  mov     rcx, rbx; this
0x1800820ee  mov     rsi, rax
0x1800820f1  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x1800820f6  movzx   edi, ax
0x1800820f9  cmp     edi, 1Fh
0x1800820fc  jbe     short loc_180082140
0x1800820fe  mov     rcx, [rbx+5D158h]
0x180082105  mov     r9d, 1Dh
0x18008210b  mov     r8d, 1
0x180082111  mov     rdx, [rcx]
0x180082114  mov     rax, [rdx+10h]
0x180082118  lea     rdx, [rsp+98h+Buf1]
0x18008211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082122  cmp     eax, 1Dh
0x180082125  jnz     short loc_180082140
0x180082127  mov     r8d, 1Dh; Size
0x18008212d  lea     rdx, [rsp+98h+Buf2]; Buf2
0x180082132  lea     rcx, [rsp+98h+Buf1]; Buf1
0x180082137  call    memcmp
0x18008213c  test    eax, eax
0x18008213e  jz      short loc_18008215F
0x180082140  mov     rcx, [rbx+5D158h]
0x180082147  lea     rdx, [rsi+rdi]
0x18008214b  xor     r8d, r8d
0x18008214e  mov     rax, [rcx]
0x180082151  mov     rax, [rax+18h]
0x180082155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008215a  jmp     loc_1800820C2
0x18008215f  lea     eax, [rdi-1Fh]
0x180082162  mov     r8d, 1; unsigned __int64
0x180082168  lea     edx, [rax+1]; unsigned __int64
0x18008216b  mov     [rbx+274h], eax
0x180082171  mov     rcx, rbx; this
0x180082174  call    ?calloc@LibRaw@@IEAAPEAX_K0@Z; LibRaw::calloc(unsigned __int64,unsigned __int64)
0x180082179  mov     rcx, [rbx+5D158h]
0x180082180  mov     r10, rax
0x180082183  mov     r9d, [rbx+274h]
0x18008218a  mov     r8d, 1
0x180082190  mov     [rbx+278h], rax
0x180082197  mov     rdx, [rcx]
0x18008219a  mov     rax, [rdx+10h]
0x18008219e  mov     rdx, r10
0x1800821a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800821a6  mov     ecx, eax
0x1800821a8  mov     rax, [rbx+278h]
0x1800821af  mov     byte ptr [rcx+rax], 0
0x1800821b3  mov     rsi, [rsp+98h+arg_10]
0x1800821bb  mov     rcx, [rbx+5D158h]
0x1800821c2  xor     r8d, r8d
0x1800821c5  mov     [rbx+5D1E0h], r14w
0x1800821cd  mov     rdx, rbp
0x1800821d0  mov     rax, [rcx]
0x1800821d3  mov     rax, [rax+18h]
0x1800821d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800821dc  mov     rcx, [rsp+98h+var_28]
0x1800821e1  xor     rcx, rsp; StackCookie
0x1800821e4  call    __security_check_cookie
0x1800821e9  mov     rbx, [rsp+98h+arg_18]
0x1800821f1  add     rsp, 80h
0x1800821f8  pop     r14
0x1800821fa  pop     rdi
0x1800821fb  pop     rbp
0x1800821fc  retn
```
