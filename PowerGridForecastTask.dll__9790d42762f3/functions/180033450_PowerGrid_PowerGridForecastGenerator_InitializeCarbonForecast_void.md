# PowerGrid::PowerGridForecastGenerator::InitializeCarbonForecast(void)

- ea: `0x180033450`
- end: `0x180033733`
- name: `?InitializeCarbonForecast@PowerGridForecastGenerator@PowerGrid@@AEAAJXZ`
- size: `739`
- prototype: `__int64 __fastcall(PowerGrid::PowerGridForecastGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033344`

## callees

- `0x180026937`
- `0x18002dcd4`
- `0x180033450`
- `0x18003381c`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800334cf`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800334cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033494`

## string_xrefs

- `0x180033536`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x1800335ac`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x180033600`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`
- `0x180033670`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`

## pseudocode

```c
__int64 __fastcall PowerGrid::PowerGridForecastGenerator::InitializeCarbonForecast(
        PowerGrid::PowerGridForecastGenerator *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, __int64, PowerGrid::PowerGridForecastGenerator *); // rsi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-50h] BYREF
  __int64 v23; // [rsp+28h] [rbp-48h] BYREF
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v22 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Sustainability.GridIntensityProvider",
         0x35u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180033732LL);
  }
  v22 = 0;
  v24 = 0;
  v5 = RoActivateInstance(string, &v24);
  if ( (v5 & 0x80000000) == 0 )
  {
    if ( !memcmp_0(&GUID_e0ebc8c6_e9fa_425d_bb32_f31998042e60, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v22 = v24;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
             v24,
             &GUID_e0ebc8c6_e9fa_425d_bb32_f31998042e60,
             &v22);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)v5,
      v22);
    v6 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v8 = v22;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, PowerGrid::PowerGridForecastGenerator *))(*(_QWORD *)v22 + 56LL);
  v10 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v9(v8, 72, this);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v11,
      v22);
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v5;
  }
  v23 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, 0, &v23);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v13,
      v22);
    v14 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v5;
  }
  v25 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 64LL))(v23, &v25);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
      (const char *)(unsigned int)v16,
      v22);
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v5;
  }
  v19 = v25;
  *((_QWORD *)this + 1) = v25;
  *((_QWORD *)this + 2) = v19 + 2592000000000LL;
  v20 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180033450  mov     [rsp-18h+arg_8], rbx
0x180033455  mov     [rsp-18h+arg_10], rsi
0x18003345a  push    rbp
0x18003345b  push    rdi
0x18003345c  push    r14
0x18003345e  mov     rbp, rsp
0x180033461  sub     rsp, 70h
0x180033465  mov     rax, cs:__security_cookie
0x18003346c  xor     rax, rsp
0x18003346f  mov     [rbp+var_10], rax
0x180033473  mov     rdi, rcx
0x180033476  xor     r14d, r14d
0x180033479  mov     [rbp+var_50], r14
0x18003347d  mov     [rbp+string], r14
0x180033481  lea     r9, [rbp+string]; string
0x180033485  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180033489  lea     edx, [r14+35h]; length
0x18003348d  lea     rcx, ?RuntimeClass_Windows_Internal_Sustainability_GridIntensityProvider@@3QBGB; "Windows.Internal.Sustainability.GridInt"...
0x180033494  call    cs:__imp_WindowsCreateStringReference
0x18003349a  test    eax, eax
0x18003349c  js      loc_18003372B
0x1800334a2  mov     rbx, [rbp+string]
0x1800334a6  mov     rcx, [rbp+var_50]
0x1800334aa  test    rcx, rcx
0x1800334ad  jz      short loc_1800334C0
0x1800334af  mov     [rbp+var_50], r14
0x1800334b3  mov     rax, [rcx]
0x1800334b6  mov     rax, [rax+10h]
0x1800334ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334bf  nop
0x1800334c0  mov     [rbp+var_50], r14
0x1800334c4  mov     [rbp+var_40], r14
0x1800334c8  lea     rdx, [rbp+var_40]
0x1800334cc  mov     rcx, rbx
0x1800334cf  call    cs:__imp_RoActivateInstance
0x1800334d5  mov     ebx, eax
0x1800334d7  test    eax, eax
0x1800334d9  js      short loc_18003352B
0x1800334db  mov     r8d, 10h; Size
0x1800334e1  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800334e8  lea     rcx, _GUID_e0ebc8c6_e9fa_425d_bb32_f31998042e60; Buf1
0x1800334ef  call    memcmp_0
0x1800334f4  mov     rcx, [rbp+var_40]
0x1800334f8  test    eax, eax
0x1800334fa  jnz     short loc_180033502
0x1800334fc  mov     [rbp+var_50], rcx
0x180033500  jmp     short loc_18003352B
0x180033502  mov     rax, [rcx]
0x180033505  lea     r8, [rbp+var_50]
0x180033509  lea     rdx, _GUID_e0ebc8c6_e9fa_425d_bb32_f31998042e60
0x180033510  mov     rax, [rax]
0x180033513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033518  mov     ebx, eax
0x18003351a  mov     rcx, [rbp+var_40]
0x18003351e  mov     rax, [rcx]
0x180033521  mov     rax, [rax+10h]
0x180033525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003352a  nop
0x18003352b  test    ebx, ebx
0x18003352d  jns     short loc_180033569
0x18003352f  mov     rcx, [rbp+18h]; this
0x180033533  mov     r9d, ebx; char *
0x180033536  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x18003353d  mov     edx, 0C9h; void *
0x180033542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033547  nop
0x180033548  mov     rcx, [rbp+var_50]
0x18003354c  test    rcx, rcx
0x18003354f  jz      short loc_180033562
0x180033551  mov     [rbp+var_50], r14
0x180033555  mov     rax, [rcx]
0x180033558  mov     rax, [rax+10h]
0x18003355c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033561  nop
0x180033562  mov     eax, ebx
0x180033564  jmp     loc_18003370A
0x180033569  mov     rbx, [rbp+var_50]
0x18003356d  mov     rax, [rbx]
0x180033570  mov     rsi, [rax+38h]
0x180033574  mov     rcx, [rdi]
0x180033577  test    rcx, rcx
0x18003357a  jz      short loc_18003358C
0x18003357c  mov     [rdi], r14
0x18003357f  mov     rdx, [rcx]
0x180033582  mov     rax, [rdx+10h]
0x180033586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003358b  nop
0x18003358c  mov     r8, rdi
0x18003358f  mov     edx, 48h ; 'H'
0x180033594  mov     rcx, rbx
0x180033597  mov     rax, rsi
0x18003359a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003359f  mov     ebx, eax
0x1800335a1  test    eax, eax
0x1800335a3  jns     short loc_1800335DA
0x1800335a5  mov     rcx, [rbp+18h]; this
0x1800335a9  mov     r9d, eax; char *
0x1800335ac  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x1800335b3  mov     edx, 0CDh; void *
0x1800335b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335bd  nop
0x1800335be  mov     rcx, [rbp+var_50]
0x1800335c2  test    rcx, rcx
0x1800335c5  jz      short loc_1800335D8
0x1800335c7  mov     [rbp+var_50], r14
0x1800335cb  mov     rax, [rcx]
0x1800335ce  mov     rax, [rax+10h]
0x1800335d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335d7  nop
0x1800335d8  jmp     short loc_180033562
0x1800335da  mov     [rbp+var_48], r14
0x1800335de  mov     rcx, [rdi]
0x1800335e1  mov     rax, [rcx]
0x1800335e4  lea     r8, [rbp+var_48]
0x1800335e8  xor     edx, edx
0x1800335ea  mov     rax, [rax+30h]
0x1800335ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335f3  mov     ebx, eax
0x1800335f5  test    eax, eax
0x1800335f7  jns     short loc_18003364B
0x1800335f9  mov     rcx, [rbp+18h]; this
0x1800335fd  mov     r9d, eax; char *
0x180033600  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x180033607  mov     edx, 0D2h; void *
0x18003360c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033611  nop
0x180033612  mov     rcx, [rbp+var_48]
0x180033616  test    rcx, rcx
0x180033619  jz      short loc_18003362C
0x18003361b  mov     [rbp+var_48], r14
0x18003361f  mov     rax, [rcx]
0x180033622  mov     rax, [rax+10h]
0x180033626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003362b  nop
0x18003362c  mov     rcx, [rbp+var_50]
0x180033630  test    rcx, rcx
0x180033633  jz      short loc_180033646
0x180033635  mov     [rbp+var_50], r14
0x180033639  mov     rax, [rcx]
0x18003363c  mov     rax, [rax+10h]
0x180033640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033645  nop
0x180033646  jmp     loc_180033562
0x18003364b  mov     [rbp+var_38], r14
0x18003364f  mov     rcx, [rbp+var_48]
0x180033653  mov     rax, [rcx]
0x180033656  lea     rdx, [rbp+var_38]
0x18003365a  mov     rax, [rax+40h]
0x18003365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033663  mov     ebx, eax
0x180033665  test    eax, eax
0x180033667  jns     short loc_1800336BB
0x180033669  mov     rcx, [rbp+18h]; this
0x18003366d  mov     r9d, eax; char *
0x180033670  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x180033677  mov     edx, 0D6h; void *
0x18003367c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033681  nop
0x180033682  mov     rcx, [rbp+var_48]
0x180033686  test    rcx, rcx
0x180033689  jz      short loc_18003369C
0x18003368b  mov     [rbp+var_48], r14
0x18003368f  mov     rax, [rcx]
0x180033692  mov     rax, [rax+10h]
0x180033696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003369b  nop
0x18003369c  mov     rcx, [rbp+var_50]
0x1800336a0  test    rcx, rcx
0x1800336a3  jz      short loc_1800336B6
0x1800336a5  mov     [rbp+var_50], r14
0x1800336a9  mov     rax, [rcx]
0x1800336ac  mov     rax, [rax+10h]
0x1800336b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336b5  nop
0x1800336b6  jmp     loc_180033562
0x1800336bb  mov     rax, [rbp+var_38]
0x1800336bf  mov     [rdi+8], rax
0x1800336c3  mov     rcx, 25B7F3D4000h
0x1800336cd  add     rcx, rax
0x1800336d0  mov     [rdi+10h], rcx
0x1800336d4  mov     rcx, [rbp+var_48]
0x1800336d8  test    rcx, rcx
0x1800336db  jz      short loc_1800336EE
0x1800336dd  mov     [rbp+var_48], r14
0x1800336e1  mov     rax, [rcx]
0x1800336e4  mov     rax, [rax+10h]
0x1800336e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336ed  nop
0x1800336ee  mov     rcx, [rbp+var_50]
0x1800336f2  test    rcx, rcx
0x1800336f5  jz      short loc_180033708
0x1800336f7  mov     [rbp+var_50], r14
0x1800336fb  mov     rax, [rcx]
0x1800336fe  mov     rax, [rax+10h]
0x180033702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033707  nop
0x180033708  xor     eax, eax
0x18003370a  mov     rcx, [rbp+var_10]
0x18003370e  xor     rcx, rsp; StackCookie
0x180033711  call    __security_check_cookie
0x180033716  lea     r11, [rsp+70h+var_s0]
0x18003371b  mov     rbx, [r11+28h]
0x18003371f  mov     rsi, [r11+30h]
0x180033723  mov     rsp, r11
0x180033726  pop     r14
0x180033728  pop     rdi
0x180033729  pop     rbp
0x18003372a  retn
0x18003372b  mov     ecx, eax; this
0x18003372d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
