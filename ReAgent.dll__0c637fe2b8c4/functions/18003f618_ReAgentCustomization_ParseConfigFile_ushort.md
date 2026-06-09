# ReAgentCustomization::ParseConfigFile(ushort *)

- ea: `0x18003f618`
- end: `0x18003fc48`
- name: `?ParseConfigFile@ReAgentCustomization@@QEAAKPEAG@Z`
- size: `1584`
- prototype: `unsigned int(ReAgentCustomization *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800224f0`
- `0x180026158`

## callees

- `0x1800059fc`
- `0x180008600`
- `0x180017014`
- `0x18003ece4`
- `0x18003ed88`
- `0x18003f618`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003f860`
- `msvcrt!_wcsicmp` at `0x18003f860`
- `ntdll!RtlNtStatusToDosError` at `0x18003f6f0`
- `ntdll!RtlNtStatusToDosError` at `0x18003fbf7`
- `ntdll!RtlNtStatusToDosError` at `0x18003f6f0`
- `ntdll!RtlNtStatusToDosError` at `0x18003fbf7`
- `ServicingCommon!RtlCreateMicrodom` at `0x18003f6d0`
- `ServicingCommon!RtlCreateMicrodom` at `0x18003f6d0`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003f9ca`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003f9e7`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fa23`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fa74`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fad2`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb0c`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb48`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb65`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fbac`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fbc9`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003f9ca`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003f9e7`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fa23`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fa74`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fad2`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb0c`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb48`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fb65`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fbac`
- `ServicingCommon!RtlFreeLUtf8String` at `0x18003fbc9`

## string_xrefs

