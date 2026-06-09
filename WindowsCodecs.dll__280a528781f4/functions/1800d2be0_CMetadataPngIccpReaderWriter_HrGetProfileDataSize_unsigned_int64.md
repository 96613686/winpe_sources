# CMetadataPngIccpReaderWriter::HrGetProfileDataSize(unsigned __int64 *)

- ea: `0x1800d2be0`
- end: `0x1800d2d40`
- name: `?HrGetProfileDataSize@CMetadataPngIccpReaderWriter@@MEAAJPEA_K@Z`
- size: `352`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d2b00`

## callees

- `0x18001dd10`
- `0x1800267d8`
- `0x18004c958`
- `0x18004ce08`
- `0x1800bb784`
- `0x1800d2be0`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2d28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2d28`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::HrGetProfileDataSize(
        CMetadataPngIccpReaderWriter *this,
        unsigned __int64 *a2)
{
  ULONGLONG v4; // rax
  SIZE_T v5; // rbx
  void *v6; // rsi
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned __int64 v9; // r14
  unsigned int v10; // eax
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  int v13; // [rsp+48h] [rbp-31h]
  void *v14; // [rsp+50h] [rbp-29h]
  unsigned int v15; // [rsp+58h] [rbp-21h]
  ULONGLONG pullResult; // [rsp+E0h] [rbp+67h] BYREF

  pullResult = 0;
  if ( ULongLongMult(*((_QWORD *)this + 22), 2u, &pullResult) >= 0 )
    v4 = pullResult;
  else
    v4 = *((_QWORD *)this + 22);
  v5 = 15;
  if ( v4 > 0xF )
    v5 = v4;
  v6 = CoTaskMemAlloc(v5);
  if ( v6 )
  {
    memset_0(&v12, 0, 0x58u);
    if ( !(unsigned int)deflateInit2_((unsigned int)&v12, -1, v8, 15, 8, 0, (__int64)"1.3.1", 88) )
    {
      v9 = 0;
      v12 = *((_QWORD *)this + 21);
      v13 = *((_DWORD *)this + 44);
      while ( 1 )
      {
        v15 = v5;
        v14 = v6;
        v10 = deflate(&v12, 4);
        if ( v10 > 1 )
          break;
        v9 += v5 - v15;
        if ( v10 )
        {
          if ( !v13 && !(unsigned int)deflateEnd(&v12) )
          {
            v7 = 0;
            *a2 = v9;
            goto LABEL_18;
          }
          break;
        }
      }
    }
    v7 = -2003292304;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2003292304);
LABEL_18:
    CoTaskMemFree(v6);
  }
  else
  {
    v7 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v7;
}

