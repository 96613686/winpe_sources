# std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>,std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::_Emplace_reallocate<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &>(std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> * const,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &)

- ea: `0x18002a440`
- end: `0x18002a74b`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@?$vector@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@1@QEAV21@AEBV21@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18002a964`

## callees

- `0x180004434`
- `0x180004460`
- `0x1800147e4`
- `0x180014824`
- `0x18002a440`
- `0x18002a754`
- `0x18002a870`
- `0x180041010`

## pseudocode

```c
char *__fastcall std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>::_Emplace_reallocate<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &>(
        char **a1,
        char *a2,
        _QWORD *a3)
{
  __int64 v4; // r9
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // r13
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r15
  _QWORD *v11; // rdi
  void *v12; // rax
  __int64 v13; // r12
  _QWORD *v14; // rdx
  __int64 v15; // rax
  char *v16; // r8
  char *v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // r12
  char *v20; // rdx
  _QWORD *v21; // rcx
  char *v22; // r14
  char *v23; // rax
  volatile signed __int32 *v24; // rsi
  char *v25; // rax
  char *v26; // rcx
  _QWORD *v28; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v29; // [rsp+28h] [rbp-38h]
  char **v30; // [rsp+30h] [rbp-30h]
  _QWORD v31[3]; // [rsp+38h] [rbp-28h] BYREF
  char *v32; // [rsp+50h] [rbp-10h]
  _QWORD *v33; // [rsp+58h] [rbp-8h]
  char *v34; // [rsp+A0h] [rbp+40h]
  char *v35; // [rsp+A0h] [rbp+40h]

  v34 = *a1;
  v4 = (a1[1] - *a1) >> 4;
  if ( v4 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<std::unique_ptr<_MIDI_PIN_INFO>>::_Xlength();
  v6 = (a1[2] - *a1) >> 4;
  v7 = v6 >> 1;
  if ( v6 > 0xFFFFFFFFFFFFFFFLL - (v6 >> 1) )
    goto LABEL_43;
  v8 = v4 + 1;
  v9 = v4 + 1;
  if ( v6 + v7 >= v4 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0xFFFFFFFFFFFFFFFLL )
    goto LABEL_43;
  v10 = 16 * v9;
  if ( !(16 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(16 * v9);
    goto LABEL_13;
  }
  if ( v10 + 39 < v10 )
LABEL_43:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    goto LABEL_38;
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_13:
  v13 = (a2 - v34) >> 4;
  v31[2] = v9;
  v14 = &v11[2 * v13];
  v31[0] = a1;
  *v14 = 0;
  v33 = v14 + 2;
  v14[1] = 0;
  v15 = a3[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *v14 = *a3;
  v14[1] = a3[1];
  v16 = a1[1];
  v17 = *a1;
  v32 = (char *)&v11[2 * ((a2 - v34) >> 4)];
  v18 = v11;
  v30 = a1;
  v29 = v11;
  if ( a2 == v16 )
  {
    if ( v17 != v16 )
    {
      do
      {
        *v18 = 0;
        v18[1] = 0;
        *v18 = *(_QWORD *)v17;
        v18[1] = *((_QWORD *)v17 + 1);
        v18 += 2;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v17 + 1) = 0;
        v17 += 16;
      }
      while ( v17 != v16 );
      v29 = v18;
    }
    v28 = v18;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(&v28);
    v19 = 2 * v13;
  }
  else
  {
    if ( v17 != a2 )
    {
      do
      {
        *v18 = 0;
        v18[1] = 0;
        *v18 = *(_QWORD *)v17;
        v18[1] = *((_QWORD *)v17 + 1);
        v18 += 2;
        *(_QWORD *)v17 = 0;
        *((_QWORD *)v17 + 1) = 0;
        v17 += 16;
      }
      while ( v17 != a2 );
      v29 = v18;
    }
    v28 = v18;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(&v28);
    v20 = a1[1];
    v19 = 2 * v13;
    v32 = (char *)v11;
    v30 = a1;
    v21 = &v11[v19 + 2];
    v29 = v21;
    if ( a2 != v20 )
    {
      do
      {
        *v21 = 0;
        v21[1] = 0;
        *v21 = *(_QWORD *)a2;
        v21[1] = *((_QWORD *)a2 + 1);
        v21 += 2;
        *(_QWORD *)a2 = 0;
        *((_QWORD *)a2 + 1) = 0;
        a2 += 16;
      }
      while ( a2 != v20 );
      v29 = v21;
    }
    v28 = v21;
    std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(&v28);
  }
  v31[1] = 0;
  v22 = *a1;
  if ( *a1 )
  {
    v35 = a1[1];
    if ( v22 != v35 )
    {
      v23 = a1[1];
      do
      {
        v24 = (volatile signed __int32 *)*((_QWORD *)v22 + 1);
        if ( v24 )
        {
          if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
          v23 = v35;
        }
        v22 += 16;
      }
      while ( v22 != v23 );
    }
    v25 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v26 = *a1;
    }
    else
    {
      v26 = (char *)*((_QWORD *)v25 - 1);
      if ( (unsigned __int64)(v25 - v26 - 8) > 0x1F )
LABEL_38:
        __fastfail(5u);
    }
    operator delete(v26);
  }
  *a1 = (char *)v11;
  a1[1] = (char *)&v11[2 * v8];
  a1[2] = (char *)&v11[v10 / 8];
  std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>::_Reallocation_guard::~_Reallocation_guard(v31);
  return (char *)&v11[v19];
}

```

## disassembly

```asm
0x18002a440  mov     [rsp-38h+arg_8], rbx
0x18002a445  mov     [rsp-38h+arg_10], r8
0x18002a44a  push    rbp
0x18002a44b  push    rsi
0x18002a44c  push    rdi
0x18002a44d  push    r12
0x18002a44f  push    r13
0x18002a451  push    r14
0x18002a453  push    r15
0x18002a455  mov     rbp, rsp
0x18002a458  sub     rsp, 60h
0x18002a45c  mov     rax, [rcx]
0x18002a45f  mov     r8, 0FFFFFFFFFFFFFFFh
0x18002a469  mov     r9, [rcx+8]
0x18002a46d  mov     rsi, rdx
0x18002a470  sub     r9, rax
0x18002a473  mov     [rbp+arg_0], rax
0x18002a477  sar     r9, 4
0x18002a47b  mov     rbx, rcx
0x18002a47e  cmp     r9, r8
0x18002a481  jz      loc_18002A73F
0x18002a487  mov     rcx, [rcx+10h]
0x18002a48b  sub     rcx, rax
0x18002a48e  mov     rax, r8
0x18002a491  sar     rcx, 4
0x18002a495  mov     rdx, rcx
0x18002a498  shr     rdx, 1
0x18002a49b  sub     rax, rdx
0x18002a49e  cmp     rcx, rax
0x18002a4a1  ja      loc_18002A745
0x18002a4a7  lea     r13, [r9+1]
0x18002a4ab  lea     rax, [rcx+rdx]
0x18002a4af  mov     r14, r13
0x18002a4b2  cmp     rax, r13
0x18002a4b5  cmovnb  r14, rax
0x18002a4b9  cmp     r14, r8
0x18002a4bc  ja      loc_18002A745
0x18002a4c2  mov     r15, r14
0x18002a4c5  shl     r15, 4
0x18002a4c9  test    r15, r15
0x18002a4cc  jnz     short loc_18002A4D2
0x18002a4ce  xor     edi, edi
0x18002a4d0  jmp     short loc_18002A50F
0x18002a4d2  cmp     r15, 1000h
0x18002a4d9  jb      short loc_18002A504
0x18002a4db  lea     rcx, [r15+27h]; Size
0x18002a4df  cmp     rcx, r15
0x18002a4e2  jbe     loc_18002A745
0x18002a4e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a4ed  test    rax, rax
0x18002a4f0  jz      loc_18002A6F5
0x18002a4f6  lea     rdi, [rax+27h]
0x18002a4fa  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18002a4fe  mov     [rdi-8], rax
0x18002a502  jmp     short loc_18002A50F
0x18002a504  mov     rcx, r15; Size
0x18002a507  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a50c  mov     rdi, rax
0x18002a50f  mov     rcx, [rbp+arg_10]
0x18002a513  mov     r12, rsi
0x18002a516  sub     r12, [rbp+arg_0]
0x18002a51a  sar     r12, 4
0x18002a51e  mov     rdx, r12
0x18002a521  mov     [rbp+var_18], r14
0x18002a525  xor     r14d, r14d
0x18002a528  shl     rdx, 4
0x18002a52c  add     rdx, rdi
0x18002a52f  mov     [rbp+var_28], rbx
0x18002a533  lea     rax, [rdx+10h]
0x18002a537  mov     [rdx], r14
0x18002a53a  mov     [rbp+var_8], rax
0x18002a53e  mov     [rdx+8], r14
0x18002a542  mov     rax, [rcx+8]
0x18002a546  test    rax, rax
0x18002a549  jz      short loc_18002A54F
0x18002a54b  lock inc dword ptr [rax+8]
0x18002a54f  mov     rax, [rcx]
0x18002a552  mov     [rdx], rax
0x18002a555  mov     rax, [rcx+8]
0x18002a559  mov     [rdx+8], rax
0x18002a55d  mov     r8, [rbx+8]
0x18002a561  mov     rcx, [rbx]
0x18002a564  mov     [rbp+var_10], rdx
0x18002a568  mov     rdx, rdi
0x18002a56b  mov     [rbp+var_30], rbx
0x18002a56f  mov     [rbp+var_38], rdx
0x18002a573  cmp     rsi, r8
0x18002a576  jnz     short loc_18002A5C0
0x18002a578  cmp     rcx, r8
0x18002a57b  jz      short loc_18002A5AA
0x18002a57d  mov     [rdx], r14
0x18002a580  mov     [rdx+8], r14
0x18002a584  mov     rax, [rcx]
0x18002a587  mov     [rdx], rax
0x18002a58a  mov     rax, [rcx+8]
0x18002a58e  mov     [rdx+8], rax
0x18002a592  add     rdx, 10h
0x18002a596  mov     [rcx], r14
0x18002a599  mov     [rcx+8], r14
0x18002a59d  add     rcx, 10h
0x18002a5a1  cmp     rcx, r8
0x18002a5a4  jnz     short loc_18002A57D
0x18002a5a6  mov     [rbp+var_38], rdx
0x18002a5aa  lea     rcx, [rbp+var_40]
0x18002a5ae  mov     [rbp+var_40], rdx
0x18002a5b2  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(void)
0x18002a5b7  shl     r12, 4
0x18002a5bb  jmp     loc_18002A65A
0x18002a5c0  cmp     rcx, rsi
0x18002a5c3  jz      short loc_18002A5F2
0x18002a5c5  mov     [rdx], r14
0x18002a5c8  mov     [rdx+8], r14
0x18002a5cc  mov     rax, [rcx]
0x18002a5cf  mov     [rdx], rax
0x18002a5d2  mov     rax, [rcx+8]
0x18002a5d6  mov     [rdx+8], rax
0x18002a5da  add     rdx, 10h
0x18002a5de  mov     [rcx], r14
0x18002a5e1  mov     [rcx+8], r14
0x18002a5e5  add     rcx, 10h
0x18002a5e9  cmp     rcx, rsi
0x18002a5ec  jnz     short loc_18002A5C5
0x18002a5ee  mov     [rbp+var_38], rdx
0x18002a5f2  lea     rcx, [rbp+var_40]
0x18002a5f6  mov     [rbp+var_40], rdx
0x18002a5fa  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(void)
0x18002a5ff  mov     rdx, [rbx+8]
0x18002a603  shl     r12, 4
0x18002a607  mov     [rbp+var_10], rdi
0x18002a60b  mov     [rbp+var_30], rbx
0x18002a60f  lea     rcx, [r12+10h]
0x18002a614  add     rcx, rdi
0x18002a617  mov     [rbp+var_38], rcx
0x18002a61b  cmp     rsi, rdx
0x18002a61e  jz      short loc_18002A64D
0x18002a620  mov     [rcx], r14
0x18002a623  mov     [rcx+8], r14
0x18002a627  mov     rax, [rsi]
0x18002a62a  mov     [rcx], rax
0x18002a62d  mov     rax, [rsi+8]
0x18002a631  mov     [rcx+8], rax
0x18002a635  add     rcx, 10h
0x18002a639  mov     [rsi], r14
0x18002a63c  mov     [rsi+8], r14
0x18002a640  add     rsi, 10h
0x18002a644  cmp     rsi, rdx
0x18002a647  jnz     short loc_18002A620
0x18002a649  mov     [rbp+var_38], rcx
0x18002a64d  mov     [rbp+var_40], rcx
0x18002a651  lea     rcx, [rbp+var_40]
0x18002a655  call    ??1?$_Uninitialized_backout_al@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAA@XZ; std::_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>::~_Uninitialized_backout_al<std::allocator<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>>(void)
0x18002a65a  mov     [rbp+var_20], r14
0x18002a65e  mov     r14, [rbx]
0x18002a661  test    r14, r14
0x18002a664  jz      loc_18002A704
0x18002a66a  mov     rsi, [rbx+8]
0x18002a66e  mov     [rbp+arg_0], rsi
0x18002a672  cmp     r14, rsi
0x18002a675  jz      short loc_18002A6C7
0x18002a677  mov     rax, rsi
0x18002a67a  mov     rsi, [r14+8]
0x18002a67e  test    rsi, rsi
0x18002a681  jz      short loc_18002A6BE
0x18002a683  or      eax, 0FFFFFFFFh
0x18002a686  lock xadd [rsi+8], eax
0x18002a68b  cmp     eax, 1
0x18002a68e  jnz     short loc_18002A6BA
0x18002a690  mov     rax, [rsi]
0x18002a693  mov     rcx, rsi
0x18002a696  mov     rax, [rax]
0x18002a699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a69e  or      eax, 0FFFFFFFFh
0x18002a6a1  lock xadd [rsi+0Ch], eax
0x18002a6a6  cmp     eax, 1
0x18002a6a9  jnz     short loc_18002A6BA
0x18002a6ab  mov     rax, [rsi]
0x18002a6ae  mov     rcx, rsi
0x18002a6b1  mov     rax, [rax+8]
0x18002a6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6ba  mov     rax, [rbp+arg_0]
0x18002a6be  add     r14, 10h
0x18002a6c2  cmp     r14, rax
0x18002a6c5  jnz     short loc_18002A67A
0x18002a6c7  mov     rax, [rbx]
0x18002a6ca  mov     rdx, [rbx+10h]
0x18002a6ce  sub     rdx, rax
0x18002a6d1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002a6d5  cmp     rdx, 1000h
0x18002a6dc  jb      short loc_18002A6FC
0x18002a6de  mov     rcx, [rax-8]
0x18002a6e2  sub     rax, rcx
0x18002a6e5  sub     rax, 8
0x18002a6e9  cmp     rax, 1Fh
0x18002a6ed  ja      short loc_18002A6F5
0x18002a6ef  add     rdx, 27h ; '''
0x18002a6f3  jmp     short loc_18002A6FF
0x18002a6f5  mov     ecx, 5
0x18002a6fa  int     29h; Win8: RtlFailFast(ecx)
0x18002a6fc  mov     rcx, rax; Block
0x18002a6ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a704  mov     [rbx], rdi
0x18002a707  lea     rax, [r15+rdi]
0x18002a70b  shl     r13, 4
0x18002a70f  lea     rcx, [rbp+var_28]
0x18002a713  add     r13, rdi
0x18002a716  mov     [rbx+8], r13
0x18002a71a  mov     [rbx+10h], rax
0x18002a71e  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002a723  mov     rbx, [rsp+60h+arg_8]
0x18002a72b  lea     rax, [r12+rdi]
0x18002a72f  add     rsp, 60h
0x18002a733  pop     r15
0x18002a735  pop     r14
0x18002a737  pop     r13
0x18002a739  pop     r12
0x18002a73b  pop     rdi
0x18002a73c  pop     rsi
0x18002a73d  pop     rbp
0x18002a73e  retn
0x18002a73f  call    ?_Xlength@?$vector@V?$unique_ptr@V_MIDI_PIN_INFO@@U?$default_delete@V_MIDI_PIN_INFO@@@std@@@std@@V?$allocator@V?$unique_ptr@V_MIDI_PIN_INFO@@U?$default_delete@V_MIDI_PIN_INFO@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::unique_ptr<_MIDI_PIN_INFO>>::_Xlength(void)
0x18002a745  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
