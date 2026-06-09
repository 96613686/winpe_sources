# CloudExperienceHostAPI::UtilStaticsCore::IsDataMartSim(HSTRING__ *,uchar *)

- ea: `0x1800b7630`
- end: `0x1800b770b`
- name: `?IsDataMartSim@UtilStaticsCore@CloudExperienceHostAPI@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `219`
- prototype: `int(CloudExperienceHostAPI::UtilStaticsCore *__hidden this, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x1800128a4`
- `0x1800153f8`
- `0x180059ecc`
- `0x1800b7630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7686`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b7664`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b76de`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b7664`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b76de`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::UtilStaticsCore::IsDataMartSim(
        CloudExperienceHostAPI::UtilStaticsCore *this,
        HSTRING a2,
        bool *a3)
{
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v11; // [rsp+40h] [rbp+18h] BYREF
  __int64 v12; // [rsp+48h] [rbp+20h] BYREF

  *a3 = 0;
  v11 = 0;
  result = PersistentRegPathGetDWORD(5, L"Network", L"PaidCell", &v11);
  if ( (_DWORD)result || v11 )
  {
    v12 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v7 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &v12,
           L"%s%s",
           L"Network\\DataMarketplace\\PerSimSettings\\",
           StringRawBuffer);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( !(unsigned int)PersistentRegPathGetDWORD(5, v12, L"SupportDataMarketplace", &v11) )
        *a3 = v11 == 1;
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
        (const char *)(unsigned int)v7,
        v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800b7630  mov     [rsp+arg_0], rbx
0x1800b7635  push    rdi; int
0x1800b7636  sub     rsp, 20h
0x1800b763a  mov     rdi, r8
0x1800b763d  mov     byte ptr [r8], 0
0x1800b7641  mov     rbx, rdx
0x1800b7644  mov     [rsp+28h+arg_10], 0
0x1800b764c  lea     r8, aPaidcell; "PaidCell"
0x1800b7653  mov     ecx, 5
0x1800b7658  lea     rdx, aNetwork; "Network"
0x1800b765f  lea     r9, [rsp+28h+arg_10]
0x1800b7664  call    cs:__imp_PersistentRegPathGetDWORD
0x1800b766a  test    eax, eax
0x1800b766c  jnz     short loc_1800B7678
0x1800b766e  cmp     [rsp+28h+arg_10], eax
0x1800b7672  jz      loc_1800B7700
0x1800b7678  xor     edx, edx; length
0x1800b767a  mov     [rsp+28h+arg_18], 0
0x1800b7683  mov     rcx, rbx; string
0x1800b7686  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b768c  mov     r9, rax
0x1800b768f  lea     r8, aNetworkDatamar; "Network\\DataMarketplace\\PerSimSetting"...
0x1800b7696  lea     rdx, aSS_0; "%s%s"
0x1800b769d  lea     rcx, [rsp+28h+arg_18]
0x1800b76a2  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800b76a7  mov     ebx, eax
0x1800b76a9  test    eax, eax
0x1800b76ab  jns     short loc_1800B76C8
0x1800b76ad  mov     rcx, [rsp+28h]; this
0x1800b76b2  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800b76b9  mov     r9d, eax; char *
0x1800b76bc  mov     edx, 0FDh; void *
0x1800b76c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b76c6  jmp     short loc_1800B76F4
0x1800b76c8  mov     rdx, [rsp+28h+arg_18]
0x1800b76cd  lea     r9, [rsp+28h+arg_10]
0x1800b76d2  lea     r8, aSupportdatamar; "SupportDataMarketplace"
0x1800b76d9  mov     ecx, 5
0x1800b76de  call    cs:__imp_PersistentRegPathGetDWORD
0x1800b76e4  test    eax, eax
0x1800b76e6  jnz     short loc_1800B76F2
0x1800b76e8  cmp     [rsp+28h+arg_10], 1
0x1800b76ed  setz    al
0x1800b76f0  mov     [rdi], al
0x1800b76f2  xor     ebx, ebx
0x1800b76f4  lea     rcx, [rsp+28h+arg_18]
0x1800b76f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b76fe  mov     eax, ebx
0x1800b7700  mov     rbx, [rsp+28h+arg_0]
0x1800b7705  add     rsp, 20h
0x1800b7709  pop     rdi
0x1800b770a  retn
```
