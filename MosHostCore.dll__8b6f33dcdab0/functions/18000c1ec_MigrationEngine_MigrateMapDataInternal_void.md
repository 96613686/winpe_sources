# MigrationEngine::MigrateMapDataInternal(void)

- ea: `0x18000c1ec`
- end: `0x18000c347`
- name: `?MigrateMapDataInternal@MigrationEngine@@AEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(MigrationEngine *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b6f4`
- `0x18000bf38`

## callees

- `0x180008e00`
- `0x18000b170`
- `0x18000c1ec`
- `0x18001f6cc`

## import_xrefs

- `MosStorage!MosStorageEnsureMapDataDirectoryAndKeepFileHandle` at `0x18000c2b5`
- `MosStorage!MosStorageEnsureMapDataDirectoryAndKeepFileHandle` at `0x18000c2b5`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c326`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c326`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c283`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c283`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c22a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c22a`

## string_xrefs

- `0x18000c243`: `BitsTemp`
- `0x18000c264`: `[Migration] Copying data from %ls to %ls`

## pseudocode

```c
__int64 __fastcall MigrationEngine::MigrateMapDataInternal(MigrationEngine *this)
{
  unsigned int v2; // edi
  const unsigned __int16 *v3; // rsi
  const unsigned __int16 *v4; // rbp
  int v5; // eax
  int v6; // r8d
  void *v8; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v9; // [rsp+68h] [rbp+10h] BYREF

  *((_DWORD *)this + 829) = 60;
  if ( ((*((_DWORD *)this + 828) - 2) & 0xFFFFFFFD) == 0 )
  {
    v2 = 0;
    if ( (*((_BYTE *)this + 8) & 1) == 0 )
      return v2;
    v9 = L"BitsTemp";
    v3 = (const unsigned __int16 *)((char *)this + 1676);
    v4 = (const unsigned __int16 *)((char *)this + 28);
    ZTraceHelper(
      3,
      "MigrationEngine::MigrateMapDataInternal",
      294,
      this,
      "[Migration] Copying data from %ls to %ls",
      (const wchar_t *)this + 14,
      (const wchar_t *)this + 838);
    *((_DWORD *)this + 829) = 70;
    v8 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v8,
      0);
    v5 = MosStorageEnsureMapDataDirectoryAndKeepFileHandle(v3, *((_DWORD *)this + 417) != 0, &v8);
    if ( v5 >= 0 )
    {
      *((_DWORD *)this + 829) = 80;
      v5 = CopyDirectory(
             v4,
             v3,
             1,
             &v9,
             MigrationEngine::s_CopyProgressCallback,
             this,
             (LPBOOL)this + 831,
             lambda_964897154a50d9304c6beff2e370e409_::_lambda_invoker_cdecl_);
      if ( v5 >= 0 )
      {
LABEL_9:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
        return v2;
      }
      v6 = 312;
    }
    else
    {
      v6 = 301;
    }
    v2 = ZTraceReportPropagation(v5, "MigrationEngine::MigrateMapDataInternal", v6, this);
    goto LABEL_9;
  }
  return (unsigned int)ZTraceReportOrigination(-2147019873, "MigrationEngine::MigrateMapDataInternal", 280, this);
}

