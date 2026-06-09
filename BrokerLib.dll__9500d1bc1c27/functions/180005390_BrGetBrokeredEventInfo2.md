# BrGetBrokeredEventInfo2

- ea: `0x180005390`
- end: `0x180005577`
- name: `BrGetBrokeredEventInfo2`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005390`
- `0x1800058e0`
- `0x180005a80`
- `0x180005b50`
- `0x180009e94`
- `0x18001e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrGetBrokeredEventInfo2(const void *a1, __int64 a2, _DWORD *a3, _DWORD *a4, _QWORD *a5)
{
  unsigned int v8; // ebx
  _QWORD *v9; // r14
  __int64 v10; // r15
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  __int64 result; // rax
  Broker::Win32Error *v15; // [rsp+20h] [rbp-68h] BYREF
  __int64 v16; // [rsp+28h] [rbp-60h] BYREF
  volatile signed __int32 *v17; // [rsp+30h] [rbp-58h]
  __int64 v18; // [rsp+38h] [rbp-50h] BYREF
  volatile signed __int32 *v19; // [rsp+40h] [rbp-48h]
  __int64 v20; // [rsp+90h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
  {
    v8 = 87;
    goto LABEL_29;
  }
  if ( a3 || a4 )
  {
    v9 = a5;
  }
  else
  {
    v9 = a5;
    if ( !a5 )
    {
      v8 = 87;
      goto LABEL_29;
    }
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v18, a1);
    v10 = v18;
    v20 = a2;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
        *(_QWORD *)(v18 + 8));
    Broker::BrokeredEventTable::Find(v10 + 208, &v16, &v20);
    v11 = v16;
    if ( a3 )
      *a3 = *(_DWORD *)(v16 + 28);
    if ( a4 )
      *a4 = *(_DWORD *)(v11 + 32);
    if ( v9 )
      *v9 = *(_QWORD *)(v11 + 40);
    v12 = v17;
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = v19;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    result = 0;
  }
  catch ( Broker::NotFound )
  {
    LODWORD(v20) = 1168;
    v8 = 1168;
    goto LABEL_29;
  }
  catch ( Broker::Win32Error *v15 )
  {
    LODWORD(v20) = *((_DWORD *)v15 + 8);
    v8 = v20;
    if ( !(_DWORD)v20 )
      return v8;
LABEL_29:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v8);
    return v8;
  }
  catch ( ... )
  {
    LODWORD(v20) = 1287;
    v8 = 1287;
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x180005390  push    rbx
0x180005392  push    rsi
0x180005393  push    rdi
0x180005394  push    r12
0x180005396  push    r14
0x180005398  push    r15
0x18000539a  sub     rsp, 58h
0x18000539e  mov     rsi, r9
0x1800053a1  mov     rdi, r8
0x1800053a4  mov     rbx, rdx
0x1800053a7  test    rcx, rcx
0x1800053aa  jnz     short loc_1800053B6
0x1800053ac  mov     ebx, 57h ; 'W'
0x1800053b1  jmp     loc_180005547
0x1800053b6  test    rbx, rbx
0x1800053b9  jz      short loc_1800053AC
0x1800053bb  xor     r12d, r12d
0x1800053be  test    rdi, rdi
0x1800053c1  jnz     short loc_1800053DF
0x1800053c3  test    rsi, rsi
0x1800053c6  jnz     short loc_1800053DF
0x1800053c8  mov     r14, [rsp+88h+arg_20]
0x1800053d0  test    r14, r14
0x1800053d3  jnz     short loc_1800053E7
0x1800053d5  mov     ebx, 57h ; 'W'
0x1800053da  jmp     loc_180005547
0x1800053df  mov     r14, [rsp+88h+arg_20]
0x1800053e7  mov     rdx, rcx
0x1800053ea  lea     rcx, [rsp+88h+var_50]
0x1800053ef  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800053f4  nop
0x1800053f5  mov     r15, [rsp+88h+var_50]
0x1800053fa  mov     [rsp+88h+arg_0], rbx
0x180005402  mov     rcx, cs:WPP_GLOBAL_Control
0x180005409  test    dword ptr [rcx+1Ch], 800h
0x180005410  jz      short loc_180005431
0x180005412  cmp     byte ptr [rcx+19h], 5
0x180005416  jb      short loc_180005431
0x180005418  mov     r9, [r15+8]
0x18000541c  mov     edx, 24h ; '$'
0x180005421  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180005428  mov     rcx, [rcx+10h]
0x18000542c  call    WPP_SF__guid_
0x180005431  lea     rcx, [r15+0D0h]
0x180005438  lea     r8, [rsp+88h+arg_0]
0x180005440  lea     rdx, [rsp+88h+var_60]
0x180005445  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBQEAU_BROKERED_EVENT@@@Z; Broker::BrokeredEventTable::Find(_BROKERED_EVENT * const &)
0x18000544a  mov     rcx, [rsp+88h+var_60]
0x18000544f  test    rdi, rdi
0x180005452  jnz     loc_180005516
0x180005458  test    rsi, rsi
0x18000545b  jnz     loc_180005520
0x180005461  test    r14, r14
0x180005464  jz      short loc_18000546D
0x180005466  mov     rax, [rcx+28h]
0x18000546a  mov     [r14], rax
0x18000546d  mov     rbx, [rsp+88h+var_58]
0x180005472  mov     edi, 0FFFFFFFFh
0x180005477  test    rbx, rbx
0x18000547a  jz      short loc_1800054B2
0x18000547c  mov     eax, edi
0x18000547e  lock xadd [rbx+8], eax
0x180005483  cmp     eax, 1
0x180005486  jnz     short loc_1800054B2
0x180005488  mov     rax, [rbx]
0x18000548b  mov     rcx, rbx
0x18000548e  mov     rax, [rax]
0x180005491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005496  mov     eax, edi
0x180005498  lock xadd [rbx+0Ch], eax
0x18000549d  cmp     eax, 1
0x1800054a0  jnz     short loc_1800054B2
0x1800054a2  mov     rax, [rbx]
0x1800054a5  mov     rcx, rbx
0x1800054a8  mov     rax, [rax+8]
0x1800054ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b1  nop
0x1800054b2  mov     rbx, [rsp+88h+var_48]
0x1800054b7  test    rbx, rbx
0x1800054ba  jz      short loc_1800054F0
0x1800054bc  mov     eax, edi
0x1800054be  lock xadd [rbx+8], eax
0x1800054c3  cmp     eax, 1
0x1800054c6  jnz     short loc_1800054F0
0x1800054c8  mov     rax, [rbx]
0x1800054cb  mov     rcx, rbx
0x1800054ce  mov     rax, [rax]
0x1800054d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d6  lock xadd [rbx+0Ch], edi
0x1800054db  cmp     edi, 1
0x1800054de  jnz     short loc_1800054F0
0x1800054e0  mov     rax, [rbx]
0x1800054e3  mov     rcx, rbx
0x1800054e6  mov     rax, [rax+8]
0x1800054ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ef  nop
0x1800054f0  mov     eax, r12d
0x1800054f3  add     rsp, 58h
0x1800054f7  pop     r15
0x1800054f9  pop     r14
0x1800054fb  pop     r12
0x1800054fd  pop     rdi
0x1800054fe  pop     rsi
0x1800054ff  pop     rbx
0x180005500  retn
0x180005501  mov     eax, ebx
0x180005503  add     rsp, 58h
0x180005507  pop     r15
0x180005509  pop     r14
0x18000550b  pop     r12
0x18000550d  pop     rdi
0x18000550e  pop     rsi
0x18000550f  pop     rbx
0x180005510  retn
0x180005511  jmp     loc_18000541C
0x180005516  mov     eax, [rcx+1Ch]
0x180005519  mov     [rdi], eax
0x18000551b  jmp     loc_180005458
0x180005520  mov     eax, [rcx+20h]
0x180005523  mov     [rsi], eax
0x180005525  jmp     loc_180005461
0x18000552a  mov     ebx, dword ptr [rsp+88h+arg_0]
0x180005531  jmp     short loc_180005547
0x180005533  mov     ebx, dword ptr [rsp+88h+arg_0]
0x18000553a  test    ebx, ebx
0x18000553c  jz      short loc_180005501
0x18000553e  jmp     short loc_180005547
0x180005540  mov     ebx, dword ptr [rsp+88h+arg_0]
0x180005547  mov     rcx, cs:WPP_GLOBAL_Control
0x18000554e  test    dword ptr [rcx+1Ch], 800h
0x180005555  jz      short loc_180005501
0x180005557  cmp     byte ptr [rcx+19h], 2
0x18000555b  jb      short loc_180005501
0x18000555d  mov     edx, 1Ah
0x180005562  mov     r9d, ebx
0x180005565  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18000556c  mov     rcx, [rcx+10h]
0x180005570  call    WPP_SF_d
0x180005575  jmp     short loc_180005501
```
