# CPersistStreamInit::WriteVARIANTColumnDataToStream(tagVARIANT *,uchar,uchar)

- ea: `0x18001f4a0`
- end: `0x18001f5bb`
- name: `?WriteVARIANTColumnDataToStream@CPersistStreamInit@@AEAAJPEAUtagVARIANT@@EE@Z`
- size: `283`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, VARIANTARG *pvarg, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c994`

## callees

- `0x18001ac00`
- `0x18001c934`
- `0x18001f4a0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001f569`
- `OLEAUT32!__imp_VariantInit` at `0x18001f569`
- `OLEAUT32!__imp_VariantClear` at `0x18001f597`
- `OLEAUT32!__imp_VariantClear` at `0x18001f597`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteVARIANTColumnDataToStream(CPersistStreamInit *this, VARIANTARG *pvarg)
{
  VARTYPE vt; // r10
  int v5; // edx
  __int64 result; // rax
  unsigned int v7; // edi
  unsigned __int16 *bstrVal; // [rsp+98h] [rbp+10h] BYREF

  vt = pvarg->vt;
  v5 = pvarg->vt - 1;
  if ( !v5 )
    return 2147500037LL;
  if ( v5 == 8208 )
  {
    v7 = CPersistStreamInit::BinaryOut(this, *(unsigned __int8 **)(pvarg->llVal + 16), *(_DWORD *)(pvarg->llVal + 24));
    goto LABEL_9;
  }
  bstrVal = 0;
  if ( vt == 8 )
  {
    v7 = 0;
    bstrVal = pvarg->bstrVal;
    VariantInit(pvarg);
    goto LABEL_7;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 12);
  v7 = result;
  if ( (int)result >= 0 )
  {
LABEL_7:
    CPersistStreamInit::WriteBSTRColumnDataToStream(this, &bstrVal);
LABEL_9:
    VariantClear(pvarg);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001f4a0  mov     rax, rsp
0x18001f4a3  mov     [rax+8], rbx
0x18001f4a7  mov     [rax+18h], rsi
0x18001f4ab  push    rdi
0x18001f4ac  sub     rsp, 80h
0x18001f4b3  movzx   r10d, word ptr [rdx]
0x18001f4b7  mov     rbx, rdx
0x18001f4ba  mov     edx, r10d
0x18001f4bd  mov     qword ptr [rax-18h], 0
0x18001f4c5  mov     r11b, r8b
0x18001f4c8  mov     rsi, rcx
0x18001f4cb  sub     edx, 1
0x18001f4ce  jz      loc_18001F5A1
0x18001f4d4  cmp     edx, 2010h
0x18001f4da  jz      loc_18001F581
0x18001f4e0  mov     r8d, 8
0x18001f4e6  mov     qword ptr [rax+10h], 0
0x18001f4ee  cmp     r10w, r8w
0x18001f4f2  jz      short loc_18001F558
0x18001f4f4  mov     rcx, [rcx+28h]
0x18001f4f8  lea     r10, [rsp+88h+arg_8]
0x18001f500  mov     [rsp+88h+var_28], 0
0x18001f508  lea     edx, [r8+4]
0x18001f50c  mov     [rsp+88h+var_30], r9b
0x18001f511  lea     r9d, [r8+10h]
0x18001f515  mov     [rsp+88h+var_38], r11b
0x18001f51a  mov     rax, [rcx]
0x18001f51d  mov     [rsp+88h+var_40], 0
0x18001f526  mov     [rsp+88h+var_48], 0
0x18001f52e  mov     [rsp+88h+var_50], r9
0x18001f533  mov     rax, [rax+18h]
0x18001f537  mov     [rsp+88h+var_58], r10
0x18001f53c  lea     r10, [rsp+88h+var_18]
0x18001f541  mov     [rsp+88h+var_60], rbx
0x18001f546  mov     [rsp+88h+var_68], r10
0x18001f54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f550  mov     edi, eax
0x18001f552  test    eax, eax
0x18001f554  jns     short loc_18001F56F
0x18001f556  jmp     short loc_18001F5A6
0x18001f558  mov     rax, [rbx+8]
0x18001f55c  xor     edi, edi
0x18001f55e  mov     rcx, rbx; pvarg
0x18001f561  mov     [rsp+88h+arg_8], rax
0x18001f569  call    cs:__imp_VariantInit
0x18001f56f  lea     rdx, [rsp+88h+arg_8]; unsigned __int16 **
0x18001f577  mov     rcx, rsi; this
0x18001f57a  call    ?WriteBSTRColumnDataToStream@CPersistStreamInit@@AEAAJPEAPEAG@Z; CPersistStreamInit::WriteBSTRColumnDataToStream(ushort * *)
0x18001f57f  jmp     short loc_18001F594
0x18001f581  mov     rdx, [rbx+8]
0x18001f585  mov     r8d, [rdx+18h]; unsigned int
0x18001f589  mov     rdx, [rdx+10h]; unsigned __int8 *
0x18001f58d  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001f592  mov     edi, eax
0x18001f594  mov     rcx, rbx; pvarg
0x18001f597  call    cs:__imp_VariantClear
0x18001f59d  mov     eax, edi
0x18001f59f  jmp     short loc_18001F5A6
0x18001f5a1  mov     eax, 80004005h
0x18001f5a6  lea     r11, [rsp+88h+var_8]
0x18001f5ae  mov     rbx, [r11+10h]
0x18001f5b2  mov     rsi, [r11+20h]
0x18001f5b6  mov     rsp, r11
0x18001f5b9  pop     rdi
0x18001f5ba  retn
```
