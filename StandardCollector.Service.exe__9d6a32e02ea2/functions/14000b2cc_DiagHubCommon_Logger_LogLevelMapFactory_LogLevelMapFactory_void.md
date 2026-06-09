# DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(void)

- ea: `0x14000b2cc`
- end: `0x14000b526`
- name: `??0LogLevelMapFactory@Logger@DiagHubCommon@@QEAA@XZ`
- size: `602`
- prototype: `int *__fastcall(DiagHubCommon::Logger::LogLevelMapFactory *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x140002114`
- `0x140004b0c`
- `0x14000cf14`
- `0x140013834`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
int *__fastcall DiagHubCommon::Logger::LogLevelMapFactory::LogLevelMapFactory(
        DiagHubCommon::Logger::LogLevelMapFactory *this)
{
  _QWORD *v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int *v13; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v14[24]; // [rsp+28h] [rbp-28h] BYREF
  int *v15; // [rsp+40h] [rbp-10h]

  v15 = &dword_140024B60;
  v13 = &dword_140024B60;
  dword_140024B60 = 0;
  qword_140024B68 = 0;
  qword_140024B70 = 0;
  v1 = operator new(0x38u);
  *v1 = v1;
  v1[1] = v1;
  qword_140024B68 = (__int64)v1;
  qword_140024B78 = 0;
  xmmword_140024B80 = 0;
  qword_140024B90 = 7;
  qword_140024B98 = 8;
  dword_140024B60 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    &qword_140024B78,
    16,
    v1);
  LODWORD(v13) = 0;
  v2 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v2 + 24LL), L"None");
  LODWORD(v13) = 1;
  v3 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v3 + 24LL), L"Info");
  LODWORD(v13) = 2;
  v4 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v4 + 24LL), L"Debug");
  LODWORD(v13) = 4;
  v5 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v5 + 24LL), L"Warning");
  LODWORD(v13) = 8;
  v6 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v6 + 24LL), L"Error");
  LODWORD(v13) = 16;
  v7 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v7 + 24LL), L"Perf");
  LODWORD(v13) = 15;
  v8 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v8 + 24LL), L"AllInfo");
  LODWORD(v13) = 14;
  v9 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
         (__int64)&dword_140024B60,
         (__int64)v14,
         &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v9 + 24LL), L"AllDebug");
  LODWORD(v13) = 12;
  v10 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
          (__int64)&dword_140024B60,
          (__int64)v14,
          &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v10 + 24LL), L"AllWarning");
  LODWORD(v13) = 0xFFFFFFF;
  v11 = std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
          (__int64)&dword_140024B60,
          (__int64)v14,
          &v13);
  std::wstring::operator=((void *)(*(_QWORD *)v11 + 24LL), L"All");
  return &dword_140024B60;
}

