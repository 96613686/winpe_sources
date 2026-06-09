# CFileIoChannel::Cancel(Rdp::Avenc::IIoPacket *)

- ea: `0x180032ec0`
- end: `0x1800330eb`
- name: `?Cancel@CFileIoChannel@@UEAAJPEAUIIoPacket@Avenc@Rdp@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this, struct Rdp::Avenc::IIoPacket *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800089f0`
- `0x18000d6d8`
- `0x18000eb00`
- `0x180013b38`
- `0x18001ddbc`
- `0x180031a20`
- `0x180032ec0`
- `0x1800330f4`
- `0x180034c84`
- `0x180035978`
- `0x180035c68`
- `0x180035d14`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180032f21`
- `msvcp_win!_Mtx_unlock` at `0x180032f6b`
- `msvcp_win!_Mtx_unlock` at `0x180032ffa`
- `msvcp_win!_Mtx_unlock` at `0x18003304e`
- `msvcp_win!_Mtx_unlock` at `0x180033099`
- `msvcp_win!_Mtx_unlock` at `0x180032f21`
- `msvcp_win!_Mtx_unlock` at `0x180032f6b`
- `msvcp_win!_Mtx_unlock` at `0x180032ffa`
- `msvcp_win!_Mtx_unlock` at `0x18003304e`
- `msvcp_win!_Mtx_unlock` at `0x180033099`

## string_xrefs

- `0x180032fc7`: `Packet is already completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileIoChannel::Cancel(CFileIoChannel *this, struct Rdp::Avenc::IIoPacket *a2)
{
  struct _Mtx_internal_imp_t *v3; // rsi
  std::_Mutex_base *v4; // rcx
  __int64 result; // rax
  char *v6; // r14
  _QWORD *v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  const char *v12; // r9
  const char *v13; // [rsp+20h] [rbp-38h]
  const char *v14; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct Rdp::Avenc::IIoPacket *v17; // [rsp+68h] [rbp+10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+18h] BYREF
  char *v19; // [rsp+78h] [rbp+20h]

  v17 = a2;
  v3 = (CFileIoChannel *)((char *)this + 32);
  v19 = (char *)this + 32;
  v4 = (CFileIoChannel *)((char *)this + 32);
  try
  {
    std::_Mutex_base::lock(v4);
    if ( *((_BYTE *)this + 433) )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x220,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0x800704C7LL,
        (int)"Channel I/O is cancelled",
        v14);
      _Mtx_unlock(v3);
      result = 2147943623LL;
    }
    else if ( *((_BYTE *)this + 432) )
    {
      v6 = (char *)this + 112;
      std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::find(
        (char *)this + 112,
        &v18,
        &v17);
      v7 = (_QWORD *)((char *)this + 120);
      v8 = v18;
      if ( v18 == *v7 )
      {
        v12 = (const char *)(unsigned int)wil::verify_hresult<long>(2147943568LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x226,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          v12,
          (int)"Unable to find Io packet",
          v14);
      }
      wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(
        &v18,
        *(_QWORD *)(v18 + 24));
      v10 = v18;
      if ( *(_BYTE *)(v18 + 192) )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x22A,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)0x80004005LL,
          (int)"Packet is already completed",
          v14);
        wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v18);
        _Mtx_unlock(v3);
        result = 2147500037LL;
      }
      else if ( *(_BYTE *)(v18 + 193) )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x22B,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
          (const char *)0x80004005LL,
          (int)"Packet is not cancellable",
          v14);
        wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v18);
        _Mtx_unlock(v3);
        result = 2147500037LL;
      }
      else
      {
        v11 = std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>::operator()<Rdp::Avenc::IIoPacket *>(
                v9,
                v8 + 16);
        std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Erase_bucket(
          v6,
          v8,
          v11 & *((_QWORD *)v6 + 6));
        std::list<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>::_Unchecked_erase(v7);
        CIoPacket::Cancel(v10, 0);
        wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v18);
        _Mtx_unlock(v3);
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Channel is not started",
        v14);
      _Mtx_unlock(v3);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    CFileIoChannel::CancelAllPendingIo((__int64)this, 1u);
    return (unsigned int)wil::details::in1diag3::Return_CaughtExceptionMsg(
                           retaddr,
                           (void *)0x233,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           "Failed to cancel IO packet",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180032ec0  mov     [rsp+arg_8], rdx
0x180032ec5  mov     [rsp+arg_0], rcx
0x180032eca  push    rbx
0x180032ecb  push    rsi
0x180032ecc  push    rdi
0x180032ecd  push    r14
0x180032ecf  push    r15
0x180032ed1  sub     rsp, 30h
0x180032ed5  mov     rbx, rcx
0x180032ed8  lea     rsi, [rcx+20h]
0x180032edc  mov     [rsp+58h+arg_18], rsi
0x180032ee1  mov     rcx, rsi; this
0x180032ee4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180032ee9  nop
0x180032eea  cmp     byte ptr [rbx+1B1h], 0
0x180032ef1  jz      short loc_180032F34
0x180032ef3  mov     rcx, [rsp+58h]; this
0x180032ef8  lea     rax, aChannelIOIsCan; "Channel I/O is cancelled"
0x180032eff  mov     qword ptr [rsp+58h+var_38], rax; int
0x180032f04  mov     ebx, 800704C7h
0x180032f09  mov     r9d, ebx; char *
0x180032f0c  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032f13  mov     edx, 220h; void *
0x180032f18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032f1d  nop
0x180032f1e  mov     rcx, rsi; _Mtx_t
0x180032f21  call    cs:__imp__Mtx_unlock
0x180032f28  nop     dword ptr [rax+rax+00h]
0x180032f2d  mov     eax, ebx
0x180032f2f  jmp     loc_1800330AD
0x180032f34  cmp     byte ptr [rbx+1B0h], 0
0x180032f3b  jnz     short loc_180032F7E
0x180032f3d  mov     rcx, [rsp+58h]; this
0x180032f42  lea     rax, aChannelIsNotSt; "Channel is not started"
0x180032f49  mov     qword ptr [rsp+58h+var_38], rax; int
0x180032f4e  mov     ebx, 8000FFFFh
0x180032f53  mov     r9d, ebx; char *
0x180032f56  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032f5d  mov     edx, 221h; void *
0x180032f62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032f67  nop
0x180032f68  mov     rcx, rsi; _Mtx_t
0x180032f6b  call    cs:__imp__Mtx_unlock
0x180032f72  nop     dword ptr [rax+rax+00h]
0x180032f77  mov     eax, ebx
0x180032f79  jmp     loc_1800330AD
0x180032f7e  lea     r14, [rbx+70h]
0x180032f82  lea     r8, [rsp+58h+arg_8]
0x180032f87  lea     rdx, [rsp+58h+arg_10]
0x180032f8c  mov     rcx, r14
0x180032f8f  call    ?find@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBQEAUIIoPacket@Avenc@Rdp@@@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::find(Rdp::Avenc::IIoPacket * const &)
0x180032f94  lea     r15, [rbx+78h]
0x180032f98  mov     rbx, [rsp+58h+arg_10]
0x180032f9d  cmp     rbx, [r15]
0x180032fa0  jz      loc_1800330BA
0x180032fa6  mov     rdx, [rbx+18h]
0x180032faa  lea     rcx, [rsp+58h+arg_10]
0x180032faf  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x180032fb4  mov     rdi, [rsp+58h+arg_10]
0x180032fb9  cmp     byte ptr [rdi+0C0h], 0
0x180032fc0  jz      short loc_18003300D
0x180032fc2  mov     rcx, [rsp+58h]; this
0x180032fc7  lea     rax, aPacketIsAlread_0; "Packet is already completed"
0x180032fce  mov     qword ptr [rsp+58h+var_38], rax; int
0x180032fd3  mov     ebx, 80004005h
0x180032fd8  mov     r9d, ebx; char *
0x180032fdb  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180032fe2  mov     edx, 22Ah; void *
0x180032fe7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180032fec  lea     rcx, [rsp+58h+arg_10]
0x180032ff1  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180032ff6  nop
0x180032ff7  mov     rcx, rsi; _Mtx_t
0x180032ffa  call    cs:__imp__Mtx_unlock
0x180033001  nop     dword ptr [rax+rax+00h]
0x180033006  mov     eax, ebx
0x180033008  jmp     loc_1800330AD
0x18003300d  cmp     byte ptr [rdi+0C1h], 0
0x180033014  jz      short loc_18003305E
0x180033016  mov     rcx, [rsp+58h]; this
0x18003301b  lea     rax, aPacketIsNotCan; "Packet is not cancellable"
0x180033022  mov     qword ptr [rsp+58h+var_38], rax; int
0x180033027  mov     ebx, 80004005h
0x18003302c  mov     r9d, ebx; char *
0x18003302f  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180033036  mov     edx, 22Bh; void *
0x18003303b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033040  lea     rcx, [rsp+58h+arg_10]
0x180033045  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x18003304a  nop
0x18003304b  mov     rcx, rsi; _Mtx_t
0x18003304e  call    cs:__imp__Mtx_unlock
0x180033055  nop     dword ptr [rax+rax+00h]
0x18003305a  mov     eax, ebx
0x18003305c  jmp     short loc_1800330AD
0x18003305e  lea     rdx, [rbx+10h]
0x180033062  call    ??$?RPEAUIIoPacket@Avenc@Rdp@@@?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@QEBA_KAEBQEAUIIoPacket@Avenc@Rdp@@@Z; std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>::operator()<Rdp::Avenc::IIoPacket *>(Rdp::Avenc::IIoPacket * const &)
0x180033067  mov     r8, [r14+30h]
0x18003306b  and     r8, rax
0x18003306e  mov     rdx, rbx
0x180033071  mov     rcx, r14
0x180033074  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Erase_bucket(std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *> *,unsigned __int64)
0x180033079  mov     rcx, r15
0x18003307c  call    ?_Unchecked_erase@?$list@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>::_Unchecked_erase(std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *> * const)
0x180033081  xor     edx, edx
0x180033083  mov     rcx, rdi
0x180033086  call    ?Cancel@CIoPacket@@QEAAXW4CancelReason@IoPacket@@@Z; CIoPacket::Cancel(IoPacket::CancelReason)
0x18003308b  lea     rcx, [rsp+58h+arg_10]
0x180033090  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180033095  nop
0x180033096  mov     rcx, rsi; _Mtx_t
0x180033099  call    cs:__imp__Mtx_unlock
0x1800330a0  nop     dword ptr [rax+rax+00h]
0x1800330a5  xor     eax, eax
0x1800330a7  jmp     short loc_1800330AD
0x1800330a9  mov     eax, dword ptr [rsp+58h+arg_0]
0x1800330ad  add     rsp, 30h
0x1800330b1  pop     r15
0x1800330b3  pop     r14
0x1800330b5  pop     rdi
0x1800330b6  pop     rsi
0x1800330b7  pop     rbx
0x1800330b8  retn
0x1800330ba  mov     ecx, 80070490h
0x1800330bf  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800330c4  mov     r9d, eax; char *
0x1800330c7  mov     rcx, [rsp+58h]; this
0x1800330cc  lea     rax, aUnableToFindIo; "Unable to find Io packet"
0x1800330d3  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800330d8  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800330df  mov     edx, 226h; void *
0x1800330e4  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
