# Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun(Windows::Compat::Appraiser::WicaRun *,Windows::Compat::Appraiser::RunInfoData *,Windows::Compat::Appraiser::RunInfoDataStruct *,void *)

- ea: `0x180063c20`
- end: `0x180064227`
- name: `?InitializeComponentsIntoWicaRun@XmlAppraiser@Appraiser@Compat@Windows@@AEAAJPEAUWicaRun@234@PEAVRunInfoData@234@PEAURunInfoDataStruct@234@PEAX@Z`
- size: `1543`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::XmlAppraiser *__hidden this, struct Windows::Compat::Appraiser::WicaRun *, struct Windows::Compat::Appraiser::RunInfoData *, struct Windows::Compat::Appraiser::RunInfoDataStruct *, void *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006122c`
- `0x180061580`
- `0x180063c20`
- `0x180064f4c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180062c74`
- `0x180062ffc`
- `0x180063c20`
- `0x18008eac8`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180063e33`
- `KERNEL32!GetSystemTime` at `0x180063fd5`
- `KERNEL32!GetSystemTime` at `0x180063e33`
- `KERNEL32!GetSystemTime` at `0x180063fd5`

## string_xrefs

- `0x180063ce2`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063d47`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063e19`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063f01`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180063fac`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180064063`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800640b0`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800640f2`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180064136`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006418f`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800641d3`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180064098`: `Unable to initialize component and can't replace, swallowing.`
- `0x1800640e0`: `Error initializing component with type ID "%ls": [0x%x].`
- `0x1800641e4`: `Error initializing component with type ID "%ls": [0x%x].`
- `0x180063ce9`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x180063d3c`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x180063e03`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x180063eeb`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x18006405c`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x1800640a9`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x1800640eb`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x18006412b`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x180064184`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x1800641c8`: `Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun`
- `0x180063d53`: `Error initializing component with type ID "%ls", swallowing: [0x%x].`
- `0x180064051`: `Error initializing component with type ID "%ls", swallowing: [0x%x].`
- `0x180064178`: `Error initializing replacement components: [0x%x].`
- `0x1800641b4`: `Error initializing replacement components: [0x%x].`
- `0x18006411f`: `Unable to initialize component and can't replace.`
- `0x180063ef2`: `Error initializing replacement components, swallowing: [0x%x].`
- `0x18006415c`: `Error initializing replacement components, swallowing: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun(
        Windows::Compat::Appraiser::XmlAppraiser *this,
        struct Windows::Compat::Appraiser::WicaRun *a2,
        struct Windows::Compat::Appraiser::RunInfoData *a3,
        struct Windows::Compat::Appraiser::RunInfoDataStruct *a4,
        void *a5)
{
  struct Windows::Compat::Appraiser::RunInfoDataStruct *v5; // rbx
  unsigned __int64 v7; // rax
  struct Windows::Compat::Appraiser::WicaRun *v8; // rsi
  unsigned __int64 v10; // r12
  const wchar_t ***v11; // rdi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  const wchar_t **v14; // rdi
  const unsigned __int16 *v15; // rdx
  struct Windows::Compat::Appraiser::RunInfoData *RunInfoObjectByName; // r14
  unsigned int v17; // ebx
  char v18; // dl
  const char *v19; // rax
  int v20; // eax
  volatile signed __int64 *v21; // rcx
  void **v22; // rdx
  int v23; // esi
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  volatile signed __int64 *v27; // rcx
  void **v28; // rdx
  int v29; // edi
  int v30; // r8d
  int v31; // r9d
  const char *v32; // r9
  unsigned int v33; // ecx
  struct Windows::Compat::Appraiser::RunInfoDataStruct *v35; // [rsp+20h] [rbp-E0h]
  char *v36; // [rsp+30h] [rbp-D0h]
  __int64 v37; // [rsp+38h] [rbp-C8h]
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39[4]; // [rsp+64h] [rbp-9Ch] BYREF
  struct Windows::Compat::Appraiser::WicaRun *v40; // [rsp+68h] [rbp-98h]
  char *v41; // [rsp+70h] [rbp-90h] BYREF
  char *v42; // [rsp+78h] [rbp-88h] BYREF
  const char *v43; // [rsp+80h] [rbp-80h] BYREF
  const char *v44; // [rsp+88h] [rbp-78h] BYREF
  const char *v45; // [rsp+90h] [rbp-70h] BYREF
  void *v46; // [rsp+98h] [rbp-68h]
  struct Windows::Compat::Appraiser::RunInfoDataStruct *v47; // [rsp+A0h] [rbp-60h]
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME v49; // [rsp+C0h] [rbp-40h] BYREF
  struct _SYSTEMTIME v50; // [rsp+D0h] [rbp-30h] BYREF
  char v51[144]; // [rsp+E0h] [rbp-20h] BYREF
  char v52[144]; // [rsp+170h] [rbp+70h] BYREF

  v5 = a4;
  v46 = a5;
  v7 = *((_QWORD *)a3 + 13);
  v8 = a2;
  v47 = a4;
  v40 = a2;
  if ( !v7 )
    return 0;
  v10 = 0;
  while ( 1 )
  {
    v11 = 0;
    if ( v10 < v7 )
    {
      v41 = 0;
      v12 = *((_QWORD *)a3 + 12) * v10;
      if ( !is_mul_ok(*((_QWORD *)a3 + 12), v10)
        || (v13 = *((_QWORD *)a3 + 16), v11 = (const wchar_t ***)(v13 + v12), v13 + v12 < v13) )
      {
        v11 = 0;
      }
    }
    v14 = *v11;
    v15 = v14[2];
    if ( v15 )
    {
      RunInfoObjectByName = Windows::Compat::Appraiser::XmlAppraiser::GetRunInfoObjectByName(this, v15);
      if ( !RunInfoObjectByName )
      {
        v17 = -2147023728;
        v36 = (char *)v14[2];
        v18 = 66;
        v19 = "Could not get the RunInfo object for specified name %ls.";
LABEL_10:
        LODWORD(v35) = v17;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v18,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
          (const char *)v35,
          (int)v19,
          v36);
        return v17;
      }
    }
    else
    {
      RunInfoObjectByName = 0;
    }
    v20 = Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun(
            this,
            v8,
            a3,
            (struct Windows::Compat::Appraiser::ComponentInfo *)v14,
            v5,
            v46);
    v17 = v20;
    if ( !*((_BYTE *)v14 + 96) )
      break;
    if ( v20 < 0 )
    {
      LODWORD(v37) = v20;
      LODWORD(v35) = v20;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        86,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
        (const char *)v35,
        (int)"Error initializing component with type ID \"%ls\", swallowing: [0x%x].",
        (const char *)*v14,
        v37);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v51);
      v21 = (volatile signed __int64 *)v51;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v21 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v21,
        _InterlockedExchangeAdd64(v21 + 17, 0),
        v52);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v22);
      v23 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v38 = v17;
        v42 = v52;
        *(_DWORD *)v39 = 598;
        v43 = "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun";
        v44 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
        v45 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v41 = (char *)&v49;
        v49 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v23,
          (unsigned int)&unk_1802A1507,
          v24,
          v25,
          (__int64)&v41,
          (__int64)&v45,
          (__int64)v39,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v38,
          (__int64)&v42);
      }
      v8 = v40;
LABEL_23:
      if ( !RunInfoObjectByName || (v17 & 0x80000000) == 0 && v17 != 1 )
        goto LABEL_54;
      goto LABEL_26;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x256u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
        "Error initializing component with type ID \"%ls\", swallowing: [0x%x].",
        *v14,
        v20);
    if ( v17 != 1 )
      goto LABEL_23;
    if ( !RunInfoObjectByName )
    {
      if ( !Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode() )
      {
        LODWORD(v35) = -2147467259;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          89,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
          (const char *)v35,
          (int)"Unable to initialize component and can't replace, swallowing.",
          v36);
      }
      goto LABEL_54;
    }
LABEL_26:
    v26 = Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun(
            this,
            v8,
            RunInfoObjectByName,
            v47,
            v46);
    v17 = v26;
    if ( *((_BYTE *)v14 + 96) )
    {
      if ( v26 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          goto LABEL_54;
        v32 = "Error initializing replacement components, swallowing: [0x%x].";
        v33 = 631;
        goto LABEL_53;
      }
      LODWORD(v36) = v26;
      LODWORD(v35) = v26;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        119,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
        (const char *)v35,
        (int)"Error initializing replacement components, swallowing: [0x%x].",
        v36);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v51);
      v27 = (volatile signed __int64 *)v51;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v27 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v27,
        _InterlockedExchangeAdd64(v27 + 17, 0),
        v52);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v28);
      v29 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        *(_DWORD *)v39 = v17;
        v41 = v52;
        v45 = "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun";
        v44 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
        v38 = 631;
        v43 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v42 = (char *)&v50;
        v50 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v29,
          (unsigned int)&unk_1802A14A4,
          v30,
          v31,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v38,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)v39,
          (__int64)&v41);
      }
    }
    else
    {
      if ( v26 < 0 )
      {
        LODWORD(v36) = v26;
        v19 = "Error initializing replacement components: [0x%x].";
        v18 = 123;
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        v32 = "Error initializing replacement components: [0x%x].";
        v33 = 635;
LABEL_53:
        LODWORD(v35) = v26;
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          v33,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
          v32,
          v35);
      }
    }
LABEL_54:
    v7 = *((_QWORD *)a3 + 13);
    if ( ++v10 >= v7 )
      return 0;
    v5 = v47;
  }
  if ( v20 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x25Eu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
        "Error initializing component with type ID \"%ls\": [0x%x].",
        *v14,
        v20);
    if ( v17 != 1 )
      goto LABEL_23;
    if ( !RunInfoObjectByName )
    {
      LODWORD(v35) = -2147467259;
      v17 = -2147467259;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        98,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
        (const char *)v35,
        (int)"Unable to initialize component and can't replace.",
        v36);
      return v17;
    }
    goto LABEL_26;
  }
  LODWORD(v37) = v20;
  LODWORD(v35) = v20;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    94,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
    "Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun",
    (const char *)v35,
    (int)"Error initializing component with type ID \"%ls\": [0x%x].",
    (const char *)*v14,
    v37);
  return v17;
}

```

