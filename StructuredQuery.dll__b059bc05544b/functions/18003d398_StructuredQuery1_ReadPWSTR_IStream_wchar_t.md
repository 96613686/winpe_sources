# StructuredQuery1::ReadPWSTR(IStream *,wchar_t * *)

- ea: `0x18003d398`
- end: `0x18003d43d`
- name: `?ReadPWSTR@StructuredQuery1@@YAJPEAUIStream@@PEAPEA_W@Z`
- size: `165`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, struct IStream *, wchar_t **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d290`
- `0x18003dc94`

## callees

- `0x18003d398`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3da`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d3b7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d3fb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d3b7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d3fb`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadPWSTR(StructuredQuery1 *this, struct IStream *a2, wchar_t **a3)
{
  void *v3; // rbx
  HRESULT v6; // edi
  unsigned __int64 v7; // rax
  void *v8; // rax
  unsigned int pv; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  pv = 0;
  v6 = IStream_Read(this, &pv, 4u);
  if ( v6 >= 0 && pv )
  {
    v7 = 2LL * pv;
    if ( v7 > 0xFFFFFFFF )
    {
      v6 = -2147024362;
    }
    else
    {
      v8 = CoTaskMemAlloc((unsigned int)v7);
      v3 = v8;
      if ( v8 )
      {
        v6 = IStream_Read(this, v8, 2 * pv - 2);
        if ( v6 < 0 )
        {
          CoTaskMemFree(v3);
          v3 = 0;
        }
        else
        {
          *((_WORD *)v3 + pv - 1) = 0;
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  *(_QWORD *)a2 = v3;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003d398  push    rbx
0x18003d39a  push    rsi
0x18003d39b  push    rdi
0x18003d39c  push    r14
0x18003d39e  sub     rsp, 28h
0x18003d3a2  xor     ebx, ebx
0x18003d3a4  mov     r14, rdx
0x18003d3a7  lea     rdx, [rsp+48h+pv]; pv
0x18003d3ac  mov     [rsp+48h+pv], ebx
0x18003d3b0  mov     rsi, rcx
0x18003d3b3  lea     r8d, [rbx+4]; cb
0x18003d3b7  call    cs:__imp_IStream_Read
0x18003d3bd  mov     edi, eax
0x18003d3bf  test    eax, eax
0x18003d3c1  js      short loc_18003D413
0x18003d3c3  mov     eax, [rsp+48h+pv]
0x18003d3c7  test    eax, eax
0x18003d3c9  jz      short loc_18003D413
0x18003d3cb  add     rax, rax
0x18003d3ce  mov     ecx, 0FFFFFFFFh
0x18003d3d3  cmp     rax, rcx
0x18003d3d6  ja      short loc_18003D422
0x18003d3d8  mov     ecx, eax; cb
0x18003d3da  call    cs:__imp_CoTaskMemAlloc
0x18003d3e0  mov     rbx, rax
0x18003d3e3  test    rax, rax
0x18003d3e6  jz      short loc_18003D429
0x18003d3e8  mov     r8d, [rsp+48h+pv]
0x18003d3ed  mov     rdx, rax; pv
0x18003d3f0  mov     rcx, rsi; pstm
0x18003d3f3  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003d3fb  call    cs:__imp_IStream_Read
0x18003d401  mov     edi, eax
0x18003d403  test    eax, eax
0x18003d405  js      short loc_18003D430
0x18003d407  mov     ecx, [rsp+48h+pv]
0x18003d40b  dec     ecx
0x18003d40d  xor     eax, eax
0x18003d40f  mov     [rbx+rcx*2], ax
0x18003d413  mov     [r14], rbx
0x18003d416  mov     eax, edi
0x18003d418  add     rsp, 28h
0x18003d41c  pop     r14
0x18003d41e  pop     rdi
0x18003d41f  pop     rsi
0x18003d420  pop     rbx
0x18003d421  retn
0x18003d422  mov     edi, 80070216h
0x18003d427  jmp     short loc_18003D413
0x18003d429  mov     edi, 8007000Eh
0x18003d42e  jmp     short loc_18003D413
0x18003d430  mov     rcx, rbx; pv
0x18003d433  call    cs:__imp_CoTaskMemFree
0x18003d439  xor     ebx, ebx
0x18003d43b  jmp     short loc_18003D413
```
