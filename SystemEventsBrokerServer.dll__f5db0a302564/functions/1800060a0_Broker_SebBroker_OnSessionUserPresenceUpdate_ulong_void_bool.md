# Broker::SebBroker::OnSessionUserPresenceUpdate(ulong,void *,bool)

- ea: `0x1800060a0`
- end: `0x180006358`
- name: `?OnSessionUserPresenceUpdate@SebBroker@Broker@@QEAAXKPEAX_N@Z`
- size: `696`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this, unsigned int, void *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800020c0`

## callees

- `0x1800030e0`
- `0x1800060a0`
- `0x180006d90`
- `0x1800076a0`
- `0x18001cf50`
- `0x1800223e0`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800061b3`
- `ntdll!RtlEqualSid` at `0x1800061b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800060ed`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800060ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006297`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006297`
- `ntdll!RtlPublishWnfStateData` at `0x18000630b`
- `ntdll!RtlPublishWnfStateData` at `0x18000630b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060f3`

## pseudocode

```c
void __fastcall Broker::SebBroker::OnSessionUserPresenceUpdate(
        Broker::SebBroker *this,
        unsigned int a2,
        void *a3,
        unsigned __int8 a4)
{
  Broker::SebBroker *v4; // r13
  __int64 **v6; // rbx
  volatile signed __int32 *v7; // r14
  __int64 v8; // r15
  __int64 *v9; // rbx
  PSID v10; // r13
  __int64 v11; // rax
  __int64 **v12; // rcx
  __int64 *j; // rcx
  __int64 v14; // rcx
  __int64 v15; // rsi
  volatile signed __int32 *v16; // rdi
  std::_Ref_count_base *v17; // rcx
  __int64 v18; // rcx
  __int64 *i; // rax
  __int64 v21; // [rsp+38h] [rbp-1090h] BYREF
  PSID Sid2; // [rsp+40h] [rbp-1088h]
  Broker::SebBroker *v23; // [rsp+48h] [rbp-1080h]
  char *v24; // [rsp+50h] [rbp-1078h]
  std::_Ref_count_base *v25[2]; // [rsp+58h] [rbp-1070h]
  _DWORD v26[1024]; // [rsp+70h] [rbp-1058h] BYREF

  v23 = this;
  v4 = this;
  Sid2 = a3;
  v24 = (char *)this + 8;
  RtlAcquireSRWLockExclusive((char *)this + 8);
  GetCurrentThreadId();
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a2);
  v6 = (__int64 **)*((_QWORD *)v4 + 2);
  *(_OWORD *)v25 = 0;
  v7 = 0;
  v8 = 0;
  v9 = *v6;
  while ( v9 != *((__int64 **)v4 + 2) )
  {
    v10 = Sid2;
    v11 = **(_QWORD **)v9[5];
    v21 = v11;
    while ( v11 != *(_QWORD *)v9[5] )
    {
      if ( *(_QWORD *)(v11 + 40) )
      {
        v14 = *(_QWORD *)(v11 + 48);
        if ( v14 )
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v15 = *(_QWORD *)(v11 + 40);
        v16 = *(volatile signed __int32 **)(v11 + 48);
        if ( *(_DWORD *)(v15 + 40) == a2 && RtlEqualSid(*(PSID *)v15, v10) )
        {
          if ( v16 )
            _InterlockedIncrement(v16 + 2);
          v17 = (std::_Ref_count_base *)v7;
          v8 = v15;
          v7 = v16;
          if ( v17 )
            std::_Ref_count_base::_Decref(v17);
        }
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v21);
      v11 = v21;
    }
    v12 = (__int64 **)v9[2];
    v4 = v23;
    if ( *((_BYTE *)v12 + 25) )
    {
      for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v9 != (__int64 *)i[2] )
          break;
        v9 = i;
      }
      v9 = i;
    }
    else
    {
      v9 = (__int64 *)v9[2];
      for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v9 = j;
    }
  }
  if ( v8 )
  {
    *(_BYTE *)(v8 + 16) = a4;
    if ( *(_DWORD *)(v8 + 80) || *(_DWORD *)(v8 + 84) )
    {
      v18 = *(_QWORD *)(v8 + 80);
      v26[1] = a2;
      v26[0] = (2 * a4) | 1;
      RtlPublishWnfStateData(v18, 0, v26, 8, 0);
    }
  }
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a2);
  RtlReleaseSRWLockExclusive(v24);
}

```

## disassembly

