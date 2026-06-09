# getGenericSetupPath(char const *,Vpath &,ulong)

- ea: `0x180046d10`
- end: `0x180047389`
- name: `?getGenericSetupPath@@YAXPEBDAEAVVpath@@K@Z`
- size: `1657`
- prototype: `void __fastcall(const char *, struct Vpath *, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047390`
- `0x1800473d0`
- `0x180107580`
- `0x180138970`
- `0x180145000`
- `0x1801a64e0`

## callees

- `0x180046d10`
- `0x1801c1770`
- `0x1801c2da0`

## import_xrefs

- `onetutil!?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ` at `0x180046e30`
- `onetutil!?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ` at `0x180046e30`
- `onetutil!?releaseFPGlobalCriticalSection@VprocessGlobals@@SAXXZ` at `0x18004714e`
- `onetutil!?releaseFPGlobalCriticalSection@VprocessGlobals@@SAXXZ` at `0x18004714e`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047209`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047275`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x1800472df`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047343`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047209`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047275`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x1800472df`
- `onetutil!??1Vpath@@QEAA@XZ` at `0x180047343`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x1800471fe`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x18004726a`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x1800472d4`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x180047338`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x1800471fe`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x18004726a`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x1800472d4`
- `onetutil!??4Vpath@@QEAAAEAV0@AEBV0@@Z` at `0x180047338`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180046dbf`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180046df1`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180046dbf`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180046df1`
- `onetutil!?utf8Length@Vstring@@QEBAIXZ` at `0x180046e8d`
- `onetutil!?utf8Length@Vstring@@QEBAIXZ` at `0x180046e8d`
- `onetutil!??0Vregistry@@QEAA@PEBD@Z` at `0x180046d73`
- `onetutil!??0Vregistry@@QEAA@PEBD@Z` at `0x180046d73`
- `onetutil!??1Vregistry@@UEAA@XZ` at `0x180047170`
- `onetutil!??1Vregistry@@UEAA@XZ` at `0x180047170`
- `onetutil!??0VregistryValue@@QEAA@AEBVVstring@@@Z` at `0x180046d96`
- `onetutil!??0VregistryValue@@QEAA@AEBVVstring@@@Z` at `0x180046d96`
- `onetutil!??1VregistryValue@@QEAA@XZ` at `0x180047165`
- `onetutil!??1VregistryValue@@QEAA@XZ` at `0x180047165`
- `onetutil!?openKey@Vregistry@@QEAAPEAVVstatus@@K@Z` at `0x180046db1`
- `onetutil!?openKey@Vregistry@@QEAAPEAVVstatus@@K@Z` at `0x180046db1`
- `onetutil!?getValue@Vregistry@@UEAAPEAVVstatus@@AEAVVregistryValue@@KPEAJ@Z` at `0x180046de3`
- `onetutil!?getValue@Vregistry@@UEAAPEAVVstatus@@AEAVVregistryValue@@KPEAJ@Z` at `0x180046de3`
- `onetutil!?strValue@VregistryValue@@QEBA?AVVstring@@XZ` at `0x180046e3f`
- `onetutil!?strValue@VregistryValue@@QEBA?AVVstring@@XZ` at `0x180046e3f`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x1800471f1`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x18004725d`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x1800472c7`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x18004732b`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x1800471f1`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x18004725d`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x1800472c7`
- `onetutil!??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z` at `0x18004732b`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180046d86`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800471c2`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800471d5`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x18004722e`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047241`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047299`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800472ac`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800472ff`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047311`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180046d86`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800471c2`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800471d5`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x18004722e`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047241`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047299`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800472ac`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x1800472ff`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180047311`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180046da2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18004715a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047215`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047281`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800472eb`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18004734e`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047359`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180046da2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18004715a`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047215`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047281`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800472eb`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18004734e`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180047359`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046e54`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046e95`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046eb2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046ed0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046eee`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046fa1`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046fde`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047004`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18004703f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047065`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800470a0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800470c6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047101`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047128`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046e54`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046e95`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046eb2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046ed0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046eee`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046fa1`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180046fde`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047004`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18004703f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047065`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800470a0`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800470c6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047101`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180047128`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046ea1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046ebf`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046edd`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046efb`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046ea1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046ebf`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046edd`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180046efb`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046e79`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046fc8`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046ffe`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047029`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x18004705f`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x18004708a`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1800470c0`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1800470eb`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047121`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047148`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046e79`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046fc8`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180046ffe`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047029`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x18004705f`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x18004708a`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1800470c0`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1800470eb`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047121`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180047148`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046e81`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046fd0`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046ff6`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047031`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047057`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047092`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1800470b8`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1800470f3`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047119`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047140`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046e81`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046fd0`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180046ff6`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047031`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047057`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047092`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1800470b8`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1800470f3`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047119`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x180047140`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x180046e5e`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x180046fad`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x18004700e`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x18004706f`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x1800470d0`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x180046e5e`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x180046fad`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x18004700e`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x18004706f`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x1800470d0`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f63`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f73`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f83`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f94`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f63`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f73`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f83`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x180046f94`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ea9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ec7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ee5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046f03`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ea9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ec7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046ee5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180046f03`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f1b`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f30`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f45`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f5a`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f1b`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f30`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f45`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180046f5a`

## string_xrefs

- `0x180046d68`: `SOFTWARE\\Microsoft\Shared Tools\Web Server Extensions\16.0`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall getGenericSetupPath(const char *a1, struct Vpath *a2, int a3)
{
  struct Vpath *v4; // rbx
  const char *v5; // rax
  struct Vstatus *Value; // rdi
  struct VprocessGlobals *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rdi
  char *v10; // rax
  char *v11; // r13
  char *v12; // rax
  char *v13; // r12
  char *v14; // rax
  char *v15; // r15
  char *v16; // rax
  char *v17; // r14
  Vpath *v18; // rax
  Vstring *v19; // rcx
  Vpath *v20; // rax
  Vpath *v21; // rax
  Vpath *v22; // rax
  char v23; // [rsp+38h] [rbp-D0h]
  bool v24; // [rsp+39h] [rbp-CFh]
  char v25; // [rsp+3Ch] [rbp-CCh]
  bool v26; // [rsp+3Dh] [rbp-CBh]
  char v27; // [rsp+40h] [rbp-C8h]
  bool v28; // [rsp+41h] [rbp-C7h]
  char v29; // [rsp+44h] [rbp-C4h]
  bool v30; // [rsp+45h] [rbp-C3h]
  char IsCurrentHeapLocal; // [rsp+48h] [rbp-C0h]
  bool v32; // [rsp+49h] [rbp-BFh]
  char *Source; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v34[8]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v35[8]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v36[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v37[8]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v38[8]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v39; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v40[8]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v41[8]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v42[8]; // [rsp+98h] [rbp-70h] BYREF
  const char *v43; // [rsp+A0h] [rbp-68h]
  struct Vpath *v44; // [rsp+A8h] [rbp-60h]
  __int64 v45; // [rsp+B0h] [rbp-58h]
  _BYTE v46[40]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v47[24]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v48[24]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v49[24]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v50[32]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v51[160]; // [rsp+148h] [rbp+40h] BYREF

  v45 = -2;
  v4 = a2;
  v44 = a2;
  v5 = a1;
  v43 = a1;
  if ( !qword_18036CFE0 )
  {
    Vregistry::Vregistry((Vregistry *)v51, "SOFTWARE\\\\Microsoft\\Shared Tools\\Web Server Extensions\\16.0");
    Vstring::Vstring((Vstring *)v34, "Location");
    VregistryValue::VregistryValue((VregistryValue *)v46, (const struct Vstring *)v34);
    Vstring::~Vstring((Vstring *)v34);
    Value = Vregistry::openKey((Vregistry *)v51, 0x20019u);
    if ( Value )
    {
      v7 = VgetProcessGlobals();
      v8 = 3249867;
    }
    else
    {
      Value = Vregistry::getValue((Vregistry *)v51, (struct VregistryValue *)v46, 1u, 0);
      if ( !Value )
      {
        VprocessGlobals::acquireFPGlobalCriticalSection();
        VregistryValue::strValue(v46, &Source);
        if ( !qword_18036CFE0 )
        {
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
          {
            IsCurrentHeapLocal = COWSAllocator::IsCurrentHeapLocal();
            v32 = IsCurrentHeapLocal == 1;
            if ( IsCurrentHeapLocal == 1 )
              COWSAllocator::UseGlobalHeap();
          }
          v9 = Vstring::utf8Length((Vstring *)&Source);
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
            v10 = (char *)COWSAllocator::AllocCurrentHeap((unsigned int)v9);
          else
            v10 = (char *)malloc((unsigned int)v9);
          v11 = v10;
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
            v12 = (char *)COWSAllocator::AllocCurrentHeap(v9);
          else
            v12 = (char *)malloc(v9);
          v13 = v12;
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
            v14 = (char *)COWSAllocator::AllocCurrentHeap(v9);
          else
            v14 = (char *)malloc(v9);
          v15 = v14;
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
            v16 = (char *)COWSAllocator::AllocCurrentHeap(v9);
          else
            v16 = (char *)malloc(v9);
          v17 = v16;
          strncpy_s(v11, v9, Source, 0xFFFFFFFFFFFFFFFFuLL);
          strncpy_s(v13, v9, Source, 0xFFFFFFFFFFFFFFFFuLL);
          strncpy_s(v15, v9, Source, 0xFFFFFFFFFFFFFFFFuLL);
          strncpy_s(v17, v9, Source, 0xFFFFFFFFFFFFFFFFuLL);
          v13[Vstrlen(v13) - 1] = 52;
          v15[Vstrlen(v15) - 1] = 50;
          v17[Vstrlen(v17) - 2] = 54;
          v17[Vstrlen(v17) - 1] = 48;
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
          {
            v23 = COWSAllocator::IsCurrentHeapLocal();
            v24 = v23 == 1;
            if ( v23 == 1 )
              COWSAllocator::UseGlobalHeap();
          }
          _InterlockedExchange64(&qword_18036CFD8, (__int64)v17);
          if ( (unsigned int)COWSAllocator::QueryNewMode() && v24 )
          {
            if ( v23 )
              COWSAllocator::UseLocalHeap();
            else
              COWSAllocator::UseGlobalHeap();
          }
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
          {
            v25 = COWSAllocator::IsCurrentHeapLocal();
            v26 = v25 == 1;
            if ( v25 == 1 )
              COWSAllocator::UseGlobalHeap();
          }
          _InterlockedExchange64(&qword_18036CFD0, (__int64)v15);
          if ( (unsigned int)COWSAllocator::QueryNewMode() && v26 )
          {
            if ( v25 )
              COWSAllocator::UseLocalHeap();
            else
              COWSAllocator::UseGlobalHeap();
          }
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
          {
            v27 = COWSAllocator::IsCurrentHeapLocal();
            v28 = v27 == 1;
            if ( v27 == 1 )
              COWSAllocator::UseGlobalHeap();
          }
          _InterlockedExchange64(&qword_18036CFC8, (__int64)v13);
          if ( (unsigned int)COWSAllocator::QueryNewMode() && v28 )
          {
            if ( v27 )
              COWSAllocator::UseLocalHeap();
            else
              COWSAllocator::UseGlobalHeap();
          }
          if ( (unsigned int)COWSAllocator::QueryNewMode() )
          {
            v29 = COWSAllocator::IsCurrentHeapLocal();
            v30 = v29 == 1;
            if ( v29 == 1 )
              COWSAllocator::UseGlobalHeap();
          }
          _InterlockedExchange64(&qword_18036CFE0, (__int64)v11);
          if ( (unsigned int)COWSAllocator::QueryNewMode() && v30 )
          {
            if ( v29 )
              COWSAllocator::UseLocalHeap();
            else
              COWSAllocator::UseGlobalHeap();
          }
          if ( (unsigned int)COWSAllocator::QueryNewMode() && v32 )
          {
            if ( IsCurrentHeapLocal )
              COWSAllocator::UseLocalHeap();
            else
              COWSAllocator::UseGlobalHeap();
          }
        }
        VprocessGlobals::releaseFPGlobalCriticalSection();
        Vstring::~Vstring((Vstring *)&Source);
        goto LABEL_61;
      }
      v7 = VgetProcessGlobals();
      v8 = 3249868;
    }
    (*(void (__fastcall **)(struct VprocessGlobals *, __int64, _QWORD, __int64, struct Vstatus *))(*(_QWORD *)v7 + 32LL))(
      v7,
      v8,
      0,
      1,
      Value);
    (**(void (__fastcall ***)(struct Vstatus *, __int64))Value)(Value, 1);
LABEL_61:
    VregistryValue::~VregistryValue((VregistryValue *)v46);
    Vregistry::~Vregistry((Vregistry *)v51);
    v5 = v43;
    v4 = v44;
  }
  switch ( a3 )
  {
    case 2:
    case 11:
      Vstring::Vstring((Vstring *)v42, v5);
      Vstring::Vstring((Vstring *)v41, (const char *)qword_18036CFD8);
      v22 = Vpath::Vpath((Vpath *)v50, (const struct Vstring *)v41, (const struct Vstring *)v42, qword_18020E990);
      Vpath::operator=(v4, v22);
      Vpath::~Vpath((Vpath *)v50);
      Vstring::~Vstring((Vstring *)v41);
      v19 = (Vstring *)v42;
      goto LABEL_74;
    case 3:
    case 12:
      Vstring::Vstring((Vstring *)v40, v5);
      Vstring::Vstring((Vstring *)&v39, (const char *)qword_18036CFD0);
      v21 = Vpath::Vpath((Vpath *)v49, (const struct Vstring *)&v39, (const struct Vstring *)v40, qword_18020E990);
      Vpath::operator=(v4, v21);
      Vpath::~Vpath((Vpath *)v49);
      Vstring::~Vstring((Vstring *)&v39);
      v19 = (Vstring *)v40;
      goto LABEL_74;
    case 4:
    case 14:
      Vstring::Vstring((Vstring *)v38, v5);
      Vstring::Vstring((Vstring *)v37, (const char *)qword_18036CFC8);
      v20 = Vpath::Vpath((Vpath *)v48, (const struct Vstring *)v37, (const struct Vstring *)v38, qword_18020E990);
      Vpath::operator=(v4, v20);
      Vpath::~Vpath((Vpath *)v48);
      Vstring::~Vstring((Vstring *)v37);
      v19 = (Vstring *)v38;
      goto LABEL_74;
    case 5:
    case 15:
      Vstring::Vstring((Vstring *)v36, v5);
      Vstring::Vstring((Vstring *)v35, (const char *)qword_18036CFE0);
      v18 = Vpath::Vpath((Vpath *)v47, (const struct Vstring *)v35, (const struct Vstring *)v36, qword_18020E990);
      Vpath::operator=(v4, v18);
      Vpath::~Vpath((Vpath *)v47);
      Vstring::~Vstring((Vstring *)v35);
      v19 = (Vstring *)v36;
LABEL_74:
      Vstring::~Vstring(v19);
      break;
  }
}

```

