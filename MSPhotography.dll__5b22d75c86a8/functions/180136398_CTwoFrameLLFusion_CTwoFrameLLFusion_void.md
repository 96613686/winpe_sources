# CTwoFrameLLFusion::~CTwoFrameLLFusion(void)

- ea: `0x180136398`
- end: `0x180136424`
- name: `??1CTwoFrameLLFusion@@EEAA@XZ`
- size: `140`
- prototype: `void __fastcall(CTwoFrameLLFusion *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180136710`

## callees

- `0x180031274`
- `0x180136398`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801363e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801363e6`

## pseudocode

```c
void __fastcall CTwoFrameLLFusion::~CTwoFrameLLFusion(CTwoFrameLLFusion *this)
{
  unsigned int i; // edi

  *(_QWORD *)this = &CTwoFrameLLFusion::`vftable';
  for ( i = 0; i < 2; ++i )
  {
    vt::vector<vt::CImg,0>::clear((char *)this + 16);
    vt::vector<vt::CImg,0>::clear((char *)this + 48);
    vt::vector<vt::CImg,0>::clear((char *)this + 80);
    vt::vector<vt::CImg,0>::clear((char *)this + 112);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  vt::vector<vt::CImg,0>::clear((char *)this + 112);
  vt::vector<vt::CImg,0>::clear((char *)this + 80);
  vt::vector<vt::CImg,0>::clear((char *)this + 48);
  vt::vector<vt::CImg,0>::clear((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180136398  push    rbx
0x18013639a  push    rbp
0x18013639b  push    rsi
0x18013639c  push    rdi
0x18013639d  push    r14
0x18013639f  push    r15
0x1801363a1  sub     rsp, 28h
0x1801363a5  lea     rax, ??_7CTwoFrameLLFusion@@6B@; const CTwoFrameLLFusion::`vftable'
0x1801363ac  mov     rbx, rcx
0x1801363af  mov     [rcx], rax
0x1801363b2  xor     edi, edi
0x1801363b4  lea     rcx, [rbx+10h]
0x1801363b8  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363bd  lea     rcx, [rbx+30h]
0x1801363c1  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363c6  lea     rcx, [rbx+50h]
0x1801363ca  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363cf  lea     rcx, [rbx+70h]
0x1801363d3  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363d8  inc     edi
0x1801363da  cmp     edi, 2
0x1801363dd  jb      short loc_1801363B4
0x1801363df  lea     rcx, [rbx+98h]; lpCriticalSection
0x1801363e6  call    cs:__imp_DeleteCriticalSection
0x1801363ec  lea     rcx, [rbx+70h]
0x1801363f0  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363f5  lea     rcx, [rbx+50h]
0x1801363f9  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x1801363fe  lea     rcx, [rbx+30h]
0x180136402  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180136407  lea     rcx, [rbx+10h]
0x18013640b  call    ?clear@?$vector@VCImg@vt@@$0A@@vt@@QEAAXXZ; vt::vector<vt::CImg,0>::clear(void)
0x180136410  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180136417  add     rsp, 28h
0x18013641b  pop     r15
0x18013641d  pop     r14
0x18013641f  pop     rdi
0x180136420  pop     rsi
0x180136421  pop     rbp
0x180136422  pop     rbx
0x180136423  retn
```
