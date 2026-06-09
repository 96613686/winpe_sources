# _loadProfileFile

- ea: `0x18000b5a0`
- end: `0x18000b662`
- name: `_loadProfileFile`
- size: `194`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IXMLDOMSchemaCollection *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e2f0`

## callees

- `0x18000b5a0`
- `0x1800125a4`
- `0x180013280`
- `0x180014010`

## string_xrefs

- `0x18000b5c9`: `xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN/pro`

## pseudocode

```c
__int64 __fastcall loadProfileFile(
        unsigned __int16 *a1,
        struct IXMLDOMSchemaCollection *a2,
        struct IXMLDOMDocument2 **a3)
{
  unsigned int v5; // ebx
  struct IXMLDOMDocument2 *v7; // rbx
  unsigned int v8; // edi
  struct IXMLDOMDocument2 *v9; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  v5 = XcCreateXmlDoc(
         (OLECHAR *)L"xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://ww"
                     "w.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking"
                     "/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MB"
                     "NProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.mic"
                     "rosoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN"
                     "/profile/v7' xmlns:MBNProfileV8='http://www.microsoft.com/networking/WWAN/profile/v8' xmlns:MBNProf"
                     "ileV9='http://www.microsoft.com/networking/WWAN/profile/v9' ",
         a2,
         &v9);
  if ( v5 )
  {
    if ( v9 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->Release)(v9);
    return v5;
  }
  else
  {
    v7 = v9;
    v8 = XcLoadFrom(v9, a1, &v10);
    if ( v8 )
    {
      if ( v7 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
      return v8;
    }
    else if ( v10 )
    {
      *a3 = v7;
      return 0;
    }
    else
    {
      if ( v7 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
      return 1206;
    }
  }
}

```

## disassembly

```asm
0x18000b5a0  mov     rax, rsp
0x18000b5a3  mov     [rax+8], rbx
0x18000b5a7  mov     [rax+10h], rsi
0x18000b5ab  push    rdi
0x18000b5ac  sub     rsp, 30h
0x18000b5b0  mov     rsi, r8
0x18000b5b3  mov     rdi, rcx
0x18000b5b6  mov     qword ptr [rax-18h], 0
0x18000b5be  mov     dword ptr [rax+20h], 0
0x18000b5c5  lea     r8, [rax-18h]; struct IXMLDOMDocument2 **
0x18000b5c9  lea     rcx, aXmlnsMbnprofil; "xmlns:MBNProfile='http://www.microsoft."...
0x18000b5d0  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000b5d5  mov     ebx, eax
0x18000b5d7  test    eax, eax
0x18000b5d9  jz      short loc_18000B5F6
0x18000b5db  mov     rcx, [rsp+38h+var_18]
0x18000b5e0  test    rcx, rcx
0x18000b5e3  jz      short loc_18000B5F2
0x18000b5e5  mov     rdx, [rcx]
0x18000b5e8  mov     rax, [rdx+10h]
0x18000b5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f1  nop
0x18000b5f2  mov     eax, ebx
0x18000b5f4  jmp     short loc_18000B652
0x18000b5f6  lea     r8, [rsp+38h+arg_18]; int *
0x18000b5fb  mov     rdx, rdi; unsigned __int16 *
0x18000b5fe  mov     rbx, [rsp+38h+var_18]
0x18000b603  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000b606  call    ?XcLoadFrom@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z; XcLoadFrom(IXMLDOMDocument2 *,ushort const *,int *)
0x18000b60b  mov     edi, eax
0x18000b60d  test    eax, eax
0x18000b60f  jz      short loc_18000B62A
0x18000b611  test    rbx, rbx
0x18000b614  jz      short loc_18000B626
0x18000b616  mov     rcx, [rbx]
0x18000b619  mov     rax, [rcx+10h]
0x18000b61d  mov     rcx, rbx
0x18000b620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b625  nop
0x18000b626  mov     eax, edi
0x18000b628  jmp     short loc_18000B652
0x18000b62a  cmp     [rsp+38h+arg_18], 0
0x18000b62f  jnz     short loc_18000B64D
0x18000b631  test    rbx, rbx
0x18000b634  jz      short loc_18000B646
0x18000b636  mov     rax, [rbx]
0x18000b639  mov     rcx, rbx
0x18000b63c  mov     rax, [rax+10h]
0x18000b640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b645  nop
0x18000b646  mov     eax, 4B6h
0x18000b64b  jmp     short loc_18000B652
0x18000b64d  mov     [rsi], rbx
0x18000b650  xor     eax, eax
0x18000b652  mov     rbx, [rsp+38h+arg_0]
0x18000b657  mov     rsi, [rsp+38h+arg_8]
0x18000b65c  add     rsp, 30h
0x18000b660  pop     rdi
0x18000b661  retn
```
