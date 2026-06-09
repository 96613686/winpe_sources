# WPP_RECORDER_SF_S

- ea: `0x1400014cc`
- end: `0x1400015c6`
- name: `WPP_RECORDER_SF_S`
- size: `250`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140018008`
- `0x14001812c`
- `0x140018234`
- `0x14001833c`
- `0x140018804`

## callees

- `0x1400014cc`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400015aa`
- `WppRecorder!WppAutoLogTrace` at `0x1400015aa`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_S(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6)
{
  const char *v6; // rbx
  __int64 v7; // rdi
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  const char *v13; // rcx
  bool v14; // zf
  int v16; // [rsp+20h] [rbp-58h]

  v6 = a6;
  v7 = -1;
  v10 = 10;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    if ( a6 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&a6[2 * v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v12 = 10;
    }
    v13 = a6;
    if ( !a6 )
      v13 = L"NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      a4,
      v13,
      v12,
      0);
  }
  v14 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( *(_WORD *)&a6[2 * v7] );
    v10 = 2 * v7 + 2;
    v14 = a6 == 0;
  }
  if ( v14 )
    v6 = L"NULL";
  LOWORD(v16) = a4;
  return WppAutoLogTrace(a1, 0, 4, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids, v16, v6, v10, 0);
}

```

## disassembly

```asm
0x1400014cc  push    rbx
0x1400014ce  push    rbp
0x1400014cf  push    rsi
0x1400014d0  push    rdi
0x1400014d1  push    r12
0x1400014d3  push    r14
0x1400014d5  push    r15
0x1400014d7  sub     rsp, 40h
0x1400014db  mov     rax, cs:WPP_GLOBAL_Control
0x1400014e2  lea     r12, aNull_0; "NULL"
0x1400014e9  mov     rbx, [rsp+78h+arg_28]
0x1400014f1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400014f5  xor     r15d, r15d
0x1400014f8  movzx   ebp, r9w
0x1400014fc  mov     r14, rcx
0x1400014ff  mov     edx, [rax+2Ch]
0x140001502  lea     esi, [rdi+0Bh]
0x140001505  test    dl, 8
0x140001508  jz      short loc_140001568
0x14000150a  test    rbx, rbx
0x14000150d  jz      short loc_140001526
0x14000150f  mov     rax, rdi
0x140001512  inc     rax
0x140001515  cmp     [rbx+rax*2], r15w
0x14000151a  jnz     short loc_140001512
0x14000151c  lea     rdx, ds:2[rax*2]
0x140001524  jmp     short loc_140001529
0x140001526  mov     rdx, rsi
0x140001529  mov     rax, cs:pfnWppTraceMessage
0x140001530  lea     r8, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140001537  test    rbx, rbx
0x14000153a  mov     [rsp+78h+var_48], r15
0x14000153f  mov     [rsp+78h+var_50], rdx
0x140001544  mov     rcx, rbx
0x140001547  cmovz   rcx, r12
0x14000154b  mov     r9d, ebp
0x14000154e  mov     [rsp+78h+var_58], rcx
0x140001553  mov     edx, 2Bh ; '+'
0x140001558  mov     rcx, cs:WPP_GLOBAL_Control
0x14000155f  mov     rcx, [rcx+18h]
0x140001563  call    _guard_dispatch_icall
0x140001568  test    rbx, rbx
0x14000156b  jz      short loc_140001582
0x14000156d  inc     rdi
0x140001570  cmp     [rbx+rdi*2], r15w
0x140001575  jnz     short loc_14000156D
0x140001577  lea     rsi, ds:2[rdi*2]
0x14000157f  test    rbx, rbx
0x140001582  cmovz   rbx, r12
0x140001586  mov     [rsp+78h+var_40], r15
0x14000158b  xor     edx, edx
0x14000158d  mov     [rsp+78h+var_48], rsi
0x140001592  mov     [rsp+78h+var_50], rbx
0x140001597  lea     r9, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14000159e  mov     rcx, r14
0x1400015a1  mov     word ptr [rsp+78h+var_58], bp
0x1400015a6  lea     r8d, [rdx+4]
0x1400015aa  call    cs:__imp_WppAutoLogTrace
0x1400015b1  nop     dword ptr [rax+rax+00h]
0x1400015b6  add     rsp, 40h
0x1400015ba  pop     r15
0x1400015bc  pop     r14
0x1400015be  pop     r12
0x1400015c0  pop     rdi
0x1400015c1  pop     rsi
0x1400015c2  pop     rbp
0x1400015c3  pop     rbx
0x1400015c4  retn
```
