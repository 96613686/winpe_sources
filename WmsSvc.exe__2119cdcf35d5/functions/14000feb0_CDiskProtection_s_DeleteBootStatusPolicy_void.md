# CDiskProtection::s_DeleteBootStatusPolicy(void)

- ea: `0x14000feb0`
- end: `0x140010077`
- name: `?s_DeleteBootStatusPolicy@CDiskProtection@@KAJXZ`
- size: `455`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009778`
- `0x140013794`

## callees

- `0x14000feb0`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000ff25`
- `KERNEL32!IsDebuggerPresent` at `0x14000ffff`
- `KERNEL32!IsDebuggerPresent` at `0x14000ff25`
- `KERNEL32!IsDebuggerPresent` at `0x14000ffff`
- `bcd!BcdOpenObject` at `0x14000ff84`
- `bcd!BcdOpenObject` at `0x14000ff84`
- `bcd!BcdCloseObject` at `0x14001004b`
- `bcd!BcdCloseObject` at `0x14001004b`
- `bcd!BcdDeleteElement` at `0x14000ffa7`
- `bcd!BcdDeleteElement` at `0x14000ffa7`
- `bcd!BcdCloseStore` at `0x14001005b`
- `bcd!BcdCloseStore` at `0x14001005b`
- `bcd!BcdOpenSystemStore` at `0x14000fed8`
- `bcd!BcdOpenSystemStore` at `0x14000fed8`

## string_xrefs

- `0x14000fef2`: `CDiskProtection::s_DeleteBootStatusPolicy`
- `0x14000ffcd`: `CDiskProtection::s_DeleteBootStatusPolicy`

## pseudocode

```c
__int64 CDiskProtection::s_DeleteBootStatusPolicy(void)
{
  int v0; // ebx
  unsigned int v1; // r15d
  unsigned int v2; // ebx
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp-28h]
  unsigned int v6; // [rsp+30h] [rbp-28h]
  unsigned int v7; // [rsp+38h] [rbp-20h]
  unsigned int v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  v9 = 0;
  v0 = BcdOpenSystemStore(&v10);
  if ( v0 )
  {
    v1 = 4858;
    goto LABEL_3;
  }
  v0 = BcdOpenObject(v10, &GUID_CURRENT_BOOT_ENTRY, &v9);
  if ( v0 )
  {
    v1 = 4863;
LABEL_3:
    v2 = v0 | 0x10000000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v1,
      L"CDiskProtection::s_DeleteBootStatusPolicy",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v2);
    if ( IsDebuggerPresent() )
    {
      v7 = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v1,
        L"CDiskProtection::s_DeleteBootStatusPolicy",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        v7);
    }
    else
    {
      v5 = v2;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v1,
        L"CDiskProtection::s_DeleteBootStatusPolicy",
        L"CBRAEx",
        L"status == ((NTSTATUS)0x00000000L)",
        v5);
    }
    goto LABEL_14;
  }
  v2 = 0;
  v3 = BcdDeleteElement(v9, 620757216);
  if ( v3 && v3 != -1073741275 )
  {
    v2 = v3 | 0x10000000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x1307u,
      L"CDiskProtection::s_DeleteBootStatusPolicy",
      L"CBRAEx",
      L"(status == ((NTSTATUS)0x00000000L)) || (status == ((NTSTATUS)0xC0000225L))",
      v3 | 0x10000000);
    if ( IsDebuggerPresent() )
    {
      v8 = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        4871,
        L"CDiskProtection::s_DeleteBootStatusPolicy",
        L"CBRAEx",
        L"(status == ((NTSTATUS)0x00000000L)) || (status == ((NTSTATUS)0xC0000225L))",
        v8);
    }
    else
    {
      v6 = v2;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        4871,
        L"CDiskProtection::s_DeleteBootStatusPolicy",
        L"CBRAEx",
        L"(status == ((NTSTATUS)0x00000000L)) || (status == ((NTSTATUS)0xC0000225L))",
        v6);
    }
  }
LABEL_14:
  if ( v9 )
    BcdCloseObject();
  if ( v10 )
    BcdCloseStore();
  return v2;
}

```

## disassembly

