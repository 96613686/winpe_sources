# CallAudioRouting::_OnAudioDeviceAdded(Windows::Devices::Enumeration::IDeviceWatcher *,Windows::Devices::Enumeration::IDeviceInformation *)

- ea: `0x180068840`
- end: `0x180068a70`
- name: `?_OnAudioDeviceAdded@CallAudioRouting@@AEAAJPEAUIDeviceWatcher@Enumeration@Devices@Windows@@PEAUIDeviceInformation@345@@Z`
- size: `560`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this, struct Windows::Devices::Enumeration::IDeviceWatcher *, struct Windows::Devices::Enumeration::IDeviceInformation *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x180059298`
- `0x18005f9c0`
- `0x180063a78`
- `0x180068840`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068870`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006892e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006892e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068a34`

## string_xrefs

- `0x180068894`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800688e4`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068970`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_OnAudioDeviceAdded(
        CallAudioRouting *this,
        struct Windows::Devices::Enumeration::IDeviceWatcher *a2,
        struct Windows::Devices::Enumeration::IDeviceInformation *a3)
{
  int v5; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::Devices::Enumeration::IDeviceInformation *, HSTRING *); // rbx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // r8
  BackTraceCollection *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // eax
  BackTraceCollection *v18; // rcx
  CallAudioRouting *v20; // [rsp+60h] [rbp-19h] BYREF
  __int64 (__fastcall *v21)(CallAudioRouting *); // [rsp+68h] [rbp-11h] BYREF
  int v22; // [rsp+70h] [rbp-9h]
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  void *Block[2]; // [rsp+80h] [rbp+7h] BYREF
  __int16 v25; // [rsp+90h] [rbp+17h] BYREF
  __int64 v26; // [rsp+92h] [rbp+19h]
  int v27; // [rsp+9Ah] [rbp+21h]
  __int16 v28; // [rsp+9Eh] [rbp+25h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = CallAudioRouting::_CheckShutdown(this);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v8 = *(_QWORD *)a3;
    string = 0;
    v9 = *(__int64 (__fastcall **)(struct Windows::Devices::Enumeration::IDeviceInformation *, HSTRING *))(v8 + 48);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(a3, &string);
    v7 = v10;
    if ( v10 >= 0 )
    {
      Block[0] = &v25;
      v26 = 0;
      Block[1] = &v25;
      v27 = 0;
      v28 = 0;
      v25 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
      {
        v13 = -1;
        do
          ++v13;
        while ( StringRawBuffer[v13] );
      }
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
      {
        v22 = 0;
        v21 = CallAudioRouting::_HandleAudioDeviceAdded;
        v20 = this;
        if ( this )
          (*(void (__fastcall **)(CallAudioRouting *))(*(_QWORD *)this + 8LL))(this);
        v17 = QueueAsyncWorkItemBase_ATL::CComPtr_CallAudioRouting__long____cdecl_CallAudioRouting::___utl::basic_string_unsigned_short_utl::char_traits_unsigned_short__utl::allocator_unsigned_short____const____utl::basic_string_unsigned_short_utl::char_traits_unsigned_short__utl::allocator_unsigned_short____detail::Empty_detail::Empty_detail::Empty_detail::Empty_detail::Empty_detail::Empty_detail::Empty_detail::Empty_(
                *((_QWORD *)this + 27),
                &v20,
                &v21,
                Block);
        v18 = v20;
        v7 = v17;
        if ( v20 )
          (*(void (__fastcall **)(CallAudioRouting *))(*(_QWORD *)v20 + 16LL))(v20);
        if ( (v7 & 0x80000000) == 0 )
        {
          if ( Block[0] != &v25 )
            operator delete(Block[0]);
          WindowsDeleteString(string);
          v7 = 0;
          goto LABEL_22;
        }
        BackTraceCollection::Capture(v18, v7);
        v15 = 454;
        v16 = 1;
      }
      else
      {
        v7 = -2147024882;
        BackTraceCollection::Capture(v14, -2147024882);
        v15 = 451;
        v16 = 0;
      }
      Log_HREvent_17(v7, v16, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v15);
      if ( Block[0] != &v25 )
        operator delete(Block[0]);
    }
    else
    {
      BackTraceCollection::Capture(v11, v10);
      Log_HREvent_17(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 448);
    }
    WindowsDeleteString(string);
LABEL_22:
    string = 0;
    goto LABEL_23;
  }
  BackTraceCollection::Capture(v6, v5);
  Log_HREvent_17(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 445);
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return v7;
}

```

