# WindowsMidiServicesInternal::JsonSetGuidProperty(winrt::Windows::Data::Json::JsonObject const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &)

- ea: `0x14003b55c`
- end: `0x14003b77b`
- name: `?JsonSetGuidProperty@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003a960`

## callees

- `0x1400054c0`
- `0x14000617c`
- `0x1400061e8`
- `0x140007c20`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x1400145bc`
- `0x1400250ac`
- `0x14003a534`
- `0x14003b55c`
- `0x14003be6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b6c5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b6d5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b773`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b6c5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b6d5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003b773`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall WindowsMidiServicesInternal::JsonSetGuidProperty(__int64 **a1, _QWORD *a2, IID *a3)
{
  __int64 v7; // rax
  const char *v8; // rdx
  _WORD *v9; // rsi
  __int64 v10; // rbx
  struct winrt::impl::shared_hstring_header *v11; // rdi
  volatile signed __int32 *v12; // rsi
  __int64 v13; // r12
  const void *v14; // rbx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  __int64 *v17; // r8
  __int64 v18; // rcx
  int v19; // r15d
  HANDLE v20; // rax
  char result; // al
  __int64 v22; // [rsp+20h] [rbp-B8h] BYREF
  _DWORD *v23; // [rsp+28h] [rbp-B0h] BYREF
  _DWORD v24[4]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD *v25; // [rsp+40h] [rbp-98h]
  IID v26; // [rsp+50h] [rbp-88h] BYREF
  volatile signed __int32 *v27; // [rsp+60h] [rbp-78h] BYREF
  char *v28[4]; // [rsp+80h] [rbp-58h] BYREF

  v22 = 0;
  if ( winrt::Windows::Foundation::operator==((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))a1, &v22) )
    return 0;
  try
  {
    v26 = *a3;
    v7 = WindowsMidiServicesInternal::GuidToString((__int64)v28, &v26);
    v9 = (_WORD *)v7;
    if ( *(_QWORD *)(v7 + 24) > 7u )
      v9 = *(_WORD **)v7;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( (_DWORD)v10 )
    {
      v11 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v10, v8);
      memcpy_s((char *)v11 + 28, 2LL * (unsigned int)v10, v9, 2LL * (unsigned int)v10);
    }
    else
    {
      v11 = 0;
    }
    if ( v11 )
    {
      if ( (*(_BYTE *)v11 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v11 + 6);
        v12 = (volatile signed __int32 *)v11;
        goto LABEL_16;
      }
      v13 = *((unsigned int *)v11 + 1);
      if ( (_DWORD)v13 )
      {
        v14 = (const void *)*((_QWORD *)v11 + 2);
        v12 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v13, v8);
        memcpy_s((void *const)(v12 + 7), 2 * v13, v14, 2 * v13);
        goto LABEL_16;
      }
    }
    v12 = 0;
LABEL_16:
    *(_QWORD *)&v26.Data1 = v12;
    if ( v11 )
    {
      v15 = _InterlockedDecrement((volatile signed __int32 *)v11 + 6);
      if ( v15 )
      {
        if ( v15 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
      }
    }
    std::wstring::~wstring(v28);
    v27 = v12;
    v17 = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateStringValue(
                       (const struct winrt::param::hstring *)&v22,
                       &v27);
    v18 = a2[2];
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    if ( (_DWORD)v18 )
    {
      if ( *((_WORD *)a2 + (unsigned int)v18) )
        abort();
      v24[0] = 1;
      v24[1] = v18;
      v25 = a2;
      v23 = v24;
    }
    else
    {
      v23 = 0;
    }
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      a1,
      (__int64 *)&v23,
      v17);
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
    if ( v12 )
    {
      v19 = _InterlockedDecrement(v12 + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          abort();
      }
      else
      {
        v20 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v12);
      }
    }
    result = 1;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14003b55c  mov     [rsp+arg_8], rbx
