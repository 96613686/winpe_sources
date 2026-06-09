# AggregatorsCommon::Utilities::ValidateArray(winrt::array_view<winrt::hstring const>,uint,uint)

- ea: `0x1800218dc`
- end: `0x180021aa2`
- name: `?ValidateArray@Utilities@AggregatorsCommon@@YAXU?$array_view@$$CBUhstring@winrt@@@winrt@@II@Z`
- size: `454`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800142e8`
- `0x180014dac`

## callees

- `0x180002250`
- `0x180002d60`
- `0x180002e00`
- `0x180003516`
- `0x180007a54`
- `0x180007d44`
- `0x180007e84`
- `0x180017954`
- `0x180020548`
- `0x180020a24`
- `0x180020a78`
- `0x1800218dc`
- `0x180021aa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800219d5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800219d5`

## string_xrefs

- `0x180021a14`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\utilities.cpp`
- `0x180021a5d`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AggregatorsCommon::Utilities::ValidateArray(__int64 a1)
{
  __int64 v1; // rax
  struct winrt::impl::shared_hstring_header **v2; // rsi
  __int64 v3; // r15
  struct winrt::impl::shared_hstring_header *v4; // rdi
  unsigned int v5; // r14d
  const void *v6; // rbx
  void *v7; // rbx
  int v8; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-69h] BYREF
  int v11; // [rsp+28h] [rbp-61h]
  const wchar_t *v12; // [rsp+30h] [rbp-59h] BYREF
  const char *v13; // [rsp+38h] [rbp-51h]
  __int64 v14; // [rsp+40h] [rbp-49h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE Src[32]; // [rsp+88h] [rbp-1h] BYREF

  v11 = 10;
  v1 = *(unsigned int *)(a1 + 8);
  if ( !(_DWORD)v1 )
  {
    LODWORD(v12) = 41;
    v13 = "onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\utilities.cpp";
    v14 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)Src, L"Empty array passed");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)Src,
      (const struct winrt::impl::slim_source_location *)&v12);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( (unsigned int)v1 > 0xA )
  {
    LODWORD(lpMem) = winrt::array_view<winrt::hstring const>::size();
    v12 = L"Array size {} is more than the maximum {}.";
    std::format<unsigned int,unsigned int &>(Src);
    LODWORD(v12) = 46;
    v13 = "onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\utilities.cpp";
    v14 = 0;
    winrt::param::hstring::hstring(v16, Src);
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v16,
      (const struct winrt::impl::slim_source_location *)&v12);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v2 = *(struct winrt::impl::shared_hstring_header ***)a1;
  v3 = *(_QWORD *)a1 + 8 * v1;
  while ( v2 != (struct winrt::impl::shared_hstring_header **)v3 )
  {
    v4 = *v2;
    if ( !*v2 )
      goto LABEL_5;
    if ( (*(_BYTE *)v4 & 1) != 0 )
    {
      v5 = *((_DWORD *)v4 + 1);
      if ( !v5 )
      {
LABEL_5:
        v4 = 0;
        goto LABEL_10;
      }
      v6 = (const void *)*((_QWORD *)v4 + 2);
      v4 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v5);
      memcpy_s((char *)v4 + 28, 2LL * v5, v6, 2LL * v5);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)v4 + 6);
    }
