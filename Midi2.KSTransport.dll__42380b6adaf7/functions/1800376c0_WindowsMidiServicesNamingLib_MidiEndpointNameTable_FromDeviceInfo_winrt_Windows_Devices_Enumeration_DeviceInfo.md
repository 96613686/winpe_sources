# WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromDeviceInfo(winrt::Windows::Devices::Enumeration::DeviceInformation const &)

- ea: `0x1800376c0`
- end: `0x1800378b2`
- name: `?FromDeviceInfo@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBUDeviceInformation@Enumeration@Devices@Windows@winrt@@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800378b8`

## callees

- `0x180004460`
- `0x1800051e6`
- `0x180005314`
- `0x18000d1c0`
- `0x1800112b0`
- `0x180014fc4`
- `0x180015348`
- `0x180017d7c`
- `0x1800376c0`
- `0x180037af0`
- `0x1800395b4`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037769`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037769`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromDeviceInfo(_QWORD *a1, __int64 *a2)
{
  const char *v4; // rdx
  __int64 v5; // rcx
  struct winrt::impl::shared_hstring_header *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  struct winrt::impl::shared_hstring_header *v10; // rbx
  _OWORD *v11; // rcx
  __int64 v12; // rdi
  signed int v13; // eax
  __int64 v14; // r8
  void *v15; // rbx
  __int64 *v16; // rdi
  __int64 v18; // [rsp+28h] [rbp-38h] BYREF
  struct winrt::impl::shared_hstring_header *v19; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  int v21; // [rsp+40h] [rbp-20h]
  unsigned int v22; // [rsp+48h] [rbp-18h] BYREF
  const char *v23; // [rsp+50h] [rbp-10h]
  __int64 v24; // [rsp+58h] [rbp-8h]
  __int64 *v25; // [rsp+90h] [rbp+30h] BYREF
  __int64 v26; // [rsp+98h] [rbp+38h] BYREF

  v25 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a2, &v25) )
  {
LABEL_15:
    v16 = (__int64 *)operator new(0x48u);
    v25 = v16;
    *(_OWORD *)v16 = 0;
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = 1;
    *v16 = (__int64)&std::_Ref_count_obj2<WindowsMidiServicesNamingLib::MidiEndpointNameTable>::`vftable';
    *((_OWORD *)v16 + 1) = 0;
    *((_OWORD *)v16 + 2) = 0;
    *((_OWORD *)v16 + 3) = 0;
    v16[8] = 0;
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)(v16 + 2));
    *a1 = v16 + 2;
    a1[1] = v16;
    return a1;
  }
  v25 = &v18;
  v5 = *a2;
  v18 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, v4);
  v10 = v6;
  v11 = (_OWORD *)((char *)v6 + 28);
  if ( v6 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno(v11, v7, v8, v9) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *v11 = *(_OWORD *)L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v6 + 44) = *(_OWORD *)L"A-11FA-4BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v6 + 60) = *(_OWORD *)L"BD0-9D2C-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v6 + 76) = *(_OWORD *)L"-6B7780CD80AD} 960";
    *(_OWORD *)((char *)v6 + 92) = *(_OWORD *)L"D80AD} 960";
    *((_DWORD *)v6 + 27) = *(_DWORD *)L"60";
  }
  v19 = v10;
  WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(&v26, &v19, &v18);
  v25 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v26, &v25) )
  {
    if ( v26 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
    goto LABEL_15;
  }
  LODWORD(v25) = 0;
  pv = 0;
  v12 = v26;
  v22 = 1966;
  v23 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.foundation.h";
  v24 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 **, LPVOID *))(*(_QWORD *)v26 + 48LL))(v26, &v25, &pv);
  if ( v13 < 0 )
    winrt::throw_hresult(v13, &v22, v14);
  v15 = pv;
  v21 = (int)v25;
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromPropertyData(a1, &pv);
  if ( v15 )
    CoTaskMemFree_0(v15);
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  return a1;
}

```

## disassembly

```asm
0x1800376c0  mov     [rsp-18h+arg_0], rbx
0x1800376c5  push    rbp
0x1800376c6  push    rsi
0x1800376c7  push    rdi
0x1800376c8  mov     rbp, rsp
0x1800376cb  sub     rsp, 60h
0x1800376cf  mov     rbx, rdx
0x1800376d2  mov     rsi, rcx
0x1800376d5  mov     [rbp+arg_10], 0
0x1800376dd  lea     rdx, [rbp+arg_10]
0x1800376e1  mov     rcx, rbx
0x1800376e4  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800376e9  test    al, al
0x1800376eb  jnz     loc_180037842
0x1800376f1  lea     rax, [rbp+var_38]
0x1800376f5  mov     [rbp+arg_10], rax
0x1800376f9  mov     rcx, [rbx]
0x1800376fc  mov     [rbp+var_38], rcx
0x180037700  test    rcx, rcx
0x180037703  jz      short loc_180037712
0x180037705  mov     rax, [rcx]
0x180037708  mov     rax, [rax+8]
0x18003770c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037711  nop
0x180037712  mov     ecx, 2Ah ; '*'; this
0x180037717  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18003771c  mov     rbx, rax
0x18003771f  lea     rcx, [rax+1Ch]
0x180037723  test    rcx, rcx
0x180037726  jz      short loc_180037769
0x180037728  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18003772f  movups  xmmword ptr [rcx], xmm0
0x180037732  movaps  xmm1, xmmword ptr cs:a3f114a6a11fa4b+10h; "A-11FA-4BD0-9D2C-6B7780CD80AD} 960"
0x180037739  movups  xmmword ptr [rcx+10h], xmm1
0x18003773d  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b+20h; "BD0-9D2C-6B7780CD80AD} 960"
0x180037744  movups  xmmword ptr [rcx+20h], xmm0
0x180037748  movaps  xmm1, xmmword ptr cs:a3f114a6a11fa4b+30h; "-6B7780CD80AD} 960"
0x18003774f  movups  xmmword ptr [rcx+30h], xmm1
0x180037753  movaps  xmm0, xmmword ptr cs:a3f114a6a11fa4b+40h; "D80AD} 960"
0x18003775a  movups  xmmword ptr [rcx+40h], xmm0
0x18003775e  mov     eax, dword ptr cs:a3f114a6a11fa4b+50h; "60"
0x180037764  mov     [rcx+50h], eax
0x180037767  jmp     short loc_18003777A
0x180037769  call    cs:__imp__o__errno
0x18003776f  mov     dword ptr [rax], 16h
0x180037775  call    _invalid_parameter_noinfo
0x18003777a  mov     [rbp+var_30], rbx
0x18003777e  lea     r8, [rbp+var_38]
0x180037782  lea     rdx, [rbp+var_30]
0x180037786  lea     rcx, [rbp+arg_18]
0x18003778a  call    ?SafeGetSwdBinaryPropertyFromDeviceInformation@WindowsMidiServicesInternal@@YA?AU?$IReferenceArray@E@Foundation@Windows@winrt@@Uhstring@5@UDeviceInformation@Enumeration@Devices@45@@Z; WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x18003778f  nop
0x180037790  mov     [rbp+arg_10], 0
0x180037798  lea     rdx, [rbp+arg_10]
0x18003779c  lea     rcx, [rbp+arg_18]
0x1800377a0  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800377a5  test    al, al
0x1800377a7  jnz     loc_180037832
0x1800377ad  mov     dword ptr [rbp+arg_10], 0
0x1800377b4  mov     [rbp+pv], 0
0x1800377bc  mov     rdi, [rbp+arg_18]
0x1800377c0  mov     [rbp+var_18], 7AEh
0x1800377c7  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800377ce  mov     [rbp+var_10], rax
0x1800377d2  mov     [rbp+var_8], 0
0x1800377da  mov     rax, [rdi]
0x1800377dd  lea     r8, [rbp+pv]
0x1800377e1  lea     rdx, [rbp+arg_10]
0x1800377e5  mov     rcx, rdi
0x1800377e8  mov     rax, [rax+30h]
0x1800377ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377f1  test    eax, eax
0x1800377f3  js      loc_1800378A6
0x1800377f9  mov     rbx, [rbp+pv]
0x1800377fd  mov     [rbp+pv], rbx
0x180037801  mov     eax, dword ptr [rbp+arg_10]
0x180037804  mov     [rbp+var_20], eax
0x180037807  lea     rdx, [rbp+pv]
0x18003780b  mov     rcx, rsi
0x18003780e  call    ?FromPropertyData@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBU?$com_array@E@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromPropertyData(winrt::com_array<uchar> const &)
0x180037813  nop
0x180037814  test    rbx, rbx
0x180037817  jz      short loc_180037822
0x180037819  mov     rcx, rbx; pv
0x18003781c  call    CoTaskMemFree_0
0x180037821  nop
0x180037822  test    rdi, rdi
0x180037825  jz      short loc_180037893
0x180037827  lea     rcx, [rbp+arg_18]
0x18003782b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180037830  jmp     short loc_180037893
0x180037832  cmp     [rbp+arg_18], 0
0x180037837  jz      short loc_180037842
0x180037839  lea     rcx, [rbp+arg_18]
0x18003783d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180037842  mov     ecx, 48h ; 'H'; Size
0x180037847  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003784c  mov     rdi, rax
0x18003784f  mov     [rbp+arg_10], rax
0x180037853  xorps   xmm0, xmm0
0x180037856  movups  xmmword ptr [rax], xmm0
0x180037859  mov     eax, 1
0x18003785e  mov     [rdi+8], eax
0x180037861  mov     [rdi+0Ch], eax
0x180037864  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesNamingLib::MidiEndpointNameTable>::`vftable'
0x18003786b  mov     [rdi], rax
0x18003786e  lea     rbx, [rdi+10h]
0x180037872  xor     eax, eax
0x180037874  movups  xmmword ptr [rbx], xmm0
0x180037877  movups  xmmword ptr [rbx+10h], xmm0
0x18003787b  movups  xmmword ptr [rbx+20h], xmm0
0x18003787f  mov     [rbx+30h], rax
0x180037883  mov     rcx, rbx; this
0x180037886  call    ??0MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ; WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(void)
0x18003788b  nop
0x18003788c  mov     [rsi], rbx
0x18003788f  mov     [rsi+8], rdi
0x180037893  mov     rax, rsi
0x180037896  mov     rbx, [rsp+60h+arg_0]
0x18003789e  add     rsp, 60h
0x1800378a2  pop     rdi
0x1800378a3  pop     rsi
0x1800378a4  pop     rbp
0x1800378a5  retn
0x1800378a6  lea     rdx, [rbp+var_18]
0x1800378aa  mov     ecx, eax
0x1800378ac  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
