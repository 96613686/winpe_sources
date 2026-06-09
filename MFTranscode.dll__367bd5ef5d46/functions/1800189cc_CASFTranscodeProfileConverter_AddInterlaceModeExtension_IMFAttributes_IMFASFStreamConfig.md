# CASFTranscodeProfileConverter::AddInterlaceModeExtension(IMFAttributes *,IMFASFStreamConfig *)

- ea: `0x1800189cc`
- end: `0x180018b4c`
- name: `?AddInterlaceModeExtension@CASFTranscodeProfileConverter@@AEAAJPEAUIMFAttributes@@PEAUIMFASFStreamConfig@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CASFTranscodeProfileConverter *__hidden this, struct IMFAttributes *, struct IMFASFStreamConfig *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180018f9c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800189cc`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a77`

## string_xrefs

- `0x1800189e2`: `CASFTranscodeProfileConverter::AddInterlaceModeExtension`
- `0x180018ace`: `CASFTranscodeProfileConverter::AddInterlaceModeExtension`

## pseudocode

```c
__int64 __fastcall CASFTranscodeProfileConverter::AddInterlaceModeExtension(
        CASFTranscodeProfileConverter *this,
        struct IMFAttributes *a2,
        struct IMFASFStreamConfig *a3)
{
  struct IMFAttributesVtbl *lpVtbl; // rax
  int v7; // edi
  HRESULT (__stdcall *AddPayloadExtension)(IMFASFStreamConfig *, GUID, WORD, BYTE *, DWORD); // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IID v14; // [rsp+30h] [rbp-28h] BYREF
  char v15; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+68h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v15,
    "CASFTranscodeProfileConverter::AddInterlaceModeExtension",
    820);
  lpVtbl = a2->lpVtbl;
  v7 = 0;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, int *))lpVtbl->GetUINT32)(
         a2,
         &MF_MT_INTERLACE_MODE,
         &v16) >= 0
    && (unsigned int)(v16 - 3) <= 4 )
  {
    AddPayloadExtension = a3->lpVtbl->AddPayloadExtension;
    v14 = MFASFSampleExtension_ContentType;
    v7 = ((__int64 (__fastcall *)(struct IMFASFStreamConfig *, IID *, __int64, _QWORD, _DWORD))AddPayloadExtension)(
           a3,
           &v14,
           1,
           0,
           0);
    if ( v7 >= 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 4u )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 7), 103, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v16);
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CASFTranscodeProfileConverter::AddInterlaceModeExtension",
            835,
            v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800189cc  mov     [rsp+arg_10], rbx
0x1800189d1  push    rsi
0x1800189d2  push    rdi
0x1800189d3  push    r14
0x1800189d5  sub     rsp, 40h
0x1800189d9  mov     r14, r8
0x1800189dc  mov     rbx, rdx
0x1800189df  mov     rsi, rcx
0x1800189e2  lea     rdx, aCasftranscodep_0; "CASFTranscodeProfileConverter::AddInter"...
0x1800189e9  mov     r8d, 334h; int
0x1800189ef  lea     rcx, [rsp+58h+arg_0]; this
0x1800189f4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800189f9  mov     rax, [rbx]
0x1800189fc  lea     r8, [rsp+58h+arg_8]
0x180018a01  xor     edi, edi
0x180018a03  lea     rdx, MF_MT_INTERLACE_MODE
0x180018a0a  mov     rcx, rbx
0x180018a0d  mov     [rsp+58h+arg_8], edi
0x180018a11  mov     rax, [rax+38h]
0x180018a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a1a  test    eax, eax
0x180018a1c  js      loc_180018B32
0x180018a22  mov     eax, [rsp+58h+arg_8]
0x180018a26  add     eax, 0FFFFFFFDh
0x180018a29  cmp     eax, 4
0x180018a2c  ja      loc_180018B32
0x180018a32  mov     rax, [r14]
0x180018a35  lea     r8d, [rdi+1]
0x180018a39  movups  xmm0, xmmword ptr cs:MFASFSampleExtension_ContentType.Data1
0x180018a40  xor     r9d, r9d
0x180018a43  mov     [rsp+58h+var_38], edi
0x180018a47  lea     rdx, [rsp+58h+var_28]
0x180018a4c  mov     rcx, r14
0x180018a4f  mov     rax, [rax+140h]
0x180018a56  movdqu  [rsp+58h+var_28], xmm0
0x180018a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a61  mov     edi, eax
0x180018a63  test    eax, eax
0x180018a65  jns     loc_180018B02
0x180018a6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018a72  test    rcx, rcx
0x180018a75  jnz     short loc_180018AB8
0x180018a77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018a7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018a84  mov     rcx, rax
0x180018a87  test    rax, rax
0x180018a8a  jz      short loc_180018AAA
0x180018a8c  mov     rax, [rax]
0x180018a8f  mov     edx, 7F0h
0x180018a94  mov     rax, [rax+8]
0x180018a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a9d  test    eax, eax
0x180018a9f  jz      short loc_180018AAA
0x180018aa1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018aa8  jmp     short loc_180018AB8
0x180018aaa  lea     rcx, qword_180069A90; this
0x180018ab1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018ab8  cmp     byte ptr [rcx+8], 0
0x180018abc  jz      short loc_180018AE3
0x180018abe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018ac3  cmp     [rax+7CCh], edi
0x180018ac9  jz      short loc_180018AE3
0x180018acb  mov     r9d, edi; int
0x180018ace  lea     rdx, aCasftranscodep_0; "CASFTranscodeProfileConverter::AddInter"...
0x180018ad5  mov     r8d, 343h; int
0x180018adb  mov     rcx, rax; this
0x180018ade  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018ae3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180018ae8  cmp     al, 1
0x180018aea  jb      short loc_180018B32
0x180018aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180018af3  mov     edx, 66h ; 'f'
0x180018af8  mov     [rsp+58h+var_38], edi
0x180018afc  mov     rcx, [rcx+10h]
0x180018b00  jmp     short loc_180018B23
0x180018b02  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180018b07  cmp     al, 4
0x180018b09  jb      short loc_180018B32
0x180018b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b12  mov     edx, 67h ; 'g'
0x180018b17  mov     eax, [rsp+58h+arg_8]
0x180018b1b  mov     [rsp+58h+var_38], eax
0x180018b1f  mov     rcx, [rcx+38h]
0x180018b23  mov     r9, rsi
0x180018b26  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180018b2d  call    WPP_SF_qd
0x180018b32  lea     rcx, [rsp+58h+arg_0]; this
0x180018b37  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180018b3c  mov     rbx, [rsp+58h+arg_10]
0x180018b41  mov     eax, edi
0x180018b43  add     rsp, 40h
0x180018b47  pop     r14
0x180018b49  pop     rdi
0x180018b4a  pop     rsi
0x180018b4b  retn
```
