# Broker::SebBroker::QueryEventData(Broker::ApplicationIdentity const &,_GUID const &,_SebiSystemEventCreationParameter &,bool)

- ea: `0x18000e880`
- end: `0x18000ec05`
- name: `?QueryEventData@SebBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_GUID@@AEAU_SebiSystemEventCreationParameter@@_N@Z`
- size: `901`
- prototype: `void(Broker::SebBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _GUID *, struct _SebiSystemEventCreationParameter *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ec10`

## callees

- `0x180008c00`
- `0x18000e79c`
- `0x18000e880`
- `0x180011590`
- `0x1800173d4`
- `0x18001c00c`
- `0x18001d9ac`
- `0x18001f2e8`
- `0x180022434`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000ea46`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000ea46`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18000e9a0`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x18000e9a0`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000e952`
- `BrokerLib!BrFindBrokeredEvent` at `0x18000e952`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::SebBroker::QueryEventData(
        Broker::SebBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _GUID *a3,
        struct _SebiSystemEventCreationParameter *a4,
        bool a5)
{
  __int64 *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  volatile signed __int32 *v12; // rbx
  const WCHAR *lpString2; // rax
  const WCHAR *v14; // r8
  size_t v15; // rax
  const void *v16; // rcx
  size_t v17; // r8
  _QWORD *v18; // rax
  int v19; // edx
  int v20; // r8d
  _QWORD *v21; // r15
  __int64 v22; // rcx
  __int64 *v23; // [rsp+50h] [rbp-41h] BYREF
  __int64 v24; // [rsp+58h] [rbp-39h] BYREF
  __int64 v25; // [rsp+60h] [rbp-31h]
  __int128 v26; // [rsp+68h] [rbp-29h]
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-11h] BYREF
  int v28; // [rsp+98h] [rbp+7h]
  __int64 v29; // [rsp+F0h] [rbp+5Fh] BYREF

  v26 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a3);
  v29 = 0;
  v23 = 0;
  if ( !*((_QWORD *)this + 17) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v28 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v24 = *((_QWORD *)this + 17);
  v25 = 1;
  Broker::BrokerLock::Acquire((Broker::BrokerLock *)&v24);
  *(struct _GUID *)pExceptionObject = *a3;
  if ( (unsigned int)BrFindBrokeredEvent(*((_QWORD *)this + 17), pExceptionObject, 0, 0, &v29) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v28 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 17), v29, 0, 0, &v23) )
  {
    *(_OWORD *)&pExceptionObject[8] = 0;
    v28 = 3;
    *(_QWORD *)pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)pExceptionObject;
  }
  v9 = v23;
  v10 = v23[1];
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  v11 = *v9;
  *(_QWORD *)&v26 = *v9;
  v12 = (volatile signed __int32 *)v9[1];
  *((_QWORD *)&v26 + 1) = v12;
  if ( a5 )
  {
    if ( !Broker::ApplicationIdentity::CheckPackageName((Broker::ApplicationIdentity *)(v11 + 8), a2) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = (_QWORD *)((char *)a2 + 56);
        if ( v21[3] > 7u )
          v21 = (_QWORD *)*v21;
        WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, (_DWORD)a3, (__int64)v21);
      }
      *(_OWORD *)&pExceptionObject[8] = 0;
      v28 = 5;
      *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)pExceptionObject;
    }
  }
  else
  {
    lpString2 = (const WCHAR *)((char *)a2 + 24);
    if ( *((_QWORD *)a2 + 6) > 7u )
      lpString2 = *(const WCHAR **)lpString2;
    v14 = (const WCHAR *)(v11 + 32);
    if ( *(_QWORD *)(v11 + 56) > 7u )
      v14 = *(const WCHAR **)v14;
    if ( CompareStringEx(&LocaleName, 1u, v14, *(_DWORD *)(v11 + 48), lpString2, *((_DWORD *)a2 + 10), 0, 0, 0) != 2
      || (v15 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2,
          v16 = *(const void **)(v11 + 8),
          v17 = *(_QWORD *)(v11 + 16) - (_QWORD)v16,
          v17 < v15)
      || v17 > v15
      || memcmp_0(v16, *(const void **)a2, v17) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = (_QWORD *)((char *)a2 + 56);
        if ( *((_QWORD *)a2 + 10) > 7u )
          v18 = (_QWORD *)*v18;
        WPP_SF__guid__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), *(PSID *)a2, (__int64)v18);
      }
      *(_OWORD *)&pExceptionObject[8] = 0;
      v28 = 5;
      *(_QWORD *)pExceptionObject = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)pExceptionObject;
    }
  }
  v22 = *(_QWORD *)(v11 + 124);
  *((_DWORD *)a4 + 2) = *(_DWORD *)(v11 + 96);
  *((_DWORD *)a4 + 3) = *(_DWORD *)(v11 + 100);
  *((_DWORD *)a4 + 5) = *(_DWORD *)(v11 + 120);
  *((_DWORD *)a4 + 4) = *(_DWORD *)(v11 + 136);
  *(_QWORD *)a4 = v22;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, a3);
  if ( HIDWORD(v25) )
    Broker::BrokerLock::Release((Broker::BrokerLock *)&v24);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
}

```

