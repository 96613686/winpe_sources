# LibRaw::nikon_read_curve(void)

- ea: `0x1800491d0`
- end: `0x1800493c3`
- name: `?nikon_read_curve@LibRaw@@IEAAXXZ`
- size: `499`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000adf0`

## callees

- `0x180002a00`
- `0x180044d60`
- `0x180045470`
- `0x1800491d0`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::nikon_read_curve(LibRaw *this)
{
  __int16 v2; // r14
  __int16 v3; // si
  unsigned int v4; // ebp
  int v5; // edi
  __int64 v6; // r8
  int v7; // r14d
  _WORD *v8; // rsi
  __int64 v9; // r15
  __int64 v10; // r10
  char *v11; // r9
  int v12; // r8d
  int v13; // edx
  unsigned __int16 v14; // [rsp+20h] [rbp-38h] BYREF

  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
    *((_QWORD *)this + 47659),
    *((_QWORD *)this + 47681),
    0);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
  if ( v2 == 73 || v3 == 88 )
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 47659) + 24LL))(
      *((_QWORD *)this + 47659),
      2110,
      1);
  LibRaw::read_shorts(this, &v14, 4u);
  v4 = (1 << *((_DWORD *)this + 95378)) & 0x7FFF;
  v5 = v4;
  v6 = LibRaw::get2(this);
  if ( (unsigned int)v6 > 1 )
    v5 = (int)v4 / ((int)v6 - 1);
  if ( v2 == 68 )
  {
    if ( v3 == 32 )
    {
      if ( v5 > 0 )
        goto LABEL_12;
    }
    else if ( v3 == 64 && v5 > 3 )
    {
      v5 /= 4;
      v4 >>= 2;
LABEL_12:
      v7 = 0;
      if ( (_WORD)v6 )
      {
        v8 = (_WORD *)((char *)this + 5392);
        v9 = v6;
        do
        {
          *v8 = LibRaw::get2(this);
          v8 += v5;
          --v9;
        }
        while ( v9 );
      }
      v10 = v4;
      if ( v4 )
      {
        v11 = (char *)this + 5392;
        do
        {
          v11 += 2;
          v12 = v7;
          v13 = v7 % v5;
          ++v7;
          *((_WORD *)v11 - 1) = (v13 * *((unsigned __int16 *)this + v12 - v13 + v5 + 2696)
                               + (v5 - v13) * *((unsigned __int16 *)this + v12 - v13 + 2696))
                              / v5;
          --v10;
        }
        while ( v10 );
      }
      return;
    }
  }
  else if ( v2 == 70 )
  {
    return;
  }
  if ( (unsigned __int16)v6 <= 0x4001u )
    LibRaw::read_shorts(this, (unsigned __int16 *)this + 2696, v6);
}

```

## disassembly

