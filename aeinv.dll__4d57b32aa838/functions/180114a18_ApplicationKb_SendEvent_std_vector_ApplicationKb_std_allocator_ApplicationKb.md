# ApplicationKb::SendEvent(std::vector<ApplicationKb,std::allocator<ApplicationKb>> &)

- ea: `0x180114a18`
- end: `0x180114ee8`
- name: `?SendEvent@ApplicationKb@@SAXAEAV?$vector@VApplicationKb@@V?$allocator@VApplicationKb@@@std@@@std@@@Z`
- size: `1232`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005667c`

## callees

- `0x180001008`
- `0x180001ad4`
- `0x18000243c`
- `0x1800197d4`
- `0x18001d350`
- `0x18002cef4`
- `0x180030038`
- `0x180051960`
- `0x180059920`
- `0x1800679f8`
- `0x1801149bc`
- `0x180114a18`
- `0x180125490`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180114a50`
- `KERNEL32!GetProcessHeap` at `0x180114a50`
- `KERNEL32!HeapAlloc` at `0x180114a64`
- `KERNEL32!HeapAlloc` at `0x180114a64`
- `ole32!CoCreateGuid` at `0x180114c52`
- `ole32!CoCreateGuid` at `0x180114c52`
- `ole32!StringFromCLSID` at `0x180114c77`
- `ole32!StringFromCLSID` at `0x180114c77`

## string_xrefs