## disassembly

```asm
0x18000e880  push    rbp
0x18000e882  push    rbx
0x18000e883  push    rsi
0x18000e884  push    rdi
0x18000e885  push    r12
0x18000e887  push    r13
0x18000e889  push    r14
0x18000e88b  push    r15
0x18000e88d  lea     rbp, [rsp-17h]
0x18000e892  sub     rsp, 0A8h
0x18000e899  mov     rsi, r9
0x18000e89c  mov     r12, r8
0x18000e89f  mov     r15, rdx
0x18000e8a2  mov     rbx, rcx
0x18000e8a5  xorps   xmm0, xmm0
0x18000e8a8  movdqu  [rbp+4Fh+var_78], xmm0
0x18000e8ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8b4  test    byte ptr [rcx+1Ch], 1
0x18000e8b8  jz      short loc_18000E8D8
0x18000e8ba  cmp     byte ptr [rcx+19h], 4
0x18000e8be  jb      short loc_18000E8D8
0x18000e8c0  mov     edx, 19h
0x18000e8c5  mov     r9, r8
0x18000e8c8  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000e8cf  mov     rcx, [rcx+10h]
0x18000e8d3  call    WPP_SF__guid_
0x18000e8d8  xor     r13d, r13d
0x18000e8db  mov     [rbp+4Fh+arg_0], r13
0x18000e8df  mov     [rbp+4Fh+var_90], r13
0x18000e8e3  mov     rax, [rbx+88h]
0x18000e8ea  test    rax, rax
0x18000e8ed  jnz     short loc_18000E919
0x18000e8ef  xorps   xmm0, xmm0
0x18000e8f2  movups  xmmword ptr [rbp+4Fh+pExceptionObject+8], xmm0
0x18000e8f6  mov     [rbp+4Fh+var_48], 3
0x18000e8fd  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000e904  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x18000e908  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000e90f  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000e913  call    _CxxThrowException_0
0x18000e919  mov     [rbp+4Fh+var_88], rax
0x18000e91d  mov     [rbp+4Fh+var_80], 1
0x18000e925  lea     rcx, [rbp+4Fh+var_88]; this
0x18000e929  call    ?Acquire@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Acquire(void)
0x18000e92e  nop
0x18000e92f  movups  xmm0, xmmword ptr [r12]
0x18000e934  movaps  xmmword ptr [rbp+4Fh+pExceptionObject], xmm0
0x18000e938  lea     rax, [rbp+4Fh+arg_0]
0x18000e93c  mov     [rsp+0E0h+lpString2], rax
0x18000e941  xor     r9d, r9d
0x18000e944  xor     r8d, r8d
0x18000e947  lea     rdx, [rbp+4Fh+pExceptionObject]
0x18000e94b  mov     rcx, [rbx+88h]
0x18000e952  call    cs:__imp_BrFindBrokeredEvent
0x18000e958  test    eax, eax
0x18000e95a  jz      short loc_18000E986
0x18000e95c  xorps   xmm0, xmm0
0x18000e95f  movups  xmmword ptr [rbp+4Fh+pExceptionObject+8], xmm0
0x18000e963  mov     [rbp+4Fh+var_48], 3
0x18000e96a  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000e971  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x18000e975  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000e97c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000e980  call    _CxxThrowException_0
0x18000e986  lea     rax, [rbp+4Fh+var_90]
0x18000e98a  mov     [rsp+0E0h+lpString2], rax
0x18000e98f  xor     r9d, r9d
0x18000e992  xor     r8d, r8d
0x18000e995  mov     rdx, [rbp+4Fh+arg_0]
0x18000e999  mov     rcx, [rbx+88h]
0x18000e9a0  call    cs:__imp_BrGetBrokeredEventInfo2
0x18000e9a6  test    eax, eax
0x18000e9a8  jz      short loc_18000E9D4
0x18000e9aa  xorps   xmm0, xmm0
0x18000e9ad  movups  xmmword ptr [rbp+4Fh+pExceptionObject+8], xmm0
0x18000e9b1  mov     [rbp+4Fh+var_48], 3
0x18000e9b8  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000e9bf  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x18000e9c3  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000e9ca  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000e9ce  call    _CxxThrowException_0
0x18000e9d4  mov     rbx, [rbp+4Fh+var_90]
0x18000e9d8  mov     rax, [rbx+8]
0x18000e9dc  test    rax, rax
0x18000e9df  jz      short loc_18000E9E5
0x18000e9e1  lock inc dword ptr [rax+8]
0x18000e9e5  mov     rdi, [rbx]
0x18000e9e8  mov     qword ptr [rbp+4Fh+var_78], rdi
0x18000e9ec  mov     rbx, [rbx+8]
0x18000e9f0  mov     qword ptr [rbp+4Fh+var_78+8], rbx
0x18000e9f4  cmp     [rbp+4Fh+arg_20], 0
0x18000e9f8  jnz     loc_18000EAEA
0x18000e9fe  mov     ecx, [r15+28h]
0x18000ea02  lea     rax, [r15+18h]
0x18000ea06  cmp     qword ptr [rax+18h], 7
0x18000ea0b  jbe     short loc_18000EA10
0x18000ea0d  mov     rax, [rax]
0x18000ea10  lea     r8, [rdi+20h]
0x18000ea14  cmp     qword ptr [r8+18h], 7
0x18000ea19  jbe     short loc_18000EA1E
0x18000ea1b  mov     r8, [r8]; lpString1
0x18000ea1e  mov     [rsp+0E0h+lParam], r13; lParam
0x18000ea23  mov     [rsp+0E0h+lpReserved], r13; lpReserved
0x18000ea28  mov     [rsp+0E0h+lpVersionInformation], r13; lpVersionInformation
0x18000ea2d  mov     [rsp+0E0h+cchCount2], ecx; cchCount2
0x18000ea31  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18000ea36  mov     r9d, [rdi+30h]; cchCount1
0x18000ea3a  mov     edx, 1; dwCmpFlags
0x18000ea3f  lea     rcx, LocaleName; lpLocaleName
0x18000ea46  call    cs:__imp_CompareStringEx
0x18000ea4c  cmp     eax, 2
0x18000ea4f  jnz     short loc_18000EA7A
0x18000ea51  mov     rdx, [r15]; Buf2
0x18000ea54  mov     rax, [r15+8]
0x18000ea58  sub     rax, rdx
0x18000ea5b  mov     rcx, [rdi+8]; Buf1
0x18000ea5f  mov     r8, [rdi+10h]
0x18000ea63  sub     r8, rcx; Size
0x18000ea66  cmp     r8, rax
0x18000ea69  jb      short loc_18000EA7A
0x18000ea6b  ja      short loc_18000EA7A
0x18000ea6d  call    memcmp_0
0x18000ea72  test    eax, eax
0x18000ea74  jz      loc_18000EB56
0x18000ea7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea81  test    byte ptr [rcx+1Ch], 20h
0x18000ea85  jz      short loc_18000EAC0
0x18000ea87  cmp     byte ptr [rcx+19h], 2
0x18000ea8b  jb      short loc_18000EAC0
0x18000ea8d  lea     rax, [r15+38h]
0x18000ea91  cmp     qword ptr [rax+18h], 7
0x18000ea96  jbe     short loc_18000EA9B
0x18000ea98  mov     rax, [rax]
0x18000ea9b  mov     edx, 1Ah
0x18000eaa0  mov     qword ptr [rsp+0E0h+cchCount2], rax; __int64
0x18000eaa5  mov     rax, [r15]
0x18000eaa8  mov     [rsp+0E0h+lpString2], rax; pSid
0x18000eaad  mov     r9, r12
0x18000eab0  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000eab7  mov     rcx, [rcx+10h]; LoggerHandle
0x18000eabb  call    WPP_SF__guid__sid_S
0x18000eac0  xorps   xmm0, xmm0
0x18000eac3  movups  xmmword ptr [rbp+4Fh+pExceptionObject+8], xmm0
0x18000eac7  mov     [rbp+4Fh+var_48], 5
0x18000eace  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000ead5  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x18000ead9  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000eae0  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000eae4  call    _CxxThrowException_0
0x18000eaea  mov     rdx, r15; struct Broker::ApplicationIdentity *
0x18000eaed  lea     rcx, [rdi+8]; this
0x18000eaf1  call    ?CheckPackageName@ApplicationIdentity@Broker@@QEBA_NAEBU12@@Z; Broker::ApplicationIdentity::CheckPackageName(Broker::ApplicationIdentity const &)
0x18000eaf6  test    al, al
0x18000eaf8  jnz     short loc_18000EB56
0x18000eafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb01  test    byte ptr [rcx+1Ch], 20h
0x18000eb05  jz      short loc_18000EB2C
0x18000eb07  cmp     byte ptr [rcx+19h], 2
0x18000eb0b  jb      short loc_18000EB2C
0x18000eb0d  add     r15, 38h ; '8'
0x18000eb11  cmp     qword ptr [r15+18h], 7
0x18000eb16  jbe     short loc_18000EB1B
0x18000eb18  mov     r15, [r15]
0x18000eb1b  mov     [rsp+0E0h+lpString2], r15
0x18000eb20  mov     r9, r12
0x18000eb23  mov     rcx, [rcx+10h]
0x18000eb27  call    WPP_SF__guid_S
0x18000eb2c  xorps   xmm0, xmm0
0x18000eb2f  movups  xmmword ptr [rbp+4Fh+pExceptionObject+8], xmm0
0x18000eb33  mov     [rbp+4Fh+var_48], 5
0x18000eb3a  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000eb41  mov     qword ptr [rbp+4Fh+pExceptionObject], rax
0x18000eb45  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000eb4c  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000eb50  call    _CxxThrowException_0
0x18000eb56  mov     rcx, [rdi+7Ch]
0x18000eb5a  mov     eax, [rdi+60h]
0x18000eb5d  mov     [rsi+8], eax
0x18000eb60  mov     eax, [rdi+64h]
0x18000eb63  mov     [rsi+0Ch], eax
0x18000eb66  mov     eax, [rdi+78h]
0x18000eb69  mov     [rsi+14h], eax
0x18000eb6c  mov     eax, [rdi+88h]
0x18000eb72  mov     [rsi+10h], eax
0x18000eb75  mov     [rsi], rcx
0x18000eb78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb7f  test    byte ptr [rcx+1Ch], 1
0x18000eb83  jz      short loc_18000EBA4
0x18000eb85  cmp     byte ptr [rcx+19h], 4
0x18000eb89  jb      short loc_18000EBA4
0x18000eb8b  mov     edx, 1Ch
0x18000eb90  mov     r9, r12
0x18000eb93  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18000eb9a  mov     rcx, [rcx+10h]
0x18000eb9e  call    WPP_SF__guid_
0x18000eba3  nop
0x18000eba4  cmp     dword ptr [rbp+4Fh+var_80+4], 0
0x18000eba8  jz      short loc_18000EBB4
0x18000ebaa  lea     rcx, [rbp+4Fh+var_88]; this
0x18000ebae  call    ?Release@BrokerLock@Broker@@QEAAXXZ; Broker::BrokerLock::Release(void)
0x18000ebb3  nop
0x18000ebb4  test    rbx, rbx
0x18000ebb7  jz      short loc_18000EBF1
0x18000ebb9  mov     edi, 0FFFFFFFFh
0x18000ebbe  mov     eax, edi
0x18000ebc0  lock xadd [rbx+8], eax
0x18000ebc5  cmp     eax, 1
0x18000ebc8  jnz     short loc_18000EBF1
0x18000ebca  mov     rax, [rbx]
0x18000ebcd  mov     rcx, rbx
0x18000ebd0  mov     rax, [rax]
0x18000ebd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd8  lock xadd [rbx+0Ch], edi
0x18000ebdd  cmp     edi, 1
0x18000ebe0  jnz     short loc_18000EBF1
0x18000ebe2  mov     rax, [rbx]
0x18000ebe5  mov     rcx, rbx
0x18000ebe8  mov     rax, [rax+8]
0x18000ebec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf1  add     rsp, 0A8h
0x18000ebf8  pop     r15
0x18000ebfa  pop     r14
0x18000ebfc  pop     r13
0x18000ebfe  pop     r12
0x18000ec00  pop     rdi
0x18000ec01  pop     rsi
0x18000ec02  pop     rbx
0x18000ec03  pop     rbp
0x18000ec04  retn
```
