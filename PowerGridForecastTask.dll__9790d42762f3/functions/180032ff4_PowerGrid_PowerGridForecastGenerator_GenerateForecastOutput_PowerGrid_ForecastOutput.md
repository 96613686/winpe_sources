# PowerGrid::PowerGridForecastGenerator::GenerateForecastOutput(PowerGrid::ForecastOutput &)

- ea: `0x180032ff4`
- end: `0x18003333c`
- name: `?GenerateForecastOutput@PowerGridForecastGenerator@PowerGrid@@AEAAJAEAUForecastOutput@2@@Z`
- size: `840`
- prototype: `__int64 __fastcall(PowerGrid::PowerGridForecastGenerator *__hidden this, struct PowerGrid::ForecastOutput *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180033834`

## callees

- `0x18002dcd4`
- `0x180032ff4`
- `0x18003373c`
- `0x180034bd4`
- `0x1800350e0`
- `0x180037010`

## string_xrefs

- `0x180033067`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x1800330a5`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x1800330f8`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x18003314e`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x18003329f`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x1800332d4`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x180033309`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`

## pseudocode

```c
__int64 __fastcall PowerGrid::PowerGridForecastGenerator::GenerateForecastOutput(
        PowerGrid::PowerGridForecastGenerator *this,
        struct PowerGrid::ForecastOutput *a2)
{
  char *v4; // r15
  int v5; // eax
  unsigned int v6; // edi
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // r14
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v27; // [rsp+28h] [rbp-48h] BYREF
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  __int64 v29; // [rsp+38h] [rbp-38h] BYREF
  __int64 v30; // [rsp+40h] [rbp-30h] BYREF
  __int128 v31; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v4 = (char *)a2 + 8;
  *((_QWORD *)a2 + 2) = *((_QWORD *)a2 + 1);
  *(_DWORD *)a2 = *((_DWORD *)this + 8);
  if ( *((int *)this + 8) < 0 )
    return 0;
  v27 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, &v27);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v5,
      v26);
    return v6;
  }
  v26 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, 0, &v26);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v8,
      v26);
    v9 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v6;
  }
  v28 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 64LL))(v26, &v28);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v10,
      v26);
    v11 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v6;
  }
  v29 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 72LL))(v26, &v29);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v12,
      v26);
    v13 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v6;
  }
  *((_QWORD *)a2 + 4) = v28;
  *((_QWORD *)a2 + 5) = v29;
  v14 = 0;
  if ( !v27 )
  {
LABEL_24:
    v22 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return 0;
  }
  while ( 1 )
  {
    v31 = 0;
    v15 = *(_QWORD *)this;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)this + 48LL);
    v17 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v16(v15, v14, &v26);
    v19 = v18;
    if ( v18 < 0 )
      break;
    v30 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL))(v26, &v30);
    v19 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
        (const char *)(unsigned int)v20,
        v26);
      v24 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v19;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 64LL))(v26, &v28);
    v19 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
        (const char *)(unsigned int)v21,
        v26);
      v23 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      return v19;
    }
    *(_QWORD *)&v31 = v30;
    BYTE8(v31) = PowerGrid::PowerGridForecastGenerator::IsLowUserImpactTime(
                   this,
                   (struct Windows::Foundation::DateTime *)&v28);
    std::vector<PowerGrid::ForecastData>::push_back(v4, &v31);
    if ( ++v14 >= v27 )
      goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x119,
    (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
    (const char *)(unsigned int)v18,
    v26);
  v25 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return v19;
}

