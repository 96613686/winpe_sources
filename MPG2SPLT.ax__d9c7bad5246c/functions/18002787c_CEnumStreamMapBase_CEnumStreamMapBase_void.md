# CEnumStreamMapBase::~CEnumStreamMapBase(void)

- ea: `0x18002787c`
- end: `0x1800278d8`
- name: `??1CEnumStreamMapBase@@UEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CEnumStreamMapBase *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800278e0`
- `0x180027930`
- `0x180027980`

## callees

- `0x18002787c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800278ac`
- `ole32!CoTaskMemFree` at `0x1800278b6`
- `ole32!CoTaskMemFree` at `0x1800278bf`
- `ole32!CoTaskMemFree` at `0x1800278ac`
- `ole32!CoTaskMemFree` at `0x1800278b6`
- `ole32!CoTaskMemFree` at `0x1800278bf`

## pseudocode

```c
void __fastcall CEnumStreamMapBase::~CEnumStreamMapBase(CEnumStreamMapBase *this)
{
  __int64 **v1; // rdi
  __int64 v2; // rcx
  LPVOID *v3; // rbx
  __int64 *v4; // rax
  __int64 *v5; // rdx

  *(_QWORD *)this = &CEnumStreamMapBase::`vftable';
  v1 = (__int64 **)((char *)this + 32);
  while ( 1 )
  {
    v5 = *v1;
    if ( *v1 == (__int64 *)v1 )
      break;
    v2 = *v5;
    v3 = (LPVOID *)(v5 - 4);
    v4 = (__int64 *)v5[1];
    *v4 = *v5;
    *(_QWORD *)(v2 + 8) = v4;
    CoTaskMemFree((LPVOID)*(v5 - 3));
    CoTaskMemFree(v3[3]);
    CoTaskMemFree(v3);
  }
}

```

## disassembly

```asm
0x18002787c  mov     [rsp+arg_0], rbx
0x180027881  push    rdi
0x180027882  sub     rsp, 20h
0x180027886  lea     rax, ??_7CEnumStreamMapBase@@6B@; const CEnumStreamMapBase::`vftable'
0x18002788d  mov     [rcx], rax
0x180027890  lea     rdi, [rcx+20h]
0x180027894  jmp     short loc_1800278C5
0x180027896  mov     rcx, [rdx]
0x180027899  lea     rbx, [rdx-20h]
0x18002789d  mov     rax, [rdx+8]
0x1800278a1  mov     [rax], rcx
0x1800278a4  mov     [rcx+8], rax
0x1800278a8  mov     rcx, [rbx+8]; pv
0x1800278ac  call    cs:__imp_CoTaskMemFree
0x1800278b2  mov     rcx, [rbx+18h]; pv
0x1800278b6  call    cs:__imp_CoTaskMemFree
0x1800278bc  mov     rcx, rbx; pv
0x1800278bf  call    cs:__imp_CoTaskMemFree
0x1800278c5  mov     rdx, [rdi]
0x1800278c8  cmp     rdx, rdi
0x1800278cb  jnz     short loc_180027896
0x1800278cd  mov     rbx, [rsp+28h+arg_0]
0x1800278d2  add     rsp, 20h
0x1800278d6  pop     rdi
0x1800278d7  retn
```
