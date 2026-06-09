# CFileIoChannel::AllocateIoPacket(unsigned __int64,uint *,uint,void *,Rdp::Avenc::IIoPacketCompleteEvents *,Rdp::Avenc::IIoPacket * *,uint)

- ea: `0x180032c90`
- end: `0x180032eb1`
- name: `?AllocateIoPacket@CFileIoChannel@@UEAAJ_KPEAIIPEAXPEAUIIoPacketCompleteEvents@Avenc@Rdp@@PEAPEAUIIoPacket@34@I@Z`
- size: `545`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this, unsigned __int64, unsigned int *, unsigned int Buf2, void *, struct Rdp::Avenc::IIoPacketCompleteEvents *, struct Rdp::Avenc::IIoPacket **, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006f84`
- `0x18000d6d8`
- `0x18000eb00`
- `0x180013b38`
- `0x18003201c`
- `0x180032398`
- `0x180032c90`
- `0x180034120`
- `0x180034c84`
- `0x180035650`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180032d57`
- `msvcp_win!_Mtx_unlock` at `0x180032da4`
- `msvcp_win!_Mtx_unlock` at `0x180032dc6`
- `msvcp_win!_Mtx_unlock` at `0x180032e83`
- `msvcp_win!_Mtx_unlock` at `0x180032d57`
- `msvcp_win!_Mtx_unlock` at `0x180032da4`
- `msvcp_win!_Mtx_unlock` at `0x180032dc6`
- `msvcp_win!_Mtx_unlock` at `0x180032e83`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CFileIoChannel::AllocateIoPacket(
        CFileIoChannel *this,
        __int64 a2,
        unsigned int *a3,
        unsigned int Buf2,
        void *a5,
        struct Rdp::Avenc::IIoPacketCompleteEvents *a6,
        struct Rdp::Avenc::IIoPacket **a7,
        unsigned int a8)
{
  unsigned __int64 v8; // r15
  struct _Mtx_internal_imp_t *v13; // rdi
  CIoPacket *v14; // rax
  char *v15; // rcx
  struct Rdp::Avenc::IIoPacket *v16; // rbx
  const char *Buf1; // [rsp+28h] [rbp-60h]
  _QWORD v18[2]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v19[56]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  CIoPacket *v21; // [rsp+98h] [rbp+10h] BYREF

  v8 = Buf2;
  if ( a2 )
  {
    if ( !a8 || CFileIoChannel::WaitForPendingIoPacketQueue(this, a8) )
    {
      v13 = (CFileIoChannel *)((char *)this + 32);
      v18[1] = (char *)this + 32;
      std::_Mutex_base::lock((CFileIoChannel *)((char *)this + 32));
      if ( *((_BYTE *)this + 433) )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)0x800704C7LL,
          (int)"Channel I/O is cancelled",
          Buf1);
        _Mtx_unlock(v13);
        return 2147943623LL;
      }
      else if ( *((_BYTE *)this + 432) )
      {
        if ( CFileIoChannel::IsPendingIoPacketQueueFull(this) )
        {
          _Mtx_unlock((CFileIoChannel *)((char *)this + 32));
          return 2147942570LL;
        }
        else
        {
          v21 = (CIoPacket *)operator new(0xC8u);
          v14 = CIoPacket::CIoPacket(v21, this, a2, a3, v8, a5, a6);
          wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(&v21, v14);
          v15 = (char *)this + 112;
          v16 = v21;
          v18[0] = v21;
          std::unordered_map<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>::_Insert_or_assign<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &>(
            v15,
            v19,
            v18,
            &v21);
          v21 = 0;
          *a7 = v16;
          wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>((__int64 *)&v21);
          _Mtx_unlock(v13);
          return 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Channel is not started",
          Buf1);
        _Mtx_unlock(v13);
        return 2147549183LL;
      }
    }
    else
    {
      return 2147943860LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)0x80070057LL,
      (int)"PacketLength cannot be 0",
      Buf1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180032c90  mov     [rsp+arg_10], rbx
