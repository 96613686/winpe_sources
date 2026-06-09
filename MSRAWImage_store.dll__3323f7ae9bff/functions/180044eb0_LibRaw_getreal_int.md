# LibRaw::getreal(int)

- ea: `0x180044eb0`
- end: `0x180045150`
- name: `?getreal@LibRaw@@IEAANH@Z`
- size: `672`
- prototype: `double __fastcall(LibRaw *__hidden this, int)`
- caller_count: `23`
- callee_count: `5`
- tags: ``

## callers

- `0x180050ee0`
- `0x180052970`
- `0x1800603b0`
- `0x180060640`
- `0x180061a90`
- `0x180062810`
- `0x180063c90`
- `0x180065900`
- `0x18006c0e0`
- `0x180075f80`
- `0x18007ff70`
- `0x180082a00`
- `0x180088f80`
- `0x18008c470`
- `0x18008cd00`
- `0x18008d6e0`
- `0x18008ed30`
- `0x18008ffb0`
- `0x1800906a0`
- `0x180090f80`
- `0x180091e70`
- `0x180092060`
- `0x1800922a0`

## callees

- `0x180002a00`
- `0x180044d60`
- `0x180044de0`
- `0x180044eb0`
- `0x1800b4010`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180044fd7`
- `WS2_32!__imp_ntohs` at `0x180044fd7`

## pseudocode

```c
double __fastcall LibRaw::getreal(LibRaw *this, int a2)
{
  unsigned int v3; // eax
  double result; // xmm0_8
  double v5; // xmm6_8
  double v6; // xmm1_8
  __m128i v8; // xmm0
  __int16 v9; // bx
  unsigned __int64 v10; // rbx
  char v11; // al
  __int64 v12; // rcx
  double v13; // [rsp+20h] [rbp-28h]

  switch ( a2 )
  {
    case 3:
      v3 = LibRaw::get2(this);
      goto LABEL_13;
    case 4:
      return (double)(int)LibRaw::get4(this);
    case 5:
    case 10:
      v5 = (double)(int)LibRaw::get4(this);
      v6 = (double)(int)LibRaw::get4(this);
      if ( v6 == 0.0 )
        return v5 / 1.0;
      else
        return v5 / v6;
    case 8:
      v8 = _mm_cvtsi32_si128((__int16)LibRaw::get2(this));
      goto LABEL_14;
    case 9:
      v3 = LibRaw::get4(this);
      goto LABEL_13;
    case 11:
      return COERCE_FLOAT(LibRaw::get4(this));
    case 12:
      v9 = *((_WORD *)this + 190704);
      v10 = 7 * ((v9 != 18761) ^ (unsigned __int64)(ntohs(0x1234u) == 4660));
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      v12 = *((_QWORD *)this + 47659);
      *((_BYTE *)&v13 + v10) = v11;
      *((_BYTE *)&v13 + (v10 ^ 1)) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
      *((_BYTE *)&v13 + (v10 ^ 2)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      *((_BYTE *)&v13 + (v10 ^ 3)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      *((_BYTE *)&v13 + (v10 ^ 4)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      *((_BYTE *)&v13 + (v10 ^ 5)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      *((_BYTE *)&v13 + (v10 ^ 6)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      *((_BYTE *)&v13 + (v10 ^ 7)) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
      return v13;
    default:
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 48LL))(*((_QWORD *)this + 47659));
LABEL_13:
      v8 = _mm_cvtsi32_si128(v3);
LABEL_14:
      *(_QWORD *)&result = *(_OWORD *)&_mm_cvtepi32_pd(v8);
      return result;
  }
}

```

## disassembly

```asm
0x180044eb0  push    rdi
0x180044eb2  sub     rsp, 40h
0x180044eb6  movaps  [rsp+48h+var_18], xmm6
0x180044ebb  mov     rax, cs:__security_cookie
0x180044ec2  xor     rax, rsp
0x180044ec5  mov     [rsp+48h+var_20], rax
0x180044eca  add     edx, 0FFFFFFFDh; switch 10 cases
0x180044ecd  mov     rdi, rcx
0x180044ed0  cmp     edx, 9
0x180044ed3  ja      def_180044EED; jumptable 0000000180044EED default case, cases 6,7
0x180044ed9  movsxd  rax, edx
0x180044edc  lea     rcx, __ImageBase
0x180044ee3  mov     edx, ds:(jpt_180044EED - 180000000h)[rcx+rax*4]
0x180044eea  add     rdx, rcx
0x180044eed  jmp     rdx; switch jump
0x180044eef  mov     rcx, rdi; jumptable 0000000180044EED case 3
0x180044ef2  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x180044ef7  movzx   eax, ax
0x180044efa  jmp     loc_180045106
0x180044eff  mov     rcx, rdi; jumptable 0000000180044EED case 4
0x180044f02  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044f07  mov     eax, eax
0x180044f09  xorps   xmm0, xmm0
0x180044f0c  cvtsi2sd xmm0, rax
0x180044f11  jmp     loc_18004510E
0x180044f16  mov     rcx, rdi; jumptable 0000000180044EED case 5
0x180044f19  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044f1e  mov     eax, eax
0x180044f20  xorps   xmm6, xmm6
0x180044f23  mov     rcx, rdi; this
0x180044f26  cvtsi2sd xmm6, rax
0x180044f2b  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044f30  mov     eax, eax
0x180044f32  xorps   xmm1, xmm1
0x180044f35  cvtsi2sd xmm1, rax
0x180044f3a  xorps   xmm0, xmm0
0x180044f3d  ucomisd xmm1, xmm0
0x180044f41  jp      short loc_180044F59
0x180044f43  jnz     short loc_180044F59
0x180044f45  movsd   xmm0, cs:__real@3ff0000000000000
0x180044f4d  divsd   xmm6, xmm0
0x180044f51  movaps  xmm0, xmm6
0x180044f54  jmp     loc_18004510E
0x180044f59  divsd   xmm6, xmm1
0x180044f5d  movaps  xmm0, xmm1
0x180044f60  movaps  xmm0, xmm6
0x180044f63  jmp     loc_18004510E
0x180044f68  mov     rcx, rdi; jumptable 0000000180044EED case 8
0x180044f6b  call    ?get2@LibRaw@@IEAAGXZ; LibRaw::get2(void)
0x180044f70  movsx   ecx, ax
0x180044f73  movd    xmm0, ecx
0x180044f77  jmp     loc_18004510A
0x180044f7c  mov     rcx, rdi; jumptable 0000000180044EED case 9
0x180044f7f  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044f84  jmp     loc_180045106
0x180044f89  mov     rcx, rdi; jumptable 0000000180044EED case 10
0x180044f8c  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044f91  mov     rcx, rdi; this
0x180044f94  movd    xmm6, eax
0x180044f98  cvtdq2pd xmm6, xmm6
0x180044f9c  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044fa1  movd    xmm1, eax
0x180044fa5  cvtdq2pd xmm1, xmm1
0x180044fa9  jmp     short loc_180044F3A
0x180044fab  mov     rcx, rdi; jumptable 0000000180044EED case 11
0x180044fae  call    ?get4@LibRaw@@IEAAIXZ; LibRaw::get4(void)
0x180044fb3  movd    xmm0, eax
0x180044fb7  cvtps2pd xmm0, xmm0
0x180044fba  jmp     loc_18004510E
0x180044fbf  mov     [rsp+48h+arg_8], rbx; jumptable 0000000180044EED case 12
0x180044fc4  movzx   ebx, word ptr [rdi+5D1E0h]
0x180044fcb  mov     [rsp+48h+arg_10], rsi
0x180044fd0  mov     esi, 1234h
0x180044fd5  mov     ecx, esi; netshort
0x180044fd7  call    cs:__imp_ntohs
0x180044fdd  mov     rcx, [rdi+5D158h]
0x180044fe4  xor     edx, edx
0x180044fe6  cmp     ax, si
0x180044fe9  mov     r8d, edx
0x180044fec  mov     eax, 4949h
0x180044ff1  setz    r8b
0x180044ff5  cmp     bx, ax
0x180044ff8  mov     rax, [rcx]
0x180044ffb  setnz   dl
0x180044ffe  xor     r8, rdx
0x180045001  imul    rbx, r8, 7
0x180045005  mov     rax, [rax+30h]
0x180045009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004500e  mov     rcx, [rdi+5D158h]
0x180045015  mov     byte ptr [rsp+rbx+48h+var_28], al
0x180045019  mov     rax, [rcx]
0x18004501c  mov     rax, [rax+30h]
0x180045020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045025  mov     rcx, rbx
0x180045028  xor     rcx, 1
0x18004502c  mov     byte ptr [rsp+rcx+48h+var_28], al
0x180045030  mov     rcx, [rdi+5D158h]
0x180045037  mov     rax, [rcx]
0x18004503a  mov     rax, [rax+30h]
0x18004503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045043  mov     rcx, rbx
0x180045046  xor     rcx, 2
0x18004504a  mov     byte ptr [rsp+rcx+48h+var_28], al
0x18004504e  mov     rcx, [rdi+5D158h]
0x180045055  mov     rax, [rcx]
0x180045058  mov     rax, [rax+30h]
0x18004505c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045061  mov     rcx, rbx
0x180045064  xor     rcx, 3
0x180045068  mov     byte ptr [rsp+rcx+48h+var_28], al
0x18004506c  mov     rcx, [rdi+5D158h]
0x180045073  mov     rax, [rcx]
0x180045076  mov     rax, [rax+30h]
0x18004507a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004507f  mov     rcx, rbx
0x180045082  xor     rcx, 4
0x180045086  mov     byte ptr [rsp+rcx+48h+var_28], al
0x18004508a  mov     rcx, [rdi+5D158h]
0x180045091  mov     rax, [rcx]
0x180045094  mov     rax, [rax+30h]
0x180045098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004509d  mov     rcx, rbx
0x1800450a0  xor     rcx, 5
0x1800450a4  mov     byte ptr [rsp+rcx+48h+var_28], al
0x1800450a8  mov     rcx, [rdi+5D158h]
0x1800450af  mov     rax, [rcx]
0x1800450b2  mov     rax, [rax+30h]
0x1800450b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450bb  mov     rcx, rbx
0x1800450be  xor     rcx, 6
0x1800450c2  mov     byte ptr [rsp+rcx+48h+var_28], al
0x1800450c6  mov     rcx, [rdi+5D158h]
0x1800450cd  mov     rax, [rcx]
0x1800450d0  mov     rax, [rax+30h]
0x1800450d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450d9  mov     rsi, [rsp+48h+arg_10]
0x1800450de  xor     rbx, 7
0x1800450e2  mov     byte ptr [rsp+rbx+48h+var_28], al
0x1800450e6  movsd   xmm0, [rsp+48h+var_28]
0x1800450ec  mov     rbx, [rsp+48h+arg_8]
0x1800450f1  jmp     short loc_18004510E
0x1800450f3  mov     rcx, [rdi+5D158h]; jumptable 0000000180044EED default case, cases 6,7
0x1800450fa  mov     rax, [rcx]
0x1800450fd  mov     rax, [rax+30h]
0x180045101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045106  movd    xmm0, eax
0x18004510a  cvtdq2pd xmm0, xmm0
0x18004510e  mov     rcx, [rsp+48h+var_20]
0x180045113  xor     rcx, rsp; StackCookie
0x180045116  call    __security_check_cookie
0x18004511b  movaps  xmm6, [rsp+48h+var_18]
0x180045120  add     rsp, 40h
0x180045124  pop     rdi
0x180045125  retn
```
