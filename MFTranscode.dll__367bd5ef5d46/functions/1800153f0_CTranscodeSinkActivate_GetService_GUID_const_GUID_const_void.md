# CTranscodeSinkActivate::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800153f0`
- end: `0x180015615`
- name: `?GetService@CTranscodeSinkActivate@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(CTranscodeSinkActivate *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800153f0`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015556`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015556`
- `MFPlat!CreatePropertyStore` at `0x18001553a`
- `MFPlat!CreatePropertyStore` at `0x18001553a`

## string_xrefs

- `0x180015402`: `CTranscodeSinkActivate::GetService`
- `0x18001548d`: `CTranscodeSinkActivate::GetService`
- `0x1800155ad`: `CTranscodeSinkActivate::GetService`

## pseudocode

```c
__int64 __fastcall CTranscodeSinkActivate::GetService(
        CTranscodeSinkActivate *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        IPropertyStore **a4)
{
  __int64 v8; // rdx
  __int64 *v9; // rcx
  HRESULT PropertyStore; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  char *v17; // rbp
  IPropertyStore **v18; // rdi
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v24; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "CTranscodeSinkActivate::GetService", 593);
  if ( a4 )
  {
    *a4 = 0;
    v15 = *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&MF_PROPERTY_HANDLER_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
      v15 = *(_QWORD *)MF_PROPERTY_HANDLER_SERVICE.Data4 - *(_QWORD *)a2->Data4;
    if ( v15 )
    {
      PropertyStore = -1072875846;
      goto LABEL_35;
    }
    v16 = *(_QWORD *)&IID_IPropertyStore.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&IID_IPropertyStore.Data1 == *(_QWORD *)&a3->Data1 )
      v16 = *(_QWORD *)IID_IPropertyStore.Data4 - *(_QWORD *)a3->Data4;
    if ( v16 )
    {
      PropertyStore = -2147467262;
      goto LABEL_35;
    }
    v17 = (char *)this - 80;
    PropertyStore = 0;
    v18 = (IPropertyStore **)((char *)this + 72);
    if ( *((_QWORD *)v17 + 19) || (PropertyStore = CreatePropertyStore(v18), PropertyStore >= 0) )
    {
      *a4 = *v18;
      if ( *v18 )
        ((void (__fastcall *)(IPropertyStore *))(*v18)->lpVtbl->AddRef)(*v18);
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != PropertyStore )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeSinkActivate::GetService",
            606,
            PropertyStore);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 92;
        v13 = v17;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    PropertyStore = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v12 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v12, "CTranscodeSinkActivate::GetService", 597, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = (char *)this - 80;
      v14 = 91;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids,
        v13,
        PropertyStore);
    }
  }
LABEL_35:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return (unsigned int)PropertyStore;
}

```

## disassembly

