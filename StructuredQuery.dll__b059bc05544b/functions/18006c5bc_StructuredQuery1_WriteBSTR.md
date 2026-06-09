# StructuredQuery1::WriteBSTR

- ea: `0x18006c5bc`
- end: `0x18006c625`
- name: `StructuredQuery1::WriteBSTR`
- size: `105`
- prototype: `__int64 __fastcall(IStream *pstm, void *pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037e50`

## callees

- `0x18006c5bc`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18006c5d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18006c5d4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18006c5f2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18006c614`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18006c5f2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18006c614`

## pseudocode

```c
int __fastcall StructuredQuery1::WriteBSTR(IStream *pstm, OLECHAR *pv)
{
  UINT v4; // eax
  int result; // eax
  UINT pva; // [rsp+38h] [rbp+10h] BYREF

  if ( pv )
    v4 = SysStringLen(pv) + 1;
  else
    v4 = 0;
  pva = v4;
  result = IStream_Write(pstm, &pva, 4u);
  if ( result >= 0 )
  {
    if ( pva )
      return IStream_Write(pstm, pv, 2 * pva - 2);
  }
  return result;
}

```

## disassembly

```asm
0x18006c5bc  mov     [rsp+arg_0], rbx
0x18006c5c1  push    rdi
0x18006c5c2  sub     rsp, 20h
0x18006c5c6  mov     rbx, rdx
0x18006c5c9  mov     rdi, rcx
0x18006c5cc  test    rdx, rdx
0x18006c5cf  jz      short loc_18006C5DE
0x18006c5d1  mov     rcx, rdx; pbstr
0x18006c5d4  call    cs:__imp_SysStringLen
0x18006c5da  inc     eax
0x18006c5dc  jmp     short loc_18006C5E0
0x18006c5de  xor     eax, eax
0x18006c5e0  mov     r8d, 4; cb
0x18006c5e6  mov     [rsp+28h+pv], eax
0x18006c5ea  lea     rdx, [rsp+28h+pv]; pv
0x18006c5ef  mov     rcx, rdi; pstm
0x18006c5f2  call    cs:__imp_IStream_Write
0x18006c5f8  test    eax, eax
0x18006c5fa  js      short loc_18006C61A
0x18006c5fc  mov     r8d, [rsp+28h+pv]
0x18006c601  test    r8d, r8d
0x18006c604  jz      short loc_18006C61A
0x18006c606  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18006c60e  mov     rdx, rbx; pv
0x18006c611  mov     rcx, rdi; pstm
0x18006c614  call    cs:__imp_IStream_Write
0x18006c61a  mov     rbx, [rsp+28h+arg_0]
0x18006c61f  add     rsp, 20h
0x18006c623  pop     rdi
0x18006c624  retn
```
