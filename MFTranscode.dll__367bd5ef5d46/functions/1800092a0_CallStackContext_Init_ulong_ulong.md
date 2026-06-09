# CallStackContext::Init(ulong,ulong)

- ea: `0x1800092a0`
- end: `0x180009312`
- name: `?Init@CallStackContext@@QEAAXKK@Z`
- size: `114`
- prototype: `void __fastcall(CallStackContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004ef84`

## callees

- `0x1800092a0`
- `0x180017e20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092fb`

## pseudocode

```c
void __fastcall CallStackContext::Init(GUID *this, unsigned int a2, unsigned int a3)
{
  int v5; // eax

  if ( a3 >= 0x7C )
    v5 = 124;
  else
    v5 = a3;
  *(_DWORD *)this[124].Data4 = v5;
  memset_0(this, 0, 0x7C0u);
  *(_DWORD *)&this[124].Data2 = 0;
  *(_QWORD *)&this[126].Data1 = 0;
  *(_DWORD *)&this[124].Data4[4] = 0;
  this[125] = GUID_00000000_0000_0000_0000_000000000000;
  *(_DWORD *)this[126].Data4 = 0;
  GetCurrentThreadId();
  this[124].Data1 = a2;
}

```

## disassembly

```asm
0x1800092a0  mov     [rsp+arg_0], rbx
0x1800092a5  push    rdi
0x1800092a6  sub     rsp, 20h
0x1800092aa  mov     edi, edx
0x1800092ac  mov     rbx, rcx
0x1800092af  cmp     r8d, 7Ch ; '|'
0x1800092b3  jnb     short loc_1800092BA
0x1800092b5  mov     eax, r8d
0x1800092b8  jmp     short loc_1800092BF
0x1800092ba  mov     eax, 7Ch ; '|'
0x1800092bf  xor     edx, edx; Val
0x1800092c1  mov     [rcx+7C8h], eax
0x1800092c7  mov     r8d, 7C0h; Size
0x1800092cd  call    memset_0
0x1800092d2  xor     eax, eax
0x1800092d4  mov     [rbx+7C4h], eax
0x1800092da  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800092e1  mov     [rbx+7E0h], rax
0x1800092e8  mov     [rbx+7CCh], eax
0x1800092ee  movups  xmmword ptr [rbx+7D0h], xmm0
0x1800092f5  mov     [rbx+7E8h], eax
0x1800092fb  call    cs:__imp_GetCurrentThreadId
0x180009301  mov     [rbx+7C0h], edi
0x180009307  mov     rbx, [rsp+28h+arg_0]
0x18000930c  add     rsp, 20h
0x180009310  pop     rdi
0x180009311  retn
```
