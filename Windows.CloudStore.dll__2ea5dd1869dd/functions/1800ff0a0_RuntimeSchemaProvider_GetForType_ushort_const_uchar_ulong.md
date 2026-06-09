# RuntimeSchemaProvider::GetForType(ushort const *,uchar * *,ulong *)

- ea: `0x1800ff0a0`
- end: `0x1800ff290`
- name: `?GetForType@RuntimeSchemaProvider@@UEAAJPEBGPEAPEAEPEAK@Z`
- size: `496`
- prototype: `int(RuntimeSchemaProvider *__hidden this, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801cae70`

## callees

- `0x18003e670`
- `0x18003f6c4`
- `0x18007e0c8`
- `0x18007e75c`
- `0x180091b04`
- `0x1800c8458`
- `0x1800ff0a0`
- `0x1800ff298`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff0ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff0ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ff137`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ff215`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ff137`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ff215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff266`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff1ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff266`

## pseudocode

```c
__int64 __fastcall RuntimeSchemaProvider::GetForType(
        HKEY *this,
        const unsigned __int16 *a2,
        LPVOID *a3,
        unsigned int *a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  int v10; // ebx
  void *v11; // rcx
  void *v12; // rcx
  unsigned int v13; // eax
  void *v14; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-18h] BYREF
  void *v20; // [rsp+40h] [rbp-10h] BYREF
  char v21; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  *a4 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(this[6], a2, 0, 1u, &hKey);
  if ( v8 == 2 || v8 == 1018 )
    goto LABEL_23;
  if ( v8 )
  {
    v9 = 65;
LABEL_9:
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v9,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\runtimeschemaprovider.cpp",
            (const char *)v8,
            phkResult);
    goto LABEL_24;
  }
  cbData = 0;
  v8 = RegQueryValueExW(hKey, L"Schema", 0, 0, 0, &cbData);
  if ( v8 == 2 || v8 == 1018 )
    goto LABEL_23;
  if ( v8 )
  {
    v9 = 68;
    goto LABEL_9;
  }
  pv = 0;
  p_pv = &pv;
  v21 = 1;
  v20 = 0;
  v18 = 0;
  v10 = ULongLongMult(cbData, 1u, &v18);
  if ( v10 >= 0 )
    v10 = CTCoAllocPolicy::Alloc(v11, 1u, v18, &v20);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v10 >= 0 )
  {
    v13 = RegQueryValueExW(hKey, L"Schema", 0, 0, (LPBYTE)pv, &cbData);
    if ( v13 != 2 && v13 != 1018 )
    {
      if ( !v13 )
      {
        *a3 = pv;
        *a4 = cbData;
        pv = 0;
        v10 = 0;
        goto LABEL_24;
      }
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x49,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\runtimeschemaprovider.cpp",
              (const char *)v13,
              phkResulta);
      goto LABEL_14;
    }
    v14 = pv;
    pv = 0;
    if ( v14 )
      CoTaskMemFree(v14);
LABEL_23:
    v10 = -2147024894;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x47,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\runtimeschemaprovider.cpp",
    (const char *)(unsigned int)v10,
    phkResult);
LABEL_14:
  v12 = pv;
  pv = 0;
  if ( v12 )
    CoTaskMemFree(v12);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ff0a0  mov     [rsp-28h+arg_8], rbx
