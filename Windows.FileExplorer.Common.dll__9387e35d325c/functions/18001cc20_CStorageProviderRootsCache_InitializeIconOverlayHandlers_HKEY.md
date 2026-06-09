# CStorageProviderRootsCache::InitializeIconOverlayHandlers(HKEY__ *)

- ea: `0x18001cc20`
- end: `0x18001cd9c`
- name: `?InitializeIconOverlayHandlers@CStorageProviderRootsCache@@AEAAJPEAUHKEY__@@@Z`
- size: `380`
- prototype: `int(CStorageProviderRootsCache *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016fe8`

## callees

- `0x1800077c8`
- `0x180007900`
- `0x18001cc20`
- `0x18001d028`
- `0x18001d060`
- `0x180037780`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18001cd20`
- `SHCORE!__imp_GUIDFromStringW` at `0x18001cd20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ccb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ccb7`

## string_xrefs

- `0x18001cd69`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderRootsCache::InitializeIconOverlayHandlers(CStorageProviderRootsCache *this, HKEY a2)
{
  unsigned int i; // esi
  int v5; // eax
  unsigned int v6; // edi
  LSTATUS ValueW; // eax
  bool v8; // sf
  __int64 v10; // r9
  __int64 v11; // rdx
  int pdwType; // [rsp+20h] [rbp-59h]
  LPCWSTR lpValue; // [rsp+40h] [rbp-39h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-31h] BYREF
  __int128 v15; // [rsp+50h] [rbp-29h] BYREF
  _WORD pvData[40]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  for ( i = 0; ; ++i )
  {
    if ( i >= 0x32 )
      return 0;
    lpValue = 0;
    v5 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &lpValue,
           L"%s_%d",
           L"IconOverlayHandler",
           i);
    v6 = v5;
    if ( v5 < 0 )
      break;
    pcbData = 78;
    ValueW = RegGetValueW(a2, 0, lpValue, 2u, 0, pvData, &pcbData);
    v8 = ValueW < 0;
    if ( ValueW )
    {
      pvData[0] = 0;
      v8 = ValueW < 0;
      if ( ValueW > 0 )
        v8 = 1;
    }
    if ( v8 )
    {
      if ( lpValue )
        CoTaskMemFree((LPVOID)lpValue);
      return 0;
    }
    v15 = 0;
    if ( !(unsigned int)GUIDFromStringW(pvData, &v15) )
    {
      v6 = -2147023266;
      v10 = 2147944030LL;
      v11 = 2859;
      goto LABEL_16;
    }
    v5 = CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_Add<_GUID const &>(
           (char *)this + 624,
           &v15);
    v6 = v5;
    if ( v5 < 0 )
    {
      v11 = 2860;
      goto LABEL_19;
    }
    if ( lpValue )
      CoTaskMemFree((LPVOID)lpValue);
  }
  v11 = 2855;
LABEL_19:
  v10 = (unsigned int)v5;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)v10,
    pdwType);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpValue);
  return v6;
}

```

## disassembly

