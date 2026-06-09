# HNS::Service::Resource::PortResource::AllocateResource(void)

- ea: `0x1801cddb0`
- end: `0x1801ce34c`
- name: `?AllocateResource@PortResource@Resource@Service@HNS@@MEAA?AV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `1436`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x1801d1aa0`
- `0x1801d7870`

## callees

- `0x18005f0c0`
- `0x18005ffa0`
- `0x1800677fc`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x1800b5c7c`
- `0x1800b65d8`
- `0x1800d22b8`
- `0x1800d4834`
- `0x1800fbeb4`
- `0x18019dbb4`
- `0x1801cddb0`
- `0x1801cedf4`
- `0x18023d280`
- `0x18023d498`
- `0x18023d80c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ce231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ce231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ce229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ce229`
- `RPCRT4!UuidCreate` at `0x1801cdfc8`
- `RPCRT4!UuidCreate` at `0x1801ce163`
- `RPCRT4!UuidCreate` at `0x1801cdfc8`
- `RPCRT4!UuidCreate` at `0x1801ce163`

## string_xrefs

- `0x1801cddf1`: `HNS::Service::Resource::PortResource::AllocateResource`
- `0x1801ce302`: `HNS::Service::Resource::PortResource::AllocateResource`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall HNS::Service::Resource::PortResource::AllocateResource(__int64 a1, _QWORD *a2)
{
  char v3; // r12
  GUID v4; // xmm0
  char v5; // si
  GUID v6; // xmm0
  GUID v7; // xmm0
  UUID *p_Buf2; // r8
  GUID v9; // xmm0
  GUID v10; // xmm0
  GUID v11; // xmm0
  bool v12; // di
  __int64 FriendlyName; // rax
  char v14; // al
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rsi
  char *v17; // r14
  DWORD LastError; // ebx
  int v19; // esi
  int v20; // edi
  const unsigned __int16 *v21; // rbx
  __int64 v22; // rcx
  _QWORD *result; // rax
  int v24; // [rsp+28h] [rbp-61h]
  int v25[2]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v26; // [rsp+48h] [rbp-41h]
  UUID Buf1; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v28[2]; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int64 v29; // [rsp+78h] [rbp-11h]
  UUID Buf2; // [rsp+80h] [rbp-9h] BYREF
  __int64 v31; // [rsp+90h] [rbp+7h]

  v26 = a2;
  *(_QWORD *)&Buf1.Data1 = a2;
  v3 = 0;
  v25[1] = 0;
  HNSTraceProvider::TraceEnter("HNS::Service::Resource::PortResource::AllocateResource", 0xA0u);
  v25[0] = 2;
  Buf1 = *(UUID *)(a1 + 528);
  HNSObject::Set<unsigned long>(*(_QWORD *)(a1 + 552), a1 + 496, v25, *(unsigned int *)(a1 + 544));
  if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 1560), a1 + 1504) )
  {
    v4 = GUID_NULL;
  }
  else
  {
    HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), &Buf1, a1 + 1504);
    v4 = Buf1;
  }
  Buf1 = v4;
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    v5 = 0;
    if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 2096), a1 + 2040) )
    {
      v6 = GUID_NULL;
    }
    else
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 2096), &Buf1, a1 + 2040);
      v6 = Buf1;
    }
    Buf1 = v6;
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 2032), a1 + 1976) )
      {
        v9 = GUID_NULL;
      }
      else
      {
        HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 2032), v28, a1 + 1976);
        v9 = *(GUID *)v28;
      }
      *(GUID *)v28 = v9;
      if ( !memcmp_0(v28, &GUID_NULL, 0x10u) )
      {
        Buf1 = 0;
        UuidCreate(&Buf1);
        Buf2 = Buf1;
        *(_OWORD *)v28 = *(_OWORD *)(a1 + 1536);
        p_Buf2 = &Buf2;
      }
      else
      {
        if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 2032), a1 + 1976) )
        {
          v10 = GUID_NULL;
        }
        else
        {
          HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 2032), v28, a1 + 1976);
          v10 = *(GUID *)v28;
        }
        Buf1 = v10;
        *(_OWORD *)v28 = *(_OWORD *)(a1 + 1536);
        p_Buf2 = &Buf1;
      }
    }
    else
    {
      if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 2096), a1 + 2040) )
      {
        v7 = GUID_NULL;
      }
      else
      {
        HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 2096), &Buf1, a1 + 2040);
        v7 = Buf1;
      }
      *(GUID *)v28 = v7;
      Buf1 = *(UUID *)(a1 + 1536);
      p_Buf2 = (UUID *)v28;
    }
    HNSObject::Set<_GUID>(*(_QWORD *)(a1 + 1560), a1 + 1504, p_Buf2, *(unsigned int *)(a1 + 1552));
    if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 1624), a1 + 1568) )
    {
      v11 = GUID_NULL;
    }
    else
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1624), &Buf2, a1 + 1568);
      v11 = Buf2;
    }
    Buf2 = v11;
    HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), v28, a1 + 1504);
    if ( !memcmp_0(v28, &Buf2, 0x10u) )
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), &Buf1, a1 + 1504);
      Buf1.Data4[7] ^= 1u;
      Buf2 = *(UUID *)(a1 + 1536);
      HNSObject::Set<_GUID>(*(_QWORD *)(a1 + 1560), a1 + 1504, &Buf1, *(unsigned int *)(a1 + 1552));
    }
  }
  else
  {
    v5 = 1;
  }
  v12 = 1;
  if ( !(unsigned int)HNSObject::PropertyExists(*(_QWORD *)(a1 + 1496), a1 + 1440) )
  {
    HNSObject::Get<std::wstring>(*(_QWORD *)(a1 + 1496), &Buf2, a1 + 1440);
    v3 = 5;
    if ( v31 )
      v12 = 0;
  }
  if ( (v3 & 1) != 0 )
    std::wstring::~wstring(&Buf2);
  if ( v12 )
  {
    FriendlyName = HNS::Service::Resource::PortResource::GenerateFriendlyName(a1, v28);
    Buf2 = *(UUID *)(a1 + 1472);
    HNSObject::Set<std::wstring>(*(_QWORD *)(a1 + 1496), a1 + 1440, FriendlyName, *(unsigned int *)(a1 + 1488));
    std::wstring::~wstring(v28);
  }
  if ( !v5 )
  {
    HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), &Buf2, a1 + 1504);
    if ( SwitchHelper::SwitchPortExists((SwitchHelper *)(a1 + 2104), &Buf2) )
    {
      Buf1 = 0;
      UuidCreate(&Buf1);
      *(UUID *)v28 = Buf1;
      Buf2 = *(UUID *)(a1 + 1536);
      HNSObject::Set<_GUID>(*(_QWORD *)(a1 + 1560), a1 + 1504, v28, *(unsigned int *)(a1 + 1552));
    }
  }
  v14 = Property<unsigned char>::get(a1 + 1760);
  v15 = a1 + 1376;
  if ( v14 )
  {
    v25[0] = (unsigned __int8)Property<unsigned char>::get(v15);
    Buf1.Data1 = (unsigned __int8)Property<unsigned char>::get(a1 + 1824);
    HNSObject::Get<std::wstring>(*(_QWORD *)(a1 + 1496), v28, a1 + 1440);
    v16 = (const unsigned __int16 *)v28;
    if ( v29 > 7 )
      v16 = v28[0];
    HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), &Buf2, a1 + 1504);
    v17 = *(char **)(a1 + 2232);
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v17);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 2232) = 0;
    SwitchHelper::SwitchPortCreateWithHandle(
      (SwitchHelper *)(a1 + 2104),
      (void **)(a1 + 2232),
      &Buf2,
      v16,
      Buf1.Data1,
      v24,
      v25[0]);
  }
  else
  {
    v19 = (unsigned __int8)Property<unsigned char>::get(v15);
    v20 = (unsigned __int8)Property<unsigned char>::get(a1 + 1824);
    HNSObject::Get<std::wstring>(*(_QWORD *)(a1 + 1496), v28, a1 + 1440);
    v21 = (const unsigned __int16 *)v28;
    if ( v29 > 7 )
      v21 = v28[0];
    HNSObject::Get<_GUID>(*(_QWORD *)(a1 + 1560), &Buf2, a1 + 1504);
    SwitchHelper::SwitchPortCreate((SwitchHelper *)(a1 + 2104), &Buf2, v21, v20, 0, v19);
  }
  std::wstring::~wstring(v28);
  Buf1.Data1 = 3;
  Buf2 = *(UUID *)(a1 + 528);
  HNSObject::Set<unsigned long>(*(_QWORD *)(a1 + 552), a1 + 496, &Buf1, *(unsigned int *)(a1 + 544));
  HNSTraceProvider::TraceSuccess("HNS::Service::Resource::PortResource::AllocateResource", 0xEFu);
  v22 = *(_QWORD *)(a1 + 944);
  result = v26;
  *v26 = v22;
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 16));
  return result;
}

```

