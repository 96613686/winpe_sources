# WmiSecurityAttributes::WmiSecurityAttributes(int)

- ea: `0x14000661c`
- end: `0x1400067e1`
- name: `??0WmiSecurityAttributes@@QEAA@H@Z`
- size: `453`
- prototype: `WmiSecurityAttributes *__fastcall(WmiSecurityAttributes *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400076bc`
- `0x14000b2e4`

## callees

- `0x14000653c`
- `0x14000661c`
- `0x140006a18`
- `0x140017010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400067b4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400067b4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400066ab`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006706`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1400066ab`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006706`

## pseudocode

```c
WmiSecurityAttributes *__fastcall WmiSecurityAttributes::WmiSecurityAttributes(WmiSecurityAttributes *this)
{
  WmiSecurityAttributes *v1; // rdi
  int v2; // eax
  char *v3; // rsi
  WmiSecurity **v4; // r15
  int *v5; // r13
  int v6; // r14d
  int v7; // r12d
  _QWORD *v8; // rax
  __int64 *v9; // rdx
  WmiSecurity *v10; // rax
  WmiSecurity *v11; // rax
  _QWORD *v12; // rax
  void *v13; // rcx
  WmiSecurity *v14; // rcx
  __int64 v16; // [rsp+0h] [rbp-78h] BYREF
  WmiSecurity **v17; // [rsp+20h] [rbp-58h]
  int *v18; // [rsp+28h] [rbp-50h]
  char *v19; // [rsp+30h] [rbp-48h]
  WmiSecurity *v20; // [rsp+38h] [rbp-40h]
  int v22; // [rsp+88h] [rbp+10h]
  int v23; // [rsp+90h] [rbp+18h]
  __int64 v24; // [rsp+98h] [rbp+20h]
  __int64 v25; // [rsp+98h] [rbp+20h]

  v1 = this;
  *(_QWORD *)this = &__Wrapper<_SECURITY_ATTRIBUTES>::`vftable';
  v2 = 2;
  do
  {
    v3 = (char *)this + 8;
    v19 = (char *)this + 8;
    *((_QWORD *)this + 1) = 0;
    --v2;
  }
  while ( v2 );
  *(_QWORD *)this = &__WrapperPtr<_SECURITY_ATTRIBUTES>::`vftable';
  v4 = (WmiSecurity **)((char *)this + 24);
  v17 = (WmiSecurity **)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = &__WrapperPtr<WmiSecurity>::`vftable';
  v5 = (int *)((char *)this + 32);
  v18 = (int *)((char *)this + 32);
  *((_DWORD *)this + 8) = 0;
  v6 = 0;
  v22 = 0;
  v7 = 0;
  v23 = 0;
  v24 = *(_QWORD *)this;
  try
  {
    v8 = CWin32DefaultArena::WbemMemAlloc(0x18u);
    if ( v8 )
    {
      *(_OWORD *)v8 = 0;
      v8[2] = 0;
    }
    else
    {
      v8 = 0;
    }
    (*(void (__fastcall **)(WmiSecurityAttributes *, _QWORD *))(v24 + 8))(v1, v8);
    if ( *(_QWORD *)v3 )
    {
      v7 = 1;
      v23 = 1;
      v25 = *((_QWORD *)v1 + 2);
      v10 = (WmiSecurity *)CWin32DefaultArena::WbemMemAlloc(0x30u);
      v20 = v10;
      v11 = v10 ? WmiSecurity::WmiSecurity(v10) : 0LL;
      (*(void (__fastcall **)(__int64, WmiSecurity *))(v25 + 8))((__int64)v1 + 16, v11);
      v12 = (_QWORD *)*((_QWORD *)v1 + 3);
      if ( v12 )
      {
        if ( *v12 )
        {
          **(_DWORD **)v3 = 24;
          *(_QWORD *)(*(_QWORD *)v3 + 8LL) = **((_QWORD **)v1 + 3);
          *(_DWORD *)(*(_QWORD *)v3 + 16LL) = 0;
          v6 = 1;
          v22 = 1;
        }
      }
    }
  }
  catch ( ... )
  {
    v9 = &v16;
    v1 = this;
    v6 = v22;
    v7 = v23;
    v4 = v17;
    v5 = v18;
    v3 = v19;
  }
  if ( v7 && !v6 )
  {
    v13 = *(void **)v3;
    *(_QWORD *)v3 = 0;
    if ( v13 )
      CWin32DefaultArena::WbemMemFree(v13);
    v14 = *v4;
    *v4 = 0;
    if ( v14 )
      WmiSecurity::`scalar deleting destructor'(v14, (unsigned int)v9);
  }
  *v5 = v6;
  return v1;
}

