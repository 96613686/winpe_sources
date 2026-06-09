# CWaitThreadList::Wait(void *)

- ea: `0x180062018`
- end: `0x1800621db`
- name: `?Wait@CWaitThreadList@@QEAAXPEAX@Z`
- size: `451`
- prototype: `void(CWaitThreadList *__hidden this, void *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180061940`
- `0x1800f9f70`

## callees

- `0x180048ec8`
- `0x180062018`
- `0x1800621e4`
- `0x18008d9f4`
- `0x1800e95f0`
- `0x1801006a8`
- `0x1801244f0`
- `0x180124d80`
- `0x1801327d4`
- `0x180133570`
- `0x180156e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800620e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800620ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800620e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800620ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062045`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800620ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062045`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800620ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800620cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800620cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006204e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006204e`

## string_xrefs

- `0x1800621c9`: `onecoreuap\base\appmodel\Search\common\include\eventsem_common.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWaitThreadList::Wait(CWaitThreadList *this, void *a2)
{
  DWORD CurrentThreadId; // r14d
  volatile signed __int32 *v5; // rbx
  int v6; // edi
  int v7; // r8d
  _QWORD *i; // rax
  CThreadSmartWait *v9; // rdi
  HANDLE *v10; // rax
  const char *v11; // r9
  int v12; // edx
  struct _SECURITY_ATTRIBUTES *const v13; // r8
  CEventSem *v14; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CEventSem *v16; // [rsp+50h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v5 = (volatile signed __int32 *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  *((_DWORD *)this + 3) = GetCurrentThreadId();
  v16 = (CWaitThreadList *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 4) )
  {
    CSyncReadWrite::LokInitWriteEvent((CWaitThreadList *)((char *)this + 8));
    CEventSem::Reset(*((CEventSem **)this + 14));
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v6 )
    CEventSem::Wait(*((CEventSem **)this + 14), 0xFFFFFFFF, v7);
  for ( i = *(_QWORD **)this; i; i = (_QWORD *)*i )
  {
    v9 = (CThreadSmartWait *)i[1];
    if ( *((_DWORD *)v9 + 6) == CurrentThreadId )
      goto LABEL_9;
  }
  v14 = (CEventSem *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v14;
  if ( !v14 )
  {
    v9 = 0;
    goto LABEL_24;
  }
  v9 = CThreadSmartWait::CThreadSmartWait(v14, *((_DWORD *)this + 30));
  v16 = v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = *(_QWORD *)this;
    *((_QWORD *)v9 + 1) = v9;
    *(_QWORD *)this = v9;
    ++*((_DWORD *)this + 31);
LABEL_24:
    v16 = 0;
  }
  TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(&v16);
LABEL_9:
  if ( v9 )
    *((_BYTE *)v9 + 28) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *v5 == 1 )
    *((_DWORD *)this + 3) = -1;
  _InterlockedDecrement(v5);
  v10 = (HANDLE *)*((_QWORD *)this + 13);
  if ( !v10 )
  {
    v16 = (CEventSem *)operator new(8u);
    v10 = (HANDLE *)CEventSem::CEventSem(v16, v12, v13);
    *((_QWORD *)this + 13) = v10;
  }
  if ( !SetEvent(*v10) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\eventsem_common.hxx",
      v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v9 )
    CThreadSmartWait::Wait(v9, a2, *((_DWORD *)this + 31));
}

```

## disassembly

