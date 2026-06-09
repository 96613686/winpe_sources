# GetFrameDef::FreeStuff(void)

- ea: `0x180013830`
- end: `0x1800138e2`
- name: `?FreeStuff@GetFrameDef@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(GetFrameDef *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800137c4`
- `0x1800138f0`
- `0x180013d70`

## callees

- `0x180013830`

## import_xrefs

- `MSVFW32!ICClose` at `0x1800138ce`
- `MSVFW32!ICClose` at `0x1800138ce`
- `MSVFW32!ICSendMessage` at `0x1800138c4`
- `MSVFW32!ICSendMessage` at `0x1800138c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013851`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013884`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013851`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180013884`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013848`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001385b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001387b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001388e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180013848`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001385b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001387b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001388e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013864`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013897`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013864`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013897`

## pseudocode

```c
void __fastcall GetFrameDef::FreeStuff(GetFrameDef *this)
{
  const void *v2; // rcx
  HGLOBAL v3; // rax
  HGLOBAL v4; // rax
  const void *v5; // rcx
  HGLOBAL v6; // rax
  HGLOBAL v7; // rax
  HIC v8; // rcx
  UINT v9; // edx

  v2 = (const void *)*((_QWORD *)this + 9);
  if ( v2 && v2 != *((const void **)this + 7) )
  {
    v3 = GlobalHandle(v2);
    GlobalUnlock(v3);
    v4 = GlobalHandle(*((LPCVOID *)this + 9));
    GlobalFree(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (const void *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GlobalHandle(v5);
    GlobalUnlock(v6);
    v7 = GlobalHandle(*((LPCVOID *)this + 7));
    GlobalFree(v7);
    *((_QWORD *)this + 7) = 0;
  }
  v8 = (HIC)*((_QWORD *)this + 11);
  if ( v8 )
  {
    v9 = 16447;
    if ( !*((_DWORD *)this + 24) )
      v9 = 16398;
    ICSendMessage(v8, v9, 0, 0);
    ICClose(*((HIC *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
}

```

## disassembly

```asm
0x180013830  push    rbx
0x180013832  sub     rsp, 20h
0x180013836  mov     rbx, rcx
0x180013839  mov     rcx, [rcx+48h]; pMem
0x18001383d  test    rcx, rcx
0x180013840  jz      short loc_180013872
0x180013842  cmp     rcx, [rbx+38h]
0x180013846  jz      short loc_180013872
0x180013848  call    cs:__imp_GlobalHandle
0x18001384e  mov     rcx, rax; hMem
0x180013851  call    cs:__imp_GlobalUnlock
0x180013857  mov     rcx, [rbx+48h]; pMem
0x18001385b  call    cs:__imp_GlobalHandle
0x180013861  mov     rcx, rax; hMem
0x180013864  call    cs:__imp_GlobalFree
0x18001386a  mov     qword ptr [rbx+48h], 0
0x180013872  mov     rcx, [rbx+38h]; pMem
0x180013876  test    rcx, rcx
0x180013879  jz      short loc_1800138A5
0x18001387b  call    cs:__imp_GlobalHandle
0x180013881  mov     rcx, rax; hMem
0x180013884  call    cs:__imp_GlobalUnlock
0x18001388a  mov     rcx, [rbx+38h]; pMem
0x18001388e  call    cs:__imp_GlobalHandle
0x180013894  mov     rcx, rax; hMem
0x180013897  call    cs:__imp_GlobalFree
0x18001389d  mov     qword ptr [rbx+38h], 0
0x1800138a5  mov     rcx, [rbx+58h]; hic
0x1800138a9  test    rcx, rcx
0x1800138ac  jz      short loc_1800138DC
0x1800138ae  xor     r9d, r9d; dw2
0x1800138b1  xor     r8d, r8d; dw1
0x1800138b4  mov     edx, 403Fh
0x1800138b9  cmp     [rbx+60h], r8d
0x1800138bd  jnz     short loc_1800138C4
0x1800138bf  mov     edx, 400Eh; msg
0x1800138c4  call    cs:__imp_ICSendMessage
0x1800138ca  mov     rcx, [rbx+58h]; hic
0x1800138ce  call    cs:__imp_ICClose
0x1800138d4  mov     qword ptr [rbx+58h], 0
0x1800138dc  add     rsp, 20h
0x1800138e0  pop     rbx
0x1800138e1  retn
```
