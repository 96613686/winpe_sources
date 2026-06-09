# CServiceModule::_EnableDisablePenProcessTypes(int)

- ea: `0x180012060`
- end: `0x180012319`
- name: `?_EnableDisablePenProcessTypes@CServiceModule@@AEAAHH@Z`
- size: `697`
- prototype: `__int64 __fastcall(const struct _GUID *this, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fa00`
- `0x180023bd0`
- `0x180025bbc`
- `0x180028964`

## callees

- `0x180012060`
- `0x180012320`
- `0x18001a174`
- `0x18001bbe0`
- `0x180031010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800120d9`
- `USER32!GetSystemMetrics` at `0x1800120d9`

## pseudocode

```c
__int64 __fastcall CServiceModule::_EnableDisablePenProcessTypes(const struct _GUID *this, int a2)
{
  unsigned __int64 v4; // r8
  const struct _GUID *v5; // rcx
  int ManualOverride; // ebx
  unsigned __int64 v7; // r8
  bool v8; // zf
  int v9; // eax
  _DWORD *v10; // rsi
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // r14d
  _DWORD *v14; // rsi
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  _DWORD *v18; // rsi
  int v19; // eax
  int v20; // ecx
  _DWORD *v21; // rsi
  int v22; // eax
  int v23; // ecx
  _DWORD *v24; // rsi
  int v25; // eax
  int v26; // ecx
  _DWORD *v27; // rdi
  int v28; // eax
  int v29; // ecx
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-38h] BYREF
  __int128 v32; // [rsp+24h] [rbp-34h]

  v4 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v4 )
    PrivateTraceEvent(this, 0x619u, v4, 1u);
  ManualOverride = GetManualOverride();
  v7 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v7 )
    PrivateTraceEvent(v5, 0x619u, v7, 2u);
  v31 = a2;
  v32 = 0;
  v8 = GetSystemMetrics(67) == 0;
  DWORD2(v32) = *(_DWORD *)&this[4].Data2;
  v9 = *(_DWORD *)&this[4].Data4[4];
  DWORD1(v32) = !v8;
  HIDWORD(v32) = v9;
  _mm_lfence();
  v10 = *(_DWORD **)&this[35].Data1;
  if ( ManualOverride == 2 )
  {
    v11 = 2;
  }
  else
  {
    v12 = v10[2];
    v11 = 0;
    if ( v12 != -1 )
    {
      if ( ((4 << v12) & ManualOverride) != 0 )
        v11 = 2;
      else
        v11 = ManualOverride & 1;
    }
  }
  LODWORD(v32) = v11;
  v13 = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v10 + 8LL))(v10, &v31);
  v10[3] = v13 != 0;
  v14 = *(_DWORD **)this[35].Data4;
  if ( ManualOverride == 2 )
  {
    v15 = 2;
  }
  else
  {
    v16 = v14[2];
    v15 = 0;
    if ( v16 != -1 )
    {
      if ( ((4 << v16) & ManualOverride) != 0 )
        v15 = 2;
      else
        v15 = ManualOverride & 1;
    }
  }
  LODWORD(v32) = v15;
  v17 = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v14 + 8LL))(v14, &v31);
  if ( v13 || v17 )
    v13 = 1;
  v14[3] = v17 != 0;
  v18 = *(_DWORD **)&this[36].Data1;
  if ( ManualOverride == 2 )
  {
    v19 = 2;
  }
  else
  {
    v20 = v18[2];
    v19 = 0;
    if ( v20 != -1 )
    {
      if ( ((4 << v20) & ManualOverride) != 0 )
        v19 = 2;
      else
        v19 = ManualOverride & 1;
    }
  }
  LODWORD(v32) = v19;
  v18[3] = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v18 + 8LL))(v18, &v31) != 0;
  v21 = *(_DWORD **)this[36].Data4;
  if ( ManualOverride == 2 )
  {
    v22 = 2;
  }
  else
  {
    v23 = v21[2];
    v22 = 0;
    if ( v23 != -1 )
    {
      if ( ((4 << v23) & ManualOverride) != 0 )
        v22 = 2;
      else
        v22 = ManualOverride & 1;
    }
  }
  LODWORD(v32) = v22;
  v21[3] = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v21 + 8LL))(v21, &v31) != 0;
  v24 = *(_DWORD **)&this[37].Data1;
  if ( ManualOverride == 2 )
  {
    v25 = 2;
  }
  else
  {
    v26 = v24[2];
    v25 = 0;
    if ( v26 != -1 )
    {
      if ( ((4 << v26) & ManualOverride) != 0 )
        v25 = 2;
      else
        v25 = ManualOverride & 1;
    }
  }
  LODWORD(v32) = v25;
  v24[3] = (*(__int64 (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v24 + 8LL))(v24, &v31) != 0;
  v27 = *(_DWORD **)this[37].Data4;
  if ( ManualOverride != 2 )
  {
    v29 = v27[2];
    v28 = 0;
    if ( v29 == -1 )
      goto LABEL_43;
    if ( ((4 << v29) & ManualOverride) == 0 )
    {
      v28 = ManualOverride & 1;
      goto LABEL_43;
    }
  }
  v28 = 2;
LABEL_43:
  LODWORD(v32) = v28;
  v8 = (*(unsigned int (__fastcall **)(_DWORD *, int *))(*(_QWORD *)v27 + 8LL))(v27, &v31) == 0;
  result = v13;
  v27[3] = !v8;
  return result;
}

```

