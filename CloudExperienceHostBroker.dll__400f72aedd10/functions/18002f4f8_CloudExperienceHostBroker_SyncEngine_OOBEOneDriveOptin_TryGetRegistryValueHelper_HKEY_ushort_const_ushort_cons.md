# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetRegistryValueHelper(HKEY__ *,ushort const *,ushort const *,ushort const *,HSTRING__ * *,uchar *)

- ea: `0x18002f4f8`
- end: `0x18002f71e`
- name: `?TryGetRegistryValueHelper@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@AEAAJPEAUHKEY__@@PEBG11PEAPEAUHSTRING__@@PEAE@Z`
- size: `550`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValueName, HKEY hKey, bool *pcbData)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f490`
- `0x18002f730`

## callees

- `0x180008344`
- `0x180012408`
- `0x1800177c8`
- `0x18002253c`
- `0x180028a7c`
- `0x18002f4f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f5b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f5b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f57f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f57f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f6ca`

## string_xrefs

- `0x18002f545`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002f68b`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetRegistryValueHelper(
        CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpValueName,
        HKEY hKey,
        bool *pcbData)
{
  HSTRING *v7; // rsi
  bool *v8; // rdi
  int v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  const unsigned __int16 *v12; // rbx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r9
  LSTATUS ValueW; // eax
  int String; // eax
  __int64 v18; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  PCNZWCH sourceString; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *pvData; // [rsp+70h] [rbp+20h] BYREF
  HKEY Type; // [rsp+78h] [rbp+28h] BYREF

  Type = a2;
  pvData = this;
  v7 = (HSTRING *)hKey;
  v8 = pcbData;
  lpSubKey = 0;
  *pcbData = 0;
  *v7 = 0;
  v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &lpSubKey,
         L"%s\\%s",
         a3,
         a4);
  v10 = v9;
  if ( v9 >= 0 )
  {
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x101u, &hKey);
    v12 = lpValueName;
    if ( lpValueName && *lpValueName )
    {
      LODWORD(Type) = 0;
      if ( !RegQueryValueExW(hKey, lpValueName, 0, (LPDWORD)&Type, 0, 0) )
      {
        sourceString = 0;
        if ( (_DWORD)Type == 1 )
        {
          String = SHRegAllocData(hKey, 0, v12, v13, (void **)&sourceString);
          v10 = String;
          if ( String < 0 )
          {
            v14 = 336;
            goto LABEL_17;
          }
        }
        else
        {
          if ( (_DWORD)Type != 4 )
          {
            v10 = -2147467259;
            v14 = 345;
            v15 = 2147500037LL;
LABEL_18:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
              (const char *)v15,
              phkResulta);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            goto LABEL_28;
          }
          LODWORD(pvData) = 0;
          LODWORD(pcbData) = 4;
          ValueW = RegGetValueW(hKey, 0, v12, 0x10u, 0, &pvData, (LPDWORD)&pcbData);
          v10 = ValueW;
          if ( ValueW > 0 )
            v10 = (unsigned __int16)ValueW | 0x80070000;
          if ( (v10 & 0x80000000) != 0 )
          {
            v15 = v10;
            v14 = 340;
            goto LABEL_18;
          }
          String = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                     &sourceString,
                     L"%d",
                     (unsigned int)pvData);
          v10 = String;
          if ( String < 0 )
          {
            v14 = 341;
LABEL_17:
            v15 = (unsigned int)String;
            goto LABEL_18;
          }
        }
        if ( sourceString )
        {
          v18 = -1;
          do
            ++v18;
          while ( sourceString[v18] );
        }
        else
        {
          LODWORD(v18) = 0;
        }
        String = WindowsCreateString(sourceString, v18, v7);
        v10 = String;
        if ( String < 0 )
        {
          v14 = 348;
          goto LABEL_17;
        }
        *v8 = 1;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
      }
    }
    else
    {
      *v8 = v11 == 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v10 = 0;
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x140,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v9,
    phkResult);
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  return v10;
}

