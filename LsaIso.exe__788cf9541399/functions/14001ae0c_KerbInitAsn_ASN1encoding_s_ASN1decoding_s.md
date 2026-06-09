# KerbInitAsn(ASN1encoding_s * *,ASN1decoding_s * *)

- ea: `0x14001ae0c`
- end: `0x14001af05`
- name: `?KerbInitAsn@@YAJPEAPEAUASN1encoding_s@@PEAPEAUASN1decoding_s@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct ASN1encoding_s **, struct ASN1decoding_s **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001b770`
- `0x14001b834`
- `0x14001b92c`

## callees

- `0x140011964`
- `0x14001ae0c`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x14001ae7b`
- `MSASN1!ASN1_CreateModule` at `0x14001ae7b`
- `MSASN1!ASN1_CreateDecoder` at `0x14001aeb6`
- `MSASN1!ASN1_CreateDecoder` at `0x14001aeb6`
- `MSASN1!ASN1_CreateEncoder` at `0x14001aeab`
- `MSASN1!ASN1_CreateEncoder` at `0x14001aeab`

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
               off_14003C450,
               off_14003C1C0,
               off_14003C6E0,
               qword_14004A220,
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
0x14001ae0c  mov     r11, rsp
0x14001ae0f  mov     [r11+8], rbx
0x14001ae13  push    rdi
0x14001ae14  sub     rsp, 50h
0x14001ae18  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x14001ae1f  mov     rdi, rdx
0x14001ae22  mov     rbx, rcx
0x14001ae25  jnz     short loc_14001AE8A
0x14001ae27  mov     [rsp+58h+var_18], 3562726Bh
0x14001ae2f  lea     rax, qword_14004A220
0x14001ae36  mov     [r11-20h], rax
0x14001ae3a  mov     edx, 400h
0x14001ae3f  lea     rax, off_14003C6E0
0x14001ae46  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x14001ae50  mov     [r11-28h], rax
0x14001ae54  mov     r9d, 51h ; 'Q'
0x14001ae5a  lea     rax, off_14003C1C0
0x14001ae61  mov     r8d, 1000h
0x14001ae67  mov     [r11-30h], rax
0x14001ae6b  mov     ecx, 10000h
0x14001ae70  lea     rax, off_14003C450
0x14001ae77  mov     [r11-38h], rax
0x14001ae7b  call    cs:__imp_ASN1_CreateModule
0x14001ae81  mov     cs:KRB5_Module, rax
0x14001ae88  jmp     short loc_14001AE91
0x14001ae8a  mov     rax, cs:KRB5_Module
0x14001ae91  xor     r9d, r9d
0x14001ae94  mov     [rsp+58h+var_38], 0
0x14001ae9d  xor     r8d, r8d
0x14001aea0  mov     rcx, rax
0x14001aea3  test    rbx, rbx
0x14001aea6  jz      short loc_14001AEB3
0x14001aea8  mov     rdx, rbx
0x14001aeab  call    cs:__imp_ASN1_CreateEncoder
0x14001aeb1  jmp     short loc_14001AEBC
0x14001aeb3  mov     rdx, rdi
0x14001aeb6  call    cs:__imp_ASN1_CreateDecoder
0x14001aebc  test    eax, eax
0x14001aebe  jz      short loc_14001AEF6
0x14001aec0  mov     ebx, 3Ch ; '<'
0x14001aec5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aecc  lea     rdx, WPP_GLOBAL_Control
0x14001aed3  cmp     rcx, rdx
0x14001aed6  jz      short loc_14001AEF8
0x14001aed8  test    byte ptr [rcx+1Ch], 1
0x14001aedc  jz      short loc_14001AEF8
0x14001aede  mov     rcx, [rcx+10h]
0x14001aee2  lea     edx, [rbx-18h]
0x14001aee5  mov     r9d, eax
0x14001aee8  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x14001aeef  call    WPP_SF_d
0x14001aef4  jmp     short loc_14001AEF8
0x14001aef6  xor     ebx, ebx
0x14001aef8  mov     eax, ebx
0x14001aefa  mov     rbx, [rsp+58h+arg_0]
0x14001aeff  add     rsp, 50h
0x14001af03  pop     rdi
0x14001af04  retn
```
