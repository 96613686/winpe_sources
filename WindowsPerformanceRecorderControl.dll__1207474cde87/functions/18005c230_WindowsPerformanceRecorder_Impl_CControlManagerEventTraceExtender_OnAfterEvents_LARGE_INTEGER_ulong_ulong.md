# WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18005c230`
- end: `0x18005c44d`
- name: `?OnAfterEvents@CControlManagerEventTraceExtender@Impl@WindowsPerformanceRecorder@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `541`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180008330`
- `0x18001e6e0`
- `0x180021810`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004f964`
- `0x18005766c`
- `0x18005c230`
- `0x18005c460`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c315`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c3be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c3e5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c315`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c3be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c3e5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c2f9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005c2f9`

## string_xrefs

- `0x18005c395`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender::OnAfterEvents(
        WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rax
  char *v9; // rsi
  char *v10; // rax
  void *v11; // rax
  void *v12; // rbx
  unsigned int Error; // ebx
  __int64 result; // rax
  signed int v15; // r15d
  const char *v16; // [rsp+28h] [rbp-F0h]
  int v17; // [rsp+30h] [rbp-E8h]
  void *Src; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-D8h] BYREF
  char *v20; // [rsp+48h] [rbp-D0h]
  __int64 v21; // [rsp+50h] [rbp-C8h]
  void *v22; // [rsp+58h] [rbp-C0h]
  ATL::CAtlException *v23; // [rsp+60h] [rbp-B8h] BYREF
  _WORD v24[2]; // [rsp+70h] [rbp-A8h] BYREF
  char v25; // [rsp+74h] [rbp-A4h]
  union _LARGE_INTEGER v26; // [rsp+80h] [rbp-98h]
  __int128 v27; // [rsp+88h] [rbp-90h]
  void *v28; // [rsp+B8h] [rbp-60h]
  int v29; // [rsp+C0h] [rbp-58h]
  unsigned int v30; // [rsp+C4h] [rbp-54h]

  v21 = -2;
  try
  {
    if ( *((_BYTE *)this + 88) )
    {
      memset_0(v24, 0, 0x58u);
      v24[0] = a4;
      v27 = PerfinfoGuid;
      v25 = 34;
      v30 = a3;
      v8 = *((_QWORD *)this + 10);
      v9 = *(char **)(v8 + 496);
      v10 = *(char **)(v8 + 504);
      v20 = v10;
      while ( v9 != v10 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v19,
          v9);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
          &Src,
          v19);
        v17 = *((_DWORD *)Src - 4) + 1;
        v11 = malloc(v17);
        v12 = v11;
        v22 = v11;
        if ( !v11 )
        {
          Error = ATL::AtlHresultFromLastError();
          free(0);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
          return Error;
        }
        memset_0(v11, 0, v17);
        memcpy_0(v12, Src, v17);
        v26 = a2;
        v28 = v12;
        v29 = v17;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                *((_QWORD *)this + 2),
                v24,
                0,
                0);
        if ( v15 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"OnAfterEvents",
            (const char *)0x66,
            v15,
            "COMGUARD",
            v16);
          free(v12);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
          return (unsigned int)v15;
        }
        ++a2.QuadPart;
        free(v12);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
        v9 += 8;
        v10 = v20;
      }
    }
    result = Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, a3, a4);
  }
  catch ( ATL::CAtlException *v23 )
  {
    return *(unsigned int *)v23;
  }
  if ( *((_BYTE *)this + 88) )
  {
    memset_0(v24, 0, 0x58u);
    v24[0] = a4;
    v27 = PerfinfoGuid;
    v25 = 34;
    v30 = a3;
    v8 = *((_QWORD *)this + 10);
    v9 = *(char **)(v8 + 496);
    v10 = *(char **)(v8 + 504);
    v20 = v10;
    while ( v9 != v10 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v19,
        v9);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
        &Src,
        v19);
      v17 = *((_DWORD *)Src - 4) + 1;
      v11 = malloc(v17);
      v12 = v11;
      v22 = v11;
      if ( !v11 )
      {
        Error = ATL::AtlHresultFromLastError();
        free(0);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
        return Error;
      }
      memset_0(v11, 0, v17);
      memcpy_0(v12, Src, v17);
      v26 = a2;
      v28 = v12;
      v29 = v17;
      v15 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
              *((_QWORD *)this + 2),
              v24,
              0,
              0);
      if ( v15 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"OnAfterEvents",
          (const char *)0x66,
          v15,
          "COMGUARD",
          v16);
        free(v12);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
        return (unsigned int)v15;
      }
      ++a2.QuadPart;
      free(v12);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Src);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v19);
      v9 += 8;
      v10 = v20;
    }
  }
}

