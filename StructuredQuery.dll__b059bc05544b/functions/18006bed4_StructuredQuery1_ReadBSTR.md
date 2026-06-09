# StructuredQuery1::ReadBSTR

- ea: `0x18006bed4`
- end: `0x18006bf67`
- name: `StructuredQuery1::ReadBSTR`
- size: `147`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003dc94`

## callees

- `0x18006bed4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006bf0b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006bf0b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bf49`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bf49`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bef3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bf2c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bef3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bf2c`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBSTR(IStream *pstm, OLECHAR **a2)
{
  OLECHAR *v2; // rbx
  HRESULT v5; // edi
  BSTR v6; // rax
  int pv; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  pv = 0;
  v5 = IStream_Read(pstm, &pv, 4u);
  if ( v5 >= 0 && pv )
  {
    v6 = SysAllocStringLen(0, pv - 1);
    v2 = v6;
    if ( v6 )
    {
      v5 = IStream_Read(pstm, v6, 2 * pv - 2);
      if ( v5 < 0 )
      {
        SysFreeString(v2);
        v2 = 0;
      }
      else
      {
        v2[pv - 1] = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  *a2 = v2;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006bed4  push    rbx
0x18006bed6  push    rsi
0x18006bed7  push    rdi
0x18006bed8  push    r14
0x18006beda  sub     rsp, 28h
0x18006bede  xor     ebx, ebx
0x18006bee0  mov     r14, rdx
0x18006bee3  lea     rdx, [rsp+48h+pv]; pv
0x18006bee8  mov     [rsp+48h+pv], ebx
0x18006beec  mov     rsi, rcx
0x18006beef  lea     r8d, [rbx+4]; cb
0x18006bef3  call    cs:__imp_IStream_Read
0x18006bef9  mov     edi, eax
0x18006befb  test    eax, eax
0x18006befd  js      short loc_18006BF58
0x18006beff  mov     edx, [rsp+48h+pv]
0x18006bf03  test    edx, edx
0x18006bf05  jz      short loc_18006BF58
0x18006bf07  dec     edx; ui
0x18006bf09  xor     ecx, ecx; strIn
0x18006bf0b  call    cs:__imp_SysAllocStringLen
0x18006bf11  mov     rbx, rax
0x18006bf14  test    rax, rax
0x18006bf17  jz      short loc_18006BF53
0x18006bf19  mov     r8d, [rsp+48h+pv]
0x18006bf1e  mov     rdx, rax; pv
0x18006bf21  mov     rcx, rsi; pstm
0x18006bf24  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18006bf2c  call    cs:__imp_IStream_Read
0x18006bf32  mov     edi, eax
0x18006bf34  test    eax, eax
0x18006bf36  js      short loc_18006BF46
0x18006bf38  mov     ecx, [rsp+48h+pv]
0x18006bf3c  dec     ecx
0x18006bf3e  xor     eax, eax
0x18006bf40  mov     [rbx+rcx*2], ax
0x18006bf44  jmp     short loc_18006BF58
0x18006bf46  mov     rcx, rbx; bstrString
0x18006bf49  call    cs:__imp_SysFreeString
0x18006bf4f  xor     ebx, ebx
0x18006bf51  jmp     short loc_18006BF58
0x18006bf53  mov     edi, 8007000Eh
0x18006bf58  mov     [r14], rbx
0x18006bf5b  mov     eax, edi
0x18006bf5d  add     rsp, 28h
0x18006bf61  pop     r14
0x18006bf63  pop     rdi
0x18006bf64  pop     rsi
0x18006bf65  pop     rbx
0x18006bf66  retn
```
