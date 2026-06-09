# _anonymous_namespace_::GetUserFromStateRepo

- ea: `0x18006e4f4`
- end: `0x18006e825`
- name: `_anonymous_namespace_::GetUserFromStateRepo`
- size: `817`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800694cc`
- `0x18006e0c0`
- `0x18006fde0`

## callees

- `0x1800060a0`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x18006e4f4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e6c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e6c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e6a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e6a3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006e581`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006e581`

## string_xrefs

- `0x18006e7e1`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e7f6`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006e813`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 *__fastcall anonymous_namespace_::GetUserFromStateRepo(__int64 *a1, char *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  int v9; // eax
  int v10; // ecx
  PVOID Reserved1; // rbx
  __int64 (__fastcall *v12)(PVOID, _QWORD, __int64 *); // rdi
  __int64 v13; // rcx
  unsigned int v14; // r14d
  int v15; // r12d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  char *v19; // rbx
  PCWSTR StringRawBuffer; // rax
  signed __int64 v21; // rbx
  int v22; // edx
  int v23; // ecx
  PVOID v24; // rbx
  __int64 (__fastcall *v25)(PVOID, _QWORD, __int64 *); // rdi
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+20h] [rbp-49h] BYREF
  int v34; // [rsp+28h] [rbp-41h]
  HSTRING v35; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-21h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  __int64 v39; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v36[1] = a1;
  v34 = 0;
  v33 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_41:
    wil::details::in1diag3::Throw_Hr(
      v8,
      (void *)0x2E,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v33);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v33);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_41;
  v36[0] = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v33 + 96LL))(v33, v36);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v9,
      v33);
  *a1 = 0;
  v34 = 1;
  hstringHeader.Reserved.Reserved1 = (PVOID)v36[0];
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &string;
  LODWORD(string) = 0;
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v36[0] + 56LL))(
          v36[0],
          &hstringHeader.Reserved.Reserved2[8]);
  **(_DWORD **)&hstringHeader.Reserved.Reserved2[16] = v10;
  v34 = 7;
  if ( v10 >= 0 && *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
  {
    Reserved1 = hstringHeader.Reserved.Reserved1;
    v12 = *(__int64 (__fastcall **)(PVOID, _QWORD, __int64 *))(*(_QWORD *)hstringHeader.Reserved.Reserved1 + 48LL);
    v13 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v10 = v12(Reserved1, 0, &v39);
    **(_DWORD **)&hstringHeader.Reserved.Reserved2[16] = v10;
  }
  v14 = 0;
  v15 = *(_DWORD *)&hstringHeader.Reserved.Reserved2[8];
  while ( v10 >= 0 && v14 != v15 )
  {
    v35 = 0;
    v16 = v39;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 64LL);
    WindowsDeleteString(0);
    v35 = 0;
    v18 = v17(v16, &v35);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v18,
        v33);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v19 = a2;
    else
      v19 = *(char **)a2;
    StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
    v21 = v19 - (char *)StringRawBuffer;
    do
    {
      v22 = *(PCWSTR)((char *)StringRawBuffer + v21);
      v23 = *StringRawBuffer - v22;
      if ( v23 )
        break;
      ++StringRawBuffer;
    }
    while ( v22 );
    if ( !v23 )
    {
      v27 = v39;
      if ( *a1 != v39 )
      {
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
        v28 = *a1;
        *a1 = v27;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      WindowsDeleteString(v35);
      break;
    }
    WindowsDeleteString(v35);
    ++v14;
    v10 = **(_DWORD **)&hstringHeader.Reserved.Reserved2[16];
    if ( (int)**(_DWORD **)&hstringHeader.Reserved.Reserved2[16] < 0 )
      break;
    if ( v14 < *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
    {
      v24 = hstringHeader.Reserved.Reserved1;
      v25 = *(__int64 (__fastcall **)(PVOID, _QWORD, __int64 *))(*(_QWORD *)hstringHeader.Reserved.Reserved1 + 48LL);
      v26 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v10 = v25(v24, v14, &v39);
      **(_DWORD **)&hstringHeader.Reserved.Reserved2[16] = v10;
    }
  }
  v29 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v36[0];
  if ( v36[0] )
  {
    v36[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return a1;
}

```

## disassembly

