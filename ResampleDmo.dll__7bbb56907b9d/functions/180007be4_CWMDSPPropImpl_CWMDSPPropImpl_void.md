# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x180007be4`
- end: `0x180007c5c`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000785c`
- `0x180007ae0`

## callees

- `0x180007be4`
- `0x180007c64`
- `0x18000b1b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c3b`

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
0x180007be4  mov     [rsp+arg_0], rbx
0x180007be9  push    rdi
0x180007bea  sub     rsp, 20h
0x180007bee  cmp     qword ptr [rcx+18h], 0
0x180007bf3  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x180007bfa  mov     [rcx], rax
0x180007bfd  mov     rbx, rcx
0x180007c00  jz      short loc_180007C37
0x180007c02  xor     edi, edi
0x180007c04  cmp     [rcx+8], edi
0x180007c07  jbe     short loc_180007C37
0x180007c09  mov     rax, [rbx+18h]
0x180007c0d  mov     ecx, edi
0x180007c0f  inc     rcx
0x180007c12  lea     rcx, [rcx+rdi*8]
0x180007c16  lea     rdx, [rax+rcx*8]
0x180007c1a  mov     rcx, [rbx+10h]
0x180007c1e  lea     rax, [rdi+rdi*2]
0x180007c22  shl     rax, 5
0x180007c26  movzx   ecx, word ptr [rax+rcx+14h]
0x180007c2b  call    WMDSPPropClear
0x180007c30  inc     edi
0x180007c32  cmp     edi, [rbx+8]
0x180007c35  jb      short loc_180007C09
0x180007c37  lea     rcx, [rbx+30h]; lpCriticalSection
0x180007c3b  call    cs:__imp_DeleteCriticalSection
0x180007c41  mov     rcx, [rbx+18h]; Block
0x180007c45  test    rcx, rcx
0x180007c48  jnz     short loc_180007C55
0x180007c4a  mov     rbx, [rsp+28h+arg_0]
0x180007c4f  add     rsp, 20h
0x180007c53  pop     rdi
0x180007c54  retn
0x180007c55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007c5a  jmp     short loc_180007C4A
```