0x180032c95  mov     [rsp+arg_0], rcx
0x180032c9a  push    rsi
0x180032c9b  push    rdi
0x180032c9c  push    r12
0x180032c9e  push    r14
0x180032ca0  push    r15
0x180032ca2  sub     rsp, 60h
0x180032ca6  mov     r15d, r9d
0x180032ca9  mov     r12, r8
0x180032cac  mov     r14, rdx
0x180032caf  mov     rbx, rcx
0x180032cb2  xor     esi, esi
0x180032cb4  test    rdx, rdx
0x180032cb7  jnz     short loc_180032CED
0x180032cb9  mov     rcx, [rsp+88h]; this
0x180032cc1  lea     rax, aPacketlengthCa; "PacketLength cannot be 0"
0x180032cc8  mov     [rsp+88h+Buf2], rax; int
0x180032ccd  mov     ebx, 80070057h
0x180032cd2  mov     r9d, ebx; char *
0x180032cd5  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032cdc  mov     edx, 1A4h; void *
0x180032ce1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032ce6  mov     eax, ebx
0x180032ce8  jmp     loc_180032E9B
0x180032ced  mov     edx, [rsp+88h+arg_38]; unsigned int
0x180032cf4  test    edx, edx
0x180032cf6  jz      short loc_180032D0B
0x180032cf8  call    ?WaitForPendingIoPacketQueue@CFileIoChannel@@AEAA_NI@Z; CFileIoChannel::WaitForPendingIoPacketQueue(uint)
0x180032cfd  test    al, al
0x180032cff  jnz     short loc_180032D0B
0x180032d01  mov     eax, 800705B4h
0x180032d06  jmp     loc_180032E9B
0x180032d0b  lea     rdi, [rbx+20h]
0x180032d0f  mov     [rsp+88h+var_40], rdi
0x180032d14  mov     rcx, rdi; this
0x180032d17  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180032d1c  nop
0x180032d1d  cmp     byte ptr [rbx+1B1h], 0
0x180032d24  jz      short loc_180032D6A
0x180032d26  mov     rcx, [rsp+88h]; this
0x180032d2e  lea     rax, aChannelIOIsCan; "Channel I/O is cancelled"
0x180032d35  mov     [rsp+88h+Buf2], rax; int
0x180032d3a  mov     ebx, 800704C7h
0x180032d3f  mov     r9d, ebx; char *
0x180032d42  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032d49  mov     edx, 1AFh; void *
0x180032d4e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032d53  nop
0x180032d54  mov     rcx, rdi; _Mtx_t
0x180032d57  call    cs:__imp__Mtx_unlock
0x180032d5e  nop     dword ptr [rax+rax+00h]
0x180032d63  mov     eax, ebx
0x180032d65  jmp     loc_180032E9B
0x180032d6a  cmp     byte ptr [rbx+1B0h], 0
0x180032d71  jnz     short loc_180032DB7
0x180032d73  mov     rcx, [rsp+88h]; this
0x180032d7b  lea     rax, aChannelIsNotSt; "Channel is not started"
0x180032d82  mov     [rsp+88h+Buf2], rax; int
0x180032d87  mov     ebx, 8000FFFFh
0x180032d8c  mov     r9d, ebx; char *
0x180032d8f  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032d96  mov     edx, 1B0h; void *
0x180032d9b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032da0  nop
0x180032da1  mov     rcx, rdi; _Mtx_t
0x180032da4  call    cs:__imp__Mtx_unlock
0x180032dab  nop     dword ptr [rax+rax+00h]
0x180032db0  mov     eax, ebx
0x180032db2  jmp     loc_180032E9B
0x180032db7  mov     rcx, rbx; this
0x180032dba  call    ?IsPendingIoPacketQueueFull@CFileIoChannel@@AEBA_NXZ; CFileIoChannel::IsPendingIoPacketQueueFull(void)
0x180032dbf  test    al, al
0x180032dc1  jz      short loc_180032DDC
0x180032dc3  mov     rcx, rdi; _Mtx_t
0x180032dc6  call    cs:__imp__Mtx_unlock
0x180032dcd  nop     dword ptr [rax+rax+00h]
0x180032dd2  mov     eax, 800700AAh
0x180032dd7  jmp     loc_180032E9B
0x180032ddc  mov     ecx, 0C8h; Size
0x180032de1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032de6  mov     r10, rax
0x180032de9  mov     [rsp+88h+arg_8], rax
0x180032df1  mov     rax, [rsp+88h+arg_28]
0x180032df9  mov     [rsp+88h+var_58], rax; struct Rdp::Avenc::IIoPacketCompleteEvents *
0x180032dfe  mov     rax, [rsp+88h+arg_20]
0x180032e06  mov     [rsp+88h+Buf1], rax; Buf1
0x180032e0b  mov     [rsp+88h+Buf2], r15; Buf2
0x180032e10  mov     r9, r12; unsigned int *
0x180032e13  mov     r8, r14; unsigned __int64
0x180032e16  mov     rdx, rbx; struct CFileIoChannel *
0x180032e19  mov     rcx, r10; this
0x180032e1c  call    ??0CIoPacket@@QEAA@PEAVCFileIoChannel@@_KPEAI1PEAXPEAUIIoPacketCompleteEvents@Avenc@Rdp@@@Z; CIoPacket::CIoPacket(CFileIoChannel *,unsigned __int64,uint *,unsigned __int64,void *,Rdp::Avenc::IIoPacketCompleteEvents *)
0x180032e21  nop
0x180032e22  mov     rdx, rax
0x180032e25  lea     rcx, [rsp+88h+arg_8]
0x180032e2d  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x180032e32  nop
0x180032e33  lea     rcx, [rbx+70h]
0x180032e37  mov     rbx, [rsp+88h+arg_8]
0x180032e3f  mov     [rsp+88h+var_48], rbx
0x180032e44  lea     r9, [rsp+88h+arg_8]
0x180032e4c  lea     r8, [rsp+88h+var_48]
0x180032e51  lea     rdx, [rsp+88h+var_38]
0x180032e56  call    ??$_Insert_or_assign@PEAUIIoPacket@Avenc@Rdp@@AEAV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@7@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAUIIoPacket@Avenc@Rdp@@AEAV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@Z; std::unordered_map<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>::_Insert_or_assign<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &>(Rdp::Avenc::IIoPacket * &&,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &)
0x180032e5b  mov     [rsp+88h+arg_8], 0
0x180032e67  mov     rax, [rsp+88h+arg_30]
0x180032e6f  mov     [rax], rbx
0x180032e72  lea     rcx, [rsp+88h+arg_8]
0x180032e7a  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180032e7f  nop
0x180032e80  mov     rcx, rdi; _Mtx_t
0x180032e83  call    cs:__imp__Mtx_unlock
0x180032e8a  nop     dword ptr [rax+rax+00h]
0x180032e8f  nop
0x180032e90  jmp     short loc_180032E99
0x180032e92  mov     esi, dword ptr [rsp+88h+arg_8]
0x180032e99  mov     eax, esi
0x180032e9b  mov     rbx, [rsp+88h+arg_10]
0x180032ea3  add     rsp, 60h
0x180032ea7  pop     r15
0x180032ea9  pop     r14
0x180032eab  pop     r12
0x180032ead  pop     rdi
0x180032eae  pop     rsi
0x180032eaf  retn
```
