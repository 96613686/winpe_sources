# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180001fe4`
- end: `0x180002185`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `__int64 __fastcall(void *Src, struct std::filesystem::path *, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000297c`
- `0x180002a14`
- `0x180002bd8`
- `0x180002f78`

## callees

- `0x180001d7c`
- `0x180001fe4`
- `0x180002198`
- `0x1800048a8`
- `0x180015870`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
std::filesystem::path *__fastcall std::filesystem::operator/(
        std::filesystem::path *Src,
        struct std::filesystem::path *a2,
        _QWORD *a3)
{
  struct std::filesystem::path *v4; // rsi
  __int64 v6; // r13
  _DWORD *v7; // r15
  __int64 v8; // rcx
  unsigned __int8 v9; // r12
  size_t v10; // r14
  unsigned __int64 v11; // rdi
  std::filesystem::path *v12; // rbp
  _WORD *v13; // rcx
  std::filesystem::path *v14; // rax

  v4 = a2;
  v6 = a3[2];
  v7 = a3;
  if ( a3[3] > 7u )
    v7 = (_DWORD *)*a3;
  if ( !v6 || 2 * v6 >= 4 && (*v7 & 0xFFFFFFDF) - 3801153 < 0x1A || *(_WORD *)v7 == 92 || *(_WORD *)v7 == 47 )
  {
    std::filesystem::path::path(Src, a2);
    std::filesystem::path::operator/=(Src, (std::filesystem *)a3);
    return Src;
  }
  v8 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(struct std::filesystem::path **)a2;
  if ( v8 == 2 )
  {
    if ( (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 < 0x1A )
      goto LABEL_12;
  }
  else if ( !v8 )
  {
    goto LABEL_12;
  }
  v10 = 2 * v8;
  if ( *((_WORD *)v4 + v8 - 1) != 92 && *(_WORD *)((char *)v4 + v10 - 2) != 47 )
  {
    v9 = 1;
    goto LABEL_13;
  }
LABEL_12:
  v9 = 0;
  v10 = 2 * v8;
LABEL_13:
  v11 = v6 + v8 + v9;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( v11 <= 7 )
    *((_QWORD *)Src + 2) = v11;
  else
    std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(Src);
  v12 = Src;
  if ( *((_QWORD *)Src + 3) > 7u )
    v12 = *(std::filesystem::path **)Src;
  memmove(v12, v4, v10);
  v13 = (_WORD *)((char *)v12 + v10);
  if ( v9 )
    *v13++ = 92;
  memmove(v13, v7, 2 * v6);
  *((_QWORD *)Src + 2) = v11;
  v14 = Src;
  if ( *((_QWORD *)Src + 3) > 7u )
    v14 = *(std::filesystem::path **)Src;
  *((_WORD *)v14 + v11) = 0;
  return Src;
}

```

## disassembly

```asm
0x180001fe4  mov     [rsp+arg_8], rbx
0x180001fe9  mov     [rsp+arg_0], rcx
0x180001fee  push    rbp
0x180001fef  push    rsi
0x180001ff0  push    rdi
0x180001ff1  push    r12
0x180001ff3  push    r13
0x180001ff5  push    r14
0x180001ff7  push    r15
0x180001ff9  sub     rsp, 20h
0x180001ffd  mov     rdi, r8
0x180002000  mov     rsi, rdx
0x180002003  mov     rbx, rcx
0x180002006  mov     r10d, 1
0x18000200c  mov     [rsp+58h+arg_10], r10d
0x180002011  mov     r13, [r8+10h]
0x180002015  mov     r15, r8
0x180002018  cmp     qword ptr [r8+18h], 7
0x18000201d  jbe     short loc_180002022
0x18000201f  mov     r15, [r8]
0x180002022  lea     rax, ds:0[r13*2]
0x18000202a  xor     edx, edx
0x18000202c  test    r13, r13
0x18000202f  jz      loc_180002150
0x180002035  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002039  mov     r8d, 0FFFFFFDFh
0x18000203f  mov     r9d, 3A0041h
0x180002045  cmp     rax, 4
0x180002049  jl      short loc_18000205D
0x18000204b  mov     eax, [r15]
0x18000204e  and     eax, r8d
0x180002051  sub     eax, r9d
0x180002054  cmp     eax, 1Ah
0x180002057  jb      loc_180002150
0x18000205d  mov     r11d, 5Ch ; '\'
0x180002063  cmp     [r15], r11w
0x180002067  jz      loc_180002150
0x18000206d  cmp     word ptr [r15], 2Fh ; '/'
0x180002072  jz      loc_180002150
0x180002078  mov     rcx, [rsi+10h]
0x18000207c  cmp     qword ptr [rsi+18h], 7
0x180002081  jbe     short loc_180002086
0x180002083  mov     rsi, [rsi]
0x180002086  cmp     rcx, 2
0x18000208a  jnz     short loc_1800020D7
0x18000208c  mov     eax, [rsi]
0x18000208e  and     eax, r8d
0x180002091  sub     eax, r9d
0x180002094  cmp     eax, 1Ah
0x180002097  jnb     short loc_1800020DC
0x180002099  mov     r12b, dl
0x18000209c  lea     r14, [rcx+rcx]
0x1800020a0  movzx   edi, r12b
0x1800020a4  add     rdi, rcx
0x1800020a7  add     rdi, r13
0x1800020aa  xorps   xmm0, xmm0
0x1800020ad  movups  xmmword ptr [rbx], xmm0
0x1800020b0  mov     [rbx+10h], rdx
0x1800020b4  mov     qword ptr [rbx+18h], 7
0x1800020bc  mov     [rbx], dx
0x1800020bf  mov     [rsp+58h+arg_10], r10d
0x1800020c4  cmp     rdi, 7
0x1800020c8  jbe     short loc_1800020F6
0x1800020ca  mov     rdx, rdi
0x1800020cd  mov     rcx, rbx; Src
0x1800020d0  call    ??$_Reallocate_grow_by@V_lambda_d27e2b2d334e86d578b418f53091db3c_@@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_d27e2b2d334e86d578b418f53091db3c_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_d27e2b2d334e86d578b418f53091db3c_,>(unsigned __int64,_lambda_d27e2b2d334e86d578b418f53091db3c_)
0x1800020d5  jmp     short loc_1800020FA
0x1800020d7  test    rcx, rcx
0x1800020da  jz      short loc_180002099
0x1800020dc  lea     r14, [rcx+rcx]
0x1800020e0  cmp     [r14+rsi-2], r11w
0x1800020e6  jz      short loc_180002099
0x1800020e8  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x1800020ef  jz      short loc_180002099
0x1800020f1  mov     r12b, r10b
0x1800020f4  jmp     short loc_1800020A0
0x1800020f6  mov     [rbx+10h], rdi
0x1800020fa  mov     rbp, rbx
0x1800020fd  cmp     qword ptr [rbx+18h], 7
0x180002102  jbe     short loc_180002107
0x180002104  mov     rbp, [rbx]
0x180002107  mov     r8, r14; Size
0x18000210a  mov     rdx, rsi; Src
0x18000210d  mov     rcx, rbp; void *
0x180002110  call    memmove
0x180002115  lea     rcx, [r14+rbp]
0x180002119  xor     esi, esi
0x18000211b  test    r12b, r12b
0x18000211e  jz      short loc_180002129
0x180002120  mov     word ptr [rcx], 5Ch ; '\'
0x180002125  add     rcx, 2; void *
0x180002129  lea     r8, ds:0[r13*2]; Size
0x180002131  mov     rdx, r15; Src
0x180002134  call    memmove
0x180002139  mov     [rbx+10h], rdi
0x18000213d  mov     rax, rbx
0x180002140  cmp     qword ptr [rbx+18h], 7
0x180002145  jbe     short loc_18000214A
0x180002147  mov     rax, [rbx]
0x18000214a  mov     [rax+rdi*2], si
0x18000214e  jmp     short loc_18000216D
0x180002150  mov     rdx, rsi; struct std::filesystem::path *
0x180002153  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180002158  nop
0x180002159  mov     [rsp+58h+arg_10], 3
0x180002161  mov     rdx, rdi; void *
0x180002164  mov     rcx, rbx; Src
0x180002167  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000216c  nop
0x18000216d  mov     rax, rbx
0x180002170  mov     rbx, [rsp+58h+arg_8]
0x180002175  add     rsp, 20h
0x180002179  pop     r15
0x18000217b  pop     r14
0x18000217d  pop     r13
0x18000217f  pop     r12
0x180002181  pop     rdi
0x180002182  pop     rsi
0x180002183  pop     rbp
0x180002184  retn
```
