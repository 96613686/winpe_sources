# Broker::TimeBroker::AlignKeepAliveTimers(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x1800050d0`
- end: `0x1800053ec`
- name: `?AlignKeepAliveTimers@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `796`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005d10`
- `0x18000fe70`

## callees

- `0x180003800`
- `0x180004dd4`
- `0x1800050d0`
- `0x180005b30`
- `0x180013978`
- `0x1800181d8`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x180005266`
- `BrokerLib!BrBufferFree` at `0x180005266`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800051a7`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x1800051a7`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005152`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x180005152`

## pseudocode

```c
void __fastcall Broker::TimeBroker::AlignKeepAliveTimers(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  Broker::KeepAliveEvent *v4; // r15
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int i; // edi
  unsigned int BrokeredEventInfo2; // eax
  unsigned int v9; // ebx
  __int64 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r8
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rcx
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 *v19; // rbp
  _QWORD *v20; // rcx
  __int64 *v21; // rdx
  __int64 v22; // [rsp+0h] [rbp-F8h] BYREF
  __int64 *v23; // [rsp+30h] [rbp-C8h] BYREF
  struct Broker::KeepAliveEvent *v24[2]; // [rsp+38h] [rbp-C0h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-B0h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+60h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-88h]
  unsigned int v29; // [rsp+78h] [rbp-80h]
  void **v30; // [rsp+80h] [rbp-78h] BYREF
  __int128 v31; // [rsp+88h] [rbp-70h]
  int v32; // [rsp+98h] [rbp-60h]
  unsigned int v33; // [rsp+A0h] [rbp-58h]
  __int64 v34; // [rsp+A8h] [rbp-50h] BYREF
  _QWORD *v35; // [rsp+108h] [rbp+10h]
  unsigned int v36; // [rsp+110h] [rbp+18h] BYREF
  __int64 v37; // [rsp+118h] [rbp+20h] BYREF

  v2 = a2;
  v4 = (Broker::KeepAliveEvent *)*a2;
  if ( *(_BYTE *)(*a2 + 284LL) )
  {
    v15 = (std::_Ref_count_base *)a2[1];
  }
  else
  {
    if ( *((_DWORD *)v4 + 22) )
    {
      if ( *(_QWORD *)(a1 + 192) )
      {
        v36 = 0;
        v37 = 0;
        *(_OWORD *)v24 = 0;
        v5 = BrQueryBrokeredEvents2(*(_QWORD *)(a1 + 192), 0, 0, 0xFFFFFFFFLL, &v36, &v37);
        v6 = v5;
        if ( !v5 )
          goto LABEL_5;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v5);
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v27 = 0;
          v28 = 1;
          pExceptionObject = &Broker::Win32Error::`vftable';
          v29 = v6;
          throw (Broker::Win32Error *)&pExceptionObject;
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v34) )
          {
            v21 = &v22;
            v19 = v21;
            v20 = WPP_GLOBAL_Control;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)v20 + 25) >= 2u )
              WPP_SF_d(v20[2], 98, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, *((unsigned int *)v19 + 50));
            if ( v19[35] )
              BrBufferFree();
            v19[21] = (__int64)&std::exception::`vftable';
            o___std_exception_destroy_0(v19 + 22);
            v2 = v35;
            __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_1800053DE);
            goto LABEL_23;
          }
        }
LABEL_5:
        for ( i = 0; i < v36; ++i )
        {
          v23 = 0;
          BrokeredEventInfo2 = BrGetBrokeredEventInfo2(*(_QWORD *)(a1 + 192), *(_QWORD *)(v37 + 8LL * i), 0, 0, &v23);
          v9 = BrokeredEventInfo2;
          if ( BrokeredEventInfo2 )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                97,
                &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
                BrokeredEventInfo2);
            v31 = 0;
            v32 = 1;
            v30 = &Broker::Win32Error::`vftable';
            v33 = v9;
            throw (Broker::Win32Error *)&v30;
          }
          v10 = v23;
          v11 = v23[1];
          if ( v11 )
            _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
          v12 = *v10;
          v25[0] = v12;
          v13 = (volatile signed __int32 *)v10[1];
          v25[1] = v13;
          v14 = *v2;
          if ( *(_QWORD *)(v12 + 248) != *(_QWORD *)(*v2 + 248LL)
            && *(_DWORD *)(v12 + 72) == *(_DWORD *)(v14 + 72)
            && *(_DWORD *)(v12 + 88) )
          {
            v16 = *(_QWORD *)(v14 + 64);
            v17 = *(_QWORD *)(v12 + 64);
            v18 = v17;
            if ( v17 <= v16 )
              v18 = *(_QWORD *)(v14 + 64);
            if ( v17 >= v16 )
              v17 = *(_QWORD *)(v14 + 64);
            if ( v18 % v17 < *(_QWORD *)(v14 + 56) )
            {
              std::shared_ptr<Broker::TimeEvent>::operator=(v24, v25);
              if ( v13 )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
              break;
            }
          }
          if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        if ( v24[0] )
          Broker::KeepAliveEvent::Align(v4, v24[0], *(_QWORD *)(a1 + 200));
        if ( v37 )
          BrBufferFree();
        if ( v24[1] )
          std::_Ref_count_base::_Decref(v24[1]);
      }
LABEL_23:
      v15 = (std::_Ref_count_base *)v2[1];
      goto LABEL_24;
    }
    v15 = (std::_Ref_count_base *)a2[1];
  }
LABEL_24:
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
}

```

