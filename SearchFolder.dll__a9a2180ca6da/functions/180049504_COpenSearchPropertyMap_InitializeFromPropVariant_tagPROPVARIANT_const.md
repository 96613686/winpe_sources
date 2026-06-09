# COpenSearchPropertyMap::InitializeFromPropVariant(tagPROPVARIANT const &)

- ea: `0x180049504`
- end: `0x1800495a4`
- name: `?InitializeFromPropVariant@COpenSearchPropertyMap@@QEAAJAEBUtagPROPVARIANT@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(COpenSearchPropertyMap *__hidden this, PROPVARIANT *propvarIn)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044618`

## callees

- `0x180049504`
- `0x180049b48`
- `0x180049ccc`

## import_xrefs

- `SHLWAPI!StrStrA` at `0x180049551`
- `SHLWAPI!StrStrA` at `0x18004956a`
- `SHLWAPI!StrStrA` at `0x180049551`
- `SHLWAPI!StrStrA` at `0x18004956a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049591`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004951e`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004951e`

## pseudocode

```c
__int64 __fastcall COpenSearchPropertyMap::InitializeFromPropVariant(OLECHAR *this, PROPVARIANT *propvarIn)
{
  int v3; // ebx
  const WCHAR *v4; // rax
  PSTR v5; // rax
  const BYTE *v6; // rbx
  PSTR v7; // rax
  PCSTR pszFirst; // [rsp+40h] [rbp+18h] BYREF

  v3 = -2147467259;
  v4 = PropVariantToStringWithDefault(propvarIn, 0);
  if ( v4 )
  {
    pszFirst = 0;
    v3 = _CoAllocAnsiStringFromWideString(v4, (char **)&pszFirst);
    if ( v3 >= 0 )
    {
      v5 = StrStrA(pszFirst, "<![CDATA[");
      if ( v5 )
      {
        v6 = (const BYTE *)(v5 + 10);
        v7 = StrStrA(v5 + 10, "]]>");
        if ( v7 )
          *v7 = 0;
      }
      else
      {
        v6 = (const BYTE *)pszFirst;
      }
      v3 = COpenSearchPropertyMap::_InitializeFromXmlFragment(this, v6);
      CoTaskMemFree((LPVOID)pszFirst);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180049504  mov     [rsp+arg_0], rbx
0x180049509  push    rsi
0x18004950a  sub     rsp, 20h
0x18004950e  mov     rax, rdx
0x180049511  mov     rsi, rcx
0x180049514  mov     rcx, rax; propvarIn
0x180049517  xor     edx, edx; pszDefault
0x180049519  mov     ebx, 80004005h
0x18004951e  call    cs:__imp_PropVariantToStringWithDefault
0x180049524  test    rax, rax
0x180049527  jz      short loc_180049597
0x180049529  lea     rdx, [rsp+28h+pszFirst]; char **
0x18004952e  mov     [rsp+28h+pszFirst], 0
0x180049537  mov     rcx, rax; lpWideCharStr
0x18004953a  call    ?_CoAllocAnsiStringFromWideString@@YAJPEBGPEAPEAD@Z; _CoAllocAnsiStringFromWideString(ushort const *,char * *)
0x18004953f  mov     ebx, eax
0x180049541  test    eax, eax
0x180049543  js      short loc_180049597
0x180049545  mov     rcx, [rsp+28h+pszFirst]; pszFirst
0x18004954a  lea     rdx, aCdata; "<![CDATA["
0x180049551  call    cs:__imp_StrStrA
0x180049557  test    rax, rax
0x18004955a  jz      short loc_18004957A
0x18004955c  lea     rbx, [rax+0Ah]
0x180049560  mov     rcx, rbx; pszFirst
0x180049563  lea     rdx, asc_18005CF68; "]]>"
0x18004956a  call    cs:__imp_StrStrA
0x180049570  test    rax, rax
0x180049573  jz      short loc_18004957F
0x180049575  mov     byte ptr [rax], 0
0x180049578  jmp     short loc_18004957F
0x18004957a  mov     rbx, [rsp+28h+pszFirst]
0x18004957f  mov     rdx, rbx; char *
0x180049582  mov     rcx, rsi; this
0x180049585  call    ?_InitializeFromXmlFragment@COpenSearchPropertyMap@@AEAAJPEBD@Z; COpenSearchPropertyMap::_InitializeFromXmlFragment(char const *)
0x18004958a  mov     rcx, [rsp+28h+pszFirst]; pv
0x18004958f  mov     ebx, eax
0x180049591  call    cs:__imp_CoTaskMemFree
0x180049597  mov     eax, ebx
0x180049599  mov     rbx, [rsp+28h+arg_0]
0x18004959e  add     rsp, 20h
0x1800495a2  pop     rsi
0x1800495a3  retn
```