```asm
0x18006e4f4  push    rbp
0x18006e4f6  push    rbx
0x18006e4f7  push    rsi
0x18006e4f8  push    rdi
0x18006e4f9  push    r12
0x18006e4fb  push    r13
0x18006e4fd  push    r14
0x18006e4ff  push    r15
0x18006e501  lea     rbp, [rsp-1Fh]
0x18006e506  sub     rsp, 88h
0x18006e50d  mov     rax, cs:__security_cookie
0x18006e514  xor     rax, rsp
0x18006e517  mov     [rbp+57h+var_50], rax
0x18006e51b  mov     r15, rdx
0x18006e51e  mov     rsi, rcx
0x18006e521  mov     [rbp+57h+var_80], rcx
0x18006e525  xor     r13d, r13d
0x18006e528  mov     [rbp+57h+var_98], r13d
0x18006e52c  mov     [rbp+57h+var_A0], r13
0x18006e530  mov     [rbp+57h+string], r13
0x18006e534  lea     r9, [rbp+57h+string]; string
0x18006e538  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006e53c  lea     edx, [r13+25h]; length
0x18006e540  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18006e547  call    cs:__imp_WindowsCreateStringReference
0x18006e54d  test    eax, eax
0x18006e54f  js      loc_18006E808
0x18006e555  mov     rbx, [rbp+57h+string]
0x18006e559  mov     rcx, [rbp+57h+var_A0]
0x18006e55d  test    rcx, rcx
0x18006e560  jz      short loc_18006E573
0x18006e562  mov     [rbp+57h+var_A0], r13
0x18006e566  mov     rax, [rcx]
0x18006e569  mov     rax, [rax+10h]
0x18006e56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e572  nop
0x18006e573  lea     r8, [rbp+57h+var_A0]
0x18006e577  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18006e57e  mov     rcx, rbx
0x18006e581  call    cs:__imp_RoGetActivationFactory
0x18006e587  mov     rcx, [rbp+5Fh]
0x18006e58b  test    eax, eax
0x18006e58d  js      loc_18006E810
0x18006e593  mov     [rbp+57h+var_88], r13
0x18006e597  mov     rcx, [rbp+57h+var_A0]
0x18006e59b  mov     rax, [rcx]
0x18006e59e  lea     rdx, [rbp+57h+var_88]
0x18006e5a2  mov     rax, [rax+60h]
0x18006e5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5ab  mov     rcx, [rbp+5Fh]; this
0x18006e5af  test    eax, eax
0x18006e5b1  js      loc_18006E7DE
0x18006e5b7  mov     [rsi], r13
0x18006e5ba  mov     [rbp+57h+var_98], 1
0x18006e5c1  mov     rcx, [rbp+57h+var_88]
0x18006e5c5  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x18006e5c9  lea     rax, [rbp+57h+string]
0x18006e5cd  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18006e5d1  mov     dword ptr [rbp+57h+string], r13d
0x18006e5d5  mov     [rbp+57h+var_58], r13
0x18006e5d9  mov     rax, [rcx]
0x18006e5dc  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]
0x18006e5e0  mov     rax, [rax+38h]
0x18006e5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5e9  mov     ecx, eax
0x18006e5eb  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18006e5ef  mov     [rax], ecx
0x18006e5f1  mov     [rbp+57h+var_98], 7
0x18006e5f8  test    ecx, ecx
0x18006e5fa  js      short loc_18006E640
0x18006e5fc  cmp     dword ptr [rbp+57h+hstringHeader.Reserved+8], r13d
0x18006e600  jbe     short loc_18006E640
0x18006e602  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18006e606  mov     rax, [rbx]
0x18006e609  mov     rdi, [rax+30h]
0x18006e60d  mov     rcx, [rbp+57h+var_58]
0x18006e611  test    rcx, rcx
0x18006e614  jz      short loc_18006E627
0x18006e616  mov     [rbp+57h+var_58], r13
0x18006e61a  mov     rax, [rcx]
0x18006e61d  mov     rax, [rax+10h]
0x18006e621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e626  nop
0x18006e627  lea     r8, [rbp+57h+var_58]
0x18006e62b  xor     edx, edx
0x18006e62d  mov     rcx, rbx
0x18006e630  mov     rax, rdi
0x18006e633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e638  mov     ecx, eax
0x18006e63a  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18006e63e  mov     [rax], ecx
0x18006e640  mov     r14d, r13d
0x18006e643  mov     r12d, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18006e647  test    ecx, ecx
0x18006e649  js      loc_18006E76D
0x18006e64f  cmp     r14d, r12d
0x18006e652  jz      loc_18006E76D
0x18006e658  mov     [rbp+57h+var_90], r13
0x18006e65c  mov     rdi, [rbp+57h+var_58]
0x18006e660  mov     rax, [rdi]
0x18006e663  mov     rbx, [rax+40h]
0x18006e667  xor     ecx, ecx; string
0x18006e669  call    cs:__imp_WindowsDeleteString
0x18006e66f  mov     [rbp+57h+var_90], r13
0x18006e673  lea     rdx, [rbp+57h+var_90]
0x18006e677  mov     rcx, rdi
0x18006e67a  mov     rax, rbx
0x18006e67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e682  mov     rcx, [rbp+5Fh]; this
0x18006e686  test    eax, eax
0x18006e688  js      loc_18006E7F3
0x18006e68e  cmp     qword ptr [r15+18h], 7
0x18006e693  jbe     short loc_18006E69A
0x18006e695  mov     rbx, [r15]
0x18006e698  jmp     short loc_18006E69D
0x18006e69a  mov     rbx, r15
0x18006e69d  xor     edx, edx; length
0x18006e69f  mov     rcx, [rbp+57h+var_90]; string
0x18006e6a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e6a9  sub     rbx, rax
0x18006e6ac  movzx   ecx, word ptr [rax]
0x18006e6af  movzx   edx, word ptr [rax+rbx]
0x18006e6b3  sub     ecx, edx
0x18006e6b5  jnz     short loc_18006E6BF
0x18006e6b7  add     rax, 2
0x18006e6bb  test    edx, edx
0x18006e6bd  jnz     short loc_18006E6AC
0x18006e6bf  test    ecx, ecx
0x18006e6c1  jz      short loc_18006E72C
0x18006e6c3  mov     rcx, [rbp+57h+var_90]; string
0x18006e6c7  call    cs:__imp_WindowsDeleteString
0x18006e6cd  inc     r14d
0x18006e6d0  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18006e6d4  mov     ecx, [rax]
0x18006e6d6  test    ecx, ecx
0x18006e6d8  js      loc_18006E76D
0x18006e6de  cmp     r14d, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18006e6e2  jnb     loc_18006E647
0x18006e6e8  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18006e6ec  mov     rax, [rbx]
0x18006e6ef  mov     rdi, [rax+30h]
0x18006e6f3  mov     rcx, [rbp+57h+var_58]
0x18006e6f7  test    rcx, rcx
0x18006e6fa  jz      short loc_18006E70D
0x18006e6fc  mov     [rbp+57h+var_58], r13
0x18006e700  mov     rax, [rcx]
0x18006e703  mov     rax, [rax+10h]
0x18006e707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e70c  nop
0x18006e70d  lea     r8, [rbp+57h+var_58]
0x18006e711  mov     edx, r14d
0x18006e714  mov     rcx, rbx
0x18006e717  mov     rax, rdi
0x18006e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e71f  mov     ecx, eax
0x18006e721  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18006e725  mov     [rax], ecx
0x18006e727  jmp     loc_18006E647
0x18006e72c  mov     rbx, [rbp+57h+var_58]
0x18006e730  cmp     [rsi], rbx
0x18006e733  jz      short loc_18006E762
0x18006e735  test    rbx, rbx
0x18006e738  jz      short loc_18006E74A
0x18006e73a  mov     rax, [rbx]
0x18006e73d  mov     rcx, rbx
0x18006e740  mov     rax, [rax+8]
0x18006e744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e749  nop
0x18006e74a  mov     rcx, [rsi]
0x18006e74d  mov     [rsi], rbx
0x18006e750  test    rcx, rcx
0x18006e753  jz      short loc_18006E762
0x18006e755  mov     rax, [rcx]
0x18006e758  mov     rax, [rax+10h]
0x18006e75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e761  nop
0x18006e762  mov     rcx, [rbp+57h+var_90]; string
0x18006e766  call    cs:__imp_WindowsDeleteString
0x18006e76c  nop
0x18006e76d  mov     rcx, [rbp+57h+var_58]
0x18006e771  test    rcx, rcx
0x18006e774  jz      short loc_18006E787
0x18006e776  mov     [rbp+57h+var_58], r13
0x18006e77a  mov     rax, [rcx]
0x18006e77d  mov     rax, [rax+10h]
0x18006e781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e786  nop
0x18006e787  mov     rcx, [rbp+57h+var_88]
0x18006e78b  test    rcx, rcx
0x18006e78e  jz      short loc_18006E7A1
0x18006e790  mov     [rbp+57h+var_88], r13
0x18006e794  mov     rax, [rcx]
0x18006e797  mov     rax, [rax+10h]
0x18006e79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7a0  nop
0x18006e7a1  mov     rcx, [rbp+57h+var_A0]
0x18006e7a5  test    rcx, rcx
0x18006e7a8  jz      short loc_18006E7BB
0x18006e7aa  mov     [rbp+57h+var_A0], r13
0x18006e7ae  mov     rdx, [rcx]
0x18006e7b1  mov     rax, [rdx+10h]
0x18006e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7ba  nop
0x18006e7bb  mov     rax, rsi
0x18006e7be  mov     rcx, [rbp+57h+var_50]
0x18006e7c2  xor     rcx, rsp; StackCookie
0x18006e7c5  call    __security_check_cookie
0x18006e7ca  add     rsp, 88h
0x18006e7d1  pop     r15
0x18006e7d3  pop     r14
0x18006e7d5  pop     r13
0x18006e7d7  pop     r12
0x18006e7d9  pop     rdi
0x18006e7da  pop     rsi
0x18006e7db  pop     rbx
0x18006e7dc  pop     rbp
0x18006e7dd  retn
0x18006e7de  mov     r9d, eax; char *
0x18006e7e1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e7e8  mov     edx, 31h ; '1'; void *
0x18006e7ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e7f3  mov     r9d, eax; char *
0x18006e7f6  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e7fd  mov     edx, 38h ; '8'; void *
0x18006e802  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e808  mov     ecx, eax; this
0x18006e80a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006e80f  nop
0x18006e810  mov     r9d, eax; char *
0x18006e813  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006e81a  mov     edx, 2Eh ; '.'; void *
0x18006e81f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
