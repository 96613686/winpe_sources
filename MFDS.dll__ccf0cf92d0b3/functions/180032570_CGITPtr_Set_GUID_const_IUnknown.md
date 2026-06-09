# CGITPtr::Set(_GUID const &,IUnknown *)

- ea: `0x180032570`
- end: `0x1800326f9`
- name: `?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(CGITPtr *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030060`
- `0x180034d1c`
- `0x180070f50`
- `0x180071480`
- `0x1800802fc`
- `0x180089178`
- `0x18008a0b0`
- `0x180097eb0`

## callees

- `0x1800140b0`
- `0x180032570`
- `0x180032a50`
- `0x180032adc`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800325b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800325b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800325cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003267b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800325cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003267b`

## pseudocode

```c
__int64 __fastcall CGITPtr::Set(CGITPtr *this, const struct _GUID *a2, struct IUnknown *a3)
{
  HRESULT Instance; // ebx
  CallStackTracing *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax

  Instance = 0;
  if ( CGITPtr::s_pGIT
    || (Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &CGITPtr::s_pGIT),
        Instance >= 0) )
  {
    CGITPtr::Release(this);
    if ( a3 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, const struct _GUID *, CGITPtr *))(*(_QWORD *)CGITPtr::s_pGIT + 24LL))(
                   CGITPtr::s_pGIT,
                   a3,
                   a2,
                   this);
      if ( Instance < 0 )
      {
        v11 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
          {
            v10 = 44;
            goto LABEL_21;
          }
        }
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
      {
        v10 = 36;
LABEL_21:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CGITPtr::Set", v10, Instance);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032570  push    rbx
0x180032572  push    rbp
0x180032573  push    rsi
0x180032574  push    rdi
0x180032575  sub     rsp, 38h
0x180032579  xor     ebx, ebx
0x18003257b  mov     rdi, r8
0x18003257e  cmp     cs:?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA, rbx; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180032585  mov     rbp, rdx
0x180032588  mov     rsi, rcx
0x18003258b  jnz     loc_18003263C
0x180032591  lea     rax, ?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180032598  xor     edx, edx; pUnkOuter
0x18003259a  lea     r9, IID_IGlobalInterfaceTable; riid
0x1800325a1  mov     [rsp+58h+ppv], rax; ppv
0x1800325a6  lea     r8d, [rbx+1]; dwClsContext
0x1800325aa  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800325b1  call    cs:__imp_CoCreateInstance
0x1800325b8  nop     dword ptr [rax+rax+00h]
0x1800325bd  mov     ebx, eax
0x1800325bf  test    eax, eax
0x1800325c1  jns     short loc_18003263C
0x1800325c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800325ca  test    rcx, rcx
0x1800325cd  jnz     short loc_180032616
0x1800325cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800325d6  nop     dword ptr [rax+rax+00h]
0x1800325db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800325e2  mov     rcx, rax
0x1800325e5  test    rax, rax
0x1800325e8  jz      short loc_180032608
0x1800325ea  mov     rax, [rax]
0x1800325ed  mov     edx, 7F0h
0x1800325f2  mov     rax, [rax+8]
0x1800325f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325fb  test    eax, eax
0x1800325fd  jz      short loc_180032608
0x1800325ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032606  jmp     short loc_180032616
0x180032608  lea     rcx, qword_1800EB130; this
0x18003260f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032616  cmp     byte ptr [rcx+8], 0
0x18003261a  jz      loc_1800326ED
0x180032620  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032625  cmp     [rax+7CCh], ebx
0x18003262b  jz      loc_1800326ED
0x180032631  mov     r8d, 24h ; '$'
0x180032637  jmp     loc_1800326DB
0x18003263c  mov     rcx, rsi; this
0x18003263f  call    ?Release@CGITPtr@@QEAAXXZ; CGITPtr::Release(void)
0x180032644  test    rdi, rdi
0x180032647  jz      loc_1800326ED
0x18003264d  mov     rcx, cs:?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180032654  mov     r9, rsi
0x180032657  mov     r8, rbp
0x18003265a  mov     rdx, rdi
0x18003265d  mov     rax, [rcx]
0x180032660  mov     rax, [rax+18h]
0x180032664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032669  mov     ebx, eax
0x18003266b  test    eax, eax
0x18003266d  jns     short loc_1800326ED
0x18003266f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032676  test    rcx, rcx
0x180032679  jnz     short loc_1800326C2
0x18003267b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032682  nop     dword ptr [rax+rax+00h]
0x180032687  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003268e  mov     rcx, rax
0x180032691  test    rax, rax
0x180032694  jz      short loc_1800326B4
0x180032696  mov     rax, [rax]
0x180032699  mov     edx, 7F0h
0x18003269e  mov     rax, [rax+8]
0x1800326a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326a7  test    eax, eax
0x1800326a9  jz      short loc_1800326B4
0x1800326ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800326b2  jmp     short loc_1800326C2
0x1800326b4  lea     rcx, qword_1800EB130; this
0x1800326bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800326c2  cmp     byte ptr [rcx+8], 0
0x1800326c6  jz      short loc_1800326ED
0x1800326c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800326cd  cmp     [rax+7CCh], ebx
0x1800326d3  jz      short loc_1800326ED
0x1800326d5  mov     r8d, 2Ch ; ','; int
0x1800326db  mov     r9d, ebx; int
0x1800326de  lea     rdx, aCgitptrSet; "CGITPtr::Set"
0x1800326e5  mov     rcx, rax; this
0x1800326e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800326ed  mov     eax, ebx
0x1800326ef  add     rsp, 38h
0x1800326f3  pop     rdi
0x1800326f4  pop     rsi
0x1800326f5  pop     rbp
0x1800326f6  pop     rbx
0x1800326f7  retn
```
