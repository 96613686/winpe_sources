# OOBEOneDriveOptin::TryGetOfficeRegistryValue(ushort const *,ushort const *,ushort * *,uchar *)

- ea: `0x18001bf10`
- end: `0x18001c0d4`
- name: `?TryGetOfficeRegistryValue@OOBEOneDriveOptin@@UEAAJPEBG0PEAPEAGPEAE@Z`
- size: `452`
- prototype: `int(OOBEOneDriveOptin *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000d5a0`
- `0x180018268`
- `0x180018c98`
- `0x18001b5d4`
- `0x18001bf10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bfca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bfca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf95`

## string_xrefs

- `0x18001bf5b`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001c070`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall OOBEOneDriveOptin::TryGetOfficeRegistryValue(
        OOBEOneDriveOptin *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int8 *Type)
{
  unsigned __int8 *v5; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  int DWORD; // eax
  int phkResult; // [rsp+20h] [rbp-38h]
  int phkResulta; // [rsp+20h] [rbp-38h]
  void *v17; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  unsigned int v21; // [rsp+A8h] [rbp+50h] BYREF

  v5 = Type;
  lpSubKey[0] = 0;
  *Type = 0;
  *a4 = 0;
  v8 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         lpSubKey,
         L"%s\\%s",
         L"Software\\Microsoft\\Office",
         a2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0x101u, &hKey);
    if ( a3 && *a3 )
    {
      LODWORD(Type) = 0;
      if ( !RegQueryValueExW(hKey, a3, 0, (LPDWORD)&Type, 0, 0) )
      {
        v17 = 0;
        if ( (_DWORD)Type == 1 )
        {
          DWORD = SHRegAllocData(hKey, 0, a3, 2u, &v17, 0);
          v9 = DWORD;
          if ( DWORD < 0 )
          {
            v11 = 223;
            goto LABEL_15;
          }
        }
        else
        {
          if ( (_DWORD)Type != 4 )
          {
            v9 = -2147467259;
            v11 = 232;
            v12 = 2147500037LL;
LABEL_16:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v11,
              (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
              (const char *)v12,
              phkResulta);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            goto LABEL_20;
          }
          v21 = 0;
          DWORD = SHRegGetDWORD(hKey, 0, a3, &v21);
          v9 = DWORD;
          if ( DWORD < 0 )
          {
            v11 = 227;
LABEL_15:
            v12 = (unsigned int)DWORD;
            goto LABEL_16;
          }
          DWORD = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &v17,
                    L"%d",
                    v21);
          v9 = DWORD;
          if ( DWORD < 0 )
          {
            v11 = 228;
            goto LABEL_15;
          }
        }
        *a4 = (unsigned __int16 *)v17;
        *v5 = 1;
        v17 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
      }
    }
    else
    {
      *v5 = v10 == 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v9 = 0;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCF,
    (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v8,
    phkResult);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpSubKey);
  return v9;
}

```

## disassembly