0x14003b561  mov     [rsp+arg_18], rsi
0x14003b566  push    rdi
0x14003b567  push    r12
0x14003b569  push    r13
0x14003b56b  push    r14
0x14003b56d  push    r15
0x14003b56f  sub     rsp, 0B0h
0x14003b576  mov     rax, cs:__security_cookie
0x14003b57d  xor     rax, rsp
0x14003b580  mov     [rsp+0D8h+var_38], rax
0x14003b588  mov     rbx, r8
0x14003b58b  mov     r14, rdx
0x14003b58e  mov     r13, rcx
0x14003b591  xor     r12d, r12d
0x14003b594  mov     [rsp+0D8h+var_B8], r12
0x14003b599  lea     rdx, [rsp+0D8h+var_B8]
0x14003b59e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x14003b5a3  test    al, al
0x14003b5a5  jnz     loc_14003B73F
0x14003b5ab  movups  xmm0, xmmword ptr [rbx]
0x14003b5ae  movdqu  [rsp+0D8h+var_88], xmm0
0x14003b5b4  lea     rdx, [rsp+0D8h+var_88]
0x14003b5b9  lea     rcx, [rsp+0D8h+var_58]
0x14003b5c1  call    ?GuidToString@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@Z; WindowsMidiServicesInternal::GuidToString(_GUID)
0x14003b5c6  mov     rsi, rax
0x14003b5c9  cmp     qword ptr [rax+18h], 7
0x14003b5ce  jbe     short loc_14003B5D3
0x14003b5d0  mov     rsi, [rax]
0x14003b5d3  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003b5d7  mov     rbx, r15
0x14003b5da  inc     rbx
0x14003b5dd  cmp     [rsi+rbx*2], r12w
0x14003b5e2  jnz     short loc_14003B5DA
0x14003b5e4  test    ebx, ebx
0x14003b5e6  jnz     short loc_14003B5ED
0x14003b5e8  mov     rdi, r12
0x14003b5eb  jmp     short loc_14003B60C
0x14003b5ed  mov     ecx, ebx; this
0x14003b5ef  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14003b5f4  mov     rdi, rax
0x14003b5f7  mov     edx, ebx
0x14003b5f9  add     rdx, rdx; DestinationSize
0x14003b5fc  lea     rcx, [rax+1Ch]; Destination
0x14003b600  mov     r9, rdx; SourceSize
0x14003b603  mov     r8, rsi; Source
0x14003b606  call    memcpy_s
0x14003b60b  nop
0x14003b60c  test    rdi, rdi
0x14003b60f  jnz     short loc_14003B616
0x14003b611  mov     rsi, r12
0x14003b614  jmp     short loc_14003B659
0x14003b616  test    byte ptr [rdi], 1
0x14003b619  jnz     short loc_14003B624
0x14003b61b  lock inc dword ptr [rdi+18h]
0x14003b61f  mov     rsi, rdi
0x14003b622  jmp     short loc_14003B659
0x14003b624  mov     r12d, [rdi+4]
0x14003b628  test    r12d, r12d
0x14003b62b  jnz     short loc_14003B632
0x14003b62d  xor     r12d, r12d
0x14003b630  jmp     short loc_14003B611
0x14003b632  mov     rbx, [rdi+10h]
0x14003b636  mov     ecx, r12d; this
0x14003b639  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x14003b63e  mov     rsi, rax
0x14003b641  mov     rdx, r12
0x14003b644  add     rdx, rdx; DestinationSize
0x14003b647  lea     rcx, [rax+1Ch]; Destination
0x14003b64b  mov     r9, rdx; SourceSize
0x14003b64e  mov     r8, rbx; Source
0x14003b651  call    memcpy_s
0x14003b656  xor     r12d, r12d
0x14003b659  mov     qword ptr [rsp+0D8h+var_88], rsi
0x14003b65e  test    rdi, rdi
0x14003b661  jz      short loc_14003B684
0x14003b663  mov     eax, r15d
0x14003b666  lock xadd [rdi+18h], eax
0x14003b66b  sub     eax, 1
0x14003b66e  jnz     short loc_14003B6C1
0x14003b670  nop
0x14003b671  call    WINRT_IMPL_GetProcessHeap
0x14003b676  mov     rcx, rax; hHeap
0x14003b679  mov     r8, rdi; lpMem
0x14003b67c  xor     edx, edx; dwFlags
0x14003b67e  call    WINRT_IMPL_HeapFree
0x14003b683  nop
0x14003b684  lea     rcx, [rsp+0D8h+var_58]; void *
0x14003b68c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003b691  mov     [rsp+0D8h+var_78], rsi
0x14003b696  lea     rdx, [rsp+0D8h+var_78]
0x14003b69b  lea     rcx, [rsp+0D8h+var_B8]; struct winrt::param::hstring *
0x14003b6a0  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003b6a5  mov     r8, rax
0x14003b6a8  mov     rcx, [r14+10h]
0x14003b6ac  cmp     qword ptr [r14+18h], 7
0x14003b6b1  jbe     short loc_14003B6B6
0x14003b6b3  mov     r14, [r14]
0x14003b6b6  test    ecx, ecx
0x14003b6b8  jnz     short loc_14003B6CC
0x14003b6ba  mov     [rsp+0D8h+var_B0], r12
0x14003b6bf  jmp     short loc_14003B6F7
0x14003b6c1  test    eax, eax
0x14003b6c3  jns     short loc_14003B684
0x14003b6c5  call    cs:__imp_abort
0x14003b6cc  mov     eax, ecx
0x14003b6ce  cmp     [r14+rax*2], r12w
0x14003b6d3  jz      short loc_14003B6DC
0x14003b6d5  call    cs:__imp_abort
0x14003b6dc  mov     [rsp+0D8h+var_A8], 1
0x14003b6e4  mov     [rsp+0D8h+var_A4], ecx
0x14003b6e8  mov     [rsp+0D8h+var_98], r14
0x14003b6ed  lea     rax, [rsp+0D8h+var_A8]
0x14003b6f2  mov     [rsp+0D8h+var_B0], rax
0x14003b6f7  lea     rdx, [rsp+0D8h+var_B0]
0x14003b6fc  mov     rcx, r13
0x14003b6ff  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003b704  nop
0x14003b705  cmp     [rsp+0D8h+var_B8], r12
0x14003b70a  jz      short loc_14003B717
0x14003b70c  lea     rcx, [rsp+0D8h+var_B8]
0x14003b711  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003b716  nop
0x14003b717  test    rsi, rsi
0x14003b71a  jz      short loc_14003B73B
0x14003b71c  lock xadd [rsi+18h], r15d
0x14003b722  sub     r15d, 1
0x14003b726  jnz     short loc_14003B76E
0x14003b728  nop
0x14003b729  call    WINRT_IMPL_GetProcessHeap
0x14003b72e  mov     rcx, rax; hHeap
0x14003b731  mov     r8, rsi; lpMem
0x14003b734  xor     edx, edx; dwFlags
0x14003b736  call    WINRT_IMPL_HeapFree
0x14003b73b  mov     al, 1
0x14003b73d  jmp     short loc_14003B741
0x14003b73f  xor     al, al
0x14003b741  mov     rcx, [rsp+0D8h+var_38]
0x14003b749  xor     rcx, rsp; StackCookie
0x14003b74c  call    __security_check_cookie
0x14003b751  lea     r11, [rsp+0D8h+var_28]
0x14003b759  mov     rbx, [r11+38h]
0x14003b75d  mov     rsi, [r11+48h]
0x14003b761  mov     rsp, r11
0x14003b764  pop     r15
0x14003b766  pop     r14
0x14003b768  pop     r13
0x14003b76a  pop     r12
0x14003b76c  pop     rdi
0x14003b76d  retn
0x14003b76e  test    r15d, r15d
0x14003b771  jns     short loc_14003B73B
0x14003b773  call    cs:__imp_abort
```
