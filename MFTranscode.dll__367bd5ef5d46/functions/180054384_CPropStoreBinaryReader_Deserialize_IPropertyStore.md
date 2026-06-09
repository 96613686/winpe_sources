# CPropStoreBinaryReader::Deserialize(IPropertyStore *)

- ea: `0x180054384`
- end: `0x180054787`
- name: `?Deserialize@CPropStoreBinaryReader@@QEAAJPEAUIPropertyStore@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CPropStoreBinaryReader *__hidden this, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800541ac`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050738`
- `0x180050750`
- `0x180054384`
- `0x180054790`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005449d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054752`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005449d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054752`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054411`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800545a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005462f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800546ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054411`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054519`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800545a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005462f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800546ba`

## string_xrefs

- `0x1800543ab`: `CPropStoreBinaryReader::Deserialize`

## pseudocode

```c
__int64 __fastcall CPropStoreBinaryReader::Deserialize(CPropStoreBinaryReader *this, struct IPropertyStore *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  unsigned int i; // edi
  __int64 v11; // rdx
  const struct _tagpropertykey *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v28[4]; // [rsp+30h] [rbp-40h] BYREF
  int v29; // [rsp+34h] [rbp-3Ch] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-38h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-20h] BYREF
  int v32; // [rsp+60h] [rbp-10h] BYREF

  v32 = 0;
  v29 = 0;
  v31 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v28, "CPropStoreBinaryReader::Deserialize", 420);
  v5 = CBinaryReader::ReadInt32((CPropStoreBinaryReader *)((char *)this + 520), &v29);
  if ( v5 >= 0 )
  {
    for ( i = 0; i < v29; ++i )
    {
      PropVariantClear(&pvar);
      v5 = CBinaryReader::ReadGuid((CPropStoreBinaryReader *)((char *)this + 520), &v31);
      if ( v5 < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CPropStoreBinaryReader::Deserialize", 427, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 61;
          goto LABEL_60;
        }
        break;
      }
      v5 = CBinaryReader::ReadInt32((CPropStoreBinaryReader *)((char *)this + 520), &v32);
      if ( v5 < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v5 )
            CallStackContext::TraceFailure(v23, "CPropStoreBinaryReader::Deserialize", 428, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 62;
          goto LABEL_60;
        }
        break;
      }
      v5 = CPropStoreBinaryReader::ReadVariant(this, v12, &pvar);
      if ( v5 < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v5 )
            CallStackContext::TraceFailure(v20, "CPropStoreBinaryReader::Deserialize", 431, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 63;
          goto LABEL_60;
        }
        break;
      }
      if ( pvar.vt )
      {
        v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _GUID *, PROPVARIANT *))a2->lpVtbl->SetValue)(
               a2,
               &v31,
               &pvar);
        if ( v5 < 0 )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v16;
            if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
            {
              v15 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v15 + 8) )
          {
            v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
            if ( *((_DWORD *)v17 + 499) != v5 )
              CallStackContext::TraceFailure(v17, "CPropStoreBinaryReader::Deserialize", 435, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 64;
            goto LABEL_60;
          }
          break;
        }
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
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CPropStoreBinaryReader::Deserialize", 420, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 60;
LABEL_60:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v5);
    }
  }
  PropVariantClear(&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180054384  mov     [rsp-38h+arg_10], rbx
0x180054389  push    rbp
0x18005438a  push    rsi
0x18005438b  push    rdi
0x18005438c  push    r12
0x18005438e  push    r13
0x180054390  push    r14
0x180054392  push    r15
0x180054394  mov     rbp, rsp
0x180054397  sub     rsp, 70h
0x18005439b  mov     rax, cs:__security_cookie
0x1800543a2  xor     rax, rsp
0x1800543a5  mov     [rbp+var_8], rax
0x1800543a9  xor     eax, eax
0x1800543ab  lea     r13, aCpropstorebina_2; "CPropStoreBinaryReader::Deserialize"
0x1800543b2  mov     r15, rdx
0x1800543b5  mov     [rbp+var_10], eax
0x1800543b8  mov     rsi, rcx
0x1800543bb  mov     qword ptr [rbp+pvar+10h], rax
0x1800543bf  xorps   xmm0, xmm0
0x1800543c2  lea     rcx, [rbp+var_40]; this
0x1800543c6  xorps   xmm1, xmm1
0x1800543c9  mov     edi, 1A4h
0x1800543ce  xor     r12d, r12d
0x1800543d1  mov     r8d, edi; int
0x1800543d4  mov     rdx, r13; char *
0x1800543d7  mov     [rbp+var_3C], r12d
0x1800543db  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800543df  movups  xmmword ptr [rbp+pvar], xmm1
0x1800543e3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800543e8  lea     r14, [rsi+208h]
0x1800543ef  mov     rcx, r14; this
0x1800543f2  lea     rdx, [rbp+var_3C]; int *
0x1800543f6  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1800543fb  mov     ebx, eax
0x1800543fd  test    eax, eax
0x1800543ff  jns     loc_18005448D
0x180054405  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005440c  test    rcx, rcx
0x18005440f  jnz     short loc_180054452
0x180054411  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054417  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005441e  mov     rcx, rax
0x180054421  test    rax, rax
0x180054424  jz      short loc_180054444
0x180054426  mov     rax, [rax]
0x180054429  mov     edx, 7F0h
0x18005442e  mov     rax, [rax+8]
0x180054432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054437  test    eax, eax
0x180054439  jz      short loc_180054444
0x18005443b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054442  jmp     short loc_180054452
0x180054444  lea     rcx, qword_180069A90; this
0x18005444b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054452  cmp     [rcx+8], r12b
0x180054456  jz      short loc_180054476
0x180054458  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005445d  cmp     [rax+7CCh], ebx
0x180054463  jz      short loc_180054476
0x180054465  mov     r9d, ebx; int
0x180054468  mov     r8d, edi; int
0x18005446b  mov     rdx, r13; char *
0x18005446e  mov     rcx, rax; this
0x180054471  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054476  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005447b  cmp     al, 1
0x18005447d  jb      loc_18005474E
0x180054483  mov     edx, 3Ch ; '<'
0x180054488  jmp     loc_180054730
0x18005448d  mov     edi, r12d
0x180054490  cmp     edi, [rbp+var_3C]
0x180054493  jnb     loc_18005474E
0x180054499  lea     rcx, [rbp+pvar]; pvar
0x18005449d  call    cs:__imp_PropVariantClear
0x1800544a3  lea     rdx, [rbp+var_20]; struct _GUID *
0x1800544a7  mov     rcx, r14; this
0x1800544aa  call    ?ReadGuid@CBinaryReader@@QEAAJAEAU_GUID@@@Z; CBinaryReader::ReadGuid(_GUID &)
0x1800544af  mov     ebx, eax
0x1800544b1  test    eax, eax
0x1800544b3  js      loc_1800546AE
0x1800544b9  lea     rdx, [rbp+var_10]; int *
0x1800544bd  mov     rcx, r14; this
0x1800544c0  call    ?ReadInt32@CBinaryReader@@QEAAJAEAJ@Z; CBinaryReader::ReadInt32(long &)
0x1800544c5  mov     ebx, eax
0x1800544c7  test    eax, eax
0x1800544c9  js      loc_180054623
0x1800544cf  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800544d3  mov     rcx, rsi; this
0x1800544d6  call    ?ReadVariant@CPropStoreBinaryReader@@IEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPropStoreBinaryReader::ReadVariant(_tagpropertykey const &,tagPROPVARIANT *)
0x1800544db  mov     ebx, eax
0x1800544dd  test    eax, eax
0x1800544df  js      loc_180054598
0x1800544e5  cmp     word ptr [rbp+pvar], r12w
0x1800544ea  jz      short loc_180054509
0x1800544ec  mov     rax, [r15]
0x1800544ef  lea     r8, [rbp+pvar]
0x1800544f3  lea     rdx, [rbp+var_20]
0x1800544f7  mov     rcx, r15
0x1800544fa  mov     rax, [rax+30h]
0x1800544fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054503  mov     ebx, eax
0x180054505  test    eax, eax
0x180054507  js      short loc_18005450D
0x180054509  inc     edi
0x18005450b  jmp     short loc_180054490
0x18005450d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054514  test    rcx, rcx
0x180054517  jnz     short loc_18005455A
0x180054519  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005451f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054526  mov     rcx, rax
0x180054529  test    rax, rax
0x18005452c  jz      short loc_18005454C
0x18005452e  mov     rax, [rax]
0x180054531  mov     edx, 7F0h
0x180054536  mov     rax, [rax+8]
0x18005453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005453f  test    eax, eax
0x180054541  jz      short loc_18005454C
0x180054543  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005454a  jmp     short loc_18005455A
0x18005454c  lea     rcx, qword_180069A90; this
0x180054553  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005455a  cmp     [rcx+8], r12b
0x18005455e  jz      short loc_180054581
0x180054560  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054565  cmp     [rax+7CCh], ebx
0x18005456b  jz      short loc_180054581
0x18005456d  mov     r9d, ebx; int
0x180054570  mov     r8d, 1B3h; int
0x180054576  mov     rdx, r13; char *
0x180054579  mov     rcx, rax; this
0x18005457c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054581  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054586  cmp     al, 1
0x180054588  jb      loc_18005474E
0x18005458e  mov     edx, 40h ; '@'
0x180054593  jmp     loc_180054730
0x180054598  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005459f  test    rcx, rcx
0x1800545a2  jnz     short loc_1800545E5
0x1800545a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800545aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800545b1  mov     rcx, rax
0x1800545b4  test    rax, rax
0x1800545b7  jz      short loc_1800545D7
0x1800545b9  mov     rax, [rax]
0x1800545bc  mov     edx, 7F0h
0x1800545c1  mov     rax, [rax+8]
0x1800545c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545ca  test    eax, eax
0x1800545cc  jz      short loc_1800545D7
0x1800545ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800545d5  jmp     short loc_1800545E5
0x1800545d7  lea     rcx, qword_180069A90; this
0x1800545de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800545e5  cmp     [rcx+8], r12b
0x1800545e9  jz      short loc_18005460C
0x1800545eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800545f0  cmp     [rax+7CCh], ebx
0x1800545f6  jz      short loc_18005460C
0x1800545f8  mov     r9d, ebx; int
0x1800545fb  mov     r8d, 1AFh; int
0x180054601  mov     rdx, r13; char *
0x180054604  mov     rcx, rax; this
0x180054607  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005460c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054611  cmp     al, 1
0x180054613  jb      loc_18005474E
0x180054619  mov     edx, 3Fh ; '?'
0x18005461e  jmp     loc_180054730
0x180054623  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005462a  test    rcx, rcx
0x18005462d  jnz     short loc_180054670
0x18005462f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054635  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005463c  mov     rcx, rax
0x18005463f  test    rax, rax
0x180054642  jz      short loc_180054662
0x180054644  mov     rax, [rax]
0x180054647  mov     edx, 7F0h
0x18005464c  mov     rax, [rax+8]
0x180054650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054655  test    eax, eax
0x180054657  jz      short loc_180054662
0x180054659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054660  jmp     short loc_180054670
0x180054662  lea     rcx, qword_180069A90; this
0x180054669  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054670  cmp     [rcx+8], r12b
0x180054674  jz      short loc_180054697
0x180054676  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005467b  cmp     [rax+7CCh], ebx
0x180054681  jz      short loc_180054697
0x180054683  mov     r9d, ebx; int
0x180054686  mov     r8d, 1ACh; int
0x18005468c  mov     rdx, r13; char *
0x18005468f  mov     rcx, rax; this
0x180054692  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054697  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005469c  cmp     al, 1
0x18005469e  jb      loc_18005474E
0x1800546a4  mov     edx, 3Eh ; '>'
0x1800546a9  jmp     loc_180054730
0x1800546ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546b5  test    rcx, rcx
0x1800546b8  jnz     short loc_1800546FB
0x1800546ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800546c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546c7  mov     rcx, rax
0x1800546ca  test    rax, rax
0x1800546cd  jz      short loc_1800546ED
0x1800546cf  mov     rax, [rax]
0x1800546d2  mov     edx, 7F0h
0x1800546d7  mov     rax, [rax+8]
0x1800546db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546e0  test    eax, eax
0x1800546e2  jz      short loc_1800546ED
0x1800546e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546eb  jmp     short loc_1800546FB
0x1800546ed  lea     rcx, qword_180069A90; this
0x1800546f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800546fb  cmp     [rcx+8], r12b
0x1800546ff  jz      short loc_180054722
0x180054701  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054706  cmp     [rax+7CCh], ebx
0x18005470c  jz      short loc_180054722
0x18005470e  mov     r9d, ebx; int
0x180054711  mov     r8d, 1ABh; int
0x180054717  mov     rdx, r13; char *
0x18005471a  mov     rcx, rax; this
0x18005471d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054722  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054727  cmp     al, 1
0x180054729  jb      short loc_18005474E
0x18005472b  mov     edx, 3Dh ; '='
0x180054730  mov     rcx, cs:WPP_GLOBAL_Control
0x180054737  lea     r8, WPP_363825162bad371b7f2cc59a20a496c3_Traceguids
0x18005473e  mov     r9, rsi
0x180054741  mov     [rsp+70h+var_50], ebx
0x180054745  mov     rcx, [rcx+10h]
0x180054749  call    WPP_SF_qd
0x18005474e  lea     rcx, [rbp+pvar]; pvar
0x180054752  call    cs:__imp_PropVariantClear
0x180054758  lea     rcx, [rbp+var_40]; this
0x18005475c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054761  mov     eax, ebx
0x180054763  mov     rcx, [rbp+var_8]
0x180054767  xor     rcx, rsp; StackCookie
0x18005476a  call    __security_check_cookie
0x18005476f  mov     rbx, [rsp+70h+arg_10]
0x180054777  add     rsp, 70h
0x18005477b  pop     r15
0x18005477d  pop     r14
0x18005477f  pop     r13
0x180054781  pop     r12
0x180054783  pop     rdi
0x180054784  pop     rsi
0x180054785  pop     rbp
0x180054786  retn
```
