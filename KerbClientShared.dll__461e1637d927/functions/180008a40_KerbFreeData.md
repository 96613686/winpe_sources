# KerbFreeData

- ea: `0x180008a40`
- end: `0x180008b57`
- name: `KerbFreeData`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016f0`
- `0x180009d60`
- `0x18000a1b0`
- `0x18000aed0`
- `0x18000b790`
- `0x180014d5c`
- `0x180016328`
- `0x180016680`

## callees

- `0x180008a40`
- `0x1800146ec`

## import_xrefs

- `MSASN1!ASN1_FreeDecoded` at `0x180008b31`
- `MSASN1!ASN1_FreeDecoded` at `0x180008b31`
- `MSASN1!ASN1_CreateDecoder` at `0x180008ae9`
- `MSASN1!ASN1_CreateDecoder` at `0x180008ae9`
- `MSASN1!ASN1_CloseDecoder` at `0x180008b41`
- `MSASN1!ASN1_CloseDecoder` at `0x180008b41`
- `MSASN1!ASN1_CreateModule` at `0x180008ac0`
- `MSASN1!ASN1_CreateModule` at `0x180008ac0`

## pseudocode

```c
void __fastcall KerbFreeData(unsigned int a1, __int64 a2)
{
  __int64 Module; // rax
  unsigned int v5; // eax
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    v6 = 0;
    if ( fKRB5ModuleStarted )
    {
      Module = KRB5_Module;
    }
    else
    {
      fKRB5ModuleStarted = 1;
      Module = ASN1_CreateModule(0x10000, 1024, 4096, 81, off_18002A2E0, off_18002A050, off_18002A570, L"\b", 895644267);
      KRB5_Module = Module;
    }
    v5 = ASN1_CreateDecoder(Module, &v6, 0, 0, 0);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v5);
    }
    else
    {
      ASN1_FreeDecoded(v6, a2, a1);
      if ( v6 )
        ASN1_CloseDecoder();
    }
  }
}

```

## disassembly

```asm
0x180008a40  test    rdx, rdx
0x180008a43  jz      locret_180008B56
0x180008a49  mov     r11, rsp
0x180008a4c  mov     [r11+8], rbx
0x180008a50  mov     [r11+18h], rsi
0x180008a54  push    rdi
0x180008a55  sub     rsp, 50h
0x180008a59  xor     esi, esi
0x180008a5b  mov     rbx, rdx
0x180008a5e  cmp     cs:?fKRB5ModuleStarted@@3HA, esi; int fKRB5ModuleStarted
0x180008a64  mov     edi, ecx
0x180008a66  mov     [r11+10h], rsi
0x180008a6a  jnz     short loc_180008ACF
0x180008a6c  mov     [rsp+58h+var_18], 3562726Bh
0x180008a74  lea     rax, asc_18002D920; "\b"
0x180008a7b  mov     [r11-20h], rax
0x180008a7f  mov     edx, 400h
0x180008a84  lea     rax, off_18002A570
0x180008a8b  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180008a95  mov     [r11-28h], rax
0x180008a99  mov     ecx, 10000h
0x180008a9e  lea     rax, off_18002A050
0x180008aa5  mov     r9d, 51h ; 'Q'
0x180008aab  mov     [r11-30h], rax
0x180008aaf  mov     r8d, 1000h
0x180008ab5  lea     rax, off_18002A2E0
0x180008abc  mov     [r11-38h], rax
0x180008ac0  call    cs:__imp_ASN1_CreateModule
0x180008ac6  mov     cs:KRB5_Module, rax
0x180008acd  jmp     short loc_180008AD6
0x180008acf  mov     rax, cs:KRB5_Module
0x180008ad6  xor     r9d, r9d
0x180008ad9  mov     [rsp+58h+var_38], rsi
0x180008ade  xor     r8d, r8d
0x180008ae1  lea     rdx, [rsp+58h+arg_8]
0x180008ae6  mov     rcx, rax
0x180008ae9  call    cs:__imp_ASN1_CreateDecoder
0x180008aef  test    eax, eax
0x180008af1  jz      short loc_180008B26
0x180008af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008afa  lea     rdx, WPP_GLOBAL_Control
0x180008b01  cmp     rcx, rdx
0x180008b04  jz      short loc_180008B47
0x180008b06  test    byte ptr [rcx+1Ch], 1
0x180008b0a  jz      short loc_180008B47
0x180008b0c  mov     rcx, [rcx+10h]
0x180008b10  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180008b17  mov     edx, 24h ; '$'
0x180008b1c  mov     r9d, eax
0x180008b1f  call    WPP_SF_d
0x180008b24  jmp     short loc_180008B47
0x180008b26  mov     rcx, [rsp+58h+arg_8]
0x180008b2b  mov     r8d, edi
0x180008b2e  mov     rdx, rbx
0x180008b31  call    cs:__imp_ASN1_FreeDecoded
0x180008b37  mov     rcx, [rsp+58h+arg_8]
0x180008b3c  test    rcx, rcx
0x180008b3f  jz      short loc_180008B47
0x180008b41  call    cs:__imp_ASN1_CloseDecoder
0x180008b47  mov     rbx, [rsp+58h+arg_0]
0x180008b4c  mov     rsi, [rsp+58h+arg_10]
0x180008b51  add     rsp, 50h
0x180008b55  pop     rdi
0x180008b56  retn
```