0x1800ff0a5  push    rbp
0x1800ff0a6  push    rsi
0x1800ff0a7  push    rdi
0x1800ff0a8  push    r14
0x1800ff0aa  push    r15
0x1800ff0ac  mov     rbp, rsp
0x1800ff0af  sub     rsp, 50h
0x1800ff0b3  mov     rsi, r9
0x1800ff0b6  mov     r14, r8
0x1800ff0b9  mov     rbx, rdx
0x1800ff0bc  mov     rdi, rcx
0x1800ff0bf  xor     r15d, r15d
0x1800ff0c2  mov     [r8], r15
0x1800ff0c5  mov     [r9], r15d
0x1800ff0c8  mov     [rbp+hKey], r15
0x1800ff0cc  xor     edx, edx
0x1800ff0ce  lea     rcx, [rbp+hKey]
0x1800ff0d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ff0d7  lea     rax, [rbp+hKey]
0x1800ff0db  mov     [rsp+50h+phkResult], rax; phkResult
0x1800ff0e0  lea     r9d, [r15+1]; samDesired
0x1800ff0e4  xor     r8d, r8d; ulOptions
0x1800ff0e7  mov     rdx, rbx; lpSubKey
0x1800ff0ea  mov     rcx, [rdi+30h]; hKey
0x1800ff0ee  call    cs:__imp_RegOpenKeyExW
0x1800ff0f4  cmp     eax, 2
0x1800ff0f7  jz      loc_1800FF26C
0x1800ff0fd  mov     edi, 3FAh
0x1800ff102  cmp     eax, edi
0x1800ff104  jz      loc_1800FF26C
0x1800ff10a  test    eax, eax
0x1800ff10c  jz      short loc_1800FF114
0x1800ff10e  lea     edx, [r15+41h]
0x1800ff112  jmp     short loc_1800FF157
0x1800ff114  mov     [rbp+cbData], r15d
0x1800ff118  lea     rax, [rbp+cbData]
0x1800ff11c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800ff121  mov     [rsp+50h+phkResult], r15; int
0x1800ff126  xor     r9d, r9d; lpType
0x1800ff129  xor     r8d, r8d; lpReserved
0x1800ff12c  lea     rdx, aSchema_0; "Schema"
0x1800ff133  mov     rcx, [rbp+hKey]; hKey
0x1800ff137  call    cs:__imp_RegQueryValueExW
0x1800ff13d  cmp     eax, 2
0x1800ff140  jz      loc_1800FF26C
0x1800ff146  cmp     eax, edi
0x1800ff148  jz      loc_1800FF26C
0x1800ff14e  test    eax, eax
0x1800ff150  jz      short loc_1800FF171
0x1800ff152  mov     edx, 44h ; 'D'; void *
0x1800ff157  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800ff15e  mov     r9d, eax; char *
0x1800ff161  mov     rcx, [rbp+28h]; this
0x1800ff165  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ff16a  mov     ebx, eax
0x1800ff16c  jmp     loc_1800FF271
0x1800ff171  mov     [rbp+pv], r15
0x1800ff175  lea     rax, [rbp+pv]
0x1800ff179  mov     [rbp+var_18], rax
0x1800ff17d  mov     [rbp+var_8], 1
0x1800ff181  mov     [rbp+var_10], r15
0x1800ff185  mov     [rbp+var_20], r15
0x1800ff189  mov     ecx, [rbp+cbData]; unsigned __int64
0x1800ff18c  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800ff190  mov     edx, 1; unsigned __int64
0x1800ff195  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800ff19a  mov     ebx, eax
0x1800ff19c  test    eax, eax
0x1800ff19e  js      short loc_1800FF1B4
0x1800ff1a0  lea     r9, [rbp+var_10]; void **
0x1800ff1a4  mov     r8, [rbp+var_20]; unsigned __int64
0x1800ff1a8  mov     edx, 1; unsigned int
0x1800ff1ad  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800ff1b2  mov     ebx, eax
0x1800ff1b4  lea     rcx, [rbp+var_18]
0x1800ff1b8  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800ff1bd  test    ebx, ebx
0x1800ff1bf  jns     short loc_1800FF1F2
0x1800ff1c1  mov     rcx, [rbp+28h]; this
0x1800ff1c5  mov     r9d, ebx; char *
0x1800ff1c8  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800ff1cf  mov     edx, 47h ; 'G'; void *
0x1800ff1d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff1d9  mov     rcx, [rbp+pv]; pv
0x1800ff1dd  mov     [rbp+pv], r15
0x1800ff1e1  test    rcx, rcx
0x1800ff1e4  jz      loc_1800FF271
0x1800ff1ea  call    cs:__imp_CoTaskMemFree
0x1800ff1f0  jmp     short loc_1800FF271
0x1800ff1f2  mov     rax, [rbp+pv]
0x1800ff1f6  lea     rcx, [rbp+cbData]
0x1800ff1fa  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x1800ff1ff  mov     [rsp+50h+phkResult], rax; unsigned int
0x1800ff204  xor     r9d, r9d; lpType
0x1800ff207  xor     r8d, r8d; lpReserved
0x1800ff20a  lea     rdx, aSchema_0; "Schema"
0x1800ff211  mov     rcx, [rbp+hKey]; hKey
0x1800ff215  call    cs:__imp_RegQueryValueExW
0x1800ff21b  cmp     eax, 2
0x1800ff21e  jz      short loc_1800FF259
0x1800ff220  cmp     eax, edi
0x1800ff222  jz      short loc_1800FF259
0x1800ff224  test    eax, eax
0x1800ff226  jz      short loc_1800FF244
0x1800ff228  mov     rcx, [rbp+28h]; this
0x1800ff22c  mov     r9d, eax; char *
0x1800ff22f  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800ff236  mov     edx, 49h ; 'I'; void *
0x1800ff23b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ff240  mov     ebx, eax
0x1800ff242  jmp     short loc_1800FF1D9
0x1800ff244  mov     rax, [rbp+pv]
0x1800ff248  mov     [r14], rax
0x1800ff24b  mov     eax, [rbp+cbData]
0x1800ff24e  mov     [rsi], eax
0x1800ff250  mov     [rbp+pv], r15
0x1800ff254  mov     ebx, r15d
0x1800ff257  jmp     short loc_1800FF271
0x1800ff259  mov     rcx, [rbp+pv]; pv
0x1800ff25d  mov     [rbp+pv], r15
0x1800ff261  test    rcx, rcx
0x1800ff264  jz      short loc_1800FF26C
0x1800ff266  call    cs:__imp_CoTaskMemFree
0x1800ff26c  mov     ebx, 80070002h
0x1800ff271  lea     rcx, [rbp+hKey]
0x1800ff275  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ff27a  mov     eax, ebx
0x1800ff27c  mov     rbx, [rsp+50h+arg_8]
0x1800ff284  add     rsp, 50h
0x1800ff288  pop     r15
0x1800ff28a  pop     r14
0x1800ff28c  pop     rdi
0x1800ff28d  pop     rsi
0x1800ff28e  pop     rbp
0x1800ff28f  retn
```
