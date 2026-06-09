# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x140008428`
- end: `0x14000853f`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `279`
- prototype: `ATL::CDacl::CAccessAce *__fastcall(ATL::CDacl::CAccessAce *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000a0f8`

## callees

- `0x140007d8c`
- `0x140008428`
- `0x14000a220`
- `0x14000a2e8`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400084cd`
- `ADVAPI32!GetLengthSid` at `0x1400084cd`
- `ADVAPI32!IsValidSid` at `0x1400084c0`
- `ADVAPI32!IsValidSid` at `0x1400084c0`
- `ADVAPI32!CopySid` at `0x1400084dc`
- `ADVAPI32!CopySid` at `0x1400084dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::CAccessAce(
        ATL::CDacl::CAccessAce *this,
        const struct ATL::CSid *a2)
{
  char *v4; // rsi
  char *v5; // rdi
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v4 = (char *)this + 8;
  *((_QWORD *)this + 1) = &ATL::CSid::`vftable';
  *((_BYTE *)this + 84) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 20);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    (char *)this + 96,
    (char *)a2 + 88);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    v4 + 96,
    (char *)a2 + 96);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    v4 + 104,
    (char *)a2 + 104);
  *((_QWORD *)v4 + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    v5 = (char *)a2 + 8;
    if ( !IsValidSid(v5) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid(v5);
    if ( !CopySid(LengthSid, v4 + 8, v5) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  *((_DWORD *)this + 32) = 1;
  *((_BYTE *)this + 132) = 0;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)this = &ATL::CDacl::CAccessAce::`vftable';
  *((_BYTE *)this + 144) = 1;
  return this;
}

```

## disassembly

```asm
0x140008428  mov     r11, rsp
0x14000842b  mov     [r11+10h], rbx
0x14000842f  mov     [r11+18h], rsi
0x140008433  mov     [r11+8], rcx
0x140008437  push    rdi
0x140008438  sub     rsp, 20h
0x14000843c  mov     rdi, rdx
0x14000843f  mov     rbx, rcx
0x140008442  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x140008449  mov     [rcx], rax
0x14000844c  lea     rsi, [rcx+8]
0x140008450  mov     [r11+8], rsi
0x140008454  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x14000845b  mov     [rsi], rax
0x14000845e  mov     al, [rdx+4Ch]
0x140008461  mov     [rsi+4Ch], al
0x140008464  mov     eax, [rdx+50h]
0x140008467  mov     [rsi+50h], eax
0x14000846a  add     rdx, 58h ; 'X'
0x14000846e  lea     rcx, [rsi+58h]
0x140008472  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x140008477  nop
0x140008478  lea     rdx, [rdi+60h]
0x14000847c  lea     rcx, [rsi+60h]
0x140008480  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x140008485  nop
0x140008486  lea     rdx, [rdi+68h]
0x14000848a  lea     rcx, [rsi+68h]
0x14000848e  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x140008493  nop
0x140008494  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000849b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400084a2  mov     rax, [rax+18h]
0x1400084a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084ab  add     rax, 18h
0x1400084af  mov     [rsi+70h], rax
0x1400084b3  cmp     byte ptr [rdi+4Ch], 0
0x1400084b7  jz      short loc_1400084E6
0x1400084b9  add     rdi, 8
0x1400084bd  mov     rcx, rdi; pSid
0x1400084c0  call    cs:__imp_IsValidSid
0x1400084c6  test    eax, eax
0x1400084c8  jz      short loc_140008534
0x1400084ca  mov     rcx, rdi; pSid
0x1400084cd  call    cs:__imp_GetLengthSid
0x1400084d3  lea     rdx, [rsi+8]; pDestinationSid
0x1400084d7  mov     r8, rdi; pSourceSid
0x1400084da  mov     ecx, eax; nDestinationSidLength
0x1400084dc  call    cs:__imp_CopySid
0x1400084e2  test    eax, eax
0x1400084e4  jz      short loc_140008526
0x1400084e6  mov     dword ptr [rbx+80h], 1
0x1400084f0  mov     byte ptr [rbx+84h], 0
0x1400084f7  mov     qword ptr [rbx+88h], 0
0x140008502  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x140008509  mov     [rbx], rax
0x14000850c  mov     byte ptr [rbx+90h], 1
0x140008513  mov     rax, rbx
0x140008516  mov     rbx, [rsp+28h+arg_8]
0x14000851b  mov     rsi, [rsp+28h+arg_10]
0x140008520  add     rsp, 20h
0x140008524  pop     rdi
0x140008525  retn
0x140008526  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000852b  nop
0x14000852c  mov     ecx, eax; int
0x14000852e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140008534  mov     ecx, 80070057h; int
0x140008539  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
