# Windows::UsoProductEnumerator::GetProducts(void)

- ea: `0x140370ce4`
- end: `0x140370fd5`
- name: `?GetProducts@UsoProductEnumerator@Windows@@QEAA?AV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@Ucase_insensitive_less@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@XZ`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1402dcd74`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x14004519c`
- `0x140045404`
- `0x140053618`
- `0x140370ce4`
- `0x140371070`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370eca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370eca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370f42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140370e12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140370e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140370dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140370dff`

## string_xrefs

- `0x140370f99`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370fae`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370fc3`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::UsoProductEnumerator::GetProducts(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned int i; // r12d
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r15
  _QWORD *v13; // rsi
  void *v14; // r14
  DWORD LastError; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  void *v19; // rbx
  __int64 v20; // r8
  void *v21; // rax
  __int64 v22; // r8
  void *v23; // rax
  __int128 v25; // [rsp+20h] [rbp-60h] BYREF
  __int128 v26; // [rsp+30h] [rbp-50h]
  int v27; // [rsp+40h] [rbp-40h]
  __int64 v28; // [rsp+48h] [rbp-38h]
  LPVOID pv; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v30; // [rsp+58h] [rbp-28h] BYREF
  LPVOID v31; // [rsp+60h] [rbp-20h] BYREF
  __int64 *v32; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v28 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(96);
  *(_QWORD *)v4 = v4;
  *(_QWORD *)(v4 + 8) = v4;
  *(_QWORD *)(v4 + 16) = v4;
  *(_WORD *)(v4 + 24) = 257;
  *(_QWORD *)a2 = v4;
  v27 = 1;
  for ( i = 0; i < *(_DWORD *)a1; ++i )
  {
    v32 = 0;
    v6 = *(__int64 **)(a1 + 24);
    v7 = *v6;
    *(_QWORD *)&v25 = &v32;
    *((_QWORD *)&v25 + 1) = 0;
    LOBYTE(v26) = 1;
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, char *))(v7 + 32))(v6, i, (char *)&v25 + 8);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
        (const char *)(unsigned int)v8,
        v25);
    if ( (_BYTE)v26 )
    {
      v9 = *(_QWORD *)v25;
      *(_QWORD *)v25 = *((_QWORD *)&v25 + 1);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v31 = 0;
    v10 = *v32;
    *(_QWORD *)&v25 = &v31;
    *((_QWORD *)&v25 + 1) = 0;
    LOBYTE(v26) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64 *, char *))(v10 + 24))(v32, (char *)&v25 + 8);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
        (const char *)(unsigned int)v11,
        v25);
    if ( (_BYTE)v26 )
    {
      v12 = *((_QWORD *)&v25 + 1);
      v13 = (_QWORD *)v25;
      v14 = *(void **)v25;
      if ( *(_QWORD *)v25 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v14);
        SetLastError(LastError);
      }
      *v13 = v12;
    }
    v30 = 0;
    v16 = *v32;
    v30 = 0;
    if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v16 + 40))(v32, L"Version", &v30) < 0 )
    {
      v25 = 0;
      v26 = 0;
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)v31 + v22) );
      std::wstring::_Construct<1,wchar_t const *>(&v25, v31, v22);
      v23 = (void *)std::map<std::wstring,std::wstring,case_insensitive_less,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
                      a2,
                      &v25);
      std::wstring::operator=(v23, L"0.0.0.0");
      std::wstring::~wstring(&v25);
    }
    else
    {
      pv = 0;
      v17 = *v30;
      pv = 0;
      v18 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v17 + 32))(v30, &pv);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v18,
          v25);
      v19 = pv;
      v25 = 0;
      v26 = 0;
      v20 = -1;
      do
        ++v20;
      while ( *((_WORD *)v31 + v20) );
      std::wstring::_Construct<1,wchar_t const *>(&v25, v31, v20);
      v21 = (void *)std::map<std::wstring,std::wstring,case_insensitive_less,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
                      a2,
                      &v25);
      std::wstring::operator=(v21, v19);
      std::wstring::~wstring(&v25);
      if ( pv )
        CoTaskMemFree(pv);
    }
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    if ( v31 )
      CoTaskMemFree(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
  }
  return a2;
}

```

## disassembly

