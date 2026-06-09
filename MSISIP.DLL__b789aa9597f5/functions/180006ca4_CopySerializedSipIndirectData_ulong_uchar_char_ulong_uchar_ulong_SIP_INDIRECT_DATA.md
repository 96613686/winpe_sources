# CopySerializedSipIndirectData(ulong,uchar *,char *,ulong,uchar *,ulong,SIP_INDIRECT_DATA_ *)

- ea: `0x180006ca4`
- end: `0x180006dda`
- name: `?CopySerializedSipIndirectData@@YAKKPEAEPEADK0KPEAUSIP_INDIRECT_DATA_@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(size_t Size, unsigned __int8 *, size_t *, unsigned int, unsigned __int8 *Src, unsigned int, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011c0`

## callees

- `0x180006ca4`
- `0x180006de0`
- `0x18000d2c2`

## pseudocode

```c
__int64 __fastcall CopySerializedSipIndirectData(
        size_t Size,
        unsigned __int8 *a2,
        size_t *a3,
        unsigned int a4,
        unsigned __int8 *Src,
        unsigned int a6,
        struct SIP_INDIRECT_DATA_ *a7)
{
  size_t v8; // rbp
  __int64 v9; // r14
  int v10; // eax
  struct SIP_INDIRECT_DATA_ *v11; // r10
  __int64 result; // rax
  CHAR *v13; // r10
  const void *v14; // r11
  BYTE *v15; // r12
  size_t *v16; // r8
  int v17; // edi
  __int64 v18; // r11
  __int64 v19; // rcx
  CHAR *v20; // r10
  int v21; // r11d
  CHAR *v22; // rbx
  size_t v23; // [rsp+20h] [rbp-58h]
  size_t v24; // [rsp+20h] [rbp-58h]

  v8 = a4;
  v9 = (unsigned int)Size;
  v10 = a6 - 64;
  if ( (int)(a6 - 64) >= 23 )
  {
    v11 = a7 + 1;
    if ( (unsigned __int64)v10 > 0x7FFFFFFF )
    {
      LOWORD(result) = 87;
      goto LABEL_17;
    }
    LODWORD(result) = StringCopyWorkerA((STRSAFE_LPSTR)&a7[1], v10, a3, "1.3.6.1.4.1.311.2.1.30", v23);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    a7->Data.pszObjId = v13;
    if ( a6 - 87 >= (unsigned int)v9 )
    {
      v15 = (BYTE *)(v13 + 23);
      memcpy_0(v13 + 23, v14, (unsigned int)v9);
      v17 = a6 - 87 - v9;
      a7->Data.Value.pbData = v15;
      v18 = -1;
      a7->Data.Value.cbData = v9;
      do
        ++v18;
      while ( *((_BYTE *)a3 + v18) );
      if ( v17 >= (int)v18 + 1 )
      {
        v11 = (struct SIP_INDIRECT_DATA_ *)&v15[v9];
        if ( v17 )
        {
          v19 = v17;
          if ( (unsigned __int64)v17 <= 0x7FFFFFFF )
          {
            LODWORD(result) = StringCopyWorkerA((STRSAFE_LPSTR)&v15[v9], v17, v16, (STRSAFE_PCNZCH)a3, v24);
            if ( (int)result >= 0 )
            {
              a7->DigestAlgorithm.pszObjId = v20;
              a7->DigestAlgorithm.Parameters.cbData = 0;
              a7->DigestAlgorithm.Parameters.pbData = 0;
              if ( v17 - v21 >= (unsigned int)v8 )
              {
                v22 = &v20[v21];
                memcpy_0(v22, Src, v8);
                result = 0;
                a7->Digest.pbData = (BYTE *)v22;
                a7->Digest.cbData = v8;
                return result;
              }
              return 122;
            }
            return (unsigned __int16)result;
          }
        }
        else
        {
          v19 = 0;
        }
        LOWORD(result) = 87;
        if ( !v19 )
          return (unsigned __int16)result;
LABEL_17:
        LOBYTE(v11->Data.pszObjId) = 0;
        return (unsigned __int16)result;
      }
    }
  }
  return 122;
}

```

## disassembly