```asm
0x18001cc20  mov     [rsp-8+arg_10], rsi
0x18001cc25  mov     [rsp-8+arg_18], rdi
0x18001cc2a  push    rbp
0x18001cc2b  push    r14
0x18001cc2d  push    r15
0x18001cc2f  lea     rbp, [rsp-47h]
0x18001cc34  sub     rsp, 0C0h
0x18001cc3b  mov     rax, cs:__security_cookie
0x18001cc42  xor     rax, rsp
0x18001cc45  mov     [rbp+57h+var_20], rax
0x18001cc49  mov     r15, rdx
0x18001cc4c  mov     r14, rcx
0x18001cc4f  xor     esi, esi
0x18001cc51  cmp     esi, 32h ; '2'
0x18001cc54  jnb     loc_18001CCDE
0x18001cc5a  mov     [rbp+57h+lpValue], 0
0x18001cc62  mov     r9d, esi
0x18001cc65  lea     r8, aIconoverlayhan; "IconOverlayHandler"
0x18001cc6c  lea     rdx, aSD; "%s_%d"
0x18001cc73  lea     rcx, [rbp+57h+lpValue]
0x18001cc77  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001cc7c  mov     edi, eax
0x18001cc7e  test    eax, eax
0x18001cc80  js      loc_18001CD91
0x18001cc86  mov     [rbp+57h+var_88], 4Eh ; 'N'
0x18001cc8d  lea     rax, [rbp+57h+var_88]
0x18001cc91  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18001cc96  lea     rax, [rbp+57h+var_70]
0x18001cc9a  mov     [rsp+0D0h+pvData], rax; pvData
0x18001cc9f  mov     [rsp+0D0h+pdwType], 0; int
0x18001cca8  mov     r9d, 2; dwFlags
0x18001ccae  mov     r8, [rbp+57h+lpValue]; lpValue
0x18001ccb2  xor     edx, edx; lpSubKey
0x18001ccb4  mov     rcx, r15; hkey
0x18001ccb7  call    cs:__imp_RegGetValueW
0x18001ccbd  test    eax, eax
0x18001ccbf  jz      short loc_18001CCD5
0x18001ccc1  xor     ecx, ecx
0x18001ccc3  mov     [rbp+57h+var_70], cx
0x18001ccc7  test    eax, eax
0x18001ccc9  jle     short loc_18001CCD5
0x18001cccb  movzx   eax, ax
0x18001ccce  or      eax, 80070000h
0x18001ccd3  test    eax, eax
0x18001ccd5  jns     short loc_18001CD11
0x18001ccd7  cmp     [rbp+57h+lpValue], 0
0x18001ccdc  jnz     short loc_18001CD05
0x18001ccde  xor     eax, eax
0x18001cce0  mov     rcx, [rbp+57h+var_20]
0x18001cce4  xor     rcx, rsp; StackCookie
0x18001cce7  call    __security_check_cookie
0x18001ccec  lea     r11, [rsp+0D0h+var_10]
0x18001ccf4  mov     rsi, [r11+30h]
0x18001ccf8  mov     rdi, [r11+38h]
0x18001ccfc  mov     rsp, r11
0x18001ccff  pop     r15
0x18001cd01  pop     r14
0x18001cd03  pop     rbp
0x18001cd04  retn
0x18001cd05  mov     rcx, [rbp+57h+lpValue]; pv
0x18001cd09  call    cs:__imp_CoTaskMemFree
0x18001cd0f  jmp     short loc_18001CCDE
0x18001cd11  xorps   xmm0, xmm0
0x18001cd14  movups  [rbp+57h+var_80], xmm0
0x18001cd18  lea     rdx, [rbp+57h+var_80]
0x18001cd1c  lea     rcx, [rbp+57h+var_70]
0x18001cd20  call    cs:__imp_GUIDFromStringW
0x18001cd26  test    eax, eax
0x18001cd28  jz      short loc_18001CD5C
0x18001cd2a  lea     rcx, [r14+270h]
0x18001cd31  lea     rdx, [rbp+57h+var_80]
0x18001cd35  call    ??$_Add@AEBU_GUID@@@?$CTSimpleArray@U_GUID@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@U_GUID@@@@V?$CSimpleArrayStandardCompareHelper@U_GUID@@@@V?$CSimpleArrayStandardMergeHelper@U_GUID@@@@@@QEAAJAEBU_GUID@@PEA_K@Z; CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_Add<_GUID const &>(_GUID const &,unsigned __int64 *)
0x18001cd3a  mov     edi, eax
0x18001cd3c  test    eax, eax
0x18001cd3e  js      short loc_18001CD8A
0x18001cd40  inc     esi
0x18001cd42  cmp     [rbp+57h+lpValue], 0
0x18001cd47  jz      loc_18001CC51
0x18001cd4d  mov     rcx, [rbp+57h+lpValue]; pv
0x18001cd51  call    cs:__imp_CoTaskMemFree
0x18001cd57  jmp     loc_18001CC51
0x18001cd5c  mov     edi, 8007065Eh
0x18001cd61  mov     r9d, edi; char *
0x18001cd64  mov     edx, 0B2Bh; void *
0x18001cd69  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001cd70  mov     rcx, [rbp+5Fh]; this
0x18001cd74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd79  nop
0x18001cd7a  lea     rcx, [rbp+57h+lpValue]; void *
0x18001cd7e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001cd83  mov     eax, edi
0x18001cd85  jmp     loc_18001CCE0
0x18001cd8a  mov     edx, 0B2Ch
0x18001cd8f  jmp     short loc_18001CD96
0x18001cd91  mov     edx, 0B27h
0x18001cd96  mov     r9d, eax
0x18001cd99  jmp     short loc_18001CD69
```