```asm
0x14000feb0  mov     rax, rsp
0x14000feb3  mov     [rax+18h], rbx
0x14000feb7  mov     [rax+20h], rbp
0x14000febb  push    rsi
0x14000febc  push    r14
0x14000febe  push    r15
0x14000fec0  sub     rsp, 40h
0x14000fec4  lea     rcx, [rax+10h]
0x14000fec8  mov     qword ptr [rax+10h], 0
0x14000fed0  mov     qword ptr [rax+8], 0
0x14000fed8  call    cs:__imp_BcdOpenSystemStore
0x14000fede  mov     ebx, eax
0x14000fee0  test    eax, eax
0x14000fee2  jz      loc_14000FF73
0x14000fee8  mov     r15d, 12FAh
0x14000feee  bts     ebx, 1Ch
0x14000fef2  lea     rsi, aCdiskprotectio_110; "CDiskProtection::s_DeleteBootStatusPoli"...
0x14000fef9  lea     rbp, aCbraex; "CBRAEx"
0x14000ff00  mov     [rsp+58h+var_30], ebx; int
0x14000ff04  lea     r14, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x14000ff0b  mov     r8, rsi; unsigned __int16 *
0x14000ff0e  mov     r9, rbp; unsigned __int16 *
0x14000ff11  mov     [rsp+58h+var_38], r14; unsigned __int16 *
0x14000ff16  mov     edx, r15d; unsigned int
0x14000ff19  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000ff20  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ff25  call    cs:__imp_IsDebuggerPresent
0x14000ff2b  test    eax, eax
0x14000ff2d  jz      short loc_14000FF62
0x14000ff2f  mov     [rsp+58h+var_20], ebx
0x14000ff33  mov     r9d, r15d
0x14000ff36  mov     [rsp+58h+var_28], r14
0x14000ff3b  mov     qword ptr [rsp+58h+var_30], rbp
0x14000ff40  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000ff47  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000ff4e  mov     [rsp+58h+var_38], rsi
0x14000ff53  mov     ecx, 2; unsigned __int8
0x14000ff58  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000ff5d  jmp     loc_140010041
0x14000ff62  mov     dword ptr [rsp+58h+var_28], ebx
0x14000ff66  mov     r8d, r15d
0x14000ff69  mov     qword ptr [rsp+58h+var_30], r14
0x14000ff6e  jmp     loc_140010026
0x14000ff73  mov     rcx, [rsp+58h+arg_8]
0x14000ff78  lea     r8, [rsp+58h+arg_0]
0x14000ff7d  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x14000ff84  call    cs:__imp_BcdOpenObject
0x14000ff8a  mov     ebx, eax
0x14000ff8c  test    eax, eax
0x14000ff8e  jz      short loc_14000FF9B
0x14000ff90  mov     r15d, 12FFh
0x14000ff96  jmp     loc_14000FEEE
0x14000ff9b  mov     rcx, [rsp+58h+arg_0]
0x14000ffa0  mov     edx, 250000E0h
0x14000ffa5  xor     ebx, ebx
0x14000ffa7  call    cs:__imp_BcdDeleteElement
0x14000ffad  test    eax, eax
0x14000ffaf  jz      loc_140010041
0x14000ffb5  cmp     eax, 0C0000225h
0x14000ffba  jz      loc_140010041
0x14000ffc0  mov     ebx, eax
0x14000ffc2  lea     rbp, aCbraex; "CBRAEx"
0x14000ffc9  bts     ebx, 1Ch
0x14000ffcd  lea     rsi, aCdiskprotectio_110; "CDiskProtection::s_DeleteBootStatusPoli"...
0x14000ffd4  mov     r14d, 1307h
0x14000ffda  mov     [rsp+58h+var_30], ebx; int
0x14000ffde  lea     r15, aStatusNtstatus; "(status == ((NTSTATUS)0x00000000L)) || "...
0x14000ffe5  mov     r9, rbp; unsigned __int16 *
0x14000ffe8  mov     r8, rsi; unsigned __int16 *
0x14000ffeb  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x14000fff0  mov     edx, r14d; unsigned int
0x14000fff3  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000fffa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ffff  call    cs:__imp_IsDebuggerPresent
0x140010005  test    eax, eax
0x140010007  jz      short loc_14001001A
0x140010009  mov     [rsp+58h+var_20], ebx
0x14001000d  mov     r9d, r14d
0x140010010  mov     [rsp+58h+var_28], r15
0x140010015  jmp     loc_14000FF3B
0x14001001a  mov     dword ptr [rsp+58h+var_28], ebx
0x14001001e  mov     r8d, r14d
0x140010021  mov     qword ptr [rsp+58h+var_30], r15
0x140010026  mov     r9, rsi
0x140010029  mov     [rsp+58h+var_38], rbp
0x14001002e  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140010035  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001003c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140010041  mov     rcx, [rsp+58h+arg_0]
0x140010046  test    rcx, rcx
0x140010049  jz      short loc_140010051
0x14001004b  call    cs:__imp_BcdCloseObject
0x140010051  mov     rcx, [rsp+58h+arg_8]
0x140010056  test    rcx, rcx
0x140010059  jz      short loc_140010061
0x14001005b  call    cs:__imp_BcdCloseStore
0x140010061  mov     rbp, [rsp+58h+arg_18]
0x140010066  mov     eax, ebx
0x140010068  mov     rbx, [rsp+58h+arg_10]
0x14001006d  add     rsp, 40h
0x140010071  pop     r15
0x140010073  pop     r14
0x140010075  pop     rsi
0x140010076  retn
```