```

## disassembly

```asm
0x1800d2be0  push    rbp
0x1800d2be2  push    rbx
0x1800d2be3  push    rsi
0x1800d2be4  push    rdi
0x1800d2be5  push    r14
0x1800d2be7  push    r15
0x1800d2be9  lea     rbp, [rsp-2Fh]
0x1800d2bee  sub     rsp, 0A8h
0x1800d2bf5  mov     r15, rdx
0x1800d2bf8  mov     [rbp+57h+pullResult], 0
0x1800d2c00  mov     rdi, rcx
0x1800d2c03  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800d2c07  mov     rcx, [rcx+0B0h]; ullMultiplicand
0x1800d2c0e  mov     edx, 2; ullMultiplier
0x1800d2c13  call    ULongLongMult
0x1800d2c18  test    eax, eax
0x1800d2c1a  jns     short loc_1800D2C25
0x1800d2c1c  mov     rax, [rdi+0B0h]
0x1800d2c23  jmp     short loc_1800D2C29
0x1800d2c25  mov     rax, [rbp+57h+pullResult]
0x1800d2c29  mov     ebx, 0Fh
0x1800d2c2e  cmp     rax, rbx
0x1800d2c31  cmova   rbx, rax
0x1800d2c35  mov     rcx, rbx; cb
0x1800d2c38  call    cs:__imp_CoTaskMemAlloc
0x1800d2c3e  mov     rsi, rax
0x1800d2c41  test    rax, rax
0x1800d2c44  jnz     short loc_1800D2C63
0x1800d2c46  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d2c4c  mov     ebx, 8007000Eh
0x1800d2c51  jz      loc_1800D2D2E
0x1800d2c57  mov     ecx, ebx; int
0x1800d2c59  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2c5e  jmp     loc_1800D2D2E
0x1800d2c63  mov     r14d, 58h ; 'X'
0x1800d2c69  lea     rcx, [rbp+57h+var_90]; void *
0x1800d2c6d  mov     r8d, r14d; Size
0x1800d2c70  xor     edx, edx; Val
0x1800d2c72  call    memset_0
0x1800d2c77  mov     [rsp+0D0h+var_98], r14d
0x1800d2c7c  lea     rax, a131; "1.3.1"
0x1800d2c83  mov     [rsp+0D0h+var_A0], rax
0x1800d2c88  lea     r9d, [r14-49h]
0x1800d2c8c  mov     [rsp+0D0h+var_A8], 0
0x1800d2c94  lea     rcx, [rbp+57h+var_90]
0x1800d2c98  or      edx, 0FFFFFFFFh
0x1800d2c9b  mov     [rsp+0D0h+var_B0], 8
0x1800d2ca3  call    deflateInit2_
0x1800d2ca8  test    eax, eax
0x1800d2caa  jnz     short loc_1800D2D10
0x1800d2cac  mov     rax, [rdi+0A8h]
0x1800d2cb3  xor     r14d, r14d
0x1800d2cb6  mov     [rbp+57h+var_90], rax
0x1800d2cba  mov     eax, [rdi+0B0h]
0x1800d2cc0  mov     [rbp+57h+var_88], eax
0x1800d2cc3  xor     eax, eax
0x1800d2cc5  mov     [rbp+57h+var_78], ebx
0x1800d2cc8  mov     [rbp+57h+var_80], rsi
0x1800d2ccc  test    eax, eax
0x1800d2cce  jnz     short loc_1800D2CF1
0x1800d2cd0  lea     edx, [rax+4]
0x1800d2cd3  lea     rcx, [rbp+57h+var_90]
0x1800d2cd7  call    deflate
0x1800d2cdc  cmp     eax, 1
0x1800d2cdf  ja      short loc_1800D2D10
0x1800d2ce1  mov     ecx, [rbp+57h+var_78]
0x1800d2ce4  mov     rdx, rbx
0x1800d2ce7  sub     rdx, rcx
0x1800d2cea  add     r14, rdx
0x1800d2ced  test    eax, eax
0x1800d2cef  jz      short loc_1800D2CC5
0x1800d2cf1  cmp     eax, 1
0x1800d2cf4  jnz     short loc_1800D2D10
0x1800d2cf6  cmp     [rbp+57h+var_88], 0
0x1800d2cfa  jnz     short loc_1800D2D10
0x1800d2cfc  lea     rcx, [rbp+57h+var_90]
0x1800d2d00  call    deflateEnd
0x1800d2d05  test    eax, eax
0x1800d2d07  jnz     short loc_1800D2D10
0x1800d2d09  xor     ebx, ebx
0x1800d2d0b  mov     [r15], r14
0x1800d2d0e  jmp     short loc_1800D2D25
0x1800d2d10  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d2d17  mov     ebx, 88982F70h
0x1800d2d1c  jz      short loc_1800D2D25
0x1800d2d1e  mov     ecx, ebx; int
0x1800d2d20  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2d25  mov     rcx, rsi; pv
0x1800d2d28  call    cs:__imp_CoTaskMemFree
0x1800d2d2e  mov     eax, ebx
0x1800d2d30  add     rsp, 0A8h
0x1800d2d37  pop     r15
0x1800d2d39  pop     r14
0x1800d2d3b  pop     rdi
0x1800d2d3c  pop     rsi
0x1800d2d3d  pop     rbx
0x1800d2d3e  pop     rbp
0x1800d2d3f  retn
```