```

## disassembly

```asm
0x14000b2cc  mov     [rsp-8+arg_0], r14
0x14000b2d1  push    rbp
0x14000b2d2  mov     rbp, rsp
0x14000b2d5  sub     rsp, 50h
0x14000b2d9  mov     rax, [rbp+var_10]
0x14000b2dd  mov     [rbp+var_10], rax
0x14000b2e1  lea     r14, dword_140024B60
0x14000b2e8  mov     [rbp+var_10], r14
0x14000b2ec  mov     [rbp+var_30], r14
0x14000b2f0  mov     cs:dword_140024B60, 0
0x14000b2fa  mov     cs:qword_140024B68, 0
0x14000b305  mov     cs:qword_140024B70, 0
0x14000b310  mov     ecx, 38h ; '8'; Size
0x14000b315  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b31a  mov     [rax], rax
0x14000b31d  mov     [rax+8], rax
0x14000b321  mov     cs:qword_140024B68, rax
0x14000b328  mov     cs:qword_140024B78, 0
0x14000b333  xorps   xmm0, xmm0
0x14000b336  movdqa  cs:xmmword_140024B80, xmm0
0x14000b33e  mov     cs:qword_140024B90, 7
0x14000b349  mov     cs:qword_140024B98, 8
0x14000b354  mov     cs:dword_140024B60, 3F800000h
0x14000b35e  mov     r8, rax
0x14000b361  mov     edx, 10h
0x14000b366  lea     rcx, qword_140024B78
0x14000b36d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x14000b372  nop
0x14000b373  mov     dword ptr [rbp+var_30], 0
0x14000b37a  lea     r8, [rbp+var_30]
0x14000b37e  lea     rdx, [rbp+var_28]
0x14000b382  mov     rcx, r14
0x14000b385  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b38a  mov     rcx, [rax]
0x14000b38d  add     rcx, 18h; void *
0x14000b391  lea     rdx, aNone; "None"
0x14000b398  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b39d  mov     dword ptr [rbp+var_30], 1
0x14000b3a4  lea     r8, [rbp+var_30]
0x14000b3a8  lea     rdx, [rbp+var_28]
0x14000b3ac  mov     rcx, r14
0x14000b3af  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b3b4  mov     rcx, [rax]
0x14000b3b7  add     rcx, 18h; void *
0x14000b3bb  lea     rdx, aInfo; "Info"
0x14000b3c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b3c7  mov     dword ptr [rbp+var_30], 2
0x14000b3ce  lea     r8, [rbp+var_30]
0x14000b3d2  lea     rdx, [rbp+var_28]
0x14000b3d6  mov     rcx, r14
0x14000b3d9  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b3de  mov     rcx, [rax]
0x14000b3e1  add     rcx, 18h; void *
0x14000b3e5  lea     rdx, aDebug; "Debug"
0x14000b3ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b3f1  mov     dword ptr [rbp+var_30], 4
0x14000b3f8  lea     r8, [rbp+var_30]
0x14000b3fc  lea     rdx, [rbp+var_28]
0x14000b400  mov     rcx, r14
0x14000b403  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b408  mov     rcx, [rax]
0x14000b40b  add     rcx, 18h; void *
0x14000b40f  lea     rdx, aWarning; "Warning"
0x14000b416  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b41b  mov     dword ptr [rbp+var_30], 8
0x14000b422  lea     r8, [rbp+var_30]
0x14000b426  lea     rdx, [rbp+var_28]
0x14000b42a  mov     rcx, r14
0x14000b42d  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b432  mov     rcx, [rax]
0x14000b435  add     rcx, 18h; void *
0x14000b439  lea     rdx, aError; "Error"
0x14000b440  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b445  mov     dword ptr [rbp+var_30], 10h
0x14000b44c  lea     r8, [rbp+var_30]
0x14000b450  lea     rdx, [rbp+var_28]
0x14000b454  mov     rcx, r14
0x14000b457  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b45c  mov     rcx, [rax]
0x14000b45f  add     rcx, 18h; void *
0x14000b463  lea     rdx, aPerf; "Perf"
0x14000b46a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b46f  mov     dword ptr [rbp+var_30], 0Fh
0x14000b476  lea     r8, [rbp+var_30]
0x14000b47a  lea     rdx, [rbp+var_28]
0x14000b47e  mov     rcx, r14
0x14000b481  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b486  mov     rcx, [rax]
0x14000b489  add     rcx, 18h; void *
0x14000b48d  lea     rdx, aAllinfo; "AllInfo"
0x14000b494  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b499  mov     dword ptr [rbp+var_30], 0Eh
0x14000b4a0  lea     r8, [rbp+var_30]
0x14000b4a4  lea     rdx, [rbp+var_28]
0x14000b4a8  mov     rcx, r14
0x14000b4ab  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b4b0  mov     rcx, [rax]
0x14000b4b3  add     rcx, 18h; void *
0x14000b4b7  lea     rdx, aAlldebug; "AllDebug"
0x14000b4be  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b4c3  mov     dword ptr [rbp+var_30], 0Ch
0x14000b4ca  lea     r8, [rbp+var_30]
0x14000b4ce  lea     rdx, [rbp+var_28]
0x14000b4d2  mov     rcx, r14
0x14000b4d5  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b4da  mov     rcx, [rax]
0x14000b4dd  add     rcx, 18h; void *
0x14000b4e1  lea     rdx, aAllwarning; "AllWarning"
0x14000b4e8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b4ed  mov     dword ptr [rbp+var_30], 0FFFFFFFh
0x14000b4f4  lea     r8, [rbp+var_30]
0x14000b4f8  lea     rdx, [rbp+var_28]
0x14000b4fc  mov     rcx, r14
0x14000b4ff  call    ??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)
0x14000b504  mov     rcx, [rax]
0x14000b507  add     rcx, 18h; void *
0x14000b50b  lea     rdx, aAll; "All"
0x14000b512  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x14000b517  nop
0x14000b518  mov     rax, r14
0x14000b51b  mov     r14, [rsp+50h+arg_0]
0x14000b520  add     rsp, 50h
0x14000b524  pop     rbp
0x14000b525  retn
```
