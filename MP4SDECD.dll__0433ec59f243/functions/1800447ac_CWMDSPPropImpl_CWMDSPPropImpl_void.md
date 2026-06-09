# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x1800447ac`
- end: `0x180044822`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002b704`

## callees

- `0x18002a6b0`
- `0x1800447ac`
- `0x180044d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044803`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044803`

## pseudocode

```c
void __fastcall CWMDSPPropImpl::~CWMDSPPropImpl(CWMDSPPropImpl *this)
{
  bool v1; // zf
  __int64 i; // rdi
  void *v4; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CWMDSPPropImpl::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      WMDSPPropClear(
        *(unsigned __int16 *)(96 * i + *((_QWORD *)this + 2) + 20),
        *((_QWORD *)this + 3) + 8 * ((unsigned int)i + 1LL + 8 * i));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x1800447ac  mov     [rsp+arg_0], rbx
0x1800447b1  push    rdi
0x1800447b2  sub     rsp, 20h
0x1800447b6  cmp     qword ptr [rcx+18h], 0
0x1800447bb  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x1800447c2  mov     [rcx], rax
0x1800447c5  mov     rbx, rcx
0x1800447c8  jz      short loc_1800447FF
0x1800447ca  xor     edi, edi
0x1800447cc  cmp     [rcx+8], edi
0x1800447cf  jbe     short loc_1800447FF
0x1800447d1  mov     rax, [rbx+18h]
0x1800447d5  mov     ecx, edi
0x1800447d7  inc     rcx
0x1800447da  lea     rcx, [rcx+rdi*8]
0x1800447de  lea     rdx, [rax+rcx*8]
0x1800447e2  mov     rcx, [rbx+10h]
0x1800447e6  lea     rax, [rdi+rdi*2]
0x1800447ea  shl     rax, 5
0x1800447ee  movzx   ecx, word ptr [rax+rcx+14h]
0x1800447f3  call    WMDSPPropClear
0x1800447f8  inc     edi
0x1800447fa  cmp     edi, [rbx+8]
0x1800447fd  jb      short loc_1800447D1
0x1800447ff  lea     rcx, [rbx+30h]; lpCriticalSection
0x180044803  call    cs:__imp_DeleteCriticalSection
0x180044809  mov     rcx, [rbx+18h]; Block
0x18004480d  test    rcx, rcx
0x180044810  jz      short loc_180044817
0x180044812  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180044817  mov     rbx, [rsp+28h+arg_0]
0x18004481c  add     rsp, 20h
0x180044820  pop     rdi
0x180044821  retn
```
