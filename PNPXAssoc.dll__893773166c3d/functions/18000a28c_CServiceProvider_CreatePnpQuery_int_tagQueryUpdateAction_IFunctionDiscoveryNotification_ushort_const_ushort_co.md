# CServiceProvider::CreatePnpQuery(int,tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *,ushort const *,ulong,CChildDeviceInfo *)

- ea: `0x18000a28c`
- end: `0x18000a46c`
- name: `?CreatePnpQuery@CServiceProvider@@IEAAJHW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG2KPEAVCChildDeviceInfo@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CServiceProvider *this, unsigned int, enum tagQueryUpdateAction, struct IFunctionDiscoveryNotification *, unsigned __int16 *, wchar_t *String1, unsigned int, struct CChildDeviceInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000b2e4`

## callees

- `0x18000a28c`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000bfcc`
- `0x18000ccec`
- `0x18000d09c`
- `0x18000d16c`
- `0x18000d2a8`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a407`
- `KERNEL32!LeaveCriticalSection` at `0x18000a407`
- `KERNEL32!EnterCriticalSection` at `0x18000a2dc`
- `KERNEL32!EnterCriticalSection` at `0x18000a2dc`

## pseudocode

```c
__int64 __fastcall CServiceProvider::CreatePnpQuery(
        CServiceProvider *this,
        unsigned int a2,
        enum tagQueryUpdateAction a3,
        struct IFunctionDiscoveryNotification *a4,
        unsigned __int16 *a5,
        wchar_t *String1,
        unsigned int a7,
        struct CChildDeviceInfo *a8)
{
  CPnpNotification *v12; // rcx
  CPnpNotification *v13; // rcx
  CPnpNotification *v14; // rbx
  int v15; // eax
  bool v16; // cf
  CPnpNotification *v18; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  EnterCriticalSection(&g_csGlobalLock);
  if ( !a2 )
  {
    if ( g_pPnpNotification )
    {
      CPnpNotification::Unsubscribe(g_pPnpNotification, String1);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwClientCount, 0xFFFFFFFF) == 1 )
        CPnpNotification::Uninitialize(v13);
      (*(void (__fastcall **)(CPnpNotification *))(*(_QWORD *)g_pPnpNotification + 16LL))(g_pPnpNotification);
      *((_DWORD *)this + 26) = 0;
    }
    goto LABEL_19;
  }
  if ( *((_DWORD *)this + 26) )
  {
    if ( !g_pPnpNotification )
    {
      a2 = -2147467259;
      goto LABEL_19;
    }
LABEL_18:
    a2 = CPnpNotification::SubscribeForNotification(v12, a3, a4, a5, String1, a7, a8);
    goto LABEL_19;
  }
  if ( g_pPnpNotification )
  {
    (*(void (__fastcall **)(CPnpNotification *))(*(_QWORD *)g_pPnpNotification + 8LL))(g_pPnpNotification);
    goto LABEL_17;
  }
  v18 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  g_pPnpNotification = 0;
  a2 = ATL::CComObject<CPnpNotification>::CreateInstance(&v18);
  if ( !a2 )
  {
    v14 = v18;
    (*(void (__fastcall **)(CPnpNotification *))(*(_QWORD *)v18 + 8LL))(v18);
    g_pPnpNotification = v14;
LABEL_17:
    _InterlockedIncrement((volatile signed __int32 *)&g_dwClientCount);
    *((_DWORD *)this + 26) = 1;
    goto LABEL_18;
  }
LABEL_19:
  LeaveCriticalSection(&g_csGlobalLock);
  v15 = 0;
  if ( a2 )
    v16 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v16 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v15) = !v16;
    if ( v15 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  return a2;
}

```

## disassembly

