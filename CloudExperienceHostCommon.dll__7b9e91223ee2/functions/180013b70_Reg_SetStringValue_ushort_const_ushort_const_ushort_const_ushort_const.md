# Reg::SetStringValue(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180013b70`
- end: `0x180013c0d`
- name: `?SetStringValue@Reg@@YAXPEBG000@Z`
- size: `157`
- prototype: `void(Reg *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012774`
- `0x1800d7ca0`

## callees

- `0x180013b70`
- `0x1800143b0`
- `0x18001475c`
- `0x1800798e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bcf`

## string_xrefs

- `0x180013be1`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Reg::SetStringValue(Reg *this, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  HKEY v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = a2;
  v6 = Reg::OpenKey((__int64)L"WebSignInNav", (__int64)a2, 0x20006u);
  v11 = (const unsigned __int16 *)v6;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&a4[2 * v7] );
  v8 = RegSetValueExW(v6, a3, 0, 1u, a4, 2 * v7 + 2);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v8,
      lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
}

```

## disassembly

```asm
0x180013b70  mov     [rsp+arg_0], rbx
0x180013b75  mov     [rsp+arg_10], rsi
0x180013b7a  mov     [rsp+arg_8], rdx
0x180013b7f  push    rdi
0x180013b80  sub     rsp, 30h
0x180013b84  mov     rbx, r9
0x180013b87  mov     rdi, r8
0x180013b8a  mov     r8d, 20006h
0x180013b90  lea     rcx, aWebsigninnav; "WebSignInNav"
0x180013b97  call    Reg__OpenKey
0x180013b9c  mov     [rsp+38h+arg_8], rax
0x180013ba1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013ba5  xor     esi, esi
0x180013ba7  inc     rcx
0x180013baa  cmp     [rbx+rcx*2], si
0x180013bae  jnz     short loc_180013BA7
0x180013bb0  lea     ecx, ds:2[rcx*2]
0x180013bb7  mov     [rsp+38h+cbData], ecx; cbData
0x180013bbb  mov     [rsp+38h+lpData], rbx; unsigned int
0x180013bc0  mov     r9d, 1; dwType
0x180013bc6  xor     r8d, r8d; Reserved
0x180013bc9  mov     rdx, rdi; lpValueName
0x180013bcc  mov     rcx, rax; hKey
0x180013bcf  call    cs:__imp_RegSetValueExW
0x180013bd5  mov     rcx, [rsp+38h]; this
0x180013bda  test    eax, eax
0x180013bdc  jz      short loc_180013BF3
0x180013bde  mov     r9d, eax; char *
0x180013be1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180013be8  mov     edx, 3Dh ; '='; void *
0x180013bed  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180013bf3  lea     rcx, [rsp+38h+arg_8]
0x180013bf8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013bfd  mov     rbx, [rsp+38h+arg_0]
0x180013c02  mov     rsi, [rsp+38h+arg_10]
0x180013c07  add     rsp, 30h
0x180013c0b  pop     rdi
0x180013c0c  retn
```
