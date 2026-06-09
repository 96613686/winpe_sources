# CFileIoChannel::OnReadIrpAvailable(WDFREQUEST__ *,unsigned __int64)

- ea: `0x1800342b0`
- end: `0x18003437a`
- name: `?OnReadIrpAvailable@CFileIoChannel@@QEAAXPEAUWDFREQUEST__@@_K@Z`
- size: `202`
- prototype: `void(CFileIoChannel *__hidden this, struct WDFREQUEST__ *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011a60`

## callees

- `0x18000d6d8`
- `0x180011044`
- `0x1800342b0`
- `0x1800346e4`
- `0x180034848`
- `0x18003f010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003433b`
- `msvcp_win!_Mtx_unlock` at `0x18003435e`
- `msvcp_win!_Mtx_unlock` at `0x18003433b`
- `msvcp_win!_Mtx_unlock` at `0x18003435e`

## string_xrefs

- `0x180034317`: `Read Irp buffer length %zu is too small`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFileIoChannel::OnReadIrpAvailable(CFileIoChannel *this, struct WDFREQUEST__ *a2, const char *a3)
{
  struct _Mtx_internal_imp_t *v6; // rdi
  std::_Mutex_base *v7; // rcx
  const char *v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = (CFileIoChannel *)((char *)this + 32);
  v7 = (CFileIoChannel *)((char *)this + 32);
  try
  {
    std::_Mutex_base::lock(v7);
    if ( (unsigned __int64)a3 >= *((unsigned int *)this + 89) )
    {
      CFileIoChannel::QueuePendingIrp(this, a2);
      CFileIoChannel::ProcessPendingIoPacketQueue(this);
    }
    else
    {
      (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, __int64))(WdfFunctions_02025 + 1304))(
        WdfDriverGlobals,
        a2,
        3221225507LL);
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x3FA,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0xC0000023LL,
        (int)"Read Irp buffer length %zu is too small",
        a3);
    }
    _Mtx_unlock(v6);
  }
  catch ( ... )
  {
    CFileIoChannel::CancelAllPendingIo((__int64)this, 1u);
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x408,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      "Failed to process Read Irp",
      v8);
  }
}

```

## disassembly

```asm
0x1800342b0  mov     [rsp+arg_8], rbx
0x1800342b5  mov     [rsp+arg_0], rcx
0x1800342ba  push    rsi
0x1800342bb  push    rdi
0x1800342bc  push    r14
0x1800342be  sub     rsp, 30h
0x1800342c2  mov     rsi, r8
0x1800342c5  mov     r14, rdx
0x1800342c8  mov     rbx, rcx
0x1800342cb  lea     rdi, [rcx+20h]
0x1800342cf  mov     [rsp+48h+arg_18], rdi
0x1800342d4  mov     rcx, rdi; this
0x1800342d7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800342dc  nop
0x1800342dd  mov     eax, [rbx+164h]
0x1800342e3  mov     rdx, r14; struct WDFREQUEST__ *
0x1800342e6  cmp     rsi, rax
0x1800342e9  jnb     short loc_18003434A
0x1800342eb  mov     rax, cs:WdfFunctions_02025
0x1800342f2  mov     ebx, 0C0000023h
0x1800342f7  mov     r8d, ebx
0x1800342fa  mov     rcx, cs:WdfDriverGlobals
0x180034301  mov     rax, [rax+518h]
0x180034308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003430d  mov     rcx, [rsp+48h]; this
0x180034312  mov     [rsp+48h+var_20], rsi; char *
0x180034317  lea     rax, aReadIrpBufferL; "Read Irp buffer length %zu is too small"
0x18003431e  mov     qword ptr [rsp+48h+var_28], rax; int
0x180034323  mov     r9d, ebx; char *
0x180034326  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003432d  mov     edx, 3FAh; void *
0x180034332  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180034337  nop
0x180034338  mov     rcx, rdi; _Mtx_t
0x18003433b  call    cs:__imp__Mtx_unlock
0x180034342  nop     dword ptr [rax+rax+00h]
0x180034347  nop
0x180034348  jmp     short loc_18003436B
0x18003434a  mov     rcx, rbx; this
0x18003434d  call    ?QueuePendingIrp@CFileIoChannel@@QEAAXPEAUWDFREQUEST__@@@Z; CFileIoChannel::QueuePendingIrp(WDFREQUEST__ *)
0x180034352  mov     rcx, rbx; this
0x180034355  call    ?ProcessPendingIoPacketQueue@CFileIoChannel@@AEAAXXZ; CFileIoChannel::ProcessPendingIoPacketQueue(void)
0x18003435a  nop
0x18003435b  mov     rcx, rdi; _Mtx_t
0x18003435e  call    cs:__imp__Mtx_unlock
0x180034365  nop     dword ptr [rax+rax+00h]
0x18003436a  nop
0x18003436b  mov     rbx, [rsp+48h+arg_8]
0x180034370  add     rsp, 30h
0x180034374  pop     r14
0x180034376  pop     rdi
0x180034377  pop     rsi
0x180034378  retn
```
