# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1801f1090`
- end: `0x1801f146b`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `987`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18017d0d8`
- `0x1801f1090`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801f118b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801f118b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801f123c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801f123c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801f10a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801f10dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801f10a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801f10dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f10fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f11ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f1266`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f1314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f13b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f10fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f11ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f1266`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f1314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f13b8`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const PROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  char v33; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 12);
  if ( *(_WORD *)a2 == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 15);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 15, a2);
      if ( v5 >= 0 )
      {
        *((_WORD *)this + 48) = 31;
        v16 = (unsigned __int16 *)CoTaskMemAlloc(*((unsigned int *)a2 + 2));
        this[13] = v16;
        if ( v16 )
        {
          v5 = StringCchCopyW(
                 v16,
                 (unsigned __int64)*((unsigned int *)a2 + 2) >> 1,
                 *((const unsigned __int16 **)a2 + 2));
          if ( v5 < 0 )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( g_wppLevels )
            {
              v10 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v21, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( g_wppLevels )
          {
            v10 = 37;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != v5 )
            CallStackContext::TraceFailure(v15, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( g_wppLevels )
        {
          v10 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v9 + 499) != v5 )
          CallStackContext::TraceFailure(v9, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( g_wppLevels )
      {
        v10 = 35;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CWMMCDIProperty::SetNativeValue", 451);
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v31, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( g_wppLevels )
    {
      v10 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801f1090  push    rbp
0x1801f1092  push    rsi
0x1801f1093  push    rdi
0x1801f1094  push    r12
0x1801f1096  push    r14
0x1801f1098  push    r15
0x1801f109a  sub     rsp, 38h
0x1801f109e  mov     rbp, rcx
0x1801f10a1  mov     rsi, rdx
0x1801f10a4  add     rcx, 60h ; '`'; pvar
0x1801f10a8  call    cs:__imp_PropVariantClear
0x1801f10af  nop     dword ptr [rax+rax+00h]
0x1801f10b4  cmp     word ptr [rsi], 41h ; 'A'
0x1801f10b8  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x1801f10bf  mov     rdx, r14; char *
0x1801f10c2  lea     rcx, [rsp+68h+arg_0]; this
0x1801f10c7  jnz     loc_1801F139A
0x1801f10cd  mov     r8d, 1A7h; int
0x1801f10d3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801f10d8  lea     rcx, [rbp+78h]; pvar
0x1801f10dc  call    cs:__imp_PropVariantClear
0x1801f10e3  nop     dword ptr [rax+rax+00h]
0x1801f10e8  mov     edi, eax
0x1801f10ea  test    eax, eax
0x1801f10ec  jns     loc_1801F1184
0x1801f10f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f10f9  test    rcx, rcx
0x1801f10fc  jnz     short loc_1801F1146
0x1801f10fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f1105  nop     dword ptr [rax+rax+00h]
0x1801f110a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1111  mov     rcx, rax
0x1801f1114  test    rax, rax
0x1801f1117  jz      short loc_1801F1138
0x1801f1119  mov     rax, [rax]
0x1801f111c  mov     edx, 7F0h
0x1801f1121  mov     rax, [rax+8]
0x1801f1125  call    cs:__guard_dispatch_icall_fptr
0x1801f112b  test    eax, eax
0x1801f112d  jz      short loc_1801F1138
0x1801f112f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1136  jmp     short loc_1801F1146
0x1801f1138  lea     rcx, qword_1803CE250; this
0x1801f113f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1146  cmp     byte ptr [rcx+8], 0
0x1801f114a  jz      short loc_1801F116D
0x1801f114c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f1151  cmp     [rax+7CCh], edi
0x1801f1157  jz      short loc_1801F116D
0x1801f1159  mov     r9d, edi; int
0x1801f115c  mov     r8d, 1A7h; int
0x1801f1162  mov     rdx, r14; char *
0x1801f1165  mov     rcx, rax; this
0x1801f1168  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f116d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f1174  jb      loc_1801F1450
0x1801f117a  mov     edx, 23h ; '#'
0x1801f117f  jmp     loc_1801F1432
0x1801f1184  mov     rdx, rsi; pvarSrc
0x1801f1187  lea     rcx, [rbp+78h]; pvarDest
0x1801f118b  call    cs:__imp_PropVariantCopy
0x1801f1192  nop     dword ptr [rax+rax+00h]
0x1801f1197  mov     edi, eax
0x1801f1199  test    eax, eax
0x1801f119b  jns     loc_1801F1233
0x1801f11a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f11a8  test    rcx, rcx
0x1801f11ab  jnz     short loc_1801F11F5
0x1801f11ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f11b4  nop     dword ptr [rax+rax+00h]
0x1801f11b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f11c0  mov     rcx, rax
0x1801f11c3  test    rax, rax
0x1801f11c6  jz      short loc_1801F11E7
0x1801f11c8  mov     rax, [rax]
0x1801f11cb  mov     edx, 7F0h
0x1801f11d0  mov     rax, [rax+8]
0x1801f11d4  call    cs:__guard_dispatch_icall_fptr
0x1801f11da  test    eax, eax
0x1801f11dc  jz      short loc_1801F11E7
0x1801f11de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f11e5  jmp     short loc_1801F11F5
0x1801f11e7  lea     rcx, qword_1803CE250; this
0x1801f11ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f11f5  cmp     byte ptr [rcx+8], 0
0x1801f11f9  jz      short loc_1801F121C
0x1801f11fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f1200  cmp     [rax+7CCh], edi
0x1801f1206  jz      short loc_1801F121C
0x1801f1208  mov     r9d, edi; int
0x1801f120b  mov     r8d, 1A9h; int
0x1801f1211  mov     rdx, r14; char *
0x1801f1214  mov     rcx, rax; this
0x1801f1217  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f121c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f1223  jb      loc_1801F1450
0x1801f1229  mov     edx, 24h ; '$'
0x1801f122e  jmp     loc_1801F1432
0x1801f1233  mov     word ptr [rbp+60h], 1Fh
0x1801f1239  mov     ecx, [rsi+8]; cb
0x1801f123c  call    cs:__imp_CoTaskMemAlloc
0x1801f1243  nop     dword ptr [rax+rax+00h]
0x1801f1248  mov     [rbp+68h], rax
0x1801f124c  test    rax, rax
0x1801f124f  jnz     loc_1801F12EC
0x1801f1255  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f125c  mov     edi, 8007000Eh
0x1801f1261  test    rcx, rcx
0x1801f1264  jnz     short loc_1801F12AE
0x1801f1266  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f126d  nop     dword ptr [rax+rax+00h]
0x1801f1272  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1279  mov     rcx, rax
0x1801f127c  test    rax, rax
0x1801f127f  jz      short loc_1801F12A0
0x1801f1281  mov     rax, [rax]
0x1801f1284  mov     edx, 7F0h
0x1801f1289  mov     rax, [rax+8]
0x1801f128d  call    cs:__guard_dispatch_icall_fptr
0x1801f1293  test    eax, eax
0x1801f1295  jz      short loc_1801F12A0
0x1801f1297  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f129e  jmp     short loc_1801F12AE
0x1801f12a0  lea     rcx, qword_1803CE250; this
0x1801f12a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f12ae  cmp     byte ptr [rcx+8], 0
0x1801f12b2  jz      short loc_1801F12D5
0x1801f12b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f12b9  cmp     [rax+7CCh], edi
0x1801f12bf  jz      short loc_1801F12D5
0x1801f12c1  mov     r9d, edi; int
0x1801f12c4  mov     r8d, 1B6h; int
0x1801f12ca  mov     rdx, r14; char *
0x1801f12cd  mov     rcx, rax; this
0x1801f12d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f12d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f12dc  jb      loc_1801F1450
0x1801f12e2  mov     edx, 25h ; '%'
0x1801f12e7  jmp     loc_1801F1432
0x1801f12ec  mov     edx, [rsi+8]
0x1801f12ef  mov     rcx, rax; unsigned __int16 *
0x1801f12f2  mov     r8, [rsi+10h]; unsigned __int16 *
0x1801f12f6  shr     rdx, 1; unsigned __int64
0x1801f12f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801f12fe  mov     edi, eax
0x1801f1300  test    eax, eax
0x1801f1302  jns     loc_1801F1450
0x1801f1308  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f130f  test    rcx, rcx
0x1801f1312  jnz     short loc_1801F135C
0x1801f1314  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f131b  nop     dword ptr [rax+rax+00h]
0x1801f1320  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1327  mov     rcx, rax
0x1801f132a  test    rax, rax
0x1801f132d  jz      short loc_1801F134E
0x1801f132f  mov     rax, [rax]
0x1801f1332  mov     edx, 7F0h
0x1801f1337  mov     rax, [rax+8]
0x1801f133b  call    cs:__guard_dispatch_icall_fptr
0x1801f1341  test    eax, eax
0x1801f1343  jz      short loc_1801F134E
0x1801f1345  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f134c  jmp     short loc_1801F135C
0x1801f134e  lea     rcx, qword_1803CE250; this
0x1801f1355  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f135c  cmp     byte ptr [rcx+8], 0
0x1801f1360  jz      short loc_1801F1383
0x1801f1362  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f1367  cmp     [rax+7CCh], edi
0x1801f136d  jz      short loc_1801F1383
0x1801f136f  mov     r9d, edi; int
0x1801f1372  mov     r8d, 1BEh; int
0x1801f1378  mov     rdx, r14; char *
0x1801f137b  mov     rcx, rax; this
0x1801f137e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f1383  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f138a  jb      loc_1801F1450
0x1801f1390  mov     edx, 26h ; '&'
0x1801f1395  jmp     loc_1801F1432
0x1801f139a  mov     esi, 1C3h
0x1801f139f  mov     r8d, esi; int
0x1801f13a2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801f13a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f13ae  mov     edi, 8000FFFFh
0x1801f13b3  test    rcx, rcx
0x1801f13b6  jnz     short loc_1801F1400
0x1801f13b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f13bf  nop     dword ptr [rax+rax+00h]
0x1801f13c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f13cb  mov     rcx, rax
0x1801f13ce  test    rax, rax
0x1801f13d1  jz      short loc_1801F13F2
0x1801f13d3  mov     rax, [rax]
0x1801f13d6  mov     edx, 7F0h
0x1801f13db  mov     rax, [rax+8]
0x1801f13df  call    cs:__guard_dispatch_icall_fptr
0x1801f13e5  test    eax, eax
0x1801f13e7  jz      short loc_1801F13F2
0x1801f13e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f13f0  jmp     short loc_1801F1400
0x1801f13f2  lea     rcx, qword_1803CE250; this
0x1801f13f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f1400  cmp     byte ptr [rcx+8], 0
0x1801f1404  jz      short loc_1801F1424
0x1801f1406  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f140b  cmp     [rax+7CCh], edi
0x1801f1411  jz      short loc_1801F1424
0x1801f1413  mov     r9d, edi; int
0x1801f1416  mov     r8d, esi; int
0x1801f1419  mov     rdx, r14; char *
0x1801f141c  mov     rcx, rax; this
0x1801f141f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f1424  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f142b  jb      short loc_1801F1450
0x1801f142d  mov     edx, 27h ; '''
0x1801f1432  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f1439  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1801f1440  mov     r9, rbp
0x1801f1443  mov     [rsp+68h+var_48], edi
0x1801f1447  mov     rcx, [rcx+10h]
0x1801f144b  call    WPP_SF_qD
0x1801f1450  lea     rcx, [rsp+68h+arg_0]; this
0x1801f1455  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801f145a  mov     eax, edi
0x1801f145c  add     rsp, 38h
0x1801f1460  pop     r15
0x1801f1462  pop     r14
0x1801f1464  pop     r12
0x1801f1466  pop     rdi
0x1801f1467  pop     rsi
0x1801f1468  pop     rbp
0x1801f1469  retn
```
