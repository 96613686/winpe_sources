# WindowsStorage::Utilities::registry_key_iterator::_GetSubKeyPathForIndex(ulong)

- ea: `0x1800100fc`
- end: `0x1800102b5`
- name: `?_GetSubKeyPathForIndex@registry_key_iterator@Utilities@WindowsStorage@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `441`
- prototype: `unsigned __int16 **__fastcall(__int64, unsigned __int16 **, DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180010000`

## callees

- `0x180008678`
- `0x18000bf7c`
- `0x18000d504`
- `0x18000d904`
- `0x1800100fc`
- `0x180010670`
- `0x1800106d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010168`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010168`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001025f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001025f`

## string_xrefs

- `0x180010179`: `onecore\base\windows.storage\src\Registry.h`
- `0x1800101e7`: `onecore\base\windows.storage\src\Registry.h`
- `0x180010216`: `onecore\base\windows.storage\src\Registry.h`
- `0x18001027c`: `onecore\base\windows.storage\src\Registry.h`

## pseudocode

```c
unsigned __int16 **__fastcall WindowsStorage::Utilities::registry_key_iterator::_GetSubKeyPathForIndex(
        __int64 a1,
        unsigned __int16 **a2,
        DWORD a3)
{
  HKEY *v6; // rax
  HKEY v7; // rcx
  unsigned int v8; // eax
  const unsigned __int16 **v9; // r8
  const unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // rbx
  int v12; // eax
  int v13; // eax
  HKEY *v14; // rax
  HKEY v15; // rcx
  unsigned int v16; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-50h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-50h]
  void *v20; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD cbMaxSubKeyLen; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v23; // [rsp+B8h] [rbp+48h] BYREF

  v23 = 0;
  cbMaxSubKeyLen = 0;
  v6 = *(HKEY **)(a1 + 8);
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  v8 = RegQueryInfoKeyW(v7, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)v8,
      lpcSubKeys);
  cbMaxSubKeyLen += *(_DWORD *)(a1 + 40) + 2;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v20);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v23,
    &v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  v9 = *(const unsigned __int16 ***)(a1 + 24);
  if ( v9 )
    v10 = *v9;
  else
    v10 = 0;
  v11 = v23;
  v12 = StringCchCatW(v23, cbMaxSubKeyLen, v10);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)(unsigned int)v12,
      lpcSubKeys);
  v13 = StringCchCatW(v11, cbMaxSubKeyLen, L"\\");
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)(unsigned int)v13,
      lpcSubKeys);
  v14 = *(HKEY **)(a1 + 8);
  if ( v14 )
    v15 = *v14;
  else
    v15 = 0;
  v16 = RegEnumKeyExW(v15, a3, &v11[*(_QWORD *)(a1 + 40) + 1], &cbMaxSubKeyLen, 0, 0, 0, 0);
  if ( v16 == 259 )
  {
    *a2 = 0;
  }
  else
  {
    if ( v16 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
        (const char *)v16,
        lpcSubKeysa);
    *a2 = v11;
    v23 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v23);
  return a2;
}

