# CLibrawDataStream::read(void *,unsigned __int64,unsigned __int64)

- ea: `0x1800af7d0`
- end: `0x1800af9f6`
- name: `?read@CLibrawDataStream@@UEAAHPEAX_K1@Z`
- size: `550`
- prototype: `__int64 __fastcall(CLibrawDataStream *__hidden this, void *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800023a0`
- `0x180002590`
- `0x18009860c`
- `0x18009b9e4`
- `0x18009cd18`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800af7d0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af9d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af9d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af800`

## string_xrefs

- `0x1800af815`: `CLibrawDataStream::read`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLibrawDataStream::read(CLibrawDataStream *this, void *a2, unsigned __int64 a3, unsigned int a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r14
  unsigned int v9; // edi
  unsigned __int64 v10; // r8
  int v11; // eax
  int v12; // ebx
  void ***v13; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v15; // r8d
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  void ***v18; // rcx
  _QWORD v20[2]; // [rsp+38h] [rbp-50h] BYREF
  int v21; // [rsp+48h] [rbp-40h]
  char v22; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp+18h] BYREF
  char *v24; // [rsp+A8h] [rbp+20h]

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v24 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v9 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CLibrawDataStream::read", 203);
  v20[0] = "CLibrawDataStream::read";
  v20[1] = 0;
  v21 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CLibrawDataStream::read");
  v23 = 0;
  v10 = (unsigned int)a3 * (unsigned __int64)a4;
  if ( v10 > 0xFFFFFFFF )
  {
    v12 = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
        0,
        -2147024362);
    }
    v18 = (void ***)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = &off_1800E5190;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
      {
        v15 = 207;
        goto LABEL_24;
      }
    }
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, void *, unsigned __int64, unsigned int *))(**((_QWORD **)this + 6) + 24LL))(
            *((_QWORD *)this + 6),
            a2,
            v10,
            &v23);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v16 = v23;
      *((_QWORD *)this + 7) += v23;
      v17 = a3;
      if ( !a3 )
        v17 = 1;
      v9 = (a3 + v16 - 1) / v17;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids, 0, v11);
      }
      v13 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
        {
          v15 = 208;
LABEL_24:
          CallStackContext::TraceFailure(ThreadRelativeContext, "CLibrawDataStream::read", v15, v12);
        }
      }
    }
  }
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v20);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  LeaveCriticalSection(v8);
  return v9;
}

```

## disassembly

