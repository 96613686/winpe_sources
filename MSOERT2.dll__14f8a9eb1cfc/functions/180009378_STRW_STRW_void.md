# STRW::~STRW(void)

- ea: `0x180009378`
- end: `0x1800093e9`
- name: `??1STRW@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(STRW *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093f0`
- `0x18000a9f0`
- `0x18000b390`
- `0x18000b5e0`
- `0x18000e9b0`
- `0x18000f500`
- `0x18000f5c0`
- `0x18000f8e0`
- `0x180011fec`

## callees

- `0x180009378`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800093c1`
- `KERNEL32!HeapFree` at `0x1800093c1`
- `KERNEL32!GetProcessHeap` at `0x1800093b3`
- `KERNEL32!GetProcessHeap` at `0x1800093b3`

## pseudocode

```c
void __fastcall STRW::~STRW(STRW *this)
{
  _BYTE *v2; // rax
  __int64 i; // rcx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  *(_DWORD *)this = 0;
  v2 = (_BYTE *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    for ( i = *((_QWORD *)this + 2); i; --i )
      *v2++ = 0;
  }
  if ( *((_DWORD *)this + 6) )
  {
    v4 = (void *)*((_QWORD *)this + 1);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180009378  mov     [rsp+arg_0], rbx
0x18000937d  push    rdi
0x18000937e  sub     rsp, 20h
0x180009382  mov     dword ptr [rcx], 0
0x180009388  mov     rdi, rcx
0x18000938b  mov     rax, [rcx+8]
0x18000938f  test    rax, rax
0x180009392  jz      short loc_1800093A9
0x180009394  mov     rcx, [rcx+10h]
0x180009398  test    rcx, rcx
0x18000939b  jz      short loc_1800093A9
0x18000939d  mov     byte ptr [rax], 0
0x1800093a0  inc     rax
0x1800093a3  sub     rcx, 1
0x1800093a7  jnz     short loc_18000939D
0x1800093a9  cmp     dword ptr [rdi+18h], 0
0x1800093ad  jz      short loc_1800093C7
0x1800093af  mov     rbx, [rdi+8]
0x1800093b3  call    cs:__imp_GetProcessHeap
0x1800093b9  mov     r8, rbx; lpMem
0x1800093bc  xor     edx, edx; dwFlags
0x1800093be  mov     rcx, rax; hHeap
0x1800093c1  call    cs:__imp_HeapFree
0x1800093c7  mov     rbx, [rsp+28h+arg_0]
0x1800093cc  mov     qword ptr [rdi+10h], 0
0x1800093d4  mov     qword ptr [rdi+8], 0
0x1800093dc  mov     dword ptr [rdi+18h], 0
0x1800093e3  add     rsp, 20h
0x1800093e7  pop     rdi
0x1800093e8  retn
```