```asm
0x18001bf10  push    rbp
0x18001bf12  push    rbx
0x18001bf13  push    rsi
0x18001bf14  push    rdi
0x18001bf15  push    r14
0x18001bf17  push    r15
0x18001bf19  mov     rbp, rsp
0x18001bf1c  sub     rsp, 58h
0x18001bf20  mov     rsi, qword ptr [rbp+Type]
0x18001bf24  lea     rcx, [rbp+lpSubKey]
0x18001bf28  xor     r15d, r15d
0x18001bf2b  mov     r14, r9
0x18001bf2e  mov     rdi, r8
0x18001bf31  mov     [rbp+lpSubKey], r15
0x18001bf35  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Office"
0x18001bf3c  mov     [rsi], r15b
0x18001bf3f  mov     [r9], r15
0x18001bf42  mov     r9, rdx
0x18001bf45  lea     rdx, aSS_0; "%s\\%s"
0x18001bf4c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001bf51  mov     ebx, eax
0x18001bf53  test    eax, eax
0x18001bf55  jns     short loc_18001BF74
0x18001bf57  mov     rcx, [rbp+30h]; this
0x18001bf5b  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001bf62  mov     r9d, eax; char *
0x18001bf65  mov     edx, 0CFh; void *
0x18001bf6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf6f  jmp     loc_18001C0BC
0x18001bf74  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001bf78  lea     rax, [rbp+hKey]
0x18001bf7c  mov     r9d, 101h; samDesired
0x18001bf82  mov     [rsp+58h+phkResult], rax; phkResult
0x18001bf87  xor     r8d, r8d; ulOptions
0x18001bf8a  mov     [rbp+hKey], r15
0x18001bf8e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001bf95  call    cs:__imp_RegOpenKeyExW
0x18001bf9b  test    rdi, rdi
0x18001bf9e  jz      loc_18001C0A9
0x18001bfa4  cmp     [rdi], r15w
0x18001bfa8  jz      loc_18001C0A9
0x18001bfae  mov     rcx, [rbp+hKey]; hKey
0x18001bfb2  lea     r9, [rbp+Type]; lpType
0x18001bfb6  mov     [rsp+58h+lpcbData], r15; lpcbData
0x18001bfbb  xor     r8d, r8d; lpReserved
0x18001bfbe  mov     rdx, rdi; lpValueName
0x18001bfc1  mov     [rsp+58h+phkResult], r15; lpData
0x18001bfc6  mov     [rbp+Type], r15d
0x18001bfca  call    cs:__imp_RegQueryValueExW
0x18001bfd0  test    eax, eax
0x18001bfd2  jnz     loc_18001C0B0
0x18001bfd8  mov     eax, [rbp+Type]
0x18001bfdb  mov     [rbp+var_28], r15
0x18001bfdf  sub     eax, 1
0x18001bfe2  jz      short loc_18001C03C
0x18001bfe4  cmp     eax, 3
0x18001bfe7  jz      short loc_18001BFF8
0x18001bfe9  mov     ebx, 80004005h
0x18001bfee  mov     edx, 0E8h
0x18001bff3  mov     r9d, ebx
0x18001bff6  jmp     short loc_18001C06C
0x18001bff8  mov     rcx, [rbp+hKey]; HKEY
0x18001bffc  lea     r9, [rbp+arg_18]; unsigned int *
0x18001c000  mov     r8, rdi; unsigned __int16 *
0x18001c003  mov     [rbp+arg_18], r15d
0x18001c007  xor     edx, edx; unsigned __int16 *
0x18001c009  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001c00e  mov     ebx, eax
0x18001c010  test    eax, eax
0x18001c012  jns     short loc_18001C01B
0x18001c014  mov     edx, 0E3h
0x18001c019  jmp     short loc_18001C069
0x18001c01b  mov     r8d, [rbp+arg_18]
0x18001c01f  lea     rdx, aD; "%d"
0x18001c026  lea     rcx, [rbp+var_28]
0x18001c02a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001c02f  mov     ebx, eax
0x18001c031  test    eax, eax
0x18001c033  jns     short loc_18001C090
0x18001c035  mov     edx, 0E4h
0x18001c03a  jmp     short loc_18001C069
0x18001c03c  mov     rcx, [rbp+hKey]; HKEY
0x18001c040  lea     rax, [rbp+var_28]
0x18001c044  mov     [rsp+58h+lpcbData], r15; unsigned int *
0x18001c049  mov     r9d, 2; int
0x18001c04f  mov     r8, rdi; unsigned __int16 *
0x18001c052  mov     [rsp+58h+phkResult], rax; int
0x18001c057  xor     edx, edx; unsigned __int16 *
0x18001c059  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18001c05e  mov     ebx, eax
0x18001c060  test    eax, eax
0x18001c062  jns     short loc_18001C090
0x18001c064  mov     edx, 0DFh; void *
0x18001c069  mov     r9d, eax; char *
0x18001c06c  mov     rcx, [rbp+30h]; this
0x18001c070  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001c077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c07c  lea     rcx, [rbp+var_28]
0x18001c080  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c085  lea     rcx, [rbp+hKey]
0x18001c089  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c08e  jmp     short loc_18001C0BC
0x18001c090  mov     rax, [rbp+var_28]
0x18001c094  lea     rcx, [rbp+var_28]
0x18001c098  mov     [r14], rax
0x18001c09b  mov     byte ptr [rsi], 1
0x18001c09e  mov     [rbp+var_28], r15
0x18001c0a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c0a7  jmp     short loc_18001C0B0
0x18001c0a9  test    eax, eax
0x18001c0ab  setz    al
0x18001c0ae  mov     [rsi], al
0x18001c0b0  lea     rcx, [rbp+hKey]
0x18001c0b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c0b9  mov     ebx, r15d
0x18001c0bc  lea     rcx, [rbp+lpSubKey]
0x18001c0c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c0c5  mov     eax, ebx
0x18001c0c7  add     rsp, 58h
0x18001c0cb  pop     r15
0x18001c0cd  pop     r14
0x18001c0cf  pop     rdi
0x18001c0d0  pop     rsi
0x18001c0d1  pop     rbx
0x18001c0d2  pop     rbp
0x18001c0d3  retn
```
