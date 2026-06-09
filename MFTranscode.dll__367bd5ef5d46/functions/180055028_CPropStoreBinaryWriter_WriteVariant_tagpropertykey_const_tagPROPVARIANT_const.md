# CPropStoreBinaryWriter::WriteVariant(_tagpropertykey const &,tagPROPVARIANT const *)

- ea: `0x180055028`
- end: `0x18005528d`
- name: `?WriteVariant@CPropStoreBinaryWriter@@IEAAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z`
- size: `613`
- prototype: `int(CPropStoreBinaryWriter *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180054a10`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180052f78`
- `0x1800533dc`
- `0x180053410`
- `0x180055028`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055087`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055136`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800551d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055087`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055136`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800551d9`

## string_xrefs

- `0x180055046`: `CPropStoreBinaryWriter::WriteVariant`
- `0x1800550de`: `CPropStoreBinaryWriter::WriteVariant`
- `0x18005518d`: `CPropStoreBinaryWriter::WriteVariant`
- `0x180055230`: `CPropStoreBinaryWriter::WriteVariant`

## pseudocode

```c
__int64 __fastcall CPropStoreBinaryWriter::WriteVariant(
        CPropStoreBinaryWriter *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3)
{
  CBinaryWriter *v3; // rdi
  __int64 v6; // rdx
  int v7; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v21; // [rsp+48h] [rbp+10h] BYREF

  v3 = (CPropStoreBinaryWriter *)((char *)this + 520);
  if ( a3->vt == 13 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CPropStoreBinaryWriter::WriteVariant", 377);
    v7 = CBinaryWriter::WriteVariantType(v3, a3->vt);
    if ( v7 >= 0 )
    {
      v7 = CBinaryWriter::WriteBool(v3, 0);
      if ( v7 < 0 )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CPropStoreBinaryWriter::WriteVariant", 378, v7);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 57;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v7 )
          CallStackContext::TraceFailure(v15, "CPropStoreBinaryWriter::WriteVariant", 377, v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 56;
        goto LABEL_35;
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CPropStoreBinaryWriter::WriteVariant", 373);
    v7 = CBinaryWriter::WriteVariant(v3, a3);
    if ( v7 < 0 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v7 )
          CallStackContext::TraceFailure(v10, "CPropStoreBinaryWriter::WriteVariant", 373, v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 55;
LABEL_35:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v7);
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055028  mov     [rsp+arg_0], rbx
0x18005502d  mov     [rsp+arg_10], rbp
0x180055032  push    rdi
0x180055033  sub     rsp, 30h
0x180055037  cmp     word ptr [r8], 0Dh
0x18005503c  lea     rdi, [rcx+208h]
0x180055043  mov     rbp, rcx
0x180055046  lea     rdx, aCpropstorebina_1; "CPropStoreBinaryWriter::WriteVariant"
0x18005504d  lea     rcx, [rsp+38h+arg_8]; this
0x180055052  mov     rbx, r8
0x180055055  jz      loc_18005510A
0x18005505b  mov     r8d, 175h; int
0x180055061  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055066  mov     rdx, rbx; struct tagPROPVARIANT *
0x180055069  mov     rcx, rdi; this
0x18005506c  call    ?WriteVariant@CBinaryWriter@@QEAAJPEBUtagPROPVARIANT@@@Z; CBinaryWriter::WriteVariant(tagPROPVARIANT const *)
0x180055071  mov     ebx, eax
0x180055073  test    eax, eax
0x180055075  jns     loc_180055271
0x18005507b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055082  test    rcx, rcx
0x180055085  jnz     short loc_1800550C8
0x180055087  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005508d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055094  mov     rcx, rax
0x180055097  test    rax, rax
0x18005509a  jz      short loc_1800550BA
0x18005509c  mov     rax, [rax]
0x18005509f  mov     edx, 7F0h
0x1800550a4  mov     rax, [rax+8]
0x1800550a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550ad  test    eax, eax
0x1800550af  jz      short loc_1800550BA
0x1800550b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550b8  jmp     short loc_1800550C8
0x1800550ba  lea     rcx, qword_180069A90; this
0x1800550c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800550c8  cmp     byte ptr [rcx+8], 0
0x1800550cc  jz      short loc_1800550F3
0x1800550ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800550d3  cmp     [rax+7CCh], ebx
0x1800550d9  jz      short loc_1800550F3
0x1800550db  mov     r9d, ebx; int
0x1800550de  lea     rdx, aCpropstorebina_1; "CPropStoreBinaryWriter::WriteVariant"
0x1800550e5  mov     r8d, 175h; int
0x1800550eb  mov     rcx, rax; this
0x1800550ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800550f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800550f8  cmp     al, 1
0x1800550fa  jb      loc_180055271
0x180055100  mov     edx, 37h ; '7'
0x180055105  jmp     loc_180055253
0x18005510a  mov     r8d, 179h; int
0x180055110  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055115  movzx   edx, word ptr [rbx]; unsigned __int16
0x180055118  mov     rcx, rdi; this
0x18005511b  call    ?WriteVariantType@CBinaryWriter@@QEAAJG@Z; CBinaryWriter::WriteVariantType(ushort)
0x180055120  mov     ebx, eax
0x180055122  test    eax, eax
0x180055124  jns     loc_1800551B9
0x18005512a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055131  test    rcx, rcx
0x180055134  jnz     short loc_180055177
0x180055136  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005513c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055143  mov     rcx, rax
0x180055146  test    rax, rax
0x180055149  jz      short loc_180055169
0x18005514b  mov     rax, [rax]
0x18005514e  mov     edx, 7F0h
0x180055153  mov     rax, [rax+8]
0x180055157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005515c  test    eax, eax
0x18005515e  jz      short loc_180055169
0x180055160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055167  jmp     short loc_180055177
0x180055169  lea     rcx, qword_180069A90; this
0x180055170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055177  cmp     byte ptr [rcx+8], 0
0x18005517b  jz      short loc_1800551A2
0x18005517d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180055182  cmp     [rax+7CCh], ebx
0x180055188  jz      short loc_1800551A2
0x18005518a  mov     r9d, ebx; int
0x18005518d  lea     rdx, aCpropstorebina_1; "CPropStoreBinaryWriter::WriteVariant"
0x180055194  mov     r8d, 179h; int
0x18005519a  mov     rcx, rax; this
0x18005519d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800551a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800551a7  cmp     al, 1
0x1800551a9  jb      loc_180055271
0x1800551af  mov     edx, 38h ; '8'
0x1800551b4  jmp     loc_180055253
0x1800551b9  xor     edx, edx; int
0x1800551bb  mov     rcx, rdi; this
0x1800551be  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x1800551c3  mov     ebx, eax
0x1800551c5  test    eax, eax
0x1800551c7  jns     loc_180055271
0x1800551cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800551d4  test    rcx, rcx
0x1800551d7  jnz     short loc_18005521A
0x1800551d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800551df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800551e6  mov     rcx, rax
0x1800551e9  test    rax, rax
0x1800551ec  jz      short loc_18005520C
0x1800551ee  mov     rax, [rax]
0x1800551f1  mov     edx, 7F0h
0x1800551f6  mov     rax, [rax+8]
0x1800551fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551ff  test    eax, eax
0x180055201  jz      short loc_18005520C
0x180055203  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005520a  jmp     short loc_18005521A
0x18005520c  lea     rcx, qword_180069A90; this
0x180055213  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005521a  cmp     byte ptr [rcx+8], 0
0x18005521e  jz      short loc_180055245
0x180055220  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180055225  cmp     [rax+7CCh], ebx
0x18005522b  jz      short loc_180055245
0x18005522d  mov     r9d, ebx; int
0x180055230  lea     rdx, aCpropstorebina_1; "CPropStoreBinaryWriter::WriteVariant"
0x180055237  mov     r8d, 17Ah; int
0x18005523d  mov     rcx, rax; this
0x180055240  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180055245  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005524a  cmp     al, 1
0x18005524c  jb      short loc_180055271
0x18005524e  mov     edx, 39h ; '9'
0x180055253  mov     rcx, cs:WPP_GLOBAL_Control
0x18005525a  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x180055261  mov     r9, rbp
0x180055264  mov     [rsp+38h+var_18], ebx
0x180055268  mov     rcx, [rcx+10h]
0x18005526c  call    WPP_SF_qd
0x180055271  lea     rcx, [rsp+38h+arg_8]; this
0x180055276  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005527b  mov     rbp, [rsp+38h+arg_10]
0x180055280  mov     eax, ebx
0x180055282  mov     rbx, [rsp+38h+arg_0]
0x180055287  add     rsp, 30h
0x18005528b  pop     rdi
0x18005528c  retn
```
