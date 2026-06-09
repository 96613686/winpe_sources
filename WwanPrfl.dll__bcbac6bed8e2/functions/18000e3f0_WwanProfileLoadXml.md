# WwanProfileLoadXml

- ea: `0x18000e3f0`
- end: `0x18000e516`
- name: `WwanProfileLoadXml`
- size: `294`
- prototype: `__int64 __fastcall(struct WWAN_PROFILE *, unsigned __int16 *, struct IXMLDOMSchemaCollection *, int, _DWORD *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bc94`
- `0x18000da50`
- `0x18000e3f0`
- `0x18000f1d8`
- `0x1800125a4`
- `0x180012808`
- `0x180013334`
- `0x180014010`

## string_xrefs

- `0x18000e427`: `xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN/pro`

## pseudocode

```c
__int64 __fastcall WwanProfileLoadXml(
        struct WWAN_PROFILE *a1,
        unsigned __int16 *a2,
        struct IXMLDOMSchemaCollection *a3,
        int a4,
        _DWORD *a5,
        int a6)
{
  unsigned int LoadError; // edi
  const unsigned __int16 *v9; // rdx
  struct IXMLDOMDocument2 *v10; // rbx
  unsigned int v11; // eax
  struct IXMLDOMDocument2 *v13; // [rsp+30h] [rbp+8h] BYREF
  int v14; // [rsp+48h] [rbp+20h] BYREF

  *((_DWORD *)a1 + 981) = a4;
  v13 = 0;
  v14 = 0;
  LoadError = XcCreateXmlDoc(
                (OLECHAR *)L"xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='ht"
                            "tp://www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft."
                            "com/networking/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN"
                            "/profile/v4' xmlns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:"
                            "MBNProfileV6='http://www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http:"
                            "//www.microsoft.com/networking/WWAN/profile/v7' xmlns:MBNProfileV8='http://www.microsoft.com"
                            "/networking/WWAN/profile/v8' xmlns:MBNProfileV9='http://www.microsoft.com/networking/WWAN/profile/v9' ",
                a3,
                &v13);
  if ( LoadError )
  {
    if ( v13 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v13->lpVtbl->Release)(v13);
  }
  else
  {
    v9 = a2;
    v10 = v13;
    LoadError = XcLoadXml(v13, v9, &v14);
    if ( LoadError )
    {
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
    }
    else
    {
      if ( v14 )
        goto LABEL_15;
      LoadError = XcGetLoadError(v10);
      if ( LoadError == 1206 )
        *a5 = 3;
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
      v10 = 0;
      if ( !LoadError )
      {
LABEL_15:
        if ( a6 )
          v11 = _parseDMConfigProfile(v10, a1, 0);
        else
          v11 = parseProfile((struct IXMLDOMNode *)v10, a1, 0);
        LoadError = v11;
        if ( v11 )
          WwanProfileCleanup(a1);
        if ( v10 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
      }
    }
  }
  return LoadError;
}

```

## disassembly

```asm
0x18000e3f0  mov     r11, rsp
0x18000e3f3  mov     [r11+10h], rbx
0x18000e3f7  mov     [r11+18h], rsi
0x18000e3fb  push    rdi
0x18000e3fc  sub     rsp, 20h
0x18000e400  mov     rax, r8
0x18000e403  mov     rbx, rdx
0x18000e406  mov     rsi, rcx
0x18000e409  mov     [rcx+0F54h], r9d
0x18000e410  mov     qword ptr [r11+8], 0
0x18000e418  mov     [rsp+28h+arg_18], 0
0x18000e420  lea     r8, [r11+8]; struct IXMLDOMDocument2 **
0x18000e424  mov     rdx, rax; struct IXMLDOMSchemaCollection *
0x18000e427  lea     rcx, aXmlnsMbnprofil; "xmlns:MBNProfile='http://www.microsoft."...
0x18000e42e  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000e433  mov     edi, eax
0x18000e435  test    eax, eax
0x18000e437  jz      short loc_18000E452
0x18000e439  mov     rcx, [rsp+28h+arg_0]
0x18000e43e  test    rcx, rcx
0x18000e441  jz      short loc_18000E450
0x18000e443  mov     rax, [rcx]
0x18000e446  mov     rax, [rax+10h]
0x18000e44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e44f  nop
0x18000e450  jmp     short loc_18000E4C2
0x18000e452  lea     r8, [rsp+28h+arg_18]; int *
0x18000e457  mov     rdx, rbx; unsigned __int16 *
0x18000e45a  mov     rbx, [rsp+28h+arg_0]
0x18000e45f  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000e462  call    ?XcLoadXml@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z; XcLoadXml(IXMLDOMDocument2 *,ushort const *,int *)
0x18000e467  mov     edi, eax
0x18000e469  test    eax, eax
0x18000e46b  jz      short loc_18000E484
0x18000e46d  test    rbx, rbx
0x18000e470  jz      short loc_18000E482
0x18000e472  mov     rax, [rbx]
0x18000e475  mov     rcx, rbx
0x18000e478  mov     rax, [rax+10h]
0x18000e47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e481  nop
0x18000e482  jmp     short loc_18000E4C2
0x18000e484  cmp     [rsp+28h+arg_18], 0
0x18000e489  jnz     short loc_18000E4C4
0x18000e48b  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000e48e  call    ?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z; XcGetLoadError(IXMLDOMDocument2 *)
0x18000e493  mov     edi, eax
0x18000e495  cmp     eax, 4B6h
0x18000e49a  jnz     short loc_18000E4A7
0x18000e49c  mov     rax, [rsp+28h+arg_20]
0x18000e4a1  mov     dword ptr [rax], 3
0x18000e4a7  test    rbx, rbx
0x18000e4aa  jz      short loc_18000E4BC
0x18000e4ac  mov     rax, [rbx]
0x18000e4af  mov     rcx, rbx
0x18000e4b2  mov     rax, [rax+10h]
0x18000e4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4bb  nop
0x18000e4bc  xor     ebx, ebx
0x18000e4be  test    edi, edi
0x18000e4c0  jz      short loc_18000E4C4
0x18000e4c2  jmp     short loc_18000E504
0x18000e4c4  xor     r8d, r8d; int
0x18000e4c7  mov     rdx, rsi; struct WWAN_PROFILE *
0x18000e4ca  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000e4cd  cmp     [rsp+28h+arg_28], r8d
0x18000e4d2  jnz     short loc_18000E4DB
0x18000e4d4  call    _parseProfile
0x18000e4d9  jmp     short loc_18000E4E0
0x18000e4db  call    ?_parseDMConfigProfile@@YAKPEAUIXMLDOMDocument2@@PEAUWWAN_PROFILE@@H@Z; _parseDMConfigProfile(IXMLDOMDocument2 *,WWAN_PROFILE *,int)
0x18000e4e0  mov     edi, eax
0x18000e4e2  test    eax, eax
0x18000e4e4  jz      short loc_18000E4EF
0x18000e4e6  mov     rcx, rsi
0x18000e4e9  call    WwanProfileCleanup
0x18000e4ee  nop
0x18000e4ef  test    rbx, rbx
0x18000e4f2  jz      short loc_18000E504
0x18000e4f4  mov     rax, [rbx]
0x18000e4f7  mov     rcx, rbx
0x18000e4fa  mov     rax, [rax+10h]
0x18000e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e503  nop
0x18000e504  mov     eax, edi
0x18000e506  mov     rbx, [rsp+28h+arg_8]
0x18000e50b  mov     rsi, [rsp+28h+arg_10]
0x18000e510  add     rsp, 20h
0x18000e514  pop     rdi
0x18000e515  retn
```
