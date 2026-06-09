# CTranscodeDestination::GetStreamSinkIdByMajorType(_GUID const &,int *,ulong *)

- ea: `0x180043440`
- end: `0x180043661`
- name: `?GetStreamSinkIdByMajorType@CTranscodeDestination@@UEAAJAEBU_GUID@@PEAHPEAK@Z`
- size: `545`
- prototype: `__int64 __fastcall(CTranscodeDestination *__hidden this, const struct _GUID *, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180043440`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800434a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800435a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800434a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800435a9`

## string_xrefs

- `0x18004345c`: `CTranscodeDestination::GetStreamSinkIdByMajorType`
- `0x1800434f9`: `CTranscodeDestination::GetStreamSinkIdByMajorType`
- `0x180043600`: `CTranscodeDestination::GetStreamSinkIdByMajorType`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::GetStreamSinkIdByMajorType(
        CTranscodeDestination *this,
        const struct _GUID *a2,
        int *a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 *v9; // rcx
  unsigned int v10; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  char v21; // [rsp+50h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v21,
    "CTranscodeDestination::GetStreamSinkIdByMajorType",
    165);
  *a3 = 0;
  *a4 = 0;
  v8 = *((_QWORD *)this + 8);
  if ( !v8 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    v10 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeDestination::GetStreamSinkIdByMajorType",
          171,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 21;
LABEL_33:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v10);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v10 = 0;
  v14 = *(_QWORD *)&MFMediaType_Audio.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MFMediaType_Audio.Data1 == *(_QWORD *)&a2->Data1 )
    v14 = *(_QWORD *)MFMediaType_Audio.Data4 - *(_QWORD *)a2->Data4;
  if ( !v14 )
  {
    if ( !*(_QWORD *)(v8 + 24) )
      goto LABEL_34;
    *a3 = 1;
    v15 = *(_DWORD *)(*((_QWORD *)this + 8) + 16LL);
LABEL_17:
    *a4 = v15;
    goto LABEL_34;
  }
  v16 = *(_QWORD *)&MFMediaType_Video.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MFMediaType_Video.Data1 == *(_QWORD *)&a2->Data1 )
    v16 = *(_QWORD *)MFMediaType_Video.Data4 - *(_QWORD *)a2->Data4;
  if ( !v16 )
  {
    if ( !*(_QWORD *)(v8 + 8) )
      goto LABEL_34;
    *a3 = 1;
    v15 = **((_DWORD **)this + 8);
    goto LABEL_17;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  v10 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v19, "CTranscodeDestination::GetStreamSinkIdByMajorType", 194, -2147024809);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v13 = 22;
    goto LABEL_33;
  }
LABEL_34:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return v10;
}

```

## disassembly

