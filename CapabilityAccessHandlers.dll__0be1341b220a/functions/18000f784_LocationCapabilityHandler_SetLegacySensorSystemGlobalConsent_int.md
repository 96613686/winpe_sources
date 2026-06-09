# LocationCapabilityHandler::SetLegacySensorSystemGlobalConsent(int)

- ea: `0x18000f784`
- end: `0x18000f885`
- name: `?SetLegacySensorSystemGlobalConsent@LocationCapabilityHandler@@CAJH@Z`
- size: `257`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f530`

## callees

- `0x1800090f4`
- `0x18000f784`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f7b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f7b6`

## pseudocode

```c
__int64 __fastcall LocationCapabilityHandler::SetLegacySensorSystemGlobalConsent(unsigned int a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rcx
  int v6; // eax
  LPVOID v7; // rcx
  LPVOID v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v2 = CoCreateInstance(
         &GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd,
         0,
         4u,
         &GUID_bb31bcf1_230a_4bea_abef_26a3887f122a,
         &v10);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (int)"onecore\\base\\devices\\cam\\handler\\location\\locationcapabilityhandler.cpp",
      (const char *)(unsigned int)v2);
    v4 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v10 + 208LL))(v10, a1);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (int)"onecore\\base\\devices\\cam\\handler\\location\\locationcapabilityhandler.cpp",
      (const char *)(unsigned int)v6);
    v7 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v3;
  }
  v8 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f784  mov     r11, rsp
0x18000f787  mov     [r11+8], rbx
0x18000f78b  push    rdi
0x18000f78c  sub     rsp, 30h
0x18000f790  mov     edi, ecx
0x18000f792  mov     qword ptr [r11+10h], 0
0x18000f79a  lea     rax, [r11+10h]
0x18000f79e  mov     [r11-18h], rax
0x18000f7a2  lea     r9, _GUID_bb31bcf1_230a_4bea_abef_26a3887f122a; riid
0x18000f7a9  xor     edx, edx; pUnkOuter
0x18000f7ab  lea     r8d, [rdx+4]; dwClsContext
0x18000f7af  lea     rcx, _GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd; rclsid
0x18000f7b6  call    cs:__imp_CoCreateInstance
0x18000f7bc  mov     ebx, eax
0x18000f7be  test    eax, eax
0x18000f7c0  jns     short loc_18000F800
0x18000f7c2  mov     rcx, [rsp+38h]; this
0x18000f7c7  mov     r9d, eax; char *
0x18000f7ca  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\handler\\l"...
0x18000f7d1  mov     edx, 3Ah ; ':'; void *
0x18000f7d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7db  nop
0x18000f7dc  mov     rcx, [rsp+38h+arg_8]
0x18000f7e1  test    rcx, rcx
0x18000f7e4  jz      short loc_18000F7FC
0x18000f7e6  mov     [rsp+38h+arg_8], 0
0x18000f7ef  mov     rax, [rcx]
0x18000f7f2  mov     rax, [rax+10h]
0x18000f7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7fb  nop
0x18000f7fc  mov     eax, ebx
0x18000f7fe  jmp     short loc_18000F87A
0x18000f800  mov     rcx, [rsp+38h+arg_8]
0x18000f805  mov     rax, [rcx]
0x18000f808  mov     edx, edi
0x18000f80a  mov     rax, [rax+0D0h]
0x18000f811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f816  mov     ebx, eax
0x18000f818  test    eax, eax
0x18000f81a  jns     short loc_18000F858
0x18000f81c  mov     rcx, [rsp+38h]; this
0x18000f821  mov     r9d, eax; char *
0x18000f824  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\handler\\l"...
0x18000f82b  mov     edx, 3Bh ; ';'; void *
0x18000f830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f835  nop
0x18000f836  mov     rcx, [rsp+38h+arg_8]
0x18000f83b  test    rcx, rcx
0x18000f83e  jz      short loc_18000F856
0x18000f840  mov     [rsp+38h+arg_8], 0
0x18000f849  mov     rax, [rcx]
0x18000f84c  mov     rax, [rax+10h]
0x18000f850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f855  nop
0x18000f856  jmp     short loc_18000F7FC
0x18000f858  mov     rcx, [rsp+38h+arg_8]
0x18000f85d  test    rcx, rcx
0x18000f860  jz      short loc_18000F878
0x18000f862  mov     [rsp+38h+arg_8], 0
0x18000f86b  mov     rax, [rcx]
0x18000f86e  mov     rax, [rax+10h]
0x18000f872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f877  nop
0x18000f878  xor     eax, eax
0x18000f87a  mov     rbx, [rsp+38h+arg_0]
0x18000f87f  add     rsp, 30h
0x18000f883  pop     rdi
0x18000f884  retn
```
