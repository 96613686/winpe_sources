# CServerObject_StaThread::GetObjectAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x140027850`
- end: `0x140027a07`
- name: `?GetObjectAsync@CServerObject_StaThread@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(CServerObject_StaThread *__hidden this, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x1400055e4`
- `0x1400058dc`
- `0x1400234b8`
- `0x140027850`
- `0x14004612c`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14002787d`
- `wbemcomn!GetMemLogObject` at `0x14002787d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027888`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140027888`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400278e7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400278e7`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::GetObjectAsync(
        CServerObject_StaThread *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IUnknown *v7; // r9
  HRESULT v8; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned int v10; // r14d
  struct ProxyContainer *v11; // rbp
  bool v12; // cf
  struct ProxyContainer *v13; // rcx
  int Proxy; // eax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r9
  int v18; // edi
  struct IUnknown *v19; // rsi
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v21; // edx
  unsigned int v23; // [rsp+20h] [rbp-48h]
  unsigned int v24; // [rsp+28h] [rbp-40h]
  unsigned int v25; // [rsp+30h] [rbp-38h]
  struct IUnknown *v26; // [rsp+70h] [rbp+8h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 61);
  if ( !v7 )
  {
    v8 = -2147217372;
LABEL_3:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
    goto LABEL_21;
  }
  v26 = 0;
  v10 = a3 & 0xFFFDFFFF;
  v11 = (CServerObject_StaThread *)((char *)this + 560);
  v12 = *((_DWORD *)this + 138) < 3u;
  v13 = (CServerObject_StaThread *)((char *)this + 560);
  if ( !v12 )
    v10 = a3;
  Proxy = ProviderSubSystem_Common_Globals::GetProxy(v13, 0, &IID_IWbemServices, v7, &v26);
  if ( Proxy < 0 )
  {
    if ( Proxy != -2147217406 )
    {
      v8 = -2147217398;
      goto LABEL_3;
    }
    goto LABEL_8;
  }
  v8 = CoImpersonateClient();
  if ( v8 < 0 )
  {
    v18 = 0;
    v8 = -2147217405;
LABEL_15:
    ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v26, v18);
    goto LABEL_16;
  }
  v18 = 1;
  if ( (unsigned int)ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
    v8 = SetInterfaceSecurity(v26, v15, v16, v17, v23, v24, v25);
  if ( v8 < 0 )
    goto LABEL_15;
LABEL_16:
  if ( v8 == -2147217406 )
  {
LABEL_8:
    v8 = -2147217379;
    goto LABEL_3;
  }
  if ( v8 < 0 )
    goto LABEL_3;
  v19 = v26;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v8 = ProviderSubSystem_Common_Globals::SetCloaking(v19, v21, CurrentImpersonationLevel);
  if ( v8 >= 0 )
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *const, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))v19->lpVtbl[2].AddRef)(
           v19,
           a2,
           v10,
           a4,
           a5);
  ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v26, v18);
  if ( v8 < 0 )
    goto LABEL_3;
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140027850  mov     [rsp+arg_8], rbx
0x140027855  mov     [rsp+arg_10], rbp
0x14002785a  push    rsi
0x14002785b  push    rdi
0x14002785c  push    r12
0x14002785e  push    r14
0x140027860  push    r15
0x140027862  sub     rsp, 40h
0x140027866  mov     r15, r9
0x140027869  mov     r12, rdx
0x14002786c  mov     r9, [rcx+1E8h]; struct IUnknown *
0x140027873  test    r9, r9
0x140027876  jnz     short loc_140027893
0x140027878  mov     ebx, 80041024h
0x14002787d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140027883  mov     rcx, rax
0x140027886  mov     edx, ebx
0x140027888  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002788e  jmp     loc_14002796C
0x140027893  mov     r14d, r8d
0x140027896  mov     [rsp+68h+arg_0], 0
0x14002789f  btr     r14d, 11h
0x1400278a4  lea     rbp, [rcx+230h]
0x1400278ab  cmp     dword ptr [rcx+228h], 3
0x1400278b2  lea     rax, [rsp+68h+arg_0]
0x1400278b7  mov     rcx, rbp; struct ProxyContainer *
0x1400278ba  mov     [rsp+68h+var_48], rax; unsigned int
0x1400278bf  cmovnb  r14d, r8d
0x1400278c3  lea     r8, IID_IWbemServices; struct _GUID *
0x1400278ca  xor     edx, edx; unsigned int
0x1400278cc  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@@Z; ProviderSubSystem_Common_Globals::GetProxy(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &)
0x1400278d1  test    eax, eax
0x1400278d3  jns     short loc_1400278E7
0x1400278d5  cmp     eax, 80041002h
0x1400278da  jnz     loc_1400279FD
0x1400278e0  mov     ebx, 8004101Dh
0x1400278e5  jmp     short loc_14002787D
0x1400278e7  call    cs:__imp_CoImpersonateClient
0x1400278ed  mov     ebx, eax
0x1400278ef  test    eax, eax
0x1400278f1  js      short loc_14002790E
0x1400278f3  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x1400278f8  add     eax, 0FFFFFFFDh
0x1400278fb  mov     edi, 1
0x140027900  cmp     eax, edi
0x140027902  ja      loc_1400279EC
0x140027908  test    ebx, ebx
0x14002790a  js      short loc_140027915
0x14002790c  jmp     short loc_140027927
0x14002790e  xor     edi, edi
0x140027910  mov     ebx, 80041003h
0x140027915  mov     r8, [rsp+68h+arg_0]; struct IUnknown *
0x14002791a  mov     r9d, edi; int
0x14002791d  xor     edx, edx; unsigned int
0x14002791f  mov     rcx, rbp; struct ProxyContainer *
0x140027922  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140027927  cmp     ebx, 80041002h
0x14002792d  jz      short loc_1400278E0
0x14002792f  test    ebx, ebx
0x140027931  js      loc_14002787D
0x140027937  mov     rsi, [rsp+68h+arg_0]
0x14002793c  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x140027941  mov     r8d, eax; unsigned int
0x140027944  mov     rcx, rsi; struct IUnknown *
0x140027947  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14002794c  mov     ebx, eax
0x14002794e  test    eax, eax
0x140027950  jns     short loc_1400279C0
0x140027952  mov     r8, [rsp+68h+arg_0]; struct IUnknown *
0x140027957  mov     r9d, edi; int
0x14002795a  xor     edx, edx; unsigned int
0x14002795c  mov     rcx, rbp; struct ProxyContainer *
0x14002795f  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x140027964  test    ebx, ebx
0x140027966  js      loc_14002787D
0x14002796c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027973  lea     rax, WPP_GLOBAL_Control
0x14002797a  cmp     rcx, rax
0x14002797d  jnz     short loc_14002799A
0x14002797f  lea     r11, [rsp+68h+var_28]
0x140027984  mov     eax, ebx
0x140027986  mov     rbx, [r11+38h]
0x14002798a  mov     rbp, [r11+40h]
0x14002798e  mov     rsp, r11
0x140027991  pop     r15
0x140027993  pop     r14
0x140027995  pop     r12
0x140027997  pop     rdi
0x140027998  pop     rsi
0x140027999  retn
0x14002799a  test    byte ptr [rcx+1Ch], 4
0x14002799e  jz      short loc_14002797F
0x1400279a0  cmp     byte ptr [rcx+19h], 2
0x1400279a4  jb      short loc_14002797F
0x1400279a6  mov     rcx, [rcx+10h]
0x1400279aa  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x1400279b1  mov     edx, 18h
0x1400279b6  mov     r9d, ebx
0x1400279b9  call    WPP_SF_d
0x1400279be  jmp     short loc_14002797F
0x1400279c0  mov     rax, [rsi]
0x1400279c3  mov     r9, r15
0x1400279c6  mov     rdx, [rsp+68h+arg_20]
0x1400279ce  mov     r8d, r14d
0x1400279d1  mov     [rsp+68h+var_48], rdx
0x1400279d6  mov     rcx, rsi
0x1400279d9  mov     rdx, r12
0x1400279dc  mov     rax, [rax+38h]
0x1400279e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400279e5  mov     ebx, eax
0x1400279e7  jmp     loc_140027952
0x1400279ec  mov     rcx, [rsp+68h+arg_0]; struct IUnknown *
0x1400279f1  call    ?SetInterfaceSecurity@@YAJPEAUIUnknown@@PEAG11KKK@Z; SetInterfaceSecurity(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ulong)
0x1400279f6  mov     ebx, eax
0x1400279f8  jmp     loc_140027908
0x1400279fd  mov     ebx, 8004100Ah
0x140027a02  jmp     loc_14002787D
```
