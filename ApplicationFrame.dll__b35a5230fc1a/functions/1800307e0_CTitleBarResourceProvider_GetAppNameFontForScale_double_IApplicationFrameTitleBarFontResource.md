# CTitleBarResourceProvider::GetAppNameFontForScale(double,IApplicationFrameTitleBarFontResource * *)

- ea: `0x1800307e0`
- end: `0x18003098e`
- name: `?GetAppNameFontForScale@CTitleBarResourceProvider@@UEAAJNPEAPEAUIApplicationFrameTitleBarFontResource@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(CTitleBarResourceProvider *__hidden this, double, struct IApplicationFrameTitleBarFontResource **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004c98`
- `0x1800307e0`
- `0x180030994`
- `0x180030aec`
- `0x18003fbc0`
- `0x180040270`
- `0x180040684`
- `0x180043c30`
- `0x1800446fc`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003081f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003081f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030914`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030945`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030981`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030914`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030945`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030981`
- `GDI32!CreateFontIndirectW` at `0x1800308ba`
- `GDI32!CreateFontIndirectW` at `0x1800308ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTitleBarResourceProvider::GetAppNameFontForScale(RTL_SRWLOCK *this, double a2, PVOID *a3)
{
  RTL_SRWLOCK *v5; // rdi
  PVOID Ptr; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  int v10; // eax
  unsigned int v11; // r14d
  const char *v12; // r9
  int v13; // eax
  unsigned int v14; // ebp
  unsigned int LastError; // ebx
  unsigned int v16; // [rsp+20h] [rbp-C8h]
  int v17; // [rsp+20h] [rbp-C8h]
  _QWORD v18[2]; // [rsp+30h] [rbp-B8h] BYREF
  LOGFONTW lf; // [rsp+40h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  *a3 = 0;
  v5 = this + 6;
  AcquireSRWLockExclusive(this + 6);
  if ( !this[2].Ptr || a2 == *(double *)&this[4].Ptr && this[5].Ptr )
    goto LABEL_4;
  memset_0(&lf, 0, sizeof(lf));
  v10 = CTitleBarResourceProvider::s_LoadFont(&lf, a2, v8, v9, v16);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarresourceprovider.cpp",
      (const char *)(unsigned int)v10,
      v17);
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    return v11;
  }
  else
  {
    v18[0] = CreateFontIndirectW(&lf);
    if ( v18[0] )
    {
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&this[5]);
      v13 = Microsoft::WRL::Details::MakeAndInitialize<TitleBarFontResource,IApplicationFrameTitleBarFontResource,CAutoHandle<HFONT__ *> &>(
              &this[5],
              v18);
      v14 = v13;
      if ( v13 >= 0 )
      {
        *(double *)&this[4].Ptr = a2;
LABEL_4:
        Ptr = this[5].Ptr;
        if ( Ptr )
        {
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
          *a3 = this[5].Ptr;
        }
        if ( v5 )
          ReleaseSRWLockExclusive(v5);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarresourceprovider.cpp",
        (const char *)(unsigned int)v13,
        v17);
      CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(v18);
      if ( v5 )
        ReleaseSRWLockExclusive(v5);
      return v14;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7F,
                    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarresourceprovider.cpp",
                    v12);
      if ( v5 )
        ReleaseSRWLockExclusive(v5);
      return LastError;
    }
  }
}

```

## disassembly

