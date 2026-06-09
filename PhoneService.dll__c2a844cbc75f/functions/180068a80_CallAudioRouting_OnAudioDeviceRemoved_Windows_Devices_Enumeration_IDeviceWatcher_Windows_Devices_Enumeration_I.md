# CallAudioRouting::_OnAudioDeviceRemoved(Windows::Devices::Enumeration::IDeviceWatcher *,Windows::Devices::Enumeration::IDeviceInformationUpdate *)

- ea: `0x180068a80`
- end: `0x180068cb0`
- name: `?_OnAudioDeviceRemoved@CallAudioRouting@@AEAAJPEAUIDeviceWatcher@Enumeration@Devices@Windows@@PEAUIDeviceInformationUpdate@345@@Z`
- size: `560`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this, struct Windows::Devices::Enumeration::IDeviceWatcher *, struct Windows::Devices::Enumeration::IDeviceInformationUpdate *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x180059298`
- `0x18005f9c0`
- `0x180063a78`
- `0x180068a80`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068ab0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068c85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068b6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068b6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068c74`

## string_xrefs

- `0x180068ad4`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068b24`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180068bb0`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_OnAudioDeviceRemoved(
        CallAudioRouting *this,
        struct Windows::Devices::Enumeration::IDeviceWatcher *a2,
        struct Windows::Devices::Enumeration::IDeviceInformationUpdate *a3)
{
  int v5; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::Devices::Enumeration::IDeviceInformationUpdate *, HSTRING *); // rbx
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
    v9 = *(__int64 (__fastcall **)(struct Windows::Devices::Enumeration::IDeviceInformationUpdate *, HSTRING *))(v8 + 48);
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
        v21 = CallAudioRouting::_HandleAudioDeviceRemoved;
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
        v15 = 472;
        v16 = 1;
      }
      else
      {
        v7 = -2147024882;
        BackTraceCollection::Capture(v14, -2147024882);
        v15 = 469;
        v16 = 0;
      }
      Log_HREvent_17(v7, v16, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v15);
      if ( Block[0] != &v25 )
        operator delete(Block[0]);
    }
    else
    {
      BackTraceCollection::Capture(v11, v10);
      Log_HREvent_17(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 466);
    }
    WindowsDeleteString(string);
LABEL_22:
    string = 0;
    goto LABEL_23;
  }
  BackTraceCollection::Capture(v6, v5);
  Log_HREvent_17(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 463);
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return v7;
}

