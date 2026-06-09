# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x1801caf10`
- end: `0x1801cb3e8`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1240`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18017d0d8`
- `0x1801caf10`
- `0x180273258`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801cb026`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801cb026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801cb197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801cb197`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801caf4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801caf73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801caf4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801caf73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801caf95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb04b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb0ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb1bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb32c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801caf95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb04b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb0ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb1bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb32c`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const PROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // esi
  __int64 v7; // r8
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int v22; // eax
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  int v28; // edi
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  char v42; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v43; // [rsp+80h] [rbp+50h] BYREF

  v43 = 0;
  if ( *(_WORD *)a2 == 31 )
  {
    v4 = 0;
    PropVariantClear(this + 15);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CWMMCDIProperty::SetShellValue", 372);
    v6 = PropVariantClear(this + 12);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 12, a2);
      if ( v6 >= 0 )
      {
        *((_WORD *)this + 60) = 65;
        v6 = StringCchLengthW(*((const unsigned __int16 **)a2 + 1), 0x7FFFFFFFu, &v43);
        if ( v6 >= 0 )
        {
          v22 = 2 * v43 + 2;
          *((_DWORD *)this + 32) = v22;
          v23 = (unsigned __int16 *)CoTaskMemAlloc(v22);
          this[17] = v23;
          if ( v23 )
          {
            v28 = StringCchCopyW(
                    v23,
                    (unsigned __int64)*((unsigned int *)this + 32) >> 1,
                    *((const unsigned __int16 **)a2 + 1));
            if ( v28 >= 0 )
              goto LABEL_69;
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v33 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v28 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 398, v28);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v30 = 33;
          }
          else
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            v28 = -2147024882;
            if ( *((_BYTE *)v26 + 8) )
            {
              v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v29 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v29, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v30 = 32;
          }
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v30,
            &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            v28);
          goto LABEL_69;
        }
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
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
          if ( *((_DWORD *)v21 + 499) != v6 )
            CallStackContext::TraceFailure(v21, "CWMMCDIProperty::SetShellValue", 386, v6);
        }
        if ( g_wppLevels )
        {
          v11 = 31;
          goto LABEL_13;
        }
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v6 )
            CallStackContext::TraceFailure(v16, "CWMMCDIProperty::SetShellValue", 374, v6);
        }
        if ( g_wppLevels )
        {
          v11 = 30;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v6 )
          CallStackContext::TraceFailure(v10, "CWMMCDIProperty::SetShellValue", 372, v6);
      }
      if ( g_wppLevels )
      {
        v11 = 29;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CWMMCDIProperty::SetShellValue", 403);
    v38 = (__int64 *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v40 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v40, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
  }
LABEL_69:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return v4;
}

```

## disassembly