```asm
0x1800060a0  push    rbx
0x1800060a2  push    rbp
0x1800060a3  push    rsi
0x1800060a4  push    rdi
0x1800060a5  push    r12
0x1800060a7  push    r13
0x1800060a9  push    r14
0x1800060ab  push    r15
0x1800060ad  mov     eax, 1088h
0x1800060b2  call    _alloca_probe
0x1800060b7  sub     rsp, rax
0x1800060ba  mov     rax, cs:__security_cookie
0x1800060c1  xor     rax, rsp
0x1800060c4  mov     [rsp+10C8h+var_58], rax
0x1800060cc  lea     rdi, [rcx+8]
0x1800060d0  mov     [rsp+10C8h+var_1080], rcx
0x1800060d5  mov     r13, rcx
0x1800060d8  mov     [rsp+10C8h+var_1098], r9b
0x1800060dd  mov     rcx, rdi
0x1800060e0  mov     [rsp+10C8h+Sid2], r8
0x1800060e5  mov     r12d, edx
0x1800060e8  mov     [rsp+10C8h+var_1078], rdi
0x1800060ed  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800060f3  call    cs:__imp_GetCurrentThreadId
0x1800060f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006100  test    byte ptr [rcx+1Ch], 10h
0x180006104  jz      short loc_180006110
0x180006106  cmp     byte ptr [rcx+19h], 4
0x18000610a  jnb     loc_18000633B
0x180006110  mov     rbx, [r13+10h]
0x180006114  xorps   xmm0, xmm0
0x180006117  movdqu  xmmword ptr [rsp+10C8h+var_1070], xmm0
0x18000611d  mov     r14, [rsp+10C8h+var_1070+8]
0x180006122  mov     ebp, 0FFFFFFFFh
0x180006127  mov     r15, [rsp+10C8h+var_1070]
0x18000612c  mov     rbx, [rbx]
0x18000612f  nop
0x180006130  cmp     rbx, [r13+10h]
0x180006134  jz      loc_180006227
0x18000613a  mov     rax, [rbx+28h]
0x18000613e  mov     r13, [rsp+10C8h+Sid2]
0x180006143  mov     rax, [rax]
0x180006146  mov     rax, [rax]
0x180006149  mov     [rsp+10C8h+var_1090], rax
0x18000614e  mov     rcx, [rbx+28h]
0x180006152  cmp     rax, [rcx]
0x180006155  jnz     short loc_180006187
0x180006157  mov     rcx, [rbx+10h]
0x18000615b  mov     r13, [rsp+10C8h+var_1080]
0x180006160  cmp     byte ptr [rcx+19h], 0
0x180006164  jnz     loc_180006316
0x18000616a  mov     rbx, rcx
0x18000616d  mov     rcx, [rcx]
0x180006170  cmp     byte ptr [rcx+19h], 0
0x180006174  jnz     short loc_180006130
0x180006176  mov     rax, [rcx]
0x180006179  mov     rbx, rcx
0x18000617c  mov     rcx, rax
0x18000617f  cmp     byte ptr [rax+19h], 0
0x180006183  jz      short loc_180006176
0x180006185  jmp     short loc_180006130
0x180006187  cmp     qword ptr [rax+28h], 0
0x18000618c  jz      loc_180006213
0x180006192  mov     rcx, [rax+30h]
0x180006196  test    rcx, rcx
0x180006199  jz      short loc_18000619F
0x18000619b  lock inc dword ptr [rcx+8]
0x18000619f  mov     rsi, [rax+28h]
0x1800061a3  mov     rdi, [rax+30h]
0x1800061a7  cmp     [rsi+28h], r12d
0x1800061ab  jnz     short loc_1800061D9
0x1800061ad  mov     rcx, [rsi]; Sid1
0x1800061b0  mov     rdx, r13; Sid2
0x1800061b3  call    cs:__imp_RtlEqualSid
0x1800061b9  test    al, al
0x1800061bb  jz      short loc_1800061D9
0x1800061bd  test    rdi, rdi
0x1800061c0  jz      short loc_1800061C6
0x1800061c2  lock inc dword ptr [rdi+8]
0x1800061c6  mov     rcx, r14; this
0x1800061c9  mov     r15, rsi
0x1800061cc  mov     r14, rdi
0x1800061cf  test    rcx, rcx
0x1800061d2  jz      short loc_1800061D9
0x1800061d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800061d9  test    rdi, rdi
0x1800061dc  jz      short loc_180006213
0x1800061de  mov     eax, ebp
0x1800061e0  lock xadd [rdi+8], eax
0x1800061e5  cmp     eax, 1
0x1800061e8  jnz     short loc_180006213
0x1800061ea  mov     rax, [rdi]
0x1800061ed  mov     rcx, rdi
0x1800061f0  mov     rax, [rax]
0x1800061f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f8  mov     eax, ebp
0x1800061fa  lock xadd [rdi+0Ch], eax
0x1800061ff  cmp     eax, 1
0x180006202  jnz     short loc_180006213
0x180006204  mov     rax, [rdi]
0x180006207  mov     rcx, rdi
0x18000620a  mov     rax, [rax+8]
0x18000620e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006213  lea     rcx, [rsp+10C8h+var_1090]
0x180006218  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x18000621d  mov     rax, [rsp+10C8h+var_1090]
0x180006222  jmp     loc_18000614E
0x180006227  test    r15, r15
0x18000622a  jz      short loc_18000624B
0x18000622c  movzx   esi, [rsp+10C8h+var_1098]
0x180006231  mov     [r15+10h], sil
0x180006235  cmp     dword ptr [r15+50h], 0
0x18000623a  jnz     loc_1800062E1
0x180006240  cmp     dword ptr [r15+54h], 0
0x180006245  jnz     loc_1800062E1
0x18000624b  test    r14, r14
0x18000624e  jz      short loc_180006285
0x180006250  mov     eax, ebp
0x180006252  lock xadd [r14+8], eax
0x180006258  cmp     eax, 1
0x18000625b  jnz     short loc_180006285
0x18000625d  mov     rax, [r14]
0x180006260  mov     rcx, r14
0x180006263  mov     rax, [rax]
0x180006266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000626b  lock xadd [r14+0Ch], ebp
0x180006271  cmp     ebp, 1
0x180006274  jnz     short loc_180006285
0x180006276  mov     rax, [r14]
0x180006279  mov     rcx, r14
0x18000627c  mov     rax, [rax+8]
0x180006280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006285  mov     rcx, cs:WPP_GLOBAL_Control
0x18000628c  test    byte ptr [rcx+1Ch], 10h
0x180006290  jnz     short loc_1800062C1
0x180006292  mov     rcx, [rsp+10C8h+var_1078]
0x180006297  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000629d  mov     rcx, [rsp+10C8h+var_58]
0x1800062a5  xor     rcx, rsp; StackCookie
0x1800062a8  call    __security_check_cookie
0x1800062ad  add     rsp, 1088h
0x1800062b4  pop     r15
0x1800062b6  pop     r14
0x1800062b8  pop     r13
0x1800062ba  pop     r12
0x1800062bc  pop     rdi
0x1800062bd  pop     rsi
0x1800062be  pop     rbp
0x1800062bf  pop     rbx
0x1800062c0  retn
0x1800062c1  cmp     byte ptr [rcx+19h], 4
0x1800062c5  jb      short loc_180006292
0x1800062c7  mov     rcx, [rcx+10h]
0x1800062cb  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800062d2  mov     edx, 21h ; '!'
0x1800062d7  mov     r9d, r12d
0x1800062da  call    WPP_SF_d
0x1800062df  jmp     short loc_180006292
0x1800062e1  mov     rcx, [r15+50h]
0x1800062e5  lea     r8, [rsp+10C8h+var_1058]
0x1800062ea  mov     eax, esi
0x1800062ec  mov     [rsp+10C8h+var_1054], r12d
0x1800062f1  add     eax, eax
0x1800062f3  mov     [rsp+10C8h+var_10A8], 0
0x1800062fc  or      eax, 1
0x1800062ff  mov     r9d, 8
0x180006305  xor     edx, edx
0x180006307  mov     [rsp+10C8h+var_1058], eax
0x18000630b  call    cs:__imp_RtlPublishWnfStateData
0x180006311  jmp     loc_18000624B
0x180006316  mov     rax, [rbx+8]
0x18000631a  cmp     byte ptr [rax+19h], 0
0x18000631e  jnz     short loc_180006333
0x180006320  cmp     rbx, [rax+10h]
0x180006324  jnz     short loc_180006333
0x180006326  mov     rbx, rax
0x180006329  mov     rax, [rax+8]
0x18000632d  cmp     byte ptr [rax+19h], 0
0x180006331  jz      short loc_180006320
0x180006333  mov     rbx, rax
0x180006336  jmp     loc_180006130
0x18000633b  mov     rcx, [rcx+10h]
0x18000633f  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180006346  mov     edx, 20h ; ' '
0x18000634b  mov     r9d, r12d
0x18000634e  call    WPP_SF_d
0x180006353  jmp     loc_180006110
```