```

## disassembly

```asm
0x14000661c  mov     [rsp+arg_8], edx
0x140006620  mov     [rsp+arg_0], rcx
0x140006625  push    rbx
0x140006626  push    rsi
0x140006627  push    rdi
0x140006628  push    r12
0x14000662a  push    r13
0x14000662c  push    r14
0x14000662e  push    r15
0x140006630  sub     rsp, 40h
0x140006634  mov     rdi, rcx
0x140006637  lea     rax, ??_7?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@6B@; const __Wrapper<_SECURITY_ATTRIBUTES>::`vftable'
0x14000663e  mov     [rcx], rax
0x140006641  mov     eax, 2
0x140006646  xor     ebx, ebx
0x140006648  lea     rsi, [rcx+8]
0x14000664c  mov     [rsp+78h+var_48], rsi
0x140006651  mov     [rsi], rbx
0x140006654  sub     eax, 1
0x140006657  jnz     short loc_140006648
0x140006659  lea     rax, ??_7?$__WrapperPtr@U_SECURITY_ATTRIBUTES@@@@6B@; const __WrapperPtr<_SECURITY_ATTRIBUTES>::`vftable'
0x140006660  mov     [rcx], rax
0x140006663  lea     r15, [rcx+18h]
0x140006667  mov     [rsp+78h+var_58], r15
0x14000666c  mov     [r15], rbx
0x14000666f  lea     rcx, ??_7?$__WrapperPtr@VWmiSecurity@@@@6B@; const __WrapperPtr<WmiSecurity>::`vftable'
0x140006676  mov     [rdi+10h], rcx
0x14000667a  lea     r13, [rdi+20h]
0x14000667e  mov     [rsp+78h+var_50], r13
0x140006683  mov     [r13+0], ebx
0x140006687  mov     r14d, ebx
0x14000668a  mov     [rsp+78h+arg_8], ebx
0x140006691  mov     r12d, ebx
0x140006694  mov     [rsp+78h+arg_10], ebx
0x14000669b  mov     rax, [rdi]
0x14000669e  mov     [rsp+78h+arg_18], rax
0x1400066a6  mov     ecx, 18h
0x1400066ab  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1400066b1  test    rax, rax
0x1400066b4  jz      short loc_1400066C4
0x1400066b6  xorps   xmm0, xmm0
0x1400066b9  xor     ecx, ecx
0x1400066bb  movups  xmmword ptr [rax], xmm0
0x1400066be  mov     [rax+10h], rcx
0x1400066c2  jmp     short loc_1400066C7
0x1400066c4  mov     rax, rbx
0x1400066c7  mov     rdx, rax
0x1400066ca  mov     rcx, rdi
0x1400066cd  mov     rax, [rsp+78h+arg_18]
0x1400066d5  mov     rax, [rax+8]
0x1400066d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066de  cmp     [rsi], rbx
0x1400066e1  jz      loc_140006774
0x1400066e7  mov     r12d, 1
0x1400066ed  mov     [rsp+78h+arg_10], r12d
0x1400066f5  mov     rax, [rdi+10h]
0x1400066f9  mov     [rsp+78h+arg_18], rax
0x140006701  lea     ecx, [r12+2Fh]
0x140006706  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000670c  mov     [rsp+78h+var_40], rax
0x140006711  test    rax, rax
0x140006714  jz      short loc_140006720
0x140006716  mov     rcx, rax; this
0x140006719  call    ??0WmiSecurity@@QEAA@XZ; WmiSecurity::WmiSecurity(void)
0x14000671e  jmp     short loc_140006723
0x140006720  mov     rax, rbx
0x140006723  mov     rdx, rax
0x140006726  lea     rcx, [rdi+10h]
0x14000672a  mov     rax, [rsp+78h+arg_18]
0x140006732  mov     rax, [rax+8]
0x140006736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000673b  mov     rax, [rdi+18h]
0x14000673f  test    rax, rax
0x140006742  jz      short loc_140006774
0x140006744  cmp     [rax], rbx
0x140006747  jz      short loc_140006774
0x140006749  mov     rax, [rsi]
0x14000674c  mov     dword ptr [rax], 18h
0x140006752  mov     rax, [rdi+18h]
0x140006756  mov     rcx, [rsi]
0x140006759  mov     rax, [rax]
0x14000675c  mov     [rcx+8], rax
0x140006760  mov     rax, [rsi]
0x140006763  mov     [rax+10h], ebx
0x140006766  mov     r14d, 1
0x14000676c  mov     [rsp+78h+arg_8], r14d
0x140006774  jmp     short loc_14000679F
0x140006776  xor     ebx, ebx
0x140006778  mov     rdi, [rsp+78h+arg_0]
0x140006780  mov     r14d, [rsp+78h+arg_8]
0x140006788  mov     r12d, [rsp+78h+arg_10]
0x140006790  mov     r15, [rsp+78h+var_58]
0x140006795  mov     r13, [rsp+78h+var_50]
0x14000679a  mov     rsi, [rsp+78h+var_48]
0x14000679f  test    r12d, r12d
0x1400067a2  jz      short loc_1400067CA
0x1400067a4  test    r14d, r14d
0x1400067a7  jnz     short loc_1400067CA
0x1400067a9  mov     rcx, [rsi]
0x1400067ac  mov     [rsi], rbx
0x1400067af  test    rcx, rcx
0x1400067b2  jz      short loc_1400067BA
0x1400067b4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400067ba  mov     rcx, [r15]; this
0x1400067bd  mov     [r15], rbx
0x1400067c0  test    rcx, rcx
0x1400067c3  jz      short loc_1400067CA
0x1400067c5  call    ??_GWmiSecurity@@QEAAPEAXI@Z; WmiSecurity::`scalar deleting destructor'(uint)
0x1400067ca  mov     [r13+0], r14d
0x1400067ce  mov     rax, rdi
0x1400067d1  add     rsp, 40h
0x1400067d5  pop     r15
0x1400067d7  pop     r14
0x1400067d9  pop     r13
0x1400067db  pop     r12
0x1400067dd  pop     rdi
0x1400067de  pop     rsi
0x1400067df  pop     rbx
0x1400067e0  retn
```