- `0x180114e85`: `base\appcompat\inventory\software\inv2\lib\applicationkb.cpp`
- `0x180114ec1`: `base\appcompat\inventory\software\inv2\lib\applicationkb.cpp`
- `0x180114ed6`: `base\appcompat\inventory\software\inv2\lib\applicationkb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ApplicationKb::SendEvent(const struct ApplicationKb **a1)
{
  HANDLE ProcessHeap; // rax
  wil::details *v3; // rax
  wil::details *v4; // rsi
  unsigned int v5; // r12d
  const struct ApplicationKb *v6; // r15
  const struct ApplicationKb *v7; // r13
  wil::details *v8; // rdi
  size_t v9; // rbx
  const void *p_Src; // rdx
  char *v11; // rdi
  __int64 v12; // rbx
  const void *v13; // rdx
  char *v14; // rdi
  __int64 v15; // rbx
  const void *v16; // rdx
  char *v17; // rdi
  __int64 v18; // rbx
  const void *v19; // rdx
  char *v20; // rdi
  __int64 v21; // rbx
  const void *v22; // rdx
  char *v23; // rdi
  __int64 v24; // rbx
  const void *v25; // rdx
  HRESULT v26; // eax
  HRESULT v27; // eax
  void **v28; // rdx
  void **v29; // rdx
  UtcThrottle *v30; // rcx
  int v31; // edi
  __int64 *v32; // rbx
  int v33; // r8d
  int v34; // r9d
  __int64 *v35; // rax
  void *v36; // rdx
  int v37; // edi
  int v38; // r8d
  int v39; // r9d
  int v40; // [rsp+20h] [rbp-E0h]
  __int16 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp-80h] BYREF
  char *v44; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *Version; // [rsp+90h] [rbp-70h] BYREF
  LPOLESTR v46; // [rsp+98h] [rbp-68h] BYREF
  LPOLESTR v47; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v48; // [rsp+A8h] [rbp-58h] BYREF
  char *v49; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  wil::details *v51; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v52; // [rsp+C8h] [rbp-38h]
  __int16 *v53; // [rsp+D0h] [rbp-30h] BYREF
  int v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  char v57[8]; // [rsp+100h] [rbp+0h] BYREF
  void *Src; // [rsp+108h] [rbp+8h] BYREF
  __int64 v59; // [rsp+118h] [rbp+18h]
  unsigned __int64 v60; // [rsp+120h] [rbp+20h]
  void *v61; // [rsp+128h] [rbp+28h] BYREF
  __int64 v62; // [rsp+138h] [rbp+38h]
  unsigned __int64 v63; // [rsp+140h] [rbp+40h]
  void *v64; // [rsp+148h] [rbp+48h] BYREF
  __int64 v65; // [rsp+158h] [rbp+58h]
  unsigned __int64 v66; // [rsp+160h] [rbp+60h]
  void *v67; // [rsp+168h] [rbp+68h] BYREF
  __int64 v68; // [rsp+178h] [rbp+78h]
  unsigned __int64 v69; // [rsp+180h] [rbp+80h]
  void *v70; // [rsp+188h] [rbp+88h] BYREF
  __int64 v71; // [rsp+198h] [rbp+98h]
  unsigned __int64 v72; // [rsp+1A0h] [rbp+A0h]
  void *v73; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v74; // [rsp+1B8h] [rbp+B8h]
  unsigned __int64 v75; // [rsp+1C0h] [rbp+C0h]
  UtcThrottle *retaddr; // [rsp+228h] [rbp+128h]

  v55 = -2;
  ProcessHeap = GetProcessHeap();
  v3 = (wil::details *)HeapAlloc(ProcessHeap, 8u, 0xE000u);
  v4 = v3;
  v51 = v3;
  if ( !v3 )
  {
    AslLogCallPrintf(1, (unsigned int)"ApplicationKb::SendEvent", 85, (unsigned int)"HeapAlloc failed");
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkb.cpp",
      (const char *)0x8007000ELL,
      v40);
  }
  v5 = 0;
  v41 = 0;
  v6 = *a1;
  v7 = a1[1];
  if ( *a1 != v7 )
  {
    v8 = v3;
    while ( 1 )
    {
      ApplicationKb::ApplicationKb((ApplicationKb *)v57, v6);
      v42 = 2 * (v62 + v65 + v68 + v71 + v59 + v74) + 12;
      if ( v42 + (unsigned __int64)v5 > 0xE000 )
        break;
      v9 = 2 * v59 + 2;
      p_Src = &Src;
      if ( v60 > 7 )
        p_Src = Src;
      memcpy_0(v8, p_Src, v9);
      v11 = (char *)v8 + v9;
      v12 = 2 * v62 + 2;
      v13 = &v61;
      if ( v63 > 7 )
        v13 = v61;
      memcpy_0(v11, v13, 2 * v62 + 2);
      v14 = &v11[v12];
      v15 = 2 * v65 + 2;
      v16 = &v64;
      if ( v66 > 7 )
        v16 = v64;
      memcpy_0(v14, v16, 2 * v65 + 2);
      v17 = &v14[v15];
      v18 = 2 * v68 + 2;
      v19 = &v67;
      if ( v69 > 7 )
        v19 = v67;
      memcpy_0(v17, v19, 2 * v68 + 2);
      v20 = &v17[v18];
      v21 = 2 * v71 + 2;
      v22 = &v70;
      if ( v72 > 7 )
        v22 = v70;
      memcpy_0(v20, v22, 2 * v71 + 2);
      v23 = &v20[v21];
      v24 = 2 * v74 + 2;
      v25 = &v73;
      if ( v75 > 7 )
        v25 = v73;
      memcpy_0(v23, v25, 2 * v74 + 2);
      v8 = (wil::details *)&v23[v24];
      v5 += v42;
      ++v41;
      ApplicationKb::~ApplicationKb((ApplicationKb *)v57);
      v6 = (const struct ApplicationKb *)((char *)v6 + 200);
      if ( v6 == v7 )
        goto LABEL_20;
    }
    ApplicationKb::~ApplicationKb((ApplicationKb *)v57);
    v40 = 122;
    AslLogCallPrintf(
      1,
      (unsigned int)"ApplicationKb::SendEvent",
      146,
      (unsigned int)"UTC utcBuffer not large enough [%d]");
  }
LABEL_20:
  pguid = GUID_NULL;
  v26 = CoCreateGuid(&pguid);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkb.cpp",
      (const char *)(unsigned int)v26,
      v40);
  lpsz = 0;
  v27 = StringFromCLSID(&pguid, &lpsz);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkb.cpp",
      (const char *)(unsigned int)v27,
      v40);
  UtcThrottle::Throttle(retaddr, v28);
  v31 = xmmword_180182350;
  v32 = &ApplicationKb::ApplicationKbProviderName;
  if ( *(_DWORD *)xmmword_180182350 > 5u && (unsigned __int8)tlgKeywordOn(xmmword_180182350, 0x800000000000LL) )
  {
    v44 = &byte_180182368;
    Version = InventoryCoreGetVersion();
    v46 = (LPOLESTR)&byte_1801389F0;
    v47 = lpsz;
    v48 = &byte_1801389F0;
    v35 = &ApplicationKb::ApplicationKbProviderName;
    if ( (unsigned __int64)qword_1801836C8 > 7 )
      v35 = (__int64 *)ApplicationKb::ApplicationKbProviderName;
    v49 = (char *)v35;
    LODWORD(v42) = 3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v31,
      (unsigned int)&byte_180162C07,
      v33,
      v34,
      (__int64)&v42,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&Version,
      (__int64)&v44);
  }
  UtcThrottle::Throttle(v30, v29);
  v37 = xmmword_180182350;
  if ( *(_DWORD *)xmmword_180182350 > 5u && (unsigned __int8)tlgKeywordOn(xmmword_180182350, 0x800000000000LL) )
  {
    v49 = &byte_180182368;
    v48 = InventoryCoreGetVersion();
    v47 = (LPOLESTR)&byte_1801389F0;
    v46 = lpsz;
    Version = L"Kb";
    if ( (unsigned __int64)qword_1801836C8 > 7 )
      v32 = (__int64 *)ApplicationKb::ApplicationKbProviderName;
    v44 = (char *)v32;
    LODWORD(v42) = 1;
    v51 = v4;
    v52 = v5;
    v53 = &v41;
    v54 = 2;
    v50 = 2147485696LL;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v37,
      (unsigned int)word_180162B0A,
      v38,
      v39,
      (__int64)&v50,
      (__int64)&v53,
      (__int64)&v51,
      (__int64)&v42,
      (__int64)&v44,
      (__int64)&Version,
      (__int64)&v46,
      (__int64)&v47,
      (__int64)&v48,
      (__int64)&v49);
  }
  wil::details::FreeProcessHeap(v4, v36);
}

```

