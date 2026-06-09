# Wns::CPTransactionRequestManager::CPTransactionRequestManager(Wns::ConnectionStateMachine * const)

- ea: `0x180024a50`
- end: `0x180024bd7`
- name: `??0CPTransactionRequestManager@Wns@@QEAA@QEAVConnectionStateMachine@1@@Z`
- size: `391`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, struct Wns::ConnectionStateMachine *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180024830`

## callees

- `0x18000b6c0`
- `0x180016890`
- `0x180021750`
- `0x180026adc`
- `0x18002fafc`
- `0x18002fc0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180024b3c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180024b3c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180024ae3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180024ae3`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall Wns::CPTransactionRequestManager::CPTransactionRequestManager(
        struct _RTL_CRITICAL_SECTION *this,
        struct Wns::ConnectionStateMachine *const a2)
{
  LONG *p_LockCount; // rbx
  _QWORD *v5; // rax
  const char *v7; // [rsp+30h] [rbp-8h]
  const char *v8; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LONG *v10; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(this->DebugInfo) = 0;
  p_LockCount = &this->LockCount;
  v10 = &this->LockCount;
  this->LockCount = 0;
  this->OwningThread = 0;
  this->LockSemaphore = 0;
  v5 = operator new(0x28u);
  *v5 = v5;
  v5[1] = v5;
  *((_QWORD *)p_LockCount + 1) = v5;
  *((_QWORD *)p_LockCount + 3) = 0;
  *((_QWORD *)p_LockCount + 4) = 0;
  *((_QWORD *)p_LockCount + 5) = 0;
  *((_QWORD *)p_LockCount + 6) = 7;
  *((_QWORD *)p_LockCount + 7) = 8;
  *p_LockCount = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>>>::_Assign_grow(
    p_LockCount + 6,
    16,
    *((_QWORD *)p_LockCount + 1));
  this[1].SpinCount = (ULONG_PTR)CreateTimerQueue();
  this[2].DebugInfo = 0;
  *(_QWORD *)&this[2].LockCount = 0;
  this[2].OwningThread = 0;
  LODWORD(v10) = 0;
  std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>(
    (__int64)&this[2].LockSemaphore,
    &v10);
  std::unordered_map<unsigned __int64,enum Wns::CPTMode>::unordered_map<unsigned __int64,enum Wns::CPTMode>(&this[4].LockCount);
  this[5].SpinCount = (ULONG_PTR)a2;
  InitializeCriticalSectionEx(this + 6, 0, 0);
  this[7].DebugInfo = 0;
  *(_QWORD *)&this[7].LockCount = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x24,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\cptransactionrequestmanager.cpp",
    (const char *)0x80070057LL,
    this[5].SpinCount == 0,
    (bool)"Parent must not be null",
    v7);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\cptransactionrequestmanager.cpp",
    (const char *)0x8000FFFFLL,
    this[1].SpinCount - 1 <= 0xFFFFFFFFFFFFFFFDuLL,
    (bool)"Could not initialize timer queue",
    v8);
  return this;
}

```

## disassembly

