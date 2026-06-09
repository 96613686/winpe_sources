# CReaderProxy::Release(void)

- ea: `0x180009190`
- end: `0x180009222`
- name: `?Release@CReaderProxy@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(CReaderProxy *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005b2c`
- `0x180007910`
- `0x180009150`
- `0x180009da0`
- `0x18000a310`
- `0x180010dc4`
- `0x180012190`
- `0x18002e524`

## callees

- `0x180009190`
- `0x18001c370`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009204`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReaderProxy::Release(CReaderProxy *this)
{
  bool v2; // si
  int v3; // eax
  int v4; // eax

  v2 = 0;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  v3 = *((_DWORD *)this + 16);
  if ( v3 )
  {
    v4 = v3 - 1;
    *((_DWORD *)this + 16) = v4;
    v2 = v4 == 0;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  if ( v2 && this )
  {
    *((_QWORD *)this + 1) = &CCriticalSectionObject::`vftable';
    if ( !*((_DWORD *)this + 14) )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180009190  mov     [rsp+arg_0], rbx
0x180009195  mov     [rsp+arg_8], rsi
0x18000919a  push    rdi
0x18000919b  sub     rsp, 20h
0x18000919f  mov     rdi, rcx
0x1800091a2  xor     sil, sil
0x1800091a5  mov     rax, [rcx+8]
0x1800091a9  xor     r8d, r8d
0x1800091ac  xor     edx, edx
0x1800091ae  add     rcx, 8
0x1800091b2  mov     rax, [rax]
0x1800091b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ba  mov     eax, [rdi+40h]
0x1800091bd  test    eax, eax
0x1800091bf  jz      short loc_1800091D3
0x1800091c1  sub     eax, 1
0x1800091c4  mov     [rdi+40h], eax
0x1800091c7  movzx   esi, sil
0x1800091cb  mov     ecx, 1
0x1800091d0  cmovz   esi, ecx
0x1800091d3  mov     rax, [rdi+8]
0x1800091d7  lea     rcx, [rdi+8]
0x1800091db  mov     rax, [rax+8]
0x1800091df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e4  nop
0x1800091e5  test    sil, sil
0x1800091e8  jz      short loc_180009212
0x1800091ea  test    rdi, rdi
0x1800091ed  jz      short loc_180009212
0x1800091ef  lea     rax, ??_7CCriticalSectionObject@@6B@; const CCriticalSectionObject::`vftable'
0x1800091f6  mov     [rdi+8], rax
0x1800091fa  cmp     dword ptr [rdi+38h], 0
0x1800091fe  jnz     short loc_18000920A
0x180009200  lea     rcx, [rdi+10h]; lpCriticalSection
0x180009204  call    cs:__imp_DeleteCriticalSection
0x18000920a  mov     rcx, rdi; Block
0x18000920d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009212  mov     rbx, [rsp+28h+arg_0]
0x180009217  mov     rsi, [rsp+28h+arg_8]
0x18000921c  add     rsp, 20h
0x180009220  pop     rdi
0x180009221  retn
```