```

## disassembly

```asm
0x18000c1ec  mov     [rsp+arg_10], rbx
0x18000c1f1  push    rbp
0x18000c1f2  push    rsi
0x18000c1f3  push    rdi
0x18000c1f4  sub     rsp, 40h
0x18000c1f8  mov     rbx, rcx
0x18000c1fb  mov     dword ptr [rcx+0CF4h], 3Ch ; '<'
0x18000c205  mov     eax, [rcx+0CF0h]
0x18000c20b  sub     eax, 2
0x18000c20e  test    eax, 0FFFFFFFDh
0x18000c213  jz      short loc_18000C237
0x18000c215  mov     r9, rcx
0x18000c218  mov     r8d, 118h
0x18000c21e  lea     rdx, aMigrationengin_11; "MigrationEngine::MigrateMapDataInternal"
0x18000c225  mov     ecx, 8007139Fh
0x18000c22a  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000c230  mov     edi, eax
0x18000c232  jmp     loc_18000C338
0x18000c237  xor     edi, edi
0x18000c239  test    byte ptr [rcx+8], 1
0x18000c23d  jz      loc_18000C338
0x18000c243  lea     rax, aBitstemp; "BitsTemp"
0x18000c24a  mov     [rsp+58h+arg_8], rax
0x18000c24f  lea     rsi, [rcx+68Ch]
0x18000c256  lea     rbp, [rcx+1Ch]
0x18000c25a  mov     [rsp+58h+pbCancel], rsi
0x18000c25f  mov     [rsp+58h+lpData], rbp
0x18000c264  lea     rax, aMigrationCopyi; "[Migration] Copying data from %ls to %l"...
0x18000c26b  mov     [rsp+58h+var_38], rax
0x18000c270  mov     r9, rbx
0x18000c273  mov     r8d, 126h
0x18000c279  lea     rdx, aMigrationengin_11; "MigrationEngine::MigrateMapDataInternal"
0x18000c280  lea     ecx, [rdi+3]
0x18000c283  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000c289  mov     dword ptr [rbx+0CF4h], 46h ; 'F'
0x18000c293  mov     [rsp+58h+arg_0], rdi
0x18000c298  xor     edx, edx
0x18000c29a  lea     rcx, [rsp+58h+arg_0]
0x18000c29f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000c2a4  cmp     [rbx+684h], edi
0x18000c2aa  setnz   dl
0x18000c2ad  lea     r8, [rsp+58h+arg_0]
0x18000c2b2  mov     rcx, rsi
0x18000c2b5  call    cs:__imp_?MosStorageEnsureMapDataDirectoryAndKeepFileHandle@@YAJPEBG_NPEAPEAX@Z; MosStorageEnsureMapDataDirectoryAndKeepFileHandle(ushort const *,bool,void * *)
0x18000c2bb  test    eax, eax
0x18000c2bd  jns     short loc_18000C2C7
0x18000c2bf  mov     r8d, 12Dh
0x18000c2c5  jmp     short loc_18000C31A
0x18000c2c7  mov     dword ptr [rbx+0CF4h], 50h ; 'P'
0x18000c2d1  lea     rax, [rbx+0CFCh]
0x18000c2d8  lea     rcx, _lambda_964897154a50d9304c6beff2e370e409____lambda_invoker_cdecl_
0x18000c2df  mov     [rsp+58h+var_20], rcx; void (*)(void *)
0x18000c2e4  mov     [rsp+58h+pbCancel], rax; pbCancel
0x18000c2e9  mov     [rsp+58h+lpData], rbx; lpData
0x18000c2ee  lea     rax, ?s_CopyProgressCallback@MigrationEngine@@CAKT_LARGE_INTEGER@@000KKPEAX11@Z; MigrationEngine::s_CopyProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)
0x18000c2f5  mov     [rsp+58h+var_38], rax; unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *)
0x18000c2fa  lea     r9, [rsp+58h+arg_8]; unsigned __int16 **
0x18000c2ff  mov     r8d, 1; unsigned int
0x18000c305  mov     rdx, rsi; unsigned __int16 *
0x18000c308  mov     rcx, rbp; unsigned __int16 *
0x18000c30b  call    ?CopyDirectory@@YAJPEBG0KPEAPEBGP6AKT_LARGE_INTEGER@@222KKPEAX33@Z3PEAHP6AX3@Z@Z; CopyDirectory(ushort const *,ushort const *,ulong,ushort const * *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,void (*)(void *))
0x18000c310  test    eax, eax
0x18000c312  jns     short loc_18000C32E
0x18000c314  mov     r8d, 138h
0x18000c31a  mov     r9, rbx
0x18000c31d  lea     rdx, aMigrationengin_11; "MigrationEngine::MigrateMapDataInternal"
0x18000c324  mov     ecx, eax
0x18000c326  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c32c  mov     edi, eax
0x18000c32e  lea     rcx, [rsp+58h+arg_0]
0x18000c333  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000c338  mov     eax, edi
0x18000c33a  mov     rbx, [rsp+58h+arg_10]
0x18000c33f  add     rsp, 40h
0x18000c343  pop     rdi
0x18000c344  pop     rsi
0x18000c345  pop     rbp
0x18000c346  retn
```
