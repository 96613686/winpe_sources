# MFIsStreamAvailableToAppPackage

- ea: `0x18001ad90`
- end: `0x18001af2b`
- name: `MFIsStreamAvailableToAppPackage`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a100`

## callees

- `0x180005fa0`
- `0x1800199f4`
- `0x18001ad90`
- `0x18001b16c`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001aef2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001aef2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001af0b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001af0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001af20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001af20`

## pseudocode

```c
__int64 __fastcall MFIsStreamAvailableToAppPackage(__int64 a1, const wchar_t *a2, _DWORD *a3)
{
  unsigned int v6; // edi
  const char *v8; // rax
  wchar_t *v9; // rdx
  __int64 v10; // rdx
  int (__fastcall *v11)(__int64, __int64 *, wchar_t **, int *); // rbx
  int v12; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *Str; // [rsp+68h] [rbp+20h] BYREF

  Str = 0;
  v12 = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      v6 = 0;
      *a3 = 1;
      if ( a2 )
      {
        v11 = *(int (__fastcall **)(__int64, __int64 *, wchar_t **, int *))(*(_QWORD *)a1 + 104LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (void **)&Str,
          0);
        if ( v11(a1, MF_DEVICESTREAM_REQUIRED_PACKAGEFAMILYNAMES, &Str, &v12) >= 0 )
        {
          if ( (unsigned int)_o__wcsicmp(Str, L"pfn:blockall") )
            *a3 = wcsstr(Str, a2) != 0;
          else
            *a3 = 0;
        }
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v8 = "available";
        v9 = L"null";
        if ( Str )
          v9 = Str;
        if ( !*a3 )
          v8 = "not available";
        WPP_SF_SsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v8, (__int64)v9);
      }
      goto LABEL_5;
    }
    v6 = -2147467261;
    if ( !g_wppLevels )
      return v6;
    v10 = 50;
  }
  else
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      return v6;
    v10 = 49;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v6);
LABEL_5:
  if ( Str )
    CoTaskMemFree(Str);
  return v6;
}

```

## disassembly

```asm
0x18001ad90  mov     rax, rsp
0x18001ad93  mov     [rax+10h], rbx
0x18001ad97  mov     [rax+18h], rbp
0x18001ad9b  push    rsi
0x18001ad9c  push    rdi
0x18001ad9d  push    r14
0x18001ad9f  sub     rsp, 30h
0x18001ada3  mov     qword ptr [rax+20h], 0
0x18001adab  mov     rsi, r8
0x18001adae  mov     dword ptr [rax+8], 0
0x18001adb5  mov     rbp, rdx
0x18001adb8  mov     r14, rcx
0x18001adbb  test    rcx, rcx
0x18001adbe  jz      loc_18001AE5E
0x18001adc4  test    r8, r8
0x18001adc7  jz      loc_18001AE9B
0x18001adcd  xor     edi, edi
0x18001adcf  mov     dword ptr [r8], 1
0x18001add6  test    rdx, rdx
0x18001add9  jnz     loc_18001AEAF
0x18001addf  cmp     cs:byte_18008D62D, 8
0x18001ade6  jnb     short loc_18001AE0B
0x18001ade8  mov     rcx, [rsp+48h+Str]; pv
0x18001aded  test    rcx, rcx
0x18001adf0  jnz     loc_18001AF20
0x18001adf6  mov     rbx, [rsp+48h+arg_8]
0x18001adfb  mov     eax, edi
0x18001adfd  mov     rbp, [rsp+48h+arg_10]
0x18001ae02  add     rsp, 30h
0x18001ae06  pop     r14
0x18001ae08  pop     rdi
0x18001ae09  pop     rsi
0x18001ae0a  retn
0x18001ae0b  mov     rcx, [rsp+48h+Str]
0x18001ae10  lea     r8, aNull; "null"
0x18001ae17  test    rcx, rcx
0x18001ae1a  lea     rax, aAvailable; "available"
0x18001ae21  mov     rdx, r8
0x18001ae24  cmovnz  rdx, rcx
0x18001ae28  cmp     [rsi], edi
0x18001ae2a  lea     rcx, aNotAvailable; "not available"
0x18001ae31  mov     [rsp+48h+var_20], rdx; __int64
0x18001ae36  cmovz   rax, rcx
0x18001ae3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae41  test    rbp, rbp
0x18001ae44  mov     [rsp+48h+var_28], rax; __int64
0x18001ae49  cmovz   rbp, r8
0x18001ae4d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001ae54  mov     r9, rbp
0x18001ae57  call    WPP_SF_SsS
0x18001ae5c  jmp     short loc_18001ADE8
0x18001ae5e  mov     edi, 80070057h
0x18001ae63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ae6a  jb      short loc_18001ADF6
0x18001ae6c  mov     edx, 31h ; '1'
0x18001ae71  jmp     short loc_18001AE78
0x18001ae73  mov     edx, 32h ; '2'
0x18001ae78  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae7f  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18001ae86  xor     r9d, r9d
0x18001ae89  mov     dword ptr [rsp+48h+var_28], edi
0x18001ae8d  mov     rcx, [rcx+10h]
0x18001ae91  call    WPP_SF_qD
0x18001ae96  jmp     loc_18001ADE8
0x18001ae9b  mov     edi, 80004003h
0x18001aea0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001aea7  jb      loc_18001ADF6
0x18001aead  jmp     short loc_18001AE73
0x18001aeaf  mov     rax, [rcx]
0x18001aeb2  xor     edx, edx
0x18001aeb4  lea     rcx, [rsp+48h+Str]
0x18001aeb9  mov     rbx, [rax+68h]
0x18001aebd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001aec2  lea     r9, [rsp+48h+arg_0]
0x18001aec7  mov     rcx, r14
0x18001aeca  lea     r8, [rsp+48h+Str]
0x18001aecf  mov     rax, rbx
0x18001aed2  lea     rdx, MF_DEVICESTREAM_REQUIRED_PACKAGEFAMILYNAMES
0x18001aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aede  test    eax, eax
0x18001aee0  js      loc_18001ADDF
0x18001aee6  mov     rcx, [rsp+48h+Str]
0x18001aeeb  lea     rdx, aPfnBlockall; "pfn:blockall"
0x18001aef2  call    cs:__imp__o__wcsicmp
0x18001aef8  test    eax, eax
0x18001aefa  jnz     short loc_18001AF03
0x18001aefc  mov     [rsi], edi
0x18001aefe  jmp     loc_18001ADDF
0x18001af03  mov     rcx, [rsp+48h+Str]; Str
0x18001af08  mov     rdx, rbp; SubStr
0x18001af0b  call    cs:__imp_wcsstr
0x18001af11  xor     ecx, ecx
0x18001af13  test    rax, rax
0x18001af16  setnz   cl
0x18001af19  mov     [rsi], ecx
0x18001af1b  jmp     loc_18001ADDF
0x18001af20  call    cs:__imp_CoTaskMemFree
0x18001af26  jmp     loc_18001ADF6
```
