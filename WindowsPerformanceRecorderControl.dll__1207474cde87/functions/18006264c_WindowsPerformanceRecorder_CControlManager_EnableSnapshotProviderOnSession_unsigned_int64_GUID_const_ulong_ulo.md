# WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(unsigned __int64,_GUID const &,ulong,ulong,ulong *,ulong,bool)

- ea: `0x18006264c`
- end: `0x180062882`
- name: `?EnableSnapshotProviderOnSession@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEBU_GUID@@KKPEAKK_N@Z`
- size: `566`
- prototype: `int(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int64, const struct _GUID *, unsigned int, unsigned int, unsigned int *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180049630`
- `0x180049970`

## callees

- `0x18000829c`
- `0x180009a84`
- `0x180009b40`
- `0x18001e6e0`
- `0x18004ece0`
- `0x18004ed10`
- `0x18004f1d0`
- `0x18006264c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18006282a`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18006282a`

## string_xrefs

- `0x180062739`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::EnableSnapshotProviderOnSession(
        WindowsPerformanceRecorder::CControlManager *this,
        TRACEHANDLE a2,
        const struct _GUID *a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7,
        bool a8)
{
  __int64 (__fastcall *v11)(TRACEHANDLE, const struct _GUID *, __int64, __int64, _QWORD, _QWORD, int, __int128 *); // rdi
  __int64 v12; // r9
  signed int v13; // ebx
  unsigned int v15; // eax
  __int64 v16; // r9
  char *v17; // rbx
  ULONG v18; // eax
  unsigned int v19; // edi
  const char *v20; // [rsp+28h] [rbp-91h]
  int v21; // [rsp+50h] [rbp-69h] BYREF
  int v22; // [rsp+58h] [rbp-61h] BYREF
  struct WindowsPerformanceRecorder::CWPRControl *v23[2]; // [rsp+60h] [rbp-59h] BYREF
  __int128 v24; // [rsp+70h] [rbp-49h] BYREF
  __int128 v25; // [rsp+80h] [rbp-39h]
  __int128 v26; // [rsp+90h] [rbp-29h]
  __int128 v27; // [rsp+A0h] [rbp-19h] BYREF

  v23[1] = (struct WindowsPerformanceRecorder::CWPRControl *)-2LL;
  v21 = a4;
  v22 = 1;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v23[0] = 0;
  if ( (int)WindowsPerformanceRecorder::CWPRControl::GetInstance(v23) < 0 )
    return 50;
  v11 = (__int64 (__fastcall *)(TRACEHANDLE, const struct _GUID *, __int64, __int64, _QWORD, _QWORD, int, __int128 *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)v23[0] + 32);
  if ( !v11 )
    return 50;
  v24 = 0;
  v25 = 0;
  HIDWORD(v27) = -2147483644;
  *(_QWORD *)&v27 = a6;
  DWORD2(v27) = 4 * a7;
  LODWORD(v24) = 2;
  *(_QWORD *)&v26 = &v27;
  *((_QWORD *)&v26 + 1) = 1;
  if ( a8 )
  {
    v13 = (*(__int64 (__fastcall **)(char *, TRACEHANDLE, int *, int *))(*((_QWORD *)this + 26) + 80LL))(
            (char *)this + 208,
            a2,
            &v21,
            &v22);
    if ( v13 < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "EnableSnapshotProviderOnSession",
        (const char *)0x108,
        v13,
        "COMGUARD",
        v20);
      return (unsigned int)v13;
    }
  }
  LOBYTE(v12) = 4;
  v15 = v11(a2, a3, 1, v12, 0, 0, 10000, &v24);
  if ( v15 )
    return ATL::AtlHresultFromWin32(v15);
  LOBYTE(v16) = 4;
  v15 = v11(a2, a3, 2, v16, 0, 0, 600000, &v24);
  if ( v15 )
    return ATL::AtlHresultFromWin32(v15);
  if ( a8 )
  {
    v23[0] = 0;
    v17 = (char *)operator new(0x18u);
    *(_DWORD *)v17 = v21;
    *((_WORD *)v17 + 2) = 1;
    *(struct _GUID *)(v17 + 8) = *a3;
    v18 = TraceSetInformation(a2, TracePeriodicCaptureStateListInfo, v17, 0x18u);
    if ( v18 )
    {
      v19 = ATL::AtlHresultFromWin32(v18);
      operator delete(v17);
      return v19;
    }
    operator delete(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18006264c  push    rbp
0x18006264e  push    rbx
0x18006264f  push    rsi
0x180062650  push    rdi
0x180062651  push    r13
0x180062653  push    r14
0x180062655  push    r15
0x180062657  lea     rbp, [rsp-7]
0x18006265c  sub     rsp, 0C0h
0x180062663  mov     [rbp+37h+var_88], 0FFFFFFFFFFFFFFFEh
0x18006266b  mov     rax, cs:__security_cookie
0x180062672  xor     rax, rsp
0x180062675  mov     [rbp+37h+var_40], rax
0x180062679  mov     r15, r8
0x18006267c  mov     r14, rdx
0x18006267f  mov     r13, rcx
0x180062682  mov     [rbp+37h+var_A0], r9d
0x180062686  mov     rbx, [rbp+37h+arg_28]
0x18006268a  mov     esi, 1
0x18006268f  mov     [rbp+37h+var_98], esi
0x180062692  xorps   xmm0, xmm0
0x180062695  movups  [rbp+37h+var_80], xmm0
0x180062699  movups  [rbp+37h+var_70], xmm0
0x18006269d  movups  [rbp+37h+var_60], xmm0
0x1800626a1  movups  [rbp+37h+var_50], xmm0
0x1800626a5  mov     [rbp+37h+var_90], 0
0x1800626ad  lea     rcx, [rbp+37h+var_90]; struct WindowsPerformanceRecorder::CWPRControl **
0x1800626b1  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x1800626b6  test    eax, eax
0x1800626b8  js      loc_18006285F
0x1800626be  mov     rcx, [rbp+37h+var_90]
0x1800626c2  add     rcx, 20h ; ' '
0x1800626c6  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800626cb  mov     rdi, rax
0x1800626ce  test    rax, rax
0x1800626d1  jz      loc_18006285F
0x1800626d7  xorps   xmm0, xmm0
0x1800626da  movups  [rbp+37h+var_80], xmm0
0x1800626de  movups  [rbp+37h+var_70], xmm0
0x1800626e2  movups  [rbp+37h+var_60], xmm0
0x1800626e6  mov     dword ptr [rbp+37h+var_50+0Ch], 80000004h
0x1800626ed  mov     qword ptr [rbp+37h+var_50], rbx
0x1800626f1  mov     ecx, [rbp+37h+arg_30]
0x1800626f4  shl     ecx, 2
0x1800626f7  mov     dword ptr [rbp+37h+var_50+8], ecx
0x1800626fa  mov     dword ptr [rbp+37h+var_80], 2
0x180062701  lea     rax, [rbp+37h+var_50]
0x180062705  mov     qword ptr [rbp+37h+var_60], rax
0x180062709  mov     dword ptr [rbp+37h+var_60+8], esi
0x18006270c  mov     sil, [rbp+37h+arg_38]
0x180062710  test    sil, sil
0x180062713  jz      short loc_180062766
0x180062715  lea     rcx, [r13+0D0h]
0x18006271c  mov     rax, [rcx]
0x18006271f  lea     r9, [rbp+37h+var_98]
0x180062723  lea     r8, [rbp+37h+var_A0]
0x180062727  mov     rdx, r14
0x18006272a  mov     rax, [rax+50h]
0x18006272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062733  mov     ebx, eax
0x180062735  test    eax, eax
0x180062737  jns     short loc_180062766
0x180062739  lea     rax, aComguard; "COMGUARD"
0x180062740  mov     [rsp+0F0h+Format], rax; Format
0x180062745  mov     r9d, ebx; unsigned int
0x180062748  mov     r8d, 108h; char *
0x18006274e  lea     rdx, aEnablesnapshot; "EnableSnapshotProviderOnSession"
0x180062755  mov     ecx, 2; this
0x18006275a  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18006275f  mov     eax, ebx
0x180062761  jmp     loc_180062864
0x180062766  lea     rax, [rbp+37h+var_80]
0x18006276a  mov     [rsp+0F0h+var_B8], rax
0x18006276f  mov     [rsp+0F0h+var_C0], 2710h
0x180062777  mov     [rsp+0F0h+var_C8], 0
0x180062780  mov     [rsp+0F0h+Format], 0
0x180062789  mov     r9b, 4
0x18006278c  mov     r13d, 1
0x180062792  mov     r8d, r13d
0x180062795  mov     rdx, r15
0x180062798  mov     rcx, r14
0x18006279b  mov     rax, rdi
0x18006279e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627a3  test    eax, eax
0x1800627a5  jz      short loc_1800627B3
0x1800627a7  mov     ecx, eax; unsigned int
0x1800627a9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800627ae  jmp     loc_180062864
0x1800627b3  lea     rax, [rbp+37h+var_80]
0x1800627b7  mov     [rsp+0F0h+var_B8], rax
0x1800627bc  mov     [rsp+0F0h+var_C0], 927C0h
0x1800627c4  mov     [rsp+0F0h+var_C8], 0
0x1800627cd  mov     [rsp+0F0h+Format], 0
0x1800627d6  mov     r9b, 4
0x1800627d9  mov     r8d, 2
0x1800627df  mov     rdx, r15
0x1800627e2  mov     rcx, r14
0x1800627e5  mov     rax, rdi
0x1800627e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627ed  test    eax, eax
0x1800627ef  jnz     short loc_1800627A7
0x1800627f1  test    sil, sil
0x1800627f4  jz      short loc_18006285B
0x1800627f6  mov     [rbp+37h+var_90], 0
0x1800627fe  lea     edi, [rax+18h]
0x180062801  mov     ecx, edi; Size
0x180062803  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062808  mov     rbx, rax
0x18006280b  mov     eax, [rbp+37h+var_A0]
0x18006280e  mov     [rbx], eax
0x180062810  mov     [rbx+4], r13w
0x180062815  movups  xmm0, xmmword ptr [r15]
0x180062819  movdqu  xmmword ptr [rbx+8], xmm0
0x18006281e  mov     r9d, edi; InformationLength
0x180062821  mov     r8, rbx; TraceInformation
0x180062824  lea     edx, [rdi-8]; InformationClass
0x180062827  mov     rcx, r14; SessionHandle
0x18006282a  call    cs:__imp_TraceSetInformation
0x180062830  test    eax, eax
0x180062832  jz      short loc_18006284E
0x180062834  mov     ecx, eax; unsigned int
0x180062836  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18006283b  mov     edi, eax
0x18006283d  mov     edx, 8
0x180062842  mov     rcx, rbx; Block
0x180062845  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006284a  mov     eax, edi
0x18006284c  jmp     short loc_180062864
0x18006284e  mov     edx, 8
0x180062853  mov     rcx, rbx; Block
0x180062856  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006285b  xor     eax, eax
0x18006285d  jmp     short loc_180062864
0x18006285f  mov     eax, 32h ; '2'
0x180062864  mov     rcx, [rbp+37h+var_40]
0x180062868  xor     rcx, rsp; StackCookie
0x18006286b  call    __security_check_cookie
0x180062870  add     rsp, 0C0h
0x180062877  pop     r15
0x180062879  pop     r14
0x18006287b  pop     r13
0x18006287d  pop     rdi
0x18006287e  pop     rsi
0x18006287f  pop     rbx
0x180062880  pop     rbp
0x180062881  retn
```
