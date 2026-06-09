# Broker::TimeBroker::SetSytemTimer(void)

- ea: `0x180007c60`
- end: `0x180008096`
- name: `?SetSytemTimer@TimeBroker@Broker@@AEAAXXZ`
- size: `1078`
- prototype: `void __fastcall(Broker::TimeBroker *this, __int64, __int64, void (*)(void *, unsigned int, unsigned int))`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c14`
- `0x180001f78`
- `0x1800061e0`
- `0x1800074c0`

## callees

- `0x180007c60`
- `0x18000809c`
- `0x180008168`
- `0x18000a474`
- `0x18000b9c0`
- `0x18000e5f0`
- `0x18000ec10`
- `0x180012dd0`
- `0x18001c010`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x180007dc1`
- `ntdll!NtPowerInformation` at `0x180007dc1`

## string_xrefs

- `0x180007d63`: `TimebrokerWakeUnspecifiedCaller`

## pseudocode

```c
void __fastcall Broker::TimeBroker::SetSytemTimer(
        Broker::TimeBroker *this,
        __int64 a2,
        __int64 a3,
        void (*a4)(void *, unsigned int, unsigned int))
{
  __int64 v5; // rdx
  const wchar_t *v6; // r8
  const wchar_t *v7; // r12
  _QWORD *v8; // rcx
  union _LARGE_INTEGER v9; // r14
  __int64 v10; // rax
  volatile signed __int32 *v11; // rsi
  __int64 v12; // rcx
  wchar_t *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r8
  wchar_t *v16; // r9
  bool v17; // zf
  __int64 v18; // rax
  const wchar_t *v19; // rdx
  wchar_t v20; // cx
  wchar_t *v21; // rcx
  int v22; // r8d
  void (*v23)(void *, unsigned int, unsigned int); // r9
  __int64 v24; // rbx
  union _LARGE_INTEGER *v25; // rdi
  __int64 v26; // rbx
  union _LARGE_INTEGER v27; // rdi
  wchar_t v28; // dx
  __int64 v29; // rbx
  const wchar_t *v30; // r9
  const wchar_t *v31; // rax
  __int64 InputBuffer; // [rsp+40h] [rbp-E8h] BYREF
  _OWORD v33[8]; // [rsp+48h] [rbp-E0h] BYREF
  union _LARGE_INTEGER v34; // [rsp+C8h] [rbp-60h]

  v5 = 0x7FFFFFFFFFFFFFFFLL;
  v6 = L"Not Set";
  v7 = L"Set";
  if ( *((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v8 = (_QWORD *)**((_QWORD **)this + 6);
      v9 = (union _LARGE_INTEGER)v8[4];
      v10 = v8[6];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = (volatile signed __int32 *)v8[6];
      v12 = v8[5];
      if ( v9.QuadPart )
      {
        v13 = (wchar_t *)(v12 + 94);
        memset(v33, 0, sizeof(v33));
        InputBuffer = 44;
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        v15 = 64;
        v16 = (wchar_t *)v33;
        v17 = v14 == 0;
        v18 = 2147483646;
        if ( v17 )
        {
          v19 = L"TimebrokerWakeUnspecifiedCaller";
          do
          {
            if ( !v18 )
              break;
            v20 = *v19;
            if ( !*v19 )
              break;
            ++v19;
            *v16++ = v20;
            --v18;
            --v15;
          }
          while ( v15 );
        }
        else
        {
          do
          {
            if ( !v18 )
              break;
            v28 = *v13;
            if ( !*v13 )
              break;
            ++v13;
            *v16++ = v28;
            --v18;
            --v15;
          }
          while ( v15 );
        }
        v21 = v16 - 1;
        if ( v15 )
          v21 = v16;
        *v21 = 0;
        v34 = v9;
        NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 0x90u, 0, 0);
        v24 = *((_QWORD *)this + 12);
        v25 = (union _LARGE_INTEGER *)(v24 + 16);
        *(_QWORD *)(v24 + 16) = 0x7FFFFFFFFFFFFFFFLL;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v31 = L"Set";
          if ( !*(_BYTE *)(v24 + 24) )
            v31 = L"Not Set";
          WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)L"Not Set", v22, v9.LowPart, (__int64)v31);
        }
        if ( *(_BYTE *)(v24 + 24) )
          Broker::SystemTimer::SetWakeEnabledTimer((Broker::SystemTimer *)v24, v9);
        else
          Broker::SystemTimer::SetNonWakeEnabledTimer((void **)v24, v9, v22, v23);
LABEL_18:
        *v25 = v9;
        v5 = 0x7FFFFFFFFFFFFFFFLL;
        v6 = L"Not Set";
        goto LABEL_19;
      }
    }
    else
    {
      v11 = 0;
      v9.QuadPart = 0;
    }
    v29 = *((_QWORD *)this + 12);
    v25 = (union _LARGE_INTEGER *)(v29 + 16);
    *(_QWORD *)(v29 + 16) = 0x7FFFFFFFFFFFFFFFLL;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v30 = L"Set";
      if ( !*(_BYTE *)(v29 + 24) )
        v30 = L"Not Set";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v30);
    }
    if ( *(_BYTE *)(v29 + 24) )
      Broker::SystemTimer::ClearWakeEnabledTimer((void **)v29);
    else
      Broker::SystemTimer::ClearNonWakeEnabledTimer((void **)v29);
    goto LABEL_18;
  }
  v11 = 0;
LABEL_19:
  v26 = *((_QWORD *)this + 10);
  if ( !v26 )
    goto LABEL_20;
  if ( *((_DWORD *)this + 42) == 1 )
  {
    if ( *((_QWORD *)this + 5) )
    {
      v27 = *(union _LARGE_INTEGER *)(**((_QWORD **)this + 4) + 32LL);
      *(_QWORD *)(v26 + 16) = 0x7FFFFFFFFFFFFFFFLL;
      if ( v27.QuadPart )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          if ( !*(_BYTE *)(v26 + 24) )
            v7 = L"Not Set";
          WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), -1, (unsigned int)L"Not Set", v27.LowPart, (__int64)v7);
        }
        if ( *(_BYTE *)(v26 + 24) )
        {
          Broker::SystemTimer::SetWakeEnabledTimer((Broker::SystemTimer *)v26, v27);
          *(union _LARGE_INTEGER *)(v26 + 16) = v27;
          goto LABEL_20;
        }
        Broker::SystemTimer::SetNonWakeEnabledTimer((void **)v26, v27, (int)v6, a4);
        goto LABEL_33;
      }
    }
    else
    {
      v27.QuadPart = 0;
      *(_QWORD *)(v26 + 16) = 0x7FFFFFFFFFFFFFFFLL;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      if ( !*(_BYTE *)(v26 + 24) )
        v7 = L"Not Set";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v7);
    }
    if ( *(_BYTE *)(v26 + 24) )
      Broker::SystemTimer::ClearWakeEnabledTimer((void **)v26);
    else
      Broker::SystemTimer::ClearNonWakeEnabledTimer((void **)v26);
LABEL_33:
    *(union _LARGE_INTEGER *)(v26 + 16) = v27;
    goto LABEL_20;
  }
  *(_QWORD *)(v26 + 16) = 0x7FFFFFFFFFFFFFFFLL;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( !*(_BYTE *)(v26 + 24) )
      v7 = L"Not Set";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v7);
  }
  if ( *(_BYTE *)(v26 + 24) )
    Broker::SystemTimer::ClearWakeEnabledTimer((void **)v26);
  else
    Broker::SystemTimer::ClearNonWakeEnabledTimer((void **)v26);
  *(_QWORD *)(v26 + 16) = 0;
LABEL_20:
  if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64, const wchar_t *))v11)(v11, v5, v6);
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
}

```

