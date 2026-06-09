# Microsoft::Diagnostics::SoftLandingActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800a81a0`
- end: `0x1800a86ed`
- name: `?ParseFromXml@SoftLandingActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `1357`
- prototype: `int(Microsoft::Diagnostics::SoftLandingActionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180037b40`
- `0x180040558`
- `0x180064e8c`
- `0x1800653d0`
- `0x180080da4`
- `0x18008b254`
- `0x18009dec0`
- `0x1800a3760`
- `0x1800a37b0`
- `0x1800a3d14`
- `0x1800a6438`
- `0x1800a658c`
- `0x1800a81a0`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a82be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a842e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a82be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a842e`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a84e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a84e4`

## string_xrefs

- `0x1800a826f`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a82fd`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a83a4`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a83df`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a8474`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a8502`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a854f`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a85a5`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a85e1`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a8631`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a868b`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a86b0`: `onecore\base\telemetry\utc\service\scenarios\actions\softlandingaction.cpp`
- `0x1800a84cd`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SoftLandingActionDef::ParseFromXml(
        Microsoft::Diagnostics::SoftLandingActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r10
  char v11; // r14
  char v12; // r15
  unsigned int Element; // eax
  unsigned int v14; // ebx
  int CurrentElementName; // eax
  unsigned int v16; // ebx
  _QWORD *v18; // rdx
  int v19; // ebx
  __int64 v20; // r8
  int v21; // eax
  unsigned int v22; // r14d
  char *v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  _QWORD *v26; // rdx
  int v27; // ebx
  __int64 v28; // r8
  int InnerText; // eax
  const char *v30; // r9
  unsigned int v31; // ebx
  _QWORD *v32; // rcx
  int v33; // eax
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+28h] [rbp-C0h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD v43[2]; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int64 v45; // [rsp+60h] [rbp-88h]
  unsigned __int64 v46; // [rsp+68h] [rbp-80h]
  _QWORD v47[4]; // [rsp+70h] [rbp-78h] BYREF
  __int128 v48; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    &v40,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v41, (char *)a3 + 112, (unsigned __int16)v40);
  v9 = std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(v41, v6, v7, v8);
  std::wstring::_Assign<wchar_t>(v9 + 8, v10, *((_QWORD *)this + 13));
  v11 = 0;
  v12 = 0;
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
  {
    v38 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
        (const char *)(unsigned int)v38,
        v40);
      return v39;
    }
  }
  else
  {
    while ( 1 )
    {
      Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v14 = Element;
      if ( Element )
        break;
      std::wstring::wstring(v44);
      CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v44);
      v16 = CurrentElementName;
      if ( CurrentElementName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
          (const char *)(unsigned int)CurrentElementName,
          v40);
        std::wstring::_Tidy_deallocate(v44);
        return v16;
      }
      v18 = v44;
      if ( v46 > 7 )
        v18 = (_QWORD *)v44[0];
      v19 = v45;
      v20 = v45;
      if ( v45 >= 0xA )
        v20 = 10;
      if ( (unsigned int)_o__wcsnicmp(L"campaignid", v18, v20) || v19 != 10 )
      {
        v26 = v44;
        if ( v46 > 7 )
          v26 = (_QWORD *)v44[0];
        v27 = v45;
        v28 = v45;
        if ( v45 >= 8 )
          v28 = 8;
        if ( (unsigned int)_o__wcsnicmp(L"ruletype", v26, v28) || v27 != 8 )
        {
          if ( *((_BYTE *)a3 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
              (const char *)0x87C52407LL,
              v40);
            std::wstring::_Tidy_deallocate(v44);
            return 2277843975LL;
          }
          v36 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v37 = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
              (const char *)(unsigned int)v36,
              v40);
            std::wstring::_Tidy_deallocate(v44);
            return v37;
          }
        }
        else
        {
          std::wstring::wstring(v47);
          InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v47);
          v31 = InnerText;
          if ( InnerText < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
              (const char *)(unsigned int)InnerText,
              v40);
            std::wstring::_Tidy_deallocate(v47);
            std::wstring::_Tidy_deallocate(v44);
            return v31;
          }
          v32 = v47;
          if ( v47[3] > 7u )
            v32 = (_QWORD *)v47[0];
          if ( *((_WORD *)v32 + v47[2]) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
              v30);
          v33 = _o__wcstoui64(v32, 0, 0);
          if ( (unsigned int)(v33 - 1) > 2 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
              (const char *)0x87C5243BLL,
              v40);
            std::wstring::_Tidy_deallocate(v47);
            std::wstring::_Tidy_deallocate(v44);
            return 2277844027LL;
          }
          *((_DWORD *)this + 40) = v33;
          v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v35 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
              (const char *)(unsigned int)v34,
              v40);
            std::wstring::_Tidy_deallocate(v47);
            std::wstring::_Tidy_deallocate(v44);
            return v35;
          }
          v12 = 1;
          std::wstring::_Tidy_deallocate(v47);
        }
      }
      else
      {
        v21 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 128);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8E,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
            (const char *)(unsigned int)v21,
            v40);
          std::wstring::_Tidy_deallocate(v44);
          return v22;
        }
        v48 = 0;
        v42[0] = L" \n\r\t";
        v42[1] = std::_WChar_traits<wchar_t>::length(L" \n\r\t");
        Microsoft::Diagnostics::Utils::String::Trim((char *)this + 128, v42);
        if ( *((_QWORD *)this + 19) <= 7u )
          v23 = (char *)this + 128;
        else
          v23 = (char *)*((_QWORD *)this + 16);
        v43[0] = v23;
        v43[1] = *((_QWORD *)this + 18);
        if ( (int)Microsoft::Diagnostics::Utils::String::GUIDFromString(v43, &v48, 0) < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x99,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
            (const char *)0x87C5243ALL,
            v40);
          std::wstring::_Tidy_deallocate(v44);
          return 2277844026LL;
        }
        v24 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
            (const char *)(unsigned int)v24,
            v40);
          std::wstring::_Tidy_deallocate(v44);
          return v25;
        }
        v11 = 1;
      }
      std::wstring::_Tidy_deallocate(v44);
    }
    if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
        (const char *)Element,
        v40);
      return v14;
    }
    if ( v11 && v12 )
    {
      (*(void (__fastcall **)(Microsoft::Diagnostics::SoftLandingActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
      std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v41);
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC7,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\softlandingaction.cpp",
    (const char *)0x87C52402LL,
    v40);
  return 2277843970LL;
}

```

## disassembly

```asm
0x1800a81a0  push    rbx
0x1800a81a2  push    rsi
0x1800a81a3  push    rdi
0x1800a81a4  push    r12
0x1800a81a6  push    r13
0x1800a81a8  push    r14
0x1800a81aa  push    r15
0x1800a81ac  sub     rsp, 0B0h
0x1800a81b3  mov     rax, cs:__security_cookie
0x1800a81ba  xor     rax, rsp
0x1800a81bd  mov     [rsp+0E8h+var_48], rax
0x1800a81c5  mov     r13, r8
0x1800a81c8  mov     rdi, rdx
0x1800a81cb  mov     rsi, rcx
0x1800a81ce  movzx   edx, word ptr [rcx+78h]
0x1800a81d2  lea     rcx, [rsp+0E8h+var_C8]
0x1800a81d7  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x1800a81dc  lea     rdx, [r13+70h]
0x1800a81e0  movzx   r8d, word ptr [rsp+0E8h+var_C8]
0x1800a81e6  lea     rcx, [rsp+0E8h+var_C0]
0x1800a81eb  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800a81f0  cmp     qword ptr [rsi+70h], 7
0x1800a81f5  jbe     short loc_1800A81FD
0x1800a81f7  mov     r10, [rsi+58h]
0x1800a81fb  jmp     short loc_1800A8201
0x1800a81fd  lea     r10, [rsi+58h]
0x1800a8201  mov     rcx, [rsp+0E8h+var_C0]
0x1800a8206  call    ?top@?$stack@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$deque@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@std@@@2@@2@@std@@QEAAAEAV?$shared_ptr@VIFilterNode@Diagnostics@Microsoft@@@2@XZ; std::stack<std::shared_ptr<Microsoft::Diagnostics::IFilterNode>>::top(void)
0x1800a820b  lea     rcx, [rax+8]
0x1800a820f  mov     r8, [rsi+68h]
0x1800a8213  mov     rdx, r10
0x1800a8216  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800a821b  xor     r12d, r12d
0x1800a821e  mov     r14b, r12b
0x1800a8221  mov     r15b, r12b
0x1800a8224  mov     rcx, rdi; this
0x1800a8227  call    ?IsEmptyElement@XMLFacade@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::XMLFacade::IsEmptyElement(void)
0x1800a822c  test    al, al
0x1800a822e  jnz     loc_1800A8672
0x1800a8234  mov     rcx, rdi; this
0x1800a8237  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800a823c  mov     ebx, eax
0x1800a823e  test    eax, eax
0x1800a8240  jnz     loc_1800A8613
0x1800a8246  lea     rcx, [rsp+0E8h+var_98]; void *
0x1800a824b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a8250  nop
0x1800a8251  lea     rdx, [rsp+0E8h+var_98]
0x1800a8256  mov     rcx, rdi
0x1800a8259  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800a825e  mov     ebx, eax
0x1800a8260  test    eax, eax
0x1800a8262  jns     short loc_1800A8292
0x1800a8264  mov     rcx, [rsp+0E8h]; this
0x1800a826c  mov     r9d, eax; char *
0x1800a826f  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8276  mov     edx, 8Ah; void *
0x1800a827b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8280  nop
0x1800a8281  lea     rcx, [rsp+0E8h+var_98]
0x1800a8286  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a828b  mov     eax, ebx
0x1800a828d  jmp     loc_1800A86C9
0x1800a8292  lea     rdx, [rsp+0E8h+var_98]
0x1800a8297  cmp     [rsp+0E8h+var_80], 7
0x1800a829d  cmova   rdx, [rsp+0E8h+var_98]
0x1800a82a3  mov     rbx, [rsp+0E8h+var_88]
0x1800a82a8  mov     r8, rbx
0x1800a82ab  mov     eax, 0Ah
0x1800a82b0  cmp     rbx, rax
0x1800a82b3  cmovnb  r8, rax
0x1800a82b7  mov     rcx, cs:off_18036CD28; "campaignid"
0x1800a82be  call    cs:__imp__o__wcsnicmp
0x1800a82c4  test    eax, eax
0x1800a82c6  jnz     loc_1800A8402
0x1800a82cc  mov     eax, 0Ah
0x1800a82d1  sub     eax, ebx
0x1800a82d3  jnz     loc_1800A8402
0x1800a82d9  lea     rbx, [rsi+80h]
0x1800a82e0  mov     rdx, rbx
0x1800a82e3  mov     rcx, rdi
0x1800a82e6  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a82eb  mov     r14d, eax
0x1800a82ee  test    eax, eax
0x1800a82f0  jns     short loc_1800A8321
0x1800a82f2  mov     rcx, [rsp+0E8h]; this
0x1800a82fa  mov     r9d, eax; char *
0x1800a82fd  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8304  mov     edx, 8Eh; void *
0x1800a8309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a830e  nop
0x1800a830f  lea     rcx, [rsp+0E8h+var_98]
0x1800a8314  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8319  mov     eax, r14d
0x1800a831c  jmp     loc_1800A86C9
0x1800a8321  xorps   xmm0, xmm0
0x1800a8324  movups  [rsp+0E8h+var_58], xmm0
0x1800a832c  lea     rax, asc_180394878; " \n\r\t"
0x1800a8333  mov     [rsp+0E8h+var_B8], rax
0x1800a8338  mov     rcx, rax
0x1800a833b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800a8340  mov     [rsp+0E8h+var_B0], rax
0x1800a8345  lea     rdx, [rsp+0E8h+var_B8]
0x1800a834a  mov     rcx, rbx
0x1800a834d  call    ?Trim@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::String::Trim(std::wstring &,std::wstring_view)
0x1800a8352  cmp     qword ptr [rsi+98h], 7
0x1800a835a  jbe     short loc_1800A8361
0x1800a835c  mov     rax, [rbx]
0x1800a835f  jmp     short loc_1800A8364
0x1800a8361  mov     rax, rbx
0x1800a8364  mov     [rsp+0E8h+var_A8], rax
0x1800a8369  mov     rax, [rbx+10h]
0x1800a836d  mov     [rsp+0E8h+var_A0], rax
0x1800a8372  xor     r8d, r8d
0x1800a8375  lea     rdx, [rsp+0E8h+var_58]
0x1800a837d  lea     rcx, [rsp+0E8h+var_A8]
0x1800a8382  call    ?GUIDFromString@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::GUIDFromString(std::wstring_view,_GUID &,bool)
0x1800a8387  test    eax, eax
0x1800a8389  js      short loc_1800A83CF
0x1800a838b  mov     rcx, rdi; this
0x1800a838e  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a8393  mov     ebx, eax
0x1800a8395  test    eax, eax
0x1800a8397  jns     short loc_1800A83C7
0x1800a8399  mov     rcx, [rsp+0E8h]; this
0x1800a83a1  mov     r9d, eax; char *
0x1800a83a4  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a83ab  mov     edx, 9Ch; void *
0x1800a83b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a83b5  nop
0x1800a83b6  lea     rcx, [rsp+0E8h+var_98]
0x1800a83bb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a83c0  mov     eax, ebx
0x1800a83c2  jmp     loc_1800A86C9
0x1800a83c7  mov     r14b, 1
0x1800a83ca  jmp     loc_1800A8604
0x1800a83cf  mov     rcx, [rsp+0E8h]; this
0x1800a83d7  mov     ebx, 87C5243Ah
0x1800a83dc  mov     r9d, ebx; char *
0x1800a83df  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a83e6  mov     edx, 99h; void *
0x1800a83eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a83f0  nop
0x1800a83f1  lea     rcx, [rsp+0E8h+var_98]
0x1800a83f6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a83fb  mov     eax, ebx
0x1800a83fd  jmp     loc_1800A86C9
0x1800a8402  lea     rdx, [rsp+0E8h+var_98]
0x1800a8407  cmp     [rsp+0E8h+var_80], 7
0x1800a840d  cmova   rdx, [rsp+0E8h+var_98]
0x1800a8413  mov     rbx, [rsp+0E8h+var_88]
0x1800a8418  mov     r8, rbx
0x1800a841b  mov     eax, 8
0x1800a8420  cmp     rbx, rax
0x1800a8423  cmovnb  r8, rax
0x1800a8427  mov     rcx, cs:off_18036CDA8; "ruletype"
0x1800a842e  call    cs:__imp__o__wcsnicmp
0x1800a8434  test    eax, eax
0x1800a8436  jnz     loc_1800A858C
0x1800a843c  mov     eax, 8
0x1800a8441  sub     eax, ebx
0x1800a8443  test    eax, eax
0x1800a8445  jnz     loc_1800A858C
0x1800a844b  lea     rcx, [rsp+0E8h+var_78]; void *
0x1800a8450  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a8455  nop
0x1800a8456  lea     rdx, [rsp+0E8h+var_78]
0x1800a845b  mov     rcx, rdi
0x1800a845e  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800a8463  mov     ebx, eax
0x1800a8465  test    eax, eax
0x1800a8467  jns     short loc_1800A84A2
0x1800a8469  mov     rcx, [rsp+0E8h]; this
0x1800a8471  mov     r9d, eax; char *
0x1800a8474  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a847b  mov     edx, 0A1h; void *
0x1800a8480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8485  nop
0x1800a8486  lea     rcx, [rsp+0E8h+var_78]
0x1800a848b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8490  nop
0x1800a8491  lea     rcx, [rsp+0E8h+var_98]
0x1800a8496  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a849b  mov     eax, ebx
0x1800a849d  jmp     loc_1800A86C9
0x1800a84a2  mov     rax, [rsp+0E8h+var_68]
0x1800a84aa  lea     rcx, [rsp+0E8h+var_78]
0x1800a84af  cmp     [rsp+0E8h+var_60], 7
0x1800a84b8  cmova   rcx, [rsp+0E8h+var_78]
0x1800a84be  cmp     [rcx+rax*2], r12w
0x1800a84c3  jz      short loc_1800A84DF
0x1800a84c5  mov     rcx, [rsp+0E8h]; this
0x1800a84cd  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a84d4  mov     edx, 0B6h; void *
0x1800a84d9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a84df  xor     r8d, r8d
0x1800a84e2  xor     edx, edx
0x1800a84e4  call    cs:__imp__o__wcstoui64
0x1800a84ea  lea     ecx, [rax-1]
0x1800a84ed  cmp     ecx, 2
0x1800a84f0  jbe     short loc_1800A8530
0x1800a84f2  mov     rcx, [rsp+0E8h]; this
0x1800a84fa  mov     ebx, 87C5243Bh
0x1800a84ff  mov     r9d, ebx; char *
0x1800a8502  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8509  mov     edx, 0ADh; void *
0x1800a850e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8513  nop
0x1800a8514  lea     rcx, [rsp+0E8h+var_78]
0x1800a8519  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a851e  nop
0x1800a851f  lea     rcx, [rsp+0E8h+var_98]
0x1800a8524  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8529  mov     eax, ebx
0x1800a852b  jmp     loc_1800A86C9
0x1800a8530  mov     [rsi+0A0h], eax
0x1800a8536  mov     rcx, rdi; this
0x1800a8539  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a853e  mov     ebx, eax
0x1800a8540  test    eax, eax
0x1800a8542  jns     short loc_1800A857D
0x1800a8544  mov     rcx, [rsp+0E8h]; this
0x1800a854c  mov     r9d, eax; char *
0x1800a854f  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8556  mov     edx, 0B0h; void *
0x1800a855b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8560  nop
0x1800a8561  lea     rcx, [rsp+0E8h+var_78]
0x1800a8566  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a856b  nop
0x1800a856c  lea     rcx, [rsp+0E8h+var_98]
0x1800a8571  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8576  mov     eax, ebx
0x1800a8578  jmp     loc_1800A86C9
0x1800a857d  mov     r15b, 1
0x1800a8580  lea     rcx, [rsp+0E8h+var_78]
0x1800a8585  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a858a  jmp     short loc_1800A8604
0x1800a858c  cmp     [r13+98h], r12b
0x1800a8593  jz      short loc_1800A85C8
0x1800a8595  mov     rcx, [rsp+0E8h]; this
0x1800a859d  mov     ebx, 87C52407h
0x1800a85a2  mov     r9d, ebx; char *
0x1800a85a5  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a85ac  mov     edx, 0B6h; void *
0x1800a85b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a85b6  nop
0x1800a85b7  lea     rcx, [rsp+0E8h+var_98]
0x1800a85bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a85c1  mov     eax, ebx
0x1800a85c3  jmp     loc_1800A86C9
0x1800a85c8  mov     rcx, rdi; this
0x1800a85cb  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a85d0  mov     ebx, eax
0x1800a85d2  test    eax, eax
0x1800a85d4  jns     short loc_1800A8604
0x1800a85d6  mov     rcx, [rsp+0E8h]; this
0x1800a85de  mov     r9d, eax; char *
0x1800a85e1  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a85e8  mov     edx, 0B9h; void *
0x1800a85ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a85f2  nop
0x1800a85f3  lea     rcx, [rsp+0E8h+var_98]
0x1800a85f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a85fd  mov     eax, ebx
0x1800a85ff  jmp     loc_1800A86C9
0x1800a8604  lea     rcx, [rsp+0E8h+var_98]
0x1800a8609  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a860e  jmp     loc_1800A8234
0x1800a8613  mov     ecx, 80000000h
0x1800a8618  add     eax, ecx
0x1800a861a  test    ecx, eax
0x1800a861c  jnz     short loc_1800A8649
0x1800a861e  cmp     ebx, 80070272h
0x1800a8624  jz      short loc_1800A8649
0x1800a8626  mov     rcx, [rsp+0E8h]; this
0x1800a862e  mov     r9d, ebx; char *
0x1800a8631  lea     r8, aOnecoreBaseTel_28; "onecore\\base\\telemetry\\utc\\service"...
0x1800a8638  mov     edx, 0BDh; void *
0x1800a863d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8642  mov     eax, ebx
0x1800a8644  jmp     loc_1800A86C9
0x1800a8649  test    r14b, r14b
0x1800a864c  jz      short loc_1800A86A0
0x1800a864e  test    r15b, r15b
0x1800a8651  jz      short loc_1800A86A0
0x1800a8653  mov     rax, [rsi]
0x1800a8656  xor     edx, edx
0x1800a8658  mov     rcx, rsi
0x1800a865b  mov     rax, [rax+10h]
0x1800a865f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8664  mov     rcx, [rsp+0E8h+var_C0]
0x1800a8669  call    ?pop_back@?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(void)
0x1800a866e  xor     eax, eax
0x1800a8670  jmp     short loc_1800A86C9
0x1800a8672  mov     rcx, rdi; this
0x1800a8675  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800a867a  mov     ebx, eax
0x1800a867c  test    eax, eax
0x1800a867e  jns     short loc_1800A86A0
  ... truncated ...
```
