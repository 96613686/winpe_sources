# win_dox::OpcPart::GetContentType(void)

- ea: `0x1800a1244`
- end: `0x1800a1358`
- name: `?GetContentType@OpcPart@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009f44c`
- `0x18009f9c4`
- `0x1800a0a48`
- `0x1800a1360`
- `0x1800a35e8`
- `0x1800a4724`
- `0x1800a8e7c`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800a1244`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a132e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a132e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcPart::GetContentType(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 48))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetContentType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Au,
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
0x1800a1244  mov     rax, rsp
0x1800a1247  push    rdi
0x1800a1248  sub     rsp, 510h
0x1800a124f  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800a1258  mov     [rax+18h], rbx
0x1800a125c  mov     rax, cs:__security_cookie
0x1800a1263  xor     rax, rsp
0x1800a1266  mov     [rsp+518h+var_18], rax
0x1800a126e  mov     rbx, rdx
0x1800a1271  mov     [rsp+518h+pv], rdx
0x1800a1276  mov     [rsp+518h+pv], 0
0x1800a127f  mov     rcx, [rcx]
0x1800a1282  mov     rax, [rcx]
0x1800a1285  mov     [rsp+518h+pv], 0
0x1800a128e  lea     rdx, [rsp+518h+pv]
0x1800a1293  mov     rax, [rax+30h]
0x1800a1297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a129c  mov     edi, eax
0x1800a129e  test    eax, eax
0x1800a12a0  jns     short loc_1800A1316
0x1800a12a2  xor     edx, edx; Val
0x1800a12a4  mov     r8d, 400h; Size
0x1800a12aa  lea     rcx, [rsp+518h+var_418]; void *
0x1800a12b2  call    memset_0
0x1800a12b7  mov     r9d, edi
0x1800a12ba  lea     r8, aCallToGetconte; "Call to GetContentType failed with HRes"...
0x1800a12c1  mov     edx, 200h; unsigned __int64
0x1800a12c6  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800a12ce  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a12d3  lea     rax, [rsp+518h+var_418]
0x1800a12db  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800a12e0  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800a12e4  mov     [rsp+518h+var_4F8], 7Ah ; 'z'; unsigned int
0x1800a12ec  lea     r9, word_18013A0B6
0x1800a12f3  lea     r8, aNoFilename; "(no filename)"
0x1800a12fa  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800a12ff  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a1304  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a130b  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800a1310  call    _CxxThrowException_0
0x1800a1316  mov     rdx, [rsp+518h+pv]
0x1800a131b  mov     rcx, rbx
0x1800a131e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800a1323  nop
0x1800a1324  mov     rcx, [rsp+518h+pv]; pv
0x1800a1329  test    rcx, rcx
0x1800a132c  jz      short loc_1800A1334
0x1800a132e  call    cs:__imp_CoTaskMemFree
0x1800a1334  mov     rax, rbx
0x1800a1337  mov     rcx, [rsp+518h+var_18]
0x1800a133f  xor     rcx, rsp; StackCookie
0x1800a1342  call    __security_check_cookie
0x1800a1347  mov     rbx, [rsp+518h+arg_10]
0x1800a134f  add     rsp, 510h
0x1800a1356  pop     rdi
0x1800a1357  retn
```
