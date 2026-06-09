# VdbSubweb::createUrlDirectories(VpurlDirVvector const &,_GUID const * *,char,char,ulong const *,long const *,URL_ATTACHMENT_FLAG *,long,_GUID const *)

- ea: `0x1800a0f90`
- end: `0x1800a1d40`
- name: `?createUrlDirectories@VdbSubweb@@QEAAPEAVVstatus@@AEBVVpurlDirVvector@@PEAPEBU_GUID@@DDPEBKPEBJPEAW4URL_ATTACHMENT_FLAG@@JPEBU4@@Z`
- size: `3504`
- prototype: `struct Vstatus *__usercall@<rax>(VdbSubweb *__hidden this@<rcx>, const struct VpurlDirVvector *@<rdx>, const struct _GUID **@<r8>, char@<r9b>, char, const unsigned int *, const int *, enum URL_ATTACHMENT_FLAG *, int, const struct _GUID *)`
- caller_count: `4`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a09b0`
- `0x1800a0de0`
- `0x1800a1d40`
- `0x18014c650`

## callees

- `0x1800279ec`
- `0x18003e014`
- `0x18003e12c`
- `0x18005a36c`
- `0x18005a3fc`
- `0x18005a48c`
- `0x180090f40`
- `0x18009c670`
- `0x1800a0f90`
- `0x1800a3f10`
- `0x1800ad8a4`
- `0x1800b48e0`
- `0x1800b54d0`
- `0x1800c47f0`
- `0x1800d0800`
- `0x1800ef0f0`
- `0x1800ef190`
- `0x180137580`
- `0x180157050`
- `0x180173a70`
- `0x1801c2da0`

## import_xrefs

- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a178e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1af9`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1b76`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1c25`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a178e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1af9`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1b76`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800a1c25`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800a1203`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800a1274`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800a1203`
- `onetutil!??0Vstring@@QEAA@PEB_W@Z` at `0x1800a1274`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a17f3`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a187a`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1969`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a19e6`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1acb`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1b48`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1c3e`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a17f3`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a187a`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1969`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a19e6`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1acb`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1b48`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800a1c3e`
- `onetutil!?Url@VurlDir@@QEBAAEBVVstringStorePath@@XZ` at `0x1800a114f`
- `onetutil!?Url@VurlDir@@QEBAAEBVVstringStorePath@@XZ` at `0x1800a114f`
- `onetutil!?dirName@?$VurlTemplate@VVstoreUrlSettings@@@@QEBA?AV1@XZ` at `0x1800a11b2`
- `onetutil!?dirName@?$VurlTemplate@VVstoreUrlSettings@@@@QEBA?AV1@XZ` at `0x1800a11b2`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1800a13a8`
- `onetutil!?getUnicode@Vstring@@QEBA?AVVwstring@@XZ` at `0x1800a13a8`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d00`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d0e`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d1c`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d00`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d0e`
- `onetutil!??1VstringStorePathVvector@@QEAA@XZ` at `0x1800a1d1c`
- `onetutil!??AVstringStorePathVvector@@QEAAAEAVVstringStorePath@@I@Z` at `0x1800a1af0`
- `onetutil!??AVstringStorePathVvector@@QEAAAEAVVstringStorePath@@I@Z` at `0x1800a1b6d`
- `onetutil!??AVstringStorePathVvector@@QEAAAEAVVstringStorePath@@I@Z` at `0x1800a1af0`
- `onetutil!??AVstringStorePathVvector@@QEAAAEAVVstringStorePath@@I@Z` at `0x1800a1b6d`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a146a`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a1495`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a14bd`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a146a`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a1495`
- `onetutil!?insert@VstringStorePathVvector@@QEAAXAEBVVstringStorePath@@@Z` at `0x1800a14bd`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a0fe0`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a0ff2`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a1001`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a0fe0`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a0ff2`
- `onetutil!??0VstringStorePathVvector@@QEAA@I@Z` at `0x1800a1001`
- `onetutil!??AVpurlDirVvector@@QEBAPEAVVurlDir@@I@Z` at `0x1800a1146`
- `onetutil!??AVpurlDirVvector@@QEBAPEAVVurlDir@@I@Z` at `0x1800a1146`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1164`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a11c8`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a121a`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a128b`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1458`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1483`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a14ae`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a14f6`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1164`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a11c8`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a121a`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a128b`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1458`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a1483`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a14ae`
- `onetutil!??0Vstring@@QEAA@AEBV0@@Z` at `0x1800a14f6`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800a1bc9`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x1800a1bc9`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a11e5`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1225`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1248`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1296`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1475`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a14a0`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a14c8`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1524`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1537`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a154a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a155d`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1570`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a174d`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1760`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1773`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a17ae`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1810`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1826`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a183c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1852`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1897`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a18ad`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a18c3`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1986`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a199c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a19b2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1c53`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a11e5`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1225`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1248`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1296`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1475`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a14a0`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a14c8`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1524`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1537`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a154a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a155d`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1570`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a174d`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1760`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1773`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a17ae`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1810`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1826`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a183c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1852`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1897`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a18ad`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a18c3`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1986`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a199c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a19b2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800a1c53`
- `onetutil!??4Vstring@@QEAAAEAV0@PEBD@Z` at `0x1800a1bde`
- `onetutil!??4Vstring@@QEAAAEAV0@PEBD@Z` at `0x1800a1bde`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a1230`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a12a1`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a13d3`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a1432`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a1230`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a12a1`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a13d3`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1800a1432`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a100c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a104c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a108c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a10ae`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a16c0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1714`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a17bc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a192b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1a90`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1b14`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1bf5`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1c7b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1ca0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1cbc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1ce0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a100c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a104c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a108c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a10ae`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a16c0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1714`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a17bc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a192b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1a90`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1b14`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1bf5`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1c7b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1ca0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1cbc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800a1ce0`
- `onetutil!??0Vwstring@@QEAA@AEBV0@@Z` at `0x1800a13b6`
- `onetutil!??0Vwstring@@QEAA@AEBV0@@Z` at `0x1800a13b6`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1018`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1059`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1099`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a10ba`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a16d3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a172a`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a17ce`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a193d`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1a9f`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1b23`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1c04`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1018`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1059`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1099`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a10ba`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a16d3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a172a`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a17ce`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a193d`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1a9f`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1b23`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800a1c04`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1c89`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1cae`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1cc9`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1ced`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1c89`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1cae`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1cc9`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1800a1ced`

