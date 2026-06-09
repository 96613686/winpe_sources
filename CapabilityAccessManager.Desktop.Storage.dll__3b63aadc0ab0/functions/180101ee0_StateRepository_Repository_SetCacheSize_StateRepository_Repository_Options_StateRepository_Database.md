# StateRepository::Repository::SetCacheSize(StateRepository::Repository::Options,StateRepository::Database &)

- ea: `0x180101ee0`
- end: `0x18010200c`
- name: `?SetCacheSize@Repository@StateRepository@@CAJW4Options@12@AEAVDatabase@2@@Z`
- size: `300`
- prototype: `static int __high(enum StateRepository::Repository::Options, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180102014`

## callees

- `0x180003060`
- `0x1800eabd4`
- `0x1800eabf4`
- `0x1800fbed8`
- `0x180101ee0`
- `0x180104c64`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180101f64`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180101f64`

## string_xrefs

- `0x180101f2b`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180101f73`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180101fb6`: `cache_size`
- `0x180101fd3`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Repository::SetCacheSize(__int64 a1, unsigned int *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  _QWORD *v5; // rdx
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r9
  const char *v9; // r9
  int LastError; // eax
  int v11; // ebx
  _MEMORYSTATUSEX Buffer; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = 0;
  v4 = StateRepository::Globals::PartitionSettings::Get(a2[4]);
  if ( v4 )
    v3 = *(_DWORD *)(v4 + 32);
  if ( !*v5 )
  {
    v6 = -2147019873;
    v7 = 2014;
    v8 = 2147947423LL;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v8,
      Buffer.dwLength);
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v6,
      Buffer.dwLength);
    return (unsigned int)v6;
  }
  if ( !v3 )
  {
    Buffer.dwLength = 64;
    memset(&Buffer.dwMemoryLoad, 0, 60);
    if ( GlobalMemoryStatusEx(&Buffer) )
    {
      v11 = 2;
      if ( (unsigned int)(Buffer.ullTotalPhys >> 30) >= 2 )
      {
        v11 = 16;
        if ( (unsigned int)(Buffer.ullTotalPhys >> 30) < 0x10 )
          v11 = Buffer.ullTotalPhys >> 30;
      }
      v3 = v11 << 10;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7F7,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
                    v9);
      v6 = LastError;
      if ( LastError < 0 )
      {
        v8 = (unsigned int)LastError;
        v7 = 2018;
        goto LABEL_5;
      }
    }
  }
  v6 = StateRepository::Database::SetPragma((StateRepository::Database *)a2, "cache_size", -(__int64)v3);
  if ( v6 < 0 )
    goto LABEL_15;
  return 0;
}

```

## disassembly

```asm
0x180101ee0  mov     [rsp+arg_0], rbx
0x180101ee5  mov     [rsp+arg_10], rsi
0x180101eea  push    rdi
0x180101eeb  sub     rsp, 70h
0x180101eef  mov     rax, cs:__security_cookie
0x180101ef6  xor     rax, rsp
0x180101ef9  mov     [rsp+78h+var_18], rax
0x180101efe  mov     ecx, [rdx+10h]
0x180101f01  mov     rsi, rdx
0x180101f04  xor     ebx, ebx
0x180101f06  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x180101f0b  test    rax, rax
0x180101f0e  jz      short loc_180101F13
0x180101f10  mov     ebx, [rax+20h]
0x180101f13  cmp     qword ptr [rdx], 0
0x180101f17  jnz     short loc_180101F3C
0x180101f19  mov     edi, 8007139Fh
0x180101f1e  mov     edx, 7DEh; void *
0x180101f23  mov     r9d, edi; char *
0x180101f26  mov     rcx, [rsp+78h]; this
0x180101f2b  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180101f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101f37  jmp     loc_180101FCE
0x180101f3c  test    ebx, ebx
0x180101f3e  jnz     short loc_180101FB3
0x180101f40  xorps   xmm0, xmm0
0x180101f43  mov     [rsp+78h+Buffer.dwLength], 40h ; '@'; int
0x180101f4b  movups  xmmword ptr [rsp+78h+Buffer.ullAvailPageFile+4], xmm0
0x180101f50  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x180101f55  movups  xmmword ptr [rsp+78h+Buffer.ullAvailVirtual], xmm0
0x180101f5a  movups  xmmword ptr [rsp+78h+Buffer.dwMemoryLoad], xmm0
0x180101f5f  movups  xmmword ptr [rsp+78h+Buffer.ullAvailPhys+4], xmm0
0x180101f64  call    cs:__imp_GlobalMemoryStatusEx
0x180101f6a  test    eax, eax
0x180101f6c  jnz     short loc_180101F94
0x180101f6e  mov     rcx, [rsp+78h]; this
0x180101f73  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180101f7a  mov     edx, 7F7h; void *
0x180101f7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180101f84  mov     edi, eax
0x180101f86  test    eax, eax
0x180101f88  jns     short loc_180101FB3
0x180101f8a  mov     r9d, eax
0x180101f8d  mov     edx, 7E2h
0x180101f92  jmp     short loc_180101F26
0x180101f94  mov     rax, [rsp+78h+Buffer.ullTotalPhys]
0x180101f99  mov     ebx, 2
0x180101f9e  shr     rax, 1Eh
0x180101fa2  cmp     eax, ebx
0x180101fa4  jb      short loc_180101FB0
0x180101fa6  mov     ebx, 10h
0x180101fab  cmp     eax, ebx
0x180101fad  cmovb   ebx, eax
0x180101fb0  shl     ebx, 0Ah
0x180101fb3  mov     r8d, ebx
0x180101fb6  lea     rdx, aCacheSize; "cache_size"
0x180101fbd  neg     r8; __int64
0x180101fc0  mov     rcx, rsi; this
0x180101fc3  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x180101fc8  mov     edi, eax
0x180101fca  test    eax, eax
0x180101fcc  jns     short loc_180101FEB
0x180101fce  mov     rcx, [rsp+78h]; this
0x180101fd3  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101fda  mov     r9d, edi; char *
0x180101fdd  mov     edx, 60Ch; void *
0x180101fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101fe7  mov     eax, edi
0x180101fe9  jmp     short loc_180101FED
0x180101feb  xor     eax, eax
0x180101fed  mov     rcx, [rsp+78h+var_18]
0x180101ff2  xor     rcx, rsp; StackCookie
0x180101ff5  call    __security_check_cookie
0x180101ffa  lea     r11, [rsp+78h+var_8]
0x180101fff  mov     rbx, [r11+10h]
0x180102003  mov     rsi, [r11+20h]
0x180102007  mov     rsp, r11
0x18010200a  pop     rdi
0x18010200b  retn
```
