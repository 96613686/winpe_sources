# ATL::CHeapPtr<ushort,ATL::CComAllocator>::Allocate(unsigned __int64)

- ea: `0x1800090bc`
- end: `0x180009109`
- name: `?Allocate@?$CHeapPtr@GVCComAllocator@ATL@@@ATL@@QEAA_N_K@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024b00`

## callees

- `0x1800090bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800090d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800090d1`

## pseudocode

```c
bool __fastcall ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::Allocate(_QWORD *a1, unsigned __int64 a2)
{
  unsigned int v3; // eax
  LPVOID v4; // rax

  if ( !a2 )
  {
    v3 = 0;
    goto LABEL_3;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / a2 >= 2 )
  {
    v3 = 2 * a2;
    if ( 2 * a2 > 0x7FFFFFFF )
    {
      v4 = 0;
      goto LABEL_4;
    }
LABEL_3:
    v4 = CoTaskMemAlloc(v3);
LABEL_4:
    *a1 = v4;
    return v4 != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800090bc  push    rbx
0x1800090be  sub     rsp, 20h
0x1800090c2  mov     r8, rdx
0x1800090c5  mov     rbx, rcx
0x1800090c8  test    rdx, rdx
0x1800090cb  jnz     short loc_1800090E2
0x1800090cd  xor     eax, eax
0x1800090cf  mov     ecx, eax; cb
0x1800090d1  call    cs:__imp_CoTaskMemAlloc
0x1800090d7  test    rax, rax
0x1800090da  mov     [rbx], rax
0x1800090dd  setnz   al
0x1800090e0  jmp     short loc_180009103
0x1800090e2  xor     edx, edx
0x1800090e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800090e8  div     r8
0x1800090eb  cmp     rax, 2
0x1800090ef  jb      short loc_180009101
0x1800090f1  lea     rax, [r8+r8]
0x1800090f5  cmp     rax, 7FFFFFFFh
0x1800090fb  jbe     short loc_1800090CF
0x1800090fd  xor     eax, eax
0x1800090ff  jmp     short loc_1800090D7
0x180009101  xor     al, al
0x180009103  add     rsp, 20h
0x180009107  pop     rbx
0x180009108  retn
```
