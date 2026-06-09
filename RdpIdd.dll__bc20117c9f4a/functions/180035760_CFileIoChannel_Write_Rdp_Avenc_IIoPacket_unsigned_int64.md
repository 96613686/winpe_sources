# CFileIoChannel::Write(Rdp::Avenc::IIoPacket *,unsigned __int64)

- ea: `0x180035760`
- end: `0x180035940`
- name: `?Write@CFileIoChannel@@UEAAJPEAUIIoPacket@Avenc@Rdp@@_K@Z`
- size: `480`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this, struct Rdp::Avenc::IIoPacket *, unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800089f0`
- `0x18000d6d8`
- `0x18000eb00`
- `0x180013b38`
- `0x18001ddbc`
- `0x180031dd8`
- `0x1800346e4`
- `0x180034904`
- `0x180034c84`
- `0x180035760`
- `0x180035d14`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800357c5`
- `msvcp_win!_Mtx_unlock` at `0x18003580f`
- `msvcp_win!_Mtx_unlock` at `0x18003589a`
- `msvcp_win!_Mtx_unlock` at `0x1800358ec`
- `msvcp_win!_Mtx_unlock` at `0x1800357c5`
- `msvcp_win!_Mtx_unlock` at `0x18003580f`
- `msvcp_win!_Mtx_unlock` at `0x18003589a`
- `msvcp_win!_Mtx_unlock` at `0x1800358ec`

## string_xrefs

