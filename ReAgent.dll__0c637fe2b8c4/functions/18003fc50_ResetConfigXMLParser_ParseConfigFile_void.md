# ResetConfigXMLParser::ParseConfigFile(void)

- ea: `0x18003fc50`
- end: `0x18003ff20`
- name: `?ParseConfigFile@ResetConfigXMLParser@@QEAAKXZ`
- size: `720`
- prototype: `unsigned int __fastcall(ResetConfigXMLParser *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b988`

## callees

- `0x1800059fc`
- `0x180008600`
- `0x180016f58`
- `0x18003ece4`
- `0x18003ed88`
- `0x18003fc50`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003fd2b`
- `ntdll!RtlNtStatusToDosError` at `0x18003feb9`
- `ntdll!RtlNtStatusToDosError` at `0x18003fd2b`
- `ntdll!RtlNtStatusToDosError` at `0x18003feb9`
- `ServicingCommon!RtlCreateMicrodom` at `0x18003fd0c`
- `ServicingCommon!RtlCreateMicrodom` at `0x18003fd0c`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fecc`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fecc`

## string_xrefs

- `0x18003fd1b`: `RtlCreateMicrodom failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ResetConfigXMLParser::ParseConfigFile(ResetConfigXMLParser *this)
{
  int v2; // eax
  NTSTATUS v3; // edi
  int v4; // eax
  int v5; // eax
  const wchar_t *v6; // rdx
  ULONG v7; // ebx
  int v8; // eax
  int InnerText; // eax
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h]
  _QWORD v13[3]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v14[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+78h] [rbp-88h]
  __int128 v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v20; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-50h]
  __int128 *v22; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+C0h] [rbp-40h]
  __int128 *v24; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-30h]
  __int128 v26; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __int128 v28; // [rsp+F0h] [rbp-10h] BYREF

  v12 = -2;
  v19 = 0;
  v16 = 0;
  v18 = 0;
  v28 = 0;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v26 = 0;
  v27 = 0;
  v13[0] = *(unsigned int *)this;
  v13[1] = v13[0];
  v13[2] = *((_QWORD *)this + 1);
  v14[0] = 1;
  v14[1] = 1;
  v17 = 0;
  v15 = v13;
  v2 = RtlCreateMicrodom(v14, &v19);
  v3 = v2;
  if ( v2 < 0 )
  {
    UnattendLogW(1, L"RtlCreateMicrodom failed: 0x%x", (unsigned int)v2);
    RtlNtStatusToDosError(v3);
LABEL_25:
    v7 = RtlNtStatusToDosError(v3);
    goto LABEL_26;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 24LL))(v19, &v28);
  v3 = v4;
  if ( v4 < 0 )
  {
    UnattendLogW(1, L"GetDocument failed: 0x%x", (unsigned int)v4);
    goto LABEL_25;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 **))(*(_QWORD *)v19 + 224LL))(v19, qword_180061658, &v24);
  v3 = v5;
  if ( v5 < 0 )
  {
LABEL_7:
    UnattendLogW(1, L"GetElementsByTagName failed: 0x%x", (unsigned int)v5);
    goto LABEL_25;
  }
  if ( v25 != 1 )
  {
    v6 = L"Exactly 1 Reset tag required.";
LABEL_10:
    v7 = 13;
    UnattendLogW(1, v6);
    goto LABEL_26;
  }
  v11 = *v24;
  v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, __int128 **))(*(_QWORD *)v19 + 216LL))(
         v19,
         &v11,
         qword_180061640,
         &v22);
  v3 = v5;
  if ( v5 < 0 )
    goto LABEL_7;
  if ( !v23 )
  {
    v6 = L"No SystemDisk tags found.";
    goto LABEL_10;
  }
  if ( v23 != 1 )
  {
    v6 = L"Exactly 1 SystemDisk tag required.";
    goto LABEL_10;
  }
  v11 = *v22;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, __int128 **))(*(_QWORD *)v19 + 216LL))(
         v19,
         &v11,
         qword_180061628,
         &v20);
  v3 = v8;
  if ( v8 < 0 )
  {
    UnattendLogW(1, L"GetElementsByTagName failed. 0x%x", (unsigned int)v8);
    goto LABEL_25;
  }
  if ( !v21 )
  {
    v6 = L"No RecoveryImageIndexTags found";
    goto LABEL_10;
  }
  if ( v21 != 1 )
  {
    v6 = L"Exactly 1 RecoveryImageIndex tag required.";
    goto LABEL_10;
  }
  v11 = *v20;
  InnerText = Windows::Microdom::Rtl::Library::GetInnerText(v19, &v11, &v26);
  v3 = InnerText;
  if ( InnerText < 0 )
    UnattendLogW(1, L"GetInnerText() failed. error = 0x%x", (unsigned int)InnerText);
  *((_DWORD *)this + 1) = winreConvertLUTF8ToInt(&v26);
  v7 = 0;
  if ( v3 < 0 )
    goto LABEL_25;
