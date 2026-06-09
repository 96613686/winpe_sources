# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x180018a60`
- end: `0x180018bcf`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016a50`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x180002aac`
- `0x180002ab8`
- `0x1800155a0`
- `0x180015710`
- `0x180018a60`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180018b18`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180018b18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(
        Microsoft::Windows::Performance::CEtwTraceHandleGroup *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        void (*a4)(struct _EVENT_TRACE *),
        unsigned int (*a5)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a6)
{
  __int64 v10; // rbp
  __int64 v11; // rdi
  TRACEHANDLE v12; // rax
  signed int Error; // edi
  char *v14; // rcx
  char *v15; // rbx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-218h] BYREF

  if ( !(unsigned __int8)ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(this, a2) )
    return 2147942414LL;
  *((_DWORD *)this + 2) = a2;
  v10 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    v11 = *(_QWORD *)this;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = (LPWSTR)a3[v10];
    Logfile.EventCallback = a4;
    Logfile.BufferCallback = a5;
    Logfile.LogfileHeader.ReservedFlags = a6;
    v12 = OpenTraceW(&Logfile);
    *(_QWORD *)(v11 + 16LL * (unsigned int)v10) = v12;
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 8) = LOWORD(Logfile.LogfileHeader.Version);
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 12) = Logfile.LogfileHeader.BufferSize;
    if ( v12 == -1 )
    {
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        break;
    }
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= a2 )
      return 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v14 = *(char **)this;
    if ( *(_QWORD *)this )
    {
      v15 = v14 - 8;
      `eh vector destructor iterator'(
        v14,
        0x10u,
        *((_QWORD *)v14 - 1),
        (void (*)(void *))Microsoft::Windows::Performance::CEtwTraceHandle::~CEtwTraceHandle);
      operator delete[](v15);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018a60  push    rbx
0x180018a62  push    rbp
0x180018a63  push    rsi
0x180018a64  push    rdi
0x180018a65  push    r12
0x180018a67  push    r13
0x180018a69  push    r14
0x180018a6b  push    r15
0x180018a6d  sub     rsp, 208h
0x180018a74  mov     rax, cs:__security_cookie
0x180018a7b  xor     rax, rsp
0x180018a7e  mov     [rsp+248h+var_58], rax
0x180018a86  mov     [rsp+248h+var_228], r9
0x180018a8b  mov     r13, r8
0x180018a8e  mov     r15d, edx
0x180018a91  mov     r14, rcx
0x180018a94  mov     rax, [rsp+248h+arg_20]
0x180018a9c  mov     [rsp+248h+var_220], rax
0x180018aa1  mov     edx, edx
0x180018aa3  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x180018aa8  test    al, al
0x180018aaa  jnz     short loc_180018AB6
0x180018aac  mov     eax, 8007000Eh
0x180018ab1  jmp     loc_180018B66
0x180018ab6  mov     [r14+8], r15d
0x180018aba  xor     ebp, ebp
0x180018abc  test    r15d, r15d
0x180018abf  jz      loc_180018B64
0x180018ac5  mov     r12d, [rsp+248h+arg_28]
0x180018acd  mov     esi, ebp
0x180018acf  add     rsi, rsi
0x180018ad2  mov     rdi, [r14]
0x180018ad5  xor     edx, edx; Val
0x180018ad7  mov     r8d, 1C0h; Size
0x180018add  lea     rcx, [rsp+248h+Logfile]; void *
0x180018ae2  call    memset_0
0x180018ae7  mov     rax, [r13+rbp*8+0]
0x180018aec  mov     [rsp+248h+Logfile.LogFileName], rax
0x180018af1  mov     rax, [rsp+248h+var_228]
0x180018af6  mov     qword ptr [rsp+248h+Logfile.1A8h], rax
0x180018afe  mov     rax, [rsp+248h+var_220]
0x180018b03  mov     [rsp+248h+Logfile.BufferCallback], rax
0x180018b0b  mov     [rsp+248h+Logfile.LogfileHeader.ReservedFlags], r12d
0x180018b13  lea     rcx, [rsp+248h+Logfile]; Logfile
0x180018b18  call    cs:__imp_OpenTraceW
0x180018b1e  mov     [rdi+rsi*8], rax
0x180018b22  movzx   edx, byte ptr [rsp+248h+Logfile.LogfileHeader.4+1]
0x180018b2a  shl     edx, 8
0x180018b2d  movzx   ecx, byte ptr [rsp+248h+Logfile.LogfileHeader.4]
0x180018b35  or      edx, ecx
0x180018b37  mov     [rdi+rsi*8+8], edx
0x180018b3b  mov     ecx, [rsp+248h+Logfile.LogfileHeader.BufferSize]
0x180018b42  mov     [rdi+rsi*8+0Ch], ecx
0x180018b46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018b4a  jnz     short loc_180018B59
0x180018b4c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180018b51  mov     edi, eax
0x180018b53  xor     esi, esi
0x180018b55  test    eax, eax
0x180018b57  js      short loc_180018B8A
0x180018b59  inc     ebp
0x180018b5b  cmp     ebp, r15d
0x180018b5e  jb      loc_180018ACD
0x180018b64  xor     eax, eax
0x180018b66  mov     rcx, [rsp+248h+var_58]
0x180018b6e  xor     rcx, rsp; StackCookie
0x180018b71  call    __security_check_cookie
0x180018b76  add     rsp, 208h
0x180018b7d  pop     r15
0x180018b7f  pop     r14
0x180018b81  pop     r13
0x180018b83  pop     r12
0x180018b85  pop     rdi
0x180018b86  pop     rsi
0x180018b87  pop     rbp
0x180018b88  pop     rbx
0x180018b89  retn
0x180018b8a  cmp     [r14+8], esi
0x180018b8e  jz      short loc_180018BCB
0x180018b90  mov     rcx, [r14]; void *
0x180018b93  test    rcx, rcx
0x180018b96  jz      short loc_180018BC4
0x180018b98  lea     rbx, [rcx-8]
0x180018b9c  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x180018ba3  mov     r8, [rbx]; unsigned __int64
0x180018ba6  mov     edx, 10h; unsigned __int64
0x180018bab  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180018bb0  mov     rdx, [rbx]
0x180018bb3  shl     rdx, 4
0x180018bb7  add     rdx, 8; unsigned __int64
0x180018bbb  mov     rcx, rbx; void *
0x180018bbe  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x180018bc3  nop
0x180018bc4  mov     [r14], rsi
0x180018bc7  mov     [r14+8], esi
0x180018bcb  mov     eax, edi
0x180018bcd  jmp     short loc_180018B66
```
