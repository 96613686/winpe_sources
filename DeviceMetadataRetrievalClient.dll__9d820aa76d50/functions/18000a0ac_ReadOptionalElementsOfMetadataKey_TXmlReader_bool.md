# ReadOptionalElementsOfMetadataKey(TXmlReader &,bool *)

- ea: `0x18000a0ac`
- end: `0x18000a1f9`
- name: `?ReadOptionalElementsOfMetadataKey@@YAJAEAVTXmlReader@@PEA_N@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct TXmlReader *this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000913c`

## callees

- `0x180004dc4`
- `0x18000a0ac`
- `0x1800109e4`
- `0x180010a84`
- `0x180010bc8`
- `0x1800136d2`
- `0x180014010`

## string_xrefs

- `0x18000a0f7`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000a18d`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000a115`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/PackageInfov2`

## pseudocode

```c
__int64 __fastcall ReadOptionalElementsOfMetadataKey(struct TXmlReader *this, bool *a2)
{
  struct TXmlReader *i; // rsi
  __int64 v4; // rcx
  __int64 result; // rax
  const unsigned __int16 *v6; // rbx
  bool v7; // di
  const unsigned __int16 *v8; // [rsp+48h] [rbp+10h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  for ( i = this; ; this = i )
  {
    result = TXmlReader::ReadEndElement(
               this,
               L"MetadataKey",
               L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( (_DWORD)result != 1 )
      break;
    v4 = *(_QWORD *)i;
    String1 = 0;
    result = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v4 + 104LL))(v4, &String1, 0);
    if ( (_DWORD)result )
      break;
    if ( !wcscmp_0(String1, L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
      return 2147500037LL;
    }
    v8 = 0;
    if ( !(unsigned int)TXmlReader::ReadElementString(
                          i,
                          L"MultipleLocale",
                          L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/PackageInfov2",
                          &v8) )
    {
      v6 = v8;
      if ( *v8 == 49 && !v8[1] || !wcscmp_0(v8, L"true") )
      {
        v7 = 1;
LABEL_16:
        *a2 = v7;
        continue;
      }
      v7 = 0;
      if ( *v6 == 48 && !v6[1] || !wcscmp_0(v6, L"false") )
        goto LABEL_16;
    }
    LODWORD(v8) = 0;
    result = TXmlReader::Read(i, (enum XmlNodeType *)&v8);
    if ( (int)result < 0 )
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x18000a0ac  mov     [rsp+arg_0], rbx
0x18000a0b1  mov     [rsp+arg_18], rbp
0x18000a0b6  push    rsi
0x18000a0b7  push    rdi
0x18000a0b8  push    r14
0x18000a0ba  sub     rsp, 20h
0x18000a0be  xor     ebp, ebp
0x18000a0c0  mov     r14, rdx
0x18000a0c3  mov     [rdx], bpl
0x18000a0c6  mov     rsi, rcx
0x18000a0c9  jmp     loc_18000A18D
0x18000a0ce  mov     rcx, [rsi]
0x18000a0d1  lea     rdx, [rsp+38h+String1]
0x18000a0d6  mov     [rsp+38h+String1], rbp
0x18000a0db  xor     r8d, r8d
0x18000a0de  mov     rax, [rcx]
0x18000a0e1  mov     rax, [rax+68h]
0x18000a0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0ea  test    eax, eax
0x18000a0ec  jnz     loc_18000A1E6
0x18000a0f2  mov     rcx, [rsp+38h+String1]; String1
0x18000a0f7  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x18000a0fe  call    wcscmp_0
0x18000a103  test    eax, eax
0x18000a105  jz      loc_18000A1B3
0x18000a10b  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x18000a110  mov     [rsp+38h+arg_8], rbp
0x18000a115  lea     r8, aHttpSchemasMic_2; "http://schemas.microsoft.com/windows/20"...
0x18000a11c  mov     rcx, rsi; this
0x18000a11f  lea     rdx, aMultiplelocale; "MultipleLocale"
0x18000a126  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x18000a12b  test    eax, eax
0x18000a12d  jnz     short loc_18000A175
0x18000a12f  mov     rbx, [rsp+38h+arg_8]
0x18000a134  cmp     word ptr [rbx], 31h ; '1'
0x18000a138  jnz     short loc_18000A140
0x18000a13a  cmp     [rbx+2], bp
0x18000a13e  jz      short loc_18000A1AB
0x18000a140  lea     rdx, aTrue; "true"
0x18000a147  mov     rcx, rbx; String1
0x18000a14a  call    wcscmp_0
0x18000a14f  test    eax, eax
0x18000a151  jz      short loc_18000A1AB
0x18000a153  cmp     word ptr [rbx], 30h ; '0'
0x18000a157  mov     dil, bpl
0x18000a15a  jnz     short loc_18000A162
0x18000a15c  cmp     [rbx+2], bp
0x18000a160  jz      short loc_18000A1AE
0x18000a162  lea     rdx, aFalse; "false"
0x18000a169  mov     rcx, rbx; String1
0x18000a16c  call    wcscmp_0
0x18000a171  test    eax, eax
0x18000a173  jz      short loc_18000A1AE
0x18000a175  lea     rdx, [rsp+38h+arg_8]; enum XmlNodeType *
0x18000a17a  mov     dword ptr [rsp+38h+arg_8], ebp
0x18000a17e  mov     rcx, rsi; this
0x18000a181  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x18000a186  test    eax, eax
0x18000a188  js      short loc_18000A1E6
0x18000a18a  mov     rcx, rsi; this
0x18000a18d  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x18000a194  lea     rdx, aMetadatakey; "MetadataKey"
0x18000a19b  call    ?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadEndElement(ushort const *,ushort const *)
0x18000a1a0  cmp     eax, 1
0x18000a1a3  jz      loc_18000A0CE
0x18000a1a9  jmp     short loc_18000A1E6
0x18000a1ab  mov     dil, 1
0x18000a1ae  mov     [r14], dil
0x18000a1b1  jmp     short loc_18000A18A
0x18000a1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1ba  lea     rax, WPP_GLOBAL_Control
0x18000a1c1  cmp     rcx, rax
0x18000a1c4  jz      short loc_18000A1E1
0x18000a1c6  test    byte ptr [rcx+1Ch], 1
0x18000a1ca  jz      short loc_18000A1E1
0x18000a1cc  mov     rcx, [rcx+10h]
0x18000a1d0  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000a1d7  mov     edx, 5Ah ; 'Z'
0x18000a1dc  call    WPP_SF_
0x18000a1e1  mov     eax, 80004005h
0x18000a1e6  mov     rbx, [rsp+38h+arg_0]
0x18000a1eb  mov     rbp, [rsp+38h+arg_18]
0x18000a1f0  add     rsp, 20h
0x18000a1f4  pop     r14
0x18000a1f6  pop     rdi
0x18000a1f7  pop     rsi
0x18000a1f8  retn
```
