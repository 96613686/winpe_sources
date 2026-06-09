# MmpcRetrieveResourceUrl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180077c20`
- end: `0x180077ff5`
- name: `?MmpcRetrieveResourceUrl@@YAJPEBG0000PEAPEAG@Z`
- size: `981`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074fa0`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180051ea0`
- `0x180051f08`
- `0x180057c6c`
- `0x180058420`
- `0x18005b638`
- `0x18005b914`
- `0x18005c7c0`
- `0x18005cabc`
- `0x1800748b4`
- `0x180077c20`
- `0x1800790f8`
- `0x1800b22a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077f67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077f67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077d50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077df4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077d50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077df4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180077fbd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180077fbd`
- `RPCRT4!UuidFromStringW` at `0x180077e63`
- `RPCRT4!UuidFromStringW` at `0x180077e63`
- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x180077ea9`
- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x180077ea9`
- `dmEnrollEngine!MmpcDiscoverEndpoint` at `0x180077efd`
- `dmEnrollEngine!MmpcDiscoverEndpoint` at `0x180077efd`

## string_xrefs

- `0x180077cdc`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077e18`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077e7a`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077fc9`: `Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x180077fd0`: `OSData\Software\Microsoft\Enrollments\%s\LinkedEnrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MmpcRetrieveResourceUrl(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  signed int MdmEnrollmentWithLinkedEnrollment; // ebx
  __int64 v11; // rdx
  LSTATUS ValueW; // eax
  PVOID v14; // rdi
  __int64 v15; // rdx
  LSTATUS v16; // eax
  RPC_STATUS EnrollmentEntDmId; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r8
  unsigned __int16 **hlocal_string; // rax
  unsigned __int16 *v21; // rcx
  char IsStateSeparationEnabled; // al
  unsigned __int16 *v23; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v26; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData[2]; // [rsp+50h] [rbp-B0h] BYREF
  UUID v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v34; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 *v37; // [rsp+A8h] [rbp-58h]
  int *v38; // [rsp+B0h] [rbp-50h]
  char v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v41; // [rsp+E8h] [rbp-18h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 StringUuid[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR SubKey[264]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  memset_0(&v30, 0, 0x40u);
  v30 = 1;
  hMem = 0;
  if ( dword_18010E368 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18010E368);
    if ( dword_18010E368 == -1 )
    {
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v23 = L"OSData\\Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
      if ( !IsStateSeparationEnabled )
        v23 = L"Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
      qword_18010E370 = v23;
      Init_thread_footer(&dword_18010E368);
    }
  }
  memset_0(StringUuid, 0, 0x4Eu);
  MdmEnrollmentWithLinkedEnrollment = DmFindMdmEnrollmentWithLinkedEnrollment(a3, StringUuid);
  if ( MdmEnrollmentWithLinkedEnrollment < 0 )
  {
    v11 = 1004;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)MdmEnrollmentWithLinkedEnrollment,
      pdwType);
    return (unsigned int)MdmEnrollmentWithLinkedEnrollment;
  }
  v26 = 1;
  pcbData = 0;
  MdmEnrollmentWithLinkedEnrollment = StringCchPrintfW(SubKey, 0x104u, qword_18010E370, StringUuid);
  if ( MdmEnrollmentWithLinkedEnrollment < 0 )
  {
    v11 = 1012;
    goto LABEL_4;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"DiscoveryEndpoint", 2u, &v26, 0, &pcbData);
  MdmEnrollmentWithLinkedEnrollment = ValueW;
  if ( ValueW > 0 )
    MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)ValueW | 0x80070000;
  if ( MdmEnrollmentWithLinkedEnrollment < 0 )
  {
    v11 = 1023;
    goto LABEL_4;
  }
  if ( pcbData <= 0x104 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pvData,
      0,
      pcbData);
    v14 = pvData[0];
    if ( !pvData[0] )
    {
      MdmEnrollmentWithLinkedEnrollment = -2147024882;
      v15 = 1033;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
        (const char *)(unsigned int)MdmEnrollmentWithLinkedEnrollment,
        pdwType);
