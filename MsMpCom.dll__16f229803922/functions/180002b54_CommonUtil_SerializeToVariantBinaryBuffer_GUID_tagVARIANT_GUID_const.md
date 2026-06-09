# CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(tagVARIANT *,_GUID const &)

- ea: `0x180002b54`
- end: `0x180002bff`
- name: `??$SerializeToVariantBinaryBuffer@U_GUID@@@CommonUtil@@YAJPEAUtagVARIANT@@AEBU_GUID@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(VARIANTARG *, const void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003110`
- `0x180005260`

## callees

- `0x180001cf2`
- `0x180002b54`
- `0x180004b54`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180002b75`
- `OLEAUT32!__imp_VariantInit` at `0x180002b75`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002b91`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002b91`

## pseudocode

```c
__int64 __fastcall CommonUtil::SerializeToVariantBinaryBuffer<_GUID>(VARIANTARG *a1, const void *a2)
{
  __int64 result; // rax
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rsi
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  VariantInit(a1);
  rgsabound = (SAFEARRAYBOUND)16LL;
  v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v6 = v5;
  if ( v5 )
  {
    memmove_0(v5->pvData, a2, 0x10u);
    result = 0;
    a1->vt = 8209;
    a1->llVal = (LONGLONG)v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002b54  mov     [rsp+arg_0], rbx
0x180002b59  mov     [rsp+arg_8], rsi
0x180002b5e  push    rdi
0x180002b5f  sub     rsp, 20h
0x180002b63  mov     rdi, rdx
0x180002b66  mov     rbx, rcx
0x180002b69  test    rdx, rdx
0x180002b6c  jnz     short loc_180002B75
0x180002b6e  mov     eax, 80070057h
0x180002b73  jmp     short loc_180002BEF
0x180002b75  call    cs:__imp_VariantInit
0x180002b7b  mov     ecx, 11h; vt
0x180002b80  mov     qword ptr [rsp+28h+rgsabound.cElements], 10h
0x180002b89  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180002b8e  lea     edx, [rcx-10h]; cDims
0x180002b91  call    cs:__imp_SafeArrayCreate
0x180002b97  mov     rsi, rax
0x180002b9a  test    rax, rax
0x180002b9d  jnz     short loc_180002BD2
0x180002b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ba6  lea     rax, WPP_GLOBAL_Control
0x180002bad  cmp     rcx, rax
0x180002bb0  jz      short loc_180002BCB
0x180002bb2  test    byte ptr [rcx+1Ch], 1
0x180002bb6  jz      short loc_180002BCB
0x180002bb8  mov     rcx, [rcx+10h]
0x180002bbc  lea     edx, [rsi+0Eh]
0x180002bbf  lea     r8, WPP_1c756af73aa03d742fb0eb712210c2f8_Traceguids
0x180002bc6  call    WPP_SF_
0x180002bcb  mov     eax, 8007000Eh
0x180002bd0  jmp     short loc_180002BEF
0x180002bd2  mov     rcx, [rax+10h]; void *
0x180002bd6  mov     r8d, 10h; Size
0x180002bdc  mov     rdx, rdi; Src
0x180002bdf  call    memmove_0
0x180002be4  xor     eax, eax
0x180002be6  mov     word ptr [rbx], 2011h
0x180002beb  mov     [rbx+8], rsi
0x180002bef  mov     rbx, [rsp+28h+arg_0]
0x180002bf4  mov     rsi, [rsp+28h+arg_8]
0x180002bf9  add     rsp, 20h
0x180002bfd  pop     rdi
0x180002bfe  retn
```