```asm
0x140370ce4  mov     [rsp-38h+arg_10], rbx
0x140370ce9  push    rbp
0x140370cea  push    rsi
0x140370ceb  push    rdi
0x140370cec  push    r12
0x140370cee  push    r13
0x140370cf0  push    r14
0x140370cf2  push    r15
0x140370cf4  mov     rbp, rsp
0x140370cf7  sub     rsp, 80h
0x140370cfe  mov     rax, cs:__security_cookie
0x140370d05  xor     rax, rsp
0x140370d08  mov     [rbp+var_10], rax
0x140370d0c  mov     rdi, rdx
0x140370d0f  mov     r13, rcx
0x140370d12  mov     [rbp+var_38], rdx
0x140370d16  xor     esi, esi
0x140370d18  mov     [rbp+var_40], esi
0x140370d1b  xorps   xmm0, xmm0
0x140370d1e  movups  xmmword ptr [rdx], xmm0
0x140370d21  mov     [rdx], rsi
0x140370d24  mov     [rdx+8], rsi
0x140370d28  lea     ecx, [rsi+60h]
0x140370d2b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140370d30  mov     [rax], rax
0x140370d33  mov     [rax+8], rax
0x140370d37  mov     [rax+10h], rax
0x140370d3b  mov     word ptr [rax+18h], 101h
0x140370d41  mov     [rdi], rax
0x140370d44  mov     [rbp+var_40], 1
0x140370d4b  mov     r12d, esi
0x140370d4e  cmp     [r13+0], esi
0x140370d52  jbe     loc_140370F6C
0x140370d58  mov     [rbp+var_18], rsi
0x140370d5c  mov     rcx, [r13+18h]
0x140370d60  mov     rax, [rcx]
0x140370d63  lea     rdx, [rbp+var_18]
0x140370d67  mov     qword ptr [rbp+var_60], rdx
0x140370d6b  mov     qword ptr [rbp+var_60+8], rsi
0x140370d6f  mov     byte ptr [rbp+var_50], 1
0x140370d73  lea     r8, [rbp+var_60+8]
0x140370d77  mov     edx, r12d
0x140370d7a  mov     rax, [rax+20h]
0x140370d7e  call    _guard_dispatch_icall
0x140370d83  mov     rcx, [rbp+38h]; this
0x140370d87  test    eax, eax
0x140370d89  js      loc_140370FAB
0x140370d8f  cmp     byte ptr [rbp+var_50], sil
0x140370d93  jz      short loc_140370DB5
0x140370d95  mov     rdx, qword ptr [rbp+var_60]
0x140370d99  mov     rcx, [rdx]
0x140370d9c  mov     rax, qword ptr [rbp+var_60+8]
0x140370da0  mov     [rdx], rax
0x140370da3  test    rcx, rcx
0x140370da6  jz      short loc_140370DB5
0x140370da8  mov     rax, [rcx]
0x140370dab  mov     rax, [rax+10h]
0x140370daf  call    _guard_dispatch_icall
0x140370db4  nop
0x140370db5  mov     [rbp+var_20], rsi
0x140370db9  mov     rcx, [rbp+var_18]
0x140370dbd  mov     rax, [rcx]
0x140370dc0  lea     rdx, [rbp+var_20]
0x140370dc4  mov     qword ptr [rbp+var_60], rdx
0x140370dc8  mov     qword ptr [rbp+var_60+8], rsi
0x140370dcc  mov     byte ptr [rbp+var_50], 1
0x140370dd0  lea     rdx, [rbp+var_60+8]
0x140370dd4  mov     rax, [rax+18h]
0x140370dd8  call    _guard_dispatch_icall
0x140370ddd  mov     rcx, [rbp+38h]; this
0x140370de1  test    eax, eax
0x140370de3  js      loc_140370F96
0x140370de9  cmp     byte ptr [rbp+var_50], sil
0x140370ded  jz      short loc_140370E1D
0x140370def  mov     r15, qword ptr [rbp+var_60+8]
0x140370df3  mov     rsi, qword ptr [rbp+var_60]
0x140370df7  mov     r14, [rsi]
0x140370dfa  test    r14, r14
0x140370dfd  jz      short loc_140370E18
0x140370dff  call    cs:__imp_GetLastError
0x140370e05  mov     ebx, eax
0x140370e07  mov     rcx, r14; pv
0x140370e0a  call    cs:__imp_CoTaskMemFree
0x140370e10  mov     ecx, ebx; dwErrCode
0x140370e12  call    cs:__imp_SetLastError
0x140370e18  mov     [rsi], r15
0x140370e1b  xor     esi, esi
0x140370e1d  mov     [rbp+var_28], rsi
0x140370e21  mov     rcx, [rbp+var_18]
0x140370e25  mov     rax, [rcx]
0x140370e28  mov     [rbp+var_28], rsi
0x140370e2c  lea     r8, [rbp+var_28]
0x140370e30  lea     rdx, aVersion_0; "Version"
0x140370e37  mov     rax, [rax+28h]
0x140370e3b  call    _guard_dispatch_icall
0x140370e40  test    eax, eax
0x140370e42  js      loc_140370ED2
0x140370e48  mov     [rbp+pv], rsi
0x140370e4c  mov     rcx, [rbp+var_28]
0x140370e50  mov     rax, [rcx]
0x140370e53  mov     [rbp+pv], rsi
0x140370e57  lea     rdx, [rbp+pv]
0x140370e5b  mov     rax, [rax+20h]
0x140370e5f  call    _guard_dispatch_icall
0x140370e64  mov     rcx, [rbp+38h]; this
0x140370e68  test    eax, eax
0x140370e6a  js      loc_140370FC0
0x140370e70  mov     rbx, [rbp+pv]
0x140370e74  xorps   xmm0, xmm0
0x140370e77  movups  [rbp+var_60], xmm0
0x140370e7b  xorps   xmm1, xmm1
0x140370e7e  movdqu  [rbp+var_50], xmm1
0x140370e83  mov     rdx, [rbp+var_20]
0x140370e87  or      r8, 0FFFFFFFFFFFFFFFFh
0x140370e8b  inc     r8
0x140370e8e  cmp     [rdx+r8*2], si
0x140370e93  jnz     short loc_140370E8B
0x140370e95  lea     rcx, [rbp+var_60]
0x140370e99  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140370e9e  nop
0x140370e9f  lea     rdx, [rbp+var_60]
0x140370ea3  mov     rcx, rdi
0x140370ea6  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@Ucase_insensitive_less@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring,case_insensitive_less,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring &&)
0x140370eab  mov     rcx, rax; void *
0x140370eae  mov     rdx, rbx; Src
0x140370eb1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x140370eb6  nop
0x140370eb7  lea     rcx, [rbp+var_60]
0x140370ebb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140370ec0  nop
0x140370ec1  mov     rcx, [rbp+pv]; pv
0x140370ec5  test    rcx, rcx
0x140370ec8  jz      short loc_140370F23
0x140370eca  call    cs:__imp_CoTaskMemFree
0x140370ed0  jmp     short loc_140370F23
0x140370ed2  xorps   xmm0, xmm0
0x140370ed5  movups  [rbp+var_60], xmm0
0x140370ed9  xorps   xmm1, xmm1
0x140370edc  movdqu  [rbp+var_50], xmm1
0x140370ee1  mov     rdx, [rbp+var_20]
0x140370ee5  or      r8, 0FFFFFFFFFFFFFFFFh
0x140370ee9  inc     r8
0x140370eec  cmp     [rdx+r8*2], si
0x140370ef1  jnz     short loc_140370EE9
0x140370ef3  lea     rcx, [rbp+var_60]
0x140370ef7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140370efc  nop
0x140370efd  lea     rdx, [rbp+var_60]
0x140370f01  mov     rcx, rdi
0x140370f04  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@Ucase_insensitive_less@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring,case_insensitive_less,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring &&)
0x140370f09  mov     rcx, rax; void *
0x140370f0c  lea     rdx, a0000_0; "0.0.0.0"
0x140370f13  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x140370f18  nop
0x140370f19  lea     rcx, [rbp+var_60]
0x140370f1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140370f22  nop
0x140370f23  mov     rcx, [rbp+var_28]
0x140370f27  test    rcx, rcx
0x140370f2a  jz      short loc_140370F39
0x140370f2c  mov     rax, [rcx]
0x140370f2f  mov     rax, [rax+10h]
0x140370f33  call    _guard_dispatch_icall
0x140370f38  nop
0x140370f39  mov     rcx, [rbp+var_20]; pv
0x140370f3d  test    rcx, rcx
0x140370f40  jz      short loc_140370F49
0x140370f42  call    cs:__imp_CoTaskMemFree
0x140370f48  nop
0x140370f49  mov     rcx, [rbp+var_18]
0x140370f4d  test    rcx, rcx
0x140370f50  jz      short loc_140370F5F
0x140370f52  mov     rax, [rcx]
0x140370f55  mov     rax, [rax+10h]
0x140370f59  call    _guard_dispatch_icall
0x140370f5e  nop
0x140370f5f  inc     r12d
0x140370f62  cmp     r12d, [r13+0]
0x140370f66  jb      loc_140370D58
0x140370f6c  mov     rax, rdi
0x140370f6f  mov     rcx, [rbp+var_10]
0x140370f73  xor     rcx, rsp; StackCookie
0x140370f76  call    __security_check_cookie
0x140370f7b  mov     rbx, [rsp+80h+arg_10]
0x140370f83  add     rsp, 80h
0x140370f8a  pop     r15
0x140370f8c  pop     r14
0x140370f8e  pop     r13
0x140370f90  pop     r12
0x140370f92  pop     rdi
0x140370f93  pop     rsi
0x140370f94  pop     rbp
0x140370f95  retn
0x140370f96  mov     r9d, eax; char *
0x140370f99  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140370fa0  mov     edx, 120h; void *
0x140370fa5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140370fab  mov     r9d, eax; char *
0x140370fae  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140370fb5  mov     edx, 11Dh; void *
0x140370fba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140370fc0  mov     r9d, eax; char *
0x140370fc3  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140370fca  mov     edx, 125h; void *
0x140370fcf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
