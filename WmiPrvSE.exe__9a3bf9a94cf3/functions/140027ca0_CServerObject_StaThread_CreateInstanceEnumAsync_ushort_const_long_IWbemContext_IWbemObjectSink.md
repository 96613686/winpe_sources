# CServerObject_StaThread::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140027ca0`
- end: `0x140027e58`
- name: `?CreateInstanceEnumAsync@CServerObject_StaThread@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(CServerObject_StaThread *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x1400234b8`
- `0x140027ca0`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140027d35`
- `wbemcomn!GetMemLogObject` at `0x140027d35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027d40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027d40`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140027d4b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140027d4b`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::CreateInstanceEnumAsync(
        CServerObject_StaThread *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IUnknown *v7; // r9
  struct ProxyContainer *v10; // rsi
  int Proxy; // eax
  HRESULT v12; // ebx
  int v13; // edi
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r9
  struct IUnknown *v18; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v20; // edx
  __int64 v21; // r8
  unsigned int v23; // [rsp+20h] [rbp-68h]
  unsigned int v24; // [rsp+28h] [rbp-60h]
  unsigned int v25; // [rsp+30h] [rbp-58h]
  struct IUnknown *v26; // [rsp+90h] [rbp+8h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 61);
  if ( !v7 )
  {
    v12 = -2147217372;
    goto LABEL_9;
  }
  v10 = (CServerObject_StaThread *)((char *)this + 560);
  v26 = 0;
  Proxy = ProviderSubSystem_Common_Globals::GetProxy(
            (CServerObject_StaThread *)((char *)this + 560),
            0,
            &IID_IWbemServices,
            v7,
            &v26);
  if ( Proxy < 0 )
  {
    if ( Proxy != -2147217406 )
    {
      v12 = -2147217398;
      goto LABEL_9;
    }
    goto LABEL_4;
  }
  v12 = CoImpersonateClient();
  if ( v12 < 0 )
  {
    v13 = 0;
    v12 = -2147217405;
LABEL_6:
    ProviderSubSystem_Common_Globals::RevertProxyState(v10, 0, v26, v13);
    goto LABEL_7;
  }
  v13 = 1;
  if ( ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
    v12 = SetInterfaceSecurity(v26, v15, v16, v17, v23, v24, v25);
  if ( v12 < 0 )
    goto LABEL_6;
LABEL_7:
  if ( v12 == -2147217406 )
  {
LABEL_4:
    v12 = -2147217379;
LABEL_9:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v12);
    goto LABEL_21;
  }
  if ( v12 < 0 )
    goto LABEL_9;
  v18 = v26;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v12 = ProviderSubSystem_Common_Globals::SetCloaking(v18, v20, CurrentImpersonationLevel);
  if ( v12 >= 0 )
  {
    v21 = a3;
    LODWORD(v21) = a3 & 0xFFFDFFFF;
    if ( *((_DWORD *)this + 138) >= 3u )
      v21 = a3;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *const, __int64, struct IWbemContext *, struct IWbemObjectSink *))v18->lpVtbl[6].AddRef)(
            v18,
            a2,
            v21,
            a4,
            a5);
  }
  ProviderSubSystem_Common_Globals::RevertProxyState(v10, 0, v26, v13);
  if ( v12 < 0 )
    goto LABEL_9;
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140027ca0  mov     r11, rsp
0x140027ca3  push    rbx
0x140027ca4  push    rbp
0x140027ca5  push    rsi
0x140027ca6  push    rdi
0x140027ca7  push    r12
0x140027ca9  push    r13
0x140027cab  push    r14
0x140027cad  push    r15
0x140027caf  sub     rsp, 48h
0x140027cb3  mov     r12, r9
0x140027cb6  mov     r15d, r8d
0x140027cb9  mov     r9, [rcx+1E8h]; struct IUnknown *
0x140027cc0  mov     r13, rdx
0x140027cc3  mov     rbp, rcx
0x140027cc6  test    r9, r9
0x140027cc9  jz      loc_140027D72
0x140027ccf  lea     rsi, [rcx+230h]
0x140027cd6  mov     qword ptr [r11+8], 0
0x140027cde  lea     rax, [r11+8]
0x140027ce2  mov     rcx, rsi; struct ProxyContainer *
0x140027ce5  lea     r8, IID_IWbemServices; struct _GUID *
0x140027cec  mov     [r11-68h], rax
0x140027cf0  xor     edx, edx; unsigned int
0x140027cf2  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x140027cf7  test    eax, eax
0x140027cf9  jns     short loc_140027D4B
0x140027cfb  cmp     eax, 80041002h
0x140027d00  jnz     loc_140027E4E
0x140027d06  mov     ebx, 8004101Dh
0x140027d0b  jmp     short loc_140027D35
0x140027d0d  xor     edi, edi
0x140027d0f  mov     ebx, 80041003h
0x140027d14  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x140027d1c  mov     r9d, edi; int
0x140027d1f  xor     edx, edx; unsigned int
0x140027d21  mov     rcx, rsi; struct ProxyContainer *
0x140027d24  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140027d29  cmp     ebx, 80041002h
0x140027d2f  jz      short loc_140027D06
0x140027d31  test    ebx, ebx
0x140027d33  jns     short loc_140027D79
0x140027d35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140027d3b  mov     rcx, rax
0x140027d3e  mov     edx, ebx
0x140027d40  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140027d46  jmp     loc_140027DEE
0x140027d4b  call    cs:__imp_CoImpersonateClient
0x140027d51  mov     ebx, eax
0x140027d53  test    eax, eax
0x140027d55  js      short loc_140027D0D
0x140027d57  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140027d5c  add     eax, 0FFFFFFFDh
0x140027d5f  mov     edi, 1
0x140027d64  cmp     eax, edi
0x140027d66  ja      loc_140027E3A
0x140027d6c  test    ebx, ebx
0x140027d6e  jns     short loc_140027D29
0x140027d70  jmp     short loc_140027D14
0x140027d72  mov     ebx, 80041024h
0x140027d77  jmp     short loc_140027D35
0x140027d79  mov     r14, [rsp+88h+arg_0]
0x140027d81  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140027d86  mov     r8d, eax; unsigned int
0x140027d89  mov     rcx, r14; struct IUnknown *
0x140027d8c  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x140027d91  mov     ebx, eax
0x140027d93  test    eax, eax
0x140027d95  js      short loc_140027DD1
0x140027d97  mov     rax, [r14]
0x140027d9a  mov     r8d, r15d
0x140027d9d  mov     rdx, [rsp+88h+arg_20]
0x140027da5  btr     r8d, 11h
0x140027daa  cmp     dword ptr [rbp+228h], 3
0x140027db1  mov     r9, r12
0x140027db4  mov     [rsp+88h+var_68], rdx
0x140027db9  mov     rcx, r14
0x140027dbc  mov     rax, [rax+98h]
0x140027dc3  cmovnb  r8d, r15d
0x140027dc7  mov     rdx, r13
0x140027dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027dcf  mov     ebx, eax
0x140027dd1  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x140027dd9  mov     r9d, edi; int
0x140027ddc  xor     edx, edx; unsigned int
0x140027dde  mov     rcx, rsi; struct ProxyContainer *
0x140027de1  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140027de6  test    ebx, ebx
0x140027de8  js      loc_140027D35
0x140027dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140027df5  lea     rax, WPP_GLOBAL_Control
0x140027dfc  cmp     rcx, rax
0x140027dff  jnz     short loc_140027E14
0x140027e01  mov     eax, ebx
0x140027e03  add     rsp, 48h
0x140027e07  pop     r15
0x140027e09  pop     r14
0x140027e0b  pop     r13
0x140027e0d  pop     r12
0x140027e0f  pop     rdi
0x140027e10  pop     rsi
0x140027e11  pop     rbp
0x140027e12  pop     rbx
0x140027e13  retn
0x140027e14  test    byte ptr [rcx+1Ch], 4
0x140027e18  jz      short loc_140027E01
0x140027e1a  cmp     byte ptr [rcx+19h], 2
0x140027e1e  jb      short loc_140027E01
0x140027e20  mov     rcx, [rcx+10h]
0x140027e24  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x140027e2b  mov     edx, 24h ; '$'
0x140027e30  mov     r9d, ebx
0x140027e33  call    WPP_SF_d
0x140027e38  jmp     short loc_140027E01
0x140027e3a  mov     rcx, [rsp+88h+arg_0]; struct IUnknown *
0x140027e42  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x140027e47  mov     ebx, eax
0x140027e49  jmp     loc_140027D6C
0x140027e4e  mov     ebx, 8004100Ah
0x140027e53  jmp     loc_140027D35
```
