# ProvPackage::RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800af600`
- end: `0x1800af790`
- name: `?RemovePackage@ProvPackage@@UEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1800011d4`
- `0x18000133c`
- `0x180001408`
- `0x18000377c`
- `0x180004d50`
- `0x1800084e0`
- `0x180012ae8`
- `0x180016934`
- `0x180037a84`
- `0x18003ec00`
- `0x1800aeb84`
- `0x1800af600`
- `0x1800afb38`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af714`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800af6ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800af6ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  if ( (unsigned int)dword_1800FA480 > 5 )
  {
    if ( a1[4] <= 7u )
      v7 = (const WCHAR *)(a1 + 1);
    else
      v7 = *(const WCHAR **)v6;
    *(_QWORD *)v19 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)byte_1800EA541,
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
    if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0) )
    {
      v19[0] = GetLastError();
      v13 = std::wstring::c_str(v6);
      v14 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v20, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800FA480,
        (unsigned int)&unk_1800EA568,
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
0x1800af600  mov     [rsp+arg_10], rbx
0x1800af605  push    rbp
0x1800af606  push    rsi
0x1800af607  push    rdi
0x1800af608  sub     rsp, 50h
0x1800af60c  mov     rax, cs:__security_cookie
0x1800af613  xor     rax, rsp
0x1800af616  mov     [rsp+68h+var_20], rax
0x1800af61b  mov     rbp, rdx
0x1800af61e  mov     rdi, rcx
0x1800af621  mov     [rsp+68h+var_28], rdx
0x1800af626  mov     eax, cs:dword_1800FA480
0x1800af62c  lea     rbx, [rcx+8]
0x1800af630  cmp     eax, 5
0x1800af633  jbe     short loc_1800AF65F
0x1800af635  cmp     qword ptr [rbx+18h], 7
0x1800af63a  jbe     short loc_1800AF641
0x1800af63c  mov     rax, [rbx]
0x1800af63f  jmp     short loc_1800AF644
0x1800af641  mov     rax, rbx
0x1800af644  mov     qword ptr [rsp+68h+var_38], rax
0x1800af649  lea     rax, [rsp+68h+var_38]
0x1800af64e  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800af653  lea     rdx, byte_1800EA541
0x1800af65a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800af65f  cmp     qword ptr [rdi+68h], 0
0x1800af664  jnz     short loc_1800AF67D
0x1800af666  mov     rax, [rdi]
0x1800af669  mov     rcx, rdi
0x1800af66c  mov     rax, [rax+48h]
0x1800af670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af675  test    al, al
0x1800af677  jz      loc_1800AF76C
0x1800af67d  xor     edx, edx
0x1800af67f  lea     rcx, [rdi+68h]
0x1800af683  call    ?reset@?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@QEAAXPEAUIProvisioningPackage@@@Z; std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>>::reset(IProvisioningPackage *)
0x1800af688  mov     rdx, [rdi+70h]
0x1800af68c  mov     qword ptr [rdi+70h], 0
0x1800af694  test    rdx, rdx
0x1800af697  jz      short loc_1800AF69E
0x1800af699  call    ??R?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@QEBAXPEAVIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@Z; std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>::operator()(Windows::Internal::Management::Provisioning::IProvisioningFileManager *)
0x1800af69e  cmp     qword ptr [rbx+18h], 7
0x1800af6a3  jbe     short loc_1800AF6AA
0x1800af6a5  mov     rcx, [rbx]
0x1800af6a8  jmp     short loc_1800AF6AD
0x1800af6aa  mov     rcx, rbx; lpFileName
0x1800af6ad  call    cs:__imp_DeleteFileW
0x1800af6b3  test    eax, eax
0x1800af6b5  jz      short loc_1800AF6F7
0x1800af6b7  lea     rcx, [rdi+48h]
0x1800af6bb  mov     qword ptr [rcx+10h], 0
0x1800af6c3  cmp     qword ptr [rcx+18h], 7
0x1800af6c8  jbe     short loc_1800AF6CD
0x1800af6ca  mov     rcx, [rcx]
0x1800af6cd  xor     eax, eax
0x1800af6cf  mov     [rcx], ax
0x1800af6d2  mov     rcx, rbp
0x1800af6d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800af6da  mov     rcx, [rsp+68h+var_20]
0x1800af6df  xor     rcx, rsp; StackCookie
0x1800af6e2  call    __security_check_cookie
0x1800af6e7  mov     rbx, [rsp+68h+arg_10]
0x1800af6ef  add     rsp, 50h
0x1800af6f3  pop     rdi
0x1800af6f4  pop     rsi
0x1800af6f5  pop     rbp
0x1800af6f6  retn
0x1800af6f7  mov     eax, cs:dword_1800FA480
0x1800af6fd  cmp     eax, 2
0x1800af700  jbe     short loc_1800AF755
0x1800af702  xor     edx, edx
0x1800af704  lea     rcx, dword_1800FA480
0x1800af70b  call    _tlgKeywordOn
0x1800af710  test    al, al
0x1800af712  jz      short loc_1800AF755
0x1800af714  call    cs:__imp_GetLastError
0x1800af71a  mov     [rsp+68h+var_38], eax
0x1800af71e  mov     rcx, rbx
0x1800af721  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800af726  mov     rdx, rax
0x1800af729  lea     rcx, [rsp+68h+var_30]
0x1800af72e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800af733  lea     rdx, [rsp+68h+var_38]
0x1800af738  mov     [rsp+68h+var_40], rdx
0x1800af73d  mov     qword ptr [rsp+68h+var_48], rax
0x1800af742  lea     rdx, unk_1800EA568
0x1800af749  lea     rcx, dword_1800FA480
0x1800af750  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800af755  mov     rcx, [rsp+68h]; this
0x1800af75a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800af761  mov     edx, 0E5h; void *
0x1800af766  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800af76c  mov     ecx, 8000FFFFh
0x1800af771  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800af776  mov     r9d, eax; char *
0x1800af779  mov     rcx, [rsp+68h]; this
0x1800af77e  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800af785  mov     edx, 0D6h; void *
0x1800af78a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
