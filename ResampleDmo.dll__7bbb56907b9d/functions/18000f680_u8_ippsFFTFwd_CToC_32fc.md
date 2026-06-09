# u8_ippsFFTFwd_CToC_32fc

- ea: `0x18000f680`
- end: `0x18000f80b`
- name: `u8_ippsFFTFwd_CToC_32fc`
- size: `395`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: ``

## callers

- `0x180047aa0`
- `0x1800496a0`
- `0x1800588dc`
- `0x1800589cc`
- `0x180058b94`
- `0x180058d0c`

## callees

- `0x18000a5f0`
- `0x18000baf0`
- `0x18000bb10`
- `0x18000bb30`
- `0x18000bb70`
- `0x18000bbc0`
- `0x18000bd40`
- `0x18000bf00`
- `0x18000c4f0`
- `0x18000f680`
- `0x180011020`
- `0x180011040`
- `0x180011594`
- `0x18002c320`
- `0x18002c8d0`
- `0x18002f090`
- `0x180030ed9`
- `0x1800406c0`

## pseudocode

```c
__int64 __fastcall u8_ippsFFTFwd_CToC_32fc(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbp
  _QWORD *v5; // rbx
  int v10; // ecx
  unsigned int v11; // r14d
  __int64 v12; // rcx

  v4 = *(int *)(a3 + 4);
  v5 = 0;
  if ( (int)v4 > 3 )
  {
    v10 = *(_DWORD *)(a3 + 24);
    if ( v10 > 0 )
    {
      if ( a4 )
      {
        v5 = (_QWORD *)(a4 + (-(int)a4 & 0x1F));
      }
      else
      {
        v5 = px_ippsMalloc_8u(v10);
        if ( !v5 )
          return 4294967287LL;
      }
    }
    v11 = 1 << v4;
    if ( (int)v4 > 16 )
    {
      if ( (int)v4 > 17 )
      {
        u8_ipps_cFftFwd_Large_32fc(a3, a1, a2, v4, (__int64)v5);
LABEL_20:
        if ( v5 && !a4 )
          m7_ippsFree((__int64)v5);
        return 0;
      }
      if ( a1 == a2 )
        u8_ipps_BitRev1_C(a2, v11, *(_QWORD *)(a3 + 32));
      else
        u8_ipps_BitRev2_C(a1, a2, v11, *(_QWORD *)(a3 + 32));
      u8_ipps_cRadix4Fwd_32fc(a2, v11, *(_QWORD *)(a3 + 40), (_DWORD)v5, 1);
    }
    else
    {
      u8_ipps_cRadix4FwdNorm_32fc(a1, a2, v11, *(_QWORD *)(a3 + 40), *(_QWORD *)(a3 + 32), (__int64)v5);
    }
    if ( *(_DWORD *)(a3 + 8) )
      px_ipps_rbMpy1_32f(v12, a2, 2 * v11);
    goto LABEL_20;
  }
  if ( *(_DWORD *)(a3 + 8) )
    ((void (__fastcall *)(__int64, __int64))funcs_18000F6DD[v4])(a1, a2);
  else
    ((void (__fastcall *)(__int64, __int64))funcs_18000F6FB[v4])(a1, a2);
  return 0;
}

```

## disassembly

