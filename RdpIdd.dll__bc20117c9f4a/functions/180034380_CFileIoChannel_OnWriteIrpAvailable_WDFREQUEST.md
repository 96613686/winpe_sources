# CFileIoChannel::OnWriteIrpAvailable(WDFREQUEST__ *)

- ea: `0x180034380`
- end: `0x18003450d`
- name: `?OnWriteIrpAvailable@CFileIoChannel@@QEAAJPEAUWDFREQUEST__@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011c30`

## callees

- `0x18000d6d8`
- `0x1800106b8`
- `0x180011044`
- `0x18001ddf4`
- `0x180034380`
- `0x18003f010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800343dc`
- `msvcp_win!_Mtx_unlock` at `0x180034426`
- `msvcp_win!_Mtx_unlock` at `0x1800344f0`
- `msvcp_win!_Mtx_unlock` at `0x1800343dc`
- `msvcp_win!_Mtx_unlock` at `0x180034426`
- `msvcp_win!_Mtx_unlock` at `0x1800344f0`

## string_xrefs

- `0x1800343fd`: `Write request is not supported`
- `0x18003447b`: `Failed to retrieve Write Irp buffer`
- `0x1800344cc`: `Failed to handle Write Irp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileIoChannel::OnWriteIrpAvailable(CFileIoChannel *this, struct WDFREQUEST__ *a2)
{
  struct _Mtx_internal_imp_t *v4; // rdi
  std::_Mutex_base *v5; // rcx
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  const char *v9; // [rsp+20h] [rbp-38h]
  const char *v10; // [rsp+28h] [rbp-30h]
  const char *v11; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v4 = (CFileIoChannel *)((char *)this + 32);
  v5 = (CFileIoChannel *)((char *)this + 32);
  try
  {
    std::_Mutex_base::lock(v5);
    if ( *((_BYTE *)this + 433) )
    {
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x428,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0xC0000240LL,
        (int)"Channel I/O is cancelled",
        v10);
      _Mtx_unlock(v4);
      result = 3221226048LL;
    }
    else if ( *((_QWORD *)this + 53) )
    {
      v14 = 0;
      v15 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *, _QWORD, __int64 *, __int64 *))(WdfFunctions_02025 + 1344))(
             WdfDriverGlobals,
             a2,
             *((unsigned int *)this + 90),
             &v14,
             &v15);
      wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x441,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)v7,
        (int)"Failed to retrieve Write Irp buffer",
        v10);
      v8 = (*(__int64 (__fastcall **)(_QWORD, char *, CFileIoChannel *, __int64, __int64))(**((_QWORD **)this + 53)
                                                                                         + 24LL))(
             *((_QWORD *)this + 53),
             (char *)this + 380,
             this,
             v15,
             v14);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x444,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)v8,
        (int)"Failed to handle Write Irp",
        v11);
      _Mtx_unlock(v4);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x432,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0xC00000BBLL,
        (int)"Write request is not supported",
        v10);
      _Mtx_unlock(v4);
      result = 3221225659LL;
    }
  }
  catch ( ... )
  {
    CFileIoChannel::CancelAllPendingIo((__int64)this, 1u);
    return (unsigned int)wil::details::in1diag3::Nt_Return_CaughtExceptionMsg(
                           retaddr,
                           (void *)0x448,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           "Failed to process Write Irp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180034380  mov     [rsp+arg_0], rcx
0x180034385  push    rbx
0x180034386  push    rsi
0x180034387  push    rdi
0x180034388  sub     rsp, 40h
0x18003438c  mov     rsi, rdx
0x18003438f  mov     rbx, rcx
0x180034392  lea     rdi, [rcx+20h]
0x180034396  mov     [rsp+58h+var_28], rdi
0x18003439b  mov     rcx, rdi; this
0x18003439e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800343a3  nop
0x1800343a4  xor     eax, eax
0x1800343a6  cmp     [rbx+1B1h], al
0x1800343ac  jz      short loc_1800343EF
0x1800343ae  mov     rcx, [rsp+58h]; this
0x1800343b3  lea     rax, aChannelIOIsCan; "Channel I/O is cancelled"
0x1800343ba  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800343bf  mov     ebx, 0C0000240h
0x1800343c4  mov     r9d, ebx; char *
0x1800343c7  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800343ce  mov     edx, 428h; void *
0x1800343d3  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800343d8  nop
0x1800343d9  mov     rcx, rdi; _Mtx_t
0x1800343dc  call    cs:__imp__Mtx_unlock
0x1800343e3  nop     dword ptr [rax+rax+00h]
0x1800343e8  mov     eax, ebx
0x1800343ea  jmp     loc_180034504
0x1800343ef  cmp     [rbx+1A8h], rax
0x1800343f6  jnz     short loc_180034439
0x1800343f8  mov     rcx, [rsp+58h]; this
0x1800343fd  lea     rax, aWriteRequestIs; "Write request is not supported"
0x180034404  mov     qword ptr [rsp+58h+var_38], rax; int
0x180034409  mov     ebx, 0C00000BBh
0x18003440e  mov     r9d, ebx; char *
0x180034411  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180034418  mov     edx, 432h; void *
0x18003441d  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180034422  nop
0x180034423  mov     rcx, rdi; _Mtx_t
0x180034426  call    cs:__imp__Mtx_unlock
0x18003442d  nop     dword ptr [rax+rax+00h]
0x180034432  mov     eax, ebx
0x180034434  jmp     loc_180034504
0x180034439  mov     [rsp+58h+arg_10], rax
0x18003443e  mov     [rsp+58h+arg_18], rax
0x180034443  mov     r8d, [rbx+168h]
0x18003444a  mov     rax, cs:WdfFunctions_02025
0x180034451  lea     rcx, [rsp+58h+arg_18]
0x180034456  mov     qword ptr [rsp+58h+var_38], rcx
0x18003445b  lea     r9, [rsp+58h+arg_10]
0x180034460  mov     rdx, rsi
0x180034463  mov     rcx, cs:WdfDriverGlobals
0x18003446a  mov     rax, [rax+540h]
0x180034471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034476  mov     rcx, [rsp+58h]; this
0x18003447b  lea     rdx, aFailedToRetrie_1; "Failed to retrieve Write Irp buffer"
0x180034482  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180034487  mov     r9d, eax; char *
0x18003448a  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180034491  mov     edx, 441h; void *
0x180034496  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003449b  mov     rcx, [rbx+1A8h]
0x1800344a2  mov     r8, [rsp+58h+arg_10]
0x1800344a7  mov     rax, [rcx]
0x1800344aa  lea     rdx, [rbx+17Ch]
0x1800344b1  mov     qword ptr [rsp+58h+var_38], r8
0x1800344b6  mov     r9, [rsp+58h+arg_18]
0x1800344bb  mov     r8, rbx
0x1800344be  mov     rax, [rax+18h]
0x1800344c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344c7  mov     rcx, [rsp+58h]; this
0x1800344cc  lea     rdx, aFailedToHandle; "Failed to handle Write Irp"
0x1800344d3  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800344d8  mov     r9d, eax; char *
0x1800344db  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800344e2  mov     edx, 444h; void *
0x1800344e7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800344ec  nop
0x1800344ed  mov     rcx, rdi; _Mtx_t
0x1800344f0  call    cs:__imp__Mtx_unlock
0x1800344f7  nop     dword ptr [rax+rax+00h]
0x1800344fc  xor     eax, eax
0x1800344fe  jmp     short loc_180034504
0x180034500  mov     eax, dword ptr [rsp+58h+arg_0]
0x180034504  add     rsp, 40h
0x180034508  pop     rdi
0x180034509  pop     rsi
0x18003450a  pop     rbx
0x18003450b  retn
```
