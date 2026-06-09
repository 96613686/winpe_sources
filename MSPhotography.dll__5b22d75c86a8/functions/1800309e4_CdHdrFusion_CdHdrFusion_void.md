# CdHdrFusion::~CdHdrFusion(void)

- ea: `0x1800309e4`
- end: `0x180030a41`
- name: `??1CdHdrFusion@@EEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CdHdrFusion *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030dd0`

## callees

- `0x1800309e4`
- `0x180031274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a19`

## pseudocode

```c
void __fastcall CdHdrFusion::~CdHdrFusion(CdHdrFusion *this)
{
  unsigned int i; // edi

  *(_QWORD *)this = &CdHdrFusion::`vftable';
  for ( i = 0; i < 3; ++i )
  {
    vt::vector<vt::CImg,0>::clear((char *)this + 16);
    vt::vector<vt::CImg,0>::clear((char *)this + 48);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  vt::vector<vt::CImg,0>::clear((char *)this + 48);
  vt::vector<vt::CImg,0>::clear((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800309e4  push    rbx
0x1800309e6  push    rbp
0x1800309e7  push    rsi
0x1800309e8  push    rdi
0x1800309e9  sub     rsp, 28h
0x1800309ed  lea     rax, ??_7CdHdrFusion@@6B@; const CdHdrFusion::`vftable'
0x1800309f4  mov     rbx, rcx
0x1800309f7  mov     [rcx], rax
0x1800309fa  xor     edi, edi
0x1800309fc  lea     rcx, [rbx+10h]
0x180030a00  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180030a05  lea     rcx, [rbx+30h]
0x180030a09  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180030a0e  inc     edi
0x180030a10  cmp     edi, 3
0x180030a13  jb      short loc_1800309FC
0x180030a15  lea     rcx, [rbx+58h]; lpCriticalSection
0x180030a19  call    cs:__imp_DeleteCriticalSection
0x180030a1f  lea     rcx, [rbx+30h]
0x180030a23  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180030a28  lea     rcx, [rbx+10h]
0x180030a2c  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180030a31  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180030a38  add     rsp, 28h
0x180030a3c  pop     rdi
0x180030a3d  pop     rsi
0x180030a3e  pop     rbp
0x180030a3f  pop     rbx
0x180030a40  retn
```
