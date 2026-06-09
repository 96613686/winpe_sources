# Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob(void *,Windows::Auto<_LBLOB> *)

- ea: `0x180152eac`
- end: `0x1801530fb`
- name: `?ConvertSecurityDescriptorToBlob@SystemImplementation@Rtl@Windows@@YAJPEAXPEAV?$Auto@U_LBLOB@@@3@@Z`
- size: `591`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSD)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180135e00`
- `0x180136ef0`
- `0x180154004`
- `0x180154420`
- `0x180155c50`

## callees

- `0x1800031d0`
- `0x18000693e`
- `0x18000aedc`
- `0x1800497c0`
- `0x18004be10`
- `0x18004d970`
- `0x180152eac`

## import_xrefs

- `ntdll!RtlMakeSelfRelativeSD` at `0x180152fab`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180153045`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180152fab`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180153045`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180152ef1`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180152ef1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180152f54`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180152f54`

## string_xrefs

- `0x180153009`: `RtlAllocateLBlob( cbSecurityDescriptor, TempBlob.GetMutablePointer())`
- `0x18015306a`: `RtlMakeSelfRelativeSD( SecurityDescriptor, TempBlob.Buffer, &cbSecurityDescriptor)`
- `0x180152f2b`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x180153010`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x180153071`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x180152f03`: `RtlGetControlSecurityDescriptor(SecurityDescriptor, &Control, &Revision)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob(
        PSECURITY_DESCRIPTOR AbsoluteSD,
        __int64 a2)
{
  NTSTATUS ControlSecurityDescriptor; // ebx
  size_t v6; // rsi
  PSECURITY_DESCRIPTOR v7; // rbx
  NTSTATUS v8; // eax
  NTSTATUS v9; // edi
  __int64 v10; // rcx
  const char *v11; // [rsp+20h] [rbp-50h] BYREF
  const char *v12; // [rsp+28h] [rbp-48h]
  __int64 v13; // [rsp+30h] [rbp-40h]
  const char *v14; // [rsp+38h] [rbp-38h]
  __int128 v15; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSD; // [rsp+50h] [rbp-20h]
  WORD Control[2]; // [rsp+58h] [rbp-18h] BYREF
  ULONG BufferLength; // [rsp+5Ch] [rbp-14h] BYREF
  ULONG Revision; // [rsp+60h] [rbp-10h] BYREF

  SelfRelativeSD = 0;
  Control[0] = 0;
  Revision = 0;
  v15 = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(AbsoluteSD, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v13 = 32;
    v14 = "RtlGetControlSecurityDescriptor(SecurityDescriptor, &Control, &Revision)";
LABEL_3:
    v11 = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
    v12 = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
    RtlReportErrorOrigination(&v11, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  if ( (Control[0] & 0x8000u) != 0 )
  {
    v6 = RtlLengthSecurityDescriptor(AbsoluteSD);
    ControlSecurityDescriptor = RtlAllocateLBlob(v6, &v15);
    if ( ControlSecurityDescriptor < 0 )
      goto LABEL_7;
    v7 = SelfRelativeSD;
    memcpy_0(SelfRelativeSD, AbsoluteSD, v6);
    *(_QWORD *)&v15 = v6;
    goto LABEL_21;
  }
  BufferLength = 0;
  v8 = RtlMakeSelfRelativeSD(AbsoluteSD, 0, &BufferLength);
  ControlSecurityDescriptor = v8;
  if ( v8 != -2147483643 && v8 != -1073741789 )
  {
    if ( v8 >= 0 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1801530FALL);
    }
    v13 = 60;
    v14 = 0;
    goto LABEL_3;
  }
  ControlSecurityDescriptor = RtlAllocateLBlob(BufferLength, &v15);
  if ( ControlSecurityDescriptor < 0 )
  {
    v13 = 65;
    v11 = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
    v14 = "RtlAllocateLBlob( cbSecurityDescriptor, TempBlob.GetMutablePointer())";
    v12 = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
    RtlReportErrorOrigination(&v11, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
LABEL_7:
    if ( SelfRelativeSD )
      anonymous_namespace_::OurRtlFreeStringRoutine(SelfRelativeSD);
    return (unsigned int)ControlSecurityDescriptor;
  }
  v7 = SelfRelativeSD;
  v9 = RtlMakeSelfRelativeSD(AbsoluteSD, SelfRelativeSD, &BufferLength);
  if ( v9 >= 0 )
  {
    *(_QWORD *)&v15 = BufferLength;
LABEL_21:
    v10 = *(_QWORD *)(a2 + 16);
    *(_OWORD *)a2 = v15;
    *(_QWORD *)(a2 + 16) = v7;
    if ( v10 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v10);
    return 0;
  }
  v13 = 70;
  v11 = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
  v14 = "RtlMakeSelfRelativeSD( SecurityDescriptor, TempBlob.Buffer, &cbSecurityDescriptor)";
  v12 = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
  RtlReportErrorOrigination(&v11, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
  if ( v7 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180152eac  mov     [rsp-18h+arg_10], rbx
0x180152eb1  mov     [rsp-18h+arg_18], rsi
0x180152eb6  push    rbp
0x180152eb7  push    rdi
0x180152eb8  push    r14
0x180152eba  mov     rbp, rsp
0x180152ebd  sub     rsp, 70h
0x180152ec1  mov     rax, cs:__security_cookie
0x180152ec8  xor     rax, rsp
0x180152ecb  mov     [rbp+var_8], rax
0x180152ecf  xor     eax, eax
0x180152ed1  lea     r8, [rbp+Revision]; Revision
0x180152ed5  mov     r14, rdx
0x180152ed8  mov     [rbp+SelfRelativeSD], rax
0x180152edc  xorps   xmm0, xmm0
0x180152edf  mov     [rbp+Control], ax
0x180152ee3  lea     rdx, [rbp+Control]; Control
0x180152ee7  mov     [rbp+Revision], eax
0x180152eea  movups  [rbp+var_30], xmm0
0x180152eee  mov     rdi, rcx
0x180152ef1  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180152ef8  nop     dword ptr [rax+rax+00h]
0x180152efd  mov     ebx, eax
0x180152eff  test    eax, eax
0x180152f01  jns     short loc_180152F46
0x180152f03  lea     rax, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(Securit"...
0x180152f0a  mov     [rbp+var_40], 20h ; ' '
0x180152f12  mov     [rbp+var_38], rax
0x180152f16  lea     rcx, aOnecoreBaseWcp_35; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x180152f1d  mov     r8d, ebx
0x180152f20  mov     [rbp+var_50], rcx
0x180152f24  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180152f2b  lea     rcx, aWindowsRtlSyst_234; "Windows::Rtl::SystemImplementation::Con"...
0x180152f32  mov     [rbp+var_48], rcx
0x180152f36  lea     rcx, [rbp+var_50]
0x180152f3a  call    RtlReportErrorOrigination
0x180152f3f  mov     eax, ebx
0x180152f41  jmp     loc_1801530CE
0x180152f46  mov     eax, 8000h
0x180152f4b  mov     rcx, rdi; AbsoluteSD
0x180152f4e  test    [rbp+Control], ax
0x180152f52  jz      short loc_180152F9E
0x180152f54  call    cs:__imp_RtlLengthSecurityDescriptor
0x180152f5b  nop     dword ptr [rax+rax+00h]
0x180152f60  mov     ecx, eax
0x180152f62  lea     rdx, [rbp+var_30]
0x180152f66  mov     esi, eax
0x180152f68  call    RtlAllocateLBlob
0x180152f6d  mov     ebx, eax
0x180152f6f  test    eax, eax
0x180152f71  jns     short loc_180152F83
0x180152f73  mov     rcx, [rbp+SelfRelativeSD]
0x180152f77  test    rcx, rcx
0x180152f7a  jz      short loc_180152F3F
0x180152f7c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180152f81  jmp     short loc_180152F3F
0x180152f83  mov     rbx, [rbp+SelfRelativeSD]
0x180152f87  mov     r8, rsi; Size
0x180152f8a  mov     rcx, rbx; void *
0x180152f8d  mov     rdx, rdi; Src
0x180152f90  call    memcpy_0
0x180152f95  mov     qword ptr [rbp+var_30], rsi
0x180152f99  jmp     loc_1801530AB
0x180152f9e  lea     r8, [rbp+BufferLength]; BufferLength
0x180152fa2  mov     [rbp+BufferLength], 0
0x180152fa9  xor     edx, edx; SelfRelativeSD
0x180152fab  call    cs:__imp_RtlMakeSelfRelativeSD
0x180152fb2  nop     dword ptr [rax+rax+00h]
0x180152fb7  mov     ebx, eax
0x180152fb9  cmp     eax, 80000005h
0x180152fbe  jz      short loc_180152FE4
0x180152fc0  cmp     eax, 0C0000023h
0x180152fc5  jz      short loc_180152FE4
0x180152fc7  test    eax, eax
0x180152fc9  jns     loc_1801530F0
0x180152fcf  mov     [rbp+var_40], 3Ch ; '<'
0x180152fd7  mov     [rbp+var_38], 0
0x180152fdf  jmp     loc_180152F16
0x180152fe4  mov     ecx, [rbp+BufferLength]
0x180152fe7  lea     rdx, [rbp+var_30]
0x180152feb  call    RtlAllocateLBlob
0x180152ff0  mov     ebx, eax
0x180152ff2  test    eax, eax
0x180152ff4  jns     short loc_180153037
0x180152ff6  lea     rcx, aOnecoreBaseWcp_35; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x180152ffd  mov     [rbp+var_40], 41h ; 'A'
0x180153005  mov     [rbp+var_50], rcx
0x180153009  lea     rax, aRtlallocatelbl_1; "RtlAllocateLBlob( cbSecurityDescriptor,"...
0x180153010  lea     rcx, aWindowsRtlSyst_234; "Windows::Rtl::SystemImplementation::Con"...
0x180153017  mov     [rbp+var_38], rax
0x18015301b  mov     [rbp+var_48], rcx
0x18015301f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180153026  lea     rcx, [rbp+var_50]
0x18015302a  mov     r8d, ebx
0x18015302d  call    RtlReportErrorOrigination
0x180153032  jmp     loc_180152F73
0x180153037  mov     rbx, [rbp+SelfRelativeSD]
0x18015303b  lea     r8, [rbp+BufferLength]; BufferLength
0x18015303f  mov     rdx, rbx; SelfRelativeSD
0x180153042  mov     rcx, rdi; AbsoluteSD
0x180153045  call    cs:__imp_RtlMakeSelfRelativeSD
0x18015304c  nop     dword ptr [rax+rax+00h]
0x180153051  mov     edi, eax
0x180153053  test    eax, eax
0x180153055  jns     short loc_1801530A4
0x180153057  lea     rcx, aOnecoreBaseWcp_35; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x18015305e  mov     [rbp+var_40], 46h ; 'F'
0x180153066  mov     [rbp+var_50], rcx
0x18015306a  lea     rax, aRtlmakeselfrel_0; "RtlMakeSelfRelativeSD( SecurityDescript"...
0x180153071  lea     rcx, aWindowsRtlSyst_234; "Windows::Rtl::SystemImplementation::Con"...
0x180153078  mov     [rbp+var_38], rax
0x18015307c  mov     [rbp+var_48], rcx
0x180153080  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180153087  lea     rcx, [rbp+var_50]
0x18015308b  mov     r8d, edi
0x18015308e  call    RtlReportErrorOrigination
0x180153093  test    rbx, rbx
0x180153096  jz      short loc_1801530A0
0x180153098  mov     rcx, rbx
0x18015309b  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801530a0  mov     eax, edi
0x1801530a2  jmp     short loc_1801530CE
0x1801530a4  mov     eax, [rbp+BufferLength]
0x1801530a7  mov     qword ptr [rbp+var_30], rax
0x1801530ab  movsd   xmm2, qword ptr [r14+10h]
0x1801530b1  movups  xmm0, [rbp+var_30]
0x1801530b5  movq    rcx, xmm2
0x1801530ba  movups  xmmword ptr [r14], xmm0
0x1801530be  mov     [r14+10h], rbx
0x1801530c2  test    rcx, rcx
0x1801530c5  jz      short loc_1801530CC
0x1801530c7  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801530cc  xor     eax, eax
0x1801530ce  mov     rcx, [rbp+var_8]
0x1801530d2  xor     rcx, rsp; StackCookie
0x1801530d5  call    __security_check_cookie
0x1801530da  lea     r11, [rsp+70h+var_s0]
0x1801530df  mov     rbx, [r11+30h]
0x1801530e3  mov     rsi, [r11+38h]
0x1801530e7  mov     rsp, r11
0x1801530ea  pop     r14
0x1801530ec  pop     rdi
0x1801530ed  pop     rbp
0x1801530ee  retn
0x1801530f0  mov     ecx, 0C00000E5h; int
0x1801530f5  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
