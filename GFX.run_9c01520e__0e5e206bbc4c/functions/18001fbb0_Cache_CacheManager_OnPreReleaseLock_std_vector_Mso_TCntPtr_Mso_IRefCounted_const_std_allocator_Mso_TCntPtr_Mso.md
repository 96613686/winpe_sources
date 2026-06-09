# Cache::CacheManager::OnPreReleaseLock(std::vector<Mso::TCntPtr<Mso::IRefCounted const>,std::allocator<Mso::TCntPtr<Mso::IRefCounted const>>> &,std::vector<ARC::TPtr<ARC::IObject const>,std::allocator<ARC::TPtr<ARC::IObject const>>> &)

- ea: `0x18001fbb0`
- end: `0x18001fe8d`
- name: `?OnPreReleaseLock@CacheManager@Cache@@QEAAXAEAV?$vector@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@V?$allocator@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@AEAV?$vector@V?$TPtr@$$CBUIObject@ARC@@@ARC@@V?$allocator@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@4@@Z`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001fa94`

## callees

- `0x18001fbb0`
- `0x1800578b0`
- `0x180077780`
- `0x180161618`
- `0x1802000fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001fd4e`
- `KERNEL32!GetCurrentThreadId` at `0x18001fd4e`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18001fdc2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18001fdc2`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18001fe27`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18001fe27`

## string_xrefs