## disassembly

```asm
0x180046d10  mov     rax, rsp
0x180046d13  push    rbp
0x180046d14  push    rsi
0x180046d15  push    rdi
0x180046d16  push    r12
0x180046d18  push    r13
0x180046d1a  push    r14
0x180046d1c  push    r15
0x180046d1e  lea     rbp, [rax-128h]
0x180046d25  sub     rsp, 1F0h
0x180046d2c  mov     [rbp+120h+var_178], 0FFFFFFFFFFFFFFFEh
0x180046d34  mov     [rax+18h], rbx
0x180046d38  mov     rax, cs:__security_cookie
0x180046d3f  xor     rax, rsp
0x180046d42  mov     [rbp+120h+var_40], rax
0x180046d49  mov     esi, r8d
0x180046d4c  mov     rbx, rdx
0x180046d4f  mov     [rbp+120h+var_180], rdx
0x180046d53  mov     rax, rcx
0x180046d56  mov     [rbp+120h+var_188], rcx
0x180046d5a  cmp     cs:qword_18036CFE0, 0
0x180046d62  jnz     loc_18004717E
0x180046d68  lea     rdx, aSoftwareMicros; "SOFTWARE\\\\Microsoft\\Shared Tools\\We"...
0x180046d6f  lea     rcx, [rbp+120h+var_E0]
0x180046d73  call    cs:??0Vregistry@@QEAA@PEBD@Z; Vregistry::Vregistry(char const *)
0x180046d79  nop
0x180046d7a  lea     rdx, ValueName; "Location"
0x180046d81  lea     rcx, [rsp+220h+var_1D0]
0x180046d86  call    cs:??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x180046d8c  nop
0x180046d8d  lea     rdx, [rsp+220h+var_1D0]
0x180046d92  lea     rcx, [rbp+120h+var_170]
0x180046d96  call    cs:??0VregistryValue@@QEAA@AEBVVstring@@@Z; VregistryValue::VregistryValue(Vstring const &)
0x180046d9c  nop
0x180046d9d  lea     rcx, [rsp+220h+var_1D0]
0x180046da2  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x180046da8  mov     edx, 20019h
0x180046dad  lea     rcx, [rbp+120h+var_E0]
0x180046db1  call    cs:?openKey@Vregistry@@QEAAPEAVVstatus@@K@Z; Vregistry::openKey(ulong)
0x180046db7  mov     rdi, rax
0x180046dba  test    rax, rax
0x180046dbd  jz      short loc_180046DD1
0x180046dbf  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x180046dc5  mov     ebx, 1
0x180046dca  mov     edx, 3196CBh
0x180046dcf  jmp     short loc_180046DFC
0x180046dd1  xor     r9d, r9d
0x180046dd4  lea     ebx, [r9+1]
0x180046dd8  mov     r8d, ebx
0x180046ddb  lea     rdx, [rbp+120h+var_170]
0x180046ddf  lea     rcx, [rbp+120h+var_E0]
0x180046de3  call    cs:?getValue@Vregistry@@UEAAPEAVVstatus@@AEAVVregistryValue@@KPEAJ@Z; Vregistry::getValue(VregistryValue &,ulong,long *)
0x180046de9  mov     rdi, rax
0x180046dec  test    rax, rax
0x180046def  jz      short loc_180046E30
0x180046df1  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x180046df7  mov     edx, 3196CCh
0x180046dfc  mov     r10, rax
0x180046dff  mov     rcx, [rax]
0x180046e02  xor     r8d, r8d
0x180046e05  mov     [rsp+20h], rdi
0x180046e0a  mov     rax, [rcx+20h]
0x180046e0e  mov     r9d, ebx
0x180046e11  mov     rcx, r10
0x180046e14  call    cs:__guard_dispatch_icall_fptr
0x180046e1a  mov     rax, [rdi]
0x180046e1d  mov     edx, ebx
0x180046e1f  mov     rcx, rdi
0x180046e22  mov     rax, [rax]
0x180046e25  call    cs:__guard_dispatch_icall_fptr
0x180046e2b  jmp     loc_180047161
0x180046e30  call    cs:?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ; VprocessGlobals::acquireFPGlobalCriticalSection(void)
0x180046e36  lea     rdx, [rsp+220h+Source]
0x180046e3b  lea     rcx, [rbp+120h+var_170]
0x180046e3f  call    cs:?strValue@VregistryValue@@QEBA?AVVstring@@XZ; VregistryValue::strValue(void)
0x180046e45  nop
0x180046e46  cmp     cs:qword_18036CFE0, 0
0x180046e4e  jnz     loc_18004714E
0x180046e54  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046e5a  test    eax, eax
0x180046e5c  jz      short loc_180046E88
0x180046e5e  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180046e64  mov     byte ptr [rsp+220h+var_1E0], al
0x180046e68  cmp     al, bl
0x180046e6a  setz    cl
0x180046e6d  mov     byte ptr [rsp+220h+var_1E0+1], cl
0x180046e71  test    cl, cl
0x180046e73  jz      short loc_180046E88
0x180046e75  test    al, al
0x180046e77  jz      short loc_180046E81
0x180046e79  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180046e7f  jmp     short loc_180046E88
0x180046e81  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180046e87  nop
0x180046e88  lea     rcx, [rsp+220h+Source]
0x180046e8d  call    cs:?utf8Length@Vstring@@QEBAIXZ; Vstring::utf8Length(void)
0x180046e93  mov     edi, eax
0x180046e95  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046e9b  mov     ecx, edi; Size
0x180046e9d  test    eax, eax
0x180046e9f  jz      short loc_180046EA9
0x180046ea1  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180046ea7  jmp     short loc_180046EAF
0x180046ea9  call    cs:malloc
0x180046eaf  mov     r13, rax
0x180046eb2  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046eb8  mov     rcx, rdi; Size
0x180046ebb  test    eax, eax
0x180046ebd  jz      short loc_180046EC7
0x180046ebf  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180046ec5  jmp     short loc_180046ECD
0x180046ec7  call    cs:malloc
0x180046ecd  mov     r12, rax
0x180046ed0  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046ed6  mov     rcx, rdi; Size
0x180046ed9  test    eax, eax
0x180046edb  jz      short loc_180046EE5
0x180046edd  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180046ee3  jmp     short loc_180046EEB
0x180046ee5  call    cs:malloc
0x180046eeb  mov     r15, rax
0x180046eee  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046ef4  mov     rcx, rdi; Size
0x180046ef7  test    eax, eax
0x180046ef9  jz      short loc_180046F03
0x180046efb  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180046f01  jmp     short loc_180046F09
0x180046f03  call    cs:malloc
0x180046f09  mov     r14, rax
0x180046f0c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180046f10  mov     r8, [rsp+220h+Source]; Source
0x180046f15  mov     rdx, rdi; SizeInBytes
0x180046f18  mov     rcx, r13; Destination
0x180046f1b  call    cs:strncpy_s
0x180046f21  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180046f25  mov     r8, [rsp+220h+Source]; Source
0x180046f2a  mov     rdx, rdi; SizeInBytes
0x180046f2d  mov     rcx, r12; Destination
0x180046f30  call    cs:strncpy_s
0x180046f36  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180046f3a  mov     r8, [rsp+220h+Source]; Source
0x180046f3f  mov     rdx, rdi; SizeInBytes
0x180046f42  mov     rcx, r15; Destination
0x180046f45  call    cs:strncpy_s
0x180046f4b  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180046f4f  mov     r8, [rsp+220h+Source]; Source
0x180046f54  mov     rdx, rdi; SizeInBytes
0x180046f57  mov     rcx, r14; Destination
0x180046f5a  call    cs:strncpy_s
0x180046f60  mov     rcx, r12
0x180046f63  call    cs:?Vstrlen@@YAIPEBD@Z; Vstrlen(char const *)
0x180046f69  sub     eax, ebx
0x180046f6b  mov     byte ptr [rax+r12], 34h ; '4'
0x180046f70  mov     rcx, r15
0x180046f73  call    cs:?Vstrlen@@YAIPEBD@Z; Vstrlen(char const *)
0x180046f79  sub     eax, ebx
0x180046f7b  mov     byte ptr [rax+r15], 32h ; '2'
0x180046f80  mov     rcx, r14
0x180046f83  call    cs:?Vstrlen@@YAIPEBD@Z; Vstrlen(char const *)
0x180046f89  sub     eax, 2
0x180046f8c  mov     byte ptr [rax+r14], 36h ; '6'
0x180046f91  mov     rcx, r14
0x180046f94  call    cs:?Vstrlen@@YAIPEBD@Z; Vstrlen(char const *)
0x180046f9a  sub     eax, ebx
0x180046f9c  mov     byte ptr [rax+r14], 30h ; '0'
0x180046fa1  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046fa7  xor     edi, edi
0x180046fa9  test    eax, eax
0x180046fab  jz      short loc_180046FD7
0x180046fad  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180046fb3  mov     [rsp+220h+var_1F0], al
0x180046fb7  cmp     al, bl
0x180046fb9  setz    cl
0x180046fbc  mov     [rsp+220h+var_1EF], cl
0x180046fc0  test    cl, cl
0x180046fc2  jz      short loc_180046FD7
0x180046fc4  test    al, al
0x180046fc6  jz      short loc_180046FD0
0x180046fc8  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180046fce  jmp     short loc_180046FD7
0x180046fd0  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180046fd6  nop
0x180046fd7  xchg    r14, cs:qword_18036CFD8
0x180046fde  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180046fe4  test    eax, eax
0x180046fe6  jz      short loc_180047004
0x180046fe8  cmp     [rsp+220h+var_1EF], dil
0x180046fed  jz      short loc_180047004
0x180046fef  cmp     [rsp+220h+var_1F0], dil
0x180046ff4  jz      short loc_180046FFE
0x180046ff6  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180046ffc  jmp     short loc_180047004
0x180046ffe  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180047004  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x18004700a  test    eax, eax
0x18004700c  jz      short loc_180047038
0x18004700e  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180047014  mov     [rsp+220h+var_1EC], al
0x180047018  cmp     al, bl
0x18004701a  setz    cl
0x18004701d  mov     [rsp+220h+var_1EB], cl
0x180047021  test    cl, cl
0x180047023  jz      short loc_180047038
0x180047025  test    al, al
0x180047027  jz      short loc_180047031
0x180047029  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x18004702f  jmp     short loc_180047038
0x180047031  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180047037  nop
0x180047038  xchg    r15, cs:qword_18036CFD0
0x18004703f  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180047045  test    eax, eax
0x180047047  jz      short loc_180047065
0x180047049  cmp     [rsp+220h+var_1EB], dil
0x18004704e  jz      short loc_180047065
0x180047050  cmp     [rsp+220h+var_1EC], dil
0x180047055  jz      short loc_18004705F
0x180047057  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x18004705d  jmp     short loc_180047065
0x18004705f  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180047065  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x18004706b  test    eax, eax
0x18004706d  jz      short loc_180047099
0x18004706f  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180047075  mov     [rsp+220h+var_1E8], al
0x180047079  cmp     al, bl
0x18004707b  setz    cl
0x18004707e  mov     [rsp+220h+var_1E7], cl
0x180047082  test    cl, cl
0x180047084  jz      short loc_180047099
0x180047086  test    al, al
0x180047088  jz      short loc_180047092
0x18004708a  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180047090  jmp     short loc_180047099
0x180047092  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180047098  nop
0x180047099  xchg    r12, cs:qword_18036CFC8
0x1800470a0  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800470a6  test    eax, eax
0x1800470a8  jz      short loc_1800470C6
0x1800470aa  cmp     [rsp+220h+var_1E7], dil
0x1800470af  jz      short loc_1800470C6
0x1800470b1  cmp     [rsp+220h+var_1E8], dil
0x1800470b6  jz      short loc_1800470C0
0x1800470b8  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800470be  jmp     short loc_1800470C6
0x1800470c0  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800470c6  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1800470cc  test    eax, eax
0x1800470ce  jz      short loc_1800470FA
0x1800470d0  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1800470d6  mov     [rsp+3Ch], al
0x1800470da  cmp     al, bl
0x1800470dc  setz    cl
0x1800470df  mov     [rsp+3Dh], cl
0x1800470e3  test    cl, cl
0x1800470e5  jz      short loc_1800470FA
0x1800470e7  test    al, al
0x1800470e9  jz      short loc_1800470F3
0x1800470eb  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1800470f1  jmp     short loc_1800470FA
0x1800470f3  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1800470f9  nop
0x1800470fa  xchg    r13, cs:qword_18036CFE0
0x180047101  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x180047107  test    eax, eax
0x180047109  jz      short loc_180047128
0x18004710b  cmp     [rsp+3Dh], dil
0x180047110  jz      short loc_180047128
0x180047112  cmp     [rsp+3Ch], dil
0x180047117  jz      short loc_180047121
0x180047119  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x18004711f  jmp     short loc_180047128
0x180047121  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180047127  nop
0x180047128  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x18004712e  test    eax, eax
0x180047130  jz      short loc_18004714E
0x180047132  cmp     byte ptr [rsp+220h+var_1E0+1], dil
0x180047137  jz      short loc_18004714E
0x180047139  cmp     byte ptr [rsp+220h+var_1E0], dil
0x18004713e  jz      short loc_180047148
0x180047140  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180047146  jmp     short loc_18004714E
0x180047148  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x18004714e  call    cs:?releaseFPGlobalCriticalSection@VprocessGlobals@@SAXXZ; VprocessGlobals::releaseFPGlobalCriticalSection(void)
0x180047154  nop
0x180047155  lea     rcx, [rsp+220h+Source]
0x18004715a  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x180047160  nop
0x180047161  lea     rcx, [rbp+120h+var_170]
0x180047165  call    cs:??1VregistryValue@@QEAA@XZ; VregistryValue::~VregistryValue(void)
0x18004716b  nop
0x18004716c  lea     rcx, [rbp+120h+var_E0]
0x180047170  call    cs:??1Vregistry@@UEAA@XZ; Vregistry::~Vregistry(void)
0x180047176  mov     rax, [rbp+120h+var_188]
0x18004717a  mov     rbx, [rbp+120h+var_180]
0x18004717e  cmp     esi, 2
0x180047181  jz      loc_1800472F8
0x180047187  cmp     esi, 0Bh
  ... truncated ...
```
