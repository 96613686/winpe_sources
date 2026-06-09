# _parseUserLogonCredNode

- ea: `0x18000cf80`
- end: `0x18000d2be`
- name: `_parseUserLogonCredNode`
- size: `830`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000b4b0`
- `0x18000cf80`
- `0x180012968`
- `0x180012a4c`
- `0x180012bc8`
- `0x1800131e4`
- `0x180013458`
- `0x1800134f8`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d24b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d24b`
- `CRYPT32!CryptProtectData` at `0x18000d241`
- `CRYPT32!CryptProtectData` at `0x18000d241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2a2`

## pseudocode

```c
unsigned int __fastcall parseUserLogonCredNode(struct IXMLDOMNode *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rdx
  unsigned int result; // eax
  const unsigned __int16 *v10; // rdx
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  unsigned int SingleNode; // edi
  size_t v15; // rdi
  void *v16; // rax
  DWORD LastError; // ebx
  const wchar_t *v18; // rdx
  __int64 v19; // rax
  void *v20; // rcx
  DWORD cbData; // eax
  DATA_BLOB Src; // [rsp+40h] [rbp-20h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMNode *v24; // [rsp+98h] [rbp+38h] BYREF
  size_t Size; // [rsp+A8h] [rbp+48h] BYREF

  v7 = (unsigned __int16 *)(a2 + 3410);
  if ( a4 < 3 )
  {
    v8 = L"MBNProfileV4:UserName";
    if ( a4 != 2 )
      v8 = L"MBNProfile:UserName";
  }
  else
  {
    v8 = L"MBNProfileV9:UserName";
  }
  result = XcGetNodeStringValue(a1, v8, v7, 0x100u, 0, 0, 0);
  if ( !result )
  {
    *(_DWORD *)(a2 + 3200) |= 2u;
    if ( a4 < 3 )
    {
      v10 = L"MBNProfileV4:IgnorePassword";
      if ( a4 != 2 )
        v10 = L"MBNProfile:IgnorePassword";
    }
    else
    {
      v10 = L"MBNProfileV9:IgnorePassword";
    }
    result = XcGetNodeEnumValue(
               a1,
               v10,
               (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
               4u,
               (unsigned int *)(a2 + 3204),
               1,
               0,
               0);
    if ( !result )
    {
      v11 = *(_DWORD *)(a2 + 3924);
      if ( !v11 )
        return 0;
      if ( v11 == 1 )
      {
        v24 = 0;
        *(_QWORD *)&Src.cbData = 0;
        LODWORD(Size) = 0;
        if ( a4 < 3 )
        {
          v12 = L"MBNProfileV4:Password";
          if ( a4 != 2 )
            v12 = L"MBNProfile:Password";
        }
        else
        {
          v12 = L"MBNProfileV9:Password";
        }
        SingleNode = XcGetSingleNode(a1, v12, &v24);
        if ( SingleNode == 1168 )
        {
          if ( v24 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
          return 0;
        }
        if ( SingleNode )
        {
          if ( v24 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
          return SingleNode;
        }
        SingleNode = XcGetNodeHexBinaryValue(v24, v13, (unsigned __int8 **)&Src, (unsigned int *)&Size);
        if ( SingleNode )
        {
          if ( v24 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
          return SingleNode;
        }
        v15 = (unsigned int)Size;
        v16 = WwanMemAlloc((unsigned int)Size);
        *(_QWORD *)(a2 + 4456) = v16;
        if ( v16 )
        {
          *(_DWORD *)(a2 + 4448) = v15;
          *(_DWORD *)(a2 + 3200) |= 4u;
          memcpy_0(v16, *(const void **)&Src.cbData, v15);
          Xc_Process_user_free(*(void **)&Src.cbData);
          if ( v24 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
          return 0;
        }
        Xc_Process_user_free(*(void **)&Src.cbData);
        LastError = GetLastError();
        if ( v24 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
        return LastError;
      }
      if ( *(_DWORD *)(a2 + 3204) )
        return 0;
      LODWORD(Size) = 0;
      if ( a4 < 3 )
      {
        v18 = L"MBNProfileV4:Password";
        if ( a4 != 2 )
          v18 = L"MBNProfile:Password";
      }
      else
      {
        v18 = L"MBNProfileV9:Password";
      }
      result = getOptNodeStringValue(a1, v18, a2 + 3928, 256, &Size);
      if ( !result )
      {
        if ( (_DWORD)Size )
        {
          *(&pDataIn.cbData + 1) = 0;
          *(_QWORD *)&Src.cbData = 0;
          Src.pbData = 0;
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(a2 + 3928 + 2 * v19) );
          pDataIn.cbData = 2 * v19;
          pDataIn.pbData = (BYTE *)(a2 + 3928);
          if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &Src)
            || (v20 = WwanMemAlloc(Src.cbData), (*(_QWORD *)(a2 + 4456) = v20) == 0) )
          {
            LastError = GetLastError();
            if ( Src.pbData )
              LocalFree(Src.pbData);
            return LastError;
          }
          cbData = Src.cbData;
          *(_DWORD *)(a2 + 4448) = Src.cbData;
          *(_DWORD *)(a2 + 3200) |= 4u;
          memcpy_0(v20, Src.pbData, cbData);
          LocalFree(Src.pbData);
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp-28h+arg_0], rbx
0x18000cf85  push    rbp
0x18000cf86  push    rsi
0x18000cf87  push    rdi
0x18000cf88  push    r14
0x18000cf8a  push    r15
0x18000cf8c  mov     rbp, rsp
0x18000cf8f  sub     rsp, 60h
0x18000cf93  mov     edi, r9d
0x18000cf96  mov     rbx, rdx
0x18000cf99  mov     r14, rcx
0x18000cf9c  lea     r8, [rdx+0D52h]; unsigned __int16 *
0x18000cfa3  cmp     r9d, 3
0x18000cfa7  jb      short loc_18000CFB2
0x18000cfa9  lea     rdx, aMbnprofilev9Us_0; "MBNProfileV9:UserName"
0x18000cfb0  jmp     short loc_18000CFC7
0x18000cfb2  lea     rdx, aMbnprofilev4Us; "MBNProfileV4:UserName"
0x18000cfb9  lea     rax, aMbnprofileUser; "MBNProfile:UserName"
0x18000cfc0  cmp     edi, 2
0x18000cfc3  cmovnz  rdx, rax; unsigned __int16 *
0x18000cfc7  xor     r15d, r15d
0x18000cfca  mov     [rsp+60h+pDataOut], r15; int *
0x18000cfcf  mov     qword ptr [rsp+60h+dwFlags], r15; unsigned __int16 *
0x18000cfd4  mov     dword ptr [rsp+60h+pPromptStruct], r15d; int
0x18000cfd9  mov     r9d, 100h; unsigned __int64
0x18000cfdf  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000cfe4  test    eax, eax
0x18000cfe6  jnz     loc_18000D2AA
0x18000cfec  or      dword ptr [rbx+0C80h], 2
0x18000cff3  lea     rsi, [rbx+0C84h]
0x18000cffa  cmp     edi, 3
0x18000cffd  jb      short loc_18000D008
0x18000cfff  lea     rdx, aMbnprofilev9Ig; "MBNProfileV9:IgnorePassword"
0x18000d006  jmp     short loc_18000D01D
0x18000d008  lea     rdx, aMbnprofilev4Ig; "MBNProfileV4:IgnorePassword"
0x18000d00f  lea     rax, aMbnprofileIgno; "MBNProfile:IgnorePassword"
0x18000d016  cmp     edi, 2
0x18000d019  cmovnz  rdx, rax; unsigned __int16 *
0x18000d01d  mov     [rsp+60h+var_28], r15; int *
0x18000d022  mov     dword ptr [rsp+60h+pDataOut], r15d; unsigned int
0x18000d027  mov     [rsp+60h+dwFlags], 1; int
0x18000d02f  mov     [rsp+60h+pPromptStruct], rsi; unsigned int *
0x18000d034  mov     r9d, 4; unsigned int
0x18000d03a  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x18000d041  mov     rcx, r14; struct IXMLDOMNode *
0x18000d044  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000d049  test    eax, eax
0x18000d04b  jnz     loc_18000D2AA
0x18000d051  mov     eax, [rbx+0F54h]
0x18000d057  test    eax, eax
0x18000d059  jz      loc_18000D2A8
0x18000d05f  cmp     eax, 1
0x18000d062  jnz     loc_18000D19C
0x18000d068  mov     [rbp+arg_8], r15
0x18000d06c  mov     [rbp+Src], r15
0x18000d070  mov     dword ptr [rbp+Size], r15d
0x18000d074  cmp     edi, 3
0x18000d077  jb      short loc_18000D082
0x18000d079  lea     rdx, aMbnprofilev9Pa; "MBNProfileV9:Password"
0x18000d080  jmp     short loc_18000D097
0x18000d082  lea     rdx, aMbnprofilev4Pa; "MBNProfileV4:Password"
0x18000d089  lea     rax, aMbnprofilePass; "MBNProfile:Password"
0x18000d090  cmp     edi, 2
0x18000d093  cmovnz  rdx, rax; unsigned __int16 *
0x18000d097  lea     r8, [rbp+arg_8]; struct IXMLDOMNode **
0x18000d09b  mov     rcx, r14; struct IXMLDOMNode *
0x18000d09e  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000d0a3  mov     edi, eax
0x18000d0a5  cmp     eax, 490h
0x18000d0aa  jnz     short loc_18000D0C7
0x18000d0ac  mov     rcx, [rbp+arg_8]
0x18000d0b0  test    rcx, rcx
0x18000d0b3  jz      short loc_18000D0C2
0x18000d0b5  mov     rax, [rcx]
0x18000d0b8  mov     rax, [rax+10h]
0x18000d0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0c1  nop
0x18000d0c2  jmp     loc_18000D2A8
0x18000d0c7  test    edi, edi
0x18000d0c9  jz      short loc_18000D0E8
0x18000d0cb  mov     rcx, [rbp+arg_8]
0x18000d0cf  test    rcx, rcx
0x18000d0d2  jz      short loc_18000D0E1
0x18000d0d4  mov     rax, [rcx]
0x18000d0d7  mov     rax, [rax+10h]
0x18000d0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e0  nop
0x18000d0e1  mov     eax, edi
0x18000d0e3  jmp     loc_18000D2AA
0x18000d0e8  lea     r9, [rbp+Size]; unsigned int *
0x18000d0ec  lea     r8, [rbp+Src]; unsigned __int8 **
0x18000d0f0  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000d0f4  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x18000d0f9  mov     edi, eax
0x18000d0fb  test    eax, eax
0x18000d0fd  jz      short loc_18000D117
0x18000d0ff  mov     rcx, [rbp+arg_8]
0x18000d103  test    rcx, rcx
0x18000d106  jz      short loc_18000D115
0x18000d108  mov     rdx, [rcx]
0x18000d10b  mov     rax, [rdx+10h]
0x18000d10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d114  nop
0x18000d115  jmp     short loc_18000D0E1
0x18000d117  mov     edi, dword ptr [rbp+Size]
0x18000d11a  mov     ecx, edi; Size
0x18000d11c  call    WwanMemAlloc
0x18000d121  mov     [rbx+1168h], rax
0x18000d128  test    rax, rax
0x18000d12b  jnz     short loc_18000D15B
0x18000d12d  mov     rcx, [rbp+Src]; lpMem
0x18000d131  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000d136  call    cs:__imp_GetLastError
0x18000d13c  mov     ebx, eax
0x18000d13e  mov     rcx, [rbp+arg_8]
0x18000d142  test    rcx, rcx
0x18000d145  jz      short loc_18000D154
0x18000d147  mov     rdx, [rcx]
0x18000d14a  mov     rax, [rdx+10h]
0x18000d14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d153  nop
0x18000d154  mov     eax, ebx
0x18000d156  jmp     loc_18000D2AA
0x18000d15b  mov     [rbx+1160h], edi
0x18000d161  or      dword ptr [rbx+0C80h], 4
0x18000d168  mov     r8, rdi; Size
0x18000d16b  mov     rdx, [rbp+Src]; Src
0x18000d16f  mov     rcx, rax; void *
0x18000d172  call    memcpy_0
0x18000d177  mov     rcx, [rbp+Src]; lpMem
0x18000d17b  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000d180  nop
0x18000d181  mov     rcx, [rbp+arg_8]
0x18000d185  test    rcx, rcx
0x18000d188  jz      short loc_18000D197
0x18000d18a  mov     rax, [rcx]
0x18000d18d  mov     rax, [rax+10h]
0x18000d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d196  nop
0x18000d197  jmp     loc_18000D2A8
0x18000d19c  cmp     [rsi], r15d
0x18000d19f  jnz     loc_18000D2A8
0x18000d1a5  mov     dword ptr [rbp+Size], r15d
0x18000d1a9  lea     rsi, [rbx+0F58h]
0x18000d1b0  cmp     edi, 3
0x18000d1b3  jb      short loc_18000D1BE
0x18000d1b5  lea     rdx, aMbnprofilev9Pa; "MBNProfileV9:Password"
0x18000d1bc  jmp     short loc_18000D1D3
0x18000d1be  lea     rdx, aMbnprofilev4Pa; "MBNProfileV4:Password"
0x18000d1c5  lea     rax, aMbnprofilePass; "MBNProfile:Password"
0x18000d1cc  cmp     edi, 2
0x18000d1cf  cmovnz  rdx, rax
0x18000d1d3  lea     rax, [rbp+Size]
0x18000d1d7  mov     [rsp+60h+pPromptStruct], rax
0x18000d1dc  mov     r9d, 100h
0x18000d1e2  mov     r8, rsi
0x18000d1e5  mov     rcx, r14
0x18000d1e8  call    _getOptNodeStringValue
0x18000d1ed  test    eax, eax
0x18000d1ef  jnz     loc_18000D2AA
0x18000d1f5  cmp     dword ptr [rbp+Size], r15d
0x18000d1f9  jz      loc_18000D2A8
0x18000d1ff  mov     dword ptr [rbp+pDataIn+4], r15d
0x18000d203  mov     [rbp+Src], r15
0x18000d207  mov     [rbp+hMem], r15
0x18000d20b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d20f  inc     rax
0x18000d212  cmp     [rsi+rax*2], r15w
0x18000d217  jnz     short loc_18000D20F
0x18000d219  add     eax, eax
0x18000d21b  mov     [rbp+pDataIn.cbData], eax
0x18000d21e  mov     [rbp+pDataIn.pbData], rsi
0x18000d222  lea     rax, [rbp+Src]
0x18000d226  mov     [rsp+60h+pDataOut], rax; pDataOut
0x18000d22b  mov     [rsp+60h+dwFlags], r15d; dwFlags
0x18000d230  mov     [rsp+60h+pPromptStruct], r15; pPromptStruct
0x18000d235  xor     r9d, r9d; pvReserved
0x18000d238  xor     r8d, r8d; pOptionalEntropy
0x18000d23b  xor     edx, edx; szDataDescr
0x18000d23d  lea     rcx, [rbp+pDataIn]; pDataIn
0x18000d241  call    cs:__imp_CryptProtectData
0x18000d247  test    eax, eax
0x18000d249  jnz     short loc_18000D26B
0x18000d24b  call    cs:__imp_GetLastError
0x18000d251  mov     ebx, eax
0x18000d253  mov     rcx, [rbp+hMem]; hMem
0x18000d257  test    rcx, rcx
0x18000d25a  jz      loc_18000D154
0x18000d260  call    cs:__imp_LocalFree
0x18000d266  jmp     loc_18000D154
0x18000d26b  mov     ecx, dword ptr [rbp+Src]; Size
0x18000d26e  call    WwanMemAlloc
0x18000d273  mov     rcx, rax; void *
0x18000d276  mov     [rbx+1168h], rax
0x18000d27d  test    rax, rax
0x18000d280  jz      short loc_18000D24B
0x18000d282  mov     eax, dword ptr [rbp+Src]
0x18000d285  mov     [rbx+1160h], eax
0x18000d28b  or      dword ptr [rbx+0C80h], 4
0x18000d292  mov     r8d, eax; Size
0x18000d295  mov     rdx, [rbp+hMem]; Src
0x18000d299  call    memcpy_0
0x18000d29e  mov     rcx, [rbp+hMem]; hMem
0x18000d2a2  call    cs:__imp_LocalFree
0x18000d2a8  xor     eax, eax
0x18000d2aa  mov     rbx, [rsp+60h+arg_0]
0x18000d2b2  add     rsp, 60h
0x18000d2b6  pop     r15
0x18000d2b8  pop     r14
0x18000d2ba  pop     rdi
0x18000d2bb  pop     rsi
0x18000d2bc  pop     rbp
0x18000d2bd  retn
```
