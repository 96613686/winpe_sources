# CPropStoreBinaryReader::ReadVariant(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180054790`
- end: `0x180054a08`
- name: `?ReadVariant@CPropStoreBinaryReader@@IEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(CPropStoreBinaryReader *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180054384`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050738`
- `0x180050e58`
- `0x180050e70`
- `0x180054790`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800547ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800548c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005496b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800547ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800548c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005496b`

## string_xrefs

- `0x1800547a4`: `CPropStoreBinaryReader::ReadVariant`
- `0x180054846`: `CPropStoreBinaryReader::ReadVariant`
- `0x180054917`: `CPropStoreBinaryReader::ReadVariant`
- `0x1800549c2`: `CPropStoreBinaryReader::ReadVariant`

## pseudocode

```c
__int64 __fastcall CPropStoreBinaryReader::ReadVariant(
        CPropStoreBinaryReader *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v5; // rdx
  int Int32; // ebx
  CallStackTracing *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  CBinaryReader *v11; // rcx
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int16 v21; // [rsp+50h] [rbp+8h] BYREF
  const struct _tagpropertykey *v22; // [rsp+58h] [rbp+10h] BYREF

  v22 = a2;
  v21 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CPropStoreBinaryReader::ReadVariant", 452);
  Int32 = CBinaryReader::ReadVariantType((CPropStoreBinaryReader *)((char *)this + 520), &v21);
  if ( Int32 >= 0 )
  {
    v11 = (CPropStoreBinaryReader *)((char *)this + 520);
    if ( v21 == 13 )
    {
      LODWORD(v22) = 0;
      Int32 = CBinaryReader::ReadInt32(v11, (int *)&v22);
      if ( Int32 >= 0 )
      {
        a3->vt = 0;
        goto LABEL_37;
      }
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Int32 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CPropStoreBinaryReader::ReadVariant", 461, Int32);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 67;
        goto LABEL_12;
      }
    }
    else
    {
      Int32 = CBinaryReader::ReadVariantValue(v11, v21, a3);
      if ( Int32 < 0 )
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = (CallStackTracing *)&qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( *((_DWORD *)v15 + 499) != Int32 )
            CallStackContext::TraceFailure(v15, "CPropStoreBinaryReader::ReadVariant", 456, Int32);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 66;
          goto LABEL_12;
        }
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v9 + 499) != Int32 )
        CallStackContext::TraceFailure(v9, "CPropStoreBinaryReader::ReadVariant", 452, Int32);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 65;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, Int32);
    }
  }
LABEL_37:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)Int32;
}

```

## disassembly