```

## disassembly

```asm
0x180032ff4  mov     [rsp-28h+arg_10], rbx
0x180032ff9  mov     [rsp-28h+arg_18], rsi
0x180032ffe  push    rbp
0x180032fff  push    rdi
0x180033000  push    r12
0x180033002  push    r14
0x180033004  push    r15
0x180033006  mov     rbp, rsp
0x180033009  sub     rsp, 70h
0x18003300d  movaps  [rsp+70h+var_10], xmm6
0x180033012  mov     rax, cs:__security_cookie
0x180033019  xor     rax, rsp
0x18003301c  mov     [rbp+var_18], rax
0x180033020  mov     rbx, rdx
0x180033023  mov     rsi, rcx
0x180033026  lea     r15, [rdx+8]
0x18003302a  mov     rax, [r15]
0x18003302d  mov     [rdx+10h], rax
0x180033031  mov     eax, [rcx+20h]
0x180033034  mov     [rdx], eax
0x180033036  xor     r12d, r12d
0x180033039  cmp     [rcx+20h], r12d
0x18003303d  jl      loc_18003326C
0x180033043  mov     [rbp+var_48], r12d
0x180033047  mov     rcx, [rcx]
0x18003304a  mov     rax, [rcx]
0x18003304d  lea     rdx, [rbp+var_48]
0x180033051  mov     rax, [rax+38h]
0x180033055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003305a  mov     edi, eax
0x18003305c  test    eax, eax
0x18003305e  jns     short loc_18003307F
0x180033060  mov     rcx, [rbp+28h]; this
0x180033064  mov     r9d, eax; char *
0x180033067  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x18003306e  mov     edx, 0FFh; void *
0x180033073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033078  mov     eax, edi
0x18003307a  jmp     loc_18003326E
0x18003307f  mov     [rbp+var_50], r12
0x180033083  mov     rcx, [rsi]
0x180033086  mov     rax, [rcx]
0x180033089  lea     r8, [rbp+var_50]
0x18003308d  xor     edx, edx
0x18003308f  mov     rax, [rax+30h]
0x180033093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033098  mov     edi, eax
0x18003309a  test    eax, eax
0x18003309c  jns     short loc_1800330D3
0x18003309e  mov     rcx, [rbp+28h]; this
0x1800330a2  mov     r9d, eax; char *
0x1800330a5  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x1800330ac  mov     edx, 105h; void *
0x1800330b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330b6  nop
0x1800330b7  mov     rcx, [rbp+var_50]
0x1800330bb  test    rcx, rcx
0x1800330be  jz      short loc_1800330D1
0x1800330c0  mov     [rbp+var_50], r12
0x1800330c4  mov     rax, [rcx]
0x1800330c7  mov     rax, [rax+10h]
0x1800330cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330d0  nop
0x1800330d1  jmp     short loc_180033078
0x1800330d3  mov     [rbp+var_40], r12
0x1800330d7  mov     rcx, [rbp+var_50]
0x1800330db  mov     rax, [rcx]
0x1800330de  lea     rdx, [rbp+var_40]
0x1800330e2  mov     rax, [rax+40h]
0x1800330e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330eb  mov     edi, eax
0x1800330ed  test    eax, eax
0x1800330ef  jns     short loc_180033129
0x1800330f1  mov     rcx, [rbp+28h]; this
0x1800330f5  mov     r9d, eax; char *
0x1800330f8  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x1800330ff  mov     edx, 109h; void *
0x180033104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033109  nop
0x18003310a  mov     rcx, [rbp+var_50]
0x18003310e  test    rcx, rcx
0x180033111  jz      short loc_180033124
0x180033113  mov     [rbp+var_50], r12
0x180033117  mov     rax, [rcx]
0x18003311a  mov     rax, [rax+10h]
0x18003311e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033123  nop
0x180033124  jmp     loc_180033078
0x180033129  mov     [rbp+var_38], r12
0x18003312d  mov     rcx, [rbp+var_50]
0x180033131  mov     rax, [rcx]
0x180033134  lea     rdx, [rbp+var_38]
0x180033138  mov     rax, [rax+48h]
0x18003313c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033141  mov     edi, eax
0x180033143  test    eax, eax
0x180033145  jns     short loc_18003317F
0x180033147  mov     rcx, [rbp+28h]; this
0x18003314b  mov     r9d, eax; char *
0x18003314e  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x180033155  mov     edx, 10Dh; void *
0x18003315a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003315f  nop
0x180033160  mov     rcx, [rbp+var_50]
0x180033164  test    rcx, rcx
0x180033167  jz      short loc_18003317A
0x180033169  mov     [rbp+var_50], r12
0x18003316d  mov     rax, [rcx]
0x180033170  mov     rax, [rax+10h]
0x180033174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033179  nop
0x18003317a  jmp     loc_180033078
0x18003317f  mov     rax, [rbp+var_40]
0x180033183  mov     [rbx+20h], rax
0x180033187  mov     rax, [rbp+var_38]
0x18003318b  mov     [rbx+28h], rax
0x18003318f  mov     edi, r12d
0x180033192  cmp     [rbp+var_48], r12d
0x180033196  jbe     loc_180033252
0x18003319c  xorps   xmm6, xmm6
0x18003319f  xorps   xmm0, xmm0
0x1800331a2  movups  [rbp+var_28], xmm0
0x1800331a6  mov     rbx, [rsi]
0x1800331a9  mov     rax, [rbx]
0x1800331ac  mov     r14, [rax+30h]
0x1800331b0  mov     rcx, [rbp+var_50]
0x1800331b4  test    rcx, rcx
0x1800331b7  jz      short loc_1800331CA
0x1800331b9  mov     [rbp+var_50], r12
0x1800331bd  mov     rdx, [rcx]
0x1800331c0  mov     rax, [rdx+10h]
0x1800331c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331c9  nop
0x1800331ca  lea     r8, [rbp+var_50]
0x1800331ce  mov     edx, edi
0x1800331d0  mov     rcx, rbx
0x1800331d3  mov     rax, r14
0x1800331d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331db  mov     ebx, eax
0x1800331dd  test    eax, eax
0x1800331df  js      loc_180033302
0x1800331e5  movsd   [rbp+var_30], xmm6
0x1800331ea  mov     rcx, [rbp+var_50]
0x1800331ee  mov     rax, [rcx]
0x1800331f1  lea     rdx, [rbp+var_30]
0x1800331f5  mov     rax, [rax+30h]
0x1800331f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331fe  mov     ebx, eax
0x180033200  test    eax, eax
0x180033202  js      loc_1800332CD
0x180033208  mov     rcx, [rbp+var_50]
0x18003320c  mov     rax, [rcx]
0x18003320f  lea     rdx, [rbp+var_40]
0x180033213  mov     rax, [rax+40h]
0x180033217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003321c  mov     ebx, eax
0x18003321e  test    eax, eax
0x180033220  js      short loc_180033298
0x180033222  movsd   xmm0, [rbp+var_30]
0x180033227  movsd   qword ptr [rbp+var_28], xmm0
0x18003322c  lea     rdx, [rbp+var_40]; struct Windows::Foundation::DateTime *
0x180033230  mov     rcx, rsi; this
0x180033233  call    ?IsLowUserImpactTime@PowerGridForecastGenerator@PowerGrid@@AEAA_NAEAUDateTime@Foundation@Windows@@@Z; PowerGrid::PowerGridForecastGenerator::IsLowUserImpactTime(Windows::Foundation::DateTime &)
0x180033238  mov     byte ptr [rbp+var_28+8], al
0x18003323b  lea     rdx, [rbp+var_28]
0x18003323f  mov     rcx, r15
0x180033242  call    ?push_back@?$vector@UForecastData@PowerGrid@@V?$allocator@UForecastData@PowerGrid@@@std@@@std@@QEAAXAEBUForecastData@PowerGrid@@@Z; std::vector<PowerGrid::ForecastData>::push_back(PowerGrid::ForecastData const &)
0x180033247  inc     edi
0x180033249  cmp     edi, [rbp+var_48]
0x18003324c  jb      loc_18003319F
0x180033252  mov     rcx, [rbp+var_50]
0x180033256  test    rcx, rcx
0x180033259  jz      short loc_18003326C
0x18003325b  mov     [rbp+var_50], r12
0x18003325f  mov     rax, [rcx]
0x180033262  mov     rax, [rax+10h]
0x180033266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003326b  nop
0x18003326c  xor     eax, eax
0x18003326e  mov     rcx, [rbp+var_18]
0x180033272  xor     rcx, rsp; StackCookie
0x180033275  call    __security_check_cookie
0x18003327a  lea     r11, [rsp+70h+var_s0]
0x18003327f  mov     rbx, [r11+40h]
0x180033283  mov     rsi, [r11+48h]
0x180033287  movaps  xmm6, [rsp+70h+var_10]
0x18003328c  mov     rsp, r11
0x18003328f  pop     r15
0x180033291  pop     r14
0x180033293  pop     r12
0x180033295  pop     rdi
0x180033296  pop     rbp
0x180033297  retn
0x180033298  mov     rcx, [rbp+28h]; this
0x18003329c  mov     r9d, ebx; char *
0x18003329f  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x1800332a6  mov     edx, 121h; void *
0x1800332ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332b0  nop
0x1800332b1  mov     rcx, [rbp+var_50]
0x1800332b5  test    rcx, rcx
0x1800332b8  jz      short loc_1800332CB
0x1800332ba  mov     [rbp+var_50], r12
0x1800332be  mov     rax, [rcx]
0x1800332c1  mov     rax, [rax+10h]
0x1800332c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ca  nop
0x1800332cb  jmp     short loc_180033335
0x1800332cd  mov     rcx, [rbp+28h]; this
0x1800332d1  mov     r9d, ebx; char *
0x1800332d4  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x1800332db  mov     edx, 11Dh; void *
0x1800332e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332e5  nop
0x1800332e6  mov     rcx, [rbp+var_50]
0x1800332ea  test    rcx, rcx
0x1800332ed  jz      short loc_180033300
0x1800332ef  mov     [rbp+var_50], r12
0x1800332f3  mov     rax, [rcx]
0x1800332f6  mov     rax, [rax+10h]
0x1800332fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ff  nop
0x180033300  jmp     short loc_180033335
0x180033302  mov     rcx, [rbp+28h]; this
0x180033306  mov     r9d, ebx; char *
0x180033309  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x180033310  mov     edx, 119h; void *
0x180033315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003331a  nop
0x18003331b  mov     rcx, [rbp+var_50]
0x18003331f  test    rcx, rcx
0x180033322  jz      short loc_180033335
0x180033324  mov     [rbp+var_50], r12
0x180033328  mov     rax, [rcx]
0x18003332b  mov     rax, [rax+10h]
0x18003332f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033334  nop
0x180033335  mov     eax, ebx
0x180033337  jmp     loc_18003326E
```
