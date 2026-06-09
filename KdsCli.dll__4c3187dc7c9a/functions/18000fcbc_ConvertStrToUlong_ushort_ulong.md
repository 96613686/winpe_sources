# ConvertStrToUlong(ushort *,ulong *)

- ea: `0x18000fcbc`
- end: `0x18000fd65`
- name: `?ConvertStrToUlong@@YAJPEAGPEAK@Z`
- size: `169`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005a24`
- `0x180007354`

## callees

- `0x18000fcbc`
- `0x18001a450`

## import_xrefs

- `ntdll!RtlUnicodeStringToInteger` at `0x18000fcf8`
- `ntdll!RtlUnicodeStringToInteger` at `0x18000fcf8`
- `ntdll!RtlInitUnicodeString` at `0x18000fce5`
- `ntdll!RtlInitUnicodeString` at `0x18000fce5`

## string_xrefs

- `0x18000fd08`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x18000fd35`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall ConvertStrToUlong(PCWSTR SourceString, unsigned int *a2)
{
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  ULONG v6; // eax
  UNICODE_STRING String; // [rsp+20h] [rbp-18h] BYREF
  ULONG Value; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  String = 0;
  Value = 0;
  RtlInitUnicodeString(&String, SourceString);
  v5 = RtlUnicodeStringToInteger(&String, 0xAu, &Value);
  if ( v5 < 0 )
  {
    v4 = v5;
    SidKeyDebugTraceError(v5, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x44u);
  }
  v6 = Value;
  if ( !Value && *(_DWORD *)SourceString != 48 )
  {
    v4 = -2147467259;
    SidKeyDebugTraceError(
      0x80004005,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
      Value + 76);
    v6 = Value;
  }
  *a2 = v6;
  return v4;
}

```

## disassembly

```asm
0x18000fcbc  mov     rax, rsp
0x18000fcbf  mov     [rax+8], rbx
0x18000fcc3  mov     [rax+18h], rsi
0x18000fcc7  push    rdi
0x18000fcc8  sub     rsp, 30h
0x18000fccc  mov     rsi, rdx
0x18000fccf  mov     rdi, rcx
0x18000fcd2  mov     rdx, rcx; SourceString
0x18000fcd5  xorps   xmm0, xmm0
0x18000fcd8  xor     ebx, ebx
0x18000fcda  lea     rcx, [rax-18h]; DestinationString
0x18000fcde  movups  xmmword ptr [rax-18h], xmm0
0x18000fce2  mov     [rax+10h], ebx
0x18000fce5  call    cs:__imp_RtlInitUnicodeString
0x18000fceb  lea     r8, [rsp+38h+Value]; Value
0x18000fcf0  lea     edx, [rbx+0Ah]; Base
0x18000fcf3  lea     rcx, [rsp+38h+String]; String
0x18000fcf8  call    cs:__imp_RtlUnicodeStringToInteger
0x18000fcfe  test    eax, eax
0x18000fd00  jns     short loc_18000FD1F
0x18000fd02  mov     r9d, 44h ; 'D'; unsigned int
0x18000fd08  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fd0f  lea     rdx, aHr; "hr"
0x18000fd16  mov     ecx, eax; unsigned int
0x18000fd18  mov     ebx, eax
0x18000fd1a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fd1f  mov     eax, [rsp+38h+Value]
0x18000fd23  test    eax, eax
0x18000fd25  jnz     short loc_18000FD51
0x18000fd27  cmp     dword ptr [rdi], 30h ; '0'
0x18000fd2a  jz      short loc_18000FD51
0x18000fd2c  lea     r9d, [rax+4Ch]; unsigned int
0x18000fd30  mov     ecx, 80004005h; unsigned int
0x18000fd35  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fd3c  mov     ebx, 80004005h
0x18000fd41  lea     rdx, aHr; "hr"
0x18000fd48  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fd4d  mov     eax, [rsp+38h+Value]
0x18000fd51  mov     [rsi], eax
0x18000fd53  mov     eax, ebx
0x18000fd55  mov     rbx, [rsp+38h+arg_0]
0x18000fd5a  mov     rsi, [rsp+38h+arg_10]
0x18000fd5f  add     rsp, 30h
0x18000fd63  pop     rdi
0x18000fd64  retn
```
