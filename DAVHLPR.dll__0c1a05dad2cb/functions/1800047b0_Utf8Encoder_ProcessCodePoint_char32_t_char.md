# Utf8Encoder::ProcessCodePoint(char32_t,char &)

- ea: `0x1800047b0`
- end: `0x18000481b`
- name: `?ProcessCodePoint@Utf8Encoder@@QEAAK_UAEAD@Z`
- size: `107`
- prototype: `__int64 __fastcall(Utf8Encoder *this, unsigned int, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001830`

## callees

- `0x1800047b0`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall Utf8Encoder::ProcessCodePoint(Utf8Encoder *this, unsigned int a2, char *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  Utf8Encoder *v5; // rdx
  __int64 result; // rax
  char v7; // r10
  char v8; // al

  LOBYTE(v3) = *(_BYTE *)this;
  v4 = a2;
  v5 = this;
  if ( *(_BYTE *)this )
  {
    v7 = 0x80;
    goto LABEL_7;
  }
  if ( (unsigned int)v4 < 0x80 )
  {
    result = 0;
    *a3 = v4;
    return result;
  }
  result = GetUtf8EncodedCodeUnitCountForCodePoint((unsigned int)v4, this, a3, v4);
  if ( !(_DWORD)result )
  {
    v3 = *(unsigned __int8 *)v5;
    v7 = byte_1800076E0[2 * v3];
LABEL_7:
    v8 = v3 - 1;
    *(_BYTE *)v5 = v8;
    *a3 = v7 | ((unsigned int)v4 >> (6 * v8)) & 0x3F;
    return v8 != 0 ? 0xEA : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800047b0  sub     rsp, 28h
0x1800047b4  movzx   eax, byte ptr [rcx]
0x1800047b7  mov     r9d, edx
0x1800047ba  mov     rdx, rcx
0x1800047bd  test    al, al
0x1800047bf  jnz     short loc_1800047F1
0x1800047c1  cmp     r9d, 80h
0x1800047c8  jnb     short loc_1800047D4
0x1800047ca  xor     eax, eax
0x1800047cc  mov     [r8], r9b
0x1800047cf  add     rsp, 28h
0x1800047d3  retn
0x1800047d4  mov     ecx, r9d
0x1800047d7  call    GetUtf8EncodedCodeUnitCountForCodePoint
0x1800047dc  test    eax, eax
0x1800047de  jnz     short loc_180004816
0x1800047e0  movzx   eax, byte ptr [rdx]
0x1800047e3  lea     r10, byte_1800076E0
0x1800047ea  movzx   r10d, byte ptr [r10+rax*2]
0x1800047ef  jmp     short loc_1800047F4
0x1800047f1  mov     r10b, 80h
0x1800047f4  dec     al
0x1800047f6  movzx   eax, al
0x1800047f9  mov     [rdx], al
0x1800047fb  lea     ecx, [rax+rax*2]
0x1800047fe  add     ecx, ecx
0x180004800  shr     r9d, cl
0x180004803  and     r9b, 3Fh
0x180004807  or      r9b, r10b
0x18000480a  neg     al
0x18000480c  mov     [r8], r9b
0x18000480f  sbb     eax, eax
0x180004811  and     eax, 0EAh
0x180004816  add     rsp, 28h
0x18000481a  retn
```