## disassembly

```asm
0x1801cddb0  mov     [rsp-8+arg_10], rbx
0x1801cddb5  push    rbp
0x1801cddb6  push    rsi
0x1801cddb7  push    rdi
0x1801cddb8  push    r12
0x1801cddba  push    r13
0x1801cddbc  push    r14
0x1801cddbe  push    r15
0x1801cddc0  lea     rbp, [rsp-27h]
0x1801cddc5  sub     rsp, 0B0h
0x1801cddcc  mov     rax, cs:__security_cookie
0x1801cddd3  xor     rax, rsp
0x1801cddd6  mov     [rbp+57h+var_40], rax
0x1801cddda  mov     [rbp+57h+var_98], rdx
0x1801cddde  mov     r15, rcx
0x1801cdde1  mov     qword ptr [rbp+57h+Buf1], rdx
0x1801cdde5  xor     r12d, r12d
0x1801cdde8  mov     [rbp+57h+var_9C], r12d
0x1801cddec  mov     edx, 0A0h; unsigned int
0x1801cddf1  lea     rcx, aHnsServiceReso_49; "HNS::Service::Resource::PortResource::A"...
0x1801cddf8  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801cddfd  mov     [rbp+57h+var_A0], 2
0x1801cde04  lea     r13, [r15+1F0h]
0x1801cde0b  movups  xmm0, xmmword ptr [r13+20h]
0x1801cde10  movdqu  [rbp+57h+Buf1], xmm0
0x1801cde15  lea     rax, [rbp+57h+Buf1]
0x1801cde19  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1801cde1e  mov     r9d, [r13+30h]
0x1801cde22  lea     r8, [rbp+57h+var_A0]
0x1801cde26  mov     rdx, r13
0x1801cde29  mov     rcx, [r13+38h]
0x1801cde2d  call    ??$Set@K@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKKU_GUID@@@Z; HNSObject::Set<ulong>(std::wstring const &,ulong const &,ulong,_GUID)
0x1801cde32  nop
0x1801cde33  lea     r14, [r15+5E0h]
0x1801cde3a  mov     rdx, r14
0x1801cde3d  mov     rcx, [r14+38h]
0x1801cde41  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801cde46  test    eax, eax
0x1801cde48  jnz     short loc_1801CDE60
0x1801cde4a  mov     r8, r14
0x1801cde4d  lea     rdx, [rbp+57h+Buf1]
0x1801cde51  mov     rcx, [r14+38h]
0x1801cde55  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801cde5a  movaps  xmm0, [rbp+57h+Buf1]
0x1801cde5e  jmp     short loc_1801CDE67
0x1801cde60  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801cde67  movdqa  [rbp+57h+Buf1], xmm0
0x1801cde6c  mov     r8d, 10h; Size
0x1801cde72  lea     rdi, GUID_NULL
0x1801cde79  mov     rdx, rdi; Buf2
0x1801cde7c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1801cde80  call    memcmp_0
0x1801cde85  test    eax, eax
0x1801cde87  jz      short loc_1801CDE91
0x1801cde89  mov     sil, 1
0x1801cde8c  jmp     loc_1801CE09A
0x1801cde91  xor     sil, sil
0x1801cde94  lea     rbx, [r15+7F8h]
0x1801cde9b  mov     rdx, rbx
0x1801cde9e  mov     rcx, [rbx+38h]
0x1801cdea2  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801cdea7  test    eax, eax
0x1801cdea9  jnz     short loc_1801CDEC1
0x1801cdeab  mov     r8, rbx
0x1801cdeae  lea     rdx, [rbp+57h+Buf1]
0x1801cdeb2  mov     rcx, [rbx+38h]
0x1801cdeb6  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801cdebb  movaps  xmm0, [rbp+57h+Buf1]
0x1801cdebf  jmp     short loc_1801CDEC8
0x1801cdec1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801cdec8  movdqa  [rbp+57h+Buf1], xmm0
0x1801cdecd  mov     r8d, 10h; Size
0x1801cded3  mov     rdx, rdi; Buf2
0x1801cded6  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1801cdeda  call    memcmp_0
0x1801cdedf  test    eax, eax
0x1801cdee1  jz      short loc_1801CDF2C
0x1801cdee3  mov     rdx, rbx
0x1801cdee6  mov     rcx, [rbx+38h]
0x1801cdeea  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801cdeef  test    eax, eax
0x1801cdef1  jnz     short loc_1801CDF09
0x1801cdef3  mov     r8, rbx
0x1801cdef6  lea     rdx, [rbp+57h+Buf1]
0x1801cdefa  mov     rcx, [rbx+38h]
0x1801cdefe  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801cdf03  movaps  xmm0, [rbp+57h+Buf1]
0x1801cdf07  jmp     short loc_1801CDF10
0x1801cdf09  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801cdf10  movdqa  xmmword ptr [rbp+57h+var_80], xmm0
0x1801cdf15  movups  xmm0, xmmword ptr [r14+20h]
0x1801cdf1a  movdqu  [rbp+57h+Buf1], xmm0
0x1801cdf1f  lea     rax, [rbp+57h+Buf1]
0x1801cdf23  lea     r8, [rbp+57h+var_80]
0x1801cdf27  jmp     loc_1801CDFE9
0x1801cdf2c  lea     rbx, [r15+7B8h]
0x1801cdf33  mov     rdx, rbx
0x1801cdf36  mov     rcx, [rbx+38h]
0x1801cdf3a  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801cdf3f  test    eax, eax
0x1801cdf41  jnz     short loc_1801CDF59
0x1801cdf43  mov     r8, rbx
0x1801cdf46  lea     rdx, [rbp+57h+var_80]
0x1801cdf4a  mov     rcx, [rbx+38h]
0x1801cdf4e  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801cdf53  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x1801cdf57  jmp     short loc_1801CDF60
0x1801cdf59  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801cdf60  movdqa  xmmword ptr [rbp+57h+var_80], xmm0
0x1801cdf65  mov     r8d, 10h; Size
0x1801cdf6b  mov     rdx, rdi; Buf2
0x1801cdf6e  lea     rcx, [rbp+57h+var_80]; Buf1
0x1801cdf72  call    memcmp_0
0x1801cdf77  test    eax, eax
0x1801cdf79  jz      short loc_1801CDFBD
0x1801cdf7b  mov     rdx, rbx
0x1801cdf7e  mov     rcx, [rbx+38h]
0x1801cdf82  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801cdf87  test    eax, eax
0x1801cdf89  jnz     short loc_1801CDFA1
0x1801cdf8b  mov     r8, rbx
0x1801cdf8e  lea     rdx, [rbp+57h+var_80]
0x1801cdf92  mov     rcx, [rbx+38h]
0x1801cdf96  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801cdf9b  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x1801cdf9f  jmp     short loc_1801CDFA8
0x1801cdfa1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801cdfa8  movdqa  [rbp+57h+Buf1], xmm0
0x1801cdfad  movups  xmm0, xmmword ptr [r14+20h]
0x1801cdfb2  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1801cdfb7  lea     r8, [rbp+57h+Buf1]
0x1801cdfbb  jmp     short loc_1801CDFE5
0x1801cdfbd  xorps   xmm0, xmm0
0x1801cdfc0  movups  [rbp+57h+Buf1], xmm0
0x1801cdfc4  lea     rcx, [rbp+57h+Buf1]; Uuid
0x1801cdfc8  call    cs:__imp_UuidCreate
0x1801cdfce  movaps  xmm0, [rbp+57h+Buf1]
0x1801cdfd2  movdqa  [rbp+57h+Buf2], xmm0
0x1801cdfd7  movups  xmm1, xmmword ptr [r14+20h]
0x1801cdfdc  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x1801cdfe1  lea     r8, [rbp+57h+Buf2]
0x1801cdfe5  lea     rax, [rbp+57h+var_80]
0x1801cdfe9  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1801cdfee  mov     r9d, [r14+30h]
0x1801cdff2  mov     rdx, r14
0x1801cdff5  mov     rcx, [r14+38h]
0x1801cdff9  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x1801cdffe  nop
0x1801cdfff  lea     rbx, [r15+620h]
0x1801ce006  mov     rdx, rbx
0x1801ce009  mov     rcx, [rbx+38h]
0x1801ce00d  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801ce012  test    eax, eax
0x1801ce014  jnz     short loc_1801CE02C
0x1801ce016  mov     r8, rbx
0x1801ce019  lea     rdx, [rbp+57h+Buf2]
0x1801ce01d  mov     rcx, [rbx+38h]
0x1801ce021  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801ce026  movaps  xmm0, [rbp+57h+Buf2]
0x1801ce02a  jmp     short loc_1801CE033
0x1801ce02c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801ce033  movdqa  [rbp+57h+Buf2], xmm0
0x1801ce038  mov     r8, r14
0x1801ce03b  lea     rdx, [rbp+57h+var_80]
0x1801ce03f  mov     rcx, [r14+38h]
0x1801ce043  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801ce048  mov     r8d, 10h; Size
0x1801ce04e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801ce052  lea     rcx, [rbp+57h+var_80]; Buf1
0x1801ce056  call    memcmp_0
0x1801ce05b  test    eax, eax
0x1801ce05d  jnz     short loc_1801CE09A
0x1801ce05f  mov     r8, r14
0x1801ce062  lea     rdx, [rbp+57h+Buf1]
0x1801ce066  mov     rcx, [r14+38h]
0x1801ce06a  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801ce06f  xor     byte ptr [rbp+57h+Buf1+0Fh], 1
0x1801ce073  movups  xmm0, xmmword ptr [r14+20h]
0x1801ce078  movdqu  [rbp+57h+Buf2], xmm0
0x1801ce07d  lea     rax, [rbp+57h+Buf2]
0x1801ce081  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1801ce086  mov     r9d, [r14+30h]
0x1801ce08a  lea     r8, [rbp+57h+Buf1]
0x1801ce08e  mov     rdx, r14
0x1801ce091  mov     rcx, [r14+38h]
0x1801ce095  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x1801ce09a  lea     rbx, [r15+5A0h]
0x1801ce0a1  mov     rdx, rbx
0x1801ce0a4  mov     rcx, [rbx+38h]
0x1801ce0a8  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801ce0ad  test    eax, eax
0x1801ce0af  jnz     short loc_1801CE0D3
0x1801ce0b1  mov     r8, rbx
0x1801ce0b4  lea     rdx, [rbp+57h+Buf2]
0x1801ce0b8  mov     rcx, [rbx+38h]
0x1801ce0bc  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801ce0c1  mov     r12d, 5
0x1801ce0c7  cmp     [rbp+57h+var_50], 0
0x1801ce0cc  jz      short loc_1801CE0D3
0x1801ce0ce  xor     dil, dil
0x1801ce0d1  jmp     short loc_1801CE0D6
0x1801ce0d3  mov     dil, 1
0x1801ce0d6  test    r12b, 1
0x1801ce0da  jz      short loc_1801CE0E5
0x1801ce0dc  lea     rcx, [rbp+57h+Buf2]; void *
0x1801ce0e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801ce0e5  test    dil, dil
0x1801ce0e8  jz      short loc_1801CE126
0x1801ce0ea  lea     rdx, [rbp+57h+var_80]
0x1801ce0ee  mov     rcx, r15
0x1801ce0f1  call    ?GenerateFriendlyName@PortResource@Resource@Service@HNS@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HNS::Service::Resource::PortResource::GenerateFriendlyName(void)
0x1801ce0f6  nop
0x1801ce0f7  movups  xmm0, xmmword ptr [rbx+20h]
0x1801ce0fb  movdqu  [rbp+57h+Buf2], xmm0
0x1801ce100  lea     rcx, [rbp+57h+Buf2]
0x1801ce104  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x1801ce109  mov     r9d, [rbx+30h]
0x1801ce10d  mov     r8, rax
0x1801ce110  mov     rdx, rbx
0x1801ce113  mov     rcx, [rbx+38h]
0x1801ce117  call    ??$Set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KU_GUID@@@Z; HNSObject::Set<std::wstring>(std::wstring const &,std::wstring const &,ulong,_GUID)
0x1801ce11c  nop
0x1801ce11d  lea     rcx, [rbp+57h+var_80]; void *
0x1801ce121  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801ce126  test    sil, sil
0x1801ce129  jnz     short loc_1801CE199
0x1801ce12b  mov     r8, r14
0x1801ce12e  lea     rdx, [rbp+57h+Buf2]
0x1801ce132  mov     rcx, [r14+38h]
0x1801ce136  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801ce13b  movaps  xmm0, [rbp+57h+Buf2]
0x1801ce13f  movdqa  [rbp+57h+Buf2], xmm0
0x1801ce144  lea     rcx, [r15+838h]; this
0x1801ce14b  lea     rdx, [rbp+57h+Buf2]; struct _GUID
0x1801ce14f  call    ?SwitchPortExists@SwitchHelper@@QEAA_NU_GUID@@@Z; SwitchHelper::SwitchPortExists(_GUID)
0x1801ce154  test    al, al
0x1801ce156  jz      short loc_1801CE199
0x1801ce158  xorps   xmm0, xmm0
0x1801ce15b  movups  [rbp+57h+Buf1], xmm0
0x1801ce15f  lea     rcx, [rbp+57h+Buf1]; Uuid
0x1801ce163  call    cs:__imp_UuidCreate
0x1801ce169  movaps  xmm0, [rbp+57h+Buf1]
0x1801ce16d  movdqa  xmmword ptr [rbp+57h+var_80], xmm0
0x1801ce172  movups  xmm1, xmmword ptr [r14+20h]
0x1801ce177  movdqu  [rbp+57h+Buf2], xmm1
0x1801ce17c  lea     rax, [rbp+57h+Buf2]
0x1801ce180  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1801ce185  mov     r9d, [r14+30h]
0x1801ce189  lea     r8, [rbp+57h+var_80]
0x1801ce18d  mov     rdx, r14
0x1801ce190  mov     rcx, [r14+38h]
0x1801ce194  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x1801ce199  lea     r12, [r15+838h]
0x1801ce1a0  lea     rdi, [r15+560h]
0x1801ce1a7  lea     rcx, [r15+6E0h]
0x1801ce1ae  call    ?get@?$Property@E@@QEBA?BEXZ; Property<uchar>::get(void)
0x1801ce1b3  mov     rcx, rdi
0x1801ce1b6  test    al, al
0x1801ce1b8  jz      loc_1801CE261
0x1801ce1be  call    ?get@?$Property@E@@QEBA?BEXZ; Property<uchar>::get(void)
0x1801ce1c3  movzx   eax, al
0x1801ce1c6  mov     [rbp+57h+var_A0], eax
0x1801ce1c9  lea     rcx, [r15+720h]
0x1801ce1d0  call    ?get@?$Property@E@@QEBA?BEXZ; Property<uchar>::get(void)
0x1801ce1d5  movzx   eax, al
0x1801ce1d8  mov     dword ptr [rbp+57h+Buf1], eax
0x1801ce1db  mov     r8, rbx
0x1801ce1de  lea     rdx, [rbp+57h+var_80]
0x1801ce1e2  mov     rcx, [rbx+38h]
0x1801ce1e6  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801ce1eb  nop
0x1801ce1ec  lea     rsi, [rbp+57h+var_80]
0x1801ce1f0  cmp     [rbp+57h+var_68], 7
0x1801ce1f5  cmova   rsi, [rbp+57h+var_80]
0x1801ce1fa  mov     r8, r14
0x1801ce1fd  lea     rdx, [rbp+57h+Buf2]
0x1801ce201  mov     rcx, [r14+38h]
0x1801ce205  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801ce20a  lea     rdi, [r15+8B8h]
0x1801ce211  mov     r14, [rdi]
0x1801ce214  lea     rax, [r14-1]
0x1801ce218  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ce21c  ja      short loc_1801CE237
0x1801ce21e  call    cs:__imp_GetLastError
0x1801ce224  mov     ebx, eax
0x1801ce226  mov     rcx, r14; hObject
0x1801ce229  call    cs:__imp_CloseHandle
0x1801ce22f  mov     ecx, ebx; dwErrCode
0x1801ce231  call    cs:__imp_SetLastError
0x1801ce237  mov     qword ptr [rdi], 0
0x1801ce23e  mov     eax, [rbp+57h+var_A0]
0x1801ce241  mov     [rsp+0E0h+var_B0], eax; int
0x1801ce245  mov     eax, dword ptr [rbp+57h+Buf1]
0x1801ce248  mov     [rsp+0E0h+var_C0], eax; int
0x1801ce24c  mov     r9, rsi; unsigned __int16 *
0x1801ce24f  lea     r8, [rbp+57h+Buf2]; struct _GUID *
0x1801ce253  mov     rdx, rdi; void **
0x1801ce256  mov     rcx, r12; this
0x1801ce259  call    ?SwitchPortCreateWithHandle@SwitchHelper@@QEBAXPEAPEAXAEBU_GUID@@PEBGHHH@Z; SwitchHelper::SwitchPortCreateWithHandle(void * *,_GUID const &,ushort const *,int,int,int)
0x1801ce25e  nop
  ... truncated ...
```
