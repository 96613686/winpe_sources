# ProviderSubSystem_Globals::BeginThreadImpersonation(IUnknown * &,IServerSecurity * &,int &)

- ea: `0x1400217c8`
- end: `0x140021968`
- name: `?BeginThreadImpersonation@ProviderSubSystem_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAH@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct IUnknown **ppInterface, struct IServerSecurity **, int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020e40`
- `0x140020fc0`
- `0x140021130`
- `0x1400212a0`
- `0x14002145c`
- `0x140021520`
- `0x14003d0c0`

## callees

- `0x1400217c8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `FastProx!?AddRef@CWbemCallSecurity@@UEAAKXZ` at `0x14002189d`
- `FastProx!?AddRef@CWbemCallSecurity@@UEAAKXZ` at `0x14002189d`
- `FastProx!?GetThreadSecurity@CWbemCallSecurity@@UEAAJW4tag_WMI_THREAD_SECURITY_ORIGIN@@PEAPEAU_IWmiThreadSecHandle@@@Z` at `0x1400218ba`
- `FastProx!?GetThreadSecurity@CWbemCallSecurity@@UEAAJW4tag_WMI_THREAD_SECURITY_ORIGIN@@PEAPEAU_IWmiThreadSecHandle@@@Z` at `0x1400218ba`
- `FastProx!?Release@CWbemCallSecurity@@UEAAKXZ` at `0x14002190d`
- `FastProx!?Release@CWbemCallSecurity@@UEAAKXZ` at `0x14002190d`
- `FastProx!?SetThreadSecurity@CWbemCallSecurity@@UEAAJPEAU_IWmiThreadSecHandle@@@Z` at `0x1400218cf`
- `FastProx!?SetThreadSecurity@CWbemCallSecurity@@UEAAJPEAU_IWmiThreadSecHandle@@@Z` at `0x1400218cf`
- `FastProx!?QueryInterface@CWbemCallSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1400218e8`
- `FastProx!?QueryInterface@CWbemCallSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x1400218e8`
- `FastProx!?New@CWbemCallSecurity@@SAPEAV1@XZ` at `0x14002183c`
- `FastProx!?New@CWbemCallSecurity@@SAPEAV1@XZ` at `0x14002183c`
- `wbemcomn!GetMemLogObject` at `0x14002192b`
- `wbemcomn!GetMemLogObject` at `0x14002192b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021936`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140021936`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400217fd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400217fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProviderSubSystem_Globals::BeginThreadImpersonation(
        struct IUnknown **ppInterface,
        struct IServerSecurity **a2,
        int *a3)
{
  HRESULT ThreadSecurity; // ebx
  CWbemCallSecurity *v7; // rax
  CWbemCallSecurity *v8; // rdi
  CMemoryLog *MemLogObject; // rax
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF
  struct _IWmiThreadSecHandle *v12; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v11 = 0;
  ThreadSecurity = CoGetCallContext(&IID_IUnknown, (void **)ppInterface);
  if ( ThreadSecurity >= 0 )
  {
    ThreadSecurity = ((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))(*ppInterface)->lpVtbl->QueryInterface)(
                       *ppInterface,
                       &IID_IServerSecurity,
                       &v11);
    if ( ThreadSecurity >= 0 )
      *a3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v11);
  }
  v7 = (CWbemCallSecurity *)CWbemCallSecurity::New();
  v8 = v7;
  if ( v7 )
  {
    CWbemCallSecurity::AddRef(v7);
    v12 = 0;
    ThreadSecurity = CWbemCallSecurity::GetThreadSecurity((char *)v8 + 8, 2, &v12);
    if ( ThreadSecurity >= 0 )
    {
      ThreadSecurity = CWbemCallSecurity::SetThreadSecurity((CWbemCallSecurity *)((char *)v8 + 8), v12);
      if ( ThreadSecurity >= 0 )
      {
        ThreadSecurity = CWbemCallSecurity::QueryInterface(v8, &IID_IServerSecurity, (void **)a2);
        if ( ThreadSecurity >= 0 )
        {
          if ( *a3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
        }
      }
      (*(void (__fastcall **)(struct _IWmiThreadSecHandle *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    CWbemCallSecurity::Release(v8);
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( ThreadSecurity < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, ThreadSecurity);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_3058338b7eb536807a3546f9e85809ac_Traceguids,
      (unsigned int)ThreadSecurity);
  }
  return (unsigned int)ThreadSecurity;
}

```

## disassembly

```asm
0x1400217c8  mov     [rsp+arg_0], rbx
0x1400217cd  mov     [rsp+arg_8], rbp
0x1400217d2  push    rsi
0x1400217d3  push    rdi
0x1400217d4  push    r14
0x1400217d6  sub     rsp, 20h
0x1400217da  mov     r14, rdx
0x1400217dd  mov     dword ptr [r8], 0
0x1400217e4  mov     rdx, rcx; ppInterface
0x1400217e7  mov     [rsp+38h+arg_10], 0
0x1400217f0  mov     rdi, rcx
0x1400217f3  mov     rsi, r8
0x1400217f6  lea     rcx, IID_IUnknown; riid
0x1400217fd  call    cs:__imp_CoGetCallContext
0x140021803  mov     ebx, eax
0x140021805  test    eax, eax
0x140021807  js      short loc_14002183C
0x140021809  mov     rcx, [rdi]
0x14002180c  lea     r8, [rsp+38h+arg_10]
0x140021811  lea     rdx, IID_IServerSecurity
0x140021818  mov     rax, [rcx]
0x14002181b  mov     rax, [rax]
0x14002181e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021823  mov     ebx, eax
0x140021825  test    eax, eax
0x140021827  js      short loc_14002183C
0x140021829  mov     rcx, [rsp+38h+arg_10]
0x14002182e  mov     rax, [rcx]
0x140021831  mov     rax, [rax+30h]
0x140021835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002183a  mov     [rsi], eax
0x14002183c  call    cs:__imp_?New@CWbemCallSecurity@@SAPEAV1@XZ; CWbemCallSecurity::New(void)
0x140021842  mov     rdi, rax
0x140021845  test    rax, rax
0x140021848  jnz     short loc_14002189A
0x14002184a  mov     rcx, [rsp+38h+arg_10]
0x14002184f  test    rcx, rcx
0x140021852  jz      short loc_140021860
0x140021854  mov     rax, [rcx]
0x140021857  mov     rax, [rax+10h]
0x14002185b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021860  test    ebx, ebx
0x140021862  js      loc_14002192B
0x140021868  mov     rcx, cs:WPP_GLOBAL_Control
0x14002186f  lea     rax, WPP_GLOBAL_Control
0x140021876  cmp     rcx, rax
0x140021879  jz      short loc_140021885
0x14002187b  test    byte ptr [rcx+1Ch], 4
0x14002187f  jnz     loc_140021941
0x140021885  mov     rbp, [rsp+38h+arg_8]
0x14002188a  mov     eax, ebx
0x14002188c  mov     rbx, [rsp+38h+arg_0]
0x140021891  add     rsp, 20h
0x140021895  pop     r14
0x140021897  pop     rdi
0x140021898  pop     rsi
0x140021899  retn
0x14002189a  mov     rcx, rdi
0x14002189d  call    cs:__imp_?AddRef@CWbemCallSecurity@@UEAAKXZ; CWbemCallSecurity::AddRef(void)
0x1400218a3  lea     r8, [rsp+38h+arg_18]
0x1400218a8  mov     [rsp+38h+arg_18], 0
0x1400218b1  mov     edx, 2
0x1400218b6  lea     rcx, [rdi+8]
0x1400218ba  call    cs:__imp_?GetThreadSecurity@CWbemCallSecurity@@UEAAJW4tag_WMI_THREAD_SECURITY_ORIGIN@@PEAPEAU_IWmiThreadSecHandle@@@Z; CWbemCallSecurity::GetThreadSecurity(tag_WMI_THREAD_SECURITY_ORIGIN,_IWmiThreadSecHandle * *)
0x1400218c0  mov     ebx, eax
0x1400218c2  test    eax, eax
0x1400218c4  js      short loc_14002190A
0x1400218c6  mov     rdx, [rsp+38h+arg_18]
0x1400218cb  lea     rcx, [rdi+8]
0x1400218cf  call    cs:__imp_?SetThreadSecurity@CWbemCallSecurity@@UEAAJPEAU_IWmiThreadSecHandle@@@Z; CWbemCallSecurity::SetThreadSecurity(_IWmiThreadSecHandle *)
0x1400218d5  mov     ebx, eax
0x1400218d7  test    eax, eax
0x1400218d9  js      short loc_1400218F9
0x1400218db  mov     r8, r14
0x1400218de  lea     rdx, IID_IServerSecurity
0x1400218e5  mov     rcx, rdi
0x1400218e8  call    cs:__imp_?QueryInterface@CWbemCallSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWbemCallSecurity::QueryInterface(_GUID const &,void * *)
0x1400218ee  mov     ebx, eax
0x1400218f0  test    eax, eax
0x1400218f2  js      short loc_1400218F9
0x1400218f4  cmp     dword ptr [rsi], 0
0x1400218f7  jnz     short loc_140021918
0x1400218f9  mov     rcx, [rsp+38h+arg_18]
0x1400218fe  mov     rax, [rcx]
0x140021901  mov     rax, [rax+10h]
0x140021905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002190a  mov     rcx, rdi
0x14002190d  call    cs:__imp_?Release@CWbemCallSecurity@@UEAAKXZ; CWbemCallSecurity::Release(void)
0x140021913  jmp     loc_14002184A
0x140021918  mov     rcx, [rsp+38h+arg_10]
0x14002191d  mov     rax, [rcx]
0x140021920  mov     rax, [rax+28h]
0x140021924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021929  jmp     short loc_1400218F9
0x14002192b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140021931  mov     rcx, rax
0x140021934  mov     edx, ebx
0x140021936  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002193c  jmp     loc_140021868
0x140021941  cmp     byte ptr [rcx+19h], 2
0x140021945  jb      loc_140021885
0x14002194b  mov     rcx, [rcx+10h]
0x14002194f  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x140021956  mov     edx, 15h
0x14002195b  mov     r9d, ebx
0x14002195e  call    WPP_SF_d
0x140021963  jmp     loc_140021885
```