```asm
0x18000a28c  push    rbx
0x18000a28e  push    rbp
0x18000a28f  push    rsi
0x18000a290  push    rdi
0x18000a291  push    r12
0x18000a293  sub     rsp, 50h
0x18000a297  mov     rsi, r9
0x18000a29a  mov     ebp, r8d
0x18000a29d  mov     ebx, edx
0x18000a29f  mov     rdi, rcx
0x18000a2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a9  lea     r12, WPP_GLOBAL_Control
0x18000a2b0  cmp     rcx, r12
0x18000a2b3  jz      short loc_18000A2D5
0x18000a2b5  cmp     byte ptr [rcx+19h], 4
0x18000a2b9  jb      short loc_18000A2D5
0x18000a2bb  mov     rcx, [rcx+10h]
0x18000a2bf  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a2c6  mov     edx, 23h ; '#'
0x18000a2cb  mov     [rsp+78h+var_58], rdi
0x18000a2d0  call    WPP_SF_sq
0x18000a2d5  lea     rcx, ?g_csGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a2dc  call    cs:__imp_EnterCriticalSection
0x18000a2e2  test    ebx, ebx
0x18000a2e4  jnz     short loc_18000A333
0x18000a2e6  mov     rcx, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; this
0x18000a2ed  test    rcx, rcx
0x18000a2f0  jz      loc_18000A400
0x18000a2f6  mov     rdx, [rsp+78h+String1]; String1
0x18000a2fe  call    ?Unsubscribe@CPnpNotification@@QEAAJPEBG@Z; CPnpNotification::Unsubscribe(ushort const *)
0x18000a303  or      eax, 0FFFFFFFFh
0x18000a306  lock xadd cs:?g_dwClientCount@@3KA, eax; ulong g_dwClientCount
0x18000a30e  cmp     eax, 1
0x18000a311  jnz     short loc_18000A318
0x18000a313  call    ?Uninitialize@CPnpNotification@@QEAAXXZ; CPnpNotification::Uninitialize(void)
0x18000a318  mov     rcx, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; CPnpNotification * g_pPnpNotification
0x18000a31f  mov     rax, [rcx]
0x18000a322  mov     rax, [rax+10h]
0x18000a326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32b  mov     [rdi+68h], ebx
0x18000a32e  jmp     loc_18000A400
0x18000a333  cmp     dword ptr [rdi+68h], 0
0x18000a337  jnz     loc_18000A420
0x18000a33d  mov     rcx, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; CPnpNotification * g_pPnpNotification
0x18000a344  test    rcx, rcx
0x18000a347  jnz     short loc_18000A3AD
0x18000a349  mov     [rsp+78h+var_38], rcx
0x18000a34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a355  cmp     rcx, r12
0x18000a358  jz      short loc_18000A375
0x18000a35a  cmp     byte ptr [rcx+19h], 4
0x18000a35e  jb      short loc_18000A375
0x18000a360  mov     rcx, [rcx+10h]
0x18000a364  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000a36b  mov     edx, 20h ; ' '
0x18000a370  call    WPP_SF_s
0x18000a375  lea     rcx, [rsp+78h+var_38]
0x18000a37a  mov     cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA, 0; CPnpNotification * g_pPnpNotification
0x18000a385  call    ?CreateInstance@?$CComObject@VCPnpNotification@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPnpNotification>::CreateInstance(ATL::CComObject<CPnpNotification> * *)
0x18000a38a  mov     ebx, eax
0x18000a38c  test    eax, eax
0x18000a38e  jnz     short loc_18000A400
0x18000a390  mov     rbx, [rsp+78h+var_38]
0x18000a395  mov     rcx, rbx
0x18000a398  mov     rax, [rbx]
0x18000a39b  mov     rax, [rax+8]
0x18000a39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a4  mov     cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA, rbx; CPnpNotification * g_pPnpNotification
0x18000a3ab  jmp     short loc_18000A3B9
0x18000a3ad  mov     rax, [rcx]
0x18000a3b0  mov     rax, [rax+8]
0x18000a3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b9  lock inc cs:?g_dwClientCount@@3KA; ulong g_dwClientCount
0x18000a3c0  mov     dword ptr [rdi+68h], 1
0x18000a3c7  mov     rax, [rsp+78h+arg_38]
0x18000a3cf  mov     r8, rsi; struct IFunctionDiscoveryNotification *
0x18000a3d2  mov     r9, [rsp+78h+arg_20]; unsigned __int16 *
0x18000a3da  mov     edx, ebp; enum tagQueryUpdateAction
0x18000a3dc  mov     [rsp+78h+var_48], rax; struct CChildDeviceInfo *
0x18000a3e1  mov     eax, [rsp+78h+arg_30]
0x18000a3e8  mov     [rsp+78h+var_50], eax; unsigned int
0x18000a3ec  mov     rax, [rsp+78h+String1]
0x18000a3f4  mov     [rsp+78h+var_58], rax; String1
0x18000a3f9  call    ?SubscribeForNotification@CPnpNotification@@QEAAJW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG2KPEAVCChildDeviceInfo@@@Z; CPnpNotification::SubscribeForNotification(tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *,ushort const *,ulong,CChildDeviceInfo *)
0x18000a3fe  mov     ebx, eax
0x18000a400  lea     rcx, ?g_csGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a407  call    cs:__imp_LeaveCriticalSection
0x18000a40d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a414  xor     eax, eax
0x18000a416  test    ebx, ebx
0x18000a418  jnz     short loc_18000A431
0x18000a41a  cmp     byte ptr [rcx+19h], 4
0x18000a41e  jmp     short loc_18000A435
0x18000a420  cmp     cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA, 0; CPnpNotification * g_pPnpNotification
0x18000a428  jnz     short loc_18000A3C7
0x18000a42a  mov     ebx, 80004005h
0x18000a42f  jmp     short loc_18000A400
0x18000a431  cmp     byte ptr [rcx+19h], 2
0x18000a435  setnb   al
0x18000a438  cmp     rcx, r12
0x18000a43b  jz      short loc_18000A45F
0x18000a43d  test    eax, eax
0x18000a43f  jz      short loc_18000A45F
0x18000a441  mov     rcx, [rcx+10h]
0x18000a445  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000a44c  mov     edx, 24h ; '$'
0x18000a451  mov     [rsp+78h+var_50], ebx
0x18000a455  mov     [rsp+78h+var_58], rdi
0x18000a45a  call    WPP_SF_sqd
0x18000a45f  mov     eax, ebx
0x18000a461  add     rsp, 50h
0x18000a465  pop     r12
0x18000a467  pop     rdi
0x18000a468  pop     rsi
0x18000a469  pop     rbp
0x18000a46a  pop     rbx
0x18000a46b  retn
```
