# CRawImageReader::RemoveTagInEntryListIfExists(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> *,uint *,ushort)

- ea: `0x1800ad348`
- end: `0x1800ad4ab`
- name: `?RemoveTagInEntryListIfExists@CRawImageReader@@AEAAJPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@PEAIG@Z`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800a58b4`
- `0x1800a5b90`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x1800a497c`
- `0x1800ad23c`
- `0x1800ad348`
- `0x1800af278`
- `0x1800b4010`

## string_xrefs

- `0x1800ad382`: `CRawImageReader::RemoveTagInEntryListIfExists`
- `0x1800ad409`: `CRawImageReader::RemoveTagInEntryListIfExists`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRawImageReader::RemoveTagInEntryListIfExists(
        unsigned __int64 a1,
        __int64 *a2,
        _DWORD *a3,
        __int16 a4)
{
  int *v8; // r9
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int64 v11; // rbx
  int v13; // [rsp+20h] [rbp-88h]
  unsigned __int16 v14; // [rsp+30h] [rbp-78h] BYREF
  __int64 v15; // [rsp+38h] [rbp-70h]
  _BYTE v16[32]; // [rsp+40h] [rbp-68h] BYREF

  v15 = -2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v14,
    "CRawImageReader::RemoveTagInEntryListIfExists",
    1938);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 272) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 272) + 296LL))(*(_QWORD *)(a1 + 272));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 272) + 280LL))(
                                                            *(_QWORD *)(a1 + 272),
                                                            v16);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
  }
  CTraceBase::CAutoTrace::CAutoTrace(
    (CTraceBase::CAutoTrace *)v16,
    (struct CTraceBase *)((a1 + 56) & ((unsigned __int128)-(__int128)a1 >> 64)),
    "CRawImageReader::RemoveTagInEntryListIfExists",
    v8,
    v13);
  v11 = *a2;
  while ( v11 != a2[1] )
  {
    v14 = 0;
    Read2Bytes((unsigned __int8 *)v11, &v14, *(_BYTE *)(a1 + 107));
    if ( v14 == a4 )
    {
      *a3 += *(_DWORD *)(v11 + 16) - *(_DWORD *)(v11 + 24) - 12;
      std::_Move_unchecked<CRawImageReader::IFDDataEntry *,CRawImageReader::IFDDataEntry *>(v11 + 40, a2[1], v11);
      std::vector<unsigned char>::_Tidy(a2[1] - 24);
      a2[1] -= 40;
    }
    else
    {
      v11 += 40;
    }
  }
  CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v16);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return 0;
}

