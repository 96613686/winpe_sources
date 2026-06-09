# CPropStoreBinaryReader::Deserialize(IPropertyStore * *)

- ea: `0x1800541ac`
- end: `0x18005437e`
- name: `?Deserialize@CPropStoreBinaryReader@@QEAAJPEAPEAUIPropertyStore@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CPropStoreBinaryReader *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x1800541ac`
- `0x180054384`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800542c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800542c5`
- `MFPlat!CreatePropertyStore` at `0x1800541e5`
- `MFPlat!CreatePropertyStore` at `0x1800541e5`

## string_xrefs

- `0x1800541ca`: `CPropStoreBinaryReader::Deserialize`
- `0x180054258`: `CPropStoreBinaryReader::Deserialize`
- `0x18005431c`: `CPropStoreBinaryReader::Deserialize`

## pseudocode

```c
__int64 __fastcall CPropStoreBinaryReader::Deserialize(CPropStoreBinaryReader *this, struct IPropertyStore **a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IPropertyStore *v14; // rcx
  char v16; // [rsp+50h] [rbp+18h] BYREF
  IPropertyStore *ppStore; // [rsp+58h] [rbp+20h] BYREF

  ppStore = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CPropStoreBinaryReader::Deserialize", 398);
  v5 = CreatePropertyStore(&ppStore);
  if ( v5 >= 0 )
  {
    v5 = CPropStoreBinaryReader::Deserialize(this, ppStore);
    if ( v5 >= 0 )
    {
      v14 = ppStore;
      *a2 = ppStore;
      ((void (__fastcall *)(IPropertyStore *))v14->lpVtbl->AddRef)(v14);
      goto LABEL_25;
    }
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPropStoreBinaryReader::Deserialize", 400, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 59;
      goto LABEL_12;
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CPropStoreBinaryReader::Deserialize", 398, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 58;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v5);
    }
  }
LABEL_25:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppStore);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800541ac  mov     rax, rsp
0x1800541af  mov     [rax+8], rbx
0x1800541b3  mov     [rax+10h], rsi
0x1800541b7  push    rdi
0x1800541b8  sub     rsp, 30h
0x1800541bc  mov     rsi, rdx
0x1800541bf  mov     qword ptr [rax+20h], 0
0x1800541c7  mov     rdi, rcx
0x1800541ca  lea     rdx, aCpropstorebina_2; "CPropStoreBinaryReader::Deserialize"
0x1800541d1  lea     rcx, [rax+18h]; this
0x1800541d5  mov     r8d, 18Eh; int
0x1800541db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800541e0  lea     rcx, [rsp+38h+ppStore]; ppStore
0x1800541e5  call    cs:__imp_CreatePropertyStore
0x1800541eb  mov     ebx, eax
0x1800541ed  test    eax, eax
0x1800541ef  jns     loc_1800542A2
0x1800541f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800541fc  test    rcx, rcx
0x1800541ff  jnz     short loc_180054242
0x180054201  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054207  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005420e  mov     rcx, rax
0x180054211  test    rax, rax
0x180054214  jz      short loc_180054234
0x180054216  mov     rax, [rax]
0x180054219  mov     edx, 7F0h
0x18005421e  mov     rax, [rax+8]
0x180054222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054227  test    eax, eax
0x180054229  jz      short loc_180054234
0x18005422b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054232  jmp     short loc_180054242
0x180054234  lea     rcx, qword_180069A90; this
0x18005423b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054242  cmp     byte ptr [rcx+8], 0
0x180054246  jz      short loc_18005426D
0x180054248  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005424d  cmp     [rax+7CCh], ebx
0x180054253  jz      short loc_18005426D
0x180054255  mov     r9d, ebx; int
0x180054258  lea     rdx, aCpropstorebina_2; "CPropStoreBinaryReader::Deserialize"
0x18005425f  mov     r8d, 18Eh; int
0x180054265  mov     rcx, rax; this
0x180054268  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005426d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054272  cmp     al, 1
0x180054274  jb      loc_180054358
0x18005427a  mov     edx, 3Ah ; ':'
0x18005427f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054286  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x18005428d  mov     r9, rdi
0x180054290  mov     [rsp+38h+var_18], ebx
0x180054294  mov     rcx, [rcx+10h]
0x180054298  call    WPP_SF_qd
0x18005429d  jmp     loc_180054358
0x1800542a2  mov     rdx, [rsp+38h+ppStore]; struct IPropertyStore *
0x1800542a7  mov     rcx, rdi; this
0x1800542aa  call    ?Deserialize@CPropStoreBinaryReader@@QEAAJPEAUIPropertyStore@@@Z; CPropStoreBinaryReader::Deserialize(IPropertyStore *)
0x1800542af  mov     ebx, eax
0x1800542b1  test    eax, eax
0x1800542b3  jns     loc_180054344
0x1800542b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800542c0  test    rcx, rcx
0x1800542c3  jnz     short loc_180054306
0x1800542c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800542cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800542d2  mov     rcx, rax
0x1800542d5  test    rax, rax
0x1800542d8  jz      short loc_1800542F8
0x1800542da  mov     rax, [rax]
0x1800542dd  mov     edx, 7F0h
0x1800542e2  mov     rax, [rax+8]
0x1800542e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542eb  test    eax, eax
0x1800542ed  jz      short loc_1800542F8
0x1800542ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800542f6  jmp     short loc_180054306
0x1800542f8  lea     rcx, qword_180069A90; this
0x1800542ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054306  cmp     byte ptr [rcx+8], 0
0x18005430a  jz      short loc_180054331
0x18005430c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054311  cmp     [rax+7CCh], ebx
0x180054317  jz      short loc_180054331
0x180054319  mov     r9d, ebx; int
0x18005431c  lea     rdx, aCpropstorebina_2; "CPropStoreBinaryReader::Deserialize"
0x180054323  mov     r8d, 190h; int
0x180054329  mov     rcx, rax; this
0x18005432c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054331  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054336  cmp     al, 1
0x180054338  jb      short loc_180054358
0x18005433a  mov     edx, 3Bh ; ';'
0x18005433f  jmp     loc_18005427F
0x180054344  mov     rcx, [rsp+38h+ppStore]
0x180054349  mov     [rsi], rcx
0x18005434c  mov     rax, [rcx]
0x18005434f  mov     rax, [rax+8]
0x180054353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054358  lea     rcx, [rsp+38h+arg_10]; this
0x18005435d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054362  lea     rcx, [rsp+38h+ppStore]
0x180054367  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18005436c  mov     rsi, [rsp+38h+arg_8]
0x180054371  mov     eax, ebx
0x180054373  mov     rbx, [rsp+38h+arg_0]
0x180054378  add     rsp, 30h
0x18005437c  pop     rdi
0x18005437d  retn
```
