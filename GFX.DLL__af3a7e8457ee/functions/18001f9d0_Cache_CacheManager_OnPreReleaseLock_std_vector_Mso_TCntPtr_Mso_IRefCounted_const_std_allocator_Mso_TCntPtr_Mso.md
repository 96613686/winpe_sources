# Cache::CacheManager::OnPreReleaseLock(std::vector<Mso::TCntPtr<Mso::IRefCounted const>,std::allocator<Mso::TCntPtr<Mso::IRefCounted const>>> &,std::vector<ARC::TPtr<ARC::IObject const>,std::allocator<ARC::TPtr<ARC::IObject const>>> &)

- ea: `0x18001f9d0`
- end: `0x18001fcad`
- name: `?OnPreReleaseLock@CacheManager@Cache@@QEAAXAEAV?$vector@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@V?$allocator@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@AEAV?$vector@V?$TPtr@$$CBUIObject@ARC@@@ARC@@V?$allocator@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@4@@Z`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001f8f4`

## callees

- `0x18001f9d0`
- `0x180056ee0`
- `0x18007aa30`
- `0x18007b450`
- `0x1801fcdc8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001fb6e`
- `KERNEL32!GetCurrentThreadId` at `0x18001fb6e`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18001fbe2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18001fbe2`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18001fc47`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18001fc47`

## string_xrefs

- `0x18001fb83`: `threadID`
- `0x18001fc33`: `CacheManager::OnPreReleaseLock`

## pseudocode

```c
void __fastcall Cache::CacheManager::OnPreReleaseLock(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 *v3; // r12
  __int64 *v4; // r14
  _QWORD *v5; // rbx
  __int64 *v6; // rdi
  __int64 *v7; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD v20[2]; // [rsp+30h] [rbp-108h] BYREF
  char v21; // [rsp+40h] [rbp-F8h] BYREF
  _QWORD *v22; // [rsp+48h] [rbp-F0h]
  __int64 *v23; // [rsp+50h] [rbp-E8h]
  __int64 *v24; // [rsp+58h] [rbp-E0h]
  _QWORD v25[3]; // [rsp+68h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-B8h] BYREF
  DWORD CurrentThreadId; // [rsp+90h] [rbp-A8h]
  __int16 v28; // [rsp+94h] [rbp-A4h]
  _OWORD v29[2]; // [rsp+98h] [rbp-A0h] BYREF
  _QWORD v30[3]; // [rsp+C0h] [rbp-78h] BYREF
  __int16 v31; // [rsp+D8h] [rbp-60h]
  _OWORD v32[2]; // [rsp+E0h] [rbp-58h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = (_QWORD *)a1;
  v22 = (_QWORD *)a1;
  v6 = a2;
  v24 = a2;
  v7 = a3;
  v23 = a3;
  if ( (*(_DWORD *)(a1 + 848))-- == 1 )
  {
    v9 = *(_QWORD *)(a1 + 832);
    if ( v9 )
      std::vector<Mso::TCntPtr<Mso::IRefCounted const>>::_Insert_counted_range<Mso::TCntPtr<Mso::IRefCounted const> *>(
        v9,
        *(_QWORD *)(v9 + 8),
        v5[98],
        (__int64)(v5[99] - v5[98]) >> 3);
    v10 = v5[105];
    if ( v10 )
    {
      try
      {
        std::vector<ARC::TPtr<ARC::IObject const>>::_Insert_counted_range<ARC::TPtr<ARC::IObject const> *>(
          v10,
          *(_QWORD *)(v10 + 8),
          v5[101],
          (__int64)(v5[102] - v5[101]) >> 3);
      }
      catch ( ... )
      {
        v5 = v22;
        v7 = v23;
        v6 = v24;
        v3 = v23;
        v4 = v24;
      }
    }
    v11 = v5 + 98;
    if ( v5 + 98 != v6 )
    {
      v12 = *v11;
      *v11 = *v6;
      *v6 = v12;
      v13 = v5[99];
      v5[99] = v6[1];
      v6[1] = v13;
      v14 = v5[100];
      v5[100] = v6[2];
      v6[2] = v14;
    }
    v15 = v5 + 101;
    if ( v15 != v7 )
    {
      v16 = *v15;
      *v15 = *v7;
      *v7 = v16;
      v17 = v15[1];
      v15[1] = v7[1];
      v7[1] = v17;
      v18 = v15[2];
      v15[2] = v7[2];
      v7[2] = v18;
    }
    v19 = v6[1];
    if ( *v4 != v19 )
    {
      v30[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v30[1] = "numResourcesReleased";
      v30[2] = ((v19 - *v4) >> 3) + ((v7[1] - *v3) >> 3);
      v31 = 4;
      v32[0] = 0;
      v32[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v32[0]) = 0;
      v26[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v26[1] = "threadID";
      CurrentThreadId = GetCurrentThreadId();
      v28 = 4;
      v29[0] = 0;
      v29[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v29[0]) = 0;
      if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(592545615, 48, 100, 2) )
      {
        v20[0] = v26;
        v20[1] = v30;
        v25[0] = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v25[1] = v20;
        v25[2] = &v21;
        Mso::Logging::MsoSendStructuredTraceTag(592545615, 48, 100, 2, "CacheManager::OnPreReleaseLock", v25);
      }
      std::wstring::~wstring(v29);
      std::wstring::~wstring(v32);
    }
  }
}

```