```asm
0x180043440  mov     [rsp+arg_8], rbx
0x180043445  mov     [rsp+arg_10], rsi
0x18004344a  push    rdi
0x18004344b  push    r14
0x18004344d  push    r15
0x18004344f  sub     rsp, 30h
0x180043453  mov     r15, r8
0x180043456  mov     rdi, rdx
0x180043459  mov     rsi, rcx
0x18004345c  lea     rdx, aCtranscodedest_10; "CTranscodeDestination::GetStreamSinkIdB"...
0x180043463  mov     r8d, 0A5h; int
0x180043469  lea     rcx, [rsp+48h+arg_0]; this
0x18004346e  mov     r14, r9
0x180043471  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180043476  mov     dword ptr [r15], 0
0x18004347d  mov     dword ptr [r14], 0
0x180043484  mov     rdx, [rsi+40h]
0x180043488  test    rdx, rdx
0x18004348b  jnz     loc_180043525
0x180043491  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043498  mov     ebx, 8000FFFFh
0x18004349d  test    rcx, rcx
0x1800434a0  jnz     short loc_1800434E3
0x1800434a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800434a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800434af  mov     rcx, rax
0x1800434b2  test    rax, rax
0x1800434b5  jz      short loc_1800434D5
0x1800434b7  mov     rax, [rax]
0x1800434ba  mov     edx, 7F0h
0x1800434bf  mov     rax, [rax+8]
0x1800434c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434c8  test    eax, eax
0x1800434ca  jz      short loc_1800434D5
0x1800434cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800434d3  jmp     short loc_1800434E3
0x1800434d5  lea     rcx, qword_180069A90; this
0x1800434dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800434e3  cmp     byte ptr [rcx+8], 0
0x1800434e7  jz      short loc_18004350E
0x1800434e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800434ee  cmp     [rax+7CCh], ebx
0x1800434f4  jz      short loc_18004350E
0x1800434f6  mov     r9d, ebx; int
0x1800434f9  lea     rdx, aCtranscodedest_10; "CTranscodeDestination::GetStreamSinkIdB"...
0x180043500  mov     r8d, 0ABh; int
0x180043506  mov     rcx, rax; this
0x180043509  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004350e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043513  cmp     al, 1
0x180043515  jb      loc_180043641
0x18004351b  mov     edx, 15h
0x180043520  jmp     loc_180043623
0x180043525  mov     rax, qword ptr cs:MFMediaType_Audio.Data1
0x18004352c  xor     ebx, ebx
0x18004352e  sub     rax, [rdi]
0x180043531  jnz     short loc_18004353E
0x180043533  mov     rax, qword ptr cs:MFMediaType_Audio.Data4
0x18004353a  sub     rax, [rdi+8]
0x18004353e  test    rax, rax
0x180043541  jnz     short loc_180043563
0x180043543  cmp     [rdx+18h], rbx
0x180043547  jz      loc_180043641
0x18004354d  mov     dword ptr [r15], 1
0x180043554  mov     rax, [rsi+40h]
0x180043558  mov     ecx, [rax+10h]
0x18004355b  mov     [r14], ecx
0x18004355e  jmp     loc_180043641
0x180043563  mov     rax, qword ptr cs:MFMediaType_Video.Data1
0x18004356a  sub     rax, [rdi]
0x18004356d  jnz     short loc_18004357A
0x18004356f  mov     rax, qword ptr cs:MFMediaType_Video.Data4
0x180043576  sub     rax, [rdi+8]
0x18004357a  test    rax, rax
0x18004357d  jnz     short loc_180043598
0x18004357f  cmp     [rdx+8], rbx
0x180043583  jz      loc_180043641
0x180043589  mov     dword ptr [r15], 1
0x180043590  mov     rax, [rsi+40h]
0x180043594  mov     ecx, [rax]
0x180043596  jmp     short loc_18004355B
0x180043598  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004359f  mov     ebx, 80070057h
0x1800435a4  test    rcx, rcx
0x1800435a7  jnz     short loc_1800435EA
0x1800435a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800435af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435b6  mov     rcx, rax
0x1800435b9  test    rax, rax
0x1800435bc  jz      short loc_1800435DC
0x1800435be  mov     rax, [rax]
0x1800435c1  mov     edx, 7F0h
0x1800435c6  mov     rax, [rax+8]
0x1800435ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435cf  test    eax, eax
0x1800435d1  jz      short loc_1800435DC
0x1800435d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435da  jmp     short loc_1800435EA
0x1800435dc  lea     rcx, qword_180069A90; this
0x1800435e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435ea  cmp     byte ptr [rcx+8], 0
0x1800435ee  jz      short loc_180043615
0x1800435f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800435f5  cmp     [rax+7CCh], ebx
0x1800435fb  jz      short loc_180043615
0x1800435fd  mov     r9d, ebx; int
0x180043600  lea     rdx, aCtranscodedest_10; "CTranscodeDestination::GetStreamSinkIdB"...
0x180043607  mov     r8d, 0C2h; int
0x18004360d  mov     rcx, rax; this
0x180043610  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043615  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004361a  cmp     al, 1
0x18004361c  jb      short loc_180043641
0x18004361e  mov     edx, 16h
0x180043623  mov     rcx, cs:WPP_GLOBAL_Control
0x18004362a  lea     r8, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids
0x180043631  mov     r9, rsi
0x180043634  mov     [rsp+48h+var_28], ebx
0x180043638  mov     rcx, [rcx+10h]
0x18004363c  call    WPP_SF_qd
0x180043641  lea     rcx, [rsp+48h+arg_0]; this
0x180043646  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004364b  mov     rsi, [rsp+48h+arg_10]
0x180043650  mov     eax, ebx
0x180043652  mov     rbx, [rsp+48h+arg_8]
0x180043657  add     rsp, 30h
0x18004365b  pop     r15
0x18004365d  pop     r14
0x18004365f  pop     rdi
0x180043660  retn
```