```

## disassembly

```asm
0x180068a80  mov     [rsp-8+arg_8], rbx
0x180068a85  push    rbp
0x180068a86  push    rsi
0x180068a87  push    rdi
0x180068a88  push    r14
0x180068a8a  push    r15
0x180068a8c  lea     rbp, [rsp-37h]
0x180068a91  sub     rsp, 0B0h
0x180068a98  mov     rax, cs:__security_cookie
0x180068a9f  xor     rax, rsp
0x180068aa2  mov     [rbp+57h+var_30], rax
0x180068aa6  mov     rdi, rcx
0x180068aa9  mov     rsi, r8
0x180068aac  add     rcx, 58h ; 'X'; lpCriticalSection
0x180068ab0  call    cs:__imp_EnterCriticalSection
0x180068ab6  mov     rcx, rdi; this
0x180068ab9  call    ?_CheckShutdown@CallAudioRouting@@AEAAJXZ; CallAudioRouting::_CheckShutdown(void)
0x180068abe  xor     r15d, r15d
0x180068ac1  mov     ebx, eax
0x180068ac3  test    eax, eax
0x180068ac5  jns     short loc_180068AEB
0x180068ac7  mov     edx, eax; int
0x180068ac9  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068ace  mov     r9d, 1CFh
0x180068ad4  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068adb  lea     edx, [r15+1]
0x180068adf  mov     ecx, ebx
0x180068ae1  call    Log_HREvent_17
0x180068ae6  jmp     loc_180068C81
0x180068aeb  mov     rax, [rsi]
0x180068aee  xor     ecx, ecx; string
0x180068af0  mov     [rbp+57h+string], r15
0x180068af4  mov     rbx, [rax+30h]
0x180068af8  call    cs:__imp_WindowsDeleteString
0x180068afe  lea     rdx, [rbp+57h+string]
0x180068b02  mov     [rbp+57h+string], r15
0x180068b06  mov     rcx, rsi
0x180068b09  mov     rax, rbx
0x180068b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b11  mov     ebx, eax
0x180068b13  test    eax, eax
0x180068b15  jns     short loc_180068B46
0x180068b17  mov     edx, eax; int
0x180068b19  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068b1e  mov     r9d, 1D2h
0x180068b24  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068b2b  mov     edx, 1
0x180068b30  mov     ecx, ebx
0x180068b32  call    Log_HREvent_17
0x180068b37  mov     rcx, [rbp+57h+string]; string
0x180068b3b  call    cs:__imp_WindowsDeleteString
0x180068b41  jmp     loc_180068C7D
0x180068b46  mov     rcx, [rbp+57h+string]; string
0x180068b4a  lea     rax, [rbp+57h+var_40]
0x180068b4e  mov     [rbp+57h+Block], rax
0x180068b52  xor     edx, edx; length
0x180068b54  lea     rax, [rbp+57h+var_40]
0x180068b58  mov     [rbp+57h+var_3E], r15
0x180068b5c  mov     [rbp+57h+var_48], rax
0x180068b60  mov     [rbp+57h+var_36], r15d
0x180068b64  mov     [rbp+57h+var_32], r15w
0x180068b69  mov     [rbp+57h+var_40], r15w
0x180068b6e  call    cs:__imp_WindowsGetStringRawBuffer
0x180068b74  test    rax, rax
0x180068b77  jz      short loc_180068B89
0x180068b79  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068b7d  inc     r8
0x180068b80  cmp     [rax+r8*2], r15w
0x180068b85  jnz     short loc_180068B7D
0x180068b87  jmp     short loc_180068B8C
0x180068b89  mov     r8, r15
0x180068b8c  mov     rdx, rax
0x180068b8f  lea     rcx, [rbp+57h+Block]
0x180068b93  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180068b98  test    al, al
0x180068b9a  jnz     short loc_180068BE0
0x180068b9c  mov     ebx, 8007000Eh
0x180068ba1  mov     edx, ebx; int
0x180068ba3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068ba8  mov     r9d, 1D5h
0x180068bae  xor     edx, edx
0x180068bb0  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180068bb7  mov     ecx, ebx
0x180068bb9  call    Log_HREvent_17
0x180068bbe  mov     rcx, [rbp+57h+Block]; Block
0x180068bc2  lea     rax, [rbp+57h+var_40]
0x180068bc6  cmp     rcx, rax
0x180068bc9  jz      loc_180068B37
0x180068bcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180068bd6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068bdb  jmp     loc_180068B37
0x180068be0  mov     [rbp+57h+var_60], r15d
0x180068be4  lea     rax, ?_HandleAudioDeviceRemoved@CallAudioRouting@@IEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CallAudioRouting::_HandleAudioDeviceRemoved(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180068beb  mov     [rbp+57h+var_68], rax
0x180068bef  mov     eax, [rbp+57h+var_5C]
0x180068bf2  mov     [rbp+57h+var_5C], eax
0x180068bf5  mov     [rbp+57h+var_70], rdi
0x180068bf9  test    rdi, rdi
0x180068bfc  jz      short loc_180068C0D
0x180068bfe  mov     rax, [rdi]
0x180068c01  mov     rcx, rdi
0x180068c04  mov     rax, [rax+8]
0x180068c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c0d  mov     rcx, [rdi+0D8h]
0x180068c14  lea     r9, [rbp+57h+Block]
0x180068c18  lea     r8, [rbp+57h+var_68]
0x180068c1c  lea     rdx, [rbp+57h+var_70]
0x180068c20  call    QueueAsyncWorkItemBase_ATL__CComPtr_CallAudioRouting__long____cdecl_CallAudioRouting_____utl__basic_string_unsigned_short_utl__char_traits_unsigned_short__utl__allocator_unsigned_short____const____utl__basic_string_unsigned_short_utl__char_traits_unsigned_short__utl__allocator_unsigned_short____detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_detail__Empty_
0x180068c25  mov     rcx, [rbp+57h+var_70]
0x180068c29  mov     ebx, eax
0x180068c2b  test    rcx, rcx
0x180068c2e  jz      short loc_180068C3C
0x180068c30  mov     rdx, [rcx]
0x180068c33  mov     rax, [rdx+10h]
0x180068c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c3c  test    ebx, ebx
0x180068c3e  jns     short loc_180068C57
0x180068c40  mov     edx, ebx; int
0x180068c42  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180068c47  mov     r9d, 1D8h
0x180068c4d  mov     edx, 1
0x180068c52  jmp     loc_180068BB0
0x180068c57  mov     rcx, [rbp+57h+Block]; Block
0x180068c5b  lea     rax, [rbp+57h+var_40]
0x180068c5f  cmp     rcx, rax
0x180068c62  jz      short loc_180068C70
0x180068c64  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180068c6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068c70  mov     rcx, [rbp+57h+string]; string
0x180068c74  call    cs:__imp_WindowsDeleteString
0x180068c7a  mov     ebx, r15d
0x180068c7d  mov     [rbp+57h+string], r15
0x180068c81  lea     rcx, [rdi+58h]; lpCriticalSection
0x180068c85  call    cs:__imp_LeaveCriticalSection
0x180068c8b  mov     eax, ebx
0x180068c8d  mov     rcx, [rbp+57h+var_30]
0x180068c91  xor     rcx, rsp; StackCookie
0x180068c94  call    __security_check_cookie
0x180068c99  mov     rbx, [rsp+0D0h+arg_8]
0x180068ca1  add     rsp, 0B0h
0x180068ca8  pop     r15
0x180068caa  pop     r14
0x180068cac  pop     rdi
0x180068cad  pop     rsi
0x180068cae  pop     rbp
0x180068caf  retn
```
