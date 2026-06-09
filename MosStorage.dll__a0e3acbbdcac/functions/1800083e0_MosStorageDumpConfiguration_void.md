# MosStorageDumpConfiguration(void)

- ea: `0x1800083e0`
- end: `0x180008541`
- name: `?MosStorageDumpConfiguration@@YAJXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001c80`
- `0x180002802`
- `0x18000832c`
- `0x1800083e0`
- `0x180008a20`
- `0x180008ac0`
- `0x180008f60`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008473`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008473`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000844f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000849c`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800084dc`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008518`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000844f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000849c`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800084dc`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x180008518`

## string_xrefs

- `0x180008436`: `MosStorageDumpConfiguration`
- `0x18000848b`: `[MosHost] using data directory: %S`
- `0x1800084cb`: `[MosHost] using resource directory: %S`
- `0x180008502`: `[MosHost] using browse cache size: %d MB`

## pseudocode

```c
__int64 MosStorageDumpConfiguration(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  char v4; // al
  const char *v5; // rcx
  int DataDirectory; // eax
  int v7; // r8d
  unsigned int v9[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(pszPathOut, 0, 0x208u);
  v0 = 0;
  v9[0] = 0;
  v4 = IsExternalStoragePreferred(v2, v1, v3);
  v5 = "true";
  if ( !v4 )
    v5 = "false";
  ZTraceHelperNoThis(3, "MosStorageDumpConfiguration", 1056, "[MosHost] external storage is preferred: %s", v5);
  DataDirectory = MosStorageGetDataDirectory(pszPathOut, 0x104u);
  if ( DataDirectory >= 0 )
  {
    ZTraceHelperNoThis(3, "MosStorageDumpConfiguration", 1059, "[MosHost] using data directory: %S", pszPathOut);
    DataDirectory = MosStorageGetResourceDirectory(pszPathOut, 0x104u);
    if ( DataDirectory >= 0 )
    {
      ZTraceHelperNoThis(3, "MosStorageDumpConfiguration", 1062, "[MosHost] using resource directory: %S", pszPathOut);
      DataDirectory = MosStorageGetBrowseCacheSizeInMBytes(v9);
      if ( DataDirectory >= 0 )
      {
        ZTraceHelperNoThis(3, "MosStorageDumpConfiguration", 1065, "[MosHost] using browse cache size: %d MB", v9[0]);
        return v0;
      }
      v7 = 1064;
    }
    else
    {
      v7 = 1061;
    }
  }
  else
  {
    v7 = 1058;
  }
  return (unsigned int)ZTraceReportPropagationNoThis(DataDirectory, "MosStorageDumpConfiguration", v7);
}

```

## disassembly

```asm
0x1800083e0  mov     [rsp+arg_0], rbx
0x1800083e5  push    rdi
0x1800083e6  sub     rsp, 260h
0x1800083ed  mov     rax, cs:__security_cookie
0x1800083f4  xor     rax, rsp
0x1800083f7  mov     [rsp+268h+var_18], rax
0x1800083ff  xor     edx, edx; Val
0x180008401  lea     rcx, [rsp+268h+pszPathOut]; void *
0x180008406  mov     r8d, 208h; Size
0x18000840c  call    memset_0
0x180008411  xor     ebx, ebx
0x180008413  mov     [rsp+268h+var_238], ebx
0x180008417  call    IsExternalStoragePreferred
0x18000841c  test    al, al
0x18000841e  lea     rdx, aFalse; "false"
0x180008425  lea     rcx, aTrue; "true"
0x18000842c  mov     r8d, 420h
0x180008432  cmovz   rcx, rdx
0x180008436  lea     rdi, aMosstoragedump_0; "MosStorageDumpConfiguration"
0x18000843d  mov     [rsp+268h+var_248], rcx
0x180008442  lea     r9, aMoshostExterna; "[MosHost] external storage is preferred"...
0x180008449  lea     ecx, [rbx+3]
0x18000844c  mov     rdx, rdi
0x18000844f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008455  mov     edx, 104h; cchPathOut
0x18000845a  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x18000845f  call    ?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180008464  mov     rdx, rdi
0x180008467  test    eax, eax
0x180008469  jns     short loc_180008480
0x18000846b  mov     r8d, 422h
0x180008471  mov     ecx, eax
0x180008473  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008479  mov     ebx, eax
0x18000847b  jmp     loc_18000851E
0x180008480  lea     rax, [rsp+268h+pszPathOut]
0x180008485  mov     r8d, 423h
0x18000848b  lea     r9, aMoshostUsingDa; "[MosHost] using data directory: %S"
0x180008492  mov     [rsp+268h+var_248], rax
0x180008497  mov     ecx, 3
0x18000849c  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800084a2  mov     edx, 104h; cchPathOut
0x1800084a7  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x1800084ac  call    ?MosStorageGetResourceDirectory@@YAJPEAGK@Z; MosStorageGetResourceDirectory(ushort *,ulong)
0x1800084b1  mov     rdx, rdi
0x1800084b4  test    eax, eax
0x1800084b6  jns     short loc_1800084C0
0x1800084b8  mov     r8d, 425h
0x1800084be  jmp     short loc_180008471
0x1800084c0  lea     rax, [rsp+268h+pszPathOut]
0x1800084c5  mov     r8d, 426h
0x1800084cb  lea     r9, aMoshostUsingRe; "[MosHost] using resource directory: %S"
0x1800084d2  mov     [rsp+268h+var_248], rax
0x1800084d7  mov     ecx, 3
0x1800084dc  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800084e2  lea     rcx, [rsp+268h+var_238]; unsigned int *
0x1800084e7  call    ?MosStorageGetBrowseCacheSizeInMBytes@@YAJPEAK@Z; MosStorageGetBrowseCacheSizeInMBytes(ulong *)
0x1800084ec  mov     rdx, rdi
0x1800084ef  test    eax, eax
0x1800084f1  jns     short loc_1800084FE
0x1800084f3  mov     r8d, 428h
0x1800084f9  jmp     loc_180008471
0x1800084fe  mov     eax, [rsp+268h+var_238]
0x180008502  lea     r9, aMoshostUsingBr; "[MosHost] using browse cache size: %d M"...
0x180008509  mov     r8d, 429h
0x18000850f  mov     dword ptr [rsp+268h+var_248], eax
0x180008513  mov     ecx, 3
0x180008518  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000851e  mov     eax, ebx
0x180008520  mov     rcx, [rsp+268h+var_18]
0x180008528  xor     rcx, rsp; StackCookie
0x18000852b  call    __security_check_cookie
0x180008530  mov     rbx, [rsp+268h+arg_0]
0x180008538  add     rsp, 260h
0x18000853f  pop     rdi
0x180008540  retn
```