LABEL_33:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pvData);
      return (unsigned int)MdmEnrollmentWithLinkedEnrollment;
    }
    v16 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"DiscoveryEndpoint", 2u, &v26, pvData[0], &pcbData);
    MdmEnrollmentWithLinkedEnrollment = v16;
    if ( v16 > 0 )
      MdmEnrollmentWithLinkedEnrollment = (unsigned __int16)v16 | 0x80070000;
    if ( MdmEnrollmentWithLinkedEnrollment < 0 )
    {
      v15 = 1044;
      goto LABEL_21;
    }
    pvData[0] = 0;
    hMem = v14;
    v38 = &v30;
    v39 = 1;
    v27 = 0;
    Uuid = 0;
    EnrollmentEntDmId = UuidFromStringW(StringUuid, &Uuid);
    MdmEnrollmentWithLinkedEnrollment = EnrollmentEntDmId;
    if ( EnrollmentEntDmId >= 0 )
    {
      v29 = Uuid;
      EnrollmentEntDmId = GetEnrollmentEntDmId(&v29, &v27);
      MdmEnrollmentWithLinkedEnrollment = EnrollmentEntDmId;
      if ( EnrollmentEntDmId >= 0 )
      {
        v32 = 0;
        v31 = a1;
        v34 = a5;
        v35 = a2;
        v37 = a4;
        v36 = v27;
        memset_0(v40, 0, 0x40u);
        MdmEnrollmentWithLinkedEnrollment = MmpcDiscoverEndpoint(&v30, v40);
        if ( MdmEnrollmentWithLinkedEnrollment < 0 )
        {
          if ( v42 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer();
        }
        else
        {
          hlocal_string = (unsigned __int16 **)wil::make_hlocal_string((wil *)&v29, v41, v19);
          v21 = *hlocal_string;
          *hlocal_string = 0;
          *a6 = v21;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
          memset_0(v40, 0, 0x40u);
        }
        goto LABEL_32;
      }
      v18 = 1053;
    }
    else
    {
      v18 = 1052;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)EnrollmentEntDmId,
      pdwType);
LABEL_32:
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v27);
    LocalFree(hMem);
    goto LABEL_33;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer();
  return 2147942487LL;
}

