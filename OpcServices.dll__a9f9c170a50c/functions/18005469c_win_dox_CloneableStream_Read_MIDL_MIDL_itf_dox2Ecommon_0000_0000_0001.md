# win_dox::CloneableStream::Read(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x18005469c`
- end: `0x180054867`
- name: `?Read@CloneableStream@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b63e0`

## callees

- `0x180015a68`
- `0x1800517a0`
- `0x18005469c`
- `0x180054afc`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800546fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800546fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054772`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054772`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800546eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800546eb`

## string_xrefs

- `0x180054813`: `Call to Read failed with HResult 0x%X.`
- `0x1800547b9`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_dox::CloneableStream::Read(__int64 *a1, unsigned int *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r15
  int v6; // ecx
  signed int v7; // esi
  __int64 v8; // rsi
  _QWORD v11[3]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+60h] [rbp-A8h]
  __int64 v13; // [rsp+68h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v15[512]; // [rsp+118h] [rbp+10h] BYREF

  v11[1] = -2;
  v4 = a1[2];
  v5 = *a1;
  v11[2] = v4 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v6 = *(_DWORD *)(v4 + 52);
  *(_DWORD *)(v4 + 52) = v6 + 1;
  if ( !v6 )
    *(_DWORD *)(v4 + 48) = GetCurrentThreadId();
  LOBYTE(v12) = 1;
  v13 = v4;
  if ( !*(_BYTE *)(v4 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)v4 != v5 )
    win_dox::Stream::Seek(v4 + 64, v5, 0);
  LODWORD(v11[0]) = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**(_QWORD **)(v4 + 64) + 24LL))(
         *(_QWORD *)(v4 + 64),
         *((_QWORD *)a2 + 1),
         *a2,
         v11);
  if ( v7 < 0 )
  {
    memset_0(v15, 0, sizeof(v15));
    StringCchPrintfW(v15, 0x200u, L"Call to Read failed with HResult 0x%X.", (unsigned int)v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60u,
      v7,
      (struct win_musl::TStringEllipseBase *)v15);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = LODWORD(v11[0]);
  *(_QWORD *)v4 = LODWORD(v11[0]) + v5;
  if ( v4 != -8 )
  {
    if ( (*(_DWORD *)(v4 + 52))-- == 1 )
      *(_DWORD *)(v4 + 48) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  }
  *a1 += v8;
  return LODWORD(v11[0]);
}

```

## disassembly