```asm
0x180006ca4  push    rbx
0x180006ca6  push    rbp
0x180006ca7  push    rsi
0x180006ca8  push    rdi
0x180006ca9  push    r12
0x180006cab  push    r13
0x180006cad  push    r14
0x180006caf  push    r15
0x180006cb1  sub     rsp, 38h
0x180006cb5  mov     edi, [rsp+78h+arg_28]
0x180006cbc  mov     r15, r8
0x180006cbf  mov     ebp, r9d
0x180006cc2  mov     r11, rdx
0x180006cc5  mov     r14d, ecx
0x180006cc8  lea     eax, [rdi-40h]
0x180006ccb  cmp     eax, 17h
0x180006cce  jl      loc_180006DC4
0x180006cd4  mov     rsi, [rsp+78h+arg_30]
0x180006cdc  movsxd  rdx, eax; cchDest
0x180006cdf  lea     r10, [rsi+40h]
0x180006ce3  cmp     rdx, 7FFFFFFFh
0x180006cea  ja      loc_180006DB5
0x180006cf0  lea     r9, pszSrc; "1.3.6.1.4.1.311.2.1.30"
0x180006cf7  mov     rcx, r10; pszDest
0x180006cfa  call    StringCopyWorkerA
0x180006cff  xor     ebx, ebx
0x180006d01  test    eax, eax
0x180006d03  js      loc_180006DBF
0x180006d09  add     edi, 0FFFFFFA9h
0x180006d0c  mov     [rsi], r10
0x180006d0f  cmp     edi, r14d
0x180006d12  jb      loc_180006DC4
0x180006d18  lea     r12, [r10+17h]
0x180006d1c  mov     r8d, r14d; Size
0x180006d1f  mov     rcx, r12; void *
0x180006d22  mov     rdx, r11; Src
0x180006d25  call    memcpy_0
0x180006d2a  sub     edi, r14d
0x180006d2d  mov     [rsi+10h], r12
0x180006d31  or      r11, 0FFFFFFFFFFFFFFFFh
0x180006d35  mov     [rsi+8], r14d
0x180006d39  inc     r11
0x180006d3c  cmp     [r15+r11], bl
0x180006d40  jnz     short loc_180006D39
0x180006d42  inc     r11d
0x180006d45  cmp     edi, r11d
0x180006d48  jl      short loc_180006DC4
0x180006d4a  lea     r10, [r12+r14]
0x180006d4e  test    edi, edi
0x180006d50  jz      short loc_180006DA6
0x180006d52  movsxd  rcx, edi
0x180006d55  cmp     rcx, 7FFFFFFFh
0x180006d5c  ja      short loc_180006DA9
0x180006d5e  mov     rdx, rcx; cchDest
0x180006d61  mov     r9, r15; pszSrc
0x180006d64  mov     rcx, r10; pszDest
0x180006d67  call    StringCopyWorkerA
0x180006d6c  test    eax, eax
0x180006d6e  js      short loc_180006DBF
0x180006d70  sub     edi, r11d
0x180006d73  mov     [rsi+18h], r10
0x180006d77  mov     [rsi+20h], ebx
0x180006d7a  mov     [rsi+28h], rbx
0x180006d7e  cmp     edi, ebp
0x180006d80  jb      short loc_180006DC4
0x180006d82  mov     rdx, [rsp+78h+Src]; Src
0x180006d8a  mov     r8, rbp; Size
0x180006d8d  movsxd  rbx, r11d
0x180006d90  add     rbx, r10
0x180006d93  mov     rcx, rbx; void *
0x180006d96  call    memcpy_0
0x180006d9b  xor     eax, eax
0x180006d9d  mov     [rsi+38h], rbx
0x180006da1  mov     [rsi+30h], ebp
0x180006da4  jmp     short loc_180006DC9
0x180006da6  mov     rcx, rbx
0x180006da9  mov     eax, 80070057h
0x180006dae  test    rcx, rcx
0x180006db1  jnz     short loc_180006DBC
0x180006db3  jmp     short loc_180006DBF
0x180006db5  xor     ebx, ebx
0x180006db7  mov     eax, 80070057h
0x180006dbc  mov     [r10], bl
0x180006dbf  movzx   eax, ax
0x180006dc2  jmp     short loc_180006DC9
0x180006dc4  mov     eax, 7Ah ; 'z'
0x180006dc9  add     rsp, 38h
0x180006dcd  pop     r15
0x180006dcf  pop     r14
0x180006dd1  pop     r13
0x180006dd3  pop     r12
0x180006dd5  pop     rdi
0x180006dd6  pop     rsi
0x180006dd7  pop     rbp
0x180006dd8  pop     rbx
0x180006dd9  retn
```
