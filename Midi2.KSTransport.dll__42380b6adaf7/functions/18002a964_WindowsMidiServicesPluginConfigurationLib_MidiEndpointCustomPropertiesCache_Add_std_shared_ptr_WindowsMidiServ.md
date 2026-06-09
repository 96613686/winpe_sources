# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::Add(std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>)

- ea: `0x18002a964`
- end: `0x18002ad4c`
- name: `?Add@MidiEndpointCustomPropertiesCache@WindowsMidiServicesPluginConfigurationLib@@QEAA_NV?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@4@@Z`
- size: `1000`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800230a0`

## callees

- `0x180004460`
- `0x18002a440`
- `0x18002a964`
- `0x18002cccc`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::Add(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  char *i; // rbx
  __int64 *v7; // rsi
  __int64 *v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  volatile signed __int32 *v11; // r14
  volatile signed __int32 *v12; // rbx
  char *v13; // rbx
  _QWORD *v14; // r14
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rsi
  __int64 v24; // rdx
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  _QWORD v27[9]; // [rsp+20h] [rbp-48h] BYREF

  for ( i = *(char **)a1; i != *(char **)(a1 + 8); i += 16 )
  {
    v7 = (__int64 *)(i + 16);
    if ( WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(
           **(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria ***)i,
           *(struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria **)a2) )
    {
      v8 = *(__int64 **)(a1 + 8);
      while ( v7 != v8 )
      {
        v9 = *v7;
        v10 = v7[1];
        *v7 = 0;
        v7[1] = 0;
        *(_QWORD *)i = v9;
        v11 = (volatile signed __int32 *)*((_QWORD *)i + 1);
        *((_QWORD *)i + 1) = v10;
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        i += 16;
        v7 += 2;
      }
      v12 = *(volatile signed __int32 **)(*(_QWORD *)(a1 + 8) - 8LL);
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      *(_QWORD *)(a1 + 8) -= 16LL;
      break;
    }
  }
  v13 = (char *)operator new(0x30u);
  *(_OWORD *)v13 = 0;
  *((_DWORD *)v13 + 2) = 1;
  *((_DWORD *)v13 + 3) = 1;
  *(_QWORD *)v13 = &std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>::`vftable';
  v14 = v13 + 16;
  *((_QWORD *)v13 + 2) = 0;
  *((_QWORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 4) = 0;
  *((_QWORD *)v13 + 5) = 0;
  v27[0] = v13 + 16;
  v27[1] = v13;
  if ( v13 == (char *)-16LL )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL) )
    {
      ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
      if ( !_InterlockedDecrement((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL) )
        (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
    }
    v15 = *(volatile signed __int32 **)(a2 + 8);
    if ( v15 )
    {
      if ( !_InterlockedDecrement(v15 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( !_InterlockedDecrement(v15 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = (volatile signed __int32 *)a3[1];
    if ( v16 && !_InterlockedDecrement(v16 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( !_InterlockedDecrement(v16 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    return 0;
  }
  else
  {
    v18 = *(_QWORD *)(a2 + 8);
    if ( v18 )
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
    v19 = *(_QWORD *)(a2 + 8);
    *v14 = *(_QWORD *)a2;
    v20 = (volatile signed __int32 *)*((_QWORD *)v13 + 3);
    *((_QWORD *)v13 + 3) = v19;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v21 = a3[1];
    if ( v21 )
      _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
    v22 = a3[1];
    *((_QWORD *)v13 + 4) = *a3;
    v23 = (volatile signed __int32 *)*((_QWORD *)v13 + 5);
    *((_QWORD *)v13 + 5) = v22;
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v24 = *(_QWORD *)(a1 + 8);
    if ( v24 == *(_QWORD *)(a1 + 16) )
    {
      std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>::_Emplace_reallocate<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &>(
        (char **)a1,
        (char *)v24,
        v27);
    }
    else
    {
      *(_QWORD *)v24 = 0;
      *(_QWORD *)(v24 + 8) = 0;
      _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
      *(_QWORD *)v24 = v14;
      *(_QWORD *)(v24 + 8) = v13;
      *(_QWORD *)(a1 + 8) += 16LL;
    }
    if ( !_InterlockedDecrement((volatile signed __int32 *)v13 + 2) )
    {
      (**(void (__fastcall ***)(void *))v13)(v13);
      if ( !_InterlockedDecrement((volatile signed __int32 *)v13 + 3) )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    v25 = *(volatile signed __int32 **)(a2 + 8);
    if ( v25 )
    {
      if ( !_InterlockedDecrement(v25 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( !_InterlockedDecrement(v25 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    v26 = (volatile signed __int32 *)a3[1];
    if ( v26 )
    {
      if ( !_InterlockedDecrement(v26 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18002a964  mov     [rsp+arg_18], rbx
0x18002a969  mov     [rsp+arg_10], r8
0x18002a96e  mov     [rsp+arg_8], rdx
0x18002a973  push    rbp
0x18002a974  push    rsi
0x18002a975  push    rdi
0x18002a976  push    r12
0x18002a978  push    r13
0x18002a97a  push    r14
0x18002a97c  push    r15
0x18002a97e  sub     rsp, 30h
0x18002a982  mov     r12, r8
0x18002a985  mov     r15, rdx
0x18002a988  mov     rdi, rcx
0x18002a98b  xor     ebp, ebp
0x18002a98d  mov     rbx, [rcx]
0x18002a990  or      r13d, 0FFFFFFFFh
0x18002a994  cmp     rbx, [rdi+8]
0x18002a998  jz      loc_18002AA76
0x18002a99e  lea     rsi, [rbx+10h]
0x18002a9a2  mov     rcx, [rbx]
0x18002a9a5  mov     rdx, [r15]; struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *
0x18002a9a8  mov     rcx, [rcx]; this
0x18002a9ab  call    ?Matches@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV12@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria &)
0x18002a9b0  test    al, al
0x18002a9b2  jnz     short loc_18002A9B9
0x18002a9b4  mov     rbx, rsi
0x18002a9b7  jmp     short loc_18002A990
0x18002a9b9  mov     rbp, [rdi+8]
0x18002a9bd  jmp     short loc_18002AA26
0x18002a9bf  mov     rax, [rsi]
0x18002a9c2  mov     rcx, [rsi+8]
0x18002a9c6  mov     qword ptr [rsi], 0
0x18002a9cd  mov     qword ptr [rsi+8], 0
0x18002a9d5  mov     [rbx], rax
0x18002a9d8  mov     r14, [rbx+8]
0x18002a9dc  mov     [rbx+8], rcx
0x18002a9e0  test    r14, r14
0x18002a9e3  jz      short loc_18002AA1E
0x18002a9e5  mov     eax, r13d
0x18002a9e8  lock xadd [r14+8], eax
0x18002a9ee  add     eax, r13d
0x18002a9f1  jnz     short loc_18002AA1E
0x18002a9f3  mov     rax, [r14]
0x18002a9f6  mov     rcx, r14
0x18002a9f9  mov     rax, [rax]
0x18002a9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa01  mov     eax, r13d
0x18002aa04  lock xadd [r14+0Ch], eax
0x18002aa0a  add     eax, r13d
0x18002aa0d  jnz     short loc_18002AA1E
0x18002aa0f  mov     rax, [r14]
0x18002aa12  mov     rcx, r14
0x18002aa15  mov     rax, [rax+8]
0x18002aa19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa1e  add     rbx, 10h
0x18002aa22  add     rsi, 10h
0x18002aa26  cmp     rsi, rbp
0x18002aa29  jnz     short loc_18002A9BF
0x18002aa2b  mov     rax, [rdi+8]
0x18002aa2f  mov     rbx, [rax-8]
0x18002aa33  xor     ebp, ebp
0x18002aa35  test    rbx, rbx
0x18002aa38  jz      short loc_18002AA71
0x18002aa3a  mov     eax, r13d
0x18002aa3d  lock xadd [rbx+8], eax
0x18002aa42  add     eax, r13d
0x18002aa45  jnz     short loc_18002AA71
0x18002aa47  mov     rax, [rbx]
0x18002aa4a  mov     rcx, rbx
0x18002aa4d  mov     rax, [rax]
0x18002aa50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa55  mov     eax, r13d
0x18002aa58  lock xadd [rbx+0Ch], eax
0x18002aa5d  add     eax, r13d
0x18002aa60  jnz     short loc_18002AA71
0x18002aa62  mov     rax, [rbx]
0x18002aa65  mov     rcx, rbx
0x18002aa68  mov     rax, [rax+8]
0x18002aa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa71  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFF0h
0x18002aa76  mov     ecx, 30h ; '0'; Size
0x18002aa7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002aa80  mov     rbx, rax
0x18002aa83  mov     [rsp+68h+arg_0], rax
0x18002aa88  xorps   xmm0, xmm0
0x18002aa8b  movups  xmmword ptr [rax], xmm0
0x18002aa8e  mov     dword ptr [rax+8], 1
0x18002aa95  mov     dword ptr [rax+0Ch], 1
0x18002aa9c  lea     rax, ??_7?$_Ref_count_obj2@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>::`vftable'
0x18002aaa3  mov     [rbx], rax
0x18002aaa6  lea     r14, [rbx+10h]
0x18002aaaa  mov     [r14], rbp
0x18002aaad  mov     [r14+8], rbp
0x18002aab1  mov     [r14+10h], rbp
0x18002aab5  mov     [r14+18h], rbp
0x18002aab9  mov     [rsp+68h+var_48], r14
0x18002aabe  mov     [rsp+68h+var_40], rbx
0x18002aac3  test    r14, r14
0x18002aac6  jnz     loc_18002AB8D
0x18002aacc  mov     eax, r13d
0x18002aacf  lock xadd [rbx+8], eax
0x18002aad4  add     eax, r13d
0x18002aad7  jnz     short loc_18002AB04
0x18002aad9  mov     rax, [rbx]
0x18002aadc  mov     rcx, rbx
0x18002aadf  mov     rax, [rax]
0x18002aae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aae7  mov     eax, r13d
0x18002aaea  lock xadd [rbx+0Ch], eax
0x18002aaef  add     eax, r13d
0x18002aaf2  jnz     short loc_18002AB04
0x18002aaf4  mov     rax, [rbx]
0x18002aaf7  mov     rcx, rbx
0x18002aafa  mov     rax, [rax+8]
0x18002aafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab03  nop
0x18002ab04  mov     rbx, [r15+8]
0x18002ab08  test    rbx, rbx
0x18002ab0b  jz      short loc_18002AB45
0x18002ab0d  mov     eax, r13d
0x18002ab10  lock xadd [rbx+8], eax
0x18002ab15  add     eax, r13d
0x18002ab18  jnz     short loc_18002AB45
0x18002ab1a  mov     rax, [rbx]
0x18002ab1d  mov     rcx, rbx
0x18002ab20  mov     rax, [rax]
0x18002ab23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab28  mov     eax, r13d
0x18002ab2b  lock xadd [rbx+0Ch], eax
0x18002ab30  add     eax, r13d
0x18002ab33  jnz     short loc_18002AB45
0x18002ab35  mov     rax, [rbx]
0x18002ab38  mov     rcx, rbx
0x18002ab3b  mov     rax, [rax+8]
0x18002ab3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab44  nop
0x18002ab45  mov     rbx, [r12+8]
0x18002ab4a  test    rbx, rbx
0x18002ab4d  jz      short loc_18002AB86
0x18002ab4f  mov     eax, r13d
0x18002ab52  lock xadd [rbx+8], eax
0x18002ab57  add     eax, r13d
0x18002ab5a  jnz     short loc_18002AB86
0x18002ab5c  mov     rax, [rbx]
0x18002ab5f  mov     rcx, rbx
0x18002ab62  mov     rax, [rax]
0x18002ab65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab6a  mov     eax, r13d
0x18002ab6d  lock xadd [rbx+0Ch], eax
0x18002ab72  add     eax, r13d
0x18002ab75  jnz     short loc_18002AB86
0x18002ab77  mov     rax, [rbx]
0x18002ab7a  mov     rcx, rbx
0x18002ab7d  mov     rax, [rax+8]
0x18002ab81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab86  xor     al, al
0x18002ab88  jmp     loc_18002AD34
0x18002ab8d  mov     rax, [r15+8]
0x18002ab91  test    rax, rax
0x18002ab94  jz      short loc_18002AB9A
0x18002ab96  lock inc dword ptr [rax+8]
0x18002ab9a  mov     rcx, [r15+8]
0x18002ab9e  mov     rax, [r15]
0x18002aba1  mov     [r14], rax
0x18002aba4  mov     rsi, [r14+8]
0x18002aba8  mov     [r14+8], rcx
0x18002abac  test    rsi, rsi
0x18002abaf  jz      short loc_18002ABE8
0x18002abb1  mov     eax, r13d
0x18002abb4  lock xadd [rsi+8], eax
0x18002abb9  add     eax, r13d
0x18002abbc  jnz     short loc_18002ABE8
0x18002abbe  mov     rax, [rsi]
0x18002abc1  mov     rcx, rsi
0x18002abc4  mov     rax, [rax]
0x18002abc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abcc  mov     eax, r13d
0x18002abcf  lock xadd [rsi+0Ch], eax
0x18002abd4  add     eax, r13d
0x18002abd7  jnz     short loc_18002ABE8
0x18002abd9  mov     rax, [rsi]
0x18002abdc  mov     rcx, rsi
0x18002abdf  mov     rax, [rax+8]
0x18002abe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abe8  mov     rax, [r12+8]
0x18002abed  test    rax, rax
0x18002abf0  jz      short loc_18002ABF6
0x18002abf2  lock inc dword ptr [rax+8]
0x18002abf6  mov     rcx, [r12+8]
0x18002abfb  mov     rax, [r12]
0x18002abff  mov     [r14+10h], rax
0x18002ac03  mov     rsi, [r14+18h]
0x18002ac07  mov     [r14+18h], rcx
0x18002ac0b  test    rsi, rsi
0x18002ac0e  jz      short loc_18002AC47
0x18002ac10  mov     eax, r13d
0x18002ac13  lock xadd [rsi+8], eax
0x18002ac18  add     eax, r13d
0x18002ac1b  jnz     short loc_18002AC47
0x18002ac1d  mov     rax, [rsi]
0x18002ac20  mov     rcx, rsi
0x18002ac23  mov     rax, [rax]
0x18002ac26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac2b  mov     eax, r13d
0x18002ac2e  lock xadd [rsi+0Ch], eax
0x18002ac33  add     eax, r13d
0x18002ac36  jnz     short loc_18002AC47
0x18002ac38  mov     rax, [rsi]
0x18002ac3b  mov     rcx, rsi
0x18002ac3e  mov     rax, [rax+8]
0x18002ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac47  mov     rdx, [rdi+8]
0x18002ac4b  cmp     rdx, [rdi+10h]
0x18002ac4f  jz      short loc_18002AC6A
0x18002ac51  mov     [rdx], rbp
0x18002ac54  mov     [rdx+8], rbp
0x18002ac58  lock inc dword ptr [rbx+8]
0x18002ac5c  mov     [rdx], r14
0x18002ac5f  mov     [rdx+8], rbx
0x18002ac63  add     qword ptr [rdi+8], 10h
0x18002ac68  jmp     short loc_18002AC78
0x18002ac6a  lea     r8, [rsp+68h+var_48]
0x18002ac6f  mov     rcx, rdi
0x18002ac72  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@?$vector@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$allocator@V?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UMidiEndpointCustomPropertiesCacheEntry@WindowsMidiServicesPluginConfigurationLib@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry>>::_Emplace_reallocate<std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &>(std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> * const,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCacheEntry> const &)
0x18002ac77  nop
0x18002ac78  mov     eax, r13d
0x18002ac7b  lock xadd [rbx+8], eax
0x18002ac80  add     eax, r13d
0x18002ac83  jnz     short loc_18002ACB0
0x18002ac85  mov     rax, [rbx]
0x18002ac88  mov     rcx, rbx
0x18002ac8b  mov     rax, [rax]
0x18002ac8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac93  mov     eax, r13d
0x18002ac96  lock xadd [rbx+0Ch], eax
0x18002ac9b  add     eax, r13d
0x18002ac9e  jnz     short loc_18002ACB0
0x18002aca0  mov     rax, [rbx]
0x18002aca3  mov     rcx, rbx
0x18002aca6  mov     rax, [rax+8]
0x18002acaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acaf  nop
0x18002acb0  mov     rbx, [r15+8]
0x18002acb4  test    rbx, rbx
0x18002acb7  jz      short loc_18002ACF1
0x18002acb9  mov     eax, r13d
0x18002acbc  lock xadd [rbx+8], eax
0x18002acc1  add     eax, r13d
0x18002acc4  jnz     short loc_18002ACF1
0x18002acc6  mov     rax, [rbx]
0x18002acc9  mov     rcx, rbx
0x18002accc  mov     rax, [rax]
0x18002accf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acd4  mov     eax, r13d
0x18002acd7  lock xadd [rbx+0Ch], eax
0x18002acdc  add     eax, r13d
0x18002acdf  jnz     short loc_18002ACF1
0x18002ace1  mov     rax, [rbx]
0x18002ace4  mov     rcx, rbx
0x18002ace7  mov     rax, [rax+8]
0x18002aceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acf0  nop
0x18002acf1  mov     rbx, [r12+8]
0x18002acf6  test    rbx, rbx
0x18002acf9  jz      short loc_18002AD32
0x18002acfb  mov     eax, r13d
0x18002acfe  lock xadd [rbx+8], eax
0x18002ad03  add     eax, r13d
0x18002ad06  jnz     short loc_18002AD32
0x18002ad08  mov     rax, [rbx]
0x18002ad0b  mov     rcx, rbx
0x18002ad0e  mov     rax, [rax]
0x18002ad11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad16  mov     edx, r13d
0x18002ad19  lock xadd [rbx+0Ch], edx
0x18002ad1e  add     edx, r13d
0x18002ad21  jnz     short loc_18002AD32
0x18002ad23  mov     rdx, [rbx]
0x18002ad26  mov     rcx, rbx
0x18002ad29  mov     rax, [rdx+8]
0x18002ad2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad32  mov     al, 1
0x18002ad34  mov     rbx, [rsp+68h+arg_18]
0x18002ad3c  add     rsp, 30h
0x18002ad40  pop     r15
0x18002ad42  pop     r14
0x18002ad44  pop     r13
0x18002ad46  pop     r12
0x18002ad48  pop     rdi
0x18002ad49  pop     rsi
0x18002ad4a  pop     rbp
0x18002ad4b  retn
```
