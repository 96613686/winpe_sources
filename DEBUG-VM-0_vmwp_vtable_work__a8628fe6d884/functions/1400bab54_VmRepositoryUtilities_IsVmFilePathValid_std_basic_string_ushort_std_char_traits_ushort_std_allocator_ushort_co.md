# VmRepositoryUtilities::IsVmFilePathValid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,bool)

- ea: `0x1400bab54`
- end: `0x1400babe3`
- name: `?IsVmFilePathValid@VmRepositoryUtilities@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1401e98cc`

## callees

- `0x1400bab54`
- `0x1400babec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400baba3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400baba3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400bab6e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1400bab6e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400bab8d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1400bab8d`

## pseudocode

```c
bool __fastcall VmRepositoryUtilities::IsVmFilePathValid(VmRepositoryUtilities::Details *pszPath, __int64 a2, char a3)
{
  VmRepositoryUtilities::Details *v4; // rbx
  const WCHAR *v5; // rcx
  LPWSTR ExtensionW; // rax
  const unsigned __int16 *v7; // rdx

  v4 = pszPath;
  if ( *((_QWORD *)pszPath + 3) > 7u )
    pszPath = *(VmRepositoryUtilities::Details **)pszPath;
  if ( PathIsRelativeW((LPCWSTR)pszPath) )
    return 0;
  v5 = *((_QWORD *)v4 + 3) <= 7u ? (const WCHAR *)v4 : *(const WCHAR **)v4;
  ExtensionW = PathFindExtensionW(v5);
  if ( (unsigned int)_o__wcsicmp(ExtensionW, L".vsv") )
    return 0;
  if ( !a3 )
    return 1;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(VmRepositoryUtilities::Details **)v4;
  return VmRepositoryUtilities::Details::FileExists(v4, v7);
}

```

## disassembly

```asm
0x1400bab54  mov     [rsp+arg_0], rbx
0x1400bab59  push    rdi
0x1400bab5a  sub     rsp, 20h
0x1400bab5e  cmp     qword ptr [rcx+18h], 7
0x1400bab63  mov     dil, r8b
0x1400bab66  mov     rbx, rcx
0x1400bab69  jbe     short loc_1400BAB6E
0x1400bab6b  mov     rcx, [rcx]; pszPath
0x1400bab6e  call    cs:__imp_PathIsRelativeW
0x1400bab75  nop     dword ptr [rax+rax+00h]
0x1400bab7a  test    eax, eax
0x1400bab7c  jnz     short loc_1400BABD5
0x1400bab7e  cmp     qword ptr [rbx+18h], 7
0x1400bab83  jbe     short loc_1400BAB8A
0x1400bab85  mov     rcx, [rbx]
0x1400bab88  jmp     short loc_1400BAB8D
0x1400bab8a  mov     rcx, rbx; pszPath
0x1400bab8d  call    cs:__imp_PathFindExtensionW
0x1400bab94  nop     dword ptr [rax+rax+00h]
0x1400bab99  mov     rcx, rax
0x1400bab9c  lea     rdx, ?SAVED_STATE_FILE_EXTENSION@@3QBGB; ".vsv"
0x1400baba3  call    cs:__imp__o__wcsicmp
0x1400babaa  nop     dword ptr [rax+rax+00h]
0x1400babaf  test    eax, eax
0x1400babb1  jnz     short loc_1400BABD5
0x1400babb3  test    dil, dil
0x1400babb6  jz      short loc_1400BABD1
0x1400babb8  cmp     qword ptr [rbx+18h], 7
0x1400babbd  jbe     short loc_1400BABC2
0x1400babbf  mov     rbx, [rbx]
0x1400babc2  mov     rcx, rbx; this
0x1400babc5  call    ?FileExists@Details@VmRepositoryUtilities@@YA_NPEBG@Z; VmRepositoryUtilities::Details::FileExists(ushort const *)
0x1400babca  test    al, al
0x1400babcc  setnz   al
0x1400babcf  jmp     short loc_1400BABD7
0x1400babd1  mov     al, 1
0x1400babd3  jmp     short loc_1400BABD7
0x1400babd5  xor     al, al
0x1400babd7  mov     rbx, [rsp+28h+arg_0]
0x1400babdc  add     rsp, 20h
0x1400babe0  pop     rdi
0x1400babe1  retn
```
