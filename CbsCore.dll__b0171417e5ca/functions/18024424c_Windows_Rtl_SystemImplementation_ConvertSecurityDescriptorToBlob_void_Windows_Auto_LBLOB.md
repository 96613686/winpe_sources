# Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob(void *,Windows::Auto<_LBLOB> *)

- ea: `0x18024424c`
- end: `0x18024447f`
- name: `?ConvertSecurityDescriptorToBlob@SystemImplementation@Rtl@Windows@@YAJPEAXPEAV?$Auto@U_LBLOB@@@3@@Z`
- size: `563`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18022ace0`
- `0x18022bd10`
- `0x180245280`
- `0x180245670`
- `0x180246c80`

## callees

- `0x180019bdc`
- `0x18003ec0c`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800ef360`
- `0x18024424c`
- `0x1802cf7cc`

## import_xrefs

- `ntdll!RtlMakeSelfRelativeSD` at `0x18024432d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1802443c8`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18024432d`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1802443c8`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180244297`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180244297`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1802442e7`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1802442e7`

## string_xrefs

- `0x1802443fa`: `RtlMakeSelfRelativeSD( SecurityDescriptor, TempBlob.Buffer, &cbSecurityDescriptor)`
- `0x1802442be`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x180244366`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x1802443a5`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x1802443ef`: `Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob`
- `0x1802442c9`: `RtlGetControlSecurityDescriptor(SecurityDescriptor, &Control, &Revision)`
- `0x1802443b0`: `RtlAllocateLBlob( cbSecurityDescriptor, TempBlob.GetMutablePointer())`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob(void *Src, __int128 *a2)
{
  NTSTATUS ControlSecurityDescriptor; // eax
  _QWORD *v5; // rdx
  __int64 v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  __int128 v10; // xmm2
  void *v11; // xmm3_8
  PSECURITY_DESCRIPTOR v12; // xmm1_8
  __int128 v13; // [rsp+20h] [rbp-69h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSD; // [rsp+30h] [rbp-59h]
  _QWORD v15[4]; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v16[4]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v17[4]; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v18[4]; // [rsp+98h] [rbp+Fh] BYREF
  WORD Control[2]; // [rsp+B8h] [rbp+2Fh] BYREF
  int v20; // [rsp+BCh] [rbp+33h] BYREF
  ULONG BufferLength; // [rsp+C0h] [rbp+37h] BYREF
  ULONG Revision; // [rsp+C4h] [rbp+3Bh] BYREF

  v20 = 0;
  SelfRelativeSD = 0;
  Control[0] = 0;
  Revision = 0;
  v13 = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(Src, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v15[2] = 32;
    v15[0] = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
    v5 = v15;
    v15[1] = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
    v15[3] = "RtlGetControlSecurityDescriptor(SecurityDescriptor, &Control, &Revision)";
LABEL_14:
    v7 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v20,
           v5,
           (unsigned int)ControlSecurityDescriptor);
    goto LABEL_15;
  }
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(Src, 0, &BufferLength);
    if ( ControlSecurityDescriptor != -2147483643 && ControlSecurityDescriptor != -1073741789 )
    {
      if ( ControlSecurityDescriptor >= 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18024447ELL);
      }
      v16[2] = 60;
      v16[0] = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
      v5 = v16;
      v16[3] = 0;
      v16[1] = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
      goto LABEL_14;
    }
    ControlSecurityDescriptor = RtlAllocateLBlob(BufferLength, &v13);
    if ( ControlSecurityDescriptor < 0 )
    {
      v17[2] = 65;
      v17[0] = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
      v5 = v17;
      v17[1] = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
      v17[3] = "RtlAllocateLBlob( cbSecurityDescriptor, TempBlob.GetMutablePointer())";
      goto LABEL_14;
    }
    ControlSecurityDescriptor = RtlMakeSelfRelativeSD(Src, SelfRelativeSD, &BufferLength);
    if ( ControlSecurityDescriptor < 0 )
    {
      v18[2] = 70;
      v18[0] = "onecore\\base\\wcp\\sil\\fs_queued.cpp";
      v5 = v18;
      v18[1] = "Windows::Rtl::SystemImplementation::ConvertSecurityDescriptorToBlob";
      v18[3] = "RtlMakeSelfRelativeSD( SecurityDescriptor, TempBlob.Buffer, &cbSecurityDescriptor)";
      goto LABEL_14;
    }
    *(_QWORD *)&v13 = BufferLength;
  }
  else
  {
    v6 = RtlLengthSecurityDescriptor(Src);
    v7 = RtlAllocateLBlob(v6, &v13);
    if ( v7 < 0 )
    {
LABEL_15:
      v8 = v7;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v13);
      return v8;
    }
    memcpy_0(SelfRelativeSD, Src, (unsigned int)v6);
    *(_QWORD *)&v13 = v6;
  }
  v10 = *a2;
  v11 = (void *)*((_QWORD *)a2 + 2);
  v12 = SelfRelativeSD;
  *a2 = v13;
  *((_QWORD *)a2 + 2) = v12;
  v13 = v10;
  SelfRelativeSD = v11;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v13);
  return 0;
}

```