## disassembly

```asm
0x180007c60  push    rbx
0x180007c62  push    rbp
0x180007c63  push    rsi
0x180007c64  push    rdi
0x180007c65  push    r12
0x180007c67  push    r13
0x180007c69  push    r14
0x180007c6b  push    r15
0x180007c6d  sub     rsp, 0E8h
0x180007c74  mov     rax, cs:__security_cookie
0x180007c7b  xor     rax, rsp
0x180007c7e  mov     [rsp+128h+var_58], rax
0x180007c86  mov     r15, rcx
0x180007c89  xorps   xmm0, xmm0
0x180007c8c  movdqu  [rsp+128h+var_F8], xmm0
0x180007c92  xor     r13d, r13d
0x180007c95  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007c9c  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180007ca6  lea     r8, aNotSet; "Not Set"
0x180007cad  lea     r12, aSet; "Set"
0x180007cb4  cmp     [rcx+60h], r13
0x180007cb8  jz      loc_180007E58
0x180007cbe  cmp     [rcx+38h], r13
0x180007cc2  jz      loc_180007F20
0x180007cc8  mov     rax, [rcx+30h]
0x180007ccc  mov     rcx, [rax]
0x180007ccf  mov     r14, [rcx+20h]
0x180007cd3  mov     rax, [rcx+30h]
0x180007cd7  test    rax, rax
0x180007cda  jz      short loc_180007CE0
0x180007cdc  lock inc dword ptr [rax+8]
0x180007ce0  mov     rsi, [rcx+30h]
0x180007ce4  mov     rcx, [rcx+28h]
0x180007ce8  mov     qword ptr [rsp+128h+var_F8], rcx
0x180007ced  mov     qword ptr [rsp+128h+var_F8+8], rsi
0x180007cf2  test    r14, r14
0x180007cf5  jz      loc_180007F30
0x180007cfb  add     rcx, 5Eh ; '^'
0x180007cff  movups  [rsp+128h+var_E0], xmm0
0x180007d04  movups  [rsp+128h+var_D0], xmm0
0x180007d09  movups  [rsp+128h+var_C0], xmm0
0x180007d0e  movups  [rsp+128h+var_B0], xmm0
0x180007d13  movups  [rsp+128h+var_A0], xmm0
0x180007d1b  movups  [rsp+128h+var_90], xmm0
0x180007d23  movups  [rsp+128h+var_80], xmm0
0x180007d2b  movups  [rsp+128h+var_70], xmm0
0x180007d33  mov     [rsp+128h+InputBuffer], 2Ch ; ','
0x180007d3c  mov     rax, rbp
0x180007d3f  nop
0x180007d40  inc     rax
0x180007d43  cmp     [rcx+rax*2], r13w
0x180007d48  jnz     short loc_180007D40
0x180007d4a  mov     r8d, 40h ; '@'
0x180007d50  lea     r9, [rsp+128h+var_E0]
0x180007d55  test    rax, rax
0x180007d58  mov     eax, 7FFFFFFEh
0x180007d5d  jnz     loc_180007EE3
0x180007d63  lea     rdx, aTimebrokerwake; "TimebrokerWakeUnspecifiedCaller"
0x180007d6a  nop     word ptr [rax+rax+00h]
0x180007d70  test    rax, rax
0x180007d73  jz      short loc_180007D92
0x180007d75  movzx   ecx, word ptr [rdx]
0x180007d78  test    cx, cx
0x180007d7b  jz      short loc_180007D92
0x180007d7d  add     rdx, 2
0x180007d81  mov     [r9], cx
0x180007d85  add     r9, 2
0x180007d89  dec     rax
0x180007d8c  sub     r8, 1
0x180007d90  jnz     short loc_180007D70
0x180007d92  lea     rcx, [r9-2]
0x180007d96  test    r8, r8
0x180007d99  cmovnz  rcx, r9
0x180007d9d  mov     [rcx], r13w
0x180007da1  mov     [rsp+128h+var_60], r14
0x180007da9  mov     [rsp+128h+OutputBufferLength], r13d; OutputBufferLength
0x180007dae  xor     r9d, r9d; OutputBuffer
0x180007db1  mov     r8d, 90h; InputBufferLength
0x180007db7  lea     rdx, [rsp+128h+InputBuffer]; InputBuffer
0x180007dbc  mov     ecx, 57h ; 'W'; PowerInformationLevel
0x180007dc1  call    cs:__imp_NtPowerInformation
0x180007dc7  mov     rbx, [r15+60h]
0x180007dcb  lea     rdi, [rbx+10h]
0x180007dcf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007dd9  mov     [rdi], rax
0x180007ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007de3  test    byte ptr [rcx+1Ch], 4
0x180007de7  jnz     loc_180007FD2
0x180007ded  mov     rdx, r14; union _LARGE_INTEGER
0x180007df0  mov     rcx, rbx; this
0x180007df3  cmp     [rbx+18h], r13b
0x180007df7  jnz     short loc_180007E50
0x180007df9  call    ?SetNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetNonWakeEnabledTimer(_LARGE_INTEGER)
0x180007dfe  mov     [rdi], r14
0x180007e01  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180007e0b  lea     r8, aNotSet; "Not Set"
0x180007e12  mov     rbx, [r15+50h]
0x180007e16  test    rbx, rbx
0x180007e19  jnz     short loc_180007E88
0x180007e1b  test    rsi, rsi
0x180007e1e  jz      short loc_180007E2C
0x180007e20  mov     eax, ebp
0x180007e22  lock xadd [rsi+8], eax
0x180007e27  cmp     eax, 1
0x180007e2a  jz      short loc_180007E5F
0x180007e2c  mov     rcx, [rsp+128h+var_58]
0x180007e34  xor     rcx, rsp; StackCookie
0x180007e37  call    __security_check_cookie
0x180007e3c  add     rsp, 0E8h
0x180007e43  pop     r15
0x180007e45  pop     r14
0x180007e47  pop     r13
0x180007e49  pop     r12
0x180007e4b  pop     rdi
0x180007e4c  pop     rsi
0x180007e4d  pop     rbp
0x180007e4e  pop     rbx
0x180007e4f  retn
0x180007e50  call    ?SetWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetWakeEnabledTimer(_LARGE_INTEGER)
0x180007e55  nop
0x180007e56  jmp     short loc_180007DFE
0x180007e58  mov     rsi, qword ptr [rsp+128h+var_F8+8]
0x180007e5d  jmp     short loc_180007E12
0x180007e5f  mov     rax, [rsi]
0x180007e62  mov     rcx, rsi
0x180007e65  mov     rax, [rax]
0x180007e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6d  lock xadd [rsi+0Ch], ebp
0x180007e72  cmp     ebp, 1
0x180007e75  jnz     short loc_180007E2C
0x180007e77  mov     rax, [rsi]
0x180007e7a  mov     rcx, rsi
0x180007e7d  mov     rax, [rax+8]
0x180007e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e86  jmp     short loc_180007E2C
0x180007e88  cmp     dword ptr [r15+0A8h], 1
0x180007e90  jnz     loc_180008040
0x180007e96  cmp     [r15+28h], r13
0x180007e9a  jz      loc_180007F85
0x180007ea0  mov     rax, [r15+20h]
0x180007ea4  mov     rcx, [rax]
0x180007ea7  mov     rdi, [rcx+20h]
0x180007eab  mov     [rbx+10h], rdx
0x180007eaf  test    rdi, rdi
0x180007eb2  jz      loc_180007F8C
0x180007eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ebf  test    byte ptr [rcx+1Ch], 4
0x180007ec3  jnz     loc_18000800E
0x180007ec9  mov     rdx, rdi; union _LARGE_INTEGER
0x180007ecc  mov     rcx, rbx; this
0x180007ecf  cmp     [rbx+18h], r13b
0x180007ed3  jnz     short loc_180007F12
0x180007ed5  call    ?SetNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetNonWakeEnabledTimer(_LARGE_INTEGER)
0x180007eda  mov     [rbx+10h], rdi
0x180007ede  jmp     loc_180007E1B
0x180007ee3  test    rax, rax
0x180007ee6  jz      loc_180007D92
0x180007eec  movzx   edx, word ptr [rcx]
0x180007eef  test    dx, dx
0x180007ef2  jz      loc_180007D92
0x180007ef8  add     rcx, 2
0x180007efc  mov     [r9], dx
0x180007f00  add     r9, 2
0x180007f04  dec     rax
0x180007f07  sub     r8, 1
0x180007f0b  jnz     short loc_180007EE3
0x180007f0d  jmp     loc_180007D92
0x180007f12  call    ?SetWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetWakeEnabledTimer(_LARGE_INTEGER)
0x180007f17  mov     [rbx+10h], rdi
0x180007f1b  jmp     loc_180007E1B
0x180007f20  mov     rsi, r13
0x180007f23  mov     r14, r13
0x180007f26  mov     qword ptr [rsp+128h+var_F8], r13
0x180007f2b  mov     qword ptr [rsp+128h+var_F8+8], r13
0x180007f30  mov     rbx, [r15+60h]
0x180007f34  lea     rdi, [rbx+10h]
0x180007f38  mov     [rdi], rdx
0x180007f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f42  test    byte ptr [rcx+1Ch], 4
0x180007f46  jz      short loc_180007F6E
0x180007f48  cmp     byte ptr [rcx+19h], 5
0x180007f4c  jb      short loc_180007F6E
0x180007f4e  mov     r9, r12
0x180007f51  cmp     [rbx+18h], r13b
0x180007f55  cmovz   r9, r8
0x180007f59  mov     edx, 0Dh
0x180007f5e  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x180007f65  mov     rcx, [rcx+10h]
0x180007f69  call    WPP_SF_S
0x180007f6e  mov     rcx, rbx; this
0x180007f71  cmp     [rbx+18h], r13b
0x180007f75  jz      loc_180008004
0x180007f7b  call    ?ClearWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearWakeEnabledTimer(void)
0x180007f80  jmp     loc_180007DFE
0x180007f85  mov     rdi, r13
0x180007f88  mov     [rbx+10h], rdx
0x180007f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f93  test    byte ptr [rcx+1Ch], 4
0x180007f97  jz      short loc_180007FBF
0x180007f99  cmp     byte ptr [rcx+19h], 5
0x180007f9d  jb      short loc_180007FBF
0x180007f9f  cmp     [rbx+18h], r13b
0x180007fa3  cmovz   r12, r8
0x180007fa7  mov     edx, 0Dh
0x180007fac  mov     r9, r12
0x180007faf  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x180007fb6  mov     rcx, [rcx+10h]
0x180007fba  call    WPP_SF_S
0x180007fbf  mov     rcx, rbx; this
0x180007fc2  cmp     [rbx+18h], r13b
0x180007fc6  jz      short loc_180008036
0x180007fc8  call    ?ClearWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearWakeEnabledTimer(void)
0x180007fcd  jmp     loc_180007EDA
0x180007fd2  cmp     byte ptr [rcx+19h], 5
0x180007fd6  jb      loc_180007DED
0x180007fdc  mov     rax, r12
0x180007fdf  cmp     [rbx+18h], r13b
0x180007fe3  lea     rdx, aNotSet; "Not Set"
0x180007fea  cmovz   rax, rdx
0x180007fee  mov     qword ptr [rsp+128h+OutputBufferLength], rax
0x180007ff3  mov     r9, r14
0x180007ff6  mov     rcx, [rcx+10h]
0x180007ffa  call    WPP_SF_iS
0x180007fff  jmp     loc_180007DED
0x180008004  call    ?ClearNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearNonWakeEnabledTimer(void)
0x180008009  jmp     loc_180007DFE
0x18000800e  cmp     byte ptr [rcx+19h], 5
0x180008012  jb      loc_180007EC9
0x180008018  cmp     [rbx+18h], r13b
0x18000801c  cmovz   r12, r8
0x180008020  mov     qword ptr [rsp+128h+OutputBufferLength], r12
0x180008025  mov     r9, rdi
0x180008028  mov     rcx, [rcx+10h]
0x18000802c  call    WPP_SF_iS
0x180008031  jmp     loc_180007EC9
0x180008036  call    ?ClearNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearNonWakeEnabledTimer(void)
0x18000803b  jmp     loc_180007EDA
0x180008040  mov     [rbx+10h], rdx
0x180008044  mov     rcx, cs:WPP_GLOBAL_Control
0x18000804b  test    byte ptr [rcx+1Ch], 4
0x18000804f  jz      short loc_180008077
0x180008051  cmp     byte ptr [rcx+19h], 5
0x180008055  jb      short loc_180008077
0x180008057  cmp     [rbx+18h], r13b
0x18000805b  cmovz   r12, r8
0x18000805f  mov     edx, 0Dh
0x180008064  mov     r9, r12
0x180008067  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18000806e  mov     rcx, [rcx+10h]
0x180008072  call    WPP_SF_S
0x180008077  mov     rcx, rbx; this
0x18000807a  cmp     [rbx+18h], r13b
0x18000807e  jz      short loc_180008087
0x180008080  call    ?ClearWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearWakeEnabledTimer(void)
0x180008085  jmp     short loc_18000808C
0x180008087  call    ?ClearNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearNonWakeEnabledTimer(void)
0x18000808c  mov     [rbx+10h], r13
0x180008090  jmp     loc_180007E1B
```