LABEL_10:
    lpMem = v4;
    AggregatorsCommon::Utilities::ValidateText(
      (AggregatorsCommon::Utilities *)&lpMem,
      (const struct winrt::hstring *)0x100);
    v7 = lpMem;
    if ( lpMem )
    {
      v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v8 )
      {
        if ( v8 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v7);
      }
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x1800218dc  push    rbp
0x1800218de  push    rbx
0x1800218df  push    rsi
0x1800218e0  push    rdi
0x1800218e1  push    r14
0x1800218e3  push    r15
0x1800218e5  lea     rbp, [rsp-2Fh]
0x1800218ea  sub     rsp, 0B8h
0x1800218f1  mov     rax, cs:__security_cookie
0x1800218f8  xor     rax, rsp
0x1800218fb  mov     [rbp+57h+var_38], rax
0x1800218ff  mov     [rbp+57h+var_B8], 0Ah
0x180021906  mov     eax, [rcx+8]
0x180021909  test    eax, eax
0x18002190b  jz      loc_180021A56
0x180021911  cmp     eax, 0Ah
0x180021914  ja      loc_1800219DC
0x18002191a  mov     rsi, [rcx]
0x18002191d  lea     r15, [rsi+rax*8]
0x180021921  jmp     loc_1800219B0
0x180021926  mov     rdi, [rsi]
0x180021929  test    rdi, rdi
0x18002192c  jnz     short loc_180021932
0x18002192e  xor     edi, edi
0x180021930  jmp     short loc_18002196A
0x180021932  test    byte ptr [rdi], 1
0x180021935  jnz     short loc_18002193D
0x180021937  lock inc dword ptr [rdi+18h]
0x18002193b  jmp     short loc_18002196A
0x18002193d  mov     r14d, [rdi+4]
0x180021941  test    r14d, r14d
0x180021944  jz      short loc_18002192E
0x180021946  mov     rbx, [rdi+10h]
0x18002194a  mov     ecx, r14d; this
0x18002194d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180021952  mov     rdi, rax
0x180021955  mov     edx, r14d
0x180021958  add     rdx, rdx; DestinationSize
0x18002195b  lea     rcx, [rax+1Ch]; Destination
0x18002195f  mov     r9, rdx; SourceSize
0x180021962  mov     r8, rbx; Source
0x180021965  call    memcpy_s
0x18002196a  mov     [rbp+57h+lpMem], rdi
0x18002196e  mov     edx, 100h; struct winrt::hstring *
0x180021973  lea     rcx, [rbp+57h+lpMem]; this
0x180021977  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x18002197c  nop
0x18002197d  mov     rbx, [rbp+57h+lpMem]
0x180021981  test    rbx, rbx
0x180021984  jz      short loc_1800219AC
0x180021986  or      eax, 0FFFFFFFFh
0x180021989  lock xadd [rbx+18h], eax
0x18002198e  sub     eax, 1
0x180021991  jnz     short loc_1800219A8
0x180021993  nop
0x180021994  call    WINRT_IMPL_GetProcessHeap
0x180021999  mov     rcx, rax; hHeap
0x18002199c  mov     r8, rbx; lpMem
0x18002199f  xor     edx, edx; dwFlags
0x1800219a1  call    WINRT_IMPL_HeapFree
0x1800219a6  jmp     short loc_1800219AC
0x1800219a8  test    eax, eax
0x1800219aa  js      short loc_1800219D5
0x1800219ac  add     rsi, 8
0x1800219b0  cmp     rsi, r15
0x1800219b3  jnz     loc_180021926
0x1800219b9  mov     rcx, [rbp+57h+var_38]
0x1800219bd  xor     rcx, rsp; StackCookie
0x1800219c0  call    __security_check_cookie
0x1800219c5  add     rsp, 0B8h
0x1800219cc  pop     r15
0x1800219ce  pop     r14
0x1800219d0  pop     rdi
0x1800219d1  pop     rsi
0x1800219d2  pop     rbx
0x1800219d3  pop     rbp
0x1800219d4  retn
0x1800219d5  call    cs:__imp_abort
0x1800219dc  call    ?size@?$array_view@$$CBUhstring@winrt@@@winrt@@QEBAIXZ; winrt::array_view<winrt::hstring const>::size(void)
0x1800219e1  mov     dword ptr [rbp+57h+lpMem], eax
0x1800219e4  lea     rax, aArraySizeIsMor; "Array size {} is more than the maximum "...
0x1800219eb  mov     [rbp+57h+var_B0], rax
0x1800219ef  mov     [rbp+57h+var_A8], 2Ah ; '*'
0x1800219f7  lea     r9, [rbp+57h+var_B8]
0x1800219fb  lea     r8, [rbp+57h+lpMem]
0x1800219ff  lea     rdx, [rbp+57h+var_B0]
0x180021a03  lea     rcx, [rbp+57h+Src]; Src
0x180021a07  call    ??$format@IAEAI@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WIAEAI@0@$$QEAIAEAI@Z; std::format<uint,uint &>(std::basic_format_string<wchar_t,uint,uint &>,uint &&,uint &)
0x180021a0c  nop
0x180021a0d  mov     dword ptr [rbp+57h+var_B0], 2Eh ; '.'
0x180021a14  lea     rax, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180021a1b  mov     [rbp+57h+var_A8], rax
0x180021a1f  mov     [rbp+57h+var_A0], 0
0x180021a27  lea     rdx, [rbp+57h+Src]
0x180021a2b  lea     rcx, [rbp+57h+var_78]
0x180021a2f  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180021a34  lea     r8, [rbp+57h+var_B0]; struct winrt::impl::slim_source_location *
0x180021a38  lea     rdx, [rbp+57h+var_78]; struct winrt::param::hstring *
0x180021a3c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021a40  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180021a45  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180021a4c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021a50  call    _CxxThrowException_0
0x180021a56  mov     dword ptr [rbp+57h+var_B0], 29h ; ')'
0x180021a5d  lea     rax, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180021a64  mov     [rbp+57h+var_A8], rax
0x180021a68  mov     [rbp+57h+var_A0], 0
0x180021a70  lea     rdx, aEmptyArrayPass; "Empty array passed"
0x180021a77  lea     rcx, [rbp+57h+Src]; this
0x180021a7b  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180021a80  lea     r8, [rbp+57h+var_B0]; struct winrt::impl::slim_source_location *
0x180021a84  lea     rdx, [rbp+57h+Src]; struct winrt::param::hstring *
0x180021a88  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180021a8c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180021a91  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180021a98  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180021a9c  call    _CxxThrowException_0
```