```asm
0x1800af7d0  mov     rax, rsp
0x1800af7d3  push    rbx
0x1800af7d4  push    rbp
0x1800af7d5  push    rsi
0x1800af7d6  push    rdi
0x1800af7d7  push    r12
0x1800af7d9  push    r14
0x1800af7db  push    r15
0x1800af7dd  sub     rsp, 50h
0x1800af7e1  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800af7e9  mov     rbx, r9
0x1800af7ec  mov     rsi, r8
0x1800af7ef  mov     r15, rdx
0x1800af7f2  mov     rbp, rcx
0x1800af7f5  lea     r14, [rcx+8]
0x1800af7f9  mov     [rax+20h], r14
0x1800af7fd  mov     rcx, r14; lpCriticalSection
0x1800af800  call    cs:__imp_EnterCriticalSection
0x1800af807  nop     dword ptr [rax+rax+00h]
0x1800af80c  nop
0x1800af80d  xor     edi, edi
0x1800af80f  mov     r8d, 0CBh; int
0x1800af815  lea     r12, aClibrawdatastr_1; "CLibrawDataStream::read"
0x1800af81c  mov     rdx, r12; char *
0x1800af81f  lea     rcx, [rsp+88h+arg_0]; this
0x1800af827  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800af82c  nop
0x1800af82d  mov     [rsp+88h+var_50], r12
0x1800af832  mov     [rsp+88h+var_48], rdi
0x1800af837  lea     edx, [rdi+0Fh]; unsigned int
0x1800af83a  mov     [rsp+88h+var_40], edx
0x1800af83e  mov     r9, r12
0x1800af841  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800af848  xor     ecx, ecx; unsigned int
0x1800af84a  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800af84f  nop
0x1800af850  mov     [rsp+88h+arg_10], edi
0x1800af857  mov     r8d, ebx
0x1800af85a  mov     eax, esi
0x1800af85c  imul    r8, rax
0x1800af860  mov     eax, 0FFFFFFFFh
0x1800af865  cmp     r8, rax
0x1800af868  ja      loc_1800AF936
0x1800af86e  mov     rcx, [rbp+30h]
0x1800af872  mov     rax, [rcx]
0x1800af875  lea     r9, [rsp+88h+arg_10]
0x1800af87d  mov     rdx, r15
0x1800af880  mov     rax, [rax+18h]
0x1800af884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af889  mov     ebx, eax
0x1800af88b  test    eax, eax
0x1800af88d  jns     short loc_1800AF90A
0x1800af88f  lea     rdx, WPP_GLOBAL_Control
0x1800af896  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af89d  cmp     rcx, rdx
0x1800af8a0  jz      short loc_1800AF8CA
0x1800af8a2  lea     edx, [rdi+1]
0x1800af8a5  test    [rcx+1Ch], dl
0x1800af8a8  jz      short loc_1800AF8CA
0x1800af8aa  cmp     byte ptr [rcx+19h], 4
0x1800af8ae  jb      short loc_1800AF8CA
0x1800af8b0  lea     edx, [rdi+0Eh]
0x1800af8b3  mov     [rsp+88h+var_68], eax
0x1800af8b7  xor     r9d, r9d
0x1800af8ba  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800af8c1  mov     rcx, [rcx+10h]
0x1800af8c5  call    WPP_SF_Dd
0x1800af8ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af8d1  test    rcx, rcx
0x1800af8d4  jnz     short loc_1800AF8E4
0x1800af8d6  lea     rcx, off_1800E5190; this
0x1800af8dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af8e4  cmp     [rcx+8], dil
0x1800af8e8  jz      loc_1800AF9BC
0x1800af8ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af8f3  cmp     [rax+7CCh], ebx
0x1800af8f9  jz      loc_1800AF9BC
0x1800af8ff  mov     r8d, 0D0h
0x1800af905  jmp     loc_1800AF9AD
0x1800af90a  mov     eax, [rsp+88h+arg_10]
0x1800af911  add     [rbp+38h], rax
0x1800af915  mov     rcx, rsi
0x1800af918  mov     edx, 1
0x1800af91d  test    rsi, rsi
0x1800af920  cmovz   rcx, rdx
0x1800af924  dec     rax
0x1800af927  add     rax, rsi
0x1800af92a  xor     edx, edx
0x1800af92c  div     rcx
0x1800af92f  mov     edi, eax
0x1800af931  jmp     loc_1800AF9BC
0x1800af936  lea     rdx, WPP_GLOBAL_Control
0x1800af93d  mov     ebx, 80070216h
0x1800af942  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af949  cmp     rcx, rdx
0x1800af94c  jz      short loc_1800AF97A
0x1800af94e  mov     edx, 1
0x1800af953  test    [rcx+1Ch], dl
0x1800af956  jz      short loc_1800AF97A
0x1800af958  cmp     byte ptr [rcx+19h], 4
0x1800af95c  jb      short loc_1800AF97A
0x1800af95e  mov     edx, 0Dh
0x1800af963  mov     [rsp+88h+var_68], ebx
0x1800af967  xor     r9d, r9d
0x1800af96a  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800af971  mov     rcx, [rcx+10h]
0x1800af975  call    WPP_SF_Dd
0x1800af97a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af981  test    rcx, rcx
0x1800af984  jnz     short loc_1800AF994
0x1800af986  lea     rcx, off_1800E5190; this
0x1800af98d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800af994  cmp     [rcx+8], dil
0x1800af998  jz      short loc_1800AF9BC
0x1800af99a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800af99f  cmp     [rax+7CCh], ebx
0x1800af9a5  jz      short loc_1800AF9BC
0x1800af9a7  mov     r8d, 0CFh; int
0x1800af9ad  mov     r9d, ebx; int
0x1800af9b0  mov     rdx, r12; char *
0x1800af9b3  mov     rcx, rax; this
0x1800af9b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800af9bb  nop
0x1800af9bc  lea     rcx, [rsp+88h+var_50]; this
0x1800af9c1  call    ??1CAutoTraceStatic@@QEAA@XZ; CAutoTraceStatic::~CAutoTraceStatic(void)
0x1800af9c6  nop
0x1800af9c7  lea     rcx, [rsp+88h+arg_0]; this
0x1800af9cf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800af9d4  nop
0x1800af9d5  mov     rcx, r14; lpCriticalSection
0x1800af9d8  call    cs:__imp_LeaveCriticalSection
0x1800af9df  nop     dword ptr [rax+rax+00h]
0x1800af9e4  mov     eax, edi
0x1800af9e6  add     rsp, 50h
0x1800af9ea  pop     r15
0x1800af9ec  pop     r14
0x1800af9ee  pop     r12
0x1800af9f0  pop     rdi
0x1800af9f1  pop     rsi
0x1800af9f2  pop     rbp
0x1800af9f3  pop     rbx
0x1800af9f4  retn
```
