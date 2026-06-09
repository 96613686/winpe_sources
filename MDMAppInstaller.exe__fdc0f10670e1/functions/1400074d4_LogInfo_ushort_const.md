# LogInfo(ushort const *,...)

- ea: `0x1400074d4`
- end: `0x140007593`
- name: `?LogInfo@@YAXPEBGZZ`
- size: `191`
- prototype: `void(LPCVOID lpSource, ...)`
- caller_count: `51`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006dc8`
- `0x140009c7c`
- `0x140009f78`
- `0x14000a034`
- `0x14000a14c`
- `0x14000a230`
- `0x14000a39c`
- `0x14000a5e0`
- `0x14000cd78`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000dab4`
- `0x14000e09c`
- `0x14000e194`
- `0x14000e6cc`
- `0x14000e9bc`
- `0x14000eae8`
- `0x14000ec54`
- `0x14000eea4`
- `0x14000faf4`
- `0x140010a2c`
- `0x140013c90`
- `0x140013e20`
- `0x140014174`
- `0x140014664`
- `0x140015108`
- `0x1400156e0`
- `0x14001584c`
- `0x140015ff8`
- `0x1400161f4`
- `0x1400162cc`
- `0x1400165f8`
- `0x140016ff0`
- `0x140017610`
- `0x1400177bc`
- `0x140017b90`
- `0x140017eb0`
- `0x140017fbc`
- `0x1400182dc`
- `0x140018520`
- `0x140018970`
- `0x140018d08`
- `0x140019054`
- `0x14001984c`
- `0x140019ba8`
- `0x140019e94`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a418`

## callees

- `0x140001010`
- `0x140007318`
- `0x1400074d4`
- `0x1400078ac`
- `0x140007c64`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000752d`
- `KERNEL32!FormatMessageW` at `0x14000752d`

## pseudocode

```c
void LogInfo(LPCVOID lpSource, ...)
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
    if ( (unsigned int)v4 > 4 )
    {
      v7 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v1,
        (__int64)word_1400268E2,
        v2,
        v3,
        &v7);
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, MDMAppInstallerDebugInfoMessage, v5);
  }
  v6 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v5);
}

```

## disassembly

```asm
0x1400074d4  mov     r11, rsp
0x1400074d7  mov     [r11+8], rcx
0x1400074db  mov     [r11+10h], rdx
0x1400074df  mov     [r11+18h], r8
0x1400074e3  mov     [r11+20h], r9
0x1400074e7  push    rbp
0x1400074e8  mov     rbp, rsp
0x1400074eb  sub     rsp, 60h
0x1400074ef  lea     rax, [rbp+arg_8]
0x1400074f3  mov     [rbp+var_18], 0
0x1400074fb  mov     [rbp+var_18], rax
0x1400074ff  mov     rdx, rcx; lpSource
0x140007502  lea     rax, [rbp+var_18]
0x140007506  mov     [rbp+var_20], 0
0x14000750e  mov     [r11-38h], rax
0x140007512  xor     r9d, r9d; dwLanguageId
0x140007515  lea     rax, [rbp+var_20]
0x140007519  mov     [rsp+60h+nSize], 100h; nSize
0x140007521  xor     r8d, r8d; dwMessageId
0x140007524  mov     [r11-48h], rax
0x140007528  mov     ecx, 500h; dwFlags
0x14000752d  call    cs:__imp_FormatMessageW
0x140007533  test    eax, eax
0x140007535  jz      short loc_14000757C
0x140007537  call    ?Provider@EnterpriseDesktopAppManagementProvider@@SAPEBU_tlgProvider_t@@XZ; EnterpriseDesktopAppManagementProvider::Provider(void)
0x14000753c  mov     ecx, [rax]
0x14000753e  cmp     ecx, 4
0x140007541  jbe     short loc_140007563
0x140007543  mov     rcx, [rbp+var_20]
0x140007547  lea     rdx, word_1400268E2
0x14000754e  mov     [rbp+var_10], rcx
0x140007552  lea     rcx, [rbp+var_10]
0x140007556  mov     [rsp+60h+var_40], rcx
0x14000755b  mov     rcx, rax
0x14000755e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140007563  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x14000756a  jz      short loc_14000757C
0x14000756c  mov     r8, [rbp+var_20]
0x140007570  lea     rdx, MDMAppInstallerDebugInfoMessage
0x140007577  call    McTemplateU0z_EventWriteTransfer
0x14000757c  lea     rcx, [rbp+var_20]
0x140007580  mov     [rbp+var_18], 0
0x140007588  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000758d  add     rsp, 60h
0x140007591  pop     rbp
0x140007592  retn
```