```asm
0x1800307e0  push    rbx
0x1800307e2  push    rbp
0x1800307e3  push    rsi
0x1800307e4  push    rdi
0x1800307e5  push    r14
0x1800307e7  sub     rsp, 0C0h
0x1800307ee  movaps  [rsp+0E8h+var_38], xmm6
0x1800307f6  mov     rax, cs:__security_cookie
0x1800307fd  xor     rax, rsp
0x180030800  mov     [rsp+0E8h+var_48], rax
0x180030808  mov     rsi, r8
0x18003080b  movaps  xmm6, xmm1
0x18003080e  mov     rbx, rcx
0x180030811  mov     qword ptr [r8], 0
0x180030818  lea     rdi, [rcx+30h]
0x18003081c  mov     rcx, rdi; SRWLock
0x18003081f  call    cs:__imp_AcquireSRWLockExclusive
0x180030825  cmp     qword ptr [rbx+10h], 0
0x18003082a  jz      short loc_18003083C
0x18003082c  ucomisd xmm6, qword ptr [rbx+20h]
0x180030831  jp      short loc_18003088F
0x180030833  jnz     short loc_18003088F
0x180030835  cmp     qword ptr [rbx+28h], 0
0x18003083a  jz      short loc_18003088F
0x18003083c  mov     rcx, [rbx+28h]
0x180030840  test    rcx, rcx
0x180030843  jz      short loc_180030859
0x180030845  mov     rax, [rcx]
0x180030848  mov     rax, [rax+8]
0x18003084c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030851  nop
0x180030852  mov     rax, [rbx+28h]
0x180030856  mov     [rsi], rax
0x180030859  test    rdi, rdi
0x18003085c  jz      short loc_180030867
0x18003085e  mov     rcx, rdi; SRWLock
0x180030861  call    cs:__imp_ReleaseSRWLockExclusive
0x180030867  xor     eax, eax
0x180030869  mov     rcx, [rsp+0E8h+var_48]
0x180030871  xor     rcx, rsp; StackCookie
0x180030874  call    __security_check_cookie
0x180030879  movaps  xmm6, [rsp+0E8h+var_38]
0x180030881  add     rsp, 0C0h
0x180030888  pop     r14
0x18003088a  pop     rdi
0x18003088b  pop     rsi
0x18003088c  pop     rbp
0x18003088d  pop     rbx
0x18003088e  retn
0x18003088f  xor     edx, edx; Val
0x180030891  mov     r8d, 5Ch ; '\'; Size
0x180030897  lea     rcx, [rsp+0E8h+lf]; void *
0x18003089c  call    memset_0
0x1800308a1  movaps  xmm1, xmm6; double
0x1800308a4  lea     rcx, [rsp+0E8h+lf]; struct tagLOGFONTW *
0x1800308a9  call    ?s_LoadFont@CTitleBarResourceProvider@@CAJAEAUtagLOGFONTW@@NIII@Z; CTitleBarResourceProvider::s_LoadFont(tagLOGFONTW &,double,uint,uint,uint)
0x1800308ae  mov     r14d, eax
0x1800308b1  test    eax, eax
0x1800308b3  js      short loc_180030921
0x1800308b5  lea     rcx, [rsp+0E8h+lf]; lplf
0x1800308ba  call    cs:__imp_CreateFontIndirectW
0x1800308c0  mov     [rsp+0E8h+var_B8], rax
0x1800308c5  test    rax, rax
0x1800308c8  jz      short loc_1800308F1
0x1800308ca  lea     rcx, [rbx+28h]
0x1800308ce  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800308d3  lea     rdx, [rsp+0E8h+var_B8]
0x1800308d8  lea     rcx, [rbx+28h]
0x1800308dc  call    ??$MakeAndInitialize@VTitleBarFontResource@@UIApplicationFrameTitleBarFontResource@@AEAV?$CAutoHandle@PEAUHFONT__@@@@@Details@WRL@Microsoft@@YAJPEAPEAUIApplicationFrameTitleBarFontResource@@AEAV?$CAutoHandle@PEAUHFONT__@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TitleBarFontResource,IApplicationFrameTitleBarFontResource,CAutoHandle<HFONT__ *> &>(IApplicationFrameTitleBarFontResource * *,CAutoHandle<HFONT__ *> &)
0x1800308e1  mov     ebp, eax
0x1800308e3  test    eax, eax
0x1800308e5  js      short loc_180030953
0x1800308e7  movsd   qword ptr [rbx+20h], xmm6
0x1800308ec  jmp     loc_18003083C
0x1800308f1  mov     rcx, [rsp+0E8h]; this
0x1800308f9  lea     r8, aPcshellShellAp_2; "pcshell\\shell\\applicationframe\\frame"...
0x180030900  mov     edx, 7Fh; void *
0x180030905  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003090a  mov     ebx, eax
0x18003090c  test    rdi, rdi
0x18003090f  jz      short loc_18003091A
0x180030911  mov     rcx, rdi; SRWLock
0x180030914  call    cs:__imp_ReleaseSRWLockExclusive
0x18003091a  mov     eax, ebx
0x18003091c  jmp     loc_180030869
0x180030921  mov     rcx, [rsp+0E8h]; this
0x180030929  mov     r9d, r14d; char *
0x18003092c  lea     r8, aPcshellShellAp_2; "pcshell\\shell\\applicationframe\\frame"...
0x180030933  mov     edx, 7Ch ; '|'; void *
0x180030938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003093d  test    rdi, rdi
0x180030940  jz      short loc_18003094B
0x180030942  mov     rcx, rdi; SRWLock
0x180030945  call    cs:__imp_ReleaseSRWLockExclusive
0x18003094b  mov     eax, r14d
0x18003094e  jmp     loc_180030869
0x180030953  mov     rcx, [rsp+0E8h]; this
0x18003095b  mov     r9d, ebp; char *
0x18003095e  lea     r8, aPcshellShellAp_2; "pcshell\\shell\\applicationframe\\frame"...
0x180030965  mov     edx, 81h; void *
0x18003096a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003096f  lea     rcx, [rsp+0E8h+var_B8]
0x180030974  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x180030979  test    rdi, rdi
0x18003097c  jz      short loc_180030987
0x18003097e  mov     rcx, rdi; SRWLock
0x180030981  call    cs:__imp_ReleaseSRWLockExclusive
0x180030987  mov     eax, ebp
0x180030989  jmp     loc_180030869
```