```asm
0x1801caf10  mov     [rsp-38h+arg_0], rbx
0x1801caf15  push    rbp
0x1801caf16  push    rsi
0x1801caf17  push    rdi
0x1801caf18  push    r12
0x1801caf1a  push    r13
0x1801caf1c  push    r14
0x1801caf1e  push    r15
0x1801caf20  mov     rbp, rsp
0x1801caf23  sub     rsp, 30h
0x1801caf27  mov     eax, 1Fh
0x1801caf2c  mov     [rbp+arg_10], 0
0x1801caf34  mov     rdi, rdx
0x1801caf37  mov     rbx, rcx
0x1801caf3a  cmp     [rdx], ax
0x1801caf3d  jnz     loc_1801CB2FF
0x1801caf43  add     rcx, 78h ; 'x'; pvar
0x1801caf47  xor     r13d, r13d
0x1801caf4a  call    cs:__imp_PropVariantClear
0x1801caf51  nop     dword ptr [rax+rax+00h]
0x1801caf56  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1801caf5d  mov     r8d, 174h; int
0x1801caf63  mov     rdx, r14; char *
0x1801caf66  lea     rcx, [rbp+arg_8]; this
0x1801caf6a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801caf6f  lea     rcx, [rbx+60h]; pvar
0x1801caf73  call    cs:__imp_PropVariantClear
0x1801caf7a  nop     dword ptr [rax+rax+00h]
0x1801caf7f  mov     esi, eax
0x1801caf81  test    eax, eax
0x1801caf83  jns     loc_1801CB01F
0x1801caf89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801caf90  test    rcx, rcx
0x1801caf93  jnz     short loc_1801CAFDD
0x1801caf95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801caf9c  nop     dword ptr [rax+rax+00h]
0x1801cafa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cafa8  mov     rcx, rax
0x1801cafab  test    rax, rax
0x1801cafae  jz      short loc_1801CAFCF
0x1801cafb0  mov     rax, [rax]
0x1801cafb3  mov     edx, 7F0h
0x1801cafb8  mov     rax, [rax+8]
0x1801cafbc  call    cs:__guard_dispatch_icall_fptr
0x1801cafc2  test    eax, eax
0x1801cafc4  jz      short loc_1801CAFCF
0x1801cafc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cafcd  jmp     short loc_1801CAFDD
0x1801cafcf  lea     rcx, qword_1803CE250; this
0x1801cafd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cafdd  cmp     [rcx+8], r13b
0x1801cafe1  jz      short loc_1801CB004
0x1801cafe3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cafe8  cmp     [rax+7CCh], esi
0x1801cafee  jz      short loc_1801CB004
0x1801caff0  mov     r9d, esi; int
0x1801caff3  mov     r8d, 174h; int
0x1801caff9  mov     rdx, r14; char *
0x1801caffc  mov     rcx, rax; this
0x1801cafff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb004  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb00b  jb      loc_1801CB3C6
0x1801cb011  mov     edx, 1Dh
0x1801cb016  mov     [rsp+30h+var_10], esi
0x1801cb01a  jmp     loc_1801CB3AC
0x1801cb01f  mov     rdx, rdi; pvarSrc
0x1801cb022  lea     rcx, [rbx+60h]; pvarDest
0x1801cb026  call    cs:__imp_PropVariantCopy
0x1801cb02d  nop     dword ptr [rax+rax+00h]
0x1801cb032  xor     r15d, r15d
0x1801cb035  mov     esi, eax
0x1801cb037  test    eax, eax
0x1801cb039  jns     loc_1801CB0D1
0x1801cb03f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb046  test    rcx, rcx
0x1801cb049  jnz     short loc_1801CB093
0x1801cb04b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb052  nop     dword ptr [rax+rax+00h]
0x1801cb057  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb05e  mov     rcx, rax
0x1801cb061  test    rax, rax
0x1801cb064  jz      short loc_1801CB085
0x1801cb066  mov     rax, [rax]
0x1801cb069  mov     edx, 7F0h
0x1801cb06e  mov     rax, [rax+8]
0x1801cb072  call    cs:__guard_dispatch_icall_fptr
0x1801cb078  test    eax, eax
0x1801cb07a  jz      short loc_1801CB085
0x1801cb07c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb083  jmp     short loc_1801CB093
0x1801cb085  lea     rcx, qword_1803CE250; this
0x1801cb08c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb093  cmp     [rcx+8], r15b
0x1801cb097  jz      short loc_1801CB0BA
0x1801cb099  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb09e  cmp     [rax+7CCh], esi
0x1801cb0a4  jz      short loc_1801CB0BA
0x1801cb0a6  mov     r9d, esi; int
0x1801cb0a9  mov     r8d, 176h; int
0x1801cb0af  mov     rdx, r14; char *
0x1801cb0b2  mov     rcx, rax; this
0x1801cb0b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb0ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb0c1  jb      loc_1801CB3C6
0x1801cb0c7  mov     edx, 1Eh
0x1801cb0cc  jmp     loc_1801CB016
0x1801cb0d1  mov     word ptr [rbx+78h], 41h ; 'A'
0x1801cb0d7  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1801cb0db  mov     rcx, [rdi+8]; unsigned __int16 *
0x1801cb0df  mov     edx, 7FFFFFFFh; unsigned __int64
0x1801cb0e4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801cb0e9  mov     esi, eax
0x1801cb0eb  test    eax, eax
0x1801cb0ed  jns     loc_1801CB185
0x1801cb0f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb0fa  test    rcx, rcx
0x1801cb0fd  jnz     short loc_1801CB147
0x1801cb0ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb106  nop     dword ptr [rax+rax+00h]
0x1801cb10b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb112  mov     rcx, rax
0x1801cb115  test    rax, rax
0x1801cb118  jz      short loc_1801CB139
0x1801cb11a  mov     rax, [rax]
0x1801cb11d  mov     edx, 7F0h
0x1801cb122  mov     rax, [rax+8]
0x1801cb126  call    cs:__guard_dispatch_icall_fptr
0x1801cb12c  test    eax, eax
0x1801cb12e  jz      short loc_1801CB139
0x1801cb130  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb137  jmp     short loc_1801CB147
0x1801cb139  lea     rcx, qword_1803CE250; this
0x1801cb140  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb147  cmp     [rcx+8], r15b
0x1801cb14b  jz      short loc_1801CB16E
0x1801cb14d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb152  cmp     [rax+7CCh], esi
0x1801cb158  jz      short loc_1801CB16E
0x1801cb15a  mov     r9d, esi; int
0x1801cb15d  mov     r8d, 182h; int
0x1801cb163  mov     rdx, r14; char *
0x1801cb166  mov     rcx, rax; this
0x1801cb169  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb16e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb175  jb      loc_1801CB3C6
0x1801cb17b  mov     edx, 1Fh
0x1801cb180  jmp     loc_1801CB016
0x1801cb185  mov     eax, dword ptr [rbp+arg_10]
0x1801cb188  lea     eax, ds:2[rax*2]
0x1801cb18f  mov     ecx, eax; cb
0x1801cb191  mov     [rbx+80h], eax
0x1801cb197  call    cs:__imp_CoTaskMemAlloc
0x1801cb19e  nop     dword ptr [rax+rax+00h]
0x1801cb1a3  mov     [rbx+88h], rax
0x1801cb1aa  test    rax, rax
0x1801cb1ad  jnz     loc_1801CB24E
0x1801cb1b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb1ba  test    rcx, rcx
0x1801cb1bd  jnz     short loc_1801CB207
0x1801cb1bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb1c6  nop     dword ptr [rax+rax+00h]
0x1801cb1cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb1d2  mov     rcx, rax
0x1801cb1d5  test    rax, rax
0x1801cb1d8  jz      short loc_1801CB1F9
0x1801cb1da  mov     rax, [rax]
0x1801cb1dd  mov     edx, 7F0h
0x1801cb1e2  mov     rax, [rax+8]
0x1801cb1e6  call    cs:__guard_dispatch_icall_fptr
0x1801cb1ec  test    eax, eax
0x1801cb1ee  jz      short loc_1801CB1F9
0x1801cb1f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb1f7  jmp     short loc_1801CB207
0x1801cb1f9  lea     rcx, qword_1803CE250; this
0x1801cb200  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb207  mov     edi, 8007000Eh
0x1801cb20c  cmp     [rcx+8], r15b
0x1801cb210  jz      short loc_1801CB233
0x1801cb212  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb217  cmp     [rax+7CCh], edi
0x1801cb21d  jz      short loc_1801CB233
0x1801cb21f  mov     r9d, edi; int
0x1801cb222  mov     r8d, 186h; int
0x1801cb228  mov     rdx, r14; char *
0x1801cb22b  mov     rcx, rax; this
0x1801cb22e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb233  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb23a  jb      loc_1801CB3C6
0x1801cb240  mov     edx, 20h ; ' '
0x1801cb245  mov     [rsp+30h+var_10], edi
0x1801cb249  jmp     loc_1801CB3AC
0x1801cb24e  mov     edx, [rbx+80h]
0x1801cb254  mov     rcx, rax; unsigned __int16 *
0x1801cb257  mov     r8, [rdi+8]; unsigned __int16 *
0x1801cb25b  shr     rdx, 1; unsigned __int64
0x1801cb25e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801cb263  mov     edi, eax
0x1801cb265  test    eax, eax
0x1801cb267  jns     loc_1801CB3C6
0x1801cb26d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb274  test    rcx, rcx
0x1801cb277  jnz     short loc_1801CB2C1
0x1801cb279  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb280  nop     dword ptr [rax+rax+00h]
0x1801cb285  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb28c  mov     rcx, rax
0x1801cb28f  test    rax, rax
0x1801cb292  jz      short loc_1801CB2B3
0x1801cb294  mov     rax, [rax]
0x1801cb297  mov     edx, 7F0h
0x1801cb29c  mov     rax, [rax+8]
0x1801cb2a0  call    cs:__guard_dispatch_icall_fptr
0x1801cb2a6  test    eax, eax
0x1801cb2a8  jz      short loc_1801CB2B3
0x1801cb2aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb2b1  jmp     short loc_1801CB2C1
0x1801cb2b3  lea     rcx, qword_1803CE250; this
0x1801cb2ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb2c1  cmp     [rcx+8], r15b
0x1801cb2c5  jz      short loc_1801CB2E8
0x1801cb2c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb2cc  cmp     [rax+7CCh], edi
0x1801cb2d2  jz      short loc_1801CB2E8
0x1801cb2d4  mov     r9d, edi; int
0x1801cb2d7  mov     r8d, 18Eh; int
0x1801cb2dd  mov     rdx, r14; char *
0x1801cb2e0  mov     rcx, rax; this
0x1801cb2e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb2e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb2ef  jb      loc_1801CB3C6
0x1801cb2f5  mov     edx, 21h ; '!'
0x1801cb2fa  jmp     loc_1801CB245
0x1801cb2ff  mov     edi, 193h
0x1801cb304  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1801cb30b  mov     r8d, edi; int
0x1801cb30e  lea     rcx, [rbp+arg_8]; this
0x1801cb312  mov     rdx, r14; char *
0x1801cb315  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801cb31a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb321  mov     r13d, 8000FFFFh
0x1801cb327  test    rcx, rcx
0x1801cb32a  jnz     short loc_1801CB374
0x1801cb32c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb333  nop     dword ptr [rax+rax+00h]
0x1801cb338  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb33f  mov     rcx, rax
0x1801cb342  test    rax, rax
0x1801cb345  jz      short loc_1801CB366
0x1801cb347  mov     rax, [rax]
0x1801cb34a  mov     edx, 7F0h
0x1801cb34f  mov     rax, [rax+8]
0x1801cb353  call    cs:__guard_dispatch_icall_fptr
0x1801cb359  test    eax, eax
0x1801cb35b  jz      short loc_1801CB366
0x1801cb35d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb364  jmp     short loc_1801CB374
0x1801cb366  lea     rcx, qword_1803CE250; this
0x1801cb36d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb374  cmp     byte ptr [rcx+8], 0
0x1801cb378  jz      short loc_1801CB399
0x1801cb37a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb37f  cmp     [rax+7CCh], r13d
0x1801cb386  jz      short loc_1801CB399
0x1801cb388  mov     r9d, r13d; int
0x1801cb38b  mov     r8d, edi; int
0x1801cb38e  mov     rdx, r14; char *
0x1801cb391  mov     rcx, rax; this
0x1801cb394  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb399  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb3a0  jb      short loc_1801CB3C6
0x1801cb3a2  mov     edx, 22h ; '"'
0x1801cb3a7  mov     [rsp+30h+var_10], r13d
0x1801cb3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cb3b3  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1801cb3ba  mov     r9, rbx
0x1801cb3bd  mov     rcx, [rcx+10h]
0x1801cb3c1  call    WPP_SF_qD
0x1801cb3c6  lea     rcx, [rbp+arg_8]; this
0x1801cb3ca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801cb3cf  mov     rbx, [rsp+30h+arg_0]
0x1801cb3d4  mov     eax, r13d
0x1801cb3d7  add     rsp, 30h
0x1801cb3db  pop     r15
0x1801cb3dd  pop     r14
0x1801cb3df  pop     r13
0x1801cb3e1  pop     r12
0x1801cb3e3  pop     rdi
0x1801cb3e4  pop     rsi
0x1801cb3e5  pop     rbp
0x1801cb3e6  retn
```
