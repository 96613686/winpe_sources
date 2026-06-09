# CMFSourceBufferingSupport::_GetMaxBitrateFromDLNAProfileID(IMFAttributes *,ulong *)

- ea: `0x18006eed8`
- end: `0x18006f0c1`
- name: `?_GetMaxBitrateFromDLNAProfileID@CMFSourceBufferingSupport@@IEAAJPEAUIMFAttributes@@PEAK@Z`
- size: `489`
- prototype: `__int64 __fastcall(CMFSourceBufferingSupport *__hidden this, struct IMFAttributes *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800681cc`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x18006eed8`
- `0x180074160`
- `0x180087490`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f090`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006f030`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006f030`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ef4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ef4f`

## pseudocode

```c
__int64 __fastcall CMFSourceBufferingSupport::_GetMaxBitrateFromDLNAProfileID(
        CMFSourceBufferingSupport *this,
        struct IMFAttributes *a2,
        unsigned int *a3)
{
  HRESULT (__stdcall *GetAllocatedString)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rax
  int v6; // edi
  CallStackTracing *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  const struct CMFSourceBufferingSupport::SDLNAProfileIDBitrate near *const *i; // rbx
  __int64 v11; // rdx
  _BYTE v13[8]; // [rsp+30h] [rbp-48h] BYREF
  LPCWCH lpString1; // [rsp+38h] [rbp-40h] BYREF

  GetAllocatedString = a2->lpVtbl->GetAllocatedString;
  lpString1 = 0;
  v6 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, LPCWCH *, _QWORD))GetAllocatedString)(
         a2,
         &MF_BYTESTREAM_DLNA_PROFILE_ID,
         &lpString1,
         0);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v13,
    "CMFSourceBufferingSupport::_GetMaxBitrateFromDLNAProfileID",
    1491);
  if ( v6 >= 0 )
  {
    v6 = -2147467259;
    for ( i = &CMFSourceBufferingSupport::s_pDLNAProfileIDBitrates; *i; i += 2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( lpString1[v11] );
      if ( (int)v11 >= *((_DWORD *)i + 2) )
        LODWORD(v11) = *((_DWORD *)i + 2);
      if ( CompareStringOrdinal(lpString1, v11, *(LPCWCH *)i, -1, 1) == 2 )
      {
        *a3 = *((_DWORD *)i + 3);
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_qSD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            13,
            (unsigned int)&WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
            (_DWORD)this,
            (__int64)lpString1,
            *((_DWORD *)i + 3));
        v6 = 0;
        break;
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFSourceBufferingSupport::_GetMaxBitrateFromDLNAProfileID",
          1491,
          v6);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids, this, v6);
  }
  CoTaskMemFree((LPVOID)lpString1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006eed8  push    rbx
0x18006eeda  push    rbp
0x18006eedb  push    rsi
0x18006eedc  push    rdi
0x18006eedd  push    r14
0x18006eedf  sub     rsp, 50h
0x18006eee3  mov     rax, cs:__security_cookie
0x18006eeea  xor     rax, rsp
0x18006eeed  mov     [rsp+78h+var_38], rax
0x18006eef2  mov     rax, [rdx]
0x18006eef5  mov     r10, rdx
0x18006eef8  mov     r14, r8
0x18006eefb  lea     rdx, MF_BYTESTREAM_DLNA_PROFILE_ID
0x18006ef02  mov     rsi, rcx
0x18006ef05  lea     r8, [rsp+78h+lpString1]
0x18006ef0a  xor     ebp, ebp
0x18006ef0c  xor     r9d, r9d
0x18006ef0f  mov     rax, [rax+68h]
0x18006ef13  mov     rcx, r10
0x18006ef16  mov     [rsp+78h+lpString1], rbp
0x18006ef1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef20  mov     ebx, 5D3h
0x18006ef25  lea     rdx, aCmfsourcebuffe; "CMFSourceBufferingSupport::_GetMaxBitra"...
0x18006ef2c  mov     r8d, ebx; int
0x18006ef2f  lea     rcx, [rsp+78h+var_48]; this
0x18006ef34  mov     edi, eax
0x18006ef36  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006ef3b  test    edi, edi
0x18006ef3d  jns     loc_18006EFF3
0x18006ef43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef4a  test    rcx, rcx
0x18006ef4d  jnz     short loc_18006EF96
0x18006ef4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ef56  nop     dword ptr [rax+rax+00h]
0x18006ef5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef62  mov     rcx, rax
0x18006ef65  test    rax, rax
0x18006ef68  jz      short loc_18006EF88
0x18006ef6a  mov     rax, [rax]
0x18006ef6d  mov     edx, 7F0h
0x18006ef72  mov     rax, [rax+8]
0x18006ef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef7b  test    eax, eax
0x18006ef7d  jz      short loc_18006EF88
0x18006ef7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef86  jmp     short loc_18006EF96
0x18006ef88  lea     rcx, qword_1800EB130; this
0x18006ef8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef96  cmp     [rcx+8], bpl
0x18006ef9a  jz      short loc_18006EFBE
0x18006ef9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006efa1  cmp     [rax+7CCh], edi
0x18006efa7  jz      short loc_18006EFBE
0x18006efa9  mov     r9d, edi; int
0x18006efac  lea     rdx, aCmfsourcebuffe; "CMFSourceBufferingSupport::_GetMaxBitra"...
0x18006efb3  mov     r8d, ebx; int
0x18006efb6  mov     rcx, rax; this
0x18006efb9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006efbe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006efc5  jb      loc_18006F08B
0x18006efcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006efd2  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x18006efd9  mov     edx, 0Ch
0x18006efde  mov     [rsp+78h+bIgnoreCase], edi
0x18006efe2  mov     r9, rsi
0x18006efe5  mov     rcx, [rcx+10h]
0x18006efe9  call    WPP_SF_qD
0x18006efee  jmp     loc_18006F08B
0x18006eff3  mov     edi, 80004005h
0x18006eff8  lea     rbx, ?s_pDLNAProfileIDBitrates@CMFSourceBufferingSupport@@1QBUSDLNAProfileIDBitrate@1@B; CMFSourceBufferingSupport::SDLNAProfileIDBitrate const near * const CMFSourceBufferingSupport::s_pDLNAProfileIDBitrates
0x18006efff  mov     r8, [rbx]; lpString2
0x18006f002  test    r8, r8
0x18006f005  jz      loc_18006F08B
0x18006f00b  mov     rcx, [rsp+78h+lpString1]; lpString1
0x18006f010  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006f014  inc     rdx
0x18006f017  cmp     [rcx+rdx*2], bp
0x18006f01b  jnz     short loc_18006F014
0x18006f01d  cmp     edx, [rbx+8]
0x18006f020  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006f028  cmovge  edx, [rbx+8]; cchCount1
0x18006f02c  or      r9d, 0FFFFFFFFh; cchCount2
0x18006f030  call    cs:__imp_CompareStringOrdinal
0x18006f037  nop     dword ptr [rax+rax+00h]
0x18006f03c  cmp     eax, 2
0x18006f03f  jz      short loc_18006F047
0x18006f041  add     rbx, 10h
0x18006f045  jmp     short loc_18006EFFF
0x18006f047  mov     eax, [rbx+0Ch]
0x18006f04a  mov     [r14], eax
0x18006f04d  cmp     cs:byte_1800EACCB, 8
0x18006f054  jb      short loc_18006F089
0x18006f056  mov     eax, [rbx+0Ch]
0x18006f059  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x18006f060  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f067  mov     edx, 0Dh
0x18006f06c  mov     [rsp+78h+var_50], eax
0x18006f070  mov     r9, rsi
0x18006f073  mov     rax, [rsp+78h+lpString1]
0x18006f078  mov     qword ptr [rsp+78h+bIgnoreCase], rax
0x18006f07d  mov     rcx, [rcx+88h]
0x18006f084  call    WPP_SF_qSD
0x18006f089  mov     edi, ebp
0x18006f08b  mov     rcx, [rsp+78h+lpString1]; pv
0x18006f090  call    cs:__imp_CoTaskMemFree
0x18006f097  nop     dword ptr [rax+rax+00h]
0x18006f09c  lea     rcx, [rsp+78h+var_48]; this
0x18006f0a1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006f0a6  mov     eax, edi
0x18006f0a8  mov     rcx, [rsp+78h+var_38]
0x18006f0ad  xor     rcx, rsp; StackCookie
0x18006f0b0  call    __security_check_cookie
0x18006f0b5  add     rsp, 50h
0x18006f0b9  pop     r14
0x18006f0bb  pop     rdi
0x18006f0bc  pop     rsi
0x18006f0bd  pop     rbp
0x18006f0be  pop     rbx
0x18006f0bf  retn
```
