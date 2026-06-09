# ComUtils::MpGetReportingGuid

- ea: `0x180005e30`
- end: `0x180005f0c`
- name: `ComUtils::MpGetReportingGuid`
- size: `220`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005cd8`

## callees

- `0x180005e30`

## import_xrefs

- `mpclient!MpFreeMemory` at `0x180005ebf`
- `mpclient!MpFreeMemory` at `0x180005eed`
- `mpclient!MpFreeMemory` at `0x180005ebf`
- `mpclient!MpFreeMemory` at `0x180005eed`
- `mpclient!MpConfigGetValueAlloc` at `0x180005eaa`
- `mpclient!MpConfigGetValueAlloc` at `0x180005eaa`
- `mpclient!MpConfigClose` at `0x180005e66`
- `mpclient!MpConfigClose` at `0x180005efc`
- `mpclient!MpConfigClose` at `0x180005e66`
- `mpclient!MpConfigClose` at `0x180005efc`
- `mpclient!MpConfigOpen` at `0x180005e51`
- `mpclient!MpConfigOpen` at `0x180005e51`
- `RPCRT4!UuidFromStringW` at `0x180005ece`
- `RPCRT4!UuidFromStringW` at `0x180005ece`

## pseudocode

```c
__int64 __fastcall ComUtils::MpGetReportingGuid(UUID *Uuid)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int ValueAlloc; // eax
  RPC_WSTR v7; // rcx
  RPC_STATUS v8; // eax
  unsigned int v9; // ecx
  int v10; // eax
  bool v11; // sf
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  v2 = MpConfigOpen(L".", &v15);
  v3 = v15;
  v4 = v2;
  if ( v2 < 0 )
  {
LABEL_2:
    if ( v3 )
      MpConfigClose();
    return v4;
  }
  StringUuid[0] = 0;
  v14 = 2;
  v13 = 0;
  ValueAlloc = MpConfigGetValueAlloc(v15, L"ReportingGUID", &v14, &v13, StringUuid, 0);
  v7 = StringUuid[0];
  v4 = ValueAlloc;
  if ( ValueAlloc < 0
    || (v8 = UuidFromStringW(StringUuid[0], Uuid),
        v9 = v8 | 0x80010000,
        v10 = -v8,
        v11 = ((v10 != 0 ? v9 : 0) & 0x80000000) != 0,
        v4 = v10 != 0 ? v9 : 0,
        v7 = StringUuid[0],
        v11) )
  {
    if ( v7 )
      MpFreeMemory(v7);
    v3 = v15;
    goto LABEL_2;
  }
  if ( StringUuid[0] )
    MpFreeMemory(StringUuid[0]);
  if ( v15 )
    MpConfigClose();
  return 0;
}

```

## disassembly

```asm
0x180005e30  push    rbp
0x180005e32  push    rbx
0x180005e33  push    rdi
0x180005e34  mov     rbp, rsp
0x180005e37  sub     rsp, 40h
0x180005e3b  mov     rdi, rcx
0x180005e3e  mov     [rbp+arg_18], 0
0x180005e46  lea     rcx, asc_18000D420; "."
0x180005e4d  lea     rdx, [rbp+arg_18]
0x180005e51  call    cs:__imp_MpConfigOpen
0x180005e57  mov     rcx, [rbp+arg_18]
0x180005e5b  mov     ebx, eax
0x180005e5d  test    eax, eax
0x180005e5f  jns     short loc_180005E73
0x180005e61  test    rcx, rcx
0x180005e64  jz      short loc_180005E6C
0x180005e66  call    cs:__imp_MpConfigClose
0x180005e6c  mov     eax, ebx
0x180005e6e  jmp     loc_180005F04
0x180005e73  mov     [rbp+StringUuid], 0
0x180005e7b  mov     [rbp+arg_10], 2
0x180005e82  mov     [rbp+arg_8], 0
0x180005e89  lea     rax, [rbp+StringUuid]
0x180005e8d  mov     [rsp+40h+var_18], 0
0x180005e96  lea     r9, [rbp+arg_8]
0x180005e9a  mov     [rsp+40h+var_20], rax
0x180005e9f  lea     r8, [rbp+arg_10]
0x180005ea3  lea     rdx, aReportingguid; "ReportingGUID"
0x180005eaa  call    cs:__imp_MpConfigGetValueAlloc
0x180005eb0  mov     rcx, [rbp+StringUuid]; StringUuid
0x180005eb4  mov     ebx, eax
0x180005eb6  test    eax, eax
0x180005eb8  jns     short loc_180005ECB
0x180005eba  test    rcx, rcx
0x180005ebd  jz      short loc_180005EC5
0x180005ebf  call    cs:__imp_MpFreeMemory
0x180005ec5  mov     rcx, [rbp+arg_18]
0x180005ec9  jmp     short loc_180005E61
0x180005ecb  mov     rdx, rdi; Uuid
0x180005ece  call    cs:__imp_UuidFromStringW
0x180005ed4  mov     ecx, eax
0x180005ed6  or      ecx, 80010000h
0x180005edc  neg     eax
0x180005ede  sbb     ebx, ebx
0x180005ee0  and     ebx, ecx
0x180005ee2  mov     rcx, [rbp+StringUuid]
0x180005ee6  jl      short loc_180005EBA
0x180005ee8  test    rcx, rcx
0x180005eeb  jz      short loc_180005EF3
0x180005eed  call    cs:__imp_MpFreeMemory
0x180005ef3  mov     rcx, [rbp+arg_18]
0x180005ef7  test    rcx, rcx
0x180005efa  jz      short loc_180005F02
0x180005efc  call    cs:__imp_MpConfigClose
0x180005f02  xor     eax, eax
0x180005f04  add     rsp, 40h
0x180005f08  pop     rdi
0x180005f09  pop     rbx
0x180005f0a  pop     rbp
0x180005f0b  retn
```
