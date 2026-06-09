# PrjfCreateStreamContext

- ea: `0x1400020b4`
- end: `0x14000227f`
- name: `PrjfCreateStreamContext`
- size: `459`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400217a4`

## callees

- `0x1400020b4`
- `0x14000ba20`
- `0x14000d128`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14000213e`
- `ntoskrnl!ExUuidCreate` at `0x14000213e`
- `FLTMGR!FltReferenceContext` at `0x14000223e`
- `FLTMGR!FltReferenceContext` at `0x14000223e`
- `FLTMGR!FltAllocateContext` at `0x140002112`
- `FLTMGR!FltAllocateContext` at `0x140002112`
- `FLTMGR!FltReleaseContext` at `0x1400021cc`
- `FLTMGR!FltReleaseContext` at `0x1400021cc`

## pseudocode

```c
__int64 __fastcall PrjfCreateStreamContext(PFLT_CONTEXT Context, __int64 a2, __int64 a3, PFLT_CONTEXT *a4)
{
  NTSTATUS v8; // edi
  _OWORD *v9; // rax
  int v10; // edx
  int v11; // r8d
  PFLT_CONTEXT v12; // rcx
  PFLT_CONTEXT Contexta; // [rsp+60h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF

  Contexta = 0;
  Uuid = 0;
  v8 = FltAllocateContext(Globals, 8u, 0x30u, (POOL_TYPE)512, &Contexta);
  if ( v8 < 0 )
  {
LABEL_6:
    v12 = Contexta;
    goto LABEL_7;
  }
  v9 = Contexta;
  *(_OWORD *)Contexta = 0;
  v9[1] = 0;
  v9[2] = 0;
  v8 = ExUuidCreate(&Uuid);
  if ( v8 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        25,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        174,
        v8);
    }
    goto LABEL_6;
  }
  *(UUID *)((char *)Contexta + 24) = Uuid;
  if ( *(_BYTE *)(a2 + 21) )
  {
    *(_DWORD *)Contexta = 1;
  }
  else if ( *(_BYTE *)(a2 + 22) || *(_BYTE *)(a2 + 23) )
  {
    *(_DWORD *)Contexta = 2;
  }
  *((_BYTE *)Contexta + 44) = 1;
  FltReferenceContext(Context);
  *((_QWORD *)Contexta + 1) = Context;
  *((_QWORD *)Contexta + 2) = *(_QWORD *)(a2 + 8);
  if ( a3 )
    *((_DWORD *)Contexta + 1) = *(_DWORD *)(a3 + 60);
  v12 = 0;
  *a4 = Contexta;
  Contexta = 0;
LABEL_7:
  if ( v12 )
    FltReleaseContext(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400020b4  mov     [rsp-28h+arg_8], rbx
0x1400020b9  push    rbp
0x1400020ba  push    rsi
0x1400020bb  push    rdi
0x1400020bc  push    r14
0x1400020be  push    r15
0x1400020c0  mov     rbp, rsp
0x1400020c3  sub     rsp, 80h
0x1400020ca  mov     rax, cs:__security_cookie
0x1400020d1  xor     rax, rsp
0x1400020d4  mov     [rbp+var_8], rax
0x1400020d8  mov     rbx, rdx
0x1400020db  mov     [rbp+Context], 0
0x1400020e3  mov     edx, 8; ContextType
0x1400020e8  lea     rax, [rbp+Context]
0x1400020ec  mov     r15, r9
0x1400020ef  mov     [rsp+80h+ReturnedContext], rax; ReturnedContext
0x1400020f4  mov     rsi, r8
0x1400020f7  mov     r14, rcx
0x1400020fa  mov     rcx, cs:Globals; Filter
0x140002101  xorps   xmm0, xmm0
0x140002104  lea     r8d, [rdx+28h]; ContextSize
0x140002108  mov     r9d, 200h; PoolType
0x14000210e  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x140002112  call    cs:__imp_FltAllocateContext
0x140002119  nop     dword ptr [rax+rax+00h]
0x14000211e  mov     edi, eax
0x140002120  test    eax, eax
0x140002122  js      loc_1400021C3
0x140002128  mov     rax, [rbp+Context]
0x14000212c  lea     rcx, [rbp+Uuid]; Uuid
0x140002130  xorps   xmm0, xmm0
0x140002133  movups  xmmword ptr [rax], xmm0
0x140002136  movups  xmmword ptr [rax+10h], xmm0
0x14000213a  movups  xmmword ptr [rax+20h], xmm0
0x14000213e  call    cs:__imp_ExUuidCreate
0x140002145  nop     dword ptr [rax+rax+00h]
0x14000214a  mov     edi, eax
0x14000214c  test    eax, eax
0x14000214e  jns     loc_1400021FE
0x140002154  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000215a  lea     rax, WPP_RECORDER_INITIALIZED
0x140002161  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002168  setnz   r8b
0x14000216c  and     dl, 2
0x14000216f  jnz     short loc_140002176
0x140002171  test    r8b, r8b
0x140002174  jz      short loc_1400021C3
0x140002176  mov     r9, cs:WPP_GLOBAL_Control
0x14000217d  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002184  mov     [rsp+80h+var_30], edi
0x140002188  mov     ecx, 209h
0x14000218d  mov     [rsp+80h+var_38], 4AEh
0x140002195  mov     [rsp+80h+var_40], rax
0x14000219a  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400021a1  mov     r9, [r9+40h]
0x1400021a5  mov     [rsp+80h+var_48], rax
0x1400021aa  mov     [rsp+80h+var_50], 19h
0x1400021b1  mov     [rsp+80h+var_58], 9
0x1400021b9  mov     byte ptr [rsp+80h+ReturnedContext], 2
0x1400021be  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400021c3  mov     rcx, [rbp+Context]; Context
0x1400021c7  test    rcx, rcx
0x1400021ca  jz      short loc_1400021D8
0x1400021cc  call    cs:__imp_FltReleaseContext
0x1400021d3  nop     dword ptr [rax+rax+00h]
0x1400021d8  mov     eax, edi
0x1400021da  mov     rcx, [rbp+var_8]
0x1400021de  xor     rcx, rsp; StackCookie
0x1400021e1  call    __security_check_cookie
0x1400021e6  mov     rbx, [rsp+80h+arg_8]
0x1400021ee  add     rsp, 80h
0x1400021f5  pop     r15
0x1400021f7  pop     r14
0x1400021f9  pop     rdi
0x1400021fa  pop     rsi
0x1400021fb  pop     rbp
0x1400021fc  retn
0x1400021fe  mov     rax, [rbp+Context]
0x140002202  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x140002206  movdqu  xmmword ptr [rax+18h], xmm0
0x14000220b  cmp     byte ptr [rbx+15h], 0
0x14000220f  jz      short loc_14000221D
0x140002211  mov     rax, [rbp+Context]
0x140002215  mov     dword ptr [rax], 1
0x14000221b  jmp     short loc_140002233
0x14000221d  cmp     byte ptr [rbx+16h], 0
0x140002221  jnz     short loc_140002229
0x140002223  cmp     byte ptr [rbx+17h], 0
0x140002227  jz      short loc_140002233
0x140002229  mov     rax, [rbp+Context]
0x14000222d  mov     dword ptr [rax], 2
0x140002233  mov     rax, [rbp+Context]
0x140002237  mov     rcx, r14; Context
0x14000223a  mov     byte ptr [rax+2Ch], 1
0x14000223e  call    cs:__imp_FltReferenceContext
0x140002245  nop     dword ptr [rax+rax+00h]
0x14000224a  mov     rax, [rbp+Context]
0x14000224e  mov     [rax+8], r14
0x140002252  mov     rax, [rbp+Context]
0x140002256  mov     rcx, [rbx+8]
0x14000225a  mov     [rax+10h], rcx
0x14000225e  test    rsi, rsi
0x140002261  jz      short loc_14000226D
0x140002263  mov     rax, [rbp+Context]
0x140002267  mov     ecx, [rsi+3Ch]
0x14000226a  mov     [rax+4], ecx
0x14000226d  mov     rax, [rbp+Context]
0x140002271  xor     ecx, ecx
0x140002273  mov     [r15], rax
0x140002276  mov     [rbp+Context], rcx
0x14000227a  jmp     loc_1400021C7
```
