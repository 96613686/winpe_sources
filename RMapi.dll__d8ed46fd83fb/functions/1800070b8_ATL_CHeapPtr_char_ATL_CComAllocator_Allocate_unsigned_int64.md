# ATL::CHeapPtr<char,ATL::CComAllocator>::Allocate(unsigned __int64)

- ea: `0x1800070b8`
- end: `0x180007106`
- name: `?Allocate@?$CHeapPtr@DVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024b00`

## callees

- `0x1800070b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800070e4`

## pseudocode

```c
bool __fastcall ATL::CHeapPtr<char,ATL::CComAllocator>::Allocate(_QWORD *a1, unsigned __int64 a2)
{
  unsigned int v2; // r8d
  LPVOID v4; // rax

  v2 = a2;
  if ( !a2 )
  {
    v2 = 0;
    goto LABEL_4;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v4 = 0;
      goto LABEL_5;
    }
LABEL_4:
    v4 = CoTaskMemAlloc(v2);
LABEL_5:
    *a1 = v4;
    return v4 != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800070b8  push    rbx
0x1800070ba  sub     rsp, 20h
0x1800070be  mov     r8, rdx
0x1800070c1  mov     rbx, rcx
0x1800070c4  test    rdx, rdx
0x1800070c7  jz      short loc_1800070F9
0x1800070c9  xor     edx, edx
0x1800070cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800070cf  div     r8
0x1800070d2  cmp     rax, 1
0x1800070d6  jb      short loc_180007102
0x1800070d8  cmp     r8, 7FFFFFFFh
0x1800070df  ja      short loc_1800070FE
0x1800070e1  mov     ecx, r8d; cb
0x1800070e4  call    cs:__imp_CoTaskMemAlloc
0x1800070ea  test    rax, rax
0x1800070ed  mov     [rbx], rax
0x1800070f0  setnz   al
0x1800070f3  add     rsp, 20h
0x1800070f7  pop     rbx
0x1800070f8  retn
0x1800070f9  xor     r8d, r8d
0x1800070fc  jmp     short loc_1800070E1
0x1800070fe  xor     eax, eax
0x180007100  jmp     short loc_1800070EA
0x180007102  xor     al, al
0x180007104  jmp     short loc_1800070F3
```
