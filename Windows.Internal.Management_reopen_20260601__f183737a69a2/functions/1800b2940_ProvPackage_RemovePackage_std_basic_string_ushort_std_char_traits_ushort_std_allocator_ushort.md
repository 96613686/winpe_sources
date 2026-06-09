# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800b2940`
- end: `0x1800b2add`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1800011d4`
- `0x180001350`
- `0x180001424`
- `0x180003884`
- `0x180004eb0`
- `0x18000868c`
- `0x1800131a8`
- `0x180017094`
- `0x180036d2c`
- `0x18003e5d4`
- `0x1800b1e94`
- `0x1800b2940`
- `0x1800b2e88`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a5b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b29ed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b29ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvPackage::RemovePackage(_QWORD *a1, __int64 a2, int a3, int a4)
{
  const WCHAR *v6; // rbx
  const WCHAR *v7; // rax
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  const char *v10; // r9
  _QWORD *v11; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-48h]
  int v19[2]; // [rsp+30h] [rbp-38h] BYREF
  char v20[8]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v21; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v21 = a2;
  v6 = (const WCHAR *)(a1 + 1);
  if ( (unsigned int)dword_1800FE488 > 5 )
  {
    if ( a1[4] <= 7u )
      v7 = (const WCHAR *)(a1 + 1);
    else
      v7 = *(const WCHAR **)v6;
    *(_QWORD *)v19 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)byte_1800EE321,
      a3,
      a4,
      (__int64)v19);
  }
  if ( !a1[13] && !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*a1 + 72LL))(a1) )
  {
    v17 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v17,
      v18);
  }
  std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::reset(a1 + 13, 0);
  v8 = a1[14];
  a1[14] = 0;
  if ( v8 )
    std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>::operator()();
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v9 = v6;
  else
    v9 = *(const WCHAR **)v6;
  if ( !DeleteFileW(v9) )
  {
    if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0) )
    {
      v19[0] = GetLastError();
      v13 = std::wstring::c_str(v6);
      v14 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v20, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800FE488,
        (unsigned int)&unk_1800EE348,
        v15,
        v16,
        v14,
        (__int64)v19);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      v10);
  }
  v11 = a1 + 9;
  a1[11] = 0;
  if ( a1[12] > 7u )
    v11 = (_QWORD *)*v11;
  *(_WORD *)v11 = 0;
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x1800b2940  mov     [rsp+arg_10], rbx
0x1800b2945  push    rbp
0x1800b2946  push    rsi
0x1800b2947  push    rdi
0x1800b2948  sub     rsp, 50h
0x1800b294c  mov     rax, cs:__security_cookie
0x1800b2953  xor     rax, rsp
0x1800b2956  mov     [rsp+68h+var_20], rax
0x1800b295b  mov     rbp, rdx
0x1800b295e  mov     rdi, rcx
0x1800b2961  mov     [rsp+68h+var_28], rdx
0x1800b2966  mov     eax, cs:dword_1800FE488
0x1800b296c  lea     rbx, [rcx+8]
0x1800b2970  cmp     eax, 5
0x1800b2973  jbe     short loc_1800B299F
0x1800b2975  cmp     qword ptr [rbx+18h], 7
0x1800b297a  jbe     short loc_1800B2981
0x1800b297c  mov     rax, [rbx]
0x1800b297f  jmp     short loc_1800B2984
0x1800b2981  mov     rax, rbx
0x1800b2984  mov     qword ptr [rsp+68h+var_38], rax
0x1800b2989  lea     rax, [rsp+68h+var_38]
0x1800b298e  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800b2993  lea     rdx, byte_1800EE321
0x1800b299a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b299f  cmp     qword ptr [rdi+68h], 0
0x1800b29a4  jnz     short loc_1800B29BD
0x1800b29a6  mov     rax, [rdi]
0x1800b29a9  mov     rcx, rdi
0x1800b29ac  mov     rax, [rax+48h]
0x1800b29b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b29b5  test    al, al
0x1800b29b7  jz      loc_1800B2AB9
0x1800b29bd  xor     edx, edx
0x1800b29bf  lea     rcx, [rdi+68h]
0x1800b29c3  call    ?reset@?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@QEAAXPEAUIProvisioningPackage@@@Z; std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::reset(IProvisioningPackage *)
0x1800b29c8  mov     rdx, [rdi+70h]
0x1800b29cc  mov     qword ptr [rdi+70h], 0
0x1800b29d4  test    rdx, rdx
0x1800b29d7  jz      short loc_1800B29DE
0x1800b29d9  call    ??R?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@QEBAXPEAVIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@Z; std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>::operator()(Windows::Internal::Management::Provisioning::IProvisioningFileManager *)
0x1800b29de  cmp     qword ptr [rbx+18h], 7
0x1800b29e3  jbe     short loc_1800B29EA
0x1800b29e5  mov     rcx, [rbx]
0x1800b29e8  jmp     short loc_1800B29ED
0x1800b29ea  mov     rcx, rbx; lpFileName
0x1800b29ed  call    cs:__imp_DeleteFileW
0x1800b29f4  nop     dword ptr [rax+rax+00h]
0x1800b29f9  test    eax, eax
0x1800b29fb  jz      short loc_1800B2A3E
0x1800b29fd  lea     rcx, [rdi+48h]
0x1800b2a01  mov     qword ptr [rcx+10h], 0
0x1800b2a09  cmp     qword ptr [rcx+18h], 7
0x1800b2a0e  jbe     short loc_1800B2A13
0x1800b2a10  mov     rcx, [rcx]
0x1800b2a13  xor     eax, eax
0x1800b2a15  mov     [rcx], ax
0x1800b2a18  mov     rcx, rbp
0x1800b2a1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b2a20  mov     rcx, [rsp+68h+var_20]
0x1800b2a25  xor     rcx, rsp; StackCookie
0x1800b2a28  call    __security_check_cookie
0x1800b2a2d  mov     rbx, [rsp+68h+arg_10]
0x1800b2a35  add     rsp, 50h
0x1800b2a39  pop     rdi
0x1800b2a3a  pop     rsi
0x1800b2a3b  pop     rbp
0x1800b2a3c  retn
0x1800b2a3e  mov     eax, cs:dword_1800FE488
0x1800b2a44  cmp     eax, 2
0x1800b2a47  jbe     short loc_1800B2AA2
0x1800b2a49  xor     edx, edx
0x1800b2a4b  lea     rcx, dword_1800FE488
0x1800b2a52  call    _tlgKeywordOn
0x1800b2a57  test    al, al
0x1800b2a59  jz      short loc_1800B2AA2
0x1800b2a5b  call    cs:__imp_GetLastError
0x1800b2a62  nop     dword ptr [rax+rax+00h]
0x1800b2a67  mov     [rsp+68h+var_38], eax
0x1800b2a6b  mov     rcx, rbx
0x1800b2a6e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800b2a73  mov     rdx, rax
0x1800b2a76  lea     rcx, [rsp+68h+var_30]
0x1800b2a7b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b2a80  lea     rdx, [rsp+68h+var_38]
0x1800b2a85  mov     [rsp+68h+var_40], rdx
0x1800b2a8a  mov     qword ptr [rsp+68h+var_48], rax
0x1800b2a8f  lea     rdx, unk_1800EE348
0x1800b2a96  lea     rcx, dword_1800FE488
0x1800b2a9d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b2aa2  mov     rcx, [rsp+68h]; this
0x1800b2aa7  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800b2aae  mov     edx, 0E5h; void *
0x1800b2ab3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b2ab9  mov     ecx, 8000FFFFh
0x1800b2abe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800b2ac3  mov     r9d, eax; char *
0x1800b2ac6  mov     rcx, [rsp+68h]; this
0x1800b2acb  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800b2ad2  mov     edx, 0D6h; void *
0x1800b2ad7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