## disassembly

```asm
0x180012060  mov     [rsp+arg_10], rbx
0x180012065  mov     [rsp+arg_18], rbp
0x18001206a  push    rsi
0x18001206b  push    rdi
0x18001206c  push    r14
0x18001206e  sub     rsp, 40h
0x180012072  mov     rax, cs:__security_cookie
0x180012079  xor     rax, rsp
0x18001207c  mov     [rsp+58h+var_20], rax
0x180012081  mov     rax, cs:WPP_GLOBAL_Control
0x180012088  mov     esi, edx
0x18001208a  mov     rdi, rcx
0x18001208d  mov     r8, [rax+38h]; unsigned __int64
0x180012091  test    r8, r8
0x180012094  jz      short loc_1800120A3
0x180012096  mov     r9b, 1; unsigned __int8
0x180012099  mov     edx, 619h; unsigned int
0x18001209e  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800120a3  call    ?GetManualOverride@@YAKXZ; GetManualOverride(void)
0x1800120a8  mov     ebx, eax
0x1800120aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800120b1  mov     r8, [rax+38h]; unsigned __int64
0x1800120b5  test    r8, r8
0x1800120b8  jz      short loc_1800120C7
0x1800120ba  mov     r9b, 2; unsigned __int8
0x1800120bd  mov     edx, 619h; unsigned int
0x1800120c2  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800120c7  xorps   xmm0, xmm0
0x1800120ca  mov     [rsp+58h+var_38], esi
0x1800120ce  mov     ecx, 43h ; 'C'; nIndex
0x1800120d3  movdqu  [rsp+58h+var_34], xmm0
0x1800120d9  call    cs:__imp_GetSystemMetrics
0x1800120df  xor     ecx, ecx
0x1800120e1  test    eax, eax
0x1800120e3  mov     eax, [rdi+44h]
0x1800120e6  mov     dword ptr [rsp+58h+var_34+8], eax
0x1800120ea  mov     eax, [rdi+4Ch]
0x1800120ed  setnz   cl
0x1800120f0  mov     dword ptr [rsp+58h+var_34+4], ecx
0x1800120f4  mov     dword ptr [rsp+58h+var_34+0Ch], eax
0x1800120f8  lfence
0x1800120fb  mov     rsi, [rdi+230h]
0x180012102  mov     ebp, 4
0x180012107  cmp     ebx, 2
0x18001210a  jnz     short loc_180012110
0x18001210c  mov     eax, ebx
0x18001210e  jmp     short loc_18001212F
0x180012110  mov     ecx, [rsi+8]
0x180012113  xor     eax, eax
0x180012115  cmp     ecx, 0FFFFFFFFh
0x180012118  jz      short loc_18001212F
0x18001211a  mov     eax, ebp
0x18001211c  shl     eax, cl
0x18001211e  test    ebx, eax
0x180012120  jz      short loc_180012129
0x180012122  mov     eax, 2
0x180012127  jmp     short loc_18001212F
0x180012129  movzx   eax, bl
0x18001212c  and     eax, 1
0x18001212f  mov     dword ptr [rsp+58h+var_34], eax
0x180012133  lea     rdx, [rsp+58h+var_38]
0x180012138  mov     rax, [rsi]
0x18001213b  mov     rcx, rsi
0x18001213e  mov     rax, [rax+8]
0x180012142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012147  xor     ecx, ecx
0x180012149  mov     r14d, eax
0x18001214c  test    eax, eax
0x18001214e  setnz   cl
0x180012151  mov     [rsi+0Ch], ecx
0x180012154  mov     rsi, [rdi+238h]
0x18001215b  cmp     ebx, 2
0x18001215e  jnz     short loc_180012164
0x180012160  mov     ecx, ebx
0x180012162  jmp     short loc_180012185
0x180012164  mov     eax, [rsi+8]
0x180012167  xor     ecx, ecx
0x180012169  cmp     eax, 0FFFFFFFFh
0x18001216c  jz      short loc_180012185
0x18001216e  mov     ecx, eax
0x180012170  mov     eax, ebp
0x180012172  shl     eax, cl
0x180012174  test    ebx, eax
0x180012176  jz      short loc_18001217F
0x180012178  mov     ecx, 2
0x18001217d  jmp     short loc_180012185
0x18001217f  movzx   ecx, bl
0x180012182  and     ecx, 1
0x180012185  mov     dword ptr [rsp+58h+var_34], ecx
0x180012189  lea     rdx, [rsp+58h+var_38]
0x18001218e  mov     rax, [rsi]
0x180012191  mov     rcx, rsi
0x180012194  mov     rax, [rax+8]
0x180012198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001219d  mov     ecx, eax
0x18001219f  test    r14d, r14d
0x1800121a2  jnz     short loc_1800121A8
0x1800121a4  test    eax, eax
0x1800121a6  jz      short loc_1800121AE
0x1800121a8  mov     r14d, 1
0x1800121ae  xor     eax, eax
0x1800121b0  test    ecx, ecx
0x1800121b2  setnz   al
0x1800121b5  mov     [rsi+0Ch], eax
0x1800121b8  mov     rsi, [rdi+240h]
0x1800121bf  cmp     ebx, 2
0x1800121c2  jnz     short loc_1800121C8
0x1800121c4  mov     eax, ebx
0x1800121c6  jmp     short loc_1800121E7
0x1800121c8  mov     ecx, [rsi+8]
0x1800121cb  xor     eax, eax
0x1800121cd  cmp     ecx, 0FFFFFFFFh
0x1800121d0  jz      short loc_1800121E7
0x1800121d2  mov     eax, ebp
0x1800121d4  shl     eax, cl
0x1800121d6  test    ebx, eax
0x1800121d8  jz      short loc_1800121E1
0x1800121da  mov     eax, 2
0x1800121df  jmp     short loc_1800121E7
0x1800121e1  movzx   eax, bl
0x1800121e4  and     eax, 1
0x1800121e7  mov     dword ptr [rsp+58h+var_34], eax
0x1800121eb  lea     rdx, [rsp+58h+var_38]
0x1800121f0  mov     rax, [rsi]
0x1800121f3  mov     rcx, rsi
0x1800121f6  mov     rax, [rax+8]
0x1800121fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ff  xor     ecx, ecx
0x180012201  test    eax, eax
0x180012203  setnz   cl
0x180012206  mov     [rsi+0Ch], ecx
0x180012209  mov     rsi, [rdi+248h]
0x180012210  cmp     ebx, 2
0x180012213  jnz     short loc_180012219
0x180012215  mov     eax, ebx
0x180012217  jmp     short loc_180012238
0x180012219  mov     ecx, [rsi+8]
0x18001221c  xor     eax, eax
0x18001221e  cmp     ecx, 0FFFFFFFFh
0x180012221  jz      short loc_180012238
0x180012223  mov     eax, ebp
0x180012225  shl     eax, cl
0x180012227  test    ebx, eax
0x180012229  jz      short loc_180012232
0x18001222b  mov     eax, 2
0x180012230  jmp     short loc_180012238
0x180012232  movzx   eax, bl
0x180012235  and     eax, 1
0x180012238  mov     dword ptr [rsp+58h+var_34], eax
0x18001223c  lea     rdx, [rsp+58h+var_38]
0x180012241  mov     rax, [rsi]
0x180012244  mov     rcx, rsi
0x180012247  mov     rax, [rax+8]
0x18001224b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012250  xor     ecx, ecx
0x180012252  test    eax, eax
0x180012254  setnz   cl
0x180012257  mov     [rsi+0Ch], ecx
0x18001225a  mov     rsi, [rdi+250h]
0x180012261  cmp     ebx, 2
0x180012264  jnz     short loc_18001226A
0x180012266  mov     eax, ebx
0x180012268  jmp     short loc_180012289
0x18001226a  mov     ecx, [rsi+8]
0x18001226d  xor     eax, eax
0x18001226f  cmp     ecx, 0FFFFFFFFh
0x180012272  jz      short loc_180012289
0x180012274  mov     eax, ebp
0x180012276  shl     eax, cl
0x180012278  test    ebx, eax
0x18001227a  jz      short loc_180012283
0x18001227c  mov     eax, 2
0x180012281  jmp     short loc_180012289
0x180012283  movzx   eax, bl
0x180012286  and     eax, 1
0x180012289  mov     dword ptr [rsp+58h+var_34], eax
0x18001228d  lea     rdx, [rsp+58h+var_38]
0x180012292  mov     rax, [rsi]
0x180012295  mov     rcx, rsi
0x180012298  mov     rax, [rax+8]
0x18001229c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122a1  xor     ecx, ecx
0x1800122a3  test    eax, eax
0x1800122a5  setnz   cl
0x1800122a8  mov     [rsi+0Ch], ecx
0x1800122ab  mov     rdi, [rdi+258h]
0x1800122b2  cmp     ebx, 2
0x1800122b5  jnz     short loc_1800122BE
0x1800122b7  mov     eax, 2
0x1800122bc  jmp     short loc_1800122D4
0x1800122be  mov     ecx, [rdi+8]
0x1800122c1  xor     eax, eax
0x1800122c3  cmp     ecx, 0FFFFFFFFh
0x1800122c6  jz      short loc_1800122D4
0x1800122c8  shl     ebp, cl
0x1800122ca  test    ebx, ebp
0x1800122cc  jnz     short loc_1800122B7
0x1800122ce  movzx   eax, bl
0x1800122d1  and     eax, 1
0x1800122d4  mov     dword ptr [rsp+58h+var_34], eax
0x1800122d8  lea     rdx, [rsp+58h+var_38]
0x1800122dd  mov     rcx, [rdi]
0x1800122e0  mov     rax, [rcx+8]
0x1800122e4  mov     rcx, rdi
0x1800122e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ec  xor     ecx, ecx
0x1800122ee  test    eax, eax
0x1800122f0  mov     eax, r14d
0x1800122f3  setnz   cl
0x1800122f6  mov     [rdi+0Ch], ecx
0x1800122f9  mov     rcx, [rsp+58h+var_20]
0x1800122fe  xor     rcx, rsp; StackCookie
0x180012301  call    __security_check_cookie
0x180012306  mov     rbx, [rsp+58h+arg_10]
0x18001230b  mov     rbp, [rsp+58h+arg_18]
0x180012310  add     rsp, 40h
0x180012314  pop     r14
0x180012316  pop     rdi
0x180012317  pop     rsi
0x180012318  retn
```