- `0x18001fd63`: `threadID`
- `0x18001fe13`: `CacheManager::OnPreReleaseLock`

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
0x18001fbb0  mov     [rsp+arg_18], rbx
0x18001fbb5  push    rsi
0x18001fbb6  push    rdi
0x18001fbb7  push    r12
0x18001fbb9  push    r14
0x18001fbbb  push    r15
0x18001fbbd  sub     rsp, 110h
0x18001fbc4  mov     rax, cs:__security_cookie
0x18001fbcb  xor     rax, rsp
0x18001fbce  mov     [rsp+138h+var_38], rax
0x18001fbd6  mov     r12, r8
0x18001fbd9  mov     r14, rdx
0x18001fbdc  mov     rbx, rcx
0x18001fbdf  mov     [rsp+138h+var_F0], rcx
0x18001fbe4  mov     rdi, rdx
0x18001fbe7  mov     [rsp+138h+var_E0], rdx
0x18001fbec  mov     rsi, r8
0x18001fbef  mov     [rsp+138h+var_E8], r8
0x18001fbf4  sub     dword ptr [rcx+350h], 1
0x18001fbfb  jz      short loc_18001FC25
0x18001fbfd  mov     rcx, [rsp+138h+var_38]
0x18001fc05  xor     rcx, rsp; StackCookie
0x18001fc08  call    __security_check_cookie
0x18001fc0d  mov     rbx, [rsp+138h+arg_18]
0x18001fc15  add     rsp, 110h
0x18001fc1c  pop     r15
0x18001fc1e  pop     r14
0x18001fc20  pop     r12
0x18001fc22  pop     rdi
0x18001fc23  pop     rsi
0x18001fc24  retn
0x18001fc25  mov     rcx, [rcx+340h]
0x18001fc2c  xor     r15d, r15d
0x18001fc2f  test    rcx, rcx
0x18001fc32  jnz     loc_18001FE4C
0x18001fc38  mov     rcx, [rbx+348h]
0x18001fc3f  test    rcx, rcx
0x18001fc42  jz      short loc_18001FC63
0x18001fc44  mov     r8, [rbx+328h]
0x18001fc4b  mov     r9, [rbx+330h]
0x18001fc52  sub     r9, r8
0x18001fc55  sar     r9, 3
0x18001fc59  mov     rdx, [rcx+8]
0x18001fc5d  call    ??$_Insert_counted_range@PEAV?$TPtr@$$CBUIObject@ARC@@@ARC@@@?$vector@V?$TPtr@$$CBUIObject@ARC@@@ARC@@V?$allocator@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$TPtr@$$CBUIObject@ARC@@@ARC@@@std@@@std@@@1@PEAV?$TPtr@$$CBUIObject@ARC@@@ARC@@_K@Z; std::vector<ARC::TPtr<ARC::IObject const>>::_Insert_counted_range<ARC::TPtr<ARC::IObject const> *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ARC::TPtr<ARC::IObject const>>>>,ARC::TPtr<ARC::IObject const> *,unsigned __int64)
0x18001fc62  nop
0x18001fc63  lea     rdx, [rbx+310h]
0x18001fc6a  cmp     rdx, rdi
0x18001fc6d  jz      short loc_18001FC9B
0x18001fc6f  mov     rcx, [rdx]
0x18001fc72  mov     rax, [rdi]
0x18001fc75  mov     [rdx], rax
0x18001fc78  mov     [rdi], rcx
0x18001fc7b  mov     rcx, [rdx+8]
0x18001fc7f  mov     rax, [rdi+8]
0x18001fc83  mov     [rdx+8], rax
0x18001fc87  mov     [rdi+8], rcx
0x18001fc8b  mov     rcx, [rdx+10h]
0x18001fc8f  mov     rax, [rdi+10h]
0x18001fc93  mov     [rdx+10h], rax
0x18001fc97  mov     [rdi+10h], rcx
0x18001fc9b  add     rbx, 328h
0x18001fca2  cmp     rbx, rsi
0x18001fca5  jz      short loc_18001FCD3
0x18001fca7  mov     rcx, [rbx]
0x18001fcaa  mov     rax, [rsi]
0x18001fcad  mov     [rbx], rax
0x18001fcb0  mov     [rsi], rcx
0x18001fcb3  mov     rcx, [rbx+8]
0x18001fcb7  mov     rax, [rsi+8]
0x18001fcbb  mov     [rbx+8], rax
0x18001fcbf  mov     [rsi+8], rcx
0x18001fcc3  mov     rcx, [rbx+10h]
0x18001fcc7  mov     rax, [rsi+10h]
0x18001fccb  mov     [rbx+10h], rax
0x18001fccf  mov     [rsi+10h], rcx
0x18001fcd3  mov     rcx, [rdi+8]
0x18001fcd7  cmp     [r14], rcx
0x18001fcda  jz      loc_18001FBFD
0x18001fce0  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18001fce7  mov     [rsp+138h+var_78], rax
0x18001fcef  lea     rax, aNumresourcesre; "numResourcesReleased"
0x18001fcf6  mov     [rsp+138h+var_70], rax
0x18001fcfe  mov     rax, [rsi+8]
0x18001fd02  sub     rax, [r12]
0x18001fd06  sar     rax, 3
0x18001fd0a  sub     rcx, [r14]
0x18001fd0d  sar     rcx, 3
0x18001fd11  add     rax, rcx
0x18001fd14  mov     [rsp+138h+var_68], rax
0x18001fd1c  mov     ebx, 4
0x18001fd21  mov     [rsp+138h+var_60], bx
0x18001fd29  xorps   xmm0, xmm0
0x18001fd2c  movups  [rsp+138h+var_58], xmm0
0x18001fd34  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fd3c  movdqa  [rsp+138h+var_48], xmm1
0x18001fd45  mov     word ptr [rsp+138h+var_58], r15w
0x18001fd4e  call    cs:__imp_GetCurrentThreadId
0x18001fd54  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18001fd5b  mov     [rsp+138h+var_B8], rcx
0x18001fd63  lea     rcx, aThreadid; "threadID"
0x18001fd6a  mov     [rsp+138h+var_B0], rcx
0x18001fd72  mov     [rsp+138h+var_A8], eax
0x18001fd79  mov     [rsp+138h+var_A4], bx
0x18001fd81  xorps   xmm0, xmm0
0x18001fd84  movups  [rsp+138h+var_A0], xmm0
0x18001fd8c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fd94  movdqu  [rsp+138h+var_90], xmm1
0x18001fd9d  mov     word ptr [rsp+138h+var_A0], r15w
0x18001fda6  mov     ebx, 2
0x18001fdab  mov     r9d, ebx
0x18001fdae  lea     edi, [rbx+62h]
0x18001fdb1  mov     r8d, edi
0x18001fdb4  lea     esi, [rbx+2Eh]
0x18001fdb7  mov     edx, esi
0x18001fdb9  mov     r14d, 2351874Fh
0x18001fdbf  mov     ecx, r14d
0x18001fdc2  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18001fdc8  test    al, al
0x18001fdca  jz      short loc_18001FE2D
0x18001fdcc  lea     rax, [rsp+138h+var_B8]
0x18001fdd4  mov     [rsp+138h+var_108], rax
0x18001fdd9  lea     rax, [rsp+138h+var_78]
0x18001fde1  mov     [rsp+138h+var_100], rax
0x18001fde6  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18001fded  mov     [rsp+138h+var_D0], rax
0x18001fdf2  lea     rax, [rsp+138h+var_108]
0x18001fdf7  mov     [rsp+138h+var_C8], rax
0x18001fdfc  lea     rax, [rsp+138h+var_F8]
0x18001fe01  mov     [rsp+138h+var_C0], rax
0x18001fe06  mov     r9d, ebx
0x18001fe09  lea     rax, [rsp+138h+var_D0]
0x18001fe0e  mov     [rsp+138h+var_110], rax
0x18001fe13  lea     rax, aCachemanagerOn; "CacheManager::OnPreReleaseLock"
0x18001fe1a  mov     [rsp+138h+var_118], rax
0x18001fe1f  mov     r8d, edi
0x18001fe22  mov     edx, esi
0x18001fe24  mov     ecx, r14d
0x18001fe27  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
0x18001fe2d  lea     rcx, [rsp+138h+var_A0]
0x18001fe35  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fe3a  lea     rcx, [rsp+138h+var_58]
0x18001fe42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fe47  jmp     loc_18001FBFD
0x18001fe4c  mov     r8, [rbx+310h]
0x18001fe53  mov     r9, [rbx+318h]
0x18001fe5a  sub     r9, r8
0x18001fe5d  sar     r9, 3
0x18001fe61  mov     rdx, [rcx+8]
0x18001fe65  call    ??$_Insert_counted_range@PEAV?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@?$vector@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@V?$allocator@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@@std@@@std@@@1@PEAV?$TCntPtr@$$CBUIRefCounted@Mso@@@Mso@@_K@Z; std::vector<Mso::TCntPtr<Mso::IRefCounted const>>::_Insert_counted_range<Mso::TCntPtr<Mso::IRefCounted const> *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Mso::TCntPtr<Mso::IRefCounted const>>>>,Mso::TCntPtr<Mso::IRefCounted const> *,unsigned __int64)
0x18001fe6a  jmp     loc_18001FC38
0x18001fe6f  xor     r15d, r15d
0x18001fe72  mov     rbx, [rsp+138h+var_F0]
0x18001fe77  mov     rsi, [rsp+138h+var_E8]
0x18001fe7c  mov     rdi, [rsp+138h+var_E0]
0x18001fe81  mov     r12, rsi
0x18001fe84  mov     r14, rdi
0x18001fe87  jmp     loc_18001FC63
```
