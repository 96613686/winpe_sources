# LogError(ushort const *,...)

- ea: `0x14000740c`
- end: `0x1400074cb`
- name: `?LogError@@YAXPEBGZZ`
- size: `191`
- prototype: `void(LPCVOID lpSource, ...)`
- caller_count: `70`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140004128`
- `0x140006dc8`
- `0x1400071a0`
- `0x140009c7c`
- `0x14000a034`
- `0x14000a14c`
- `0x14000a2b0`
- `0x14000a39c`
- `0x14000a5e0`
- `0x14000cb14`
- `0x14000cd78`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000dab4`
- `0x14000e09c`
- `0x14000e9bc`
- `0x14000eae8`
- `0x14000ec54`
- `0x14001050c`
- `0x140010a2c`
- `0x140013c90`
- `0x140013e20`
- `0x140013f34`
- `0x140014038`
- `0x140014174`
- `0x140014360`
- `0x140014488`
- `0x140014664`
- `0x1400147ec`
- `0x1400149f8`
- `0x140014be4`
- `0x140014e1c`
- `0x140014f2c`
- `0x140015108`
- `0x140015464`
- `0x140015614`
- `0x1400156e0`
- `0x14001584c`
- `0x140015b7c`
- `0x140015ff8`
- `0x1400161f4`
- `0x1400162cc`
- `0x1400165f8`
- `0x14001668c`
- `0x140016800`
- `0x140016a88`
- `0x140016da8`
- `0x140016ecc`
- `0x140016ff0`

## callees

- `0x140001010`
- `0x140007318`
- `0x14000740c`
- `0x1400078ac`
- `0x140007c64`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140007465`
- `KERNEL32!FormatMessageW` at `0x140007465`

## pseudocode

```c
void LogError(LPCVOID lpSource, ...)
{
  const struct _tlgProvider_t *v1; // rax
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  const OLECHAR *v5; // [rsp+40h] [rbp-20h] BYREF
  va_list v6; // [rsp+48h] [rbp-18h] BYREF
  const OLECHAR *v7; // [rsp+50h] [rbp-10h] BYREF
  __int64 v8; // [rsp+78h] [rbp+18h] BYREF
  va_list va; // [rsp+78h] [rbp+18h]
  __int64 v10; // [rsp+80h] [rbp+20h]
  __int64 v11; // [rsp+88h] [rbp+28h]
  va_list va1; // [rsp+90h] [rbp+30h] BYREF

  va_start(va1, lpSource);
  va_start(va, lpSource);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, _QWORD);
  v11 = va_arg(va1, _QWORD);
  va_copy(v6, va);
  v5 = 0;
  if ( FormatMessageW(0x500u, lpSource, 0, 0, (LPWSTR)&v5, 0x100u, &v6) )
  {
    v1 = EnterpriseDesktopAppManagementProvider::Provider();
    v4 = *(unsigned int *)v1;
    if ( (unsigned int)v4 > 2 )
    {
      v7 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v1,
        (__int64)&dword_1400268A4,
        v2,
        v3,
        &v7);
    }
    if ( (byte_14002B9C1 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, MDMAppInstallerDebugErrorMessage, v5);
  }
  v6 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v5);
}

```

## disassembly

```asm
0x14000740c  mov     r11, rsp
0x14000740f  mov     [r11+8], rcx
0x140007413  mov     [r11+10h], rdx
0x140007417  mov     [r11+18h], r8
0x14000741b  mov     [r11+20h], r9
0x14000741f  push    rbp
0x140007420  mov     rbp, rsp
0x140007423  sub     rsp, 60h
0x140007427  lea     rax, [rbp+arg_8]
0x14000742b  mov     [rbp+var_18], 0
0x140007433  mov     [rbp+var_18], rax
0x140007437  mov     rdx, rcx; lpSource
0x14000743a  lea     rax, [rbp+var_18]
0x14000743e  mov     [rbp+var_20], 0
0x140007446  mov     [r11-38h], rax
0x14000744a  xor     r9d, r9d; dwLanguageId
0x14000744d  lea     rax, [rbp+var_20]
0x140007451  mov     [rsp+60h+nSize], 100h; nSize
0x140007459  xor     r8d, r8d; dwMessageId
0x14000745c  mov     [r11-48h], rax
0x140007460  mov     ecx, 500h; dwFlags
0x140007465  call    cs:__imp_FormatMessageW
0x14000746b  test    eax, eax
0x14000746d  jz      short loc_1400074B4
0x14000746f  call    ?Provider@EnterpriseDesktopAppManagementProvider@@SAPEBU_tlgProvider_t@@XZ; EnterpriseDesktopAppManagementProvider::Provider(void)
0x140007474  mov     ecx, [rax]
0x140007476  cmp     ecx, 2
0x140007479  jbe     short loc_14000749B
0x14000747b  mov     rcx, [rbp+var_20]
0x14000747f  lea     rdx, dword_1400268A4
0x140007486  mov     [rbp+var_10], rcx
0x14000748a  lea     rcx, [rbp+var_10]
0x14000748e  mov     [rsp+60h+var_40], rcx
0x140007493  mov     rcx, rax
0x140007496  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000749b  test    cs:byte_14002B9C1, 1
0x1400074a2  jz      short loc_1400074B4
0x1400074a4  mov     r8, [rbp+var_20]
0x1400074a8  lea     rdx, MDMAppInstallerDebugErrorMessage
0x1400074af  call    McTemplateU0z_EventWriteTransfer
0x1400074b4  lea     rcx, [rbp+var_20]
0x1400074b8  mov     [rbp+var_18], 0
0x1400074c0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400074c5  add     rsp, 60h
0x1400074c9  pop     rbp
0x1400074ca  retn
```