```asm
0x18005469c  mov     rax, rsp
0x18005469f  push    rbp
0x1800546a0  push    rsi
0x1800546a1  push    rdi
0x1800546a2  push    r14
0x1800546a4  push    r15
0x1800546a6  lea     rbp, [rax-448h]
0x1800546ad  sub     rsp, 520h
0x1800546b4  mov     [rsp+540h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x1800546bd  mov     [rax+18h], rbx
0x1800546c1  mov     rax, cs:__security_cookie
0x1800546c8  xor     rax, rsp
0x1800546cb  mov     [rbp+440h+var_30], rax
0x1800546d2  mov     rsi, rdx
0x1800546d5  mov     r14, rcx
0x1800546d8  mov     rdi, [rcx+10h]
0x1800546dc  mov     r15, [rcx]
0x1800546df  lea     rbx, [rdi+8]
0x1800546e3  mov     qword ptr [rsp+540h+var_4F0], rbx
0x1800546e8  mov     rcx, rbx; lpCriticalSection
0x1800546eb  call    cs:__imp_EnterCriticalSection
0x1800546f1  mov     ecx, [rbx+2Ch]
0x1800546f4  lea     eax, [rcx+1]
0x1800546f7  mov     [rbx+2Ch], eax
0x1800546fa  test    ecx, ecx
0x1800546fc  jnz     short loc_180054707
0x1800546fe  call    cs:__imp_GetCurrentThreadId
0x180054704  mov     [rbx+28h], eax
0x180054707  mov     byte ptr [rsp+540h+var_4E8], 1
0x18005470c  mov     [rsp+540h+var_4E0], rdi
0x180054711  cmp     byte ptr [rdi+48h], 0
0x180054715  jz      loc_1800547B9
0x18005471b  cmp     [rdi], r15
0x18005471e  jnz     loc_1800547A5
0x180054724  mov     dword ptr [rsp+540h+var_500], 0
0x18005472c  mov     rcx, [rdi+40h]
0x180054730  mov     rax, [rcx]
0x180054733  lea     r9, [rsp+540h+var_500]
0x180054738  mov     r8d, [rsi]
0x18005473b  mov     rdx, [rsi+8]
0x18005473f  mov     rax, [rax+18h]
0x180054743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054748  mov     esi, eax
0x18005474a  test    eax, eax
0x18005474c  js      loc_1800547FF
0x180054752  mov     esi, dword ptr [rsp+540h+var_500]
0x180054756  lea     rax, [rsi+r15]
0x18005475a  mov     [rdi], rax
0x18005475d  test    rbx, rbx
0x180054760  jz      short loc_180054778
0x180054762  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180054766  jnz     short loc_18005476F
0x180054768  mov     dword ptr [rbx+28h], 0
0x18005476f  mov     rcx, rbx; lpCriticalSection
0x180054772  call    cs:__imp_LeaveCriticalSection
0x180054778  add     [r14], rsi
0x18005477b  mov     eax, dword ptr [rsp+540h+var_500]
0x18005477f  mov     rcx, [rbp+440h+var_30]
0x180054786  xor     rcx, rsp; StackCookie
0x180054789  call    __security_check_cookie
0x18005478e  mov     rbx, [rsp+540h+arg_10]
0x180054796  add     rsp, 520h
0x18005479d  pop     r15
0x18005479f  pop     r14
0x1800547a1  pop     rdi
0x1800547a2  pop     rsi
0x1800547a3  pop     rbp
0x1800547a4  retn
0x1800547a5  lea     rcx, [rdi+40h]
0x1800547a9  xor     r8d, r8d
0x1800547ac  mov     rdx, r15
0x1800547af  call    ?Seek@Stream@win_dox@@QEAA_K_JW4Enum@SeekOrigin@2@@Z; win_dox::Stream::Seek(__int64,win_dox::SeekOrigin::Enum)
0x1800547b4  jmp     loc_180054724
0x1800547b9  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x1800547c0  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800547c5  mov     [rsp+540h+var_518], 8000FFFFh; unsigned int
0x1800547cd  mov     [rsp+540h+var_520], 7Fh; unsigned int
0x1800547d5  lea     r9, word_18013A0B6
0x1800547dc  lea     r8, aNoFilename; "(no filename)"
0x1800547e3  lea     rcx, [rsp+540h+pExceptionObject]; this
0x1800547e8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800547ed  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800547f4  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x1800547f9  call    _CxxThrowException_0
0x1800547ff  xor     edx, edx; Val
0x180054801  mov     r8d, 400h; Size
0x180054807  lea     rcx, [rbp+440h+var_430]; void *
0x18005480b  call    memset_0
0x180054810  mov     r9d, esi
0x180054813  lea     r8, aCallToReadFail; "Call to Read failed with HResult 0x%X."
0x18005481a  mov     edx, 200h; unsigned __int64
0x18005481f  lea     rcx, [rbp+440h+var_430]; wchar_t *
0x180054823  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180054828  lea     rax, [rbp+440h+var_430]
0x18005482c  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180054831  mov     [rsp+540h+var_518], esi; unsigned int
0x180054835  mov     [rsp+540h+var_520], 60h ; '`'; unsigned int
0x18005483d  lea     r9, word_18013A0B6
0x180054844  lea     r8, aNoFilename; "(no filename)"
0x18005484b  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180054850  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180054855  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18005485c  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180054861  call    _CxxThrowException_0
```
