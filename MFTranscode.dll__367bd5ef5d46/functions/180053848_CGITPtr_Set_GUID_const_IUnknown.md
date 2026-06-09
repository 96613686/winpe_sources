# CGITPtr::Set(_GUID const &,IUnknown *)

- ea: `0x180053848`
- end: `0x1800539cc`
- name: `?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(CGITPtr *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021670`
- `0x18002cce0`

## callees

- `0x1800035c0`
- `0x180021128`
- `0x18004f410`
- `0x180053848`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005388c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005388c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005394e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005394e`

## pseudocode

```c
__int64 __fastcall CGITPtr::Set(CGITPtr *this, const struct _GUID *a2, struct IUnknown *a3)
{
  HRESULT Instance; // ebx
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax

  Instance = 0;
  if ( CGITPtr::s_pGIT
    || (Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &CGITPtr::s_pGIT),
        Instance >= 0) )
  {
    CGITPtr::Release(this);
    if ( a3 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, GUID *, CGITPtr *))(*(_QWORD *)CGITPtr::s_pGIT
                                                                                         + 24LL))(
                   CGITPtr::s_pGIT,
                   a3,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   this);
      if ( Instance < 0 )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
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
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
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
0x180053848  mov     [rsp+arg_0], rbx
0x18005384d  mov     [rsp+arg_8], rsi
0x180053852  push    rdi
0x180053853  sub     rsp, 30h
0x180053857  xor     ebx, ebx
0x180053859  mov     rdi, r8
0x18005385c  cmp     cs:?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA, rbx; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180053863  mov     rsi, rcx
0x180053866  jnz     loc_18005390B
0x18005386c  lea     rax, ?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180053873  xor     edx, edx; pUnkOuter
0x180053875  lea     r9, IID_IGlobalInterfaceTable; riid
0x18005387c  mov     [rsp+38h+ppv], rax; ppv
0x180053881  lea     r8d, [rbx+1]; dwClsContext
0x180053885  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18005388c  call    cs:__imp_CoCreateInstance
0x180053892  mov     ebx, eax
0x180053894  test    eax, eax
0x180053896  jns     short loc_18005390B
0x180053898  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005389f  test    rcx, rcx
0x1800538a2  jnz     short loc_1800538E5
0x1800538a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800538aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538b1  mov     rcx, rax
0x1800538b4  test    rax, rax
0x1800538b7  jz      short loc_1800538D7
0x1800538b9  mov     rax, [rax]
0x1800538bc  mov     edx, 7F0h
0x1800538c1  mov     rax, [rax+8]
0x1800538c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538ca  test    eax, eax
0x1800538cc  jz      short loc_1800538D7
0x1800538ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538d5  jmp     short loc_1800538E5
0x1800538d7  lea     rcx, qword_180069A90; this
0x1800538de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538e5  cmp     byte ptr [rcx+8], 0
0x1800538e9  jz      loc_1800539BA
0x1800538ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800538f4  cmp     [rax+7CCh], ebx
0x1800538fa  jz      loc_1800539BA
0x180053900  mov     r8d, 24h ; '$'
0x180053906  jmp     loc_1800539A8
0x18005390b  mov     rcx, rsi; this
0x18005390e  call    ?Release@CGITPtr@@QEAAXXZ; CGITPtr::Release(void)
0x180053913  test    rdi, rdi
0x180053916  jz      loc_1800539BA
0x18005391c  mov     rcx, cs:?s_pGIT@CGITPtr@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * CGITPtr::s_pGIT
0x180053923  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18005392a  mov     r9, rsi
0x18005392d  mov     rdx, rdi
0x180053930  mov     rax, [rcx]
0x180053933  mov     rax, [rax+18h]
0x180053937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005393c  mov     ebx, eax
0x18005393e  test    eax, eax
0x180053940  jns     short loc_1800539BA
0x180053942  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053949  test    rcx, rcx
0x18005394c  jnz     short loc_18005398F
0x18005394e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053954  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005395b  mov     rcx, rax
0x18005395e  test    rax, rax
0x180053961  jz      short loc_180053981
0x180053963  mov     rax, [rax]
0x180053966  mov     edx, 7F0h
0x18005396b  mov     rax, [rax+8]
0x18005396f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053974  test    eax, eax
0x180053976  jz      short loc_180053981
0x180053978  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005397f  jmp     short loc_18005398F
0x180053981  lea     rcx, qword_180069A90; this
0x180053988  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005398f  cmp     byte ptr [rcx+8], 0
0x180053993  jz      short loc_1800539BA
0x180053995  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005399a  cmp     [rax+7CCh], ebx
0x1800539a0  jz      short loc_1800539BA
0x1800539a2  mov     r8d, 2Ch ; ','; int
0x1800539a8  mov     r9d, ebx; int
0x1800539ab  lea     rdx, aCgitptrSet; "CGITPtr::Set"
0x1800539b2  mov     rcx, rax; this
0x1800539b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800539ba  mov     rsi, [rsp+38h+arg_8]
0x1800539bf  mov     eax, ebx
0x1800539c1  mov     rbx, [rsp+38h+arg_0]
0x1800539c6  add     rsp, 30h
0x1800539ca  pop     rdi
0x1800539cb  retn
```
