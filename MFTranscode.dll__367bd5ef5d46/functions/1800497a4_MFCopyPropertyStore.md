# MFCopyPropertyStore

- ea: `0x1800497a4`
- end: `0x180049a93`
- name: `MFCopyPropertyStore`
- size: `751`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180034d14`
- `0x180043670`

## callees

- `0x1800035c0`
- `0x180003690`
- `0x180004a40`
- `0x180007000`
- `0x180008050`
- `0x1800085a0`
- `0x1800153ac`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180046efc`
- `0x1800497a4`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049910`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049910`

## string_xrefs

- `0x180049813`: `MFCopyPropertyStore`

## pseudocode

```c
__int64 __fastcall MFCopyPropertyStore(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v14; // edi
  __int64 v15; // rax
  _BYTE v17[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh] BYREF
  int v19[2]; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[400]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[416]; // [rsp+200h] [rbp+100h] BYREF
  PROPERTYKEY v24; // [rsp+3A0h] [rbp+2A0h] BYREF

  v19[0] = 0;
  v18 = 0;
  v24 = PKEY_Null;
  CWMPropTranslator::CWMPropTranslator((CWMPropTranslator *)v22, 0, v19);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v17, "MFCopyPropertyStore", 245);
  v5 = v19[0];
  if ( v19[0] >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a1 + 24))(a1, &v18);
    if ( v5 >= 0 )
    {
      v14 = 0;
      if ( v18 )
      {
        v5 = 0;
        do
        {
          v15 = *a1;
          memset(&pvar, 0, sizeof(pvar));
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, PROPERTYKEY *))(v15 + 32))(a1, v14, &v24) >= 0 )
          {
            *(_QWORD *)v19 = 0;
            if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(v23, &v24, v19, v21) )
            {
              if ( (unsigned int)MFGetAttributeUINT32(*(_QWORD *)v19, MF_MD_TRANSFERRABLE, 0)
                && (*(int (__fastcall **)(__int64 *, PROPERTYKEY *, PROPVARIANT *))(*a1 + 40))(a1, &v24, &pvar) >= 0 )
              {
                (*(void (__fastcall **)(__int64, PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)a2 + 48LL))(a2, &v24, &pvar);
              }
            }
          }
          CMFPropVariant::Clear(&pvar);
          ++v14;
        }
        while ( v14 < v18 );
      }
    }
    else
    {
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
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFCopyPropertyStore", 246, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 20;
        goto LABEL_13;
      }
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
      if ( v5 < 0 && *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "MFCopyPropertyStore", 245, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 19;
LABEL_13:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, 0, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v17);
  CWMPropTranslator::~CWMPropTranslator((CWMPropTranslator *)v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800497a4  mov     [rsp-8+arg_10], rbx
0x1800497a9  mov     [rsp-8+arg_18], rsi
0x1800497ae  push    rbp
0x1800497af  push    rdi
0x1800497b0  push    r14
0x1800497b2  lea     rbp, [rsp-2C0h]
0x1800497ba  sub     rsp, 3C0h
0x1800497c1  mov     rax, cs:__security_cookie
0x1800497c8  xor     rax, rsp
0x1800497cb  mov     [rbp+2D0h+var_18], rax
0x1800497d2  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800497d9  mov     eax, cs:PKEY_Null.pid
0x1800497df  lea     r8, [rsp+3D0h+var_398]; int *
0x1800497e4  mov     r14, rdx
0x1800497e7  mov     [rsp+3D0h+var_398], 0
0x1800497ef  mov     rsi, rcx
0x1800497f2  mov     [rsp+3D0h+var_39C], 0
0x1800497fa  xor     edx, edx; struct IPropertyStore *
0x1800497fc  mov     [rbp+2D0h+var_20], eax
0x180049802  lea     rcx, [rsp+3D0h+var_360]; this
0x180049807  movups  [rbp+2D0h+var_30], xmm0
0x18004980e  call    ??0CWMPropTranslator@@QEAA@PEAUIPropertyStore@@PEAJ@Z; CWMPropTranslator::CWMPropTranslator(IPropertyStore *,long *)
0x180049813  lea     rdi, aMfcopyproperty; "MFCopyPropertyStore"
0x18004981a  mov     r8d, 0F5h; int
0x180049820  mov     rdx, rdi; char *
0x180049823  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180049828  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004982d  mov     ebx, [rsp+3D0h+var_398]
0x180049831  test    ebx, ebx
0x180049833  jns     loc_1800498E6
0x180049839  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049840  test    rcx, rcx
0x180049843  jnz     short loc_180049886
0x180049845  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004984b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049852  mov     rcx, rax
0x180049855  test    rax, rax
0x180049858  jz      short loc_180049878
0x18004985a  mov     rax, [rax]
0x18004985d  mov     edx, 7F0h
0x180049862  mov     rax, [rax+8]
0x180049866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004986b  test    eax, eax
0x18004986d  jz      short loc_180049878
0x18004986f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049876  jmp     short loc_180049886
0x180049878  lea     rcx, qword_180069A90; this
0x18004987f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049886  cmp     byte ptr [rcx+8], 0
0x18004988a  jz      short loc_1800498B1
0x18004988c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049891  test    ebx, ebx
0x180049893  jns     short loc_1800498B1
0x180049895  cmp     [rax+7CCh], ebx
0x18004989b  jz      short loc_1800498B1
0x18004989d  mov     r9d, ebx; int
0x1800498a0  mov     r8d, 0F5h; int
0x1800498a6  mov     rdx, rdi; char *
0x1800498a9  mov     rcx, rax; this
0x1800498ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800498b1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800498b6  cmp     al, 1
0x1800498b8  jb      loc_180049A56
0x1800498be  mov     edx, 13h
0x1800498c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800498ca  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x1800498d1  xor     r9d, r9d
0x1800498d4  mov     [rsp+3D0h+var_3B0], ebx
0x1800498d8  mov     rcx, [rcx+10h]
0x1800498dc  call    WPP_SF_qd
0x1800498e1  jmp     loc_180049A56
0x1800498e6  mov     rax, [rsi]
0x1800498e9  lea     rdx, [rsp+3D0h+var_39C]
0x1800498ee  mov     rcx, rsi
0x1800498f1  mov     rax, [rax+18h]
0x1800498f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498fa  mov     ebx, eax
0x1800498fc  test    eax, eax
0x1800498fe  jns     loc_18004998F
0x180049904  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004990b  test    rcx, rcx
0x18004990e  jnz     short loc_180049951
0x180049910  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049916  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004991d  mov     rcx, rax
0x180049920  test    rax, rax
0x180049923  jz      short loc_180049943
0x180049925  mov     rax, [rax]
0x180049928  mov     edx, 7F0h
0x18004992d  mov     rax, [rax+8]
0x180049931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049936  test    eax, eax
0x180049938  jz      short loc_180049943
0x18004993a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049941  jmp     short loc_180049951
0x180049943  lea     rcx, qword_180069A90; this
0x18004994a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049951  cmp     byte ptr [rcx+8], 0
0x180049955  jz      short loc_180049978
0x180049957  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004995c  cmp     [rax+7CCh], ebx
0x180049962  jz      short loc_180049978
0x180049964  mov     r9d, ebx; int
0x180049967  mov     r8d, 0F6h; int
0x18004996d  mov     rdx, rdi; char *
0x180049970  mov     rcx, rax; this
0x180049973  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049978  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004997d  cmp     al, 1
0x18004997f  jb      loc_180049A56
0x180049985  mov     edx, 14h
0x18004998a  jmp     loc_1800498C3
0x18004998f  xor     edi, edi
0x180049991  cmp     [rsp+3D0h+var_39C], edi
0x180049995  jbe     loc_180049A56
0x18004999b  xor     ebx, ebx
0x18004999d  xor     eax, eax
0x18004999f  lea     r8, [rbp+2D0h+var_30]
0x1800499a6  mov     qword ptr [rsp+3D0h+pvar+10h], rax
0x1800499ab  xorps   xmm0, xmm0
0x1800499ae  mov     rax, [rsi]
0x1800499b1  mov     edx, edi
0x1800499b3  mov     rcx, rsi
0x1800499b6  movups  xmmword ptr [rsp+3D0h+pvar], xmm0
0x1800499bb  mov     rax, [rax+20h]
0x1800499bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499c4  test    eax, eax
0x1800499c6  js      short loc_180049A40
0x1800499c8  lea     r9, [rsp+3D0h+var_378]
0x1800499cd  mov     qword ptr [rsp+3D0h+var_398], rbx
0x1800499d2  lea     r8, [rsp+3D0h+var_398]
0x1800499d7  lea     rdx, [rbp+2D0h+var_30]
0x1800499de  lea     rcx, [rbp+2D0h+var_1D0]
0x1800499e5  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x1800499ea  test    eax, eax
0x1800499ec  jz      short loc_180049A40
0x1800499ee  mov     rcx, qword ptr [rsp+3D0h+var_398]
0x1800499f3  lea     rdx, MF_MD_TRANSFERRABLE
0x1800499fa  xor     r8d, r8d
0x1800499fd  call    MFGetAttributeUINT32
0x180049a02  test    eax, eax
0x180049a04  jz      short loc_180049A40
0x180049a06  mov     rax, [rsi]
0x180049a09  lea     r8, [rsp+3D0h+pvar]
0x180049a0e  lea     rdx, [rbp+2D0h+var_30]
0x180049a15  mov     rcx, rsi
0x180049a18  mov     rax, [rax+28h]
0x180049a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a21  test    eax, eax
0x180049a23  js      short loc_180049A40
0x180049a25  mov     rax, [r14]
0x180049a28  lea     r8, [rsp+3D0h+pvar]
0x180049a2d  lea     rdx, [rbp+2D0h+var_30]
0x180049a34  mov     rcx, r14
0x180049a37  mov     rax, [rax+30h]
0x180049a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a40  lea     rcx, [rsp+3D0h+pvar]; pvar
0x180049a45  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180049a4a  inc     edi
0x180049a4c  cmp     edi, [rsp+3D0h+var_39C]
0x180049a50  jb      loc_18004999D
0x180049a56  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180049a5b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049a60  lea     rcx, [rsp+3D0h+var_360]; this
0x180049a65  call    ??1CWMPropTranslator@@UEAA@XZ; CWMPropTranslator::~CWMPropTranslator(void)
0x180049a6a  mov     eax, ebx
0x180049a6c  mov     rcx, [rbp+2D0h+var_18]
0x180049a73  xor     rcx, rsp; StackCookie
0x180049a76  call    __security_check_cookie
0x180049a7b  lea     r11, [rsp+3D0h+var_10]
0x180049a83  mov     rbx, [r11+30h]
0x180049a87  mov     rsi, [r11+38h]
0x180049a8b  mov     rsp, r11
0x180049a8e  pop     r14
0x180049a90  pop     rdi
0x180049a91  pop     rbp
0x180049a92  retn
```
