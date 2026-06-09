# CTreeWalker::LoadDependencies(void)

- ea: `0x180041398`
- end: `0x18004140d`
- name: `?LoadDependencies@CTreeWalker@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(CTreeWalker *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180040c08`
- `0x180040da4`

## callees

- `0x18003ceac`
- `0x180041398`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800413be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800413be`

## string_xrefs

- `0x1800413d7`: `PathIsNetworkPathW`
- `0x1800413b5`: `SHLWAPI.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTreeWalker::LoadDependencies(CTreeWalker *this)
{
  HMODULE *v1; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx

  v1 = (HMODULE *)((char *)this + 336);
  if ( !*((_QWORD *)this + 42) )
  {
    Library = LoadLibraryExW(L"SHLWAPI.DLL", 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v1,
      Library);
    if ( *v1 )
    {
      ProcAddress = GetProcAddress(*v1, "PathIsNetworkPathW");
      v5 = *v1;
      *((_QWORD *)this + 43) = ProcAddress;
      *((_QWORD *)this + 44) = GetProcAddress(v5, "AssocQueryStringW");
    }
  }
}

```

## disassembly

```asm
0x180041398  mov     [rsp+arg_0], rbx
0x18004139d  push    rdi
0x18004139e  sub     rsp, 20h
0x1800413a2  lea     rbx, [rcx+150h]
0x1800413a9  mov     rdi, rcx
0x1800413ac  cmp     qword ptr [rbx], 0
0x1800413b0  jnz     short loc_180041402
0x1800413b2  xor     r8d, r8d; dwFlags
0x1800413b5  lea     rcx, aShlwapiDll; "SHLWAPI.DLL"
0x1800413bc  xor     edx, edx; hFile
0x1800413be  call    cs:__imp_LoadLibraryExW
0x1800413c4  mov     rdx, rax
0x1800413c7  mov     rcx, rbx
0x1800413ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800413cf  mov     rcx, [rbx]; hModule
0x1800413d2  test    rcx, rcx
0x1800413d5  jz      short loc_180041402
0x1800413d7  lea     rdx, aPathisnetworkp; "PathIsNetworkPathW"
0x1800413de  call    cs:__imp_GetProcAddress
0x1800413e4  mov     rcx, [rbx]; hModule
0x1800413e7  lea     rdx, aAssocquerystri; "AssocQueryStringW"
0x1800413ee  mov     [rdi+158h], rax
0x1800413f5  call    cs:__imp_GetProcAddress
0x1800413fb  mov     [rdi+160h], rax
0x180041402  mov     rbx, [rsp+28h+arg_0]
0x180041407  add     rsp, 20h
0x18004140b  pop     rdi
0x18004140c  retn
```