## pseudocode

```c
// Hidden C++ exception states: #wind=113
struct Vstatus *__fastcall VdbSubweb::createUrlDirectories(
        VdbSubweb *this,
        const struct VpurlDirVvector *a2,
        const struct _GUID **a3,
        char a4,
        char a5,
        const unsigned int *a6,
        const int *a7,
        enum URL_ATTACHMENT_FLAG *a8,
        unsigned int a9,
        const struct _GUID *a10)
{
  unsigned int v12; // r12d
  unsigned int v13; // esi
  VgenericStatus *v14; // rdi
  unsigned int v15; // ebx
  __int64 v16; // rcx
  void *v17; // rax
  __int64 v18; // rcx
  enum URL_ATTACHMENT_FLAG *v19; // rax
  unsigned __int64 v20; // rbx
  unsigned int *v21; // r13
  unsigned __int64 v22; // rbx
  unsigned int *v23; // rax
  unsigned int v24; // ebx
  void *v25; // rax
  char v26; // bl
  bool v27; // zf
  unsigned int v28; // ebx
  VurlDir *v29; // rax
  const struct Vstring *v30; // rax
  void *v31; // rbx
  const struct Vstring *v32; // rax
  unsigned int v33; // esi
  const wchar_t **v34; // rax
  const wchar_t **v35; // rax
  struct VdoclibManager *DoclibManager; // rax
  int v37; // ebx
  __int64 v38; // rbx
  __int64 Unicode; // rax
  unsigned int v40; // esi
  int v41; // ebx
  int UrlAttachmentFlag; // eax
  char IsThicket; // al
  int v44; // edx
  const unsigned int *v45; // rcx
  int v46; // ebx
  __int64 v47; // rcx
  VgenericStatus *v48; // rax
  int v49; // ebx
  __int64 v50; // rcx
  VgenericStatus *v51; // rax
  const char *v52; // rax
  __int64 v53; // rcx
  int v54; // ebx
  unsigned int v55; // edi
  __int64 v56; // rcx
  VgenericStatus *v57; // rax
  __int64 v58; // rax
  const char *v59; // rcx
  __int64 v60; // rax
  int v61; // ebx
  unsigned int v62; // edi
  __int64 v63; // rcx
  VgenericStatus *v64; // rax
  Vstring *v65; // rax
  const char *v66; // rax
  VgenericStatus *v67; // rax
  Vstring *v68; // rax
  const char *v69; // rax
  const char *v70; // rbx
  __int64 v71; // rcx
  VgenericStatus *v72; // rax
  VgenericStatus *v73; // rbx
  const char *v74; // rax
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v78; // [rsp+28h] [rbp-100h]
  __int64 v79; // [rsp+28h] [rbp-100h]
  __int64 v80; // [rsp+A8h] [rbp-80h] BYREF
  int v81; // [rsp+B0h] [rbp-78h]
  char v82[8]; // [rsp+B8h] [rbp-70h] BYREF
  char v83[8]; // [rsp+C0h] [rbp-68h] BYREF
  char v84[8]; // [rsp+C8h] [rbp-60h] BYREF
  _QWORD v85[2]; // [rsp+D0h] [rbp-58h] BYREF
  void *v86; // [rsp+E0h] [rbp-48h]
  void *v87; // [rsp+E8h] [rbp-40h]
  void *Block; // [rsp+F0h] [rbp-38h]
  __int64 v89; // [rsp+F8h] [rbp-30h] BYREF
  char v90[8]; // [rsp+100h] [rbp-28h] BYREF
  int v91; // [rsp+108h] [rbp-20h] BYREF
  char v92[8]; // [rsp+110h] [rbp-18h] BYREF
  char v93[8]; // [rsp+118h] [rbp-10h] BYREF
  __int64 v94; // [rsp+120h] [rbp-8h] BYREF
  char v95[8]; // [rsp+128h] [rbp+0h] BYREF
  char v96[8]; // [rsp+130h] [rbp+8h] BYREF
  char v97[8]; // [rsp+138h] [rbp+10h] BYREF
  char v98[8]; // [rsp+140h] [rbp+18h] BYREF
  _QWORD v99[2]; // [rsp+148h] [rbp+20h] BYREF
  _QWORD v100[2]; // [rsp+158h] [rbp+30h] BYREF
  _QWORD v101[2]; // [rsp+168h] [rbp+40h] BYREF
  _BYTE v102[16]; // [rsp+178h] [rbp+50h] BYREF
  int v103; // [rsp+188h] [rbp+60h]
  char v104[8]; // [rsp+198h] [rbp+70h] BYREF
  char v105[8]; // [rsp+1A0h] [rbp+78h] BYREF
  _BYTE v106[16]; // [rsp+1A8h] [rbp+80h] BYREF
  __int64 v107; // [rsp+1B8h] [rbp+90h]
  _BYTE v108[16]; // [rsp+1C0h] [rbp+98h] BYREF
  _BYTE v109[16]; // [rsp+1D0h] [rbp+A8h] BYREF
  _BYTE v110[32]; // [rsp+1E0h] [rbp+B8h] BYREF
  _BYTE v111[88]; // [rsp+200h] [rbp+D8h] BYREF
  VgenericStatus *v112; // [rsp+270h] [rbp+148h] BYREF
  const struct _GUID **v113; // [rsp+278h] [rbp+150h]
  char v114; // [rsp+280h] [rbp+158h]

  v114 = a4;
  v113 = a3;
  v107 = -2;
  v12 = 0;
  v13 = 0;
  v81 = 0;
  v14 = 0;
  VstringStorePathVvector::VstringStorePathVvector((VstringStorePathVvector *)v111, *((_DWORD *)a2 + 4));
  VstringStorePathVvector::VstringStorePathVvector((VstringStorePathVvector *)v110, *((_DWORD *)a2 + 4));
  VstringStorePathVvector::VstringStorePathVvector((VstringStorePathVvector *)v102, *((_DWORD *)a2 + 4));
  v15 = *((_DWORD *)a2 + 4);
  if ( (unsigned int)COWSAllocator::QueryNewMode(v16) )
    v17 = COWSAllocator::AllocCurrentHeap(v15);
  else
    v17 = malloc(v15);
  Block = v17;
  v19 = a8;
  if ( !a8 )
  {
    v20 = 4LL * *((unsigned int *)a2 + 4);
    if ( !is_mul_ok(*((unsigned int *)a2 + 4), 4u) )
      v20 = -1;
    if ( (unsigned int)COWSAllocator::QueryNewMode(*((unsigned int *)a2 + 4)) )
      v19 = (enum URL_ATTACHMENT_FLAG *)COWSAllocator::AllocCurrentHeap(v20);
    else
      v19 = (enum URL_ATTACHMENT_FLAG *)malloc(v20);
  }
  v87 = v19;
  if ( a6 )
  {
    v21 = 0;
  }
  else
  {
    v22 = 4LL * *((unsigned int *)a2 + 4);
    if ( !is_mul_ok(*((unsigned int *)a2 + 4), 4u) )
      v22 = -1;
    if ( (unsigned int)COWSAllocator::QueryNewMode(*((unsigned int *)a2 + 4)) )
      v23 = (unsigned int *)COWSAllocator::AllocCurrentHeap(v22);
    else
      v23 = (unsigned int *)malloc(v22);
    v21 = v23;
  }
  v24 = *((_DWORD *)a2 + 4);
  if ( (unsigned int)COWSAllocator::QueryNewMode(v18) )
    v25 = COWSAllocator::AllocCurrentHeap(v24);
  else
    v25 = malloc(v24);
  v86 = v25;
  LODWORD(v112) = 0;
  if ( !a9
    || (v13 = 1, v81 = 1, v26 = 1, *(int *)VsecurableObject::assertPermissionMask(this, v85, 0x40000000, 50) >= 0) )
  {
    v26 = 0;
  }
  if ( (v13 & 1) != 0 )
  {
    v13 &= ~1u;
    v81 = v13;
    VHRESULT::~VHRESULT((VHRESULT *)v85);
  }
  v27 = v26 == 0;
  v28 = a9;
  if ( !v27 )
    v28 = 0;
  a9 = v28;
  if ( !*((_DWORD *)a2 + 4) )
  {
LABEL_50:
    VrgwzStorePathHelper::init((VrgwzStorePathHelper *)v99, (const struct VstringStorePathVvector *)v111);
    VrgwzStorePathHelper::init((VrgwzStorePathHelper *)v100, (const struct VstringStorePathVvector *)v110);
    VrgwzStorePathHelper::init((VrgwzStorePathHelper *)v101, (const struct VstringStorePathVvector *)v102);
    a9 = -1;
    if ( v103 )
    {
      v45 = v21;
      if ( a6 )
        v45 = a6;
      v46 = *(_DWORD *)VdocumentStore::createUrlDirectories(
                         *((_QWORD *)this + 7) + 216LL,
                         v106,
                         *((_QWORD *)this + 7) + 200LL,
                         *((_QWORD *)this + 7) + 184LL,
                         (char *)this + 264,
                         v99[0],
                         v100[0],
                         v101[0],
                         a7,
                         this,
                         v87,
                         Block,
                         v45,
                         v86,
                         v113,
                         v103,
                         v114,
                         &a9,
                         v28,
                         a10);
      VHRESULT::~VHRESULT((VHRESULT *)v106);
      switch ( v46 )
      {
        case -2147023080:
          if ( (unsigned int)COWSAllocator::QueryNewMode(v47) )
            v48 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
          else
            v48 = (VgenericStatus *)malloc(0x20u);
          v112 = v48;
          if ( v48 )
            v14 = VgenericStatus::VgenericStatus(v48, 0x90063u, 0);
          else
            v14 = 0;
          goto LABEL_122;
        case -2147024684:
          v58 = *((_QWORD *)this + 7);
          if ( *(_BYTE *)(v58 + 402) )
            v59 = "http://localhost";
          else
            v59 = *(const char **)(*(_QWORD *)(v58 + 176) + 8LL * *(int *)(v58 + 168));
          v60 = sub_18005A48C(v59);
          goto LABEL_111;
        case -2147024690:
          v61 = VKillSwitch::isActivated(&stru_1802355B0, "11/03/2017", "SPEED_Disallow400CharFileNames") != 0
              ? 260
              : 400;
          v62 = VKillSwitch::isActivated(&stru_1802355B0, "11/03/2017", "SPEED_Disallow400CharFileNames") != 0
              ? 260
              : 400;
          if ( (unsigned int)COWSAllocator::QueryNewMode(v63) )
            v64 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
          else
            v64 = (VgenericStatus *)malloc(0x20u);
          v112 = v64;
          if ( v64 )
          {
            LODWORD(v79) = v61;
            v14 = VgenericStatus::VgenericStatus(v64, 0x90084u, 0, v62, v79);
          }
          else
          {
            v14 = 0;
          }
          goto LABEL_122;
        case -2147221018:
          v65 = (Vstring *)VstringStorePathVvector::operator[](v102, a9);
          v66 = Vstring::data(v65);
          v60 = sub_18005A3FC(v66);
LABEL_111:
          v14 = (VgenericStatus *)v60;
          goto LABEL_122;
        case -2147022882:
          if ( (unsigned int)COWSAllocator::QueryNewMode(v47) )
            v67 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
          else
            v67 = (VgenericStatus *)malloc(0x20u);
          v112 = v67;
          if ( v67 )
            v14 = VgenericStatus::VgenericStatus(v67, 0x500A0u, 0);
          else
            v14 = 0;
          goto LABEL_122;
      }
      if ( v46 < 0 )
      {
        v68 = (Vstring *)VstringStorePathVvector::operator[](v102, a9);
        v69 = Vstring::data(v68);
        switch ( v46 )
        {
          case -2147024893:
            v70 = v69;
            Vstring::Vstring((Vstring *)&v112);
            if ( v70 )
              sub_18003E014(v70, &v112);
            else
              Vstring::operator=(&v112, 0);
            if ( (unsigned int)COWSAllocator::QueryNewMode(v71) )
              v72 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
            else
              v72 = (VgenericStatus *)malloc(0x20u);
            v73 = v72;
            v85[0] = v72;
            if ( v72 )
            {
              v74 = Vstring::data((Vstring *)&v112);
              v14 = VgenericStatus::VgenericStatus(v73, 0x2001Du, 0, 0, v74);
            }
            else
            {
              v14 = 0;
            }
            Vstring::~Vstring((Vstring *)&v112);
            goto LABEL_122;
          case -2147024816:
            v60 = sub_1800AD8A4(v69);
            break;
          case -2147024773:
            v60 = sub_18005A36C(v69);
            break;
          default:
            v60 = sub_18003E12C(131075, 0, v69);
            break;
        }
        goto LABEL_111;
      }
    }
LABEL_122:
    VrgwzStorePathHelper::clear((VrgwzStorePathHelper *)v101);
    VrgwzStorePathHelper::clear((VrgwzStorePathHelper *)v100);
    VrgwzStorePathHelper::clear((VrgwzStorePathHelper *)v99);
    goto LABEL_123;
  }
  while ( 1 )
  {
    v89 = 0;
    v29 = (VurlDir *)VpurlDirVvector::operator[](a2, v12);
    v30 = VurlDir::Url(v29);
    v85[0] = &v80;
    Vstring::Vstring((Vstring *)&v80, v30);
    if ( !a6 )
      v21[v12] = 0;
    v31 = v86;
    *((_BYTE *)v86 + v12) = 0;
    if ( !*(_DWORD *)(v80 - 4) )
    {
      if ( v114 )
      {
        v52 = Vstring::data((VdbSubweb *)((char *)this + 368));
        v14 = (VgenericStatus *)sub_1800AD8A4(v52);
        v112 = (VgenericStatus *)&v80;
        Vstring::~Vstring((Vstring *)&v80);
        goto LABEL_124;
      }
      v85[0] = &v80;
      goto LABEL_48;
    }
    v32 = (const struct Vstring *)VurlTemplate<VstoreUrlSettings>::dirName(&v80, v104);
    v85[0] = v90;
    Vstring::Vstring((Vstring *)v90, v32);
    v33 = v13 & 0xFFFFFFF9 | 2;
    v81 = v33;
    Vstring::~Vstring((Vstring *)v104);
    v34 = (const wchar_t **)VdbSubweb::serviceUrlToStoreUrl(this, v105, v90);
    Vstring::Vstring((Vstring *)v92, *v34);
    v85[0] = v82;
    Vstring::Vstring((Vstring *)v82, (const struct Vstring *)v92);
    Vstring::~Vstring((Vstring *)v92);
    Vwstring::~Vwstring(v105);
    v13 = v33 & 0xFFFFFFFD;
    v81 = v13;
    v85[0] = v90;
    Vstring::~Vstring((Vstring *)v90);
    sub_1800279EC(&v80, v84);
    v35 = (const wchar_t **)VdbSubweb::serviceUrlToStoreUrl(this, v99, &v80);
    Vstring::Vstring((Vstring *)v93, *v35);
    v85[0] = v83;
    Vstring::Vstring((Vstring *)v83, (const struct Vstring *)v93);
    Vstring::~Vstring((Vstring *)v93);
    Vwstring::~Vwstring(v99);
    if ( a5 )
      goto LABEL_45;
    DoclibManager = VdbSubweb::getDoclibManager(this);
    v37 = *(_DWORD *)VdoclibManager::GetContainingList(DoclibManager, v108, &v80, 0, &v89);
    VHRESULT::~VHRESULT((VHRESULT *)v108);
    if ( !v37 )
      break;
    if ( v37 == 1 )
    {
      v49 = *(_DWORD *)VsecurableObject::assertPermissionMask(this, v106, 0x40000, 50);
      VHRESULT::~VHRESULT((VHRESULT *)v106);
      if ( v49 < 0 )
      {
        if ( (unsigned int)COWSAllocator::QueryNewMode(v50) )
          v51 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v51 = (VgenericStatus *)malloc(0x20u);
        v112 = v51;
        if ( v51 )
          goto LABEL_67;
        v14 = 0;
        goto LABEL_69;
      }
      goto LABEL_45;
    }
    if ( v37 == -2147024690 )
    {
      v54 = VKillSwitch::isActivated(&stru_1802355B0, "11/03/2017", "SPEED_Disallow400CharFileNames") != 0 ? 260 : 400;
      v55 = VKillSwitch::isActivated(&stru_1802355B0, "11/03/2017", "SPEED_Disallow400CharFileNames") != 0 ? 260 : 400;
      if ( (unsigned int)COWSAllocator::QueryNewMode(v56) )
        v57 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v57 = (VgenericStatus *)malloc(0x20u);
      v112 = v57;
      if ( v57 )
      {
        LODWORD(v78) = v54;
        v14 = VgenericStatus::VgenericStatus(v57, 0x90084u, 0, v55, v78);
      }
      else
      {
        v14 = 0;
      }
      goto LABEL_69;
    }
    v85[0] = v83;
    Vstring::~Vstring((Vstring *)v83);
    v85[0] = v84;
    Vstring::~Vstring((Vstring *)v84);
    v85[0] = v82;
    Vstring::~Vstring((Vstring *)v82);
    v85[0] = &v80;
LABEL_48:
    Vstring::~Vstring((Vstring *)&v80);
    if ( ++v12 >= *((_DWORD *)a2 + 4) )
    {
      v28 = a9;
      goto LABEL_50;
    }
  }
  v38 = v89;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v89 + 144LL))(v89, &v91);
  v89 = 2048;
  if ( v91 == 1 && (unsigned __int8)VdoclibManager::IsDoclibItem(&v80, v38, 0, 2) )
  {
    if ( !a6 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 480LL))(v38) )
      {
        v21[v12] = 2;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 584LL))(v38) )
          *((_BYTE *)v86 + v12) = 1;
      }
    }
    v89 = 2;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  v85[0] = this;
  Unicode = Vstring::getUnicode(v82, v100);
  ((void (__fastcall *)(__int64 *, __int64))Vwstring::Vwstring)(&v94, Unicode);
  v40 = v13 & 0xFFFFFF9F | 0x20;
  v81 = v40;
  Vwstring::~Vwstring(v100);
  v101[0] = v94;
  LOBYTE(v78) = 0;
  v41 = *(_DWORD *)VsecurityAdministration::getSecurityInfoFromStoreUrlAndCheckPerm(
                     v85,
                     v109,
                     v101,
                     v89,
                     v78,
                     0,
                     0,
                     0,
                     0,
                     0);
  VHRESULT::~VHRESULT((VHRESULT *)v109);
  v13 = v40 & 0xFFFFFFDF;
  v81 = v13;
  Vwstring::~Vwstring(&v94);
  if ( (int)(v41 + 0x80000000) < 0 || v41 == -2147024893 )
  {
LABEL_45:
    Vstring::Vstring((Vstring *)v95, (const struct Vstring *)v82);
    VstringStorePathVvector::insert((VstringStorePathVvector *)v111, (const struct VstringStorePath *)v95);
    Vstring::~Vstring((Vstring *)v95);
    Vstring::Vstring((Vstring *)v96, (const struct Vstring *)v84);
    VstringStorePathVvector::insert((VstringStorePathVvector *)v110, (const struct VstringStorePath *)v96);
    Vstring::~Vstring((Vstring *)v96);
    Vstring::Vstring((Vstring *)v97, (const struct Vstring *)v83);
    VstringStorePathVvector::insert((VstringStorePathVvector *)v102, (const struct VstringStorePath *)v97);
    Vstring::~Vstring((Vstring *)v97);
    if ( !a8 )
    {
      UrlAttachmentFlag = VdocumentStore::GetUrlAttachmentFlag(&v80);
      *((_DWORD *)v87 + (unsigned int)v112) = UrlAttachmentFlag;
    }
    Vstring::Vstring((Vstring *)v98, (const struct Vstring *)v84);
    IsThicket = VdbServer::pathComponentIsThicket(*((VdbServer **)this + 7), (const struct VstringStorePath *)v98);
    v44 = (int)v112;
    *((_BYTE *)Block + (unsigned int)v112) = IsThicket;
    LODWORD(v112) = v44 + 1;
    Vstring::~Vstring((Vstring *)v98);
    v85[0] = v83;
    Vstring::~Vstring((Vstring *)v83);
    v85[0] = v84;
    Vstring::~Vstring((Vstring *)v84);
    v85[0] = v82;
    Vstring::~Vstring((Vstring *)v82);
    v85[0] = &v80;
    goto LABEL_48;
  }
  if ( (unsigned int)COWSAllocator::QueryNewMode(0x80000000LL) )
    v51 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
  else
    v51 = (VgenericStatus *)malloc(0x20u);
  v112 = v51;
  if ( v51 )
  {
LABEL_67:
    v14 = VgenericStatus::VgenericStatus(v51, 0x1E0002u, 0);
    goto LABEL_69;
  }
  v14 = 0;
LABEL_69:
  v112 = (VgenericStatus *)v83;
  Vstring::~Vstring((Vstring *)v83);
  v112 = (VgenericStatus *)v84;
  Vstring::~Vstring((Vstring *)v84);
  v112 = (VgenericStatus *)v82;
  Vstring::~Vstring((Vstring *)v82);
  v112 = (VgenericStatus *)&v80;
  Vstring::~Vstring((Vstring *)&v80);
LABEL_123:
  v31 = v86;
LABEL_124:
  if ( (unsigned int)COWSAllocator::QueryNewMode(v53) )
    COWSAllocator::Free(Block);
  else
    free(Block);
  if ( !a8 )
  {
    if ( (unsigned int)COWSAllocator::QueryNewMode(v75) )
      COWSAllocator::Free(v87);
    else
      free(v87);
  }
  if ( (unsigned int)COWSAllocator::QueryNewMode(v75) )
    COWSAllocator::Free(v31);
  else
    free(v31);
  if ( !a6 )
  {
    if ( (unsigned int)COWSAllocator::QueryNewMode(v76) )
      COWSAllocator::Free(v21);
    else
      free(v21);
  }
  VstringStorePathVvector::~VstringStorePathVvector((VstringStorePathVvector *)v102);
  VstringStorePathVvector::~VstringStorePathVvector((VstringStorePathVvector *)v110);
  VstringStorePathVvector::~VstringStorePathVvector((VstringStorePathVvector *)v111);
  return v14;
}

```

