# win_dox::OpcRelationship::GetRelationshipType(void)

- ea: `0x180099450`
- end: `0x180099564`
- name: `?GetRelationshipType@OpcRelationship@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8754`
- `0x1800a88a8`
- `0x1800a9490`
- `0x1800f4c9c`
- `0x180105cdc`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x180099450`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009953a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009953a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationship::GetRelationshipType(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  signed int v5; // edi
  LPVOID pv[4]; // [rsp+40h] [rbp-4D8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4B8h] BYREF
  wchar_t v9[512]; // [rsp+100h] [rbp-418h] BYREF

  pv[2] = (LPVOID)-2LL;
  pv[0] = 0;
  v3 = *a1;
  v4 = *v3;
  pv[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 32))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetRelationshipType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x58u,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring(a2, pv[0]);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return a2;
}

```

## disassembly

```asm
0x180099450  mov     rax, rsp
0x180099453  push    rdi
0x180099454  sub     rsp, 510h
0x18009945b  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x180099464  mov     [rax+18h], rbx
0x180099468  mov     rax, cs:__security_cookie
0x18009946f  xor     rax, rsp
0x180099472  mov     [rsp+518h+var_18], rax
0x18009947a  mov     rbx, rdx
0x18009947d  mov     [rsp+518h+pv], rdx
0x180099482  mov     [rsp+518h+pv], 0
0x18009948b  mov     rcx, [rcx]
0x18009948e  mov     rax, [rcx]
0x180099491  mov     [rsp+518h+pv], 0
0x18009949a  lea     rdx, [rsp+518h+pv]
0x18009949f  mov     rax, [rax+20h]
0x1800994a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800994a8  mov     edi, eax
0x1800994aa  test    eax, eax
0x1800994ac  jns     short loc_180099522
0x1800994ae  xor     edx, edx; Val
0x1800994b0  mov     r8d, 400h; Size
0x1800994b6  lea     rcx, [rsp+518h+var_418]; void *
0x1800994be  call    memset_0
0x1800994c3  mov     r9d, edi
0x1800994c6  lea     r8, aCallToGetrelat; "Call to GetRelationshipType failed with"...
0x1800994cd  mov     edx, 200h; unsigned __int64
0x1800994d2  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800994da  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800994df  lea     rax, [rsp+518h+var_418]
0x1800994e7  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800994ec  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800994f0  mov     [rsp+518h+var_4F8], 58h ; 'X'; unsigned int
0x1800994f8  lea     r9, word_18013A0B6
0x1800994ff  lea     r8, aNoFilename; "(no filename)"
0x180099506  lea     rcx, [rsp+518h+pExceptionObject]; this
0x18009950b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180099510  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180099517  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x18009951c  call    _CxxThrowException_0
0x180099522  mov     rdx, [rsp+518h+pv]
0x180099527  mov     rcx, rbx
0x18009952a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009952f  nop
0x180099530  mov     rcx, [rsp+518h+pv]; pv
0x180099535  test    rcx, rcx
0x180099538  jz      short loc_180099540
0x18009953a  call    cs:__imp_CoTaskMemFree
0x180099540  mov     rax, rbx
0x180099543  mov     rcx, [rsp+518h+var_18]
0x18009954b  xor     rcx, rsp; StackCookie
0x18009954e  call    __security_check_cookie
0x180099553  mov     rbx, [rsp+518h+arg_10]
0x18009955b  add     rsp, 510h
0x180099562  pop     rdi
0x180099563  retn
```