```

## disassembly

```asm
0x180077c20  push    rbp
0x180077c22  push    rbx
0x180077c23  push    rsi
0x180077c24  push    rdi
0x180077c25  push    r12
0x180077c27  push    r13
0x180077c29  push    r14
0x180077c2b  push    r15
0x180077c2d  lea     rbp, [rsp-288h]
0x180077c35  sub     rsp, 388h
0x180077c3c  mov     rax, cs:__security_cookie
0x180077c43  xor     rax, rsp
0x180077c46  mov     [rbp+2C0h+var_50], rax
0x180077c4d  mov     r12, r9
0x180077c50  mov     rbx, r8
0x180077c53  mov     r15, rdx
0x180077c56  mov     r14, rcx
0x180077c59  mov     r13, [rbp+2C0h+arg_20]
0x180077c60  mov     rsi, [rbp+2C0h+arg_28]
0x180077c67  xor     edx, edx; Val
0x180077c69  lea     r8d, [rdx+40h]; Size
0x180077c6d  lea     rcx, [rsp+3C0h+var_350]; void *
0x180077c72  call    memset_0
0x180077c77  mov     [rsp+3C0h+var_350], 1
0x180077c7f  xor     edi, edi
0x180077c81  mov     [rbp+2C0h+hMem], rdi
0x180077c85  mov     ecx, cs:_tls_index
0x180077c8b  mov     rax, gs:58h
0x180077c94  mov     edx, 4
0x180077c99  mov     rax, [rax+rcx*8]
0x180077c9d  mov     ecx, [rdx+rax]
0x180077ca0  cmp     cs:dword_18010E368, ecx
0x180077ca6  jg      loc_180077FA4
0x180077cac  xor     edx, edx; Val
0x180077cae  lea     r8d, [rdx+4Eh]; Size
0x180077cb2  lea     rcx, [rbp+2C0h+StringUuid]; void *
0x180077cb6  call    memset_0
0x180077cbb  lea     rdx, [rbp+2C0h+StringUuid]; unsigned __int16 *
0x180077cbf  mov     rcx, rbx; unsigned __int16 *
0x180077cc2  call    ?DmFindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z; DmFindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)
0x180077cc7  mov     ebx, eax
0x180077cc9  test    eax, eax
0x180077ccb  jns     short loc_180077CED
0x180077ccd  mov     edx, 3ECh; void *
0x180077cd2  mov     rcx, [rbp+2C8h]; this
0x180077cd9  mov     r9d, ebx; char *
0x180077cdc  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077ce8  jmp     loc_180077F7E
0x180077ced  mov     [rsp+3C0h+var_37C], 1
0x180077cf5  mov     [rsp+3C0h+var_380], edi
0x180077cf9  lea     r9, [rbp+2C0h+StringUuid]
0x180077cfd  mov     r8, cs:qword_18010E370; unsigned __int16 *
0x180077d04  mov     edx, 104h; unsigned __int64
0x180077d09  lea     rcx, [rbp+2C0h+SubKey]; unsigned __int16 *
0x180077d0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077d12  mov     ebx, eax
0x180077d14  test    eax, eax
0x180077d16  jns     short loc_180077D1F
0x180077d18  mov     edx, 3F4h
0x180077d1d  jmp     short loc_180077CD2
0x180077d1f  lea     rax, [rsp+3C0h+var_380]
0x180077d24  mov     [rsp+3C0h+pcbData], rax; pcbData
0x180077d29  mov     [rsp+3C0h+pvData], rdi; pvData
0x180077d2e  lea     rax, [rsp+3C0h+var_37C]
0x180077d33  mov     [rsp+3C0h+pdwType], rax; pdwType
0x180077d38  mov     r9d, 2; dwFlags
0x180077d3e  lea     r8, aDiscoveryendpo; "DiscoveryEndpoint"
0x180077d45  lea     rdx, [rbp+2C0h+SubKey]; lpSubKey
0x180077d49  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180077d50  call    cs:__imp_RegGetValueW
0x180077d57  nop     dword ptr [rax+rax+00h]
0x180077d5c  mov     ebx, eax
0x180077d5e  test    eax, eax
0x180077d60  jle     short loc_180077D6B
0x180077d62  movzx   ebx, ax
0x180077d65  or      ebx, 80070000h
0x180077d6b  test    ebx, ebx
0x180077d6d  jns     short loc_180077D79
0x180077d6f  mov     edx, 3FFh
0x180077d74  jmp     loc_180077CD2
0x180077d79  cmp     [rsp+3C0h+var_380], 104h
0x180077d81  jbe     short loc_180077D9B
0x180077d83  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180077d8a  jz      short loc_180077D91
0x180077d8c  call    McTemplateU0d_EventWriteTransfer
0x180077d91  mov     eax, 80070057h
0x180077d96  jmp     loc_180077F80
0x180077d9b  mov     r8d, [rsp+3C0h+var_380]
0x180077da0  xor     edx, edx
0x180077da2  lea     rcx, [rsp+3C0h+var_370]
0x180077da7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180077dac  nop
0x180077dad  mov     rdi, [rsp+3C0h+var_370]
0x180077db2  test    rdi, rdi
0x180077db5  jnz     short loc_180077DC3
0x180077db7  mov     ebx, 8007000Eh
0x180077dbc  mov     edx, 409h
0x180077dc1  jmp     short loc_180077E18
0x180077dc3  lea     rax, [rsp+3C0h+var_380]
0x180077dc8  mov     [rsp+3C0h+pcbData], rax; pcbData
0x180077dcd  mov     [rsp+3C0h+pvData], rdi; pvData
0x180077dd2  lea     rax, [rsp+3C0h+var_37C]
0x180077dd7  mov     [rsp+3C0h+pdwType], rax; int
0x180077ddc  mov     r9d, 2; dwFlags
0x180077de2  lea     r8, aDiscoveryendpo; "DiscoveryEndpoint"
0x180077de9  lea     rdx, [rbp+2C0h+SubKey]; lpSubKey
0x180077ded  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180077df4  call    cs:__imp_RegGetValueW
0x180077dfb  nop     dword ptr [rax+rax+00h]
0x180077e00  mov     ebx, eax
0x180077e02  test    eax, eax
0x180077e04  jle     short loc_180077E0F
0x180077e06  movzx   ebx, ax
0x180077e09  or      ebx, 80070000h
0x180077e0f  test    ebx, ebx
0x180077e11  jns     short loc_180077E33
0x180077e13  mov     edx, 414h; void *
0x180077e18  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077e1f  mov     r9d, ebx; char *
0x180077e22  mov     rcx, [rbp+2C8h]; this
0x180077e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077e2e  jmp     loc_180077F74
0x180077e33  mov     [rsp+3C0h+var_370], 0
0x180077e3c  mov     [rbp+2C0h+hMem], rdi
0x180077e40  lea     rax, [rsp+3C0h+var_350]
0x180077e45  mov     [rbp+2C0h+var_310], rax
0x180077e49  mov     [rbp+2C0h+var_308], 1
0x180077e4d  xor     edi, edi
0x180077e4f  mov     [rsp+3C0h+var_378], rdi
0x180077e54  xorps   xmm0, xmm0
0x180077e57  movups  xmmword ptr [rbp+2C0h+Uuid.Data1], xmm0
0x180077e5b  lea     rdx, [rbp+2C0h+Uuid]; Uuid
0x180077e5f  lea     rcx, [rbp+2C0h+StringUuid]; StringUuid
0x180077e63  call    cs:__imp_UuidFromStringW
0x180077e6a  nop     dword ptr [rax+rax+00h]
0x180077e6f  mov     ebx, eax
0x180077e71  test    eax, eax
0x180077e73  jns     short loc_180077E95
0x180077e75  mov     edx, 41Ch; void *
0x180077e7a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077e81  mov     r9d, eax; char *
0x180077e84  mov     rcx, [rbp+2C8h]; this
0x180077e8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077e90  jmp     loc_180077F58
0x180077e95  movaps  xmm0, xmmword ptr [rbp+2C0h+Uuid.Data1]
0x180077e99  movdqa  [rsp+3C0h+var_360], xmm0
0x180077e9f  lea     rdx, [rsp+3C0h+var_378]
0x180077ea4  lea     rcx, [rsp+3C0h+var_360]
0x180077ea9  call    cs:__imp_GetEnrollmentEntDmId
0x180077eb0  nop     dword ptr [rax+rax+00h]
0x180077eb5  mov     ebx, eax
0x180077eb7  test    eax, eax
0x180077eb9  jns     short loc_180077EC2
0x180077ebb  mov     edx, 41Dh
0x180077ec0  jmp     short loc_180077E7A
0x180077ec2  mov     [rbp+2C0h+var_340], rdi
0x180077ec6  mov     [rsp+3C0h+var_348], r14
0x180077ecb  mov     [rbp+2C0h+var_330], r13
0x180077ecf  mov     [rbp+2C0h+var_328], r15
0x180077ed3  mov     [rbp+2C0h+var_318], r12
0x180077ed7  mov     rax, [rsp+3C0h+var_378]
0x180077edc  mov     [rbp+2C0h+var_320], rax
0x180077ee0  mov     r14d, 40h ; '@'
0x180077ee6  mov     r8d, r14d; Size
0x180077ee9  xor     edx, edx; Val
0x180077eeb  lea     rcx, [rbp+2C0h+var_300]; void *
0x180077eef  call    memset_0
0x180077ef4  lea     rdx, [rbp+2C0h+var_300]
0x180077ef8  lea     rcx, [rsp+3C0h+var_350]
0x180077efd  call    cs:__imp_MmpcDiscoverEndpoint
0x180077f04  nop     dword ptr [rax+rax+00h]
0x180077f09  mov     ebx, eax
0x180077f0b  test    eax, eax
0x180077f0d  js      short loc_180077F40
0x180077f0f  mov     rdx, [rbp+2C0h+var_2D8]; unsigned __int16 *
0x180077f13  lea     rcx, [rsp+3C0h+var_360]; this
0x180077f18  call    ?make_hlocal_string@wil@@YA@PEBG_K@Z; wil::make_hlocal_string(ushort const *,unsigned __int64)
0x180077f1d  mov     rcx, [rax]
0x180077f20  mov     [rax], rdi
0x180077f23  mov     [rsi], rcx
0x180077f26  lea     rcx, [rsp+3C0h+var_360]
0x180077f2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180077f30  mov     r8d, r14d; Size
0x180077f33  xor     edx, edx; Val
0x180077f35  lea     rcx, [rbp+2C0h+var_300]; void *
0x180077f39  call    memset_0
0x180077f3e  jmp     short loc_180077F58
0x180077f40  mov     r8, [rbp+2C0h+var_2C8]
0x180077f44  test    r8, r8
0x180077f47  jz      short loc_180077F58
0x180077f49  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x180077f50  jz      short loc_180077F58
0x180077f52  call    McTemplateU0z_EventWriteTransfer
0x180077f57  nop
0x180077f58  lea     rcx, [rsp+3C0h+var_378]
0x180077f5d  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077f62  nop
0x180077f63  mov     rcx, [rbp+2C0h+hMem]; hMem
0x180077f67  call    cs:__imp_LocalFree
0x180077f6e  nop     dword ptr [rax+rax+00h]
0x180077f73  nop
0x180077f74  lea     rcx, [rsp+3C0h+var_370]
0x180077f79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180077f7e  mov     eax, ebx
0x180077f80  mov     rcx, [rbp+2C0h+var_50]
0x180077f87  xor     rcx, rsp; StackCookie
0x180077f8a  call    __security_check_cookie
0x180077f8f  add     rsp, 388h
0x180077f96  pop     r15
0x180077f98  pop     r14
0x180077f9a  pop     r13
0x180077f9c  pop     r12
0x180077f9e  pop     rdi
0x180077f9f  pop     rsi
0x180077fa0  pop     rbx
0x180077fa1  pop     rbp
0x180077fa2  retn
0x180077fa4  lea     rcx, dword_18010E368
0x180077fab  call    _Init_thread_header
0x180077fb0  cmp     cs:dword_18010E368, 0FFFFFFFFh
0x180077fb7  jnz     loc_180077CAC
0x180077fbd  call    cs:__imp_RtlIsStateSeparationEnabled
0x180077fc4  nop     dword ptr [rax+rax+00h]
0x180077fc9  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments\\%s\\L"...
0x180077fd0  lea     rdx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\Enrollment"...
0x180077fd7  test    al, al
0x180077fd9  cmovz   rdx, r8
0x180077fdd  mov     cs:qword_18010E370, rdx
0x180077fe4  lea     rcx, dword_18010E368
0x180077feb  call    _Init_thread_footer
0x180077ff0  jmp     loc_180077CAC
```