```asm
0x18000f680  mov     rax, rsp
0x18000f683  mov     [rax+8], rbx
0x18000f687  mov     [rax+10h], rbp
0x18000f68b  mov     [rax+18h], rsi
0x18000f68f  mov     [rax+20h], rdi
0x18000f693  push    r12
0x18000f695  push    r14
0x18000f697  push    r15
0x18000f699  sub     rsp, 30h
0x18000f69d  movsxd  rbp, dword ptr [r8+4]
0x18000f6a1  xor     ebx, ebx
0x18000f6a3  mov     r12, r9
0x18000f6a6  mov     rdi, r8
0x18000f6a9  mov     rsi, rdx
0x18000f6ac  mov     r15, rcx
0x18000f6af  cmp     ebp, 3
0x18000f6b2  jg      short loc_18000F702
0x18000f6b4  cmp     [r8+8], ebx
0x18000f6b8  lea     rbx, __ImageBase
0x18000f6bf  jz      short loc_18000F6E4
0x18000f6c1  mov     rbx, (funcs_18000F6DD - 180000000h)[rbx+rbp*8]
0x18000f6c9  mov     rcx, rbx; this
0x18000f6cc  call    cs:__guard_check_icall_fptr; CWMDSP1in1outDMO::EndOfProcessing(void) ...
0x18000f6d2  mov     rdx, rsi
0x18000f6d5  mov     rcx, r15
0x18000f6d8  movss   xmm2, dword ptr [rdi+10h]
0x18000f6dd  call    rbx
0x18000f6df  jmp     loc_18000F7EA
0x18000f6e4  mov     rbx, (funcs_18000F6FB - 180000000h)[rbx+rbp*8]
0x18000f6ec  mov     rcx, rbx; this
0x18000f6ef  call    cs:__guard_check_icall_fptr; CWMDSP1in1outDMO::EndOfProcessing(void) ...
0x18000f6f5  mov     rdx, rsi
0x18000f6f8  mov     rcx, r15
0x18000f6fb  call    rbx
0x18000f6fd  jmp     loc_18000F7EA
0x18000f702  mov     ecx, [r8+18h]
0x18000f706  test    ecx, ecx
0x18000f708  jle     short loc_18000F71B
0x18000f70a  test    r9, r9
0x18000f70d  jz      short loc_18000F74D
0x18000f70f  mov     rbx, r9
0x18000f712  neg     rbx
0x18000f715  and     ebx, 1Fh
0x18000f718  add     rbx, r9
0x18000f71b  mov     ecx, ebp
0x18000f71d  mov     r14d, 1
0x18000f723  shl     r14d, cl
0x18000f726  cmp     ebp, 10h
0x18000f729  jg      short loc_18000F762
0x18000f72b  mov     rax, [rdi+20h]
0x18000f72f  mov     r9, [rdi+28h]
0x18000f733  mov     r8d, r14d
0x18000f736  mov     rdx, rsi
0x18000f739  mov     rcx, r15
0x18000f73c  mov     [rsp+48h+var_20], rbx
0x18000f741  mov     [rsp+48h+var_28], rax
0x18000f746  call    u8_ipps_cRadix4FwdNorm_32fc
0x18000f74b  jmp     short loc_18000F7A9
0x18000f74d  call    px_ippsMalloc_8u
0x18000f752  mov     rbx, rax
0x18000f755  test    rax, rax
0x18000f758  jnz     short loc_18000F71B
0x18000f75a  lea     eax, [rbx-9]
0x18000f75d  jmp     loc_18000F7EC
0x18000f762  cmp     ebp, 11h
0x18000f765  jg      short loc_18000F7C2
0x18000f767  cmp     r15, rsi
0x18000f76a  jz      short loc_18000F780
0x18000f76c  mov     r9, [rdi+20h]
0x18000f770  mov     r8d, r14d
0x18000f773  mov     rdx, rsi
0x18000f776  mov     rcx, r15
0x18000f779  call    u8_ipps_BitRev2_C
0x18000f77e  jmp     short loc_18000F78F
0x18000f780  mov     r8, [rdi+20h]
0x18000f784  mov     edx, r14d
0x18000f787  mov     rcx, rsi
0x18000f78a  call    u8_ipps_BitRev1_C
0x18000f78f  mov     r8, [rdi+28h]
0x18000f793  mov     r9, rbx
0x18000f796  mov     edx, r14d
0x18000f799  mov     rcx, rsi
0x18000f79c  mov     dword ptr [rsp+48h+var_28], 1
0x18000f7a4  call    u8_ipps_cRadix4Fwd_32fc
0x18000f7a9  cmp     dword ptr [rdi+8], 0
0x18000f7ad  jz      short loc_18000F7D8
0x18000f7af  movss   xmm0, dword ptr [rdi+10h]
0x18000f7b4  lea     r8d, [r14+r14]
0x18000f7b8  mov     rdx, rsi
0x18000f7bb  call    px_ipps_rbMpy1_32f
0x18000f7c0  jmp     short loc_18000F7D8
0x18000f7c2  mov     r9d, ebp
0x18000f7c5  mov     r8, rsi
0x18000f7c8  mov     rdx, r15
0x18000f7cb  mov     rcx, rdi
0x18000f7ce  mov     [rsp+48h+var_28], rbx
0x18000f7d3  call    u8_ipps_cFftFwd_Large_32fc
0x18000f7d8  test    rbx, rbx
0x18000f7db  jz      short loc_18000F7EA
0x18000f7dd  test    r12, r12
0x18000f7e0  jnz     short loc_18000F7EA
0x18000f7e2  mov     rcx, rbx
0x18000f7e5  call    m7_ippsFree
0x18000f7ea  xor     eax, eax
0x18000f7ec  mov     rbx, [rsp+48h+arg_0]
0x18000f7f1  mov     rbp, [rsp+48h+arg_8]
0x18000f7f6  mov     rsi, [rsp+48h+arg_10]
0x18000f7fb  mov     rdi, [rsp+48h+arg_18]
0x18000f800  add     rsp, 30h
0x18000f804  pop     r15
0x18000f806  pop     r14
0x18000f808  pop     r12
0x18000f80a  retn
```