```

## disassembly

```asm
0x18002f4f8  mov     rax, rsp
0x18002f4fb  mov     [rax+18h], rbx
0x18002f4ff  mov     [rax+20h], rsi
0x18002f503  mov     [rax+10h], rdx
0x18002f507  mov     [rax+8], rcx
0x18002f50b  push    rbp
0x18002f50c  push    rdi
0x18002f50d  push    r14
0x18002f50f  mov     rbp, rsp
0x18002f512  sub     rsp, 50h
0x18002f516  mov     rsi, [rbp+hKey]
0x18002f51a  lea     rdx, aSS; "%s\\%s"
0x18002f521  mov     rdi, [rbp+arg_30]
0x18002f525  lea     rcx, [rbp+lpSubKey]
0x18002f529  xor     r14d, r14d
0x18002f52c  mov     [rbp+lpSubKey], r14
0x18002f530  mov     [rdi], r14b
0x18002f533  mov     [rsi], r14
0x18002f536  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18002f53b  mov     ebx, eax
0x18002f53d  test    eax, eax
0x18002f53f  jns     short loc_18002F55E
0x18002f541  mov     rcx, [rbp+18h]; this
0x18002f545  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002f54c  mov     r9d, eax; char *
0x18002f54f  mov     edx, 140h; void *
0x18002f554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f559  jmp     loc_18002F6FE
0x18002f55e  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002f562  lea     rax, [rbp+hKey]
0x18002f566  mov     r9d, 101h; samDesired
0x18002f56c  mov     [rsp+50h+phkResult], rax; phkResult
0x18002f571  xor     r8d, r8d; ulOptions
0x18002f574  mov     [rbp+hKey], r14
0x18002f578  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f57f  call    cs:__imp_RegOpenKeyExW
0x18002f585  mov     rbx, [rbp+lpValueName]
0x18002f589  test    rbx, rbx
0x18002f58c  jz      loc_18002F6EB
0x18002f592  cmp     [rbx], r14w
0x18002f596  jz      loc_18002F6EB
0x18002f59c  mov     rcx, [rbp+hKey]; hKey
0x18002f5a0  lea     r9, [rbp+Type]; lpType
0x18002f5a4  mov     [rsp+50h+lpcbData], r14; unsigned int *
0x18002f5a9  xor     r8d, r8d; lpReserved
0x18002f5ac  mov     rdx, rbx; lpValueName
0x18002f5af  mov     [rsp+50h+phkResult], r14; lpData
0x18002f5b4  mov     dword ptr [rbp+Type], r14d
0x18002f5b8  call    cs:__imp_RegQueryValueExW
0x18002f5be  test    eax, eax
0x18002f5c0  jnz     loc_18002F6F2
0x18002f5c6  mov     eax, dword ptr [rbp+Type]
0x18002f5c9  mov     [rbp+sourceString], r14
0x18002f5cd  sub     eax, 1
0x18002f5d0  jz      loc_18002F662
0x18002f5d6  cmp     eax, 3
0x18002f5d9  jz      short loc_18002F5ED
0x18002f5db  mov     ebx, 80004005h
0x18002f5e0  mov     edx, 159h
0x18002f5e5  mov     r9d, ebx
0x18002f5e8  jmp     loc_18002F687
0x18002f5ed  mov     rcx, [rbp+hKey]; hkey
0x18002f5f1  lea     rax, [rbp+arg_30]
0x18002f5f5  mov     [rsp+50h+pcbData], rax; pcbData
0x18002f5fa  mov     r9d, 10h; dwFlags
0x18002f600  lea     rax, [rbp+pvData]
0x18002f604  mov     dword ptr [rbp+pvData], r14d
0x18002f608  mov     [rsp+50h+lpcbData], rax; pvData
0x18002f60d  mov     r8, rbx; lpValue
0x18002f610  xor     edx, edx; lpSubKey
0x18002f612  mov     [rsp+50h+phkResult], r14; pdwType
0x18002f617  mov     dword ptr [rbp+arg_30], 4
0x18002f61e  call    cs:__imp_RegGetValueW
0x18002f624  mov     ebx, eax
0x18002f626  test    eax, eax
0x18002f628  jle     short loc_18002F633
0x18002f62a  movzx   ebx, ax
0x18002f62d  or      ebx, 80070000h
0x18002f633  test    ebx, ebx
0x18002f635  jns     short loc_18002F641
0x18002f637  mov     r9d, ebx
0x18002f63a  mov     edx, 154h
0x18002f63f  jmp     short loc_18002F687
0x18002f641  mov     r8d, dword ptr [rbp+pvData]
0x18002f645  lea     rdx, aD; "%d"
0x18002f64c  lea     rcx, [rbp+sourceString]
0x18002f650  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18002f655  mov     ebx, eax
0x18002f657  test    eax, eax
0x18002f659  jns     short loc_18002F6AB
0x18002f65b  mov     edx, 155h
0x18002f660  jmp     short loc_18002F684
0x18002f662  mov     rcx, [rbp+hKey]; HKEY
0x18002f666  lea     rax, [rbp+sourceString]
0x18002f66a  mov     r8, rbx; unsigned __int16 *
0x18002f66d  mov     [rsp+50h+phkResult], rax; int
0x18002f672  xor     edx, edx; unsigned __int16 *
0x18002f674  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18002f679  mov     ebx, eax
0x18002f67b  test    eax, eax
0x18002f67d  jns     short loc_18002F6AB
0x18002f67f  mov     edx, 150h; void *
0x18002f684  mov     r9d, eax; char *
0x18002f687  mov     rcx, [rbp+18h]; this
0x18002f68b  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002f692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f697  lea     rcx, [rbp+sourceString]
0x18002f69b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002f6a0  lea     rcx, [rbp+hKey]
0x18002f6a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002f6a9  jmp     short loc_18002F6FE
0x18002f6ab  mov     rcx, [rbp+sourceString]; sourceString
0x18002f6af  test    rcx, rcx
0x18002f6b2  jnz     short loc_18002F6B9
0x18002f6b4  mov     rdx, r14
0x18002f6b7  jmp     short loc_18002F6C7
0x18002f6b9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002f6bd  inc     rdx; length
0x18002f6c0  cmp     [rcx+rdx*2], r14w
0x18002f6c5  jnz     short loc_18002F6BD
0x18002f6c7  mov     r8, rsi; string
0x18002f6ca  call    cs:__imp_WindowsCreateString
0x18002f6d0  mov     ebx, eax
0x18002f6d2  test    eax, eax
0x18002f6d4  jns     short loc_18002F6DD
0x18002f6d6  mov     edx, 15Ch
0x18002f6db  jmp     short loc_18002F684
0x18002f6dd  lea     rcx, [rbp+sourceString]
0x18002f6e1  mov     byte ptr [rdi], 1
0x18002f6e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002f6e9  jmp     short loc_18002F6F2
0x18002f6eb  test    eax, eax
0x18002f6ed  setz    al
0x18002f6f0  mov     [rdi], al
0x18002f6f2  lea     rcx, [rbp+hKey]
0x18002f6f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002f6fb  mov     ebx, r14d
0x18002f6fe  lea     rcx, [rbp+lpSubKey]
0x18002f702  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002f707  lea     r11, [rsp+50h+var_s0]
0x18002f70c  mov     eax, ebx
0x18002f70e  mov     rbx, [r11+30h]
0x18002f712  mov     rsi, [r11+38h]
0x18002f716  mov     rsp, r11
0x18002f719  pop     r14
0x18002f71b  pop     rdi
0x18002f71c  pop     rbp
0x18002f71d  retn
```
