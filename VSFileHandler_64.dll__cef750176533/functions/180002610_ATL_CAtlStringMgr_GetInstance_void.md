# ATL::CAtlStringMgr::GetInstance(void)

- ea: `0x180002610`
- end: `0x1800026df`
- name: `?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ`
- size: `207`
- prototype: `struct ATL::IAtlStringMgr *(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010d0`
- `0x1800060c0`
- `0x180006878`
- `0x180006918`
- `0x1800069b4`

## callees

- `0x180002610`
- `0x180007a78`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002642`
- `KERNEL32!GetProcessHeap` at `0x180002642`

## pseudocode

```c
struct ATL::IAtlStringMgr *ATL::CAtlStringMgr::GetInstance(void)
{
  int v0; // eax
  HANDLE ProcessHeap; // rax

  v0 = `ATL::CAtlStringMgr::GetInstance'::`2'::`local static guard';
  if ( (`ATL::CAtlStringMgr::GetInstance'::`2'::`local static guard' & 1) == 0 )
  {
    `ATL::CAtlStringMgr::GetInstance'::`2'::`local static guard' |= 1u;
    qword_18003EF20 = 0;
    `ATL::CAtlStringMgr::GetInstance'::`2'::strHeap = 0;
    ProcessHeap = GetProcessHeap();
    LOBYTE(qword_18003EF20) = 0;
    *(_QWORD *)&`ATL::CAtlStringMgr::GetInstance'::`2'::strHeap = &ATL::CWin32Heap::`vftable';
    *((_QWORD *)&`ATL::CAtlStringMgr::GetInstance'::`2'::strHeap + 1) = ProcessHeap;
    atexit(`ATL::CAtlStringMgr::GetInstance'::`2'::`dynamic atexit destructor for 'strHeap'');
    v0 = `ATL::CAtlStringMgr::GetInstance'::`2'::`local static guard';
  }
  if ( (v0 & 2) == 0 )
  {
    qword_18003EF00 = 2;
    `ATL::CAtlStringMgr::GetInstance'::`2'::`local static guard' = v0 | 2;
    qword_18003EEE8 = (__int64)&`ATL::CAtlStringMgr::GetInstance'::`2'::strHeap;
    `ATL::CAtlStringMgr::GetInstance'::`2'::strMgr = (__int64)&ATL::CAtlStringMgr::`vftable';
    qword_18003EF08 = 0;
    qword_18003EEF8 = 0;
    qword_18003EEF0 = (__int64)&`ATL::CAtlStringMgr::GetInstance'::`2'::strMgr;
    atexit(`ATL::CAtlStringMgr::GetInstance'::`2'::`dynamic atexit destructor for 'strMgr'');
  }
  return (struct ATL::IAtlStringMgr *)&`ATL::CAtlStringMgr::GetInstance'::`2'::strMgr;
}

```

## disassembly

```asm
0x180002610  mov     [rsp+arg_0], rbx
0x180002615  push    rdi
0x180002616  sub     rsp, 20h
0x18000261a  mov     eax, cs:??_B?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@51; `ATL::CAtlStringMgr::GetInstance(void)'::`2'::`local static guard'{2}'
0x180002620  xor     ebx, ebx
0x180002622  test    al, 1
0x180002624  jnz     short loc_180002675
0x180002626  or      eax, 1
0x180002629  xorps   xmm0, xmm0
0x18000262c  mov     cs:??_B?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@51, eax; `ATL::CAtlStringMgr::GetInstance(void)'::`2'::`local static guard'{2}'
0x180002632  xor     eax, eax
0x180002634  mov     cs:qword_18003EF20, rax
0x18000263b  movups  cs:?strHeap@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4VCWin32Heap@3@A, xmm0; ATL::CWin32Heap `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strHeap
0x180002642  call    cs:__imp_GetProcessHeap
0x180002648  lea     rcx, ??_7CWin32Heap@ATL@@6B@; const ATL::CWin32Heap::`vftable'
0x18000264f  mov     byte ptr cs:qword_18003EF20, bl
0x180002655  mov     qword ptr cs:?strHeap@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4VCWin32Heap@3@A, rcx; ATL::CWin32Heap `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strHeap
0x18000265c  lea     rcx, ??__FstrHeap@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@YAXXZ; void (__cdecl *)()
0x180002663  mov     qword ptr cs:?strHeap@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4VCWin32Heap@3@A+8, rax; ATL::CWin32Heap `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strHeap
0x18000266a  call    atexit
0x18000266f  mov     eax, cs:??_B?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@51; `ATL::CAtlStringMgr::GetInstance(void)'::`2'::`local static guard'{2}'
0x180002675  lea     rdi, ?strMgr@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4V23@A; ATL::CAtlStringMgr `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strMgr
0x18000267c  test    al, 2
0x18000267e  jnz     short loc_1800026D1
0x180002680  or      eax, 2
0x180002683  mov     cs:qword_18003EF00, 2
0x18000268e  lea     rcx, ?strHeap@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4VCWin32Heap@3@A; ATL::CWin32Heap `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strHeap
0x180002695  mov     cs:??_B?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@51, eax; `ATL::CAtlStringMgr::GetInstance(void)'::`2'::`local static guard'{2}'
0x18000269b  lea     rax, ??_7CAtlStringMgr@ATL@@6B@; const ATL::CAtlStringMgr::`vftable'
0x1800026a2  mov     cs:qword_18003EEE8, rcx
0x1800026a9  lea     rcx, ??__FstrMgr@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ@YAXXZ; void (__cdecl *)()
0x1800026b0  mov     cs:?strMgr@?1??GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@3@XZ@4V23@A, rax; ATL::CAtlStringMgr `ATL::CAtlStringMgr::GetInstance(void)'::`2'::strMgr
0x1800026b7  mov     cs:qword_18003EF08, rbx
0x1800026be  mov     cs:qword_18003EEF8, rbx
0x1800026c5  mov     cs:qword_18003EEF0, rdi
0x1800026cc  call    atexit
0x1800026d1  mov     rbx, [rsp+28h+arg_0]
0x1800026d6  mov     rax, rdi
0x1800026d9  add     rsp, 20h
0x1800026dd  pop     rdi
0x1800026de  retn
```
