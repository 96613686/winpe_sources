# CEditStream::Create(__int64,__int64)

- ea: `0x180011944`
- end: `0x180011a3f`
- name: `?Create@CEditStream@@UEAAJ_J0@Z`
- size: `251`
- prototype: `__int64 __fastcall(CEditStream *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011930`

## callees

- `0x180001d0c`
- `0x180008300`
- `0x180008350`
- `0x1800086a0`
- `0x180011944`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011967`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180011967`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001195e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001195e`

## pseudocode

```c
__int64 __fastcall CEditStream::Create(CEditStream *this, __int64 a2)
{
  HGLOBAL v4; // rax
  _QWORD *v5; // rax
  _DWORD *v7; // rax

  v4 = GlobalAlloc(0x2042u, 0x380u);
  v5 = GlobalLock(v4);
  *((_QWORD *)this - 5) = v5;
  if ( !v5 )
    return 2147762279LL;
  *(_QWORD *)((char *)this - 52) = 16;
  *((_DWORD *)this - 66) = 1;
  *((_QWORD *)this - 4) = 0;
  *((_QWORD *)this - 3) = 0;
  *((_QWORD *)this - 2) = 0;
  *v5 = a2;
  memset_0((char *)this - 260, 0, 0xCCu);
  v7 = (_DWORD *)*((_QWORD *)this - 5);
  *((_DWORD *)this - 14) = 1;
  if ( *(_QWORD *)v7 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
    *(_DWORD *)(*((_QWORD *)this - 5) + 8LL) = AVIStreamStart(**((PAVISTREAM **)this - 5));
    *(_DWORD *)(*((_QWORD *)this - 5) + 12LL) = AVIStreamLength(**((PAVISTREAM **)this - 5));
    AVIStreamInfoW(**((PAVISTREAM **)this - 5), (LPAVISTREAMINFOW)((char *)this - 260), 204);
  }
  else
  {
    v7[2] = 0;
    *(_DWORD *)(*((_QWORD *)this - 5) + 12LL) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180011944  mov     [rsp+arg_0], rbx
0x180011949  push    rdi
0x18001194a  sub     rsp, 20h
0x18001194e  mov     rdi, rdx
0x180011951  mov     rbx, rcx
0x180011954  mov     edx, 380h; dwBytes
0x180011959  mov     ecx, 2042h; uFlags
0x18001195e  call    cs:__imp_GlobalAlloc
0x180011964  mov     rcx, rax; hMem
0x180011967  call    cs:__imp_GlobalLock
0x18001196d  mov     [rbx-28h], rax
0x180011971  test    rax, rax
0x180011974  jnz     short loc_180011980
0x180011976  mov     eax, 80044067h
0x18001197b  jmp     loc_180011A34
0x180011980  mov     qword ptr [rbx-34h], 10h
0x180011988  xor     edx, edx; Val
0x18001198a  mov     dword ptr [rbx-108h], 1
0x180011994  mov     r8d, 0CCh; Size
0x18001199a  mov     qword ptr [rbx-20h], 0
0x1800119a2  mov     qword ptr [rbx-18h], 0
0x1800119aa  mov     qword ptr [rbx-10h], 0
0x1800119b2  mov     [rax], rdi
0x1800119b5  lea     rdi, [rbx-104h]
0x1800119bc  mov     rcx, rdi; void *
0x1800119bf  call    memset_0
0x1800119c4  mov     rax, [rbx-28h]
0x1800119c8  mov     dword ptr [rbx-38h], 1
0x1800119cf  mov     rcx, [rax]
0x1800119d2  test    rcx, rcx
0x1800119d5  jz      short loc_180011A20
0x1800119d7  mov     rax, [rcx]
0x1800119da  mov     rax, [rax+8]
0x1800119de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119e3  mov     rcx, [rbx-28h]
0x1800119e7  mov     rcx, [rcx]; pavi
0x1800119ea  call    AVIStreamStart
0x1800119ef  mov     rcx, [rbx-28h]
0x1800119f3  mov     [rcx+8], eax
0x1800119f6  mov     rcx, [rbx-28h]
0x1800119fa  mov     rcx, [rcx]; pavi
0x1800119fd  call    AVIStreamLength
0x180011a02  mov     rcx, [rbx-28h]
0x180011a06  mov     r8d, 0CCh; lSize
0x180011a0c  mov     rdx, rdi; psi
0x180011a0f  mov     [rcx+0Ch], eax
0x180011a12  mov     rcx, [rbx-28h]
0x180011a16  mov     rcx, [rcx]; pavi
0x180011a19  call    AVIStreamInfoW
0x180011a1e  jmp     short loc_180011A32
0x180011a20  mov     dword ptr [rax+8], 0
0x180011a27  mov     rax, [rbx-28h]
0x180011a2b  mov     dword ptr [rax+0Ch], 0
0x180011a32  xor     eax, eax
0x180011a34  mov     rbx, [rsp+28h+arg_0]
0x180011a39  add     rsp, 20h
0x180011a3d  pop     rdi
0x180011a3e  retn
```
