# CDiskProtection::s_ModifyBootStatusPolicy(void)

- ea: `0x140012788`
- end: `0x1400128eb`
- name: `?s_ModifyBootStatusPolicy@CDiskProtection@@KAJXZ`
- size: `355`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009af0`
- `0x14000b980`

## callees

- `0x140012788`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14001285c`
- `KERNEL32!IsDebuggerPresent` at `0x14001285c`
- `bcd!BcdOpenObject` at `0x1400127d7`
- `bcd!BcdOpenObject` at `0x1400127d7`
- `bcd!BcdSetElementData` at `0x14001280f`
- `bcd!BcdSetElementData` at `0x14001280f`
- `bcd!BcdCloseObject` at `0x1400128c7`
- `bcd!BcdCloseObject` at `0x1400128c7`
- `bcd!BcdCloseStore` at `0x1400128d7`
- `bcd!BcdCloseStore` at `0x1400128d7`
- `bcd!BcdOpenSystemStore` at `0x1400127b2`
- `bcd!BcdOpenSystemStore` at `0x1400127b2`

## pseudocode

```c
__int64 CDiskProtection::s_ModifyBootStatusPolicy(void)
{
  int v0; // ebx
  unsigned int v1; // r12d
  unsigned int v2; // ebx
  int v3; // eax
  unsigned int v5; // [rsp+30h] [rbp-38h]
  unsigned int v6; // [rsp+38h] [rbp-30h]
  __int64 v7; // [rsp+70h] [rbp+8h] BYREF
  __int64 v8; // [rsp+78h] [rbp+10h] BYREF
  __int64 v9; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  v9 = 0;
  v0 = BcdOpenSystemStore(&v8);
  if ( v0 )
  {
    v1 = 4798;
  }
  else
  {
    v0 = BcdOpenObject(v8, &GUID_CURRENT_BOOT_ENTRY, &v7);
    if ( v0 )
    {
      v1 = 4803;
    }
    else
    {
      v2 = 0;
      v9 = 1;
      v3 = BcdSetElementData(v7, 620757216, &v9, 8);
      if ( !v3 )
        goto LABEL_10;
      v0 = v3;
      v1 = 4817;
    }
  }
  v2 = v0 | 0x10000000;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v1,
    L"CDiskProtection::s_ModifyBootStatusPolicy",
    L"CBRAEx",
    L"status == ((NTSTATUS)0x00000000L)",
    v2);
  if ( IsDebuggerPresent() )
  {
    v6 = v2;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v1,
      L"CDiskProtection::s_ModifyBootStatusPolicy",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v6);
  }
  else
  {
    v5 = v2;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v1,
      L"CDiskProtection::s_ModifyBootStatusPolicy",
      L"CBRAEx",
      L"status == ((NTSTATUS)0x00000000L)",
      v5);
  }
LABEL_10:
  if ( v7 )
    BcdCloseObject();
  if ( v8 )
    BcdCloseStore();
  return v2;
}

```

## disassembly

```asm
0x140012788  mov     rax, rsp
0x14001278b  push    rbx
0x14001278c  push    rbp
0x14001278d  push    rsi
0x14001278e  push    r12
0x140012790  push    r14
0x140012792  sub     rsp, 40h
0x140012796  lea     rcx, [rax+10h]
0x14001279a  mov     qword ptr [rax+10h], 0
0x1400127a2  mov     qword ptr [rax+8], 0
0x1400127aa  mov     qword ptr [rax+18h], 0
0x1400127b2  call    cs:__imp_BcdOpenSystemStore
0x1400127b8  mov     ebx, eax
0x1400127ba  test    eax, eax
0x1400127bc  jz      short loc_1400127C6
0x1400127be  mov     r12d, 12BEh
0x1400127c4  jmp     short loc_140012825
0x1400127c6  mov     rcx, [rsp+68h+arg_8]
0x1400127cb  lea     r8, [rsp+68h+arg_0]
0x1400127d0  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1400127d7  call    cs:__imp_BcdOpenObject
0x1400127dd  mov     ebx, eax
0x1400127df  test    eax, eax
0x1400127e1  jz      short loc_1400127EB
0x1400127e3  mov     r12d, 12C3h
0x1400127e9  jmp     short loc_140012825
0x1400127eb  mov     rcx, [rsp+68h+arg_0]
0x1400127f0  lea     r8, [rsp+68h+arg_10]
0x1400127f8  xor     ebx, ebx
0x1400127fa  mov     [rsp+68h+arg_10], 1
0x140012806  mov     edx, 250000E0h
0x14001280b  lea     r9d, [rbx+8]
0x14001280f  call    cs:__imp_BcdSetElementData
0x140012815  test    eax, eax
0x140012817  jz      loc_1400128BD
0x14001281d  mov     ebx, eax
0x14001281f  mov     r12d, 12D1h
0x140012825  bts     ebx, 1Ch
0x140012829  lea     r14, aCbraex; "CBRAEx"
0x140012830  lea     rsi, aCdiskprotectio_156; "CDiskProtection::s_ModifyBootStatusPoli"...
0x140012837  mov     [rsp+68h+var_40], ebx; int
0x14001283b  lea     rbp, aStatusNtstatus_0; "status == ((NTSTATUS)0x00000000L)"
0x140012842  mov     r9, r14; unsigned __int16 *
0x140012845  mov     r8, rsi; unsigned __int16 *
0x140012848  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x14001284d  mov     edx, r12d; unsigned int
0x140012850  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012857  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001285c  call    cs:__imp_IsDebuggerPresent
0x140012862  test    eax, eax
0x140012864  jz      short loc_140012896
0x140012866  mov     [rsp+68h+var_30], ebx
0x14001286a  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012871  mov     [rsp+68h+var_38], rbp
0x140012876  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001287d  mov     qword ptr [rsp+68h+var_40], r14
0x140012882  mov     r9d, r12d
0x140012885  mov     ecx, 2; unsigned __int8
0x14001288a  mov     [rsp+68h+var_48], rsi
0x14001288f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140012894  jmp     short loc_1400128BD
0x140012896  mov     dword ptr [rsp+68h+var_38], ebx
0x14001289a  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400128a1  mov     qword ptr [rsp+68h+var_40], rbp
0x1400128a6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400128ad  mov     r9, rsi
0x1400128b0  mov     [rsp+68h+var_48], r14
0x1400128b5  mov     r8d, r12d
0x1400128b8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400128bd  mov     rcx, [rsp+68h+arg_0]
0x1400128c2  test    rcx, rcx
0x1400128c5  jz      short loc_1400128CD
0x1400128c7  call    cs:__imp_BcdCloseObject
0x1400128cd  mov     rcx, [rsp+68h+arg_8]
0x1400128d2  test    rcx, rcx
0x1400128d5  jz      short loc_1400128DD
0x1400128d7  call    cs:__imp_BcdCloseStore
0x1400128dd  mov     eax, ebx
0x1400128df  add     rsp, 40h
0x1400128e3  pop     r14
0x1400128e5  pop     r12
0x1400128e7  pop     rsi
0x1400128e8  pop     rbp
0x1400128e9  pop     rbx
0x1400128ea  retn
```