- `0x18003f6df`: `RtlCreateMicrodom failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ReAgentCustomization::ParseConfigFile(ReAgentCustomization *this, unsigned __int16 *a2)
{
  int v4; // esi
  int Microdom; // eax
  NTSTATUS v6; // edi
  int v7; // eax
  int v8; // eax
  const wchar_t *v9; // rdx
  ULONG v10; // ebx
  unsigned __int64 v11; // rax
  unsigned int i; // r14d
  int v13; // eax
  ULONG v14; // eax
  int v15; // eax
  int v16; // eax
  int InnerText; // eax
  ULONG v18; // eax
  bool v19; // zf
  bool v20; // zf
  __int128 v22; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-C0h]
  __int64 v24; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v25[3]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v27; // [rsp+80h] [rbp-88h]
  __int128 v28; // [rsp+90h] [rbp-78h]
  __int64 v29; // [rsp+A0h] [rbp-68h]
  __int128 v30; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-38h]
  _QWORD v34[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v35; // [rsp+E8h] [rbp-20h] BYREF
  __int128 *v36; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v37; // [rsp+100h] [rbp-8h]
  __int64 v38; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 v39; // [rsp+110h] [rbp+8h]
  __int128 *v40; // [rsp+118h] [rbp+10h] BYREF
  __int64 v41; // [rsp+120h] [rbp+18h]
  __int128 v42; // [rsp+128h] [rbp+20h] BYREF
  wchar_t String1[304]; // [rsp+138h] [rbp+30h] BYREF

  v23 = -2;
  v4 = 0;
  v34[0] = 0;
  v27 = 0;
  v29 = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  memset_0(String1, 0, 0x25Cu);
  v25[0] = *(unsigned int *)this;
  v25[1] = v25[0];
  v25[2] = *((_QWORD *)this + 1);
  v26[0] = 0x100000001LL;
  v28 = 0;
  v26[1] = v25;
  Microdom = RtlCreateMicrodom(v26, v34);
  v6 = Microdom;
  if ( Microdom < 0 )
  {
    UnattendLogW(1, L"RtlCreateMicrodom failed: 0x%x", (unsigned int)Microdom);
    RtlNtStatusToDosError(v6);
LABEL_66:
    v10 = RtlNtStatusToDosError(v6);
    goto LABEL_67;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v34[0] + 24LL))(v34[0], &v42);
  v6 = v7;
  if ( v7 < 0 )
  {
    UnattendLogW(1, L"GetDocument failed: 0x%x", (unsigned int)v7);
    goto LABEL_66;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 **))(*(_QWORD *)v34[0] + 224LL))(
         v34[0],
         qword_1800616D0,
         &v40);
  v6 = v8;
  if ( v8 < 0 )
  {
LABEL_7:
    UnattendLogW(1, L"GetElementsByTagName failed: 0x%x", (unsigned int)v8);
    goto LABEL_66;
  }
  if ( v41 == 1 )
  {
    v35 = *v40;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, __int64 *))(*(_QWORD *)v34[0] + 216LL))(
           v34[0],
           &v35,
           qword_1800616B8,
           &v38);
    v6 = v8;
    if ( v8 < 0 )
      goto LABEL_7;
    v11 = v39;
    if ( v39 )
    {
      v10 = 0;
      for ( i = 0; i < v11; ++i )
      {
        v35 = 0u;
        v36 = 0;
        v37 = 0;
        v24 = 0;
        v32 = 0;
        v33 = 0;
        v30 = 0;
        v31 = 0;
        v22 = *(_OWORD *)(v38 + 16LL * i);
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, __int64 *))(*(_QWORD *)v34[0] + 264LL))(
                v34[0],
                &v22,
                qword_1800616A0,
                &v24);
        v6 = v13;
        if ( v13 < 0 )
        {
          UnattendLogW(1, L"GetAttribute failed: 0x%x", (unsigned int)v13);
          if ( v31 )
          {
            RtlFreeLUtf8String(&v30);
            v30 = 0;
            v31 = 0;
          }
          v20 = v33 == 0;
          goto LABEL_62;
        }
        v14 = winreUtf8ToUnicode(v24, String1, 0);
        v10 = v14;
        if ( v14 )
        {
          UnattendLogW(1, L"winreUtf8ToUnicode failed: 0x%x", v14);
          if ( v31 )
          {
            RtlFreeLUtf8String(&v30);
            v30 = 0;
            v31 = 0;
          }
          v19 = v33 == 0;
          goto LABEL_56;
        }
        if ( !a2 || !_wcsicmp(String1, a2) )
          v4 = 1;
        if ( !i || v4 )
        {
          v22 = *(_OWORD *)(v38 + 16LL * i);
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, __int128 *))(*(_QWORD *)v34[0] + 216LL))(
                  v34[0],
                  &v22,
                  qword_180061688,
                  &v35);
          v6 = v15;
          if ( v15 < 0 )
          {
            UnattendLogW(1, L"GetElementsByTagName failed: 0x%x", (unsigned int)v15);
            if ( v31 )
            {
              RtlFreeLUtf8String(&v30);
              v30 = 0;
              v31 = 0;
            }
            v20 = v33 == 0;
LABEL_62:
            if ( !v20 )
            {
              RtlFreeLUtf8String(&v32);
              v32 = 0;
              v33 = 0;
            }
            Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v36);
            Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v35);
            goto LABEL_66;
          }
          if ( *((_QWORD *)&v35 + 1) != 1 )
          {
            v10 = 13;
            UnattendLogW(1, L"Exactly 1 Name tag required.");
            if ( v31 )
            {
              RtlFreeLUtf8String(&v30);
              v30 = 0;
              v31 = 0;
            }
            v19 = v33 == 0;
            goto LABEL_56;
          }
          v22 = *(_OWORD *)(v38 + 16LL * i);
          v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, __int128 **))(*(_QWORD *)v34[0] + 216LL))(
                  v34[0],
                  &v22,
                  qword_180061670,
                  &v36);
          v6 = v16;
          if ( v16 < 0 )
          {
            UnattendLogW(1, L"GetElementsByTagName failed: 0x%x", (unsigned int)v16);
LABEL_42:
            if ( v31 )
            {
              RtlFreeLUtf8String(&v30);
              v30 = 0;
              v31 = 0;
            }
            v20 = v33 == 0;
            goto LABEL_62;
          }
          if ( v37 != 1 )
          {
            v10 = 13;
            UnattendLogW(1, L"Exactly 1 Description tag required.");
LABEL_37:
            if ( v31 )
            {
              RtlFreeLUtf8String(&v30);
              v30 = 0;
              v31 = 0;
            }
            v19 = v33 == 0;
LABEL_56:
            if ( !v19 )
            {
              RtlFreeLUtf8String(&v32);
              v32 = 0;
              v33 = 0;
            }
            Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v36);
            Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v35);
            goto LABEL_67;
          }
          v22 = *(_OWORD *)v35;
          InnerText = Windows::Microdom::Rtl::Library::GetInnerText(v34[0], &v22, &v32);
          v6 = InnerText;
          if ( InnerText < 0 )
            goto LABEL_41;
          memset_0((char *)this + 16, 0, 0x25Cu);
          v18 = winreUtf8ToUnicode(&v32, (char *)this + 16, 0);
          v10 = v18;
          if ( v18 )
          {
LABEL_40:
            UnattendLogW(1, L"winreUtf8ToUnicode failed: 0x%x", v18);
            goto LABEL_37;
          }
          v22 = *v36;
          InnerText = Windows::Microdom::Rtl::Library::GetInnerText(v34[0], &v22, &v30);
          v6 = InnerText;
          if ( InnerText < 0 )
          {
LABEL_41:
            UnattendLogW(1, L"GetInnerText failed: 0x%x", (unsigned int)InnerText);
            goto LABEL_42;
          }
          memset_0((char *)this + 620, 0, 0x25Cu);
          v18 = winreUtf8ToUnicode(&v30, (char *)this + 620, 0);
          v10 = v18;
          if ( v18 )
            goto LABEL_40;
          if ( v4 )
            goto LABEL_37;
        }
        v4 = 0;
        if ( v31 )
        {
          RtlFreeLUtf8String(&v30);
          v30 = 0;
          v31 = 0;
        }
        if ( v33 )
        {
          RtlFreeLUtf8String(&v32);
          v32 = 0;
          v33 = 0;
        }
        Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v36);
        Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v35);
        v11 = v39;
      }
      if ( v6 >= 0 )
        goto LABEL_67;
      goto LABEL_66;
    }
    v9 = L"No WinReTool tags found.";
  }
  else
  {
    v9 = L"Exactly 1 BootShell tag required.";
  }
  v10 = 13;
  UnattendLogW(1, v9);
LABEL_67:
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v38);
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>((__int64)&v40);
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(v34);
  return v10;
}

```

