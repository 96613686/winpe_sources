# ShaderDiskCacheSQLite::DeleteCacheFiles(ushort const *)

- ea: `0x180049838`
- end: `0x180049966`
- name: `?DeleteCacheFiles@ShaderDiskCacheSQLite@@QEAAJPEBG@Z`
- size: `302`
- prototype: `__int64 __fastcall(ShaderDiskCacheSQLite *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800434e0`
- `0x18005063c`
- `0x1800a74e5`

## callees

- `0x1800416c4`
- `0x1800495f8`
- `0x180049838`
- `0x18004eff0`
- `0x1800a6ccc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180049945`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180049945`

## pseudocode

```c
__int64 __fastcall ShaderDiskCacheSQLite::DeleteCacheFiles(ShaderDiskCacheSQLite *this, const unsigned __int16 *a2)
{
  if ( *((_QWORD *)this + 1) )
    ShaderDiskCacheSQLite::ClearCache(this);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 88,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 72,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 80,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 16,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 24,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 32,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 96,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 104,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 112,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 120,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 128,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 136,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(
    (char *)this + 144,
    0);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,int (sqlite3 *),&int sqlite3_close_v2(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>::reset(
    (char *)this + 8,
    0);
  if ( !wcscmp_0(a2, L":memory:") )
    return 1;
  else
    return !DeleteFileW(a2) ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180049838  mov     [rsp+arg_0], rbx
0x18004983d  mov     [rsp+arg_8], rsi
0x180049842  push    rdi
0x180049843  sub     rsp, 20h
0x180049847  cmp     qword ptr [rcx+8], 0
0x18004984c  mov     rdi, rdx
0x18004984f  mov     rbx, rcx
0x180049852  jz      short loc_180049859
0x180049854  call    ?ClearCache@ShaderDiskCacheSQLite@@QEAAJXZ; ShaderDiskCacheSQLite::ClearCache(void)
0x180049859  lea     rcx, [rbx+58h]
0x18004985d  xor     edx, edx
0x18004985f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x180049864  lea     rcx, [rbx+28h]
0x180049868  xor     edx, edx
0x18004986a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x18004986f  lea     rcx, [rbx+30h]
0x180049873  xor     edx, edx
0x180049875  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x18004987a  lea     rcx, [rbx+38h]
0x18004987e  xor     edx, edx
0x180049880  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x180049885  lea     rcx, [rbx+40h]
0x180049889  xor     edx, edx
0x18004988b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x180049890  lea     rcx, [rbx+48h]
0x180049894  xor     edx, edx
0x180049896  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x18004989b  lea     rcx, [rbx+50h]
0x18004989f  xor     edx, edx
0x1800498a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498a6  lea     rcx, [rbx+10h]
0x1800498aa  xor     edx, edx
0x1800498ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498b1  lea     rcx, [rbx+18h]
0x1800498b5  xor     edx, edx
0x1800498b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498bc  lea     rcx, [rbx+20h]
0x1800498c0  xor     edx, edx
0x1800498c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498c7  lea     rcx, [rbx+60h]
0x1800498cb  xor     edx, edx
0x1800498cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498d2  lea     rcx, [rbx+68h]
0x1800498d6  xor     edx, edx
0x1800498d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498dd  lea     rcx, [rbx+70h]
0x1800498e1  xor     edx, edx
0x1800498e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498e8  lea     rcx, [rbx+78h]
0x1800498ec  xor     edx, edx
0x1800498ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x1800498f3  lea     rcx, [rbx+80h]
0x1800498fa  xor     edx, edx
0x1800498fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x180049901  lea     rcx, [rbx+88h]
0x180049908  xor     edx, edx
0x18004990a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x18004990f  lea     rcx, [rbx+90h]
0x180049916  xor     edx, edx
0x180049918  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AHPEAU1@@Z$1?sqlite3_finalize@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3_stmt@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::reset(sqlite3_stmt *)
0x18004991d  xor     edx, edx
0x18004991f  lea     rcx, [rbx+8]
0x180049923  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AHPEAU1@@Z$1?sqlite3_close_v2@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,int (sqlite3 *),&sqlite3_close_v2(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>::reset(sqlite3 *)
0x180049928  lea     rdx, aMemory_0; ":memory:"
0x18004992f  mov     rcx, rdi; String1
0x180049932  call    wcscmp_0
0x180049937  test    eax, eax
0x180049939  jnz     short loc_180049942
0x18004993b  mov     eax, 1
0x180049940  jmp     short loc_180049956
0x180049942  mov     rcx, rdi; lpFileName
0x180049945  call    cs:__imp_DeleteFileW
0x18004994b  neg     eax
0x18004994d  sbb     eax, eax
0x18004994f  not     eax
0x180049951  and     eax, 80004005h
0x180049956  mov     rbx, [rsp+28h+arg_0]
0x18004995b  mov     rsi, [rsp+28h+arg_8]
0x180049960  add     rsp, 20h
0x180049964  pop     rdi
0x180049965  retn
```