## disassembly

```asm
0x180063c20  push    rbp
0x180063c22  push    rbx
0x180063c23  push    rsi
0x180063c24  push    rdi
0x180063c25  push    r12
0x180063c27  push    r13
0x180063c29  push    r14
0x180063c2b  push    r15
0x180063c2d  lea     rbp, [rsp-118h]
0x180063c35  sub     rsp, 218h
0x180063c3c  mov     rax, cs:__security_cookie
0x180063c43  xor     rax, rsp
0x180063c46  mov     [rbp+150h+var_50], rax
0x180063c4d  mov     rax, [rbp+150h+arg_20]
0x180063c54  mov     rbx, r9
0x180063c57  mov     [rbp+150h+var_1B8], rax
0x180063c5b  mov     r15, r8
0x180063c5e  mov     rax, [r8+68h]
0x180063c62  mov     rsi, rdx
0x180063c65  mov     [rbp+150h+var_1B0], rbx
0x180063c69  mov     r13, rcx
0x180063c6c  mov     [rsp+250h+var_1E8], rdx
0x180063c71  test    rax, rax
0x180063c74  jz      loc_180064200
0x180063c7a  xor     r12d, r12d
0x180063c7d  xor     edi, edi
0x180063c7f  cmp     r12, rax
0x180063c82  jnb     short loc_180063CA7
0x180063c84  mov     rax, r12
0x180063c87  mov     [rsp+250h+var_1E0], rdi
0x180063c8c  mul     qword ptr [r15+60h]
0x180063c90  test    rdx, rdx
0x180063c93  jnz     short loc_180063CA5
0x180063c95  mov     rcx, [r15+80h]
0x180063c9c  lea     rdi, [rcx+rax]
0x180063ca0  cmp     rdi, rcx
0x180063ca3  jnb     short loc_180063CA7
0x180063ca5  xor     edi, edi
0x180063ca7  mov     rdi, [rdi]
0x180063caa  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180063cae  test    rdx, rdx
0x180063cb1  jz      short loc_180063D03
0x180063cb3  mov     rcx, r13; this
0x180063cb6  call    ?GetRunInfoObjectByName@XmlAppraiser@Appraiser@Compat@Windows@@AEAAPEAVRunInfoData@234@PEBG@Z; Windows::Compat::Appraiser::XmlAppraiser::GetRunInfoObjectByName(ushort const *)
0x180063cbb  mov     r14, rax
0x180063cbe  test    rax, rax
0x180063cc1  jnz     short loc_180063D06
0x180063cc3  mov     rax, [rdi+10h]
0x180063cc7  mov     ebx, 80070490h
0x180063ccc  mov     [rsp+250h+var_220], rax; char *
0x180063cd1  mov     edx, 242h; bool
0x180063cd6  lea     rax, aCouldNotGetThe; "Could not get the RunInfo object for sp"...
0x180063cdd  mov     [rsp+250h+var_228], rax; int
0x180063ce2  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063ce9  lea     r9, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063cf0  mov     dword ptr [rsp+250h+var_230], ebx; char *
0x180063cf4  mov     ecx, 1; this
0x180063cf9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180063cfe  jmp     loc_180064202
0x180063d03  xor     r14d, r14d
0x180063d06  mov     rax, [rbp+150h+var_1B8]
0x180063d0a  mov     r9, rdi; struct Windows::Compat::Appraiser::ComponentInfo *
0x180063d0d  mov     [rsp+250h+var_228], rax; void *
0x180063d12  mov     r8, r15; struct Windows::Compat::Appraiser::RunInfoData *
0x180063d15  mov     rdx, rsi; struct Windows::Compat::Appraiser::WicaRun *
0x180063d18  mov     [rsp+250h+var_230], rbx; struct Windows::Compat::Appraiser::RunInfoDataStruct *
0x180063d1d  mov     rcx, r13; this
0x180063d20  call    ?InitializeComponentIntoWicaRun@XmlAppraiser@Appraiser@Compat@Windows@@AEAAJPEAUWicaRun@234@PEAVRunInfoData@234@PEAUComponentInfo@234@PEAURunInfoDataStruct@234@PEAX@Z; Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentIntoWicaRun(Windows::Compat::Appraiser::WicaRun *,Windows::Compat::Appraiser::RunInfoData *,Windows::Compat::Appraiser::ComponentInfo *,Windows::Compat::Appraiser::RunInfoDataStruct *,void *)
0x180063d25  cmp     byte ptr [rdi+60h], 0
0x180063d29  mov     ebx, eax
0x180063d2b  jz      loc_1800640CB
0x180063d31  test    eax, eax
0x180063d33  jns     loc_180064044
0x180063d39  mov     rcx, [rdi]
0x180063d3c  lea     r9, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063d43  mov     dword ptr [rsp+250h+var_218], eax
0x180063d47  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063d4e  mov     [rsp+250h+var_220], rcx; char *
0x180063d53  lea     rax, aErrorInitializ_26; "Error initializing component with type "...
0x180063d5a  mov     [rsp+250h+var_228], rax; int
0x180063d5f  mov     ecx, 1; this
0x180063d64  mov     edx, 256h; bool
0x180063d69  mov     dword ptr [rsp+250h+var_230], ebx; char *
0x180063d6d  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180063d72  lea     rcx, [rbp+150h+var_170]; this
0x180063d76  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180063d7b  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180063d82  lea     rcx, [rbp+150h+var_170]
0x180063d86  test    rax, rax
0x180063d89  cmovnz  rcx, rax; this
0x180063d8d  xor     edx, edx
0x180063d8f  lock xadd [rcx+88h], rdx; unsigned __int64
0x180063d98  lea     r8, [rbp+150h+var_E0]; char *
0x180063d9c  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180063da1  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180063da8  jz      short loc_180063DB6
0x180063daa  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180063db1  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180063db6  mov     rsi, cs:qword_1802C9628
0x180063dbd  mov     eax, [rsi]
0x180063dbf  cmp     eax, 5
0x180063dc2  jbe     loc_180063E9D
0x180063dc8  mov     rcx, [rsi+18h]
0x180063dcc  mov     rdx, 200000000000h
0x180063dd6  mov     rax, [rsi+10h]
0x180063dda  test    rdx, rax
0x180063ddd  jz      loc_180063E9D
0x180063de3  mov     rax, rcx
0x180063de6  and     rax, rdx
0x180063de9  cmp     rax, rcx
0x180063dec  jnz     loc_180063E9D
0x180063df2  lea     rax, [rbp+150h+var_E0]
0x180063df6  mov     [rsp+250h+var_1F0], ebx
0x180063dfa  mov     [rsp+250h+var_1D8], rax
0x180063dff  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x180063e03  lea     rax, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063e0a  mov     dword ptr [rsp+250h+var_1EC], 256h
0x180063e12  mov     [rbp+150h+var_1D0], rax
0x180063e16  xorps   xmm0, xmm0
0x180063e19  lea     rax, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063e20  mov     [rbp+150h+var_1C8], rax
0x180063e24  lea     rax, szValueBuf
0x180063e2b  mov     [rbp+150h+var_1C0], rax
0x180063e2f  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x180063e33  call    cs:__imp_GetSystemTime
0x180063e39  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x180063e3d  lea     rax, [rbp+150h+var_190]
0x180063e41  mov     [rsp+250h+var_1E0], rax
0x180063e46  lea     rdx, unk_1802A1507
0x180063e4d  lea     rax, [rsp+250h+var_1D8]
0x180063e52  movdqa  [rbp+150h+var_190], xmm0
0x180063e57  mov     [rsp+250h+var_200], rax
0x180063e5c  mov     rcx, rsi
0x180063e5f  lea     rax, [rsp+250h+var_1F0]
0x180063e64  mov     [rsp+250h+var_208], rax
0x180063e69  lea     rax, [rbp+150h+var_1D0]
0x180063e6d  mov     [rsp+250h+var_210], rax
0x180063e72  lea     rax, [rbp+150h+var_1C8]
0x180063e76  mov     [rsp+250h+var_218], rax
0x180063e7b  lea     rax, [rsp+250h+var_1EC]
0x180063e80  mov     [rsp+250h+var_220], rax; char *
0x180063e85  lea     rax, [rbp+150h+var_1C0]
0x180063e89  mov     [rsp+250h+var_228], rax
0x180063e8e  lea     rax, [rsp+250h+var_1E0]
0x180063e93  mov     [rsp+250h+var_230], rax
0x180063e98  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063e9d  mov     rsi, [rsp+250h+var_1E8]
0x180063ea2  test    r14, r14
0x180063ea5  jz      loc_18006419B
0x180063eab  test    ebx, ebx
0x180063ead  js      short loc_180063EB8
0x180063eaf  cmp     ebx, 1
0x180063eb2  jnz     loc_18006419B
0x180063eb8  mov     rax, [rbp+150h+var_1B8]
0x180063ebc  mov     r8, r14; struct Windows::Compat::Appraiser::RunInfoData *
0x180063ebf  mov     r9, [rbp+150h+var_1B0]; struct Windows::Compat::Appraiser::RunInfoDataStruct *
0x180063ec3  mov     rdx, rsi; struct Windows::Compat::Appraiser::WicaRun *
0x180063ec6  mov     rcx, r13; this
0x180063ec9  mov     [rsp+250h+var_230], rax; void *
0x180063ece  call    ?InitializeComponentsIntoWicaRun@XmlAppraiser@Appraiser@Compat@Windows@@AEAAJPEAUWicaRun@234@PEAVRunInfoData@234@PEAURunInfoDataStruct@234@PEAX@Z; Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun(Windows::Compat::Appraiser::WicaRun *,Windows::Compat::Appraiser::RunInfoData *,Windows::Compat::Appraiser::RunInfoDataStruct *,void *)
0x180063ed3  cmp     byte ptr [rdi+60h], 0
0x180063ed7  mov     ebx, eax
0x180063ed9  jz      loc_18006416A
0x180063edf  test    eax, eax
0x180063ee1  jns     loc_180064152
0x180063ee7  mov     dword ptr [rsp+250h+var_220], eax; char *
0x180063eeb  lea     r14, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180063ef2  lea     rax, aErrorInitializ_24; "Error initializing replacement componen"...
0x180063ef9  mov     r9, r14; char *
0x180063efc  mov     [rsp+250h+var_228], rax; int
0x180063f01  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063f08  mov     edx, 277h; bool
0x180063f0d  mov     dword ptr [rsp+250h+var_230], ebx; char *
0x180063f11  mov     ecx, 1; this
0x180063f16  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180063f1b  lea     rcx, [rbp+150h+var_170]; this
0x180063f1f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180063f24  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180063f2b  lea     rcx, [rbp+150h+var_170]
0x180063f2f  test    rax, rax
0x180063f32  cmovnz  rcx, rax; this
0x180063f36  xor     edx, edx
0x180063f38  lock xadd [rcx+88h], rdx; unsigned __int64
0x180063f41  lea     r8, [rbp+150h+var_E0]; char *
0x180063f45  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180063f4a  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180063f51  jz      short loc_180063F5F
0x180063f53  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180063f5a  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180063f5f  mov     rdi, cs:qword_1802C9628
0x180063f66  mov     eax, [rdi]
0x180063f68  cmp     eax, 5
0x180063f6b  jbe     loc_18006419B
0x180063f71  mov     rcx, [rdi+18h]
0x180063f75  mov     rdx, 200000000000h
0x180063f7f  mov     rax, [rdi+10h]
0x180063f83  test    rdx, rax
0x180063f86  jz      loc_18006419B
0x180063f8c  mov     rax, rcx
0x180063f8f  and     rax, rdx
0x180063f92  cmp     rax, rcx
0x180063f95  jnz     loc_18006419B
0x180063f9b  lea     rax, [rbp+150h+var_E0]
0x180063f9f  mov     dword ptr [rsp+250h+var_1EC], ebx
0x180063fa3  mov     [rsp+250h+var_1E0], rax
0x180063fa8  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x180063fac  lea     rax, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180063fb3  mov     [rbp+150h+var_1C0], r14
0x180063fb7  mov     [rbp+150h+var_1C8], rax
0x180063fbb  xorps   xmm0, xmm0
0x180063fbe  lea     rax, szValueBuf
0x180063fc5  mov     [rsp+250h+var_1F0], 277h
0x180063fcd  mov     [rbp+150h+var_1D0], rax
0x180063fd1  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x180063fd5  call    cs:__imp_GetSystemTime
0x180063fdb  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x180063fdf  lea     rax, [rbp+150h+var_180]
0x180063fe3  mov     [rsp+250h+var_1D8], rax
0x180063fe8  lea     rdx, unk_1802A14A4
0x180063fef  lea     rax, [rsp+250h+var_1E0]
0x180063ff4  movdqa  [rbp+150h+var_180], xmm0
0x180063ff9  mov     [rsp+250h+var_200], rax
0x180063ffe  mov     rcx, rdi
0x180064001  lea     rax, [rsp+250h+var_1EC]
0x180064006  mov     [rsp+250h+var_208], rax
0x18006400b  lea     rax, [rbp+150h+var_1C0]
0x18006400f  mov     [rsp+250h+var_210], rax
0x180064014  lea     rax, [rbp+150h+var_1C8]
0x180064018  mov     [rsp+250h+var_218], rax
0x18006401d  lea     rax, [rsp+250h+var_1F0]
0x180064022  mov     [rsp+250h+var_220], rax
0x180064027  lea     rax, [rbp+150h+var_1D0]
0x18006402b  mov     [rsp+250h+var_228], rax
0x180064030  lea     rax, [rsp+250h+var_1D8]
0x180064035  mov     [rsp+250h+var_230], rax
0x18006403a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006403f  jmp     loc_18006419B
0x180064044  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006404a  test    al, 1
0x18006404c  jz      short loc_180064079
0x18006404e  mov     rax, [rdi]
0x180064051  lea     r9, aErrorInitializ_26; "Error initializing component with type "...
0x180064058  mov     dword ptr [rsp+250h+var_228], ebx
0x18006405c  lea     r8, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180064063  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006406a  mov     [rsp+250h+var_230], rax
0x18006406f  mov     ecx, 256h; unsigned int
0x180064074  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180064079  cmp     ebx, 1
0x18006407c  jnz     loc_180063EA2
0x180064082  test    r14, r14
0x180064085  jnz     loc_180063EB8
0x18006408b  call    ?IsMachineInSecurityMode@Utilities@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode(void)
0x180064090  test    al, al
0x180064092  jnz     loc_18006419B
0x180064098  lea     rax, aUnableToInitia; "Unable to initialize component and can'"...
0x18006409f  mov     edx, 259h; bool
0x1800640a4  mov     [rsp+250h+var_228], rax; int
0x1800640a9  lea     r9, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800640b0  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800640b7  mov     dword ptr [rsp+250h+var_230], 80004005h; char *
0x1800640bf  mov     ecx, ebx; this
0x1800640c1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800640c6  jmp     loc_18006419B
0x1800640cb  test    ebx, ebx
0x1800640cd  js      loc_1800641C5
0x1800640d3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800640d9  test    al, 1
0x1800640db  jz      short loc_180064108
0x1800640dd  mov     rax, [rdi]
0x1800640e0  lea     r9, aErrorInitializ_11; "Error initializing component with type "...
0x1800640e7  mov     dword ptr [rsp+250h+var_228], ebx
0x1800640eb  lea     r8, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800640f2  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800640f9  mov     [rsp+250h+var_230], rax
0x1800640fe  mov     ecx, 25Eh; unsigned int
0x180064103  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180064108  cmp     ebx, 1
0x18006410b  jnz     loc_180063EA2
0x180064111  test    r14, r14
0x180064114  jnz     loc_180063EB8
0x18006411a  mov     ecx, 80004005h
0x18006411f  lea     rax, aUnableToInitia_0; "Unable to initialize component and can'"...
0x180064126  mov     [rsp+250h+var_228], rax; int
0x18006412b  lea     r9, aWindowsCompatA_276; "Windows::Compat::Appraiser::XmlAppraise"...
0x180064132  mov     dword ptr [rsp+250h+var_230], ecx; char *
0x180064136  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006413d  mov     ebx, ecx
0x18006413f  mov     edx, 262h; bool
0x180064144  lea     ecx, [r14+1]; this
0x180064148  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006414d  jmp     loc_180064202
0x180064152  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180064158  test    al, 1
0x18006415a  jz      short loc_18006419B
0x18006415c  lea     r9, aErrorInitializ_24; "Error initializing replacement componen"...
0x180064163  mov     ecx, 277h
0x180064168  jmp     short loc_180064184
0x18006416a  test    ebx, ebx
0x18006416c  js      short loc_1800641B0
  ... truncated ...
```
