# CMidi2KSAggregateMidiBidi::~CMidi2KSAggregateMidiBidi(void)

- ea: `0x180012434`
- end: `0x180012496`
- name: `??1CMidi2KSAggregateMidiBidi@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CMidi2KSAggregateMidiBidi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800124a0`

## callees

- `0x180005044`
- `0x18000d430`
- `0x180012304`
- `0x180012380`
- `0x180012434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012468`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012468`

## pseudocode

```c
void __fastcall CMidi2KSAggregateMidiBidi::~CMidi2KSAggregateMidiBidi(CMidi2KSAggregateMidiBidi *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 7);
  if ( v1 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(&v1[2]);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v1[1].LockSemaphore);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v1[1].LockCount);
    DeleteCriticalSection(v1);
    operator delete(v1);
  }
  std::wstring::~wstring((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180012434  mov     [rsp+arg_0], rbx
0x180012439  push    rdi
0x18001243a  sub     rsp, 20h
0x18001243e  mov     rbx, [rcx+38h]
0x180012442  mov     rdi, rcx
0x180012445  test    rbx, rbx
0x180012448  jz      short loc_18001247B
0x18001244a  lea     rcx, [rbx+50h]
0x18001244e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(void)
0x180012453  lea     rcx, [rbx+40h]
0x180012457  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001245c  lea     rcx, [rbx+30h]
0x180012460  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x180012465  mov     rcx, rbx; lpCriticalSection
0x180012468  call    cs:__imp_DeleteCriticalSection
0x18001246e  mov     edx, 60h ; '`'
0x180012473  mov     rcx, rbx; Block
0x180012476  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001247b  lea     rcx, [rdi+10h]; void *
0x18001247f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012484  mov     rbx, [rsp+28h+arg_0]
0x180012489  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180012490  add     rsp, 20h
0x180012494  pop     rdi
0x180012495  retn
```
