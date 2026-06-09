# CServerObject_StaThread::AccessCheck(ushort const *,ushort const *,long,uchar const *)

- ea: `0x14003d680`
- end: `0x14003d7b1`
- name: `?AccessCheck@CServerObject_StaThread@@UEAAJPEBG0JPEBE@Z`
- size: `305`
- prototype: `__int64 __fastcall(CServerObject_StaThread *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x1400234b8`
- `0x14003d680`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003d75a`
- `wbemcomn!GetMemLogObject` at `0x14003d75a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d765`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003d765`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::AccessCheck(
        CServerObject_StaThread *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int8 *a5)
{
  struct IUnknown *v7; // r9
  int v9; // ebx
  struct ProxyContainer *v10; // rsi
  int v11; // eax
  struct IUnknown *v12; // rdi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v14; // edx
  CMemoryLog *MemLogObject; // rax
  struct IUnknown *v17; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+80h] [rbp+8h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 64);
  v9 = -2147217372;
  if ( !v7 )
    goto LABEL_8;
  v18 = 0;
  v10 = (CServerObject_StaThread *)((char *)this + 536);
  v17 = 0;
  v11 = ProviderSubSystem_Common_Globals::SetProxyState(
          (CServerObject_StaThread *)((char *)this + 536),
          3u,
          &IID_IWbemEventProviderSecurity,
          v7,
          &v17,
          &v18);
  v9 = v11;
  if ( v11 == -2147217406 )
  {
    v9 = -2147217379;
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    goto LABEL_9;
  }
  if ( v11 < 0 )
    goto LABEL_8;
  v12 = v17;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v9 = ProviderSubSystem_Common_Globals::SetCloaking(v12, v14, CurrentImpersonationLevel);
  if ( v9 >= 0 )
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, const unsigned __int8 *))v12->lpVtbl[1].QueryInterface)(
           v12,
           a2,
           a3,
           a4,
           a5);
  ProviderSubSystem_Common_Globals::RevertProxyState(v10, 3u, v17, v18);
  if ( v9 < 0 )
    goto LABEL_8;
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003d680  mov     r11, rsp
0x14003d683  push    rbx
0x14003d684  push    rbp
0x14003d685  push    rsi
0x14003d686  push    rdi
0x14003d687  push    r14
0x14003d689  push    r15
0x14003d68b  sub     rsp, 48h
0x14003d68f  mov     ebp, r9d
0x14003d692  mov     r14, r8
0x14003d695  mov     r9, [rcx+200h]; struct IUnknown *
0x14003d69c  mov     r15, rdx
0x14003d69f  mov     ebx, 80041024h
0x14003d6a4  test    r9, r9
0x14003d6a7  jz      loc_14003D75A
0x14003d6ad  lea     rax, [r11+8]
0x14003d6b1  mov     dword ptr [r11+8], 0
0x14003d6b9  mov     [r11-50h], rax
0x14003d6bd  lea     rsi, [rcx+218h]
0x14003d6c4  lea     rax, [r11-48h]
0x14003d6c8  mov     qword ptr [r11-48h], 0
0x14003d6d0  lea     r8, IID_IWbemEventProviderSecurity; struct _GUID *
0x14003d6d7  mov     [r11-58h], rax
0x14003d6db  mov     edx, 3; unsigned int
0x14003d6e0  mov     rcx, rsi; struct ProxyContainer *
0x14003d6e3  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003d6e8  mov     ebx, eax
0x14003d6ea  cmp     eax, 80041002h
0x14003d6ef  jnz     short loc_14003D6F6
0x14003d6f1  lea     ebx, [rax+1Bh]
0x14003d6f4  jmp     short loc_14003D75A
0x14003d6f6  test    eax, eax
0x14003d6f8  js      short loc_14003D75A
0x14003d6fa  mov     rdi, [rsp+78h+var_48]
0x14003d6ff  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003d704  mov     r8d, eax; unsigned int
0x14003d707  mov     rcx, rdi; struct IUnknown *
0x14003d70a  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003d70f  mov     ebx, eax
0x14003d711  test    eax, eax
0x14003d713  js      short loc_14003D73C
0x14003d715  mov     rax, [rdi]
0x14003d718  mov     r9d, ebp
0x14003d71b  mov     r8, [rsp+78h+arg_20]
0x14003d723  mov     rdx, r15
0x14003d726  mov     [rsp+78h+var_58], r8
0x14003d72b  mov     rcx, rdi
0x14003d72e  mov     r8, r14
0x14003d731  mov     rax, [rax+18h]
0x14003d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d73a  mov     ebx, eax
0x14003d73c  mov     r9d, [rsp+78h+arg_0]; int
0x14003d744  mov     edx, 3; unsigned int
0x14003d749  mov     r8, [rsp+78h+var_48]; struct IUnknown *
0x14003d74e  mov     rcx, rsi; struct ProxyContainer *
0x14003d751  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003d756  test    ebx, ebx
0x14003d758  jns     short loc_14003D76B
0x14003d75a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003d760  mov     rcx, rax
0x14003d763  mov     edx, ebx
0x14003d765  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003d76b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d772  lea     rax, WPP_GLOBAL_Control
0x14003d779  cmp     rcx, rax
0x14003d77c  jz      short loc_14003D7A2
0x14003d77e  test    byte ptr [rcx+1Ch], 4
0x14003d782  jz      short loc_14003D7A2
0x14003d784  cmp     byte ptr [rcx+19h], 2
0x14003d788  jb      short loc_14003D7A2
0x14003d78a  mov     rcx, [rcx+10h]
0x14003d78e  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003d795  mov     edx, 2Eh ; '.'
0x14003d79a  mov     r9d, ebx
0x14003d79d  call    WPP_SF_d
0x14003d7a2  mov     eax, ebx
0x14003d7a4  add     rsp, 48h
0x14003d7a8  pop     r15
0x14003d7aa  pop     r14
0x14003d7ac  pop     rdi
0x14003d7ad  pop     rsi
0x14003d7ae  pop     rbp
0x14003d7af  pop     rbx
0x14003d7b0  retn
```
