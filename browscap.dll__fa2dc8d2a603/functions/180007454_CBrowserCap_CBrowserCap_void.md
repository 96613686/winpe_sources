# CBrowserCap::~CBrowserCap(void)

- ea: `0x180007454`
- end: `0x1800074d3`
- name: `??1CBrowserCap@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(CBrowserCap *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023b4`
- `0x1800025e0`

## callees

- `0x180002498`
- `0x180007454`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180007496`
- `msvcrt!free` at `0x180007496`
- `KERNEL32!DeleteCriticalSection` at `0x180007465`
- `KERNEL32!DeleteCriticalSection` at `0x1800074c1`
- `KERNEL32!DeleteCriticalSection` at `0x180007465`
- `KERNEL32!DeleteCriticalSection` at `0x1800074c1`
- `OLEAUT32!__imp_VariantClear` at `0x180007475`
- `OLEAUT32!__imp_VariantClear` at `0x180007475`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBrowserCap::~CBrowserCap(CBrowserCap *this)
{
  __int64 i; // rdi
  void *v3; // rcx
  __int64 v4; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  for ( i = *((_QWORD *)this + 11); i != *((_QWORD *)this + 12); i += 40 )
  {
    VariantClear((VARIANTARG *)(i + 16));
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(i);
  }
  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
    free(v3);
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x180007454  mov     [rsp+arg_0], rbx
0x180007459  push    rdi
0x18000745a  sub     rsp, 20h
0x18000745e  mov     rbx, rcx
0x180007461  add     rcx, 68h ; 'h'; lpCriticalSection
0x180007465  call    cs:__imp_DeleteCriticalSection
0x18000746b  mov     rdi, [rbx+58h]
0x18000746f  jmp     short loc_180007487
0x180007471  lea     rcx, [rdi+10h]; pvarg
0x180007475  call    cs:__imp_VariantClear
0x18000747b  mov     rcx, rdi
0x18000747e  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180007483  add     rdi, 28h ; '('
0x180007487  cmp     rdi, [rbx+60h]
0x18000748b  jnz     short loc_180007471
0x18000748d  mov     rcx, [rbx+58h]; Block
0x180007491  test    rcx, rcx
0x180007494  jz      short loc_18000749D
0x180007496  call    cs:__imp_free
0x18000749c  nop
0x18000749d  mov     rcx, [rbx+48h]
0x1800074a1  test    rcx, rcx
0x1800074a4  jz      short loc_1800074B3
0x1800074a6  mov     rax, [rcx]
0x1800074a9  mov     rax, [rax+10h]
0x1800074ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b2  nop
0x1800074b3  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800074b7  cmp     byte ptr [rcx+28h], 0
0x1800074bb  jz      short loc_1800074C8
0x1800074bd  mov     byte ptr [rcx+28h], 0
0x1800074c1  call    cs:__imp_DeleteCriticalSection
0x1800074c7  nop
0x1800074c8  mov     rbx, [rsp+28h+arg_0]
0x1800074cd  add     rsp, 20h
0x1800074d1  pop     rdi
0x1800074d2  retn
```