```asm
0x180054790  mov     [rsp+arg_10], rbx
0x180054795  mov     [rsp+arg_8], rdx
0x18005479a  push    rbp
0x18005479b  push    rsi
0x18005479c  push    rdi
0x18005479d  sub     rsp, 30h
0x1800547a1  mov     rsi, r8
0x1800547a4  lea     rdx, aCpropstorebina_0; "CPropStoreBinaryReader::ReadVariant"
0x1800547ab  mov     rbp, rcx
0x1800547ae  xor     eax, eax
0x1800547b0  mov     r8d, 1C4h; int
0x1800547b6  mov     [rsp+48h+arg_0], ax
0x1800547bb  lea     rcx, [rsp+48h+arg_8]; this
0x1800547c0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800547c5  lea     rdi, [rbp+208h]
0x1800547cc  mov     rcx, rdi; this
0x1800547cf  lea     rdx, [rsp+48h+arg_0]; unsigned __int16 *
0x1800547d4  call    ?ReadVariantType@CBinaryReader@@QEAAJAEAG@Z; CBinaryReader::ReadVariantType(ushort &)
0x1800547d9  mov     ebx, eax
0x1800547db  test    eax, eax
0x1800547dd  jns     loc_180054890
0x1800547e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800547ea  test    rcx, rcx
0x1800547ed  jnz     short loc_180054830
0x1800547ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800547f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800547fc  mov     rcx, rax
0x1800547ff  test    rax, rax
0x180054802  jz      short loc_180054822
0x180054804  mov     rax, [rax]
0x180054807  mov     edx, 7F0h
0x18005480c  mov     rax, [rax+8]
0x180054810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054815  test    eax, eax
0x180054817  jz      short loc_180054822
0x180054819  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054820  jmp     short loc_180054830
0x180054822  lea     rcx, qword_180069A90; this
0x180054829  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054830  cmp     byte ptr [rcx+8], 0
0x180054834  jz      short loc_18005485B
0x180054836  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005483b  cmp     [rax+7CCh], ebx
0x180054841  jz      short loc_18005485B
0x180054843  mov     r9d, ebx; int
0x180054846  lea     rdx, aCpropstorebina_0; "CPropStoreBinaryReader::ReadVariant"
0x18005484d  mov     r8d, 1C4h; int
0x180054853  mov     rcx, rax; this
0x180054856  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005485b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054860  cmp     al, 1
0x180054862  jb      loc_1800549EF
0x180054868  mov     edx, 41h ; 'A'
0x18005486d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054874  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x18005487b  mov     r9, rbp
0x18005487e  mov     [rsp+48h+var_28], ebx
0x180054882  mov     rcx, [rcx+10h]
0x180054886  call    WPP_SF_qd
0x18005488b  jmp     loc_1800549EF
0x180054890  movzx   edx, [rsp+48h+arg_0]; unsigned __int16
0x180054895  mov     rcx, rdi; this
0x180054898  cmp     dx, 0Dh
0x18005489c  jz      loc_180054943
0x1800548a2  mov     r8, rsi; struct tagPROPVARIANT *
0x1800548a5  call    ?ReadVariantValue@CBinaryReader@@QEAAJGPEAUtagPROPVARIANT@@@Z; CBinaryReader::ReadVariantValue(ushort,tagPROPVARIANT *)
0x1800548aa  mov     ebx, eax
0x1800548ac  test    eax, eax
0x1800548ae  jns     loc_1800549EF
0x1800548b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800548bb  test    rcx, rcx
0x1800548be  jnz     short loc_180054901
0x1800548c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800548c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800548cd  mov     rcx, rax
0x1800548d0  test    rax, rax
0x1800548d3  jz      short loc_1800548F3
0x1800548d5  mov     rax, [rax]
0x1800548d8  mov     edx, 7F0h
0x1800548dd  mov     rax, [rax+8]
0x1800548e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548e6  test    eax, eax
0x1800548e8  jz      short loc_1800548F3
0x1800548ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800548f1  jmp     short loc_180054901
0x1800548f3  lea     rcx, qword_180069A90; this
0x1800548fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054901  cmp     byte ptr [rcx+8], 0
0x180054905  jz      short loc_18005492C
0x180054907  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005490c  cmp     [rax+7CCh], ebx
0x180054912  jz      short loc_18005492C
0x180054914  mov     r9d, ebx; int
0x180054917  lea     rdx, aCpropstorebina_0; "CPropStoreBinaryReader::ReadVariant"
0x18005491e  mov     r8d, 1C8h; int
0x180054924  mov     rcx, rax; this
0x180054927  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005492c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054931  cmp     al, 1
0x180054933  jb      loc_1800549EF
0x180054939  mov     edx, 42h ; 'B'
0x18005493e  jmp     loc_18005486D
0x180054943  lea     rdx, [rsp+48h+arg_8]; int *
0x180054948  mov     dword ptr [rsp+48h+arg_8], 0
0x180054950  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x180054955  mov     ebx, eax
0x180054957  test    eax, eax
0x180054959  jns     loc_1800549EA
0x18005495f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054966  test    rcx, rcx
0x180054969  jnz     short loc_1800549AC
0x18005496b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054971  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054978  mov     rcx, rax
0x18005497b  test    rax, rax
0x18005497e  jz      short loc_18005499E
0x180054980  mov     rax, [rax]
0x180054983  mov     edx, 7F0h
0x180054988  mov     rax, [rax+8]
0x18005498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054991  test    eax, eax
0x180054993  jz      short loc_18005499E
0x180054995  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005499c  jmp     short loc_1800549AC
0x18005499e  lea     rcx, qword_180069A90; this
0x1800549a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549ac  cmp     byte ptr [rcx+8], 0
0x1800549b0  jz      short loc_1800549D7
0x1800549b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800549b7  cmp     [rax+7CCh], ebx
0x1800549bd  jz      short loc_1800549D7
0x1800549bf  mov     r9d, ebx; int
0x1800549c2  lea     rdx, aCpropstorebina_0; "CPropStoreBinaryReader::ReadVariant"
0x1800549c9  mov     r8d, 1CDh; int
0x1800549cf  mov     rcx, rax; this
0x1800549d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800549d7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800549dc  cmp     al, 1
0x1800549de  jb      short loc_1800549EF
0x1800549e0  mov     edx, 43h ; 'C'
0x1800549e5  jmp     loc_18005486D
0x1800549ea  xor     eax, eax
0x1800549ec  mov     [rsi], ax
0x1800549ef  lea     rcx, [rsp+48h+arg_8]; this
0x1800549f4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800549f9  mov     eax, ebx
0x1800549fb  mov     rbx, [rsp+48h+arg_10]
0x180054a00  add     rsp, 30h
0x180054a04  pop     rdi
0x180054a05  pop     rsi
0x180054a06  pop     rbp
0x180054a07  retn
```