## disassembly

```asm
0x1800a0f90  mov     rax, rsp
0x1800a0f93  mov     [rax+20h], r9b
0x1800a0f97  mov     [rax+18h], r8
0x1800a0f9b  push    rbp
0x1800a0f9c  push    rsi
0x1800a0f9d  push    rdi
0x1800a0f9e  push    r12
0x1800a0fa0  push    r13
0x1800a0fa2  push    r14
0x1800a0fa4  push    r15
0x1800a0fa6  lea     rbp, [rax-138h]
0x1800a0fad  sub     rsp, 220h
0x1800a0fb4  mov     [rbp+130h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800a0fbf  mov     [rax+8], rbx
0x1800a0fc3  mov     r14, rdx
0x1800a0fc6  mov     r15, rcx
0x1800a0fc9  xor     r12d, r12d
0x1800a0fcc  mov     esi, r12d
0x1800a0fcf  mov     [rbp+130h+var_1A8], r12d
0x1800a0fd3  mov     edi, r12d
0x1800a0fd6  mov     edx, [rdx+10h]
0x1800a0fd9  lea     rcx, [rbp+130h+var_58]
0x1800a0fe0  call    cs:??0VstringStorePathVvector@@QEAA@I@Z; VstringStorePathVvector::VstringStorePathVvector(uint)
0x1800a0fe6  nop
0x1800a0fe7  mov     edx, [r14+10h]
0x1800a0feb  lea     rcx, [rbp+130h+var_78]
0x1800a0ff2  call    cs:??0VstringStorePathVvector@@QEAA@I@Z; VstringStorePathVvector::VstringStorePathVvector(uint)
0x1800a0ff8  nop
0x1800a0ff9  mov     edx, [r14+10h]
0x1800a0ffd  lea     rcx, [rbp+130h+var_E0]
0x1800a1001  call    cs:??0VstringStorePathVvector@@QEAA@I@Z; VstringStorePathVvector::VstringStorePathVvector(uint)
0x1800a1007  nop
0x1800a1008  mov     ebx, [r14+10h]
0x1800a100c  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800a1012  mov     ecx, ebx; Size
0x1800a1014  test    eax, eax
0x1800a1016  jz      short loc_1800A1020
0x1800a1018  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a101e  jmp     short loc_1800A1026
0x1800a1020  call    cs:malloc
0x1800a1026  mov     [rbp+130h+Block], rax
0x1800a102a  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800a102e  mov     rax, [rbp+130h+arg_38]
0x1800a1035  test    rax, rax
0x1800a1038  jnz     short loc_1800A1067
0x1800a103a  mov     ecx, [r14+10h]
0x1800a103e  lea     eax, [r13+5]
0x1800a1042  mul     rcx
0x1800a1045  mov     rbx, rax
0x1800a1048  cmovo   rbx, r13
0x1800a104c  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800a1052  mov     rcx, rbx; Size
0x1800a1055  test    eax, eax
0x1800a1057  jz      short loc_1800A1061
0x1800a1059  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a105f  jmp     short loc_1800A1067
0x1800a1061  call    cs:malloc
0x1800a1067  mov     [rbp+130h+var_170], rax
0x1800a106b  cmp     [rbp+130h+arg_28], r12
0x1800a1072  jz      short loc_1800A1079
0x1800a1074  mov     r13, r12
0x1800a1077  jmp     short loc_1800A10AA
0x1800a1079  mov     ecx, [r14+10h]
0x1800a107d  mov     eax, 4
0x1800a1082  mul     rcx
0x1800a1085  mov     rbx, rax
0x1800a1088  cmovo   rbx, r13
0x1800a108c  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800a1092  mov     rcx, rbx; Size
0x1800a1095  test    eax, eax
0x1800a1097  jz      short loc_1800A10A1
0x1800a1099  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a109f  jmp     short loc_1800A10A7
0x1800a10a1  call    cs:malloc
0x1800a10a7  mov     r13, rax
0x1800a10aa  mov     ebx, [r14+10h]
0x1800a10ae  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800a10b4  mov     ecx, ebx; Size
0x1800a10b6  test    eax, eax
0x1800a10b8  jz      short loc_1800A10C2
0x1800a10ba  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1800a10c0  jmp     short loc_1800A10C8
0x1800a10c2  call    cs:malloc
0x1800a10c8  mov     [rbp+130h+var_178], rax
0x1800a10cc  mov     dword ptr [rbp+130h+arg_8], r12d
0x1800a10d3  cmp     [rbp+130h+arg_40], r12d
0x1800a10da  jz      short loc_1800A1105
0x1800a10dc  mov     r9d, 32h ; '2'
0x1800a10e2  mov     r8d, 40000000h
0x1800a10e8  lea     rdx, [rbp+130h+var_188]
0x1800a10ec  mov     rcx, r15
0x1800a10ef  call    ?assertPermissionMask@VsecurableObject@@QEBA?AVVHRESULT@@_KW4_ulstracelevel@@@Z; VsecurableObject::assertPermissionMask(unsigned __int64,_ulstracelevel)
0x1800a10f4  nop
0x1800a10f5  mov     esi, 1
0x1800a10fa  mov     [rbp+130h+var_1A8], esi
0x1800a10fd  cmp     [rax], r12d
0x1800a1100  mov     bl, sil
0x1800a1103  jl      short loc_1800A1108
0x1800a1105  mov     bl, r12b
0x1800a1108  test    sil, 1
0x1800a110c  jz      short loc_1800A111E
0x1800a110e  and     esi, 0FFFFFFFEh
0x1800a1111  mov     [rbp+130h+var_1A8], esi
0x1800a1114  lea     rcx, [rbp+130h+var_188]
0x1800a1118  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800a111e  test    bl, bl
0x1800a1120  mov     ebx, [rbp+130h+arg_40]
0x1800a1126  cmovnz  ebx, r12d
0x1800a112a  mov     [rbp+130h+arg_40], ebx
0x1800a1130  cmp     dword ptr [r14+10h], 0
0x1800a1135  jbe     loc_1800A1589
0x1800a113b  and     [rbp+130h+var_160], 0
0x1800a1140  mov     edx, r12d
0x1800a1143  mov     rcx, r14
0x1800a1146  call    cs:??AVpurlDirVvector@@QEBAPEAVVurlDir@@I@Z; VpurlDirVvector::operator[](uint)
0x1800a114c  mov     rcx, rax
0x1800a114f  call    cs:?Url@VurlDir@@QEBAAEBVVstringStorePath@@XZ; VurlDir::Url(void)
0x1800a1155  lea     rcx, [rbp+130h+var_1B0]
0x1800a1159  mov     [rbp+130h+var_188], rcx
0x1800a115d  mov     rdx, rax
0x1800a1160  lea     rcx, [rbp+130h+var_1B0]
0x1800a1164  call    cs:??0Vstring@@QEAA@AEBV0@@Z; Vstring::Vstring(Vstring const &)
0x1800a116a  nop
0x1800a116b  xor     ecx, ecx
0x1800a116d  cmp     [rbp+130h+arg_28], rcx
0x1800a1174  jnz     short loc_1800A117E
0x1800a1176  mov     eax, r12d
0x1800a1179  mov     [r13+rax*4+0], ecx
0x1800a117e  mov     eax, r12d
0x1800a1181  mov     rbx, [rbp+130h+var_178]
0x1800a1185  mov     [rax+rbx], cl
0x1800a1188  mov     rax, [rbp+130h+var_1B0]
0x1800a118c  cmp     [rax-4], ecx
0x1800a118f  jnz     short loc_1800A11AA
0x1800a1191  cmp     [rbp+130h+arg_18], cl
0x1800a1197  jnz     loc_1800A1787
0x1800a119d  lea     rax, [rbp+130h+var_1B0]
0x1800a11a1  mov     [rbp+130h+var_188], rax
0x1800a11a5  jmp     loc_1800A156C
0x1800a11aa  lea     rdx, [rbp+130h+var_C0]
0x1800a11ae  lea     rcx, [rbp+130h+var_1B0]
0x1800a11b2  call    cs:?dirName@?$VurlTemplate@VVstoreUrlSettings@@@@QEBA?AV1@XZ; VurlTemplate<VstoreUrlSettings>::dirName(void)
0x1800a11b8  nop
0x1800a11b9  lea     rcx, [rbp+130h+var_158]
0x1800a11bd  mov     [rbp+130h+var_188], rcx
0x1800a11c1  mov     rdx, rax
0x1800a11c4  lea     rcx, [rbp+130h+var_158]
0x1800a11c8  call    cs:??0Vstring@@QEAA@AEBV0@@Z; Vstring::Vstring(Vstring const &)
0x1800a11ce  nop
0x1800a11cf  or      esi, 4
0x1800a11d2  mov     [rbp+130h+var_1A8], esi
0x1800a11d5  and     esi, 0FFFFFFFBh
0x1800a11d8  mov     [rbp+130h+var_1A8], esi
0x1800a11db  or      esi, 2
0x1800a11de  mov     [rbp+130h+var_1A8], esi
0x1800a11e1  lea     rcx, [rbp+130h+var_C0]
0x1800a11e5  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1800a11eb  lea     r8, [rbp+130h+var_158]
0x1800a11ef  lea     rdx, [rbp+130h+var_B8]
0x1800a11f3  mov     rcx, r15
0x1800a11f6  call    ?serviceUrlToStoreUrl@VdbSubweb@@QEBA?AVVwstringStorePath@@AEBVVurlStorePath@@@Z; VdbSubweb::serviceUrlToStoreUrl(VurlStorePath const &)
0x1800a11fb  nop
0x1800a11fc  mov     rdx, [rax]
0x1800a11ff  lea     rcx, [rbp+130h+var_148]
0x1800a1203  call    cs:??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1800a1209  nop
0x1800a120a  lea     rax, [rbp+130h+var_1A0]
0x1800a120e  mov     [rbp+130h+var_188], rax
0x1800a1212  lea     rdx, [rbp+130h+var_148]
0x1800a1216  lea     rcx, [rbp+130h+var_1A0]
0x1800a121a  call    cs:??0Vstring@@QEAA@AEBV0@@Z; Vstring::Vstring(Vstring const &)
0x1800a1220  nop
0x1800a1221  lea     rcx, [rbp+130h+var_148]
0x1800a1225  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1800a122b  nop
0x1800a122c  lea     rcx, [rbp+130h+var_B8]
0x1800a1230  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1800a1236  and     esi, 0FFFFFFFDh
0x1800a1239  mov     [rbp+130h+var_1A8], esi
0x1800a123c  lea     rax, [rbp+130h+var_158]
0x1800a1240  mov     [rbp+130h+var_188], rax
0x1800a1244  lea     rcx, [rbp+130h+var_158]
0x1800a1248  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1800a124e  lea     rdx, [rbp+130h+var_190]
0x1800a1252  lea     rcx, [rbp+130h+var_1B0]
0x1800a1256  call    sub_1800279EC
0x1800a125b  nop
0x1800a125c  lea     r8, [rbp+130h+var_1B0]
0x1800a1260  lea     rdx, [rbp+130h+var_110]
0x1800a1264  mov     rcx, r15
0x1800a1267  call    ?serviceUrlToStoreUrl@VdbSubweb@@QEBA?AVVwstringStorePath@@AEBVVurlStorePath@@@Z; VdbSubweb::serviceUrlToStoreUrl(VurlStorePath const &)
0x1800a126c  nop
0x1800a126d  mov     rdx, [rax]
0x1800a1270  lea     rcx, [rbp+130h+var_140]
0x1800a1274  call    cs:??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1800a127a  nop
0x1800a127b  lea     rax, [rbp+130h+var_198]
0x1800a127f  mov     [rbp+130h+var_188], rax
0x1800a1283  lea     rdx, [rbp+130h+var_140]
0x1800a1287  lea     rcx, [rbp+130h+var_198]
0x1800a128b  call    cs:??0Vstring@@QEAA@AEBV0@@Z; Vstring::Vstring(Vstring const &)
0x1800a1291  nop
0x1800a1292  lea     rcx, [rbp+130h+var_140]
0x1800a1296  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1800a129c  nop
0x1800a129d  lea     rcx, [rbp+130h+var_110]
0x1800a12a1  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1800a12a7  cmp     [rbp+130h+arg_20], 0
0x1800a12ae  jnz     loc_1800A1450
0x1800a12b4  mov     rcx, r15; this
0x1800a12b7  call    ?getDoclibManager@VdbSubweb@@QEAAPEAVVdoclibManager@@XZ; VdbSubweb::getDoclibManager(void)
0x1800a12bc  mov     rcx, rax
0x1800a12bf  lea     rax, [rbp+130h+var_160]
0x1800a12c3  mov     [rsp+250h+var_230], rax
0x1800a12c8  xor     r9d, r9d
0x1800a12cb  lea     r8, [rbp+130h+var_1B0]
0x1800a12cf  lea     rdx, [rbp+130h+var_98]
0x1800a12d6  call    ?GetContainingList@VdoclibManager@@QEAA?AVVHRESULT@@AEBVVurlStorePath@@DPEAPEAUITPList@@@Z; VdoclibManager::GetContainingList(VurlStorePath const &,char,ITPList * *)
0x1800a12db  nop
0x1800a12dc  mov     ebx, [rax]
0x1800a12de  lea     rcx, [rbp+130h+var_98]
0x1800a12e5  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800a12eb  test    ebx, ebx
0x1800a12ed  jnz     loc_1800A16DE
0x1800a12f3  mov     rbx, [rbp+130h+var_160]
0x1800a12f7  mov     rax, [rbx]
0x1800a12fa  lea     rdx, [rbp+130h+var_150]
0x1800a12fe  mov     rcx, rbx
0x1800a1301  mov     rax, [rax+90h]
0x1800a1308  call    cs:__guard_dispatch_icall_fptr
0x1800a130e  mov     [rbp+130h+var_160], 800h
0x1800a1316  cmp     [rbp+130h+var_150], 1
0x1800a131a  jnz     short loc_1800A138C
0x1800a131c  mov     r9d, 2
0x1800a1322  xor     r8d, r8d
0x1800a1325  mov     rdx, rbx
0x1800a1328  lea     rcx, [rbp+130h+var_1B0]
0x1800a132c  call    ?IsDoclibItem@VdoclibManager@@SADAEBVVurlStorePath@@PEAUITPList@@PEADW4VtriState@@@Z; VdoclibManager::IsDoclibItem(VurlStorePath const &,ITPList *,char *,VtriState)
0x1800a1331  test    al, al
0x1800a1333  jz      short loc_1800A138C
0x1800a1335  cmp     [rbp+130h+arg_28], 0
0x1800a133d  jnz     short loc_1800A1384
0x1800a133f  mov     rax, [rbx]
0x1800a1342  mov     rcx, rbx
0x1800a1345  mov     rax, [rax+1E0h]
0x1800a134c  call    cs:__guard_dispatch_icall_fptr
0x1800a1352  test    eax, eax
0x1800a1354  jz      short loc_1800A1384
0x1800a1356  mov     eax, r12d
0x1800a1359  mov     dword ptr [r13+rax*4+0], 2
0x1800a1362  mov     rax, [rbx]
0x1800a1365  mov     rcx, rbx
0x1800a1368  mov     rax, [rax+248h]
0x1800a136f  call    cs:__guard_dispatch_icall_fptr
0x1800a1375  test    eax, eax
0x1800a1377  jz      short loc_1800A1384
0x1800a1379  mov     eax, r12d
0x1800a137c  mov     rcx, [rbp+130h+var_178]
0x1800a1380  mov     byte ptr [rax+rcx], 1
0x1800a1384  mov     [rbp+130h+var_160], 2
0x1800a138c  mov     rax, [rbx]
0x1800a138f  mov     rcx, rbx
0x1800a1392  mov     rax, [rax+10h]
0x1800a1396  call    cs:__guard_dispatch_icall_fptr
0x1800a139c  mov     [rbp+130h+var_188], r15
0x1800a13a0  lea     rdx, [rbp+130h+var_100]
0x1800a13a4  lea     rcx, [rbp+130h+var_1A0]
0x1800a13a8  call    cs:?getUnicode@Vstring@@QEBA?AVVwstring@@XZ; Vstring::getUnicode(void)
0x1800a13ae  nop
0x1800a13af  mov     rdx, rax
0x1800a13b2  lea     rcx, [rbp+130h+var_138]
0x1800a13b6  call    cs:??0Vwstring@@QEAA@AEBV0@@Z; Vwstring::Vwstring(Vwstring const &)
0x1800a13bc  nop
0x1800a13bd  or      esi, 40h
0x1800a13c0  mov     [rbp+130h+var_1A8], esi
0x1800a13c3  and     esi, 0FFFFFFBFh
0x1800a13c6  mov     [rbp+130h+var_1A8], esi
0x1800a13c9  or      esi, 20h
0x1800a13cc  mov     [rbp+130h+var_1A8], esi
0x1800a13cf  lea     rcx, [rbp+130h+var_100]
0x1800a13d3  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1800a13d9  mov     rax, [rbp+130h+var_138]
0x1800a13dd  mov     [rbp+130h+var_F0], rax
0x1800a13e1  xor     eax, eax
0x1800a13e3  mov     [rsp+250h+var_208], rax
0x1800a13e8  mov     [rsp+250h+var_210], rax
0x1800a13ed  mov     [rsp+250h+var_218], rax
0x1800a13f2  mov     [rsp+250h+var_220], rax
0x1800a13f7  mov     [rsp+250h+var_228], rax
0x1800a13fc  mov     byte ptr [rsp+250h+var_230], al
0x1800a1400  mov     r9, [rbp+130h+var_160]
0x1800a1404  lea     r8, [rbp+130h+var_F0]
0x1800a1408  lea     rdx, [rbp+130h+var_88]
0x1800a140f  lea     rcx, [rbp+130h+var_188]
0x1800a1413  call    ?getSecurityInfoFromStoreUrlAndCheckPerm@VsecurityAdministration@@QEAA?AVVHRESULT@@AEBVVwcharPtrStorePath@@_KDPEAU_GUID@@PEA_K3PEADPEAVVurlStorePath@@@Z; VsecurityAdministration::getSecurityInfoFromStoreUrlAndCheckPerm(VwcharPtrStorePath const &,unsigned __int64,char,_GUID *,unsigned __int64 *,unsigned __int64 *,char *,VurlStorePath *)
0x1800a1418  nop
0x1800a1419  mov     ebx, [rax]
0x1800a141b  lea     rcx, [rbp+130h+var_88]
0x1800a1422  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x1800a1428  and     esi, 0FFFFFFDFh
  ... truncated ...
```
