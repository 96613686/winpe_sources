# Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::ProcessEtwDataForNgen(_EVENT_RECORD const *)

- ea: `0x180038430`
- end: `0x180038728`
- name: `?ProcessEtwDataForNgen@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXPEBU_EVENT_RECORD@@@Z`
- size: `760`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *__hidden this, const struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180038310`

## callees

- `0x180002604`
- `0x1800089a8`
- `0x18000a078`
- `0x180038430`
- `0x1800395ec`
- `0x180039824`
- `0x18003d864`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800385b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800385b1`
- `KERNEL32!EnterCriticalSection` at `0x180038527`
- `KERNEL32!EnterCriticalSection` at `0x180038527`
- `OLEAUT32!__imp_SysAllocString` at `0x1800385e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800385e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800385bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800385bb`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800384fb`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800384fb`

## string_xrefs

- `0x1800386f3`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\ManagedInformationAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::ProcessEtwDataForNgen(
        Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *this,
        const struct _EVENT_RECORD *a2)
{
  char *UserData; // rsi
  unsigned __int64 v5; // rcx
  char *v6; // r9
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdx
  _WORD *v9; // r8
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  const OLECHAR *v13; // rbx
  wchar_t *v14; // rbx
  struct _RTL_CRITICAL_SECTION *v15; // rdi
  __int64 *v16; // r12
  __int64 v17; // rdx
  unsigned __int64 i; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 *v22; // rsi
  __int64 v23; // r12
  char *v24; // [rsp+30h] [rbp-88h] BYREF
  wchar_t *v25; // [rsp+38h] [rbp-80h]
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+40h] [rbp-78h]
  _OWORD v27[2]; // [rsp+48h] [rbp-70h] BYREF
  __int64 v28; // [rsp+68h] [rbp-50h]
  __int64 v29; // [rsp+70h] [rbp-48h]
  __int16 v30; // [rsp+78h] [rbp-40h]
  __int64 v31; // [rsp+80h] [rbp-38h]

  if ( a2->UserDataLength > 0x20u )
  {
    UserData = (char *)a2->UserData;
    v24 = UserData;
    v5 = a2->UserDataLength - 24LL;
    if ( v5 > 2 )
    {
      v6 = UserData + 24;
      v7 = v5 >> 1;
      if ( UserData != (char *)-24LL && v7 <= 0x7FFFFFFF )
      {
        v8 = v5 >> 1;
        v9 = UserData + 24;
        if ( v7 )
        {
          do
          {
            if ( !*v9 )
              break;
            ++v9;
            --v8;
          }
          while ( v8 );
        }
        v10 = v8 ? v7 - v8 : 0LL;
        if ( v8 )
        {
          v11 = 2 * v10;
          v12 = v11 + 2;
          if ( v11 + 2 >= v11 && v5 >= v12 && v5 - v12 > 2 )
          {
            _mm_lfence();
            v13 = (const OLECHAR *)&v6[v12];
            if ( wcslen((const wchar_t *)&v6[v12]) )
            {
              if ( v13 )
              {
                _mm_lfence();
                v14 = SysAllocString(v13);
                v25 = v14;
                if ( !v14 )
                  ATL::AtlThrowImpl(-2147024882);
              }
              else
              {
                v14 = 0;
                v25 = 0;
              }
              v15 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
              v26 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
              v16 = (__int64 *)(UserData + 8);
              v17 = 0xCBF29CE484222325uLL;
              for ( i = 0; i < 8; ++i )
                v17 = 0x100000001B3LL * (*((unsigned __int8 *)v16 + i) ^ (unsigned __int64)v17);
              v19 = 2 * (v17 & *((_QWORD *)this + 22));
              v20 = *((_QWORD *)this + 19);
              v21 = *(_QWORD *)(v20 + 8 * v19 + 8);
              if ( v21 == *((_QWORD *)this + 17) )
              {
LABEL_23:
                v21 = 0;
              }
              else
              {
                while ( *v16 != *(_QWORD *)(v21 + 16) )
                {
                  if ( v21 == *(_QWORD *)(v20 + 8 * v19) )
                    goto LABEL_23;
                  v21 = *(_QWORD *)(v21 + 8);
                }
              }
              if ( !v21 || v21 == *((_QWORD *)this + 17) )
              {
                _mm_lfence();
                v27[0] = 0;
                v27[1] = _mm_load_si128((const __m128i *)&_xmm);
                LOWORD(v27[0]) = 0;
                v28 = 0;
                v29 = 0;
                v30 = 0;
                try
                {
                  std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>,0>>::emplace<unsigned __int64 const &,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>();
                  _mm_lfence();
                  std::wstring::~wstring(v27);
                  v22 = (__int64 *)(v31 + 24);
                  std::wstring::operator=((char *)(v31 + 24), v14);
                  v23 = *v16;
                  v22[4] = v23;
                  v22[5] = *(_QWORD *)v24;
                  *((_BYTE *)v22 + 48) = (a2->EventHeader.Flags & 0x40) != 0;
                  v24 = 0;
                  std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(
                    (char *)this + 256,
                    &v24,
                    v22 + 4);
                  if ( v24 == *((char **)this + 33) )
                  {
                    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
                    {
                      if ( (unsigned __int64)v22[3] > 7 )
                        v22 = (__int64 *)*v22;
                      DiagHubCommon::LogStream::Write(
                        (DiagHubCommon::LogStream *)((char *)_logger + 56),
                        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
                        L"Assembly with ID [%ull] not loaded prior to module [%s] it contains.",
                        v23,
                        v22);
                    }
                  }
                  else
                  {
                    *((_DWORD *)v24 + 8) = a2->EventHeader.ProcessId;
                  }
                  *((_BYTE *)this + 112) = 1;
                }
                catch ( std::bad_alloc )
                {
                  DiagHubCommon::LogStream::Write(
                    (DiagHubCommon::LogStream *)((char *)_logger + 168),
                    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\ManagedInformationAgent.cpp",
                    L"Out of memory when trying to process etw for ngen");
                  v14 = v25;
                  v15 = v26;
                }
              }
              else
              {
                _mm_lfence();
              }
              LeaveCriticalSection(v15);
              SysFreeString(v14);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180038430  mov     [rsp+arg_10], rbx
0x180038435  mov     [rsp+arg_18], rsi
0x18003843a  push    rdi
0x18003843b  push    r12
0x18003843d  push    r13
0x18003843f  push    r14
0x180038441  push    r15
0x180038443  sub     rsp, 90h
0x18003844a  mov     r13, rdx
0x18003844d  mov     r14, rcx
0x180038450  cmp     word ptr [rdx+56h], 20h ; ' '
0x180038455  jbe     loc_1800385C1
0x18003845b  mov     rsi, [rdx+60h]
0x18003845f  mov     [rsp+0B8h+var_88], rsi
0x180038464  movzx   ecx, word ptr [rdx+56h]
0x180038468  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18003846c  cmp     rcx, 2
0x180038470  jbe     loc_1800385C1
0x180038476  lea     r9, [rsi+18h]
0x18003847a  mov     rax, rcx
0x18003847d  shr     rax, 1
0x180038480  xor     edi, edi
0x180038482  test    r9, r9
0x180038485  jz      loc_1800385C1
0x18003848b  cmp     rax, 7FFFFFFFh
0x180038491  ja      loc_1800385C1
0x180038497  mov     rdx, rax
0x18003849a  mov     r8, r9
0x18003849d  lea     r15d, [rdi+1]
0x1800384a1  test    rax, rax
0x1800384a4  jz      short loc_1800384B5
0x1800384a6  cmp     [r8], di
0x1800384aa  jz      short loc_1800384B5
0x1800384ac  add     r8, 2
0x1800384b0  sub     rdx, r15
0x1800384b3  jnz     short loc_1800384A6
0x1800384b5  test    rdx, rdx
0x1800384b8  jz      short loc_1800384BF
0x1800384ba  sub     rax, rdx
0x1800384bd  jmp     short loc_1800384C2
0x1800384bf  mov     rax, rdi
0x1800384c2  test    rdx, rdx
0x1800384c5  jz      loc_1800385C1
0x1800384cb  add     rax, rax
0x1800384ce  lea     rdx, [rax+2]
0x1800384d2  cmp     rdx, rax
0x1800384d5  jb      loc_1800385C1
0x1800384db  cmp     rcx, rdx
0x1800384de  jb      loc_1800385C1
0x1800384e4  sub     rcx, rdx
0x1800384e7  cmp     rcx, 2
0x1800384eb  jbe     loc_1800385C1
0x1800384f1  lfence
0x1800384f4  lea     rbx, [rdx+r9]
0x1800384f8  mov     rcx, rbx; String
0x1800384fb  call    cs:__imp_wcslen
0x180038501  test    rax, rax
0x180038504  jz      loc_1800385C1
0x18003850a  test    rbx, rbx
0x18003850d  jnz     loc_1800385DE
0x180038513  mov     rbx, rdi
0x180038516  mov     [rsp+0B8h+var_80], rbx
0x18003851b  lea     rdi, [r14+18h]
0x18003851f  mov     [rsp+0B8h+var_78], rdi
0x180038524  mov     rcx, rdi; lpCriticalSection
0x180038527  call    cs:__imp_EnterCriticalSection
0x18003852d  nop
0x18003852e  lea     r12, [rsi+8]
0x180038532  mov     rdx, 0CBF29CE484222325h
0x18003853c  xor     r9d, r9d
0x18003853f  mov     ecx, r9d
0x180038542  movzx   eax, byte ptr [r12+rcx]
0x180038547  xor     rdx, rax
0x18003854a  mov     r8, 100000001B3h
0x180038554  imul    rdx, r8
0x180038558  add     rcx, r15
0x18003855b  cmp     rcx, 8
0x18003855f  jb      short loc_180038542
0x180038561  mov     rax, [r14+0B0h]
0x180038568  and     rax, rdx
0x18003856b  add     rax, rax
0x18003856e  mov     rdx, [r14+98h]
0x180038575  mov     rcx, [rdx+rax*8+8]
0x18003857a  cmp     rcx, [r14+88h]
0x180038581  jz      short loc_18003859A
0x180038583  mov     r8, [rdx+rax*8]
0x180038587  mov     rax, [rcx+10h]
0x18003858b  cmp     [r12], rax
0x18003858f  jz      short loc_18003859D
0x180038591  cmp     rcx, r8
0x180038594  jnz     loc_180038714
0x18003859a  mov     rcx, r9
0x18003859d  test    rcx, rcx
0x1800385a0  jz      short loc_180038600
0x1800385a2  cmp     rcx, [r14+88h]
0x1800385a9  jz      short loc_180038600
0x1800385ab  lfence
0x1800385ae  mov     rcx, rdi; lpCriticalSection
0x1800385b1  call    cs:__imp_LeaveCriticalSection
0x1800385b7  nop
0x1800385b8  mov     rcx, rbx; bstrString
0x1800385bb  call    cs:__imp_SysFreeString
0x1800385c1  lea     r11, [rsp+0B8h+var_28]
0x1800385c9  mov     rbx, [r11+40h]
0x1800385cd  mov     rsi, [r11+48h]
0x1800385d1  mov     rsp, r11
0x1800385d4  pop     r15
0x1800385d6  pop     r14
0x1800385d8  pop     r13
0x1800385da  pop     r12
0x1800385dc  pop     rdi
0x1800385dd  retn
0x1800385de  lfence
0x1800385e1  mov     rcx, rbx; psz
0x1800385e4  call    cs:__imp_SysAllocString
0x1800385ea  mov     rbx, rax
0x1800385ed  mov     [rsp+0B8h+var_80], rax
0x1800385f2  test    rax, rax
0x1800385f5  jz      loc_18003871D
0x1800385fb  jmp     loc_18003851B
0x180038600  lfence
0x180038603  xorps   xmm0, xmm0
0x180038606  movups  [rsp+0B8h+var_70], xmm0
0x18003860b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180038613  movdqu  [rsp+0B8h+var_60], xmm1
0x180038619  mov     word ptr [rsp+0B8h+var_70], r9w
0x18003861f  mov     [rsp+0B8h+var_50], r9
0x180038624  mov     [rsp+0B8h+var_48], r9
0x180038629  mov     [rsp+0B8h+var_40], r9w
0x18003862f  lea     r9, [rsp+0B8h+var_70]
0x180038634  mov     r8, r12
0x180038637  lea     rdx, [rsp+0B8h+var_38]
0x18003863f  lea     rcx, [r14+80h]
0x180038646  call    ??$emplace@AEB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@?$_Hash@V?$_Umap_traits@_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEB_K$$QEAUModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>>,0>>::emplace<unsigned __int64 const &,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>(unsigned __int64 const &,Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails &&)
0x18003864b  nop
0x18003864c  lfence
0x18003864f  lea     rcx, [rsp+0B8h+var_70]
0x180038654  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038659  mov     rsi, [rsp+0B8h+var_38]
0x180038661  add     rsi, 18h
0x180038665  mov     rdx, rbx; Src
0x180038668  mov     rcx, rsi; void *
0x18003866b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180038670  mov     r12, [r12]
0x180038674  lea     r8, [rsi+20h]
0x180038678  mov     [r8], r12
0x18003867b  mov     rax, [rsp+0B8h+var_88]
0x180038680  mov     rax, [rax]
0x180038683  mov     [rsi+28h], rax
0x180038687  mov     al, [r13+4]
0x18003868b  shr     al, 6
0x18003868e  and     al, r15b
0x180038691  mov     [rsi+30h], al
0x180038694  mov     [rsp+0B8h+var_88], 0
0x18003869d  lea     rcx, [r14+100h]
0x1800386a4  lea     rdx, [rsp+0B8h+var_88]
0x1800386a9  call    ?find@?$_Hash@V?$_Umap_traits@_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUAssemblyDetails@ManagedInformationAgent@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::AssemblyDetails>>,0>>::find(unsigned __int64 const &)
0x1800386ae  mov     r8, [rsp+0B8h+var_88]
0x1800386b3  cmp     r8, [r14+108h]
0x1800386ba  jz      short loc_1800386C6
0x1800386bc  mov     eax, [r13+0Ch]
0x1800386c0  mov     [r8+20h], eax
0x1800386c4  jmp     short loc_1800386FF
0x1800386c6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800386cd  add     rcx, 38h ; '8'; this
0x1800386d1  mov     rax, [rcx+8]
0x1800386d5  cmp     [rcx], rax
0x1800386d8  jz      short loc_1800386FF
0x1800386da  cmp     qword ptr [rsi+18h], 7
0x1800386df  jbe     short loc_1800386E4
0x1800386e1  mov     rsi, [rsi]
0x1800386e4  mov     [rsp+0B8h+var_98], rsi
0x1800386e9  mov     r9, r12
0x1800386ec  lea     r8, aAssemblyWithId; "Assembly with ID [%ull] not loaded prio"...
0x1800386f3  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800386fa  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800386ff  xchg    r15b, [r14+70h]
0x180038703  jmp     short loc_18003870F
0x180038705  mov     rbx, [rsp+0B8h+var_80]
0x18003870a  mov     rdi, [rsp+0B8h+var_78]
0x18003870f  jmp     loc_1800385AE
0x180038714  mov     rcx, [rcx+8]
0x180038718  jmp     loc_180038587
0x18003871d  mov     ecx, 8007000Eh; int
0x180038722  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