```asm
0x180062018  mov     [rsp+arg_8], rbx
0x18006201d  mov     [rsp+arg_10], rbp
0x180062022  push    rsi
0x180062023  push    rdi
0x180062024  push    r12
0x180062026  push    r14
0x180062028  push    r15
0x18006202a  sub     rsp, 20h
0x18006202e  mov     r12, rdx
0x180062031  mov     rsi, rcx
0x180062034  call    cs:__imp_GetCurrentThreadId
0x18006203a  mov     r14d, eax
0x18006203d  lea     rbx, [rsi+8]
0x180062041  lea     rcx, [rbx+10h]; lpCriticalSection
0x180062045  call    cs:__imp_EnterCriticalSection
0x18006204b  lock inc dword ptr [rbx]
0x18006204e  call    cs:__imp_GetCurrentThreadId
0x180062054  mov     [rbx+4], eax
0x180062057  lea     rbp, [rbx+38h]
0x18006205b  mov     [rsp+48h+arg_0], rbp
0x180062060  mov     rcx, rbp; lpCriticalSection
0x180062063  call    cs:__imp_EnterCriticalSection
0x180062069  nop
0x18006206a  cmp     dword ptr [rbx+8], 0
0x18006206e  jnz     loc_180062139
0x180062074  xor     edi, edi
0x180062076  mov     rcx, rbp; lpCriticalSection
0x180062079  call    cs:__imp_LeaveCriticalSection
0x18006207f  test    edi, edi
0x180062081  jnz     loc_180062154
0x180062087  mov     rax, [rsi]
0x18006208a  test    rax, rax
0x18006208d  jz      loc_180062165
0x180062093  mov     rdi, [rax+8]
0x180062097  cmp     [rdi+18h], r14d
0x18006209b  jz      short loc_1800620A2
0x18006209d  mov     rax, [rax]
0x1800620a0  jmp     short loc_18006208A
0x1800620a2  test    rdi, rdi
0x1800620a5  jz      short loc_1800620AB
0x1800620a7  mov     byte ptr [rdi+1Ch], 1
0x1800620ab  mov     rcx, rbp; lpCriticalSection
0x1800620ae  call    cs:__imp_EnterCriticalSection
0x1800620b4  cmp     dword ptr [rbx], 1
0x1800620b7  jnz     short loc_1800620C0
0x1800620b9  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x1800620c0  lock dec dword ptr [rbx]
0x1800620c3  mov     rax, [rbx+60h]
0x1800620c7  test    rax, rax
0x1800620ca  jz      short loc_18006211C
0x1800620cc  mov     rcx, [rax]; hEvent
0x1800620cf  call    cs:__imp_SetEvent
0x1800620d5  test    eax, eax
0x1800620d7  jz      loc_1800621C4
0x1800620dd  mov     rcx, rbp; lpCriticalSection
0x1800620e0  call    cs:__imp_LeaveCriticalSection
0x1800620e6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800620ea  call    cs:__imp_LeaveCriticalSection
0x1800620f0  nop
0x1800620f1  test    rdi, rdi
0x1800620f4  jz      short loc_180062105
0x1800620f6  mov     r8d, [rsi+7Ch]; unsigned int
0x1800620fa  mov     rdx, r12; void *
0x1800620fd  mov     rcx, rdi; this
0x180062100  call    ?Wait@CThreadSmartWait@@QEAAXPEAXK@Z; CThreadSmartWait::Wait(void *,ulong)
0x180062105  mov     rbx, [rsp+48h+arg_8]
0x18006210a  mov     rbp, [rsp+48h+arg_10]
0x18006210f  add     rsp, 20h
0x180062113  pop     r15
0x180062115  pop     r14
0x180062117  pop     r12
0x180062119  pop     rdi
0x18006211a  pop     rsi
0x18006211b  retn
0x18006211c  mov     ecx, 8; Size
0x180062121  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062126  mov     [rsp+48h+arg_0], rax
0x18006212b  mov     rcx, rax; this
0x18006212e  call    ??0CEventSem@@QEAA@HQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::CEventSem(int,_SECURITY_ATTRIBUTES * const)
0x180062133  mov     [rbx+60h], rax
0x180062137  jmp     short loc_1800620CC
0x180062139  mov     rcx, rbx; this
0x18006213c  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180062141  mov     rcx, [rbx+68h]; this
0x180062145  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x18006214a  mov     edi, 1
0x18006214f  jmp     loc_180062076
0x180062154  or      edx, 0FFFFFFFFh; unsigned int
0x180062157  mov     rcx, [rbx+68h]; this
0x18006215b  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x180062160  jmp     loc_180062087
0x180062165  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006216c  mov     ecx, 38h ; '8'; unsigned __int64
0x180062171  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180062176  mov     [rsp+48h+arg_0], rax
0x18006217b  test    rax, rax
0x18006217e  jz      short loc_1800621AA
0x180062180  mov     edx, [rsi+78h]; unsigned int
0x180062183  mov     rcx, rax; this
0x180062186  call    ??0CThreadSmartWait@@QEAA@K@Z; CThreadSmartWait::CThreadSmartWait(ulong)
0x18006218b  mov     rdi, rax
0x18006218e  mov     [rsp+48h+arg_0], rax
0x180062193  test    rax, rax
0x180062196  jz      short loc_1800621B5
0x180062198  mov     rax, [rsi]
0x18006219b  mov     [rdi], rax
0x18006219e  mov     [rdi+8], rdi
0x1800621a2  mov     [rsi], rdi
0x1800621a5  inc     dword ptr [rsi+7Ch]
0x1800621a8  jmp     short loc_1800621AC
0x1800621aa  xor     edi, edi
0x1800621ac  mov     [rsp+48h+arg_0], 0
0x1800621b5  lea     rcx, [rsp+48h+arg_0]
0x1800621ba  call    ??1?$TPointer@VCThreadSmartWait@@@@QEAA@XZ; TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(void)
0x1800621bf  jmp     loc_1800620A2
0x1800621c4  mov     rcx, [rsp+48h]; this
0x1800621c9  lea     r8, aOnecoreuapBase_199; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800621d0  mov     edx, 10Ah; void *
0x1800621d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
