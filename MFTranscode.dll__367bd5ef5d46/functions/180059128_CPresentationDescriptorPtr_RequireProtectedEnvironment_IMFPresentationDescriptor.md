# CPresentationDescriptorPtr::RequireProtectedEnvironment(IMFPresentationDescriptor *)

- ea: `0x180059128`
- end: `0x18005935c`
- name: `?RequireProtectedEnvironment@CPresentationDescriptorPtr@@SAJPEAUIMFPresentationDescriptor@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003b8cc`

## callees

- `0x1800035c0`
- `0x18000a3f4`
- `0x1800153ac`
- `0x18004f410`
- `0x180059128`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800592da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059263`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800592da`

## string_xrefs

- `0x1800591c0`: `CPresentationDescriptorPtr::RequireProtectedEnvironment`
- `0x180059337`: `CPresentationDescriptorPtr::RequireProtectedEnvironment`

## pseudocode

```c
__int64 __fastcall CPresentationDescriptorPtr::RequireProtectedEnvironment(struct IMFPresentationDescriptor *a1)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v3; // rdx
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  struct IMFPresentationDescriptorVtbl *v10; // rax
  __int64 v11; // rdx
  int v12; // esi
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v16; // r9d
  int v17; // r8d
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  unsigned int v21; // [rsp+60h] [rbp+30h] BYREF
  int v22; // [rsp+68h] [rbp+38h] BYREF
  __int64 v23; // [rsp+70h] [rbp+40h] BYREF

  lpVtbl = a1->lpVtbl;
  v21 = 0;
  v4 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))lpVtbl->GetStreamDescriptorCount)(
         a1,
         &v21);
  if ( v4 >= 0 )
  {
    v9 = 0;
    v8 = 1;
    while ( 1 )
    {
      if ( v9 >= v21 )
        return v8;
      v10 = a1->lpVtbl;
      v22 = 0;
      v23 = 0;
      v12 = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, __int64 *))v10->GetStreamDescriptorByIndex)(
              a1,
              v9,
              &v22,
              &v23);
      if ( v12 < 0 )
        break;
      if ( !v23 )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          v16 = -1072875845;
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
          {
            v17 = 122;
            goto LABEL_34;
          }
        }
        goto LABEL_35;
      }
      if ( (unsigned int)MFGetAttributeUINT32(v23, &MF_SD_PROTECTED, 0) )
      {
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v23);
        return 0;
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v23);
      ++v9;
    }
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
      {
        v16 = v12;
        v17 = 121;
LABEL_34:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CPresentationDescriptorPtr::RequireProtectedEnvironment",
          v17,
          v16);
      }
    }
LABEL_35:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v23);
    return v8;
  }
  v5 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
    CallStackTracing::s_wpInstance = v6;
    if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
    {
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    if ( *((_DWORD *)v7 + 499) != v4 )
      CallStackContext::TraceFailure(v7, "CPresentationDescriptorPtr::RequireProtectedEnvironment", 113, v4);
  }
  return 1;
}

```

## disassembly