## disassembly

```asm
0x180068840  mov     [rsp-8+arg_8], rbx
0x180068845  push    rbp
0x180068846  push    rsi
0x180068847  push    rdi
0x180068848  push    r14
0x18006884a  push    r15
0x18006884c  lea     rbp, [rsp-37h]
0x180068851  sub     rsp, 0B0h
0x180068858  mov     rax, cs:__security_cookie
0x18006885f  xor     rax, rsp
0x180068862  mov     [rbp+57h+var_30], rax
0x180068866  mov     rdi, rcx
0x180068869  mov     rsi, r8
0x18006886c  add     rcx, 58h ; 'X'; lpCriticalSection
0x180068870  call    cs:__imp_EnterCriticalSection
0x180068876  mov     rcx, rdi; this
0x180068879  call    ?_CheckShutdown@CallAudioRouting@@AEAAJXZ; CallAudioRouting::_CheckShutdown(void)
0x18006887e  xor     r15d, r15d
0x180068881  mov     ebx, eax
0x180068883  test    eax, eax
0x180068885  jns     short loc_1800688AB
0x180068887  mov     edx, eax; int
0x180068889  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006888e  mov     r9d, 1BDh
0x180068894  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006889b  lea     edx, [r15+1]
0x18006889f  mov     ecx, ebx
0x1800688a1  call    Log_HREvent_17
0x1800688a6  jmp     loc_180068A41
0x1800688ab  mov     rax, [rsi]
0x1800688ae  xor     ecx, ecx; string
0x1800688b0  mov     [rbp+57h+string], r15
0x1800688b4  mov     rbx, [rax+30h]
0x1800688b8  call    cs:__imp_WindowsDeleteString
0x1800688be  lea     rdx, [rbp+57h+string]
0x1800688c2  mov     [rbp+57h+string], r15
0x1800688c6  mov     rcx, rsi
0x1800688c9  mov     rax, rbx
0x1800688cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688d1  mov     ebx, eax
0x1800688d3  test    eax, eax
0x1800688d5  jns     short loc_180068906
0x1800688d7  mov     edx, eax; int
0x1800688d9  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800688de  mov     r9d, 1C0h
0x1800688e4  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800688eb  mov     edx, 1
0x1800688f0  mov     ecx, ebx
0x1800688f2  call    Log_HREvent_17
0x1800688f7  mov     rcx, [rbp+57h+string]; string
0x1800688fb  call    cs:__imp_WindowsDeleteString
0x180068901  jmp     loc_180068A3D
0x180068906  mov     rcx, [rbp+57h+string]; string
0x18006890a  lea     rax, [rbp+57h+var_40]
0x18006890e  mov     [rbp+57h+Block], rax
0x180068912  xor     edx, edx; length
0x180068914  lea     rax, [rbp+57h+var_40]
0x180068918  mov     [rbp+57h+var_3E], r15
0x18006891c  mov     [rbp+57h+var_48], rax
0x180068920  mov     [rbp+57h+var_36], r15d
0x180068924  mov     [rbp+57h+var_32], r15w
0x180068929  mov     [rbp+57h+var_40], r15w
0x18006892e  call    cs:__imp_WindowsGetStringRawBuffer
0x180068934  test    rax, rax
0x180068937  jz      short loc_180068949
0x180068939  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006893d  inc     r8
0x180068940  cmp     [rax+r8*2], r15w
0x180068945  jnz     short loc_18006893D
0x180068947  jmp     short loc_18006894C
0x180068949  mov     r8, r15
0x18006894c  mov     rdx, rax
0x18006894f  lea     rcx, [rbp+57h+Block]
0x180068953  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180068958  test    al, al
0x18006895a  jnz     short loc_1800689A0
0x18006895c  mov     ebx, 8007000Eh
0x180068961  mov     edx, ebx; int
0x180068963  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068968  mov     r9d, 1C3h
0x18006896e  xor     edx, edx
0x180068970  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068977  mov     ecx, ebx
0x180068979  call    Log_HREvent_17
0x18006897e  mov     rcx, [rbp+57h+Block]; Block
0x180068982  lea     rax, [rbp+57h+var_40]
0x180068986  cmp     rcx, rax
0x180068989  jz      loc_1800688F7
0x18006898f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180068996  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006899b  jmp     loc_1800688F7
0x1800689a0  mov     [rbp+57h+var_60], r15d
0x1800689a4  lea     rax, ?_HandleAudioDeviceAdded@CallAudioRouting@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CallAudioRouting::_HandleAudioDeviceAdded(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x1800689ab  mov     [rbp+57h+var_68], rax
0x1800689af  mov     eax, [rbp+57h+var_5C]
0x1800689b2  mov     [rbp+57h+var_5C], eax
0x1800689b5  mov     [rbp+57h+var_70], rdi
0x1800689b9  test    rdi, rdi
0x1800689bc  jz      short loc_1800689CD
0x1800689be  mov     rax, [rdi]
0x1800689c1  mov     rcx, rdi
0x1800689c4  mov     rax, [rax+8]
0x1800689c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689cd  mov     rcx, [rdi+0D8h]
0x1800689d4  lea     r9, [rbp+57h+Block]
0x1800689d8  lea     r8, [rbp+57h+var_68]
0x1800689dc  lea     rdx, [rbp+57h+var_70]
0x1800689e0  call    QueueAsyncWorkItemBase_ATL__CComPtr_CallAudioRouting__long____cdecl_CallAudioRouting_____utl__basic_string_unsigned_short_utl__char_traits_unsigned_short__utl__allocator_unsigned_short____const____utl__basic_string_unsigned_short_utl__char_traits_unsigned_short__utl__allocator_unsigned_short____detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_
0x1800689e5  mov     rcx, [rbp+57h+var_70]
0x1800689e9  mov     ebx, eax
0x1800689eb  test    rcx, rcx
0x1800689ee  jz      short loc_1800689FC
0x1800689f0  mov     rdx, [rcx]
0x1800689f3  mov     rax, [rdx+10h]
0x1800689f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689fc  test    ebx, ebx
0x1800689fe  jns     short loc_180068A17
0x180068a00  mov     edx, ebx; int
0x180068a02  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068a07  mov     r9d, 1C6h
0x180068a0d  mov     edx, 1
0x180068a12  jmp     loc_180068970
0x180068a17  mov     rcx, [rbp+57h+Block]; Block
0x180068a1b  lea     rax, [rbp+57h+var_40]
0x180068a1f  cmp     rcx, rax
0x180068a22  jz      short loc_180068A30
0x180068a24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180068a2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068a30  mov     rcx, [rbp+57h+string]; string
0x180068a34  call    cs:__imp_WindowsDeleteString
0x180068a3a  mov     ebx, r15d
0x180068a3d  mov     [rbp+57h+string], r15
0x180068a41  lea     rcx, [rdi+58h]; lpCriticalSection
0x180068a45  call    cs:__imp_LeaveCriticalSection
0x180068a4b  mov     eax, ebx
0x180068a4d  mov     rcx, [rbp+57h+var_30]
0x180068a51  xor     rcx, rsp; StackCookie
0x180068a54  call    __security_check_cookie
0x180068a59  mov     rbx, [rsp+0D0h+arg_8]
0x180068a61  add     rsp, 0B0h
0x180068a68  pop     r15
0x180068a6a  pop     r14
0x180068a6c  pop     rdi
0x180068a6d  pop     rsi
0x180068a6e  pop     rbp
0x180068a6f  retn
```