- `0x180035866`: `Packet is already pending`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFileIoChannel::Write(CIoPacket **this, struct Rdp::Avenc::IIoPacket *a2, unsigned __int64 a3)
{
  struct _Mtx_internal_imp_t *v5; // rsi
  std::_Mutex_base *v6; // rcx
  __int64 result; // rax
  CIoPacket *v8; // rbx
  unsigned int v9; // eax
  const char *v10; // [rsp+20h] [rbp-38h]
  const char *v11; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct Rdp::Avenc::IIoPacket *v14; // [rsp+68h] [rbp+10h] BYREF
  CIoPacket *v15; // [rsp+78h] [rbp+20h] BYREF

  v14 = a2;
  v5 = (struct _Mtx_internal_imp_t *)(this + 4);
  v6 = (std::_Mutex_base *)(this + 4);
  try
  {
    std::_Mutex_base::lock(v6);
    if ( *((_BYTE *)this + 433) )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0x800704C7LL,
        (int)"Channel I/O is cancelled",
        v11);
      _Mtx_unlock(v5);
      result = 2147943623LL;
    }
    else if ( *((_BYTE *)this + 432) )
    {
      std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::find(
        this + 14,
        &v15,
        &v14);
      if ( v15 == this[15] )
      {
        v9 = wil::verify_hresult<long>(2147943568LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x1F2,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)v9,
          (int)"Unable to find Io packet",
          v11);
      }
      wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(
        &v15,
        *((_QWORD *)v15 + 3));
      v8 = v15;
      if ( *((_BYTE *)v15 + 193) )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1F6,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)0x80004005LL,
          (int)"Packet is already pending",
          v11);
        wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v15);
        _Mtx_unlock(v5);
        result = 2147500037LL;
      }
      else
      {
        if ( a3 )
          CIoPacket::Resize(v15, a3);
        *((_BYTE *)v8 + 193) = 1;
        std::list<wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>::_Emplace<wil::com_ptr_t<CIoPacket,wil::err_exception_policy> const &>(
          this + 22,
          this[22],
          &v15);
        CFileIoChannel::ProcessPendingIoPacketQueue((CFileIoChannel *)this);
        wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v15);
        _Mtx_unlock(v5);
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1ED,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Channel is not started",
        v11);
      _Mtx_unlock(v5);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    CFileIoChannel::CancelAllPendingIo((__int64)this, 1u);
    return (unsigned int)wil::details::in1diag3::Return_CaughtExceptionMsg(
                           retaddr,
                           (void *)0x204,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           "Failed to write IO packet",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180035760  mov     rax, rsp
0x180035763  mov     [rax+18h], rbx
0x180035767  mov     [rax+10h], rdx
0x18003576b  mov     [rax+8], rcx
0x18003576f  push    rsi
0x180035770  push    rdi
0x180035771  push    r14
0x180035773  sub     rsp, 40h
0x180035777  mov     r14, r8
0x18003577a  mov     rdi, rcx
0x18003577d  lea     rsi, [rcx+20h]
0x180035781  mov     [rax-28h], rsi
0x180035785  mov     rcx, rsi; this
0x180035788  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003578d  nop
0x18003578e  cmp     byte ptr [rdi+1B1h], 0
0x180035795  jz      short loc_1800357D8
0x180035797  mov     rcx, [rsp+58h]; this
0x18003579c  lea     rax, aChannelIOIsCan; "Channel I/O is cancelled"
0x1800357a3  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800357a8  mov     ebx, 800704C7h
0x1800357ad  mov     r9d, ebx; char *
0x1800357b0  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800357b7  mov     edx, 1ECh; void *
0x1800357bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800357c1  nop
0x1800357c2  mov     rcx, rsi; _Mtx_t
0x1800357c5  call    cs:__imp__Mtx_unlock
0x1800357cc  nop     dword ptr [rax+rax+00h]
0x1800357d1  mov     eax, ebx
0x1800357d3  jmp     loc_180035900
0x1800357d8  cmp     byte ptr [rdi+1B0h], 0
0x1800357df  jnz     short loc_180035822
0x1800357e1  mov     rcx, [rsp+58h]; this
0x1800357e6  lea     rax, aChannelIsNotSt; "Channel is not started"
0x1800357ed  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800357f2  mov     ebx, 8000FFFFh
0x1800357f7  mov     r9d, ebx; char *
0x1800357fa  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180035801  mov     edx, 1EDh; void *
0x180035806  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003580b  nop
0x18003580c  mov     rcx, rsi; _Mtx_t
0x18003580f  call    cs:__imp__Mtx_unlock
0x180035816  nop     dword ptr [rax+rax+00h]
0x18003581b  mov     eax, ebx
0x18003581d  jmp     loc_180035900
0x180035822  lea     rcx, [rdi+70h]
0x180035826  lea     r8, [rsp+58h+arg_8]
0x18003582b  lea     rdx, [rsp+58h+arg_18]
0x180035830  call    ?find@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBQEAUIIoPacket@Avenc@Rdp@@@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::find(Rdp::Avenc::IIoPacket * const &)
0x180035835  mov     rdx, [rsp+58h+arg_18]
0x18003583a  cmp     rdx, [rdi+78h]
0x18003583e  jz      loc_18003590F
0x180035844  mov     rdx, [rdx+18h]
0x180035848  lea     rcx, [rsp+58h+arg_18]
0x18003584d  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x180035852  nop
0x180035853  mov     rbx, [rsp+58h+arg_18]
0x180035858  cmp     byte ptr [rbx+0C1h], 0
0x18003585f  jz      short loc_1800358AA
0x180035861  mov     rcx, [rsp+58h]; this
0x180035866  lea     rax, aPacketIsAlread; "Packet is already pending"
0x18003586d  mov     qword ptr [rsp+58h+var_38], rax; int
0x180035872  mov     ebx, 80004005h
0x180035877  mov     r9d, ebx; char *
0x18003587a  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180035881  mov     edx, 1F6h; void *
0x180035886  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003588b  nop
0x18003588c  lea     rcx, [rsp+58h+arg_18]
0x180035891  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180035896  nop
0x180035897  mov     rcx, rsi; _Mtx_t
0x18003589a  call    cs:__imp__Mtx_unlock
0x1800358a1  nop     dword ptr [rax+rax+00h]
0x1800358a6  mov     eax, ebx
0x1800358a8  jmp     short loc_180035900
0x1800358aa  test    r14, r14
0x1800358ad  jz      short loc_1800358BA
0x1800358af  mov     rdx, r14; unsigned __int64
0x1800358b2  mov     rcx, rbx; this
0x1800358b5  call    ?Resize@CIoPacket@@QEAAX_K@Z; CIoPacket::Resize(unsigned __int64)
0x1800358ba  mov     byte ptr [rbx+0C1h], 1
0x1800358c1  lea     rcx, [rdi+0B0h]
0x1800358c8  lea     r8, [rsp+58h+arg_18]
0x1800358cd  mov     rdx, [rcx]
0x1800358d0  call    ??$_Emplace@AEBV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@?$list@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@PEAX@1@QEAU21@AEBV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@Z; std::list<wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>::_Emplace<wil::com_ptr_t<CIoPacket,wil::err_exception_policy> const &>(std::_List_node<wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,void *> * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> const &)
0x1800358d5  mov     rcx, rdi; this
0x1800358d8  call    ?ProcessPendingIoPacketQueue@CFileIoChannel@@AEAAXXZ; CFileIoChannel::ProcessPendingIoPacketQueue(void)
0x1800358dd  nop
0x1800358de  lea     rcx, [rsp+58h+arg_18]
0x1800358e3  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x1800358e8  nop
0x1800358e9  mov     rcx, rsi; _Mtx_t
0x1800358ec  call    cs:__imp__Mtx_unlock
0x1800358f3  nop     dword ptr [rax+rax+00h]
0x1800358f8  xor     eax, eax
0x1800358fa  jmp     short loc_180035900
0x1800358fc  mov     eax, [rsp+58h+arg_0]
0x180035900  mov     rbx, [rsp+58h+arg_10]
0x180035905  add     rsp, 40h
0x180035909  pop     r14
0x18003590b  pop     rdi
0x18003590c  pop     rsi
0x18003590d  retn
0x18003590f  mov     ecx, 80070490h
0x180035914  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180035919  mov     r9d, eax; char *
0x18003591c  mov     rcx, [rsp+58h]; this
0x180035921  lea     rax, aUnableToFindIo; "Unable to find Io packet"
0x180035928  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003592d  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180035934  mov     edx, 1F2h; void *
0x180035939  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
