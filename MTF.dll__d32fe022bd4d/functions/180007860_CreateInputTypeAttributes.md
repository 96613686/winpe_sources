# CreateInputTypeAttributes

- ea: `0x180007860`
- end: `0x1800078b5`
- name: `CreateInputTypeAttributes`
- size: `85`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006074`
- `0x180007730`
- `0x180007860`

## string_xrefs

- `0x180007895`: `mincore\textinput\dev\mtf\dll\com.cpp`

## pseudocode

```c
__int64 __fastcall CreateInputTypeAttributes(void **a1)
{
  int Instance; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
    return 2147500035LL;
  Instance = MtfClassFactoryBase::CreateInstance(
               (MtfClassFactoryBase *)&ipx::mtf::g_oInputTypeAttributesFactory,
               0,
               &GUID_b0445657_7c61_42bc_a254_07b1c55f63b0,
               a1);
  v3 = Instance;
  if ( Instance >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x73,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\dll\\com.cpp",
    (const char *)(unsigned int)Instance,
    v4);
  return v3;
}

```

## disassembly

```asm
0x180007860  push    rbx; int
0x180007862  sub     rsp, 20h
0x180007866  test    rcx, rcx
0x180007869  jnz     short loc_180007872
0x18000786b  mov     eax, 80004003h
0x180007870  jmp     short loc_1800078AF
0x180007872  mov     r9, rcx; void **
0x180007875  lea     r8, _GUID_b0445657_7c61_42bc_a254_07b1c55f63b0; struct _GUID *
0x18000787c  lea     rcx, ?g_oInputTypeAttributesFactory@mtf@ipx@@3VInputTypeAttributesFactory@12@A; this
0x180007883  xor     edx, edx; struct IUnknown *
0x180007885  call    ?CreateInstance@MtfClassFactoryBase@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; MtfClassFactoryBase::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000788a  mov     ebx, eax
0x18000788c  test    eax, eax
0x18000788e  jns     short loc_1800078AD
0x180007890  mov     rcx, [rsp+28h]; this
0x180007895  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\mtf\\dll\\com."...
0x18000789c  mov     r9d, eax; char *
0x18000789f  mov     edx, 73h ; 's'; void *
0x1800078a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078a9  mov     eax, ebx
0x1800078ab  jmp     short loc_1800078AF
0x1800078ad  xor     eax, eax
0x1800078af  add     rsp, 20h
0x1800078b3  pop     rbx
0x1800078b4  retn
```