```asm
0x180024a50  mov     rax, rsp
0x180024a53  mov     [rax+10h], rbx
0x180024a57  mov     [rax+20h], rsi
0x180024a5b  mov     [rax+8], rcx
0x180024a5f  push    rdi; char *
0x180024a60  sub     rsp, 30h
0x180024a64  mov     rdi, rdx
0x180024a67  mov     rsi, rcx
0x180024a6a  mov     dword ptr [rcx], 0
0x180024a70  lea     rbx, [rcx+8]
0x180024a74  mov     [rax+18h], rbx
0x180024a78  mov     dword ptr [rbx], 0
0x180024a7e  mov     qword ptr [rbx+8], 0
0x180024a86  mov     qword ptr [rbx+10h], 0
0x180024a8e  mov     ecx, 28h ; '('; Size
0x180024a93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024a98  mov     [rax], rax
0x180024a9b  mov     [rax+8], rax
0x180024a9f  mov     [rbx+8], rax
0x180024aa3  lea     rcx, [rbx+18h]
0x180024aa7  mov     qword ptr [rcx], 0
0x180024aae  mov     qword ptr [rcx+8], 0
0x180024ab6  mov     qword ptr [rcx+10h], 0
0x180024abe  mov     qword ptr [rbx+30h], 7
0x180024ac6  mov     qword ptr [rbx+38h], 8
0x180024ace  mov     dword ptr [rbx], 3F800000h
0x180024ad4  mov     r8, [rbx+8]
0x180024ad8  mov     edx, 10h
0x180024add  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<long const,Wns::ChannelRequestContext>>>>)
0x180024ae2  nop
0x180024ae3  call    cs:__imp_CreateTimerQueue
0x180024ae9  mov     [rsi+48h], rax
0x180024aed  mov     qword ptr [rsi+50h], 0
0x180024af5  mov     qword ptr [rsi+58h], 0
0x180024afd  mov     qword ptr [rsi+60h], 0
0x180024b05  lea     rcx, [rsi+68h]
0x180024b09  mov     dword ptr [rsp+38h+arg_10], 0
0x180024b11  lea     rdx, [rsp+38h+arg_10]
0x180024b16  call    ??0?$_Hash@V?$_Umap_traits@_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@1@AEBV?$allocator@U?$pair@$$CB_KV?$vector@UChannelRequestInternal@Wns@@V?$allocator@UChannelRequestInternal@Wns@@@std@@@std@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Wns::ChannelRequestInternal>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>>,0>>(std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>> const &,std::allocator<std::pair<unsigned __int64 const,std::vector<Wns::ChannelRequestInternal>>> const &)
0x180024b1b  nop
0x180024b1c  lea     rcx, [rsi+0A8h]
0x180024b23  call    ??0?$unordered_map@_KW4CPTMode@Wns@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KW4CPTMode@Wns@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,Wns::CPTMode>::unordered_map<unsigned __int64,Wns::CPTMode>(void)
0x180024b28  nop
0x180024b29  mov     [rsi+0E8h], rdi
0x180024b30  lea     rcx, [rsi+0F0h]; lpCriticalSection
0x180024b37  xor     r8d, r8d; Flags
0x180024b3a  xor     edx, edx; dwSpinCount
0x180024b3c  call    cs:__imp_InitializeCriticalSectionEx
0x180024b42  nop
0x180024b43  xor     eax, eax
0x180024b45  mov     [rsi+118h], rax
0x180024b4c  mov     [rsi+120h], rax
0x180024b53  cmp     [rsi+0E8h], rax
0x180024b5a  setz    al
0x180024b5d  mov     rcx, [rsp+38h]; this
0x180024b62  lea     rdx, aParentMustNotB; "Parent must not be null"
0x180024b69  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180024b6e  mov     [rsp+38h+var_18], al; char
0x180024b72  mov     r9d, 80070057h; char *
0x180024b78  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024b7f  mov     edx, 24h ; '$'; void *
0x180024b84  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180024b89  mov     rax, [rsi+48h]
0x180024b8d  dec     rax
0x180024b90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024b94  setbe   al
0x180024b97  mov     rcx, [rsp+38h]; this
0x180024b9c  lea     rdx, aCouldNotInitia; "Could not initialize timer queue"
0x180024ba3  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180024ba8  mov     [rsp+38h+var_18], al; char
0x180024bac  mov     r9d, 8000FFFFh; char *
0x180024bb2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024bb9  mov     edx, 25h ; '%'; void *
0x180024bbe  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x180024bc3  nop
0x180024bc4  mov     rax, rsi
0x180024bc7  mov     rbx, [rsp+38h+arg_8]
0x180024bcc  mov     rsi, [rsp+38h+arg_18]
0x180024bd1  add     rsp, 30h
0x180024bd5  pop     rdi
0x180024bd6  retn
```
