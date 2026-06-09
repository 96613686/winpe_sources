# CBroker::SebBroker::CreateEventW(Broker::ApplicationIdentity const &,_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *,ulong)

- ea: `0x180006e00`
- end: `0x18000768f`
- name: `?CreateEventW@SebBroker@CBroker@@QEAA?AU_GUID@@AEBUApplicationIdentity@Broker@@AEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@K@Z`
- size: `2191`
- prototype: `struct _GUID *__fastcall(CBroker::SebBroker *this, struct _GUID *__return_ptr retstr, const struct Broker::ApplicationIdentity *, const struct _CSebiSystemEventCreationParameter *, const struct CBroker::_CustomData *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009740`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x180006e00`
- `0x1800076a0`
- `0x180007700`
- `0x180007880`
- `0x180007c50`
- `0x180008c00`
- `0x1800115f8`
- `0x180011648`
- `0x180013820`
- `0x180013920`
- `0x180015bc0`
- `0x180016040`
- `0x180017120`
- `0x18001a3c0`
- `0x18001ad04`
- `0x18001cf74`
- `0x18001d9ac`
- `0x180022434`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007687`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007687`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006e63`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006e63`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000722b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000722b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e69`

## pseudocode

```c
struct _GUID *__fastcall CBroker::SebBroker::CreateEventW(
        CBroker::SebBroker *this,
        struct _GUID *__return_ptr retstr,
        const struct Broker::ApplicationIdentity *a3,
        const struct _CSebiSystemEventCreationParameter *a4,
        const struct CBroker::_CustomData *a5,
        unsigned int a6)
{
  struct _RTL_SRWLOCK **ApplicationState; // rax
  struct _RTL_SRWLOCK *v10; // rdi
  volatile signed __int32 *v11; // r12
  volatile signed __int32 *v12; // rbx
  __int64 v13; // r15
  __int64 v14; // rbx
  __int64 v15; // r15
  std::_Ref_count_base *v16; // r13
  void *v17; // rdi
  volatile signed __int32 *v18; // rbx
  std::_Ref_count_base *v19; // rax
  __int128 v20; // xmm6
  std::_Ref_count_base *v21; // rdx
  __int64 *v22; // rbx
  int v23; // r15d
  _QWORD *v24; // rsi
  __int64 v25; // rdx
  int v26; // r8d
  std::_Ref_count_base *v27; // rcx
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rbx
  std::_Ref_count_base *v31; // rbx
  void *v32; // r9
  std::_Ref_count_base *v33; // r11
  _QWORD *v34; // r10
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 *v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // rax
  struct _RTL_SRWLOCK *v41; // rax
  __int64 *Event; // rax
  CBroker::SebEvent *v43; // rdi
  _DWORD *Ptr; // rdx
  unsigned int v45; // r8d
  unsigned int v46; // ecx
  std::_Ref_count_base *v47; // [rsp+48h] [rbp-130h] BYREF
  std::_Ref_count_base *v48; // [rsp+50h] [rbp-128h]
  std::_Ref_count_base *v49[2]; // [rsp+58h] [rbp-120h] BYREF
  struct _GUID *v50; // [rsp+68h] [rbp-110h]
  std::_Ref_count_base *v51; // [rsp+70h] [rbp-108h]
  __int64 v52; // [rsp+78h] [rbp-100h]
  CBroker::SebEvent *v53[2]; // [rsp+80h] [rbp-F8h] BYREF
  const struct _CSebiSystemEventCreationParameter *v54; // [rsp+90h] [rbp-E8h]
  const struct _CSebiSystemEventCreationParameter *v55; // [rsp+A0h] [rbp-D8h]
  char *v56; // [rsp+B0h] [rbp-C8h]
  char v57; // [rsp+B8h] [rbp-C0h]
  DWORD CurrentThreadId; // [rsp+BCh] [rbp-BCh]
  __int128 v59; // [rsp+C0h] [rbp-B8h]
  __int128 Buf2; // [rsp+D0h] [rbp-A8h] BYREF
  std::_Ref_count_base *v61; // [rsp+E0h] [rbp-98h]
  std::_Ref_count_base *v62; // [rsp+E8h] [rbp-90h]
  std::_Ref_count_base **v63; // [rsp+F0h] [rbp-88h]
  void **pExceptionObject; // [rsp+F8h] [rbp-80h] BYREF
  __int128 v65; // [rsp+100h] [rbp-78h]
  int v66; // [rsp+110h] [rbp-68h]

  v54 = a4;
  v48 = a3;
  v50 = retstr;
  v55 = a4;
  *retstr = 0;
  v56 = (char *)this + 8;
  RtlAcquireSRWLockExclusive((char *)this + 8);
  CurrentThreadId = GetCurrentThreadId();
  v57 = 1;
  v59 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids,
      *((unsigned int *)a4 + 2));
  CBroker::SebBroker::ValidateCreationParameters(this, a4, a5);
  *(_OWORD *)v53 = 0;
  ApplicationState = (struct _RTL_SRWLOCK **)Broker::ApplicationStateTable::CreateApplicationState(
                                               *((_QWORD **)this + 4),
                                               v49,
                                               (__int64)a3);
  v10 = *ApplicationState;
  v11 = (volatile signed __int32 *)ApplicationState[1];
  *ApplicationState = 0;
  ApplicationState[1] = 0;
  *(_QWORD *)&v59 = v10;
  *((_QWORD *)&v59 + 1) = v11;
  v12 = (volatile signed __int32 *)v49[1];
  if ( v49[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = (unsigned int)(*((_DWORD *)a4 + 2) - 4096);
  v14 = 4 * v13;
  if ( *((_DWORD *)v10[11].Ptr + v13) != -1 )
  {
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v49, v10 + 18, 1);
    Ptr = v10[14].Ptr;
    v45 = Ptr[v13];
    v46 = v45 + 1;
    if ( v45 + 1 < v45 || v46 > *(_DWORD *)((char *)v10[11].Ptr + v14) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v41 = v10 + 7;
        if ( v10[10].Ptr > (PVOID)7 )
          v41 = (struct _RTL_SRWLOCK *)v41->Ptr;
        WPP_SF__sid_Sddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (__int64)v41,
          v13,
          v45,
          *(_DWORD *)((char *)v10[11].Ptr + v14));
      }
      v65 = 0;
      v66 = 2;
      pExceptionObject = &Broker::ApplicationLimitsExceeded::`vftable';
      throw (Broker::ApplicationLimitsExceeded *)&pExceptionObject;
    }
    Ptr[v13] = v46;
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v49);
  }
  v15 = (__int64)v54;
  if ( (byte_180035F64[40 * *((int *)v54 + 2) - 163840] & 1) == 0 )
  {
LABEL_10:
    CBroker::SebBroker::ConstructEventObject((__int64)this, (__int64 *)&v47, v48, v15, (__int64)a5, 0, 0);
    v16 = v47;
    v47 = 0;
    v51 = v16;
    v17 = operator new(0x18u);
    *((_DWORD *)v17 + 2) = 1;
    *((_DWORD *)v17 + 3) = 1;
    *(_QWORD *)v17 = &std::_Ref_count<Broker::SebEvent>::`vftable';
    *((_QWORD *)v17 + 2) = v16;
    if ( v47 )
      (**(void (__fastcall ***)(std::_Ref_count_base *, __int64))v47)(v47, 1);
    v53[0] = v16;
    v18 = (volatile signed __int32 *)v53[1];
    v53[1] = (CBroker::SebEvent *)v17;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    *v50 = *(struct _GUID *)((char *)v16 + 120);
    v19 = (CBroker::SebBroker *)((char *)this + 16);
    v48 = (CBroker::SebBroker *)((char *)this + 16);
    *(_OWORD *)v49 = 0;
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
    v49[0] = v16;
    v49[1] = (std::_Ref_count_base *)v17;
    v63 = v49;
    v20 = *(_OWORD *)((char *)v16 + 120);
    Buf2 = v20;
    if ( v17 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
      v16 = v49[0];
    }
    v61 = v16;
    v47 = v49[1];
    v62 = v49[1];
    v21 = *(std::_Ref_count_base **)v19;
    v51 = v21;
    v22 = (__int64 *)*((_QWORD *)v21 + 1);
    v23 = 0;
    if ( *((_BYTE *)v22 + 25) )
    {
      v24 = (_QWORD *)*((_QWORD *)v21 + 1);
    }
    else
    {
      do
      {
        v24 = v22;
        if ( memcmp_0(v22 + 4, &Buf2, 0x10u) >= 0 )
        {
          v23 = 1;
          v51 = (std::_Ref_count_base *)v22;
          v22 = (__int64 *)*v22;
        }
        else
        {
          v23 = 0;
          v22 = (__int64 *)v22[2];
        }
      }
      while ( !*((_BYTE *)v22 + 25) );
      v21 = v51;
      v19 = v48;
    }
    if ( !*((_BYTE *)v21 + 25) )
    {
      if ( memcmp_0(&Buf2, (char *)v21 + 32, 0x10u) >= 0 )
      {
        v27 = v47;
LABEL_28:
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        v28 = (volatile signed __int32 *)v49[1];
        if ( v49[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
            if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          }
        }
        if ( v17 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v17)(v17);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
        v15 = (__int64)v54;
        v29 = (__int64)v50;
        goto LABEL_39;
      }
      v19 = v48;
    }
    if ( *((_QWORD *)v19 + 1) == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v31 = *(std::_Ref_count_base **)v19;
    v51 = v19;
    v52 = 0;
    v32 = operator new(0x40u);
    *((_OWORD *)v32 + 2) = v20;
    *((_QWORD *)v32 + 6) = v16;
    *((_QWORD *)v32 + 7) = v47;
    v27 = 0;
    v47 = 0;
    *(_QWORD *)v32 = v31;
    *((_QWORD *)v32 + 1) = v31;
    *((_QWORD *)v32 + 2) = v31;
    *((_WORD *)v32 + 12) = 0;
    v33 = v48;
    ++*((_QWORD *)v48 + 1);
    v34 = *(_QWORD **)v33;
    *((_QWORD *)v32 + 1) = v24;
    if ( v24 == v34 )
    {
      *v34 = v32;
      v34[1] = v32;
      v34[2] = v32;
      *((_BYTE *)v32 + 24) = 1;
    }
    else
    {
      if ( v23 )
      {
        *v24 = v32;
        if ( v24 == (_QWORD *)*v34 )
          *v34 = v32;
      }
      else
      {
        v24[2] = v32;
        if ( v24 == (_QWORD *)v34[2] )
          v34[2] = v32;
      }
      if ( !*(_BYTE *)(*((_QWORD *)v32 + 1) + 24LL) )
      {
        do
        {
          v25 = *((_QWORD *)v32 + 1);
          v35 = *(__int64 **)(v25 + 8);
          v36 = *v35;
          if ( v25 == *v35 )
          {
            v37 = v35[2];
            if ( *(_BYTE *)(v37 + 24) )
            {
              if ( v32 == *(void **)(v25 + 16) )
                std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(
                  (__int64)v33,
                  v25);
              *(_BYTE *)(*((_QWORD *)v32 + 1) + 24LL) = 1;
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v32 + 1) + 8LL) + 24LL) = 0;
              v38 = *(__int64 **)(*((_QWORD *)v32 + 1) + 8LL);
              v25 = *v38;
              *v38 = *(_QWORD *)(*v38 + 16);
              v39 = *(_QWORD *)(v25 + 16);
              if ( !*(_BYTE *)(v39 + 25) )
                *(_QWORD *)(v39 + 8) = v38;
              *(_QWORD *)(v25 + 8) = v38[1];
              if ( v38 == *(__int64 **)(*(_QWORD *)v33 + 8LL) )
              {
                *(_QWORD *)(*(_QWORD *)v33 + 8LL) = v25;
                *(_QWORD *)(v25 + 16) = v38;
                v38[1] = v25;
              }
              else
              {
                v40 = (__int64 *)v38[1];
                if ( v38 == (__int64 *)v40[2] )
                  v40[2] = v25;
                else
                  *v40 = v25;
                *(_QWORD *)(v25 + 16) = v38;
                v38[1] = v25;
              }
            }
            else
            {
              *(_BYTE *)(v25 + 24) = 1;
              *(_BYTE *)(v37 + 24) = 1;
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v32 + 1) + 8LL) + 24LL) = 0;
              v32 = *(void **)(*((_QWORD *)v32 + 1) + 8LL);
            }
          }
          else if ( *(_BYTE *)(v36 + 24) )
          {
            if ( v32 == *(void **)v25 )
              std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
                (__int64)v33,
                (_QWORD *)v25);
            *(_BYTE *)(*((_QWORD *)v32 + 1) + 24LL) = 1;
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v32 + 1) + 8LL) + 24LL) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(
              (__int64)v33,
              *(_QWORD *)(*((_QWORD *)v32 + 1) + 8LL));
          }
          else
          {
            *(_BYTE *)(v25 + 24) = 1;
            *(_BYTE *)(v36 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v32 + 1) + 8LL) + 24LL) = 0;
            v32 = *(void **)(*((_QWORD *)v32 + 1) + 8LL);
          }
        }
        while ( !*(_BYTE *)(*((_QWORD *)v32 + 1) + 24LL) );
        v27 = v47;
      }
      *(_BYTE *)(v34[1] + 24LL) = 1;
    }
    goto LABEL_28;
  }
  Event = (__int64 *)CBroker::SebBroker::FindEvent(this, v49, v48);
  std::shared_ptr<CBroker::SebBroker>::operator=(v53, Event);
  if ( v49[1] )
    std::_Ref_count_base::_Decref(v49[1]);
  v43 = v53[0];
  if ( !v53[0] )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    goto LABEL_10;
  }
  v29 = (__int64)v50;
  *v50 = *(struct _GUID *)((char *)v53[0] + 120);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, v29);
  CBroker::SebEvent::IncRefCount(v43);
  if ( v53[1] )
    std::_Ref_count_base::_Decref(v53[1]);
LABEL_39:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_L_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, *(_DWORD *)(v15 + 8), v29);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  RtlReleaseSRWLockExclusive(v56);
  return (struct _GUID *)v29;
}

```

## disassembly

```asm
0x180006e00  push    rbx
0x180006e02  push    rsi
0x180006e03  push    rdi
0x180006e04  push    r12
0x180006e06  push    r13
0x180006e08  push    r14
0x180006e0a  push    r15
0x180006e0c  sub     rsp, 140h
0x180006e13  movaps  [rsp+178h+var_48], xmm6
0x180006e1b  mov     r15, r9
0x180006e1e  mov     [rsp+178h+var_E8], r9
0x180006e26  mov     rbx, r8
0x180006e29  mov     [rsp+178h+var_128], rbx
0x180006e2e  mov     [rsp+178h+var_110], rdx
0x180006e33  mov     rsi, rcx
0x180006e36  mov     [rsp+178h+var_D8], r9
0x180006e3e  mov     r13, [rsp+178h+arg_20]
0x180006e46  xor     r14d, r14d
0x180006e49  mov     [rsp+178h+var_138], r14b
0x180006e4e  xorps   xmm0, xmm0
0x180006e51  movups  xmmword ptr [rdx], xmm0
0x180006e54  lea     rax, [rcx+8]
0x180006e58  mov     [rsp+178h+var_C8], rax
0x180006e60  mov     rcx, rax
0x180006e63  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180006e69  call    cs:__imp_GetCurrentThreadId
0x180006e6f  mov     [rsp+178h+var_BC], eax
0x180006e76  mov     [rsp+178h+var_C0], 1
0x180006e7e  xorps   xmm0, xmm0
0x180006e81  movdqu  [rsp+178h+var_B8], xmm0
0x180006e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e91  test    byte ptr [rcx+1Ch], 1
0x180006e95  jz      short loc_180006EA1
0x180006e97  cmp     byte ptr [rcx+19h], 4
0x180006e9b  jnb     loc_18000740B
0x180006ea1  mov     r8, r13; struct CBroker::_CustomData *
0x180006ea4  mov     rdx, r15; struct _CSebiSystemEventCreationParameter *
0x180006ea7  mov     rcx, rsi; this
0x180006eaa  call    ?ValidateCreationParameters@SebBroker@CBroker@@AEAAXAEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@@Z; CBroker::SebBroker::ValidateCreationParameters(_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *)
0x180006eaf  nop
0x180006eb0  xorps   xmm0, xmm0
0x180006eb3  movdqu  xmmword ptr [rsp+178h+var_F8], xmm0
0x180006ebc  mov     r8, rbx
0x180006ebf  lea     rdx, [rsp+178h+var_120]
0x180006ec4  mov     rcx, [rsi+20h]
0x180006ec8  call    ?CreateApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::ApplicationStateTable::CreateApplicationState(Broker::ApplicationIdentity const &)
0x180006ecd  mov     rdi, [rax]
0x180006ed0  mov     r12, [rax+8]
0x180006ed4  mov     [rax], r14
0x180006ed7  mov     [rax+8], r14
0x180006edb  mov     qword ptr [rsp+178h+var_B8], rdi
0x180006ee3  mov     qword ptr [rsp+178h+var_B8+8], r12
0x180006eeb  mov     rbx, [rsp+178h+var_120+8]
0x180006ef0  mov     r14d, 0FFFFFFFFh
0x180006ef6  test    rbx, rbx
0x180006ef9  jz      short loc_180006F32
0x180006efb  mov     eax, r14d
0x180006efe  lock xadd [rbx+8], eax
0x180006f03  cmp     eax, 1
0x180006f06  jnz     short loc_180006F32
0x180006f08  mov     rax, [rbx]
0x180006f0b  mov     rcx, rbx
0x180006f0e  mov     rax, [rax]
0x180006f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f16  mov     eax, r14d
0x180006f19  lock xadd [rbx+0Ch], eax
0x180006f1e  cmp     eax, 1
0x180006f21  jnz     short loc_180006F32
0x180006f23  mov     rax, [rbx]
0x180006f26  mov     rcx, rbx
0x180006f29  mov     rax, [rax+8]
0x180006f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f32  mov     r15d, [r15+8]
0x180006f36  add     r15d, 0FFFFF000h
0x180006f3d  lea     rbx, ds:0[r15*4]
0x180006f45  mov     rax, [rdi+58h]
0x180006f49  cmp     dword ptr [rbx+rax], 0FFFFFFFFh
0x180006f4d  jnz     loc_1800075BD
0x180006f53  mov     [rsp+178h+var_138], 1
0x180006f58  mov     r15, [rsp+178h+var_E8]
0x180006f60  movsxd  r9, dword ptr [r15+8]
0x180006f64  lea     rax, [r9-1000h]
0x180006f6b  lea     rax, [rax+rax*4]
0x180006f6f  lea     rcx, byte_180035F64
0x180006f76  mov     rbx, [rsp+178h+var_128]
0x180006f7b  test    byte ptr [rcx+rax*8], 1
0x180006f7f  jnz     loc_180007527
0x180006f85  xor     edi, edi
0x180006f87  mov     qword ptr [rsp+178h+var_148], rdi
0x180006f8c  mov     qword ptr [rsp+178h+var_150], rdi
0x180006f91  mov     [rsp+178h+var_158], r13
0x180006f96  mov     r9, r15
0x180006f99  mov     r8, rbx
0x180006f9c  lea     rdx, [rsp+178h+var_130]
0x180006fa1  mov     rcx, rsi
0x180006fa4  call    ?ConstructEventObject@SebBroker@CBroker@@AEAA?AV?$unique_ptr@VSebEvent@CBroker@@U?$default_delete@VSebEvent@CBroker@@@std@@@std@@AEBUApplicationIdentity@Broker@@AEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; CBroker::SebBroker::ConstructEventObject(Broker::ApplicationIdentity const &,_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *,_BROKER *,_BROKERED_EVENT *)
0x180006fa9  nop
0x180006faa  mov     r13, [rsp+178h+var_130]
0x180006faf  mov     [rsp+178h+var_130], rdi
0x180006fb4  mov     [rsp+178h+var_108], r13
0x180006fb9  mov     ecx, 18h; Size
0x180006fbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fc3  mov     rdi, rax
0x180006fc6  mov     dword ptr [rax+8], 1
0x180006fcd  mov     dword ptr [rax+0Ch], 1
0x180006fd4  lea     rax, ??_7?$_Ref_count@VSebEvent@Broker@@@std@@6B@; const std::_Ref_count<Broker::SebEvent>::`vftable'
0x180006fdb  mov     [rdi], rax
0x180006fde  mov     [rdi+10h], r13
0x180006fe2  mov     rcx, [rsp+178h+var_130]
0x180006fe7  test    rcx, rcx
0x180006fea  jz      short loc_180006FFC
0x180006fec  mov     rax, [rcx]
0x180006fef  mov     edx, 1
0x180006ff4  mov     rax, [rax]
0x180006ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffc  mov     [rsp+178h+var_F8], r13
0x180007004  mov     rbx, [rsp+178h+var_F8+8]
0x18000700c  mov     [rsp+178h+var_F8+8], rdi
0x180007014  test    rbx, rbx
0x180007017  jz      short loc_180007045
0x180007019  mov     eax, r14d
0x18000701c  lock xadd [rbx+8], eax
0x180007021  cmp     eax, 1
0x180007024  jnz     short loc_180007045
0x180007026  mov     rax, [rbx]
0x180007029  mov     rcx, rbx
0x18000702c  mov     rax, [rax]
0x18000702f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007034  mov     eax, r14d
0x180007037  lock xadd [rbx+0Ch], eax
0x18000703c  cmp     eax, 1
0x18000703f  jz      loc_180007662
0x180007045  movups  xmm0, xmmword ptr [r13+78h]
0x18000704a  mov     rax, [rsp+178h+var_110]
0x18000704f  movups  xmmword ptr [rax], xmm0
0x180007052  lea     rax, [rsi+10h]
0x180007056  mov     [rsp+178h+var_128], rax
0x18000705b  xorps   xmm0, xmm0
0x18000705e  movdqu  xmmword ptr [rsp+178h+var_120], xmm0
0x180007064  test    rdi, rdi
0x180007067  jz      short loc_18000706D
0x180007069  lock inc dword ptr [rdi+8]
0x18000706d  mov     [rsp+178h+var_120], r13
0x180007072  mov     [rsp+178h+var_120+8], rdi
0x180007077  lea     rcx, [rsp+178h+var_120]
0x18000707c  mov     [rsp+178h+var_88], rcx
0x180007084  movups  xmm6, xmmword ptr [r13+78h]
0x180007089  movups  [rsp+178h+Buf2], xmm6
0x180007091  test    rdi, rdi
0x180007094  jz      short loc_18000709F
0x180007096  lock inc dword ptr [rdi+8]
0x18000709a  mov     r13, [rsp+178h+var_120]
0x18000709f  mov     [rsp+178h+var_98], r13
0x1800070a7  mov     rcx, [rsp+178h+var_120+8]
0x1800070ac  mov     [rsp+178h+var_130], rcx
0x1800070b1  mov     [rsp+178h+var_90], rcx
0x1800070b9  mov     rdx, [rax]
0x1800070bc  mov     [rsp+178h+var_108], rdx
0x1800070c1  mov     rbx, [rdx+8]
0x1800070c5  xor     r15d, r15d
0x1800070c8  xor     ecx, ecx
0x1800070ca  cmp     [rbx+19h], cl
0x1800070cd  jnz     loc_180007403
0x1800070d3  mov     rsi, rbx
0x1800070d6  lea     rcx, [rbx+20h]; Buf1
0x1800070da  mov     r8d, 10h; Size
0x1800070e0  lea     rdx, [rsp+178h+Buf2]; Buf2
0x1800070e8  call    memcmp_0
0x1800070ed  test    eax, eax
0x1800070ef  jns     loc_18000724F
0x1800070f5  xor     r15d, r15d
0x1800070f8  mov     rbx, [rbx+10h]
0x1800070fc  cmp     byte ptr [rbx+19h], 0
0x180007100  jz      short loc_1800070D3
0x180007102  mov     rdx, [rsp+178h+var_108]
0x180007107  mov     rax, [rsp+178h+var_128]
0x18000710c  cmp     byte ptr [rdx+19h], 0
0x180007110  jnz     loc_180007262
0x180007116  add     rdx, 20h ; ' '; Buf2
0x18000711a  mov     r8d, 10h; Size
0x180007120  lea     rcx, [rsp+178h+Buf2]; Buf1
0x180007128  call    memcmp_0
0x18000712d  test    eax, eax
0x18000712f  js      loc_180007676
0x180007135  mov     rcx, [rsp+178h+var_130]; this
0x18000713a  test    rcx, rcx
0x18000713d  jz      short loc_180007145
0x18000713f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007144  nop
0x180007145  mov     rbx, [rsp+178h+var_120+8]
0x18000714a  test    rbx, rbx
0x18000714d  jz      short loc_180007187
0x18000714f  mov     eax, r14d
0x180007152  lock xadd [rbx+8], eax
0x180007157  cmp     eax, 1
0x18000715a  jnz     short loc_180007187
0x18000715c  mov     rax, [rbx]
0x18000715f  mov     rcx, rbx
0x180007162  mov     rax, [rax]
0x180007165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000716a  mov     eax, r14d
0x18000716d  lock xadd [rbx+0Ch], eax
0x180007172  cmp     eax, 1
0x180007175  jnz     short loc_180007187
0x180007177  mov     rax, [rbx]
0x18000717a  mov     rcx, rbx
0x18000717d  mov     rax, [rax+8]
0x180007181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007186  nop
0x180007187  test    rdi, rdi
0x18000718a  jz      short loc_1800071C4
0x18000718c  mov     eax, r14d
0x18000718f  lock xadd [rdi+8], eax
0x180007194  cmp     eax, 1
0x180007197  jnz     short loc_1800071C4
0x180007199  mov     rax, [rdi]
0x18000719c  mov     rcx, rdi
0x18000719f  mov     rax, [rax]
0x1800071a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a7  mov     eax, r14d
0x1800071aa  lock xadd [rdi+0Ch], eax
0x1800071af  cmp     eax, 1
0x1800071b2  jnz     short loc_1800071C4
0x1800071b4  mov     rax, [rdi]
0x1800071b7  mov     rcx, rdi
0x1800071ba  mov     rax, [rax+8]
0x1800071be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c3  nop
0x1800071c4  mov     r15, [rsp+178h+var_E8]
0x1800071cc  mov     rbx, [rsp+178h+var_110]
0x1800071d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071d8  test    byte ptr [rcx+1Ch], 1
0x1800071dc  jnz     loc_180007388
0x1800071e2  test    r12, r12
0x1800071e5  jz      short loc_180007223
0x1800071e7  mov     eax, r14d
0x1800071ea  lock xadd [r12+8], eax
0x1800071f1  cmp     eax, 1
0x1800071f4  jnz     short loc_180007223
0x1800071f6  mov     rax, [r12]
0x1800071fa  mov     rcx, r12
0x1800071fd  mov     rax, [rax]
0x180007200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007205  lock xadd [r12+0Ch], r14d
0x18000720c  cmp     r14d, 1
0x180007210  jnz     short loc_180007223
0x180007212  mov     rdx, [r12]
0x180007216  mov     rcx, r12
0x180007219  mov     rax, [rdx+8]
0x18000721d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007222  nop
0x180007223  mov     rcx, [rsp+178h+var_C8]
0x18000722b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007231  mov     rax, rbx
0x180007234  movaps  xmm6, [rsp+178h+var_48]
0x18000723c  add     rsp, 140h
0x180007243  pop     r15
0x180007245  pop     r14
0x180007247  pop     r13
0x180007249  pop     r12
0x18000724b  pop     rdi
0x18000724c  pop     rsi
0x18000724d  pop     rbx
0x18000724e  retn
0x18000724f  mov     r15d, 1
0x180007255  mov     [rsp+178h+var_108], rbx
0x18000725a  mov     rbx, [rbx]
0x18000725d  jmp     loc_1800070FC
0x180007262  mov     rcx, 3FFFFFFFFFFFFFFh
0x18000726c  cmp     [rax+8], rcx
0x180007270  jz      loc_180007680
0x180007276  mov     rbx, [rax]
0x180007279  mov     [rsp+178h+var_108], rax
0x18000727e  mov     [rsp+178h+var_100], 0
0x180007287  mov     ecx, 40h ; '@'; Size
0x18000728c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007291  mov     r9, rax
0x180007294  movups  xmmword ptr [rax+20h], xmm6
0x180007298  mov     [rax+30h], r13
0x18000729c  mov     rax, [rsp+178h+var_130]
0x1800072a1  mov     [r9+38h], rax
0x1800072a5  xor     ecx, ecx
0x1800072a7  mov     [rsp+178h+var_130], rcx
0x1800072ac  mov     [r9], rbx
0x1800072af  mov     [r9+8], rbx
0x1800072b3  mov     [r9+10h], rbx
0x1800072b7  mov     [r9+18h], cx
0x1800072bc  mov     r11, [rsp+178h+var_128]
0x1800072c1  inc     qword ptr [r11+8]
0x1800072c5  mov     r10, [r11]
0x1800072c8  mov     [r9+8], rsi
0x1800072cc  cmp     rsi, r10
0x1800072cf  jz      loc_18000747F
0x1800072d5  test    r15d, r15d
0x1800072d8  jz      loc_180007371
0x1800072de  mov     [rsi], r9
0x1800072e1  cmp     rsi, [r10]
0x1800072e4  jz      loc_180007494
0x1800072ea  mov     rax, [r9+8]
0x1800072ee  cmp     [rax+18h], cl
  ... truncated ...
```