```asm
0x1800153f0  push    rbx
0x1800153f2  push    rbp
0x1800153f3  push    rsi
0x1800153f4  push    rdi
0x1800153f5  sub     rsp, 38h
0x1800153f9  mov     rbp, r8
0x1800153fc  mov     rbx, rdx
0x1800153ff  mov     rdi, rcx
0x180015402  lea     rdx, aCtranscodesink_9; "CTranscodeSinkActivate::GetService"
0x180015409  mov     r8d, 251h; int
0x18001540f  lea     rcx, [rsp+58h+arg_0]; this
0x180015414  mov     rsi, r9
0x180015417  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001541c  test    rsi, rsi
0x18001541f  jnz     loc_1800154D8
0x180015425  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001542c  mov     ebx, 80070057h
0x180015431  test    rcx, rcx
0x180015434  jnz     short loc_180015477
0x180015436  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001543c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015443  mov     rcx, rax
0x180015446  test    rax, rax
0x180015449  jz      short loc_180015469
0x18001544b  mov     rax, [rax]
0x18001544e  mov     edx, 7F0h
0x180015453  mov     rax, [rax+8]
0x180015457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001545c  test    eax, eax
0x18001545e  jz      short loc_180015469
0x180015460  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015467  jmp     short loc_180015477
0x180015469  lea     rcx, qword_180069A90; this
0x180015470  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015477  cmp     byte ptr [rcx+8], 0
0x18001547b  jz      short loc_1800154A2
0x18001547d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015482  cmp     [rax+7CCh], ebx
0x180015488  jz      short loc_1800154A2
0x18001548a  mov     r9d, ebx; int
0x18001548d  lea     rdx, aCtranscodesink_9; "CTranscodeSinkActivate::GetService"
0x180015494  mov     r8d, 255h; int
0x18001549a  mov     rcx, rax; this
0x18001549d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800154a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800154a7  cmp     al, 1
0x1800154a9  jb      loc_180015600
0x1800154af  lea     r9, [rdi-50h]
0x1800154b3  mov     edx, 5Bh ; '['
0x1800154b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154bf  lea     r8, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids
0x1800154c6  mov     [rsp+58h+var_38], ebx
0x1800154ca  mov     rcx, [rcx+10h]
0x1800154ce  call    WPP_SF_qd
0x1800154d3  jmp     loc_180015600
0x1800154d8  mov     qword ptr [rsi], 0
0x1800154df  mov     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data1
0x1800154e6  sub     rax, [rbx]
0x1800154e9  jnz     short loc_1800154F6
0x1800154eb  mov     rax, qword ptr cs:MF_PROPERTY_HANDLER_SERVICE.Data4
0x1800154f2  sub     rax, [rbx+8]
0x1800154f6  test    rax, rax
0x1800154f9  jnz     loc_1800155FB
0x1800154ff  mov     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180015506  sub     rax, [rbp+0]
0x18001550a  jnz     short loc_180015517
0x18001550c  mov     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180015513  sub     rax, [rbp+8]
0x180015517  test    rax, rax
0x18001551a  jnz     loc_1800155F4
0x180015520  lea     rbp, [rdi-50h]
0x180015524  xor     ebx, ebx
0x180015526  add     rdi, 48h ; 'H'
0x18001552a  cmp     [rbp+98h], rbx
0x180015531  jnz     loc_1800155D8
0x180015537  mov     rcx, rdi; ppStore
0x18001553a  call    cs:__imp_CreatePropertyStore
0x180015540  mov     ebx, eax
0x180015542  test    eax, eax
0x180015544  jns     loc_1800155D8
0x18001554a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015551  test    rcx, rcx
0x180015554  jnz     short loc_180015597
0x180015556  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001555c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015563  mov     rcx, rax
0x180015566  test    rax, rax
0x180015569  jz      short loc_180015589
0x18001556b  mov     rax, [rax]
0x18001556e  mov     edx, 7F0h
0x180015573  mov     rax, [rax+8]
0x180015577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001557c  test    eax, eax
0x18001557e  jz      short loc_180015589
0x180015580  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015587  jmp     short loc_180015597
0x180015589  lea     rcx, qword_180069A90; this
0x180015590  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015597  cmp     byte ptr [rcx+8], 0
0x18001559b  jz      short loc_1800155C2
0x18001559d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800155a2  cmp     [rax+7CCh], ebx
0x1800155a8  jz      short loc_1800155C2
0x1800155aa  mov     r9d, ebx; int
0x1800155ad  lea     rdx, aCtranscodesink_9; "CTranscodeSinkActivate::GetService"
0x1800155b4  mov     r8d, 25Eh; int
0x1800155ba  mov     rcx, rax; this
0x1800155bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800155c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800155c7  cmp     al, 1
0x1800155c9  jb      short loc_180015600
0x1800155cb  mov     edx, 5Ch ; '\'
0x1800155d0  mov     r9, rbp
0x1800155d3  jmp     loc_1800154B8
0x1800155d8  mov     rax, [rdi]
0x1800155db  mov     [rsi], rax
0x1800155de  mov     rcx, [rdi]
0x1800155e1  test    rcx, rcx
0x1800155e4  jz      short loc_180015600
0x1800155e6  mov     rax, [rcx]
0x1800155e9  mov     rax, [rax+8]
0x1800155ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f2  jmp     short loc_180015600
0x1800155f4  mov     ebx, 80004002h
0x1800155f9  jmp     short loc_180015600
0x1800155fb  mov     ebx, 0C00D36BAh
0x180015600  lea     rcx, [rsp+58h+arg_0]; this
0x180015605  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001560a  mov     eax, ebx
0x18001560c  add     rsp, 38h
0x180015610  pop     rdi
0x180015611  pop     rsi
0x180015612  pop     rbp
0x180015613  pop     rbx
0x180015614  retn
```