## disassembly

```asm
0x180114a18  push    rbp
0x180114a1a  push    rbx
0x180114a1b  push    rsi
0x180114a1c  push    rdi
0x180114a1d  push    r12
0x180114a1f  push    r13
0x180114a21  push    r14
0x180114a23  push    r15
0x180114a25  lea     rbp, [rsp-0E8h]
0x180114a2d  sub     rsp, 1E8h
0x180114a34  mov     [rbp+120h+var_140], 0FFFFFFFFFFFFFFFEh
0x180114a3c  mov     rax, cs:__security_cookie
0x180114a43  xor     rax, rsp
0x180114a46  mov     [rbp+120h+var_50], rax
0x180114a4d  mov     rbx, rcx
0x180114a50  call    cs:__imp_GetProcessHeap
0x180114a56  mov     rcx, rax; hHeap
0x180114a59  mov     edx, 8; dwFlags
0x180114a5e  mov     r8d, 0E000h; dwBytes
0x180114a64  call    cs:__imp_HeapAlloc
0x180114a6a  mov     rsi, rax
0x180114a6d  mov     [rbp+120h+var_160], rax
0x180114a71  test    rax, rax
0x180114a74  jz      loc_180114E97
0x180114a7a  xor     r12d, r12d
0x180114a7d  xor     ecx, ecx
0x180114a7f  mov     [rsp+220h+var_1B0], cx
0x180114a84  mov     r15, [rbx]
0x180114a87  mov     r13, [rbx+8]
0x180114a8b  lea     r14d, [r12+1]
0x180114a90  cmp     r15, r13
0x180114a93  jz      loc_180114C42
0x180114a99  mov     rdi, rax
0x180114a9c  mov     rdx, r15; struct ApplicationKb *
0x180114a9f  lea     rcx, [rbp+120h+var_120]; this
0x180114aa3  call    ??0ApplicationKb@@QEAA@AEBV0@@Z; ApplicationKb::ApplicationKb(ApplicationKb const &)
0x180114aa8  mov     rbx, [rbp+120h+var_108]
0x180114aac  mov     rcx, [rbp+120h+var_68]
0x180114ab3  add     rcx, rbx
0x180114ab6  add     rcx, [rbp+120h+var_88]
0x180114abd  add     rcx, [rbp+120h+var_A8]
0x180114ac1  add     rcx, [rbp+120h+var_C8]
0x180114ac5  add     rcx, [rbp+120h+var_E8]
0x180114ac9  lea     rcx, ds:0Ch[rcx*2]
0x180114ad1  mov     [rsp+220h+var_1A8], rcx
0x180114ad6  mov     eax, r12d
0x180114ad9  add     rax, rcx
0x180114adc  cmp     rax, 0E000h
0x180114ae2  ja      loc_180114C15
0x180114ae8  lea     rbx, ds:2[rbx*2]
0x180114af0  lea     rdx, [rbp+120h+Src]
0x180114af4  cmp     [rbp+120h+var_100], 7
0x180114af9  cmova   rdx, [rbp+120h+Src]; Src
0x180114afe  mov     r8, rbx; Size
0x180114b01  mov     rcx, rdi; void *
0x180114b04  call    memcpy_0
0x180114b09  add     rdi, rbx
0x180114b0c  mov     rax, [rbp+120h+var_E8]
0x180114b10  lea     rbx, ds:2[rax*2]
0x180114b18  lea     rdx, [rbp+120h+var_F8]
0x180114b1c  cmp     [rbp+120h+var_E0], 7
0x180114b21  cmova   rdx, [rbp+120h+var_F8]; Src
0x180114b26  mov     r8, rbx; Size
0x180114b29  mov     rcx, rdi; void *
0x180114b2c  call    memcpy_0
0x180114b31  add     rdi, rbx
0x180114b34  mov     rax, [rbp+120h+var_C8]
0x180114b38  lea     rbx, ds:2[rax*2]
0x180114b40  lea     rdx, [rbp+120h+var_D8]
0x180114b44  cmp     [rbp+120h+var_C0], 7
0x180114b49  cmova   rdx, [rbp+120h+var_D8]; Src
0x180114b4e  mov     r8, rbx; Size
0x180114b51  mov     rcx, rdi; void *
0x180114b54  call    memcpy_0
0x180114b59  add     rdi, rbx
0x180114b5c  mov     rax, [rbp+120h+var_A8]
0x180114b60  lea     rbx, ds:2[rax*2]
0x180114b68  lea     rdx, [rbp+120h+var_B8]
0x180114b6c  cmp     [rbp+120h+var_A0], 7
0x180114b74  cmova   rdx, [rbp+120h+var_B8]; Src
0x180114b79  mov     r8, rbx; Size
0x180114b7c  mov     rcx, rdi; void *
0x180114b7f  call    memcpy_0
0x180114b84  add     rdi, rbx
0x180114b87  mov     rax, [rbp+120h+var_88]
0x180114b8e  lea     rbx, ds:2[rax*2]
0x180114b96  lea     rdx, [rbp+120h+var_98]
0x180114b9d  cmp     [rbp+120h+var_80], 7
0x180114ba5  cmova   rdx, [rbp+120h+var_98]; Src
0x180114bad  mov     r8, rbx; Size
0x180114bb0  mov     rcx, rdi; void *
0x180114bb3  call    memcpy_0
0x180114bb8  add     rdi, rbx
0x180114bbb  mov     rax, [rbp+120h+var_68]
0x180114bc2  lea     rbx, ds:2[rax*2]
0x180114bca  lea     rdx, [rbp+120h+var_78]
0x180114bd1  cmp     [rbp+120h+var_60], 7
0x180114bd9  cmova   rdx, [rbp+120h+var_78]; Src
0x180114be1  mov     r8, rbx; Size
0x180114be4  mov     rcx, rdi; void *
0x180114be7  call    memcpy_0
0x180114bec  add     rdi, rbx
0x180114bef  add     r12d, dword ptr [rsp+220h+var_1A8]
0x180114bf4  add     [rsp+220h+var_1B0], r14w
0x180114bfa  lea     rcx, [rbp+120h+var_120]; this
0x180114bfe  call    ??1ApplicationKb@@UEAA@XZ; ApplicationKb::~ApplicationKb(void)
0x180114c03  add     r15, 0C8h
0x180114c0a  cmp     r15, r13
0x180114c0d  jnz     loc_180114A9C
0x180114c13  jmp     short loc_180114C42
0x180114c15  lea     rcx, [rbp+120h+var_120]; this
0x180114c19  call    ??1ApplicationKb@@UEAA@XZ; ApplicationKb::~ApplicationKb(void)
0x180114c1e  mov     [rsp+220h+var_200], 7Ah ; 'z'; int
0x180114c26  lea     r9, aUtcUtcbufferNo; "UTC utcBuffer not large enough [%d]"
0x180114c2d  mov     r8d, 92h
0x180114c33  lea     rdx, aApplicationkbS; "ApplicationKb::SendEvent"
0x180114c3a  mov     ecx, r14d
0x180114c3d  call    AslLogCallPrintf
0x180114c42  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180114c49  movdqu  xmmword ptr [rbp+120h+pguid.Data1], xmm0
0x180114c4e  lea     rcx, [rbp+120h+pguid]; pguid
0x180114c52  call    cs:__imp_CoCreateGuid
0x180114c58  mov     rcx, [rbp+128h]; this
0x180114c5f  test    eax, eax
0x180114c61  js      loc_180114ED3
0x180114c67  mov     [rbp+120h+lpsz], 0
0x180114c6f  lea     rdx, [rbp+120h+lpsz]; lplpsz
0x180114c73  lea     rcx, [rbp+120h+pguid]; rclsid
0x180114c77  call    cs:__imp_StringFromCLSID
0x180114c7d  mov     rcx, [rbp+128h]; this
0x180114c84  test    eax, eax
0x180114c86  js      loc_180114E82
0x180114c8c  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180114c91  mov     rdi, qword ptr cs:xmmword_180182350
0x180114c98  mov     eax, [rdi]
0x180114c9a  lea     r13, byte_180182368
0x180114ca1  lea     r15, byte_1801389F0
0x180114ca8  lea     rbx, ?ApplicationKbProviderName@ApplicationKb@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const ApplicationKb::ApplicationKbProviderName
0x180114caf  cmp     eax, 5
0x180114cb2  jbe     loc_180114D5D
0x180114cb8  mov     rdx, 800000000000h
0x180114cc2  mov     rcx, rdi
0x180114cc5  call    _tlgKeywordOn
0x180114cca  test    al, al
0x180114ccc  jz      loc_180114D5D
0x180114cd2  mov     [rbp+120h+var_198], r13
0x180114cd6  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180114cdb  mov     [rbp+120h+var_190], rax
0x180114cdf  mov     [rbp+120h+var_188], r15
0x180114ce3  mov     rax, [rbp+120h+lpsz]
0x180114ce7  mov     [rbp+120h+var_180], rax
0x180114ceb  mov     [rbp+120h+var_178], r15
0x180114cef  mov     rax, rbx
0x180114cf2  cmp     cs:qword_1801836C8, 7
0x180114cfa  cmova   rax, cs:?ApplicationKbProviderName@ApplicationKb@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const ApplicationKb::ApplicationKbProviderName
0x180114d02  mov     [rbp+120h+var_170], rax
0x180114d06  mov     dword ptr [rsp+220h+var_1A8], 3
0x180114d0e  lea     rax, [rbp+120h+var_198]
0x180114d12  mov     [rsp+220h+var_1D0], rax
0x180114d17  lea     rax, [rbp+120h+var_190]
0x180114d1b  mov     [rsp+220h+var_1D8], rax
0x180114d20  lea     rax, [rbp+120h+var_188]
0x180114d24  mov     [rsp+220h+var_1E0], rax
0x180114d29  lea     rax, [rbp+120h+var_180]
0x180114d2d  mov     [rsp+220h+var_1E8], rax
0x180114d32  lea     rax, [rbp+120h+var_178]
0x180114d36  mov     [rsp+220h+var_1F0], rax
0x180114d3b  lea     rax, [rbp+120h+var_170]
0x180114d3f  mov     [rsp+220h+var_1F8], rax
0x180114d44  lea     rax, [rsp+220h+var_1A8]
0x180114d49  mov     qword ptr [rsp+220h+var_200], rax
0x180114d4e  lea     rdx, byte_180162C07
0x180114d55  mov     rcx, rdi
0x180114d58  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4444AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x180114d5d  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180114d62  mov     rdi, qword ptr cs:xmmword_180182350
0x180114d69  mov     eax, [rdi]
0x180114d6b  cmp     eax, 5
0x180114d6e  jbe     loc_180114E57
0x180114d74  mov     rdx, 800000000000h
0x180114d7e  mov     rcx, rdi
0x180114d81  call    _tlgKeywordOn
0x180114d86  test    al, al
0x180114d88  jz      loc_180114E57
0x180114d8e  mov     [rbp+120h+var_170], r13
0x180114d92  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180114d97  mov     [rbp+120h+var_178], rax
0x180114d9b  mov     [rbp+120h+var_180], r15
0x180114d9f  mov     rax, [rbp+120h+lpsz]
0x180114da3  mov     [rbp+120h+var_188], rax
0x180114da7  lea     rax, aKb; "Kb"
0x180114dae  mov     [rbp+120h+var_190], rax
0x180114db2  cmp     cs:qword_1801836C8, 7
0x180114dba  cmova   rbx, cs:?ApplicationKbProviderName@ApplicationKb@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const ApplicationKb::ApplicationKbProviderName
0x180114dc2  mov     [rbp+120h+var_198], rbx
0x180114dc6  mov     dword ptr [rsp+220h+var_1A8], r14d
0x180114dcb  mov     [rbp+120h+var_160], rsi
0x180114dcf  mov     [rbp+120h+var_158], r12d
0x180114dd3  lea     rax, [rsp+220h+var_1B0]
0x180114dd8  mov     [rbp+120h+var_150], rax
0x180114ddc  mov     [rbp+120h+var_148], 2
0x180114de3  mov     eax, 80000800h
0x180114de8  mov     [rbp+120h+var_168], rax
0x180114dec  lea     rax, [rbp+120h+var_170]
0x180114df0  mov     [rsp+220h+var_1B8], rax
0x180114df5  lea     rax, [rbp+120h+var_178]
0x180114df9  mov     [rsp+220h+var_1C0], rax
0x180114dfe  lea     rax, [rbp+120h+var_180]
0x180114e02  mov     [rsp+220h+var_1C8], rax
0x180114e07  lea     rax, [rbp+120h+var_188]
0x180114e0b  mov     [rsp+220h+var_1D0], rax
0x180114e10  lea     rax, [rbp+120h+var_190]
0x180114e14  mov     [rsp+220h+var_1D8], rax
0x180114e19  lea     rax, [rbp+120h+var_198]
0x180114e1d  mov     [rsp+220h+var_1E0], rax
0x180114e22  lea     rax, [rsp+220h+var_1A8]
0x180114e27  mov     [rsp+220h+var_1E8], rax
0x180114e2c  lea     rax, [rbp+120h+var_160]
0x180114e30  mov     [rsp+220h+var_1F0], rax
0x180114e35  lea     rax, [rbp+120h+var_150]
0x180114e39  mov     [rsp+220h+var_1F8], rax
0x180114e3e  lea     rax, [rbp+120h+var_168]
0x180114e42  mov     qword ptr [rsp+220h+var_200], rax
0x180114e47  lea     rdx, word_180162B0A
0x180114e4e  mov     rcx, rdi
0x180114e51  call    ??$Write@U?$_tlgWrapperByVal@$07@@U_tlgWrapperPtrSize@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U4@U4@U4@U4@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU_tlgWrapperPtrSize@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@6666AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x180114e56  nop
0x180114e57  mov     rcx, rsi; this
0x180114e5a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180114e5f  mov     rcx, [rbp+120h+var_50]
0x180114e66  xor     rcx, rsp; StackCookie
0x180114e69  call    __security_check_cookie
0x180114e6e  add     rsp, 1E8h
0x180114e75  pop     r15
0x180114e77  pop     r14
0x180114e79  pop     r13
0x180114e7b  pop     r12
0x180114e7d  pop     rdi
0x180114e7e  pop     rsi
0x180114e7f  pop     rbx
0x180114e80  pop     rbp
0x180114e81  retn
0x180114e82  mov     r9d, eax; char *
0x180114e85  lea     r8, aBaseAppcompatI_9; "base\\appcompat\\inventory\\software\\i"...
0x180114e8c  mov     edx, 98h; void *
0x180114e91  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180114e97  lea     r9, aHeapallocFaile; "HeapAlloc failed"
0x180114e9e  mov     r8d, 55h ; 'U'
0x180114ea4  lea     rdx, aApplicationkbS; "ApplicationKb::SendEvent"
0x180114eab  lea     ecx, [r8-54h]
0x180114eaf  call    AslLogCallPrintf
0x180114eb4  mov     rcx, [rbp+128h]; this
0x180114ebb  mov     r9d, 8007000Eh; char *
0x180114ec1  lea     r8, aBaseAppcompatI_9; "base\\appcompat\\inventory\\software\\i"...
0x180114ec8  mov     edx, 56h ; 'V'; void *
0x180114ecd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180114ed3  mov     r9d, eax; char *
0x180114ed6  lea     r8, aBaseAppcompatI_9; "base\\appcompat\\inventory\\software\\i"...
0x180114edd  mov     edx, 96h; void *
0x180114ee2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