## disassembly

```asm
0x1800050d0  mov     r11, rsp
0x1800050d3  mov     [r11+8], rbx
0x1800050d7  mov     [r11+10h], rdx
0x1800050db  push    rsi
0x1800050dc  push    rdi
0x1800050dd  push    r12
0x1800050df  push    r14
0x1800050e1  push    r15
0x1800050e3  sub     rsp, 0D0h
0x1800050ea  mov     rsi, rdx
0x1800050ed  mov     r14, rcx
0x1800050f0  mov     r15, [rdx]
0x1800050f3  cmp     byte ptr [r15+11Ch], 0
0x1800050fb  jnz     loc_1800052A3
0x180005101  cmp     dword ptr [r15+58h], 0
0x180005106  jz      loc_1800052A9
0x18000510c  cmp     qword ptr [rcx+0C0h], 0
0x180005114  jz      loc_18000527D
0x18000511a  xor     r12d, r12d
0x18000511d  mov     [r11+18h], r12d
0x180005121  mov     [r11+20h], r12
0x180005125  xorps   xmm0, xmm0
0x180005128  movdqu  xmmword ptr [rsp+0F8h+var_C0], xmm0
0x18000512e  lea     rax, [r11+20h]
0x180005132  mov     [rsp+0F8h+var_D0], rax
0x180005137  lea     rax, [r11+18h]
0x18000513b  mov     [rsp+0F8h+var_D8], rax
0x180005140  mov     r9d, 0FFFFFFFFh
0x180005146  xor     r8d, r8d
0x180005149  xor     edx, edx
0x18000514b  mov     rcx, [rcx+0C0h]
0x180005152  call    cs:__imp_BrQueryBrokeredEvents2
0x180005158  mov     ebx, eax
0x18000515a  test    eax, eax
0x18000515c  jnz     loc_1800052C8
0x180005162  mov     edi, r12d
0x180005165  nop     word ptr [rax+rax+00000000h]
0x180005170  cmp     edi, [rsp+0F8h+arg_10]
0x180005177  jnb     loc_18000524B
0x18000517d  mov     [rsp+0F8h+var_C8], r12
0x180005182  mov     eax, edi
0x180005184  lea     rcx, [rsp+0F8h+var_C8]
0x180005189  mov     [rsp+0F8h+var_D8], rcx
0x18000518e  xor     r9d, r9d
0x180005191  xor     r8d, r8d
0x180005194  mov     rdx, [rsp+0F8h+arg_18]
0x18000519c  mov     rdx, [rdx+rax*8]
0x1800051a0  mov     rcx, [r14+0C0h]
0x1800051a7  call    cs:__imp_BrGetBrokeredEventInfo2
0x1800051ad  mov     ebx, eax
0x1800051af  test    eax, eax
0x1800051b1  jnz     loc_180005327
0x1800051b7  mov     rbx, [rsp+0F8h+var_C8]
0x1800051bc  mov     rax, [rbx+8]
0x1800051c0  test    rax, rax
0x1800051c3  jz      short loc_1800051C9
0x1800051c5  lock inc dword ptr [rax+8]
0x1800051c9  mov     r8, [rbx]
0x1800051cc  mov     [rsp+0F8h+var_B0], r8
0x1800051d1  mov     rbx, [rbx+8]
0x1800051d5  mov     [rsp+0F8h+var_A8], rbx
0x1800051da  mov     rcx, [rsi]
0x1800051dd  mov     rax, [rcx+0F8h]
0x1800051e4  cmp     [r8+0F8h], rax
0x1800051eb  jz      short loc_1800051FA
0x1800051ed  mov     eax, [rcx+48h]
0x1800051f0  cmp     [r8+48h], eax
0x1800051f4  jz      loc_180005395
0x1800051fa  test    rbx, rbx
0x1800051fd  jz      short loc_18000520E
0x1800051ff  mov     eax, 0FFFFFFFFh
0x180005204  lock xadd [rbx+8], eax
0x180005209  cmp     eax, 1
0x18000520c  jz      short loc_180005215
0x18000520e  inc     edi
0x180005210  jmp     loc_180005170
0x180005215  mov     rax, [rbx]
0x180005218  mov     rcx, rbx
0x18000521b  mov     rax, [rax]
0x18000521e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005223  mov     eax, 0FFFFFFFFh
0x180005228  lock xadd [rbx+0Ch], eax
0x18000522d  cmp     eax, 1
0x180005230  jnz     short loc_18000520E
0x180005232  mov     rax, [rbx]
0x180005235  mov     rcx, rbx
0x180005238  mov     rax, [rax+8]
0x18000523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005241  jmp     short loc_18000520E
0x180005243  mov     rcx, rbx; this
0x180005246  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000524b  mov     rdx, [rsp+0F8h+var_C0]; struct Broker::KeepAliveEvent *
0x180005250  test    rdx, rdx
0x180005253  jnz     loc_1800053CA
0x180005259  mov     rcx, [rsp+0F8h+arg_18]
0x180005261  test    rcx, rcx
0x180005264  jz      short loc_18000526D
0x180005266  call    cs:__imp_BrBufferFree
0x18000526c  nop
0x18000526d  mov     rcx, [rsp+0F8h+var_C0+8]; this
0x180005272  test    rcx, rcx
0x180005275  jz      short loc_18000527D
0x180005277  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000527c  nop
0x18000527d  mov     rcx, [rsi+8]; this
0x180005281  test    rcx, rcx
0x180005284  jz      short loc_18000528B
0x180005286  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000528b  mov     rbx, [rsp+0F8h+arg_0]
0x180005293  add     rsp, 0D0h
0x18000529a  pop     r15
0x18000529c  pop     r14
0x18000529e  pop     r12
0x1800052a0  pop     rdi
0x1800052a1  pop     rsi
0x1800052a2  retn
0x1800052a3  mov     rcx, [rdx+8]
0x1800052a7  jmp     short loc_180005281
0x1800052a9  mov     rcx, [rdx+8]
0x1800052ad  jmp     short loc_180005281
0x1800052af  lea     rdx, [rsp+0F8h+var_B0]
0x1800052b4  lea     rcx, [rsp+0F8h+var_C0]
0x1800052b9  call    ??4?$shared_ptr@VTimeEvent@Broker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Broker::TimeEvent>::operator=(std::shared_ptr<Broker::TimeEvent> const &)
0x1800052be  test    rbx, rbx
0x1800052c1  jz      short loc_18000524B
0x1800052c3  jmp     loc_180005243
0x1800052c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052cf  test    dword ptr [rcx+1Ch], 100h
0x1800052d6  jz      short loc_1800052F6
0x1800052d8  cmp     byte ptr [rcx+19h], 2
0x1800052dc  jb      short loc_1800052F6
0x1800052de  mov     edx, 60h ; '`'
0x1800052e3  mov     r9d, ebx
0x1800052e6  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800052ed  mov     rcx, [rcx+10h]
0x1800052f1  call    WPP_SF_d
0x1800052f6  xorps   xmm0, xmm0
0x1800052f9  movups  [rsp+0F8h+var_98], xmm0
0x1800052fe  mov     [rsp+0F8h+var_88], 1
0x180005306  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000530d  mov     [rsp+0F8h+pExceptionObject], rax
0x180005312  mov     [rsp+0F8h+var_80], ebx
0x180005316  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000531d  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180005322  call    _CxxThrowException_0
0x180005327  mov     rcx, cs:WPP_GLOBAL_Control
0x18000532e  test    dword ptr [rcx+1Ch], 100h
0x180005335  jz      short loc_180005355
0x180005337  cmp     byte ptr [rcx+19h], 2
0x18000533b  jb      short loc_180005355
0x18000533d  mov     edx, 61h ; 'a'
0x180005342  mov     r9d, ebx
0x180005345  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18000534c  mov     rcx, [rcx+10h]
0x180005350  call    WPP_SF_d
0x180005355  xorps   xmm0, xmm0
0x180005358  movups  [rsp+0F8h+var_70], xmm0
0x180005360  mov     [rsp+0F8h+var_60], 1
0x18000536b  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180005372  mov     [rsp+0F8h+var_78], rax
0x18000537a  mov     [rsp+0F8h+var_58], ebx
0x180005381  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180005388  lea     rcx, [rsp+0F8h+var_78]; pExceptionObject
0x180005390  call    _CxxThrowException_0
0x180005395  cmp     dword ptr [r8+58h], 0
0x18000539a  jz      loc_1800051FA
0x1800053a0  mov     rdx, [rcx+40h]
0x1800053a4  mov     r8, [r8+40h]
0x1800053a8  mov     rax, r8
0x1800053ab  cmp     r8, rdx
0x1800053ae  cmovle  rax, rdx
0x1800053b2  cmovge  r8, rdx
0x1800053b6  cqo
0x1800053b8  idiv    r8
0x1800053bb  cmp     rdx, [rcx+38h]
0x1800053bf  jge     loc_1800051FA
0x1800053c5  jmp     loc_1800052AF
0x1800053ca  mov     r8, [r14+0C8h]; __int64
0x1800053d1  mov     rcx, r15; this
0x1800053d4  call    ?Align@KeepAliveEvent@Broker@@QEAAXPEAV12@_J@Z; Broker::KeepAliveEvent::Align(Broker::KeepAliveEvent *,__int64)
0x1800053d9  jmp     loc_180005259
0x1800053de  mov     rsi, [rsp+0F8h+arg_8]
0x1800053e6  jmp     loc_18000527D
```
