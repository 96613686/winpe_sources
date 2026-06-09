# WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(uchar,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x18002cab8`
- end: `0x18002ccd8`
- name: `?PopulateEntryForNativeUmpDevice@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJEW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111E@Z`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002c91c`

## callees

- `0x180004180`
- `0x180004ff4`
- `0x18000500c`
- `0x18000b740`
- `0x18000f0a4`
- `0x18002a608`
- `0x18002aea0`
- `0x18002af1c`
- `0x18002c41c`
- `0x18002c688`
- `0x18002cab8`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForNativeUmpDevice(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        wchar_t *a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v11; // rax
  const void **v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // r14
  const void *v16; // rdx
  __int64 v17; // rax
  const void **v18; // rbx
  __int64 v19; // r14
  const void *v20; // rdx
  __int64 v21; // rax
  const void **v22; // rbx
  const void *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  volatile signed __int32 *v26; // rbx
  char v28[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v29; // [rsp+38h] [rbp-71h] BYREF
  volatile signed __int32 *v30; // [rsp+40h] [rbp-69h]
  _BYTE v31[32]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD Src[2]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v33[32]; // [rsp+88h] [rbp-21h] BYREF

  v28[0] = a2;
  std::make_shared<WindowsMidiServicesNamingLib::Midi1PortNameEntry,>(&v29);
  WindowsMidiServicesNamingLib::GenerateFilterPlusBlockMidi1PortName((__int64)v33, a5, a6, a7, v28[0]);
  WindowsMidiServicesNamingLib::GenerateLegacyMidi1PortName(Src, (__int64)a5, a6, a3, a8);
  v11 = std::wstring::wstring(v31, a4);
  v12 = (const void **)v11;
  v13 = v29;
  v14 = 31;
  v15 = 31;
  if ( *(_QWORD *)(v11 + 16) < 0x1Fu )
    v15 = *(_QWORD *)(v11 + 16);
  memset_0((void *)(v29 + 8), 0, 0x40u);
  if ( (unsigned __int64)v12[3] <= 7 )
    v16 = v12;
  else
    v16 = *v12;
  memcpy_0((void *)(v13 + 8), v16, 2 * v15);
  std::wstring::~wstring(v12);
  v17 = std::wstring::wstring(v31, Src);
  v18 = (const void **)v17;
  v19 = 31;
  if ( *(_QWORD *)(v17 + 16) < 0x1Fu )
    v19 = *(_QWORD *)(v17 + 16);
  memset_0((void *)(v13 + 72), 0, 0x40u);
  if ( (unsigned __int64)v18[3] <= 7 )
    v20 = v18;
  else
    v20 = *v18;
  memcpy_0((void *)(v13 + 72), v20, 2 * v19);
  std::wstring::~wstring(v18);
  v21 = std::wstring::wstring(v31, v33);
  v22 = (const void **)v21;
  if ( *(_QWORD *)(v21 + 16) < 0x1Fu )
    v14 = *(_QWORD *)(v21 + 16);
  memset_0((void *)(v13 + 136), 0, 0x40u);
  if ( (unsigned __int64)v22[3] <= 7 )
    v23 = v22;
  else
    v23 = *v22;
  memcpy_0((void *)(v13 + 136), v23, 2 * v14);
  std::wstring::~wstring(v22);
  *(_BYTE *)v13 = v28[0];
  *(_DWORD *)(v13 + 4) = a3;
  if ( !a3 )
  {
    v24 = a1;
LABEL_20:
    v25 = std::map<unsigned char,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator[](
            v24,
            v28);
    std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::operator=(v25, &v29);
    goto LABEL_21;
  }
  if ( a3 == 1 )
  {
    v24 = a1 + 16;
    goto LABEL_20;
  }
LABEL_21:
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v33);
  v26 = v30;
  if ( v30 )
  {
    if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002cab8  mov     [rsp-8+arg_10], rbx
0x18002cabd  push    rbp
0x18002cabe  push    rsi
0x18002cabf  push    rdi
0x18002cac0  push    r12
0x18002cac2  push    r13
0x18002cac4  push    r14
0x18002cac6  push    r15
0x18002cac8  lea     rbp, [rsp-7]
0x18002cacd  sub     rsp, 0B0h
0x18002cad4  mov     rax, cs:__security_cookie
0x18002cadb  xor     rax, rsp
0x18002cade  mov     [rbp+37h+var_38], rax
0x18002cae2  mov     r14, r9
0x18002cae5  mov     r15d, r8d
0x18002cae8  mov     r13, rcx
0x18002caeb  mov     [rbp+37h+var_B0], dl
0x18002caee  mov     rsi, [rbp+37h+arg_20]
0x18002caf2  mov     rdi, [rbp+37h+arg_28]
0x18002caf6  mov     rbx, [rbp+37h+arg_30]
0x18002cafa  lea     rcx, [rbp+37h+var_A8]
0x18002cafe  call    ??$make_shared@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@$$V@std@@YA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@0@XZ; std::make_shared<WindowsMidiServicesNamingLib::Midi1PortNameEntry,>(void)
0x18002cb03  mov     al, [rbp+37h+var_B0]
0x18002cb06  mov     [rsp+0E0h+var_C0], al
0x18002cb0a  mov     r9, rbx
0x18002cb0d  mov     r8, rdi
0x18002cb10  mov     rdx, rsi
0x18002cb13  lea     rcx, [rbp+37h+var_58]
0x18002cb17  call    ?GenerateFilterPlusBlockMidi1PortName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z; WindowsMidiServicesNamingLib::GenerateFilterPlusBlockMidi1PortName(std::wstring const &,std::wstring const &,std::wstring const &,uchar)
0x18002cb1c  mov     al, [rbp+37h+arg_38]
0x18002cb1f  mov     [rsp+0E0h+var_C0], al; char
0x18002cb23  mov     r9d, r15d
0x18002cb26  mov     r8, rdi
0x18002cb29  mov     rdx, rsi
0x18002cb2c  lea     rcx, [rbp+37h+Src]; Src
0x18002cb30  call    ?GenerateLegacyMidi1PortName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@E@Z; WindowsMidiServicesNamingLib::GenerateLegacyMidi1PortName(std::wstring const &,std::wstring const &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,uchar)
0x18002cb35  mov     rdx, r14
0x18002cb38  lea     rcx, [rbp+37h+var_98]
0x18002cb3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cb41  mov     rbx, rax
0x18002cb44  mov     rsi, [rbp+37h+var_A8]
0x18002cb48  mov     edi, 1Fh
0x18002cb4d  mov     r14d, edi
0x18002cb50  cmp     [rax+10h], rdi
0x18002cb54  cmovb   r14, [rax+10h]
0x18002cb59  xor     edx, edx; Val
0x18002cb5b  lea     r8d, [rdi+21h]; Size
0x18002cb5f  lea     rcx, [rsi+8]; void *
0x18002cb63  call    memset_0
0x18002cb68  cmp     qword ptr [rbx+18h], 7
0x18002cb6d  jbe     short loc_18002CB74
0x18002cb6f  mov     rdx, [rbx]
0x18002cb72  jmp     short loc_18002CB77
0x18002cb74  mov     rdx, rbx; Src
0x18002cb77  lea     r8, [r14+r14]; Size
0x18002cb7b  lea     rcx, [rsi+8]; void *
0x18002cb7f  call    memcpy_0
0x18002cb84  mov     rcx, rbx; void *
0x18002cb87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cb8c  lea     rdx, [rbp+37h+Src]
0x18002cb90  lea     rcx, [rbp+37h+var_98]
0x18002cb94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cb99  mov     rbx, rax
0x18002cb9c  mov     r14, rdi
0x18002cb9f  cmp     [rax+10h], rdi
0x18002cba3  cmovb   r14, [rax+10h]
0x18002cba8  xor     edx, edx; Val
0x18002cbaa  lea     r8d, [rdx+40h]; Size
0x18002cbae  lea     rcx, [rsi+48h]; void *
0x18002cbb2  call    memset_0
0x18002cbb7  cmp     qword ptr [rbx+18h], 7
0x18002cbbc  jbe     short loc_18002CBC3
0x18002cbbe  mov     rdx, [rbx]
0x18002cbc1  jmp     short loc_18002CBC6
0x18002cbc3  mov     rdx, rbx; Src
0x18002cbc6  lea     r8, [r14+r14]; Size
0x18002cbca  lea     rcx, [rsi+48h]; void *
0x18002cbce  call    memcpy_0
0x18002cbd3  mov     rcx, rbx; void *
0x18002cbd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cbdb  lea     rdx, [rbp+37h+var_58]
0x18002cbdf  lea     rcx, [rbp+37h+var_98]
0x18002cbe3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cbe8  mov     rbx, rax
0x18002cbeb  lea     r14, [rsi+88h]
0x18002cbf2  cmp     [rax+10h], rdi
0x18002cbf6  cmovb   rdi, [rax+10h]
0x18002cbfb  xor     edx, edx; Val
0x18002cbfd  lea     r8d, [rdx+40h]; Size
0x18002cc01  mov     rcx, r14; void *
0x18002cc04  call    memset_0
0x18002cc09  cmp     qword ptr [rbx+18h], 7
0x18002cc0e  jbe     short loc_18002CC15
0x18002cc10  mov     rdx, [rbx]
0x18002cc13  jmp     short loc_18002CC18
0x18002cc15  mov     rdx, rbx; Src
0x18002cc18  lea     r8, [rdi+rdi]; Size
0x18002cc1c  mov     rcx, r14; void *
0x18002cc1f  call    memcpy_0
0x18002cc24  mov     rcx, rbx; void *
0x18002cc27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cc2c  mov     al, [rbp+37h+var_B0]
0x18002cc2f  mov     [rsi], al
0x18002cc31  mov     [rsi+4], r15d
0x18002cc35  test    r15d, r15d
0x18002cc38  jnz     short loc_18002CC3F
0x18002cc3a  mov     rcx, r13
0x18002cc3d  jmp     short loc_18002CC49
0x18002cc3f  cmp     r15d, 1
0x18002cc43  jnz     short loc_18002CC5E
0x18002cc45  lea     rcx, [r13+10h]
0x18002cc49  lea     rdx, [rbp+37h+var_B0]
0x18002cc4d  call    ??A?$map@EV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@1@AEBE@Z; std::map<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator[](uchar const &)
0x18002cc52  lea     rdx, [rbp+37h+var_A8]
0x18002cc56  mov     rcx, rax
0x18002cc59  call    ??4?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::operator=(std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry> const &)
0x18002cc5e  lea     rcx, [rbp+37h+Src]; void *
0x18002cc62  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cc67  lea     rcx, [rbp+37h+var_58]; void *
0x18002cc6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cc70  mov     rbx, [rbp+37h+var_A0]
0x18002cc74  test    rbx, rbx
0x18002cc77  jz      short loc_18002CCAF
0x18002cc79  or      edi, 0FFFFFFFFh
0x18002cc7c  mov     eax, edi
0x18002cc7e  lock xadd [rbx+8], eax
0x18002cc83  add     eax, edi
0x18002cc85  jnz     short loc_18002CCAF
0x18002cc87  mov     rax, [rbx]
0x18002cc8a  mov     rcx, rbx
0x18002cc8d  mov     rax, [rax]
0x18002cc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc95  mov     eax, edi
0x18002cc97  lock xadd [rbx+0Ch], eax
0x18002cc9c  add     eax, edi
0x18002cc9e  jnz     short loc_18002CCAF
0x18002cca0  mov     rax, [rbx]
0x18002cca3  mov     rcx, rbx
0x18002cca6  mov     rax, [rax+8]
0x18002ccaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccaf  xor     eax, eax
0x18002ccb1  mov     rcx, [rbp+37h+var_38]
0x18002ccb5  xor     rcx, rsp; StackCookie
0x18002ccb8  call    __security_check_cookie
0x18002ccbd  mov     rbx, [rsp+0E0h+arg_10]
0x18002ccc5  add     rsp, 0B0h
0x18002cccc  pop     r15
0x18002ccce  pop     r14
0x18002ccd0  pop     r13
0x18002ccd2  pop     r12
0x18002ccd4  pop     rdi
0x18002ccd5  pop     rsi
0x18002ccd6  pop     rbp
0x18002ccd7  retn
```