```

## disassembly

```asm
0x1800ad348  push    rbx
0x1800ad34a  push    rbp
0x1800ad34b  push    rsi
0x1800ad34c  push    rdi
0x1800ad34d  push    r12
0x1800ad34f  push    r14
0x1800ad351  push    r15
0x1800ad353  sub     rsp, 70h
0x1800ad357  mov     [rsp+0A8h+var_70], 0FFFFFFFFFFFFFFFEh
0x1800ad360  mov     rax, cs:__security_cookie
0x1800ad367  xor     rax, rsp
0x1800ad36a  mov     [rsp+0A8h+var_48], rax
0x1800ad36f  movzx   r15d, r9w
0x1800ad373  mov     r14, r8
0x1800ad376  mov     rsi, rdx
0x1800ad379  mov     rbp, rcx
0x1800ad37c  mov     r8d, 792h; int
0x1800ad382  lea     rdx, aCrawimagereade_7; "CRawImageReader::RemoveTagInEntryListIf"...
0x1800ad389  lea     rcx, [rsp+0A8h+var_78]; this
0x1800ad38e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ad393  nop
0x1800ad394  xor     r12d, r12d
0x1800ad397  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ad39e  cmp     [rcx+8], r12b
0x1800ad3a2  jz      short loc_1800AD3F9
0x1800ad3a4  cmp     [rbp+110h], r12
0x1800ad3ab  jz      short loc_1800AD3F9
0x1800ad3ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad3b2  mov     rdi, rax
0x1800ad3b5  mov     rcx, [rbp+110h]
0x1800ad3bc  mov     rdx, [rcx]
0x1800ad3bf  mov     rax, [rdx+128h]
0x1800ad3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3cb  mov     ebx, eax
0x1800ad3cd  mov     rcx, [rbp+110h]
0x1800ad3d4  mov     rdx, [rcx]
0x1800ad3d7  mov     rax, [rdx+118h]
0x1800ad3de  lea     rdx, [rsp+0A8h+var_68]
0x1800ad3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3e8  movups  xmm0, xmmword ptr [rax]
0x1800ad3eb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ad3f3  mov     [rdi+7E0h], ebx
0x1800ad3f9  mov     rax, rbp
0x1800ad3fc  lea     rcx, [rbp+38h]
0x1800ad400  neg     rax
0x1800ad403  sbb     rdx, rdx
0x1800ad406  and     rdx, rcx; struct CTraceBase *
0x1800ad409  lea     r8, aCrawimagereade_7; "CRawImageReader::RemoveTagInEntryListIf"...
0x1800ad410  lea     rcx, [rsp+0A8h+var_68]; this
0x1800ad415  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800ad41a  mov     rbx, [rsi]
0x1800ad41d  cmp     rbx, [rsi+8]
0x1800ad421  jz      short loc_1800AD477
0x1800ad423  mov     [rsp+0A8h+var_78], r12w
0x1800ad429  mov     r8b, [rbp+6Bh]; bool
0x1800ad42d  lea     rdx, [rsp+0A8h+var_78]; unsigned __int16 *
0x1800ad432  mov     rcx, rbx; unsigned __int8 *
0x1800ad435  call    ?Read2Bytes@@YAXPEAEPEAG_N@Z; Read2Bytes(uchar *,ushort *,bool)
0x1800ad43a  lea     rcx, [rbx+28h]
0x1800ad43e  cmp     [rsp+0A8h+var_78], r15w
0x1800ad444  jnz     short loc_1800AD472
0x1800ad446  mov     eax, [rbx+10h]
0x1800ad449  sub     eax, [rbx+18h]
0x1800ad44c  sub     eax, 0Ch
0x1800ad44f  add     [r14], eax
0x1800ad452  mov     r8, rbx
0x1800ad455  mov     rdx, [rsi+8]
0x1800ad459  call    ??$_Move_unchecked@PEAUIFDDataEntry@CRawImageReader@@PEAU12@@std@@YAPEAUIFDDataEntry@CRawImageReader@@PEAU12@00@Z; std::_Move_unchecked<CRawImageReader::IFDDataEntry *,CRawImageReader::IFDDataEntry *>(CRawImageReader::IFDDataEntry *,CRawImageReader::IFDDataEntry *,CRawImageReader::IFDDataEntry *)
0x1800ad45e  mov     rcx, [rsi+8]
0x1800ad462  sub     rcx, 18h
0x1800ad466  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ad46b  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFD8h
0x1800ad470  jmp     short loc_1800AD41D
0x1800ad472  mov     rbx, rcx
0x1800ad475  jmp     short loc_1800AD41D
0x1800ad477  lea     rcx, [rsp+0A8h+var_68]; this
0x1800ad47c  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800ad481  nop
0x1800ad482  lea     rcx, [rsp+0A8h+var_78]; this
0x1800ad487  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ad48c  xor     eax, eax
0x1800ad48e  mov     rcx, [rsp+0A8h+var_48]
0x1800ad493  xor     rcx, rsp; StackCookie
0x1800ad496  call    __security_check_cookie
0x1800ad49b  add     rsp, 70h
0x1800ad49f  pop     r15
0x1800ad4a1  pop     r14
0x1800ad4a3  pop     r12
0x1800ad4a5  pop     rdi
0x1800ad4a6  pop     rsi
0x1800ad4a7  pop     rbp
0x1800ad4a8  pop     rbx
0x1800ad4a9  retn
```