```asm
0x1800491d0  push    rbx
0x1800491d2  push    rbp
0x1800491d3  push    rsi
0x1800491d4  push    rdi
0x1800491d5  push    r14
0x1800491d7  sub     rsp, 30h
0x1800491db  mov     rax, cs:__security_cookie
0x1800491e2  xor     rax, rsp
0x1800491e5  mov     [rsp+58h+var_30], rax
0x1800491ea  mov     rbx, rcx
0x1800491ed  xor     r8d, r8d
0x1800491f0  mov     rcx, [rcx+5D158h]
0x1800491f7  mov     rdx, [rbx+5D208h]
0x1800491fe  mov     rax, [rcx]
0x180049201  mov     rax, [rax+18h]
0x180049205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004920a  mov     rcx, [rbx+5D158h]
0x180049211  mov     rax, [rcx]
0x180049214  mov     rax, [rax+30h]
0x180049218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004921d  mov     rdx, [rbx+5D158h]
0x180049224  mov     r14d, eax
0x180049227  mov     rcx, [rdx]
0x18004922a  mov     rax, [rcx+30h]
0x18004922e  mov     rcx, rdx
0x180049231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049236  mov     esi, eax
0x180049238  mov     ebp, 1
0x18004923d  cmp     r14w, 49h ; 'I'
0x180049242  jz      short loc_18004924A
0x180049244  cmp     si, 58h ; 'X'
0x180049248  jnz     short loc_180049268
0x18004924a  mov     r9, [rbx+5D158h]
0x180049251  mov     r8d, ebp
0x180049254  mov     edx, 83Eh
0x180049259  mov     rcx, [r9]
0x18004925c  mov     rax, [rcx+18h]
0x180049260  mov     rcx, r9
0x180049263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049268  mov     r8d, 4; unsigned int
0x18004926e  lea     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x180049273  mov     rcx, rbx; this
0x180049276  call    ?read_shorts@LibRaw@@IEAAXPEAGI@Z; LibRaw::read_shorts(ushort *,uint)
0x18004927b  mov     ecx, [rbx+5D248h]
0x180049281  shl     ebp, cl
0x180049283  mov     rcx, rbx; this
0x180049286  and     ebp, 7FFFh
0x18004928c  mov     edi, ebp
0x18004928e  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x180049293  movzx   r8d, ax; unsigned int
0x180049297  cmp     r8d, 1
0x18004929b  jbe     short loc_1800492A8
0x18004929d  mov     eax, ebp
0x18004929f  lea     ecx, [r8-1]
0x1800492a3  cdq
0x1800492a4  idiv    ecx
0x1800492a6  mov     edi, eax
0x1800492a8  cmp     r14w, 44h ; 'D'
0x1800492ad  jnz     loc_18004938A
0x1800492b3  cmp     si, 20h ; ' '
0x1800492b7  jz      short loc_1800492DD
0x1800492b9  cmp     si, 40h ; '@'
0x1800492bd  jnz     loc_180049391
0x1800492c3  cmp     edi, 3
0x1800492c6  jle     loc_180049391
0x1800492cc  mov     eax, edi
0x1800492ce  cdq
0x1800492cf  and     edx, 3
0x1800492d2  lea     edi, [rdx+rax]
0x1800492d5  sar     edi, 2
0x1800492d8  shr     ebp, 2
0x1800492db  jmp     short loc_1800492E5
0x1800492dd  test    edi, edi
0x1800492df  jle     loc_180049391
0x1800492e5  xor     r14d, r14d
0x1800492e8  cmp     r14w, r8w
0x1800492ec  jnb     short loc_180049326
0x1800492ee  mov     [rsp+58h+arg_8], r12
0x1800492f3  lea     rsi, [rbx+1510h]
0x1800492fa  movsxd  r12, edi
0x1800492fd  mov     [rsp+58h+arg_10], r15
0x180049302  add     r12, r12
0x180049305  mov     r15, r8
0x180049308  mov     rcx, rbx; this
0x18004930b  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x180049310  mov     [rsi], ax
0x180049313  add     rsi, r12
0x180049316  sub     r15, 1
0x18004931a  jnz     short loc_180049308
0x18004931c  mov     r15, [rsp+58h+arg_10]
0x180049321  mov     r12, [rsp+58h+arg_8]
0x180049326  mov     r10d, ebp
0x180049329  test    ebp, ebp
0x18004932b  jz      short loc_1800493AB
0x18004932d  lea     r9, [rbx+1510h]
0x180049334  nop     dword ptr [rax+00h]
0x180049338  nop     dword ptr [rax+rax+00000000h]
0x180049340  mov     eax, r14d
0x180049343  lea     r9, [r9+2]
0x180049347  cdq
0x180049348  mov     r8d, r14d
0x18004934b  idiv    edi
0x18004934d  mov     ecx, edi
0x18004934f  inc     r14d
0x180049352  sub     ecx, edx
0x180049354  sub     r8d, edx
0x180049357  movsxd  rax, r8d
0x18004935a  movzx   eax, word ptr [rbx+rax*2+1510h]
0x180049362  imul    eax, ecx
0x180049365  lea     ecx, [r8+rdi]
0x180049369  movsxd  r8, ecx
0x18004936c  movzx   ecx, word ptr [rbx+r8*2+1510h]
0x180049375  imul    ecx, edx
0x180049378  add     eax, ecx
0x18004937a  cdq
0x18004937b  idiv    edi
0x18004937d  mov     [r9-2], ax
0x180049382  sub     r10, 1
0x180049386  jnz     short loc_180049340
0x180049388  jmp     short loc_1800493AB
0x18004938a  cmp     r14w, 46h ; 'F'
0x18004938f  jz      short loc_1800493AB
0x180049391  mov     eax, 4001h
0x180049396  cmp     r8w, ax
0x18004939a  ja      short loc_1800493AB
0x18004939c  lea     rdx, [rbx+1510h]; unsigned __int16 *
0x1800493a3  mov     rcx, rbx; this
0x1800493a6  call    ?read_shorts@LibRaw@@IEAAXPEAGI@Z; LibRaw::read_shorts(ushort *,uint)
0x1800493ab  mov     rcx, [rsp+58h+var_30]
0x1800493b0  xor     rcx, rsp; StackCookie
0x1800493b3  call    __security_check_cookie
0x1800493b8  add     rsp, 30h
0x1800493bc  pop     r14
0x1800493be  pop     rdi
0x1800493bf  pop     rsi
0x1800493c0  pop     rbp
0x1800493c1  pop     rbx
0x1800493c2  retn
```