## disassembly

```asm
0x18024424c  mov     [rsp-8+arg_10], rbx
0x180244251  push    rbp
0x180244252  push    rsi
0x180244253  push    rdi
0x180244254  lea     rbp, [rsp-47h]
0x180244259  sub     rsp, 0D0h
0x180244260  mov     rax, cs:__security_cookie
0x180244267  xor     rax, rsp
0x18024426a  mov     [rbp+57h+var_18], rax
0x18024426e  xor     eax, eax
0x180244270  mov     [rbp+57h+var_24], 0
0x180244277  mov     rsi, rdx
0x18024427a  mov     [rbp+57h+SelfRelativeSD], rax
0x18024427e  xorps   xmm0, xmm0
0x180244281  mov     [rbp+57h+Control], ax
0x180244285  lea     rdx, [rbp+57h+Control]; Control
0x180244289  mov     [rbp+57h+Revision], eax
0x18024428c  lea     r8, [rbp+57h+Revision]; Revision
0x180244290  mov     rbx, rcx
0x180244293  movups  [rbp+57h+var_C0], xmm0
0x180244297  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18024429e  nop     dword ptr [rax+rax+00h]
0x1802442a3  test    eax, eax
0x1802442a5  jns     short loc_1802442D9
0x1802442a7  lea     rcx, aOnecoreBaseWcp_40; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x1802442ae  mov     [rbp+57h+var_98], 20h ; ' '
0x1802442b6  mov     [rbp+57h+var_A8], rcx
0x1802442ba  lea     rdx, [rbp+57h+var_A8]
0x1802442be  lea     rcx, aWindowsRtlSyst_240; "Windows::Rtl::SystemImplementation::Con"...
0x1802442c5  mov     [rbp+57h+var_A0], rcx
0x1802442c9  lea     rcx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(Securit"...
0x1802442d0  mov     [rbp+57h+var_90], rcx
0x1802442d4  jmp     loc_180244405
0x1802442d9  mov     eax, 8000h
0x1802442de  mov     rcx, rbx; AbsoluteSD
0x1802442e1  test    [rbp+57h+Control], ax
0x1802442e5  jz      short loc_180244320
0x1802442e7  call    cs:__imp_RtlLengthSecurityDescriptor
0x1802442ee  nop     dword ptr [rax+rax+00h]
0x1802442f3  mov     ecx, eax
0x1802442f5  lea     rdx, [rbp+57h+var_C0]
0x1802442f9  mov     edi, eax
0x1802442fb  call    RtlAllocateLBlob
0x180244300  test    eax, eax
0x180244302  js      loc_180244411
0x180244308  mov     rcx, [rbp+57h+SelfRelativeSD]; void *
0x18024430c  mov     r8d, edi; Size
0x18024430f  mov     rdx, rbx; Src
0x180244312  call    memcpy_0
0x180244317  mov     qword ptr [rbp+57h+var_C0], rdi
0x18024431b  jmp     loc_180244427
0x180244320  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x180244324  mov     [rbp+57h+BufferLength], 0
0x18024432b  xor     edx, edx; SelfRelativeSD
0x18024432d  call    cs:__imp_RtlMakeSelfRelativeSD
0x180244334  nop     dword ptr [rax+rax+00h]
0x180244339  cmp     eax, 80000005h
0x18024433e  jz      short loc_18024437E
0x180244340  cmp     eax, 0C0000023h
0x180244345  jz      short loc_18024437E
0x180244347  test    eax, eax
0x180244349  jns     loc_180244474
0x18024434f  lea     rcx, aOnecoreBaseWcp_40; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x180244356  mov     [rbp+57h+var_78], 3Ch ; '<'
0x18024435e  mov     [rbp+57h+var_88], rcx
0x180244362  lea     rdx, [rbp+57h+var_88]
0x180244366  lea     rcx, aWindowsRtlSyst_240; "Windows::Rtl::SystemImplementation::Con"...
0x18024436d  mov     [rbp+57h+var_70], 0
0x180244375  mov     [rbp+57h+var_80], rcx
0x180244379  jmp     loc_180244405
0x18024437e  mov     ecx, [rbp+57h+BufferLength]
0x180244381  lea     rdx, [rbp+57h+var_C0]
0x180244385  call    RtlAllocateLBlob
0x18024438a  test    eax, eax
0x18024438c  jns     short loc_1802443BD
0x18024438e  lea     rcx, aOnecoreBaseWcp_40; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x180244395  mov     [rbp+57h+var_58], 41h ; 'A'
0x18024439d  mov     [rbp+57h+var_68], rcx
0x1802443a1  lea     rdx, [rbp+57h+var_68]
0x1802443a5  lea     rcx, aWindowsRtlSyst_240; "Windows::Rtl::SystemImplementation::Con"...
0x1802443ac  mov     [rbp+57h+var_60], rcx
0x1802443b0  lea     rcx, aRtlallocatelbl_1; "RtlAllocateLBlob( cbSecurityDescriptor,"...
0x1802443b7  mov     [rbp+57h+var_50], rcx
0x1802443bb  jmp     short loc_180244405
0x1802443bd  mov     rdx, [rbp+57h+SelfRelativeSD]; SelfRelativeSD
0x1802443c1  lea     r8, [rbp+57h+BufferLength]; BufferLength
0x1802443c5  mov     rcx, rbx; AbsoluteSD
0x1802443c8  call    cs:__imp_RtlMakeSelfRelativeSD
0x1802443cf  nop     dword ptr [rax+rax+00h]
0x1802443d4  test    eax, eax
0x1802443d6  jns     short loc_180244420
0x1802443d8  lea     rcx, aOnecoreBaseWcp_40; "onecore\\base\\wcp\\sil\\fs_queued.cpp"
0x1802443df  mov     [rbp+57h+var_38], 46h ; 'F'
0x1802443e7  mov     [rbp+57h+var_48], rcx
0x1802443eb  lea     rdx, [rbp+57h+var_48]
0x1802443ef  lea     rcx, aWindowsRtlSyst_240; "Windows::Rtl::SystemImplementation::Con"...
0x1802443f6  mov     [rbp+57h+var_40], rcx
0x1802443fa  lea     rcx, aRtlmakeselfrel_0; "RtlMakeSelfRelativeSD( SecurityDescript"...
0x180244401  mov     [rbp+57h+var_30], rcx
0x180244405  mov     r8d, eax
0x180244408  lea     rcx, [rbp+57h+var_24]
0x18024440c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180244411  lea     rcx, [rbp+57h+var_C0]
0x180244415  mov     ebx, eax
0x180244417  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18024441c  mov     eax, ebx
0x18024441e  jmp     short loc_180244454
0x180244420  mov     eax, [rbp+57h+BufferLength]
0x180244423  mov     qword ptr [rbp+57h+var_C0], rax
0x180244427  movups  xmm2, xmmword ptr [rsi]
0x18024442a  lea     rcx, [rbp+57h+var_C0]
0x18024442e  movsd   xmm3, qword ptr [rsi+10h]
0x180244433  movups  xmm0, [rbp+57h+var_C0]
0x180244437  movsd   xmm1, [rbp+57h+SelfRelativeSD]
0x18024443c  movups  xmmword ptr [rsi], xmm0
0x18024443f  movsd   qword ptr [rsi+10h], xmm1
0x180244444  movups  [rbp+57h+var_C0], xmm2
0x180244448  movsd   [rbp+57h+SelfRelativeSD], xmm3
0x18024444d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180244452  xor     eax, eax
0x180244454  mov     rcx, [rbp+57h+var_18]
0x180244458  xor     rcx, rsp; StackCookie
0x18024445b  call    __security_check_cookie
0x180244460  mov     rbx, [rsp+0E0h+arg_10]
0x180244468  add     rsp, 0D0h
0x18024446f  pop     rdi
0x180244470  pop     rsi
0x180244471  pop     rbp
0x180244472  retn
0x180244474  mov     ecx, 0C00000E5h; int
0x180244479  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
