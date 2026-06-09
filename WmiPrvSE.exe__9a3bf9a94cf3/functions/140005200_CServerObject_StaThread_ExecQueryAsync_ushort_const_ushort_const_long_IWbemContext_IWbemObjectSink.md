# CServerObject_StaThread::ExecQueryAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140005200`
- end: `0x1400053d6`
- name: `?ExecQueryAsync@CServerObject_StaThread@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140005200`
- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x1400234b8`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000526b`
- `wbemcomn!GetMemLogObject` at `0x14000526b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140005276`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140005276`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140005281`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140005281`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::ExecQueryAsync(
        CServerObject_StaThread *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6)
{
  struct IUnknown *v8; // r9
  struct ProxyContainer *v11; // rsi
  int Proxy; // eax
  HRESULT v13; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r9
  int v18; // edi
  struct IUnknown *v19; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v21; // edx
  __int64 v23; // r9
  unsigned int v24; // [rsp+20h] [rbp-68h]
  unsigned int v25; // [rsp+28h] [rbp-60h]
  unsigned int v26; // [rsp+30h] [rbp-58h]
  struct IUnknown *v27; // [rsp+90h] [rbp+8h] BYREF

  v8 = (struct IUnknown *)*((_QWORD *)this + 61);
  if ( !v8 )
  {
    v13 = -2147217372;
    goto LABEL_5;
  }
  v11 = (CServerObject_StaThread *)((char *)this + 560);
  v27 = 0;
  Proxy = ProviderSubSystem_Common_Globals::GetProxy(
            (CServerObject_StaThread *)((char *)this + 560),
            0,
            &IID_IWbemServices,
            v8,
            &v27);
  if ( Proxy < 0 )
  {
    if ( Proxy != -2147217406 )
    {
      v13 = -2147217398;
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  v13 = CoImpersonateClient();
  if ( v13 < 0 )
  {
    v18 = 0;
    v13 = -2147217405;
LABEL_12:
    ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v27, v18);
    goto LABEL_13;
  }
  v18 = 1;
  if ( (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
    v13 = SetInterfaceSecurity(v27, v15, v16, v17, v24, v25, v26);
  if ( v13 < 0 )
    goto LABEL_12;
LABEL_13:
  if ( v13 == -2147217406 )
  {
LABEL_4:
    v13 = -2147217379;
LABEL_5:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v13);
    goto LABEL_17;
  }
  if ( v13 < 0 )
    goto LABEL_5;
  v19 = v27;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v13 = ProviderSubSystem_Common_Globals::SetCloaking(v19, v21, CurrentImpersonationLevel);
  if ( v13 >= 0 )
  {
    v23 = a4;
    LODWORD(v23) = a4 & 0xFFFDFFFF;
    if ( *((_DWORD *)this + 138) >= 3u )
      v23 = a4;
    v13 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *const, unsigned __int16 *const, __int64, struct IWbemContext *, struct IWbemObjectSink *))v19->lpVtbl[7].QueryInterface)(
            v19,
            a2,
            a3,
            v23,
            a5,
            a6);
  }
  ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v27, v18);
  if ( v13 < 0 )
    goto LABEL_5;
LABEL_17:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005200  mov     r11, rsp
0x140005203  push    rbx
0x140005204  push    rbp
0x140005205  push    rsi
0x140005206  push    rdi
0x140005207  push    r12
0x140005209  push    r13
0x14000520b  push    r14
0x14000520d  push    r15
0x14000520f  sub     rsp, 48h
0x140005213  mov     r15d, r9d
0x140005216  mov     r12, r8
0x140005219  mov     r9, [rcx+1E8h]; struct IUnknown *
0x140005220  mov     r13, rdx
0x140005223  mov     rbp, rcx
0x140005226  test    r9, r9
0x140005229  jz      loc_140005387
0x14000522f  lea     rsi, [rcx+230h]
0x140005236  mov     qword ptr [r11+8], 0
0x14000523e  lea     rax, [r11+8]
0x140005242  mov     rcx, rsi; struct ProxyContainer *
0x140005245  lea     r8, IID_IWbemServices; struct _GUID *
0x14000524c  mov     [r11-68h], rax
0x140005250  xor     edx, edx; unsigned int
0x140005252  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x140005257  test    eax, eax
0x140005259  jns     short loc_140005281
0x14000525b  cmp     eax, 80041002h
0x140005260  jnz     loc_1400053A5
0x140005266  mov     ebx, 8004101Dh
0x14000526b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140005271  mov     rcx, rax
0x140005274  mov     edx, ebx
0x140005276  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000527c  jmp     loc_14000530B
0x140005281  call    cs:__imp_CoImpersonateClient
0x140005287  mov     ebx, eax
0x140005289  test    eax, eax
0x14000528b  js      short loc_1400052A8
0x14000528d  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140005292  add     eax, 0FFFFFFFDh
0x140005295  mov     edi, 1
0x14000529a  cmp     eax, edi
0x14000529c  ja      loc_140005391
0x1400052a2  test    ebx, ebx
0x1400052a4  js      short loc_1400052AF
0x1400052a6  jmp     short loc_1400052C4
0x1400052a8  xor     edi, edi
0x1400052aa  mov     ebx, 80041003h
0x1400052af  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x1400052b7  mov     r9d, edi; int
0x1400052ba  xor     edx, edx; unsigned int
0x1400052bc  mov     rcx, rsi; struct ProxyContainer *
0x1400052bf  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x1400052c4  cmp     ebx, 80041002h
0x1400052ca  jz      short loc_140005266
0x1400052cc  test    ebx, ebx
0x1400052ce  js      short loc_14000526B
0x1400052d0  mov     r14, [rsp+88h+arg_0]
0x1400052d8  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400052dd  mov     r8d, eax; unsigned int
0x1400052e0  mov     rcx, r14; struct IUnknown *
0x1400052e3  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x1400052e8  mov     ebx, eax
0x1400052ea  test    eax, eax
0x1400052ec  jns     short loc_14000533B
0x1400052ee  mov     r8, [rsp+88h+arg_0]; struct IUnknown *
0x1400052f6  mov     r9d, edi; int
0x1400052f9  xor     edx, edx; unsigned int
0x1400052fb  mov     rcx, rsi; struct ProxyContainer *
0x1400052fe  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140005303  test    ebx, ebx
0x140005305  js      loc_14000526B
0x14000530b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005312  lea     rax, WPP_GLOBAL_Control
0x140005319  cmp     rcx, rax
0x14000531c  jz      short loc_140005328
0x14000531e  test    byte ptr [rcx+1Ch], 4
0x140005322  jnz     loc_1400053AF
0x140005328  mov     eax, ebx
0x14000532a  add     rsp, 48h
0x14000532e  pop     r15
0x140005330  pop     r14
0x140005332  pop     r13
0x140005334  pop     r12
0x140005336  pop     rdi
0x140005337  pop     rsi
0x140005338  pop     rbp
0x140005339  pop     rbx
0x14000533a  retn
0x14000533b  mov     rdx, [rsp+88h+arg_28]
0x140005343  mov     r9d, r15d
0x140005346  mov     rax, [r14]
0x140005349  btr     r9d, 11h
0x14000534e  cmp     dword ptr [rbp+228h], 3
0x140005355  mov     r8, r12
0x140005358  mov     [rsp+88h+var_60], rdx
0x14000535d  mov     rcx, r14
0x140005360  mov     rdx, [rsp+88h+arg_20]
0x140005368  cmovnb  r9d, r15d
0x14000536c  mov     rax, [rax+0A8h]
0x140005373  mov     [rsp+88h+var_68], rdx
0x140005378  mov     rdx, r13
0x14000537b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005380  mov     ebx, eax
0x140005382  jmp     loc_1400052EE
0x140005387  mov     ebx, 80041024h
0x14000538c  jmp     loc_14000526B
0x140005391  mov     rcx, [rsp+88h+arg_0]; struct IUnknown *
0x140005399  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x14000539e  mov     ebx, eax
0x1400053a0  jmp     loc_1400052A2
0x1400053a5  mov     ebx, 8004100Ah
0x1400053aa  jmp     loc_14000526B
0x1400053af  cmp     byte ptr [rcx+19h], 2
0x1400053b3  jb      loc_140005328
0x1400053b9  mov     rcx, [rcx+10h]
0x1400053bd  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x1400053c4  mov     edx, 26h ; '&'
0x1400053c9  mov     r9d, ebx
0x1400053cc  call    WPP_SF_d
0x1400053d1  jmp     loc_140005328
```