```

## disassembly

```asm
0x1800100fc  mov     [rsp-28h+arg_8], rbx
0x180010101  push    rbp
0x180010102  push    rsi
0x180010103  push    rdi
0x180010104  push    r14
0x180010106  push    r15
0x180010108  mov     rbp, rsp
0x18001010b  sub     rsp, 70h
0x18001010f  mov     r14d, r8d
0x180010112  mov     rdi, rdx
0x180010115  mov     rsi, rcx
0x180010118  xor     r15d, r15d
0x18001011b  mov     [rbp+arg_18], r15
0x18001011f  mov     [rbp+cbMaxSubKeyLen], r15d
0x180010123  mov     rax, [rcx+8]
0x180010127  test    rax, rax
0x18001012a  jz      short loc_180010131
0x18001012c  mov     rcx, [rax]
0x18001012f  jmp     short loc_180010134
0x180010131  mov     rcx, r15; hKey
0x180010134  mov     [rsp+70h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180010139  mov     [rsp+70h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001013e  mov     [rsp+70h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180010143  mov     [rsp+70h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180010148  mov     [rsp+70h+lpcValues], r15; lpcValues
0x18001014d  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180010152  lea     rax, [rbp+cbMaxSubKeyLen]
0x180010156  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001015b  mov     [rsp+70h+lpcSubKeys], r15; int
0x180010160  xor     r9d, r9d; lpReserved
0x180010163  xor     r8d, r8d; lpcchClass
0x180010166  xor     edx, edx; lpClass
0x180010168  call    cs:__imp_RegQueryInfoKeyW
0x18001016e  mov     rcx, [rbp+28h]; this
0x180010172  test    eax, eax
0x180010174  jz      short loc_18001018B
0x180010176  mov     r9d, eax; char *
0x180010179  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x180010180  mov     edx, 1CDh; void *
0x180010185  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001018b  mov     eax, [rbp+cbMaxSubKeyLen]
0x18001018e  add     eax, 2
0x180010191  add     eax, [rsi+28h]
0x180010194  mov     [rbp+cbMaxSubKeyLen], eax
0x180010197  lea     r8d, [rax-1]
0x18001019b  xor     edx, edx
0x18001019d  lea     rcx, [rbp+var_8]
0x1800101a1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800101a6  lea     rdx, [rbp+var_8]
0x1800101aa  lea     rcx, [rbp+arg_18]
0x1800101ae  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800101b3  lea     rcx, [rbp+var_8]
0x1800101b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800101bc  mov     r8, [rsi+18h]
0x1800101c0  test    r8, r8
0x1800101c3  jz      short loc_1800101CA
0x1800101c5  mov     r8, [r8]
0x1800101c8  jmp     short loc_1800101CD
0x1800101ca  mov     r8, r15; unsigned __int16 *
0x1800101cd  mov     edx, [rbp+cbMaxSubKeyLen]; unsigned __int64
0x1800101d0  mov     rbx, [rbp+arg_18]
0x1800101d4  mov     rcx, rbx; unsigned __int16 *
0x1800101d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800101dc  mov     rcx, [rbp+28h]; this
0x1800101e0  test    eax, eax
0x1800101e2  jns     short loc_1800101F9
0x1800101e4  mov     r9d, eax; char *
0x1800101e7  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x1800101ee  mov     edx, 1D1h; void *
0x1800101f3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800101f9  mov     edx, [rbp+cbMaxSubKeyLen]; unsigned __int64
0x1800101fc  lea     r8, StringValue; "\\"
0x180010203  mov     rcx, rbx; unsigned __int16 *
0x180010206  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001020b  mov     rcx, [rbp+28h]; this
0x18001020f  test    eax, eax
0x180010211  jns     short loc_180010228
0x180010213  mov     r9d, eax; char *
0x180010216  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x18001021d  mov     edx, 1D2h; void *
0x180010222  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010228  mov     rax, [rsi+28h]
0x18001022c  inc     rax
0x18001022f  lea     r8, [rbx+rax*2]; lpName
0x180010233  mov     rax, [rsi+8]
0x180010237  test    rax, rax
0x18001023a  jz      short loc_180010241
0x18001023c  mov     rcx, [rax]
0x18001023f  jmp     short loc_180010244
0x180010241  mov     rcx, r15; hKey
0x180010244  mov     [rsp+70h+lpcValues], r15; lpftLastWriteTime
0x180010249  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcchClass
0x18001024e  mov     [rsp+70h+lpcbMaxSubKeyLen], r15; lpClass
0x180010253  mov     [rsp+70h+lpcSubKeys], r15; unsigned int
0x180010258  lea     r9, [rbp+cbMaxSubKeyLen]; lpcchName
0x18001025c  mov     edx, r14d; dwIndex
0x18001025f  call    cs:__imp_RegEnumKeyExW
0x180010265  cmp     eax, 103h
0x18001026a  jnz     short loc_180010271
0x18001026c  mov     [rdi], r15
0x18001026f  jmp     short loc_180010295
0x180010271  mov     rcx, [rbp+28h]; this
0x180010275  test    eax, eax
0x180010277  jz      short loc_18001028E
0x180010279  mov     r9d, eax; char *
0x18001027c  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x180010283  mov     edx, 1D8h; void *
0x180010288  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001028e  mov     [rdi], rbx
0x180010291  mov     [rbp+arg_18], r15
0x180010295  lea     rcx, [rbp+arg_18]
0x180010299  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001029e  mov     rax, rdi
0x1800102a1  mov     rbx, [rsp+70h+arg_8]
0x1800102a9  add     rsp, 70h
0x1800102ad  pop     r15
0x1800102af  pop     r14
0x1800102b1  pop     rdi
0x1800102b2  pop     rsi
0x1800102b3  pop     rbp
0x1800102b4  retn
```