```

## disassembly

```asm
0x18005c230  push    rbx
0x18005c232  push    rsi
0x18005c233  push    rdi
0x18005c234  push    r12
0x18005c236  push    r13
0x18005c238  push    r14
0x18005c23a  push    r15
0x18005c23c  sub     rsp, 0E0h
0x18005c243  mov     [rsp+118h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18005c24c  mov     rax, cs:__security_cookie
0x18005c253  xor     rax, rsp
0x18005c256  mov     [rsp+118h+var_48], rax
0x18005c25e  mov     r13d, r9d
0x18005c261  mov     r12d, r8d
0x18005c264  mov     rdi, rdx
0x18005c267  mov     r14, rcx
0x18005c26a  cmp     byte ptr [rcx+58h], 0
0x18005c26e  jz      loc_18005C417
0x18005c274  xor     edx, edx; Val
0x18005c276  lea     r8d, [rdx+58h]; Size
0x18005c27a  lea     rcx, [rsp+118h+var_A8]; void *
0x18005c27f  call    memset_0
0x18005c284  mov     [rsp+118h+var_A8], r13w
0x18005c28a  movups  xmm0, cs:PerfinfoGuid
0x18005c291  movdqu  [rsp+118h+var_90], xmm0
0x18005c29a  mov     [rsp+118h+var_A4], 22h ; '"'
0x18005c29f  mov     [rsp+118h+var_54], r12d
0x18005c2a7  mov     rax, [r14+50h]
0x18005c2ab  mov     rsi, [rax+1F0h]
0x18005c2b2  mov     rax, [rax+1F8h]
0x18005c2b9  mov     [rsp+118h+var_D0], rax
0x18005c2be  cmp     rsi, rax
0x18005c2c1  jz      loc_18005C40F
0x18005c2c7  mov     rdx, rsi; void *
0x18005c2ca  lea     rcx, [rsp+118h+var_D8]; void *
0x18005c2cf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18005c2d4  nop
0x18005c2d5  mov     rdx, [rsp+118h+var_D8]
0x18005c2da  lea     rcx, [rsp+118h+Src]
0x18005c2df  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18005c2e4  nop
0x18005c2e5  mov     rax, [rsp+118h+Src]
0x18005c2ea  mov     eax, [rax-10h]
0x18005c2ed  inc     eax
0x18005c2ef  mov     [rsp+118h+var_E8], eax
0x18005c2f3  movsxd  r15, eax
0x18005c2f6  mov     rcx, r15; Size
0x18005c2f9  call    cs:__imp_malloc
0x18005c2ff  mov     rbx, rax
0x18005c302  mov     [rsp+118h+var_C0], rax
0x18005c307  test    rax, rax
0x18005c30a  jnz     short loc_18005C338
0x18005c30c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005c311  mov     ebx, eax
0x18005c313  xor     ecx, ecx; Block
0x18005c315  call    cs:__imp_free
0x18005c31b  nop
0x18005c31c  lea     rcx, [rsp+118h+Src]; this
0x18005c321  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c326  nop
0x18005c327  lea     rcx, [rsp+118h+var_D8]; this
0x18005c32c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c331  mov     eax, ebx
0x18005c333  jmp     loc_18005C429
0x18005c338  mov     r8, r15; Size
0x18005c33b  xor     edx, edx; Val
0x18005c33d  mov     rcx, rbx; void *
0x18005c340  call    memset_0
0x18005c345  mov     r8, r15; Size
0x18005c348  mov     rdx, [rsp+118h+Src]; Src
0x18005c34d  mov     rcx, rbx; void *
0x18005c350  call    memcpy_0
0x18005c355  mov     [rsp+118h+var_98], rdi
0x18005c35d  mov     [rsp+118h+var_60], rbx
0x18005c365  mov     eax, [rsp+118h+var_E8]
0x18005c369  mov     [rsp+118h+var_58], eax
0x18005c370  mov     rcx, [r14+10h]
0x18005c374  mov     rax, [rcx]
0x18005c377  xor     r9d, r9d
0x18005c37a  xor     r8d, r8d
0x18005c37d  lea     rdx, [rsp+118h+var_A8]
0x18005c382  mov     rax, [rax+0C0h]
0x18005c389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c38e  mov     r15d, eax
0x18005c391  test    eax, eax
0x18005c393  jns     short loc_18005C3DF
0x18005c395  lea     rax, aComguard; "COMGUARD"
0x18005c39c  mov     [rsp+118h+Format], rax; Format
0x18005c3a1  mov     r9d, r15d; unsigned int
0x18005c3a4  mov     r8d, 66h ; 'f'; char *
0x18005c3aa  lea     rdx, aOnafterevents; "OnAfterEvents"
0x18005c3b1  lea     ecx, [r8-64h]; this
0x18005c3b5  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005c3ba  nop
0x18005c3bb  mov     rcx, rbx; Block
0x18005c3be  call    cs:__imp_free
0x18005c3c4  nop
0x18005c3c5  lea     rcx, [rsp+118h+Src]; this
0x18005c3ca  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c3cf  nop
0x18005c3d0  lea     rcx, [rsp+118h+var_D8]; this
0x18005c3d5  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c3da  mov     eax, r15d
0x18005c3dd  jmp     short loc_18005C429
0x18005c3df  inc     rdi
0x18005c3e2  mov     rcx, rbx; Block
0x18005c3e5  call    cs:__imp_free
0x18005c3eb  nop
0x18005c3ec  lea     rcx, [rsp+118h+Src]; this
0x18005c3f1  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c3f6  nop
0x18005c3f7  lea     rcx, [rsp+118h+var_D8]; this
0x18005c3fc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005c401  add     rsi, 8
0x18005c405  mov     rax, [rsp+118h+var_D0]
0x18005c40a  jmp     loc_18005C2BE
0x18005c40f  jmp     short loc_18005C417
0x18005c411  mov     eax, [rsp+118h+var_E8]
0x18005c415  jmp     short loc_18005C429
0x18005c417  mov     r9d, r13d; unsigned int
0x18005c41a  mov     r8d, r12d; unsigned int
0x18005c41d  mov     rdx, rdi; union _LARGE_INTEGER
0x18005c420  mov     rcx, r14; this
0x18005c423  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18005c428  nop
0x18005c429  mov     rcx, [rsp+118h+var_48]
0x18005c431  xor     rcx, rsp; StackCookie
0x18005c434  call    __security_check_cookie
0x18005c439  add     rsp, 0E0h
0x18005c440  pop     r15
0x18005c442  pop     r14
0x18005c444  pop     r13
0x18005c446  pop     r12
0x18005c448  pop     rdi
0x18005c449  pop     rsi
0x18005c44a  pop     rbx
0x18005c44b  retn
```
