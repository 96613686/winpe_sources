# KerbInitAsn(ASN1encoding_s * *,ASN1decoding_s * *)

- ea: `0x18007e61c`
- end: `0x18007e715`
- name: `?KerbInitAsn@@YAJPEAPEAUASN1encoding_s@@PEAPEAUASN1decoding_s@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct ASN1encoding_s **, struct ASN1decoding_s **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18007f5c4`
- `0x18007f78c`
- `0x18007fa48`

## callees

- `0x1800101ec`
- `0x18007e61c`

## import_xrefs

- `MSASN1!ASN1_CreateEncoder` at `0x18007e6bb`
- `MSASN1!ASN1_CreateEncoder` at `0x18007e6bb`
- `MSASN1!ASN1_CreateDecoder` at `0x18007e6c6`
- `MSASN1!ASN1_CreateDecoder` at `0x18007e6c6`
- `MSASN1!ASN1_CreateModule` at `0x18007e68b`
- `MSASN1!ASN1_CreateModule` at `0x18007e68b`

## pseudocode

```c
__int64 __fastcall KerbInitAsn(struct ASN1encoding_s **a1, struct ASN1decoding_s **a2)
{
  __int64 Module; // rax
  unsigned int Encoder; // eax
  unsigned int v6; // ebx

  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               81,
               off_18009D520,
               off_18009D290,
               off_18009D7B0,
               qword_1800A5110,
               895644267);
    KRB5_Module = Module;
  }
  if ( a1 )
    Encoder = ASN1_CreateEncoder(Module, a1, 0, 0, 0);
  else
    Encoder = ASN1_CreateDecoder(Module, a2, 0, 0, 0);
  if ( Encoder )
  {
    v6 = 60;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, Encoder);
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18007e61c  mov     r11, rsp
0x18007e61f  mov     [r11+8], rbx
0x18007e623  push    rdi
0x18007e624  sub     rsp, 50h
0x18007e628  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x18007e62f  mov     rdi, rdx
0x18007e632  mov     rbx, rcx
0x18007e635  jnz     short loc_18007E69A
0x18007e637  mov     [rsp+58h+var_18], 3562726Bh
0x18007e63f  lea     rax, qword_1800A5110
0x18007e646  mov     [r11-20h], rax
0x18007e64a  mov     edx, 400h
0x18007e64f  lea     rax, off_18009D7B0
0x18007e656  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18007e660  mov     [r11-28h], rax
0x18007e664  mov     r9d, 51h ; 'Q'
0x18007e66a  lea     rax, off_18009D290
0x18007e671  mov     r8d, 1000h
0x18007e677  mov     [r11-30h], rax
0x18007e67b  mov     ecx, 10000h
0x18007e680  lea     rax, off_18009D520
0x18007e687  mov     [r11-38h], rax
0x18007e68b  call    cs:__imp_ASN1_CreateModule
0x18007e691  mov     cs:KRB5_Module, rax
0x18007e698  jmp     short loc_18007E6A1
0x18007e69a  mov     rax, cs:KRB5_Module
0x18007e6a1  xor     r9d, r9d
0x18007e6a4  mov     [rsp+58h+var_38], 0
0x18007e6ad  xor     r8d, r8d
0x18007e6b0  mov     rcx, rax
0x18007e6b3  test    rbx, rbx
0x18007e6b6  jz      short loc_18007E6C3
0x18007e6b8  mov     rdx, rbx
0x18007e6bb  call    cs:__imp_ASN1_CreateEncoder
0x18007e6c1  jmp     short loc_18007E6CC
0x18007e6c3  mov     rdx, rdi
0x18007e6c6  call    cs:__imp_ASN1_CreateDecoder
0x18007e6cc  test    eax, eax
0x18007e6ce  jz      short loc_18007E706
0x18007e6d0  mov     ebx, 3Ch ; '<'
0x18007e6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e6dc  lea     rdx, WPP_GLOBAL_Control
0x18007e6e3  cmp     rcx, rdx
0x18007e6e6  jz      short loc_18007E708
0x18007e6e8  test    byte ptr [rcx+1Ch], 1
0x18007e6ec  jz      short loc_18007E708
0x18007e6ee  mov     rcx, [rcx+10h]
0x18007e6f2  lea     edx, [rbx-18h]
0x18007e6f5  mov     r9d, eax
0x18007e6f8  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18007e6ff  call    WPP_SF_d
0x18007e704  jmp     short loc_18007E708
0x18007e706  xor     ebx, ebx
0x18007e708  mov     eax, ebx
0x18007e70a  mov     rbx, [rsp+58h+arg_0]
0x18007e70f  add     rsp, 50h
0x18007e713  pop     rdi
0x18007e714  retn
```