LABEL_26:
  if ( v27 )
  {
    RtlFreeLUtf8String(&v26);
    v26 = 0;
    v27 = 0;
  }
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v20);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v22);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v24);
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v19);
  return v7;
}

```

## disassembly

```asm
0x18003fc50  push    rbp
0x18003fc52  push    rbx
0x18003fc53  push    rsi
0x18003fc54  push    rdi
0x18003fc55  lea     rbp, [rsp-18h]
0x18003fc5a  sub     rsp, 118h
0x18003fc61  mov     [rsp+130h+var_E8], 0FFFFFFFFFFFFFFFEh
0x18003fc6a  mov     rax, cs:__security_cookie
0x18003fc71  xor     rax, rsp
0x18003fc74  mov     [rbp+30h+var_30], rax
0x18003fc78  mov     rbx, rcx
0x18003fc7b  mov     [rbp+30h+var_90], 0
0x18003fc83  xorps   xmm0, xmm0
0x18003fc86  movdqu  [rsp+130h+var_B8], xmm0
0x18003fc8c  mov     [rbp+30h+var_98], 0
0x18003fc94  movups  [rbp+30h+var_40], xmm0
0x18003fc98  mov     [rbp+30h+var_68], 0
0x18003fca0  mov     [rbp+30h+var_60], 0
0x18003fca8  mov     [rbp+30h+var_78], 0
0x18003fcb0  mov     [rbp+30h+var_70], 0
0x18003fcb8  mov     [rbp+30h+var_88], 0
0x18003fcc0  mov     [rbp+30h+var_80], 0
0x18003fcc8  xor     eax, eax
0x18003fcca  movups  [rbp+30h+var_58], xmm0
0x18003fcce  mov     [rbp+30h+var_48], rax
0x18003fcd2  mov     eax, [rcx]
0x18003fcd4  mov     [rsp+130h+var_E0], rax
0x18003fcd9  mov     [rsp+130h+var_D8], rax
0x18003fcde  mov     rax, [rcx+8]
0x18003fce2  mov     [rsp+130h+var_D0], rax
0x18003fce7  mov     esi, 1
0x18003fcec  mov     [rsp+130h+var_C8], esi
0x18003fcf0  mov     [rsp+130h+var_C4], esi
0x18003fcf4  movdqu  [rbp+30h+var_A8], xmm0
0x18003fcf9  lea     rax, [rsp+130h+var_E0]
0x18003fcfe  mov     [rsp+130h+var_C0], rax
0x18003fd03  lea     rdx, [rbp+30h+var_90]
0x18003fd07  lea     rcx, [rsp+130h+var_C8]
0x18003fd0c  call    cs:__imp_RtlCreateMicrodom
0x18003fd12  mov     edi, eax
0x18003fd14  test    eax, eax
0x18003fd16  jns     short loc_18003FD36
0x18003fd18  mov     r8d, eax
0x18003fd1b  lea     rdx, aRtlcreatemicro_0; "RtlCreateMicrodom failed: 0x%x"
0x18003fd22  mov     ecx, esi
0x18003fd24  call    UnattendLogW
0x18003fd29  mov     ecx, edi; Status
0x18003fd2b  call    cs:__imp_RtlNtStatusToDosError
0x18003fd31  jmp     loc_18003FEB7
0x18003fd36  mov     rcx, [rbp+30h+var_90]
0x18003fd3a  mov     rax, [rcx]
0x18003fd3d  lea     rdx, [rbp+30h+var_40]
0x18003fd41  mov     rax, [rax+18h]
0x18003fd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd4a  mov     edi, eax
0x18003fd4c  test    eax, eax
0x18003fd4e  jns     short loc_18003FD66
0x18003fd50  lea     rdx, aGetdocumentFai; "GetDocument failed: 0x%x"
0x18003fd57  mov     r8d, eax
0x18003fd5a  mov     ecx, esi
0x18003fd5c  call    UnattendLogW
0x18003fd61  jmp     loc_18003FEB7
0x18003fd66  mov     rcx, [rbp+30h+var_90]
0x18003fd6a  mov     rax, [rcx]
0x18003fd6d  lea     r8, [rbp+30h+var_68]
0x18003fd71  lea     rdx, qword_180061658
0x18003fd78  mov     rax, [rax+0E0h]
0x18003fd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd84  mov     edi, eax
0x18003fd86  test    eax, eax
0x18003fd88  jns     short loc_18003FD93
0x18003fd8a  lea     rdx, aGetelementsbyt; "GetElementsByTagName failed: 0x%x"
0x18003fd91  jmp     short loc_18003FD57
0x18003fd93  cmp     [rbp+30h+var_60], rsi
0x18003fd97  jz      short loc_18003FDB1
0x18003fd99  lea     rdx, aExactly1ResetT; "Exactly 1 Reset tag required."
0x18003fda0  mov     ebx, 0Dh
0x18003fda5  mov     ecx, esi
0x18003fda7  call    UnattendLogW
0x18003fdac  jmp     loc_18003FEC1
0x18003fdb1  mov     rcx, [rbp+30h+var_90]
0x18003fdb5  mov     rax, [rbp+30h+var_68]
0x18003fdb9  movups  xmm0, xmmword ptr [rax]
0x18003fdbc  movdqu  [rsp+130h+var_100], xmm0
0x18003fdc2  mov     rax, [rcx]
0x18003fdc5  lea     r9, [rbp+30h+var_78]
0x18003fdc9  lea     r8, qword_180061640
0x18003fdd0  lea     rdx, [rsp+130h+var_100]
0x18003fdd5  mov     rax, [rax+0D8h]
0x18003fddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fde1  mov     edi, eax
0x18003fde3  test    eax, eax
0x18003fde5  js      short loc_18003FD8A
0x18003fde7  mov     rax, [rbp+30h+var_70]
0x18003fdeb  test    rax, rax
0x18003fdee  jnz     short loc_18003FDF9
0x18003fdf0  lea     rdx, aNoSystemdiskTa; "No SystemDisk tags found."
0x18003fdf7  jmp     short loc_18003FDA0
0x18003fdf9  cmp     rax, rsi
0x18003fdfc  jz      short loc_18003FE07
0x18003fdfe  lea     rdx, aExactly1System; "Exactly 1 SystemDisk tag required."
0x18003fe05  jmp     short loc_18003FDA0
0x18003fe07  mov     rcx, [rbp+30h+var_90]
0x18003fe0b  mov     rax, [rbp+30h+var_78]
0x18003fe0f  movups  xmm0, xmmword ptr [rax]
0x18003fe12  movdqu  [rsp+130h+var_100], xmm0
0x18003fe18  mov     rax, [rcx]
0x18003fe1b  lea     r9, [rbp+30h+var_88]
0x18003fe1f  lea     r8, qword_180061628
0x18003fe26  lea     rdx, [rsp+130h+var_100]
0x18003fe2b  mov     rax, [rax+0D8h]
0x18003fe32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe37  mov     edi, eax
0x18003fe39  test    eax, eax
0x18003fe3b  jns     short loc_18003FE49
0x18003fe3d  lea     rdx, aGetelementsbyt_0; "GetElementsByTagName failed. 0x%x"
0x18003fe44  jmp     loc_18003FD57
0x18003fe49  mov     rax, [rbp+30h+var_80]
0x18003fe4d  test    rax, rax
0x18003fe50  jnz     short loc_18003FE5E
0x18003fe52  lea     rdx, aNoRecoveryimag; "No RecoveryImageIndexTags found"
0x18003fe59  jmp     loc_18003FDA0
0x18003fe5e  cmp     rax, rsi
0x18003fe61  jz      short loc_18003FE6F
0x18003fe63  lea     rdx, aExactly1Recove; "Exactly 1 RecoveryImageIndex tag requir"...
0x18003fe6a  jmp     loc_18003FDA0
0x18003fe6f  mov     rax, [rbp+30h+var_88]
0x18003fe73  movups  xmm0, xmmword ptr [rax]
0x18003fe76  movdqu  [rsp+130h+var_100], xmm0
0x18003fe7c  lea     r8, [rbp+30h+var_58]
0x18003fe80  lea     rdx, [rsp+130h+var_100]
0x18003fe85  mov     rcx, [rbp+30h+var_90]
0x18003fe89  call    ?GetInnerText@Library@Rtl@Microdom@Windows@@YAJPEAUIRtlMicrodom@234@UElement@234@PEAV?$Auto@U_LUTF8_STRING@@@4@@Z; Windows::Microdom::Rtl::Library::GetInnerText(Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Auto<_LUTF8_STRING> *)
0x18003fe8e  mov     edi, eax
0x18003fe90  test    eax, eax
0x18003fe92  jns     short loc_18003FEA5
0x18003fe94  mov     r8d, eax
0x18003fe97  lea     rdx, aGetinnertextFa_0; "GetInnerText() failed. error = 0x%x"
0x18003fe9e  mov     ecx, esi
0x18003fea0  call    UnattendLogW
0x18003fea5  lea     rcx, [rbp+30h+var_58]
0x18003fea9  call    winreConvertLUTF8ToInt
0x18003feae  mov     [rbx+4], eax
0x18003feb1  xor     ebx, ebx
0x18003feb3  test    edi, edi
0x18003feb5  jns     short loc_18003FEC1
0x18003feb7  mov     ecx, edi; Status
0x18003feb9  call    cs:__imp_RtlNtStatusToDosError
0x18003febf  mov     ebx, eax
0x18003fec1  cmp     [rbp+30h+var_48], 0
0x18003fec6  jz      short loc_18003FEDF
0x18003fec8  lea     rcx, [rbp+30h+var_58]
0x18003fecc  call    cs:__imp_RtlFreeLUtf8String
0x18003fed2  xorps   xmm0, xmm0
0x18003fed5  xor     eax, eax
0x18003fed7  movups  [rbp+30h+var_58], xmm0
0x18003fedb  mov     [rbp+30h+var_48], rax
0x18003fedf  lea     rcx, [rbp+30h+var_88]
0x18003fee3  call    ??1?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>(void)
0x18003fee8  nop
0x18003fee9  lea     rcx, [rbp+30h+var_78]
0x18003feed  call    ??1?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>(void)
0x18003fef2  nop
0x18003fef3  lea     rcx, [rbp+30h+var_68]
0x18003fef7  call    ??1?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>(void)
0x18003fefc  nop
0x18003fefd  lea     rcx, [rbp+30h+var_90]
0x18003ff01  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18003ff06  mov     eax, ebx
0x18003ff08  mov     rcx, [rbp+30h+var_30]
0x18003ff0c  xor     rcx, rsp; StackCookie
0x18003ff0f  call    __security_check_cookie
0x18003ff14  add     rsp, 118h
0x18003ff1b  pop     rdi
0x18003ff1c  pop     rsi
0x18003ff1d  pop     rbx
0x18003ff1e  pop     rbp
0x18003ff1f  retn
```