## disassembly

```asm
0x18003f618  mov     rax, rsp
0x18003f61b  push    rbp
0x18003f61c  push    rsi
0x18003f61d  push    rdi
0x18003f61e  push    r12
0x18003f620  push    r13
0x18003f622  push    r14
0x18003f624  push    r15
0x18003f626  lea     rbp, [rax-2D8h]
0x18003f62d  sub     rsp, 3A0h
0x18003f634  mov     [rsp+3D0h+var_390], 0FFFFFFFFFFFFFFFEh
0x18003f63d  mov     [rax+18h], rbx
0x18003f641  mov     rax, cs:__security_cookie
0x18003f648  xor     rax, rsp
0x18003f64b  mov     [rbp+2D0h+var_40], rax
0x18003f652  mov     r12, rdx
0x18003f655  mov     r13, rcx
0x18003f658  xor     esi, esi
0x18003f65a  mov     [rbp+2D0h+var_300], rsi
0x18003f65e  xorps   xmm0, xmm0
0x18003f661  movdqu  xmmword ptr [rsp+3D0h+var_360+8], xmm0
0x18003f667  mov     [rbp+2D0h+var_338], rsi
0x18003f66b  movups  [rbp+2D0h+var_2B0], xmm0
0x18003f66f  mov     [rbp+2D0h+var_2C0], rsi
0x18003f673  mov     [rbp+2D0h+var_2B8], rsi
0x18003f677  mov     [rbp+2D0h+var_2D0], rsi
0x18003f67b  mov     [rbp+2D0h+var_2C8], rsi
0x18003f67f  xor     edx, edx; Val
0x18003f681  mov     r8d, 25Ch; Size
0x18003f687  lea     rcx, [rbp+2D0h+String1]; void *
0x18003f68b  call    memset_0
0x18003f690  mov     eax, [r13+0]
0x18003f694  mov     [rsp+3D0h+var_380], rax
0x18003f699  mov     [rsp+3D0h+var_378], rax
0x18003f69e  mov     rax, [r13+8]
0x18003f6a2  mov     qword ptr [rsp+3D0h+var_370], rax
0x18003f6a7  lea     r14d, [rsi+1]
0x18003f6ab  mov     dword ptr [rsp+3D0h+var_368], r14d
0x18003f6b0  mov     dword ptr [rsp+3D0h+var_368+4], r14d
0x18003f6b5  xorps   xmm0, xmm0
0x18003f6b8  movdqu  [rbp+2D0h+var_348], xmm0
0x18003f6bd  lea     rax, [rsp+3D0h+var_380]
0x18003f6c2  mov     qword ptr [rsp+3D0h+var_360], rax
0x18003f6c7  lea     rdx, [rbp+2D0h+var_300]
0x18003f6cb  lea     rcx, [rsp+3D0h+var_368]
0x18003f6d0  call    cs:__imp_RtlCreateMicrodom
0x18003f6d6  mov     edi, eax
0x18003f6d8  test    eax, eax
0x18003f6da  jns     short loc_18003F6FB
0x18003f6dc  mov     r8d, eax
0x18003f6df  lea     rdx, aRtlcreatemicro_0; "RtlCreateMicrodom failed: 0x%x"
0x18003f6e6  mov     ecx, r14d
0x18003f6e9  call    UnattendLogW
0x18003f6ee  mov     ecx, edi; Status
0x18003f6f0  call    cs:__imp_RtlNtStatusToDosError
0x18003f6f6  jmp     loc_18003FBF5
0x18003f6fb  mov     rcx, [rbp+2D0h+var_300]
0x18003f6ff  mov     rax, [rcx]
0x18003f702  lea     rdx, [rbp+2D0h+var_2B0]
0x18003f706  mov     rax, [rax+18h]
0x18003f70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f70f  mov     edi, eax
0x18003f711  test    eax, eax
0x18003f713  jns     short loc_18003F72C
0x18003f715  lea     rdx, aGetdocumentFai; "GetDocument failed: 0x%x"
0x18003f71c  mov     r8d, eax
0x18003f71f  mov     ecx, r14d
0x18003f722  call    UnattendLogW
0x18003f727  jmp     loc_18003FBF5
0x18003f72c  mov     rcx, [rbp+2D0h+var_300]
0x18003f730  mov     rax, [rcx]
0x18003f733  lea     r8, [rbp+2D0h+var_2C0]
0x18003f737  lea     rdx, qword_1800616D0
0x18003f73e  mov     rax, [rax+0E0h]
0x18003f745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f74a  mov     edi, eax
0x18003f74c  test    eax, eax
0x18003f74e  jns     short loc_18003F759
0x18003f750  lea     rdx, aGetelementsbyt; "GetElementsByTagName failed: 0x%x"
0x18003f757  jmp     short loc_18003F71C
0x18003f759  cmp     [rbp+2D0h+var_2B8], r14
0x18003f75d  jz      short loc_18003F778
0x18003f75f  lea     rdx, aExactly1Bootsh; "Exactly 1 BootShell tag required."
0x18003f766  mov     ebx, 0Dh
0x18003f76b  mov     ecx, r14d
0x18003f76e  call    UnattendLogW
0x18003f773  jmp     loc_18003FBFF
0x18003f778  mov     rcx, [rbp+2D0h+var_300]
0x18003f77c  mov     rax, [rbp+2D0h+var_2C0]
0x18003f780  movups  xmm0, xmmword ptr [rax]
0x18003f783  movdqu  [rbp+2D0h+var_2F0], xmm0
0x18003f788  mov     rax, [rcx]
0x18003f78b  lea     r9, [rbp+2D0h+var_2D0]
0x18003f78f  lea     r8, qword_1800616B8
0x18003f796  lea     rdx, [rbp+2D0h+var_2F0]
0x18003f79a  mov     rax, [rax+0D8h]
0x18003f7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7a6  mov     edi, eax
0x18003f7a8  test    eax, eax
0x18003f7aa  js      short loc_18003F750
0x18003f7ac  mov     rax, [rbp+2D0h+var_2C8]
0x18003f7b0  test    rax, rax
0x18003f7b3  jnz     short loc_18003F7BE
0x18003f7b5  lea     rdx, aNoWinretoolTag; "No WinReTool tags found."
0x18003f7bc  jmp     short loc_18003F766
0x18003f7be  mov     ebx, esi
0x18003f7c0  mov     r14d, esi
0x18003f7c3  mov     r15d, r14d
0x18003f7c6  cmp     r15, rax
0x18003f7c9  jnb     loc_18003FBF1
0x18003f7cf  mov     qword ptr [rbp+2D0h+var_2F0], rsi
0x18003f7d3  mov     qword ptr [rbp+2D0h+var_2F0+8], rsi
0x18003f7d7  mov     [rbp+2D0h+var_2E0], rsi
0x18003f7db  mov     [rbp+2D0h+var_2D8], rsi
0x18003f7df  mov     [rsp+3D0h+var_388], rsi
0x18003f7e4  xorps   xmm0, xmm0
0x18003f7e7  xor     eax, eax
0x18003f7e9  movups  [rbp+2D0h+var_318], xmm0
0x18003f7ed  mov     [rbp+2D0h+var_308], rax
0x18003f7f1  movups  [rbp+2D0h+var_330], xmm0
0x18003f7f5  mov     [rbp+2D0h+var_320], rax
0x18003f7f9  mov     rcx, [rbp+2D0h+var_300]
0x18003f7fd  add     r15, r15
0x18003f800  mov     rax, [rbp+2D0h+var_2D0]
0x18003f804  movups  xmm0, xmmword ptr [rax+r15*8]
0x18003f809  movdqu  [rsp+3D0h+var_3A8+8], xmm0
0x18003f80f  mov     rax, [rcx]
0x18003f812  lea     r9, [rsp+3D0h+var_388]
0x18003f817  lea     r8, qword_1800616A0
0x18003f81e  lea     rdx, [rsp+3D0h+var_3A8+8]
0x18003f823  mov     rax, [rax+108h]
0x18003f82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f82f  mov     edi, eax
0x18003f831  test    eax, eax
0x18003f833  js      loc_18003FB8D
0x18003f839  xor     r8d, r8d
0x18003f83c  lea     rdx, [rbp+2D0h+String1]
0x18003f840  mov     rcx, [rsp+3D0h+var_388]
0x18003f845  call    winreUtf8ToUnicode
0x18003f84a  mov     ebx, eax
0x18003f84c  test    eax, eax
0x18003f84e  jnz     loc_18003FB29
0x18003f854  test    r12, r12
0x18003f857  jz      short loc_18003F86A
0x18003f859  mov     rdx, r12; String2
0x18003f85c  lea     rcx, [rbp+2D0h+String1]; String1
0x18003f860  call    cs:__imp__wcsicmp
0x18003f866  test    eax, eax
0x18003f868  jnz     short loc_18003F86F
0x18003f86a  mov     esi, 1
0x18003f86f  test    r14d, r14d
0x18003f872  jz      short loc_18003F87C
0x18003f874  test    esi, esi
0x18003f876  jz      loc_18003F9BE
0x18003f87c  mov     rcx, [rbp+2D0h+var_300]
0x18003f880  mov     rax, [rbp+2D0h+var_2D0]
0x18003f884  movups  xmm0, xmmword ptr [rax+r15*8]
0x18003f889  movdqu  [rsp+3D0h+var_3A8+8], xmm0
0x18003f88f  mov     rax, [rcx]
0x18003f892  lea     r9, [rbp+2D0h+var_2F0]
0x18003f896  lea     r8, qword_180061688
0x18003f89d  lea     rdx, [rsp+3D0h+var_3A8+8]
0x18003f8a2  mov     rax, [rax+0D8h]
0x18003f8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8ae  mov     edi, eax
0x18003f8b0  test    eax, eax
0x18003f8b2  js      loc_18003FAEC
0x18003f8b8  cmp     qword ptr [rbp+2D0h+var_2F0+8], 1
0x18003f8bd  jnz     loc_18003FAB2
0x18003f8c3  mov     rcx, [rbp+2D0h+var_300]
0x18003f8c7  mov     rax, [rbp+2D0h+var_2D0]
0x18003f8cb  movups  xmm0, xmmword ptr [rax+r15*8]
0x18003f8d0  movdqu  [rsp+3D0h+var_3A8+8], xmm0
0x18003f8d6  mov     rax, [rcx]
0x18003f8d9  lea     r9, [rbp+2D0h+var_2E0]
0x18003f8dd  lea     r8, qword_180061670
0x18003f8e4  lea     rdx, [rsp+3D0h+var_3A8+8]
0x18003f8e9  mov     rax, [rax+0D8h]
0x18003f8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8f5  mov     edi, eax
0x18003f8f7  xor     r15d, r15d
0x18003f8fa  test    eax, eax
0x18003f8fc  js      loc_18003FAA9
0x18003f902  cmp     [rbp+2D0h+var_2D8], 1
0x18003f907  jnz     loc_18003FA90
0x18003f90d  mov     rax, qword ptr [rbp+2D0h+var_2F0]
0x18003f911  movups  xmm0, xmmword ptr [rax]
0x18003f914  movdqu  [rsp+3D0h+var_3A8+8], xmm0
0x18003f91a  lea     r8, [rbp+2D0h+var_318]
0x18003f91e  lea     rdx, [rsp+3D0h+var_3A8+8]
0x18003f923  mov     rcx, [rbp+2D0h+var_300]
0x18003f927  call    ?GetInnerText@Library@Rtl@Microdom@Windows@@YAJPEAUIRtlMicrodom@234@UElement@234@PEAV?$Auto@U_LUTF8_STRING@@@4@@Z; Windows::Microdom::Rtl::Library::GetInnerText(Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Auto<_LUTF8_STRING> *)
0x18003f92c  mov     edi, eax
0x18003f92e  test    eax, eax
0x18003f930  js      loc_18003FA55
0x18003f936  xor     edx, edx; Val
0x18003f938  mov     r8d, 25Ch; Size
0x18003f93e  lea     rcx, [r13+10h]; void *
0x18003f942  call    memset_0
0x18003f947  xor     r8d, r8d
0x18003f94a  lea     rdx, [r13+10h]
0x18003f94e  lea     rcx, [rbp+2D0h+var_318]
0x18003f952  call    winreUtf8ToUnicode
0x18003f957  mov     ebx, eax
0x18003f959  test    eax, eax
0x18003f95b  jnz     loc_18003FA3F
0x18003f961  mov     rax, [rbp+2D0h+var_2E0]
0x18003f965  movups  xmm0, xmmword ptr [rax]
0x18003f968  movdqu  [rsp+3D0h+var_3A8+8], xmm0
0x18003f96e  lea     r8, [rbp+2D0h+var_330]
0x18003f972  lea     rdx, [rsp+3D0h+var_3A8+8]
0x18003f977  mov     rcx, [rbp+2D0h+var_300]
0x18003f97b  call    ?GetInnerText@Library@Rtl@Microdom@Windows@@YAJPEAUIRtlMicrodom@234@UElement@234@PEAV?$Auto@U_LUTF8_STRING@@@4@@Z; Windows::Microdom::Rtl::Library::GetInnerText(Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Auto<_LUTF8_STRING> *)
0x18003f980  mov     edi, eax
0x18003f982  test    eax, eax
0x18003f984  js      loc_18003FA55
0x18003f98a  lea     rbx, [r13+26Ch]
0x18003f991  xor     edx, edx; Val
0x18003f993  mov     r8d, 25Ch; Size
0x18003f999  mov     rcx, rbx; void *
0x18003f99c  call    memset_0
0x18003f9a1  xor     r8d, r8d
0x18003f9a4  mov     rdx, rbx
0x18003f9a7  lea     rcx, [rbp+2D0h+var_330]
0x18003f9ab  call    winreUtf8ToUnicode
0x18003f9b0  mov     ebx, eax
0x18003f9b2  test    eax, eax
0x18003f9b4  jnz     loc_18003FA3F
0x18003f9ba  test    esi, esi
0x18003f9bc  jnz     short loc_18003FA19
0x18003f9be  xor     esi, esi
0x18003f9c0  cmp     [rbp+2D0h+var_320], rsi
0x18003f9c4  jz      short loc_18003F9DD
0x18003f9c6  lea     rcx, [rbp+2D0h+var_330]
0x18003f9ca  call    cs:__imp_RtlFreeLUtf8String
0x18003f9d0  xorps   xmm0, xmm0
0x18003f9d3  xor     eax, eax
0x18003f9d5  movups  [rbp+2D0h+var_330], xmm0
0x18003f9d9  mov     [rbp+2D0h+var_320], rax
0x18003f9dd  cmp     [rbp+2D0h+var_308], rsi
0x18003f9e1  jz      short loc_18003F9FA
0x18003f9e3  lea     rcx, [rbp+2D0h+var_318]
0x18003f9e7  call    cs:__imp_RtlFreeLUtf8String
0x18003f9ed  xorps   xmm0, xmm0
0x18003f9f0  xor     eax, eax
0x18003f9f2  movups  [rbp+2D0h+var_318], xmm0
0x18003f9f6  mov     [rbp+2D0h+var_308], rax
0x18003f9fa  lea     rcx, [rbp+2D0h+var_2E0]
0x18003f9fe  call    ??1?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>(void)
0x18003fa03  nop
0x18003fa04  lea     rcx, [rbp+2D0h+var_2F0]
0x18003fa08  call    ??1?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>(void)
0x18003fa0d  inc     r14d
0x18003fa10  mov     rax, [rbp+2D0h+var_2C8]
0x18003fa14  jmp     loc_18003F7C3
0x18003fa19  cmp     [rbp+2D0h+var_320], r15
0x18003fa1d  jz      short loc_18003FA36
0x18003fa1f  lea     rcx, [rbp+2D0h+var_330]
0x18003fa23  call    cs:__imp_RtlFreeLUtf8String
0x18003fa29  xorps   xmm0, xmm0
0x18003fa2c  xor     eax, eax
0x18003fa2e  movups  [rbp+2D0h+var_330], xmm0
0x18003fa32  mov     [rbp+2D0h+var_320], rax
0x18003fa36  cmp     [rbp+2D0h+var_308], r15
0x18003fa3a  jmp     loc_18003FB5F
0x18003fa3f  mov     r8d, eax
0x18003fa42  lea     rdx, aWinreutf8touni; "winreUtf8ToUnicode failed: 0x%x"
0x18003fa49  mov     ecx, 1
0x18003fa4e  call    UnattendLogW
0x18003fa53  jmp     short loc_18003FA19
0x18003fa55  lea     rdx, aGetinnertextFa; "GetInnerText failed: 0x%x"
0x18003fa5c  mov     r8d, eax
0x18003fa5f  mov     ecx, 1
0x18003fa64  call    UnattendLogW
0x18003fa69  nop
0x18003fa6a  cmp     [rbp+2D0h+var_320], r15
0x18003fa6e  jz      short loc_18003FA87
0x18003fa70  lea     rcx, [rbp+2D0h+var_330]
0x18003fa74  call    cs:__imp_RtlFreeLUtf8String
0x18003fa7a  xorps   xmm0, xmm0
0x18003fa7d  xor     eax, eax
0x18003fa7f  movups  [rbp+2D0h+var_330], xmm0
0x18003fa83  mov     [rbp+2D0h+var_320], rax
0x18003fa87  cmp     [rbp+2D0h+var_308], r15
0x18003fa8b  jmp     loc_18003FBC3
0x18003fa90  mov     ebx, 0Dh
0x18003fa95  lea     rdx, aExactly1Descri; "Exactly 1 Description tag required."
0x18003fa9c  lea     ecx, [rbx-0Ch]
0x18003fa9f  call    UnattendLogW
0x18003faa4  jmp     loc_18003FA19
0x18003faa9  lea     rdx, aGetelementsbyt; "GetElementsByTagName failed: 0x%x"
0x18003fab0  jmp     short loc_18003FA5C
0x18003fab2  mov     ebx, 0Dh
0x18003fab7  lea     rdx, aExactly1NameTa; "Exactly 1 Name tag required."
0x18003fabe  lea     ecx, [rbx-0Ch]
0x18003fac1  call    UnattendLogW
0x18003fac6  nop
0x18003fac7  cmp     [rbp+2D0h+var_320], 0
0x18003facc  jz      short loc_18003FAE5
0x18003face  lea     rcx, [rbp+2D0h+var_330]
  ... truncated ...
```