```asm
0x180059128  push    rbp
0x18005912a  push    rbx
0x18005912b  push    rsi
0x18005912c  push    rdi
0x18005912d  push    r14
0x18005912f  mov     rbp, rsp
0x180059132  sub     rsp, 30h
0x180059136  mov     rax, [rcx]
0x180059139  lea     rdx, [rbp+arg_0]
0x18005913d  mov     r14, rcx
0x180059140  mov     [rbp+arg_0], 0
0x180059147  mov     rax, [rax+108h]
0x18005914e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059153  mov     ebx, eax
0x180059155  test    eax, eax
0x180059157  jns     loc_1800591DF
0x18005915d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059164  test    rcx, rcx
0x180059167  jnz     short loc_1800591AA
0x180059169  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005916f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059176  mov     rcx, rax
0x180059179  test    rax, rax
0x18005917c  jz      short loc_18005919C
0x18005917e  mov     rax, [rax]
0x180059181  mov     edx, 7F0h
0x180059186  mov     rax, [rax+8]
0x18005918a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005918f  test    eax, eax
0x180059191  jz      short loc_18005919C
0x180059193  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005919a  jmp     short loc_1800591AA
0x18005919c  lea     rcx, qword_180069A90; this
0x1800591a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800591aa  cmp     byte ptr [rcx+8], 0
0x1800591ae  jz      short loc_1800591D5
0x1800591b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800591b5  cmp     [rax+7CCh], ebx
0x1800591bb  jz      short loc_1800591D5
0x1800591bd  mov     r9d, ebx; int
0x1800591c0  lea     rdx, aCpresentationd; "CPresentationDescriptorPtr::RequireProt"...
0x1800591c7  mov     r8d, 71h ; 'q'; int
0x1800591cd  mov     rcx, rax; this
0x1800591d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800591d5  mov     ebx, 1
0x1800591da  jmp     loc_18005934F
0x1800591df  xor     edi, edi
0x1800591e1  lea     ebx, [rdi+1]
0x1800591e4  cmp     edi, [rbp+arg_0]
0x1800591e7  jnb     loc_18005934F
0x1800591ed  mov     rax, [r14]
0x1800591f0  lea     r9, [rbp+arg_10]
0x1800591f4  lea     r8, [rbp+arg_8]
0x1800591f8  mov     [rbp+arg_8], 0
0x1800591ff  mov     edx, edi
0x180059201  mov     [rbp+arg_10], 0
0x180059209  mov     rcx, r14
0x18005920c  mov     rax, [rax+110h]
0x180059213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059218  mov     esi, eax
0x18005921a  test    eax, eax
0x18005921c  js      loc_1800592CE
0x180059222  mov     rcx, [rbp+arg_10]
0x180059226  test    rcx, rcx
0x180059229  jz      short loc_180059257
0x18005922b  xor     r8d, r8d
0x18005922e  lea     rdx, MF_SD_PROTECTED
0x180059235  call    MFGetAttributeUINT32
0x18005923a  lea     rcx, [rbp+arg_10]
0x18005923e  test    eax, eax
0x180059240  jnz     short loc_18005924B
0x180059242  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180059247  add     edi, ebx
0x180059249  jmp     short loc_1800591E4
0x18005924b  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180059250  xor     ebx, ebx
0x180059252  jmp     loc_18005934F
0x180059257  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005925e  test    rcx, rcx
0x180059261  jnz     short loc_1800592A4
0x180059263  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059269  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059270  mov     rcx, rax
0x180059273  test    rax, rax
0x180059276  jz      short loc_180059296
0x180059278  mov     rax, [rax]
0x18005927b  mov     edx, 7F0h
0x180059280  mov     rax, [rax+8]
0x180059284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059289  test    eax, eax
0x18005928b  jz      short loc_180059296
0x18005928d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059294  jmp     short loc_1800592A4
0x180059296  lea     rcx, qword_180069A90; this
0x18005929d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800592a4  cmp     byte ptr [rcx+8], 0
0x1800592a8  jz      loc_180059346
0x1800592ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800592b3  mov     r9d, 0C00D36BBh
0x1800592b9  cmp     [rax+7CCh], r9d
0x1800592c0  jz      loc_180059346
0x1800592c6  mov     r8d, 7Ah ; 'z'
0x1800592cc  jmp     short loc_180059337
0x1800592ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800592d5  test    rcx, rcx
0x1800592d8  jnz     short loc_18005931B
0x1800592da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800592e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800592e7  mov     rcx, rax
0x1800592ea  test    rax, rax
0x1800592ed  jz      short loc_18005930D
0x1800592ef  mov     rax, [rax]
0x1800592f2  mov     edx, 7F0h
0x1800592f7  mov     rax, [rax+8]
0x1800592fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059300  test    eax, eax
0x180059302  jz      short loc_18005930D
0x180059304  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005930b  jmp     short loc_18005931B
0x18005930d  lea     rcx, qword_180069A90; this
0x180059314  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005931b  cmp     byte ptr [rcx+8], 0
0x18005931f  jz      short loc_180059346
0x180059321  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180059326  cmp     [rax+7CCh], esi
0x18005932c  jz      short loc_180059346
0x18005932e  mov     r9d, esi; int
0x180059331  mov     r8d, 79h ; 'y'; int
0x180059337  lea     rdx, aCpresentationd; "CPresentationDescriptorPtr::RequireProt"...
0x18005933e  mov     rcx, rax; this
0x180059341  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059346  lea     rcx, [rbp+arg_10]
0x18005934a  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18005934f  mov     eax, ebx
0x180059351  add     rsp, 30h
0x180059355  pop     r14
0x180059357  pop     rdi
0x180059358  pop     rsi
0x180059359  pop     rbx
0x18005935a  pop     rbp
0x18005935b  retn
```
