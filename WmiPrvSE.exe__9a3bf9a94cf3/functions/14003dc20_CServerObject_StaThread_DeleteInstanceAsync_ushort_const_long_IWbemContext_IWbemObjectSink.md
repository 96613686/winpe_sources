# CServerObject_StaThread::DeleteInstanceAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14003dc20`
- end: `0x14003dd72`
- name: `?DeleteInstanceAsync@CServerObject_StaThread@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CServerObject_StaThread *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x1400234b8`
- `0x14003dc20`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14003dd0f`
- `wbemcomn!GetMemLogObject` at `0x14003dd0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003dd1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14003dd1a`

## pseudocode

```c
__int64 __fastcall CServerObject_StaThread::DeleteInstanceAsync(
        CServerObject_StaThread *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IUnknown *v7; // r9
  int v10; // ebx
  struct ProxyContainer *v11; // rsi
  int v12; // eax
  struct IUnknown *v13; // r14
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v15; // edx
  __int64 v16; // r8
  CMemoryLog *MemLogObject; // rax
  struct IUnknown *v19; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF

  v7 = (struct IUnknown *)*((_QWORD *)this + 61);
  v10 = -2147217372;
  if ( !v7 )
    goto LABEL_10;
  v20 = 0;
  v11 = (CServerObject_StaThread *)((char *)this + 560);
  v19 = 0;
  v12 = ProviderSubSystem_Common_Globals::SetProxyState(
          (CServerObject_StaThread *)((char *)this + 560),
          0,
          &IID_IWbemServices,
          v7,
          &v19,
          &v20);
  v10 = v12;
  if ( v12 == -2147217406 )
  {
    v10 = -2147217379;
LABEL_10:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
    goto LABEL_11;
  }
  if ( v12 < 0 )
    goto LABEL_10;
  v13 = v19;
  CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
  v10 = ProviderSubSystem_Common_Globals::SetCloaking(v13, v15, CurrentImpersonationLevel);
  if ( v10 >= 0 )
  {
    v16 = a3;
    LODWORD(v16) = a3 & 0xFFFDFFFF;
    if ( *((_DWORD *)this + 138) >= 3u )
      v16 = a3;
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *const, __int64, struct IWbemContext *, struct IWbemObjectSink *))v13->lpVtbl[5].Release)(
            v13,
            a2,
            v16,
            a4,
            a5);
  }
  ProviderSubSystem_Common_Globals::RevertProxyState(v11, 0, v19, v20);
  if ( v10 < 0 )
    goto LABEL_10;
LABEL_11:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003dc20  mov     r11, rsp
0x14003dc23  mov     [r11+10h], rbx
0x14003dc27  mov     [r11+18h], rbp
0x14003dc2b  push    rsi
0x14003dc2c  push    rdi
0x14003dc2d  push    r12
0x14003dc2f  push    r14
0x14003dc31  push    r15
0x14003dc33  sub     rsp, 40h
0x14003dc37  mov     r15, r9
0x14003dc3a  mov     ebp, r8d
0x14003dc3d  mov     r9, [rcx+1E8h]; struct IUnknown *
0x14003dc44  mov     r12, rdx
0x14003dc47  mov     rdi, rcx
0x14003dc4a  mov     ebx, 80041024h
0x14003dc4f  test    r9, r9
0x14003dc52  jz      loc_14003DD0F
0x14003dc58  lea     rax, [r11+8]
0x14003dc5c  mov     [rsp+68h+arg_0], 0
0x14003dc64  mov     [r11-40h], rax
0x14003dc68  lea     rsi, [rcx+230h]
0x14003dc6f  lea     rax, [r11-38h]
0x14003dc73  mov     qword ptr [r11-38h], 0
0x14003dc7b  lea     r8, IID_IWbemServices; struct _GUID *
0x14003dc82  mov     [r11-48h], rax
0x14003dc86  xor     edx, edx; unsigned int
0x14003dc88  mov     rcx, rsi; struct ProxyContainer *
0x14003dc8b  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14003dc90  mov     ebx, eax
0x14003dc92  cmp     eax, 80041002h
0x14003dc97  jnz     short loc_14003DC9E
0x14003dc99  lea     ebx, [rax+1Bh]
0x14003dc9c  jmp     short loc_14003DD0F
0x14003dc9e  test    eax, eax
0x14003dca0  js      short loc_14003DD0F
0x14003dca2  mov     r14, [rsp+68h+var_38]
0x14003dca7  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14003dcac  mov     r8d, eax; unsigned int
0x14003dcaf  mov     rcx, r14; struct IUnknown *
0x14003dcb2  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14003dcb7  mov     ebx, eax
0x14003dcb9  test    eax, eax
0x14003dcbb  js      short loc_14003DCF7
0x14003dcbd  mov     rax, [r14]
0x14003dcc0  mov     r8d, ebp
0x14003dcc3  mov     rdx, [rsp+68h+arg_20]
0x14003dccb  btr     r8d, 11h
0x14003dcd0  cmp     dword ptr [rdi+228h], 3
0x14003dcd7  mov     r9, r15
0x14003dcda  mov     [rsp+68h+var_48], rdx
0x14003dcdf  mov     rcx, r14
0x14003dce2  mov     rax, [rax+88h]
0x14003dce9  cmovnb  r8d, ebp
0x14003dced  mov     rdx, r12
0x14003dcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dcf5  mov     ebx, eax
0x14003dcf7  mov     r9d, [rsp+68h+arg_0]; int
0x14003dcfc  xor     edx, edx; unsigned int
0x14003dcfe  mov     r8, [rsp+68h+var_38]; struct IUnknown *
0x14003dd03  mov     rcx, rsi; struct ProxyContainer *
0x14003dd06  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14003dd0b  test    ebx, ebx
0x14003dd0d  jns     short loc_14003DD20
0x14003dd0f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14003dd15  mov     rcx, rax
0x14003dd18  mov     edx, ebx
0x14003dd1a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14003dd20  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dd27  lea     rax, WPP_GLOBAL_Control
0x14003dd2e  cmp     rcx, rax
0x14003dd31  jz      short loc_14003DD57
0x14003dd33  test    byte ptr [rcx+1Ch], 4
0x14003dd37  jz      short loc_14003DD57
0x14003dd39  cmp     byte ptr [rcx+19h], 2
0x14003dd3d  jb      short loc_14003DD57
0x14003dd3f  mov     rcx, [rcx+10h]
0x14003dd43  lea     r8, WPP_d3ea76c96a8339db06b7a6ae92e79012_Traceguids
0x14003dd4a  mov     edx, 22h ; '"'
0x14003dd4f  mov     r9d, ebx
0x14003dd52  call    WPP_SF_d
0x14003dd57  lea     r11, [rsp+68h+var_28]
0x14003dd5c  mov     eax, ebx
0x14003dd5e  mov     rbx, [r11+38h]
0x14003dd62  mov     rbp, [r11+40h]
0x14003dd66  mov     rsp, r11
0x14003dd69  pop     r15
0x14003dd6b  pop     r14
0x14003dd6d  pop     r12
0x14003dd6f  pop     rdi
0x14003dd70  pop     rsi
0x14003dd71  retn
```
