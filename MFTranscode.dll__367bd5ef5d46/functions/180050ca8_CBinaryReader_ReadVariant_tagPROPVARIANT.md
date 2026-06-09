# CBinaryReader::ReadVariant(tagPROPVARIANT *)

- ea: `0x180050ca8`
- end: `0x180050e50`
- name: `?ReadVariant@CBinaryReader@@QEAAJPEAUtagPROPVARIANT@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(CBinaryReader *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180050e70`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050ca8`
- `0x180050e58`
- `0x180050e70`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050cf5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050cf5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d9c`

## string_xrefs

- `0x180050cbd`: `CBinaryReader::ReadVariant`
- `0x180050d4c`: `CBinaryReader::ReadVariant`
- `0x180050df3`: `CBinaryReader::ReadVariant`

## pseudocode

```c
__int64 __fastcall CBinaryReader::ReadVariant(CBinaryReader *this, struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  int VariantType; // ebx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v15; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v15, "CBinaryReader::ReadVariant", 1211);
  VariantType = CBinaryReader::ReadVariantType(this, &a2->vt);
  if ( VariantType >= 0 )
  {
    VariantType = CBinaryReader::ReadVariantValue(this, a2->vt, a2);
    if ( VariantType < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != VariantType )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryReader::ReadVariant", 1213, VariantType);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 91;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v8 + 499) != VariantType )
        CallStackContext::TraceFailure(v8, "CBinaryReader::ReadVariant", 1211, VariantType);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 90;
LABEL_23:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
        this,
        VariantType);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  return (unsigned int)VariantType;
}

```

## disassembly

```asm
0x180050ca8  mov     [rsp+arg_0], rbx
0x180050cad  mov     [rsp+arg_10], rsi
0x180050cb2  push    rdi
0x180050cb3  sub     rsp, 30h
0x180050cb7  mov     rdi, rdx
0x180050cba  mov     rsi, rcx
0x180050cbd  lea     rdx, aCbinaryreaderR_2; "CBinaryReader::ReadVariant"
0x180050cc4  mov     r8d, 4BBh; int
0x180050cca  lea     rcx, [rsp+38h+arg_8]; this
0x180050ccf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050cd4  mov     rdx, rdi; unsigned __int16 *
0x180050cd7  mov     rcx, rsi; this
0x180050cda  call    ?ReadVariantType@CBinaryReader@@QEAAJAEAG@Z; CBinaryReader::ReadVariantType(ushort &)
0x180050cdf  mov     ebx, eax
0x180050ce1  test    eax, eax
0x180050ce3  jns     loc_180050D78
0x180050ce9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050cf0  test    rcx, rcx
0x180050cf3  jnz     short loc_180050D36
0x180050cf5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050cfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d02  mov     rcx, rax
0x180050d05  test    rax, rax
0x180050d08  jz      short loc_180050D28
0x180050d0a  mov     rax, [rax]
0x180050d0d  mov     edx, 7F0h
0x180050d12  mov     rax, [rax+8]
0x180050d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d1b  test    eax, eax
0x180050d1d  jz      short loc_180050D28
0x180050d1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d26  jmp     short loc_180050D36
0x180050d28  lea     rcx, qword_180069A90; this
0x180050d2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d36  cmp     byte ptr [rcx+8], 0
0x180050d3a  jz      short loc_180050D61
0x180050d3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050d41  cmp     [rax+7CCh], ebx
0x180050d47  jz      short loc_180050D61
0x180050d49  mov     r9d, ebx; int
0x180050d4c  lea     rdx, aCbinaryreaderR_2; "CBinaryReader::ReadVariant"
0x180050d53  mov     r8d, 4BBh; int
0x180050d59  mov     rcx, rax; this
0x180050d5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050d61  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050d66  cmp     al, 1
0x180050d68  jb      loc_180050E34
0x180050d6e  mov     edx, 5Ah ; 'Z'
0x180050d73  jmp     loc_180050E16
0x180050d78  movzx   edx, word ptr [rdi]; unsigned __int16
0x180050d7b  mov     r8, rdi; struct tagPROPVARIANT *
0x180050d7e  mov     rcx, rsi; this
0x180050d81  call    ?ReadVariantValue@CBinaryReader@@QEAAJGPEAUtagPROPVARIANT@@@Z; CBinaryReader::ReadVariantValue(ushort,tagPROPVARIANT *)
0x180050d86  mov     ebx, eax
0x180050d88  test    eax, eax
0x180050d8a  jns     loc_180050E34
0x180050d90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d97  test    rcx, rcx
0x180050d9a  jnz     short loc_180050DDD
0x180050d9c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050da2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050da9  mov     rcx, rax
0x180050dac  test    rax, rax
0x180050daf  jz      short loc_180050DCF
0x180050db1  mov     rax, [rax]
0x180050db4  mov     edx, 7F0h
0x180050db9  mov     rax, [rax+8]
0x180050dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dc2  test    eax, eax
0x180050dc4  jz      short loc_180050DCF
0x180050dc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050dcd  jmp     short loc_180050DDD
0x180050dcf  lea     rcx, qword_180069A90; this
0x180050dd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ddd  cmp     byte ptr [rcx+8], 0
0x180050de1  jz      short loc_180050E08
0x180050de3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050de8  cmp     [rax+7CCh], ebx
0x180050dee  jz      short loc_180050E08
0x180050df0  mov     r9d, ebx; int
0x180050df3  lea     rdx, aCbinaryreaderR_2; "CBinaryReader::ReadVariant"
0x180050dfa  mov     r8d, 4BDh; int
0x180050e00  mov     rcx, rax; this
0x180050e03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050e08  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050e0d  cmp     al, 1
0x180050e0f  jb      short loc_180050E34
0x180050e11  mov     edx, 5Bh ; '['
0x180050e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180050e1d  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180050e24  mov     r9, rsi
0x180050e27  mov     [rsp+38h+var_18], ebx
0x180050e2b  mov     rcx, [rcx+10h]
0x180050e2f  call    WPP_SF_qd
0x180050e34  lea     rcx, [rsp+38h+arg_8]; this
0x180050e39  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050e3e  mov     rsi, [rsp+38h+arg_10]
0x180050e43  mov     eax, ebx
0x180050e45  mov     rbx, [rsp+38h+arg_0]
0x180050e4a  add     rsp, 30h
0x180050e4e  pop     rdi
0x180050e4f  retn
```