## disassembly

```asm
0x18001f9d0  mov     [rsp+arg_18], rbx
0x18001f9d5  push    rsi
0x18001f9d6  push    rdi
0x18001f9d7  push    r12
0x18001f9d9  push    r14
0x18001f9db  push    r15
0x18001f9dd  sub     rsp, 110h
0x18001f9e4  mov     rax, cs:__security_cookie
0x18001f9eb  xor     rax, rsp
0x18001f9ee  mov     [rsp+138h+var_38], rax
0x18001f9f6  mov     r12, r8
0x18001f9f9  mov     r14, rdx
0x18001f9fc  mov     rbx, rcx
0x18001f9ff  mov     [rsp+138h+var_F0], rcx
0x18001fa04  mov     rdi, rdx
0x18001fa07  mov     [rsp+138h+var_E0], rdx
0x18001fa0c  mov     rsi, r8
0x18001fa0f  mov     [rsp+138h+var_E8], r8
0x18001fa14  sub     dword ptr [rcx+350h], 1
0x18001fa1b  jz      short loc_18001FA45
0x18001fa1d  mov     rcx, [rsp+138h+var_38]
0x18001fa25  xor     rcx, rsp; StackCookie
0x18001fa28  call    __security_check_cookie
0x18001fa2d  mov     rbx, [rsp+138h+arg_18]
0x18001fa35  add     rsp, 110h
0x18001fa3c  pop     r15
0x18001fa3e  pop     r14
0x18001fa40  pop     r12
0x18001fa42  pop     rdi
0x18001fa43  pop     rsi
0x18001fa44  retn
0x18001fa45  mov     rcx, [rcx+340h]
0x18001fa4c  xor     r15d, r15d
0x18001fa4f  test    rcx, rcx
0x18001fa52  jnz     loc_18001FC6C
0x18001fa58  mov     rcx, [rbx+348h]
0x18001fa5f  test    rcx, rcx
0x18001fa62  jz      short loc_18001FA83
0x18001fa64  mov     r8, [rbx+328h]
0x18001fa6b  mov     r9, [rbx+330h]
0x18001fa72  sub     r9, r8
0x18001fa75  sar     r9, 3
0x18001fa79  mov     rdx, [rcx+8]
0x18001fa7d  call    ??$_Insert_counted_range@PEAV?$TPtr@$$CBUIObject@ARC@@@ARC@@@?$vector@V?$TPtr@$$CBUIObject@ARC@@@ARC@@V?$allocator@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@std@@@1@PEAV?$TPtr@$$CBUIObject@ARC@@@ARC@@_K@Z; std::vector<ARC::TPtr<ARC::IObject const>>::_Insert_counted_range<ARC::TPtr<ARC::IObject const> *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ARC::TPtr<ARC::IObject const>>>>,ARC::TPtr<ARC::IObject const> *,unsigned __int64)
0x18001fa82  nop
0x18001fa83  lea     rdx, [rbx+310h]
0x18001fa8a  cmp     rdx, rdi
0x18001fa8d  jz      short loc_18001FABB
0x18001fa8f  mov     rcx, [rdx]
0x18001fa92  mov     rax, [rdi]
0x18001fa95  mov     [rdx], rax
0x18001fa98  mov     [rdi], rcx
0x18001fa9b  mov     rcx, [rdx+8]
0x18001fa9f  mov     rax, [rdi+8]
0x18001faa3  mov     [rdx+8], rax
0x18001faa7  mov     [rdi+8], rcx
0x18001faab  mov     rcx, [rdx+10h]
0x18001faaf  mov     rax, [rdi+10h]
0x18001fab3  mov     [rdx+10h], rax
0x18001fab7  mov     [rdi+10h], rcx
0x18001fabb  add     rbx, 328h
0x18001fac2  cmp     rbx, rsi
0x18001fac5  jz      short loc_18001FAF3
0x18001fac7  mov     rcx, [rbx]
0x18001faca  mov     rax, [rsi]
0x18001facd  mov     [rbx], rax
0x18001fad0  mov     [rsi], rcx
0x18001fad3  mov     rcx, [rbx+8]
0x18001fad7  mov     rax, [rsi+8]
0x18001fadb  mov     [rbx+8], rax
0x18001fadf  mov     [rsi+8], rcx
0x18001fae3  mov     rcx, [rbx+10h]
0x18001fae7  mov     rax, [rsi+10h]
0x18001faeb  mov     [rbx+10h], rax
0x18001faef  mov     [rsi+10h], rcx
0x18001faf3  mov     rcx, [rdi+8]
0x18001faf7  cmp     [r14], rcx
0x18001fafa  jz      loc_18001FA1D
0x18001fb00  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18001fb07  mov     [rsp+138h+var_78], rax
0x18001fb0f  lea     rax, aNumresourcesre; "numResourcesReleased"
0x18001fb16  mov     [rsp+138h+var_70], rax
0x18001fb1e  mov     rax, [rsi+8]
0x18001fb22  sub     rax, [r12]
0x18001fb26  sar     rax, 3
0x18001fb2a  sub     rcx, [r14]
0x18001fb2d  sar     rcx, 3
0x18001fb31  add     rax, rcx
0x18001fb34  mov     [rsp+138h+var_68], rax
0x18001fb3c  mov     ebx, 4
0x18001fb41  mov     [rsp+138h+var_60], bx
0x18001fb49  xorps   xmm0, xmm0
0x18001fb4c  movups  [rsp+138h+var_58], xmm0
0x18001fb54  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fb5c  movdqa  [rsp+138h+var_48], xmm1
0x18001fb65  mov     word ptr [rsp+138h+var_58], r15w
0x18001fb6e  call    cs:__imp_GetCurrentThreadId
0x18001fb74  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18001fb7b  mov     [rsp+138h+var_B8], rcx
0x18001fb83  lea     rcx, aThreadid; "threadID"
0x18001fb8a  mov     [rsp+138h+var_B0], rcx
0x18001fb92  mov     [rsp+138h+var_A8], eax
0x18001fb99  mov     [rsp+138h+var_A4], bx
0x18001fba1  xorps   xmm0, xmm0
0x18001fba4  movups  [rsp+138h+var_A0], xmm0
0x18001fbac  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fbb4  movdqu  [rsp+138h+var_90], xmm1
0x18001fbbd  mov     word ptr [rsp+138h+var_A0], r15w
0x18001fbc6  mov     ebx, 2
0x18001fbcb  mov     r9d, ebx
0x18001fbce  lea     edi, [rbx+62h]
0x18001fbd1  mov     r8d, edi
0x18001fbd4  lea     esi, [rbx+2Eh]
0x18001fbd7  mov     edx, esi
0x18001fbd9  mov     r14d, 2351874Fh
0x18001fbdf  mov     ecx, r14d
0x18001fbe2  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18001fbe8  test    al, al
0x18001fbea  jz      short loc_18001FC4D
0x18001fbec  lea     rax, [rsp+138h+var_B8]
0x18001fbf4  mov     [rsp+138h+var_108], rax
0x18001fbf9  lea     rax, [rsp+138h+var_78]
0x18001fc01  mov     [rsp+138h+var_100], rax
0x18001fc06  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18001fc0d  mov     [rsp+138h+var_D0], rax
0x18001fc12  lea     rax, [rsp+138h+var_108]
0x18001fc17  mov     [rsp+138h+var_C8], rax
0x18001fc1c  lea     rax, [rsp+138h+var_F8]
0x18001fc21  mov     [rsp+138h+var_C0], rax
0x18001fc26  mov     r9d, ebx
0x18001fc29  lea     rax, [rsp+138h+var_D0]
0x18001fc2e  mov     [rsp+138h+var_110], rax
0x18001fc33  lea     rax, aCachemanagerOn; "CacheManager::OnPreReleaseLock"
0x18001fc3a  mov     [rsp+138h+var_118], rax
0x18001fc3f  mov     r8d, edi
0x18001fc42  mov     edx, esi
0x18001fc44  mov     ecx, r14d
0x18001fc47  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
0x18001fc4d  lea     rcx, [rsp+138h+var_A0]
0x18001fc55  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fc5a  lea     rcx, [rsp+138h+var_58]
0x18001fc62  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fc67  jmp     loc_18001FA1D
0x18001fc6c  mov     r8, [rbx+310h]
0x18001fc73  mov     r9, [rbx+318h]
0x18001fc7a  sub     r9, r8
0x18001fc7d  sar     r9, 3
0x18001fc81  mov     rdx, [rcx+8]
0x18001fc85  call    ??$_Insert_counted_range@PEAV?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@?$vector@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@V?$allocator@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@@1@PEAV?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@_K@Z; std::vector<Mso::TCntPtr<Mso::IRefCounted const>>::_Insert_counted_range<Mso::TCntPtr<Mso::IRefCounted const> *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Mso::TCntPtr<Mso::IRefCounted const>>>>,Mso::TCntPtr<Mso::IRefCounted const> *,unsigned __int64)
0x18001fc8a  jmp     loc_18001FA58
0x18001fc8f  xor     r15d, r15d
0x18001fc92  mov     rbx, [rsp+138h+var_F0]
0x18001fc97  mov     rsi, [rsp+138h+var_E8]
0x18001fc9c  mov     rdi, [rsp+138h+var_E0]
0x18001fca1  mov     r12, rsi
0x18001fca4  mov     r14, rdi
0x18001fca7  jmp     loc_18001FA83
```
