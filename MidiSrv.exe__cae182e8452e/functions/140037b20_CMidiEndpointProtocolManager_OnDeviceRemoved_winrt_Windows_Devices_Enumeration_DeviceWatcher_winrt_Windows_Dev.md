# CMidiEndpointProtocolManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x140037b20`
- end: `0x140037cda`
- name: `?OnDeviceRemoved@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400054c0`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000a6b4`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140013a38`
- `0x14001dccc`
- `0x140037b20`
- `0x140037dd0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140037c82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140037c82`

## string_xrefs

- `0x140037c42`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMidiEndpointProtocolManager::OnDeviceRemoved(__int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  volatile signed __int32 *v8; // rbx
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  int v12; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  LPVOID lpMem[4]; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v20; // [rsp+60h] [rbp-29h] BYREF
  __int128 v21; // [rsp+70h] [rbp-19h]
  char *v22[4]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpMem[2] = a2;
  lpMem[3] = a3;
  lpMem[0] = 0;
  v6 = *a3;
  LODWORD(v20) = 1080;
  *((_QWORD *)&v20 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  *(_QWORD *)&v21 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v6 + 48LL))(v6, lpMem);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v20);
  v8 = (volatile signed __int32 *)lpMem[0];
  if ( lpMem[0] )
  {
    v9 = (const wchar_t *)*((_QWORD *)lpMem[0] + 2);
  }
  else
  {
    v9 = &S2;
    v8 = 0;
  }
  v20 = 0;
  v21 = 0;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v20, v9, v10);
  v11 = std::wstring::wstring((__int64)v19, (__int64)&v20);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v22, v11);
  std::wstring::~wstring((char **)&v20);
  if ( v8 )
  {
    v12 = _InterlockedDecrement(v8 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
    }
  }
  v14 = std::wstring::wstring((__int64)v19, (__int64)v22);
  v15 = CMidiEndpointProtocolManager::RemoveWorkerIfPresent(a1, v14);
  v16 = v15;
  if ( v15 >= 0 )
  {
    std::wstring::~wstring(v22);
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    if ( *a3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
      (const char *)(unsigned int)v15,
      (int)lpMem[0]);
    std::wstring::~wstring(v22);
    if ( *a2 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    if ( *a3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
    return v16;
  }
}

```

## disassembly

```asm
0x140037b20  push    rbp
0x140037b22  push    rbx
0x140037b23  push    rsi
0x140037b24  push    rdi
0x140037b25  push    r12
0x140037b27  push    r14
0x140037b29  push    r15
0x140037b2b  lea     rbp, [rsp-27h]
0x140037b30  sub     rsp, 0B0h
0x140037b37  mov     rax, cs:__security_cookie
0x140037b3e  xor     rax, rsp
0x140037b41  mov     [rbp+57h+var_40], rax
0x140037b45  mov     rdi, r8
0x140037b48  mov     rsi, rdx
0x140037b4b  mov     r15, rcx
0x140037b4e  mov     [rbp+57h+var_B0], rdx
0x140037b52  mov     [rbp+57h+var_A8], r8
0x140037b56  xor     r12d, r12d
0x140037b59  mov     [rbp+57h+lpMem], r12
0x140037b5d  mov     rcx, [r8]
0x140037b60  mov     dword ptr [rbp+57h+var_80], 438h
0x140037b67  lea     rax, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140037b6e  mov     qword ptr [rbp+57h+var_80+8], rax
0x140037b72  mov     qword ptr [rbp+57h+var_70], r12
0x140037b76  mov     rax, [rcx]
0x140037b79  lea     rdx, [rbp+57h+lpMem]
0x140037b7d  mov     rax, [rax+30h]
0x140037b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b86  test    eax, eax
0x140037b88  js      loc_140037CCE
0x140037b8e  mov     rbx, [rbp+57h+lpMem]
0x140037b92  mov     [rbp+57h+lpMem], rbx
0x140037b96  test    rbx, rbx
0x140037b99  jz      short loc_140037BA1
0x140037b9b  mov     rdx, [rbx+10h]
0x140037b9f  jmp     short loc_140037BAB
0x140037ba1  lea     rdx, S2
0x140037ba8  mov     rbx, r12
0x140037bab  xorps   xmm0, xmm0
0x140037bae  movups  [rbp+57h+var_80], xmm0
0x140037bb2  xorps   xmm1, xmm1
0x140037bb5  movdqu  [rbp+57h+var_70], xmm1
0x140037bba  or      r14, 0FFFFFFFFFFFFFFFFh
0x140037bbe  mov     r8, r14
0x140037bc1  inc     r8
0x140037bc4  cmp     [rdx+r8*2], r12w
0x140037bc9  jnz     short loc_140037BC1
0x140037bcb  lea     rcx, [rbp+57h+var_80]
0x140037bcf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140037bd4  nop
0x140037bd5  lea     rdx, [rbp+57h+var_80]
0x140037bd9  lea     rcx, [rbp+57h+var_A0]
0x140037bdd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140037be2  mov     rdx, rax
0x140037be5  lea     rcx, [rbp+57h+var_60]
0x140037be9  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140037bee  nop
0x140037bef  lea     rcx, [rbp+57h+var_80]; void *
0x140037bf3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140037bf8  nop
0x140037bf9  test    rbx, rbx
0x140037bfc  jz      short loc_140037C1D
0x140037bfe  lock xadd [rbx+18h], r14d
0x140037c04  sub     r14d, 1
0x140037c08  jnz     short loc_140037C7D
0x140037c0a  nop
0x140037c0b  call    WINRT_IMPL_GetProcessHeap
0x140037c10  mov     rcx, rax; hHeap
0x140037c13  mov     r8, rbx; lpMem
0x140037c16  xor     edx, edx; dwFlags
0x140037c18  call    WINRT_IMPL_HeapFree
0x140037c1d  lea     rdx, [rbp+57h+var_60]
0x140037c21  lea     rcx, [rbp+57h+var_A0]
0x140037c25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140037c2a  mov     rdx, rax
0x140037c2d  mov     rcx, r15
0x140037c30  call    ?RemoveWorkerIfPresent@CMidiEndpointProtocolManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidiEndpointProtocolManager::RemoveWorkerIfPresent(std::wstring)
0x140037c35  mov     ebx, eax
0x140037c37  test    eax, eax
0x140037c39  jns     short loc_140037C89
0x140037c3b  mov     rcx, [rbp+5Fh]; this
0x140037c3f  mov     r9d, eax; char *
0x140037c42  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140037c49  mov     edx, 87h; void *
0x140037c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140037c53  nop
0x140037c54  lea     rcx, [rbp+57h+var_60]; void *
0x140037c58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140037c5d  nop
0x140037c5e  cmp     [rsi], r12
0x140037c61  jz      short loc_140037C6C
0x140037c63  mov     rcx, rsi
0x140037c66  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140037c6b  nop
0x140037c6c  cmp     [rdi], r12
0x140037c6f  jz      short loc_140037C79
0x140037c71  mov     rcx, rdi
0x140037c74  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140037c79  mov     eax, ebx
0x140037c7b  jmp     short loc_140037CB0
0x140037c7d  test    r14d, r14d
0x140037c80  jns     short loc_140037C1D
0x140037c82  call    cs:__imp_abort
0x140037c89  lea     rcx, [rbp+57h+var_60]; void *
0x140037c8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140037c92  nop
0x140037c93  cmp     [rsi], r12
0x140037c96  jz      short loc_140037CA1
0x140037c98  mov     rcx, rsi
0x140037c9b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140037ca0  nop
0x140037ca1  cmp     [rdi], r12
0x140037ca4  jz      short loc_140037CAE
0x140037ca6  mov     rcx, rdi
0x140037ca9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140037cae  xor     eax, eax
0x140037cb0  mov     rcx, [rbp+57h+var_40]
0x140037cb4  xor     rcx, rsp; StackCookie
0x140037cb7  call    __security_check_cookie
0x140037cbc  add     rsp, 0B0h
0x140037cc3  pop     r15
0x140037cc5  pop     r14
0x140037cc7  pop     r12
0x140037cc9  pop     rdi
0x140037cca  pop     rsi
0x140037ccb  pop     rbx
0x140037ccc  pop     rbp
0x140037ccd  retn
0x140037cce  lea     rdx, [rbp+57h+var_80]
0x140037cd2  mov     ecx, eax
0x140037cd4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
