# CallStackContext::Init(ulong,ulong)

- ea: `0x1800022b0`
- end: `0x180002329`
- name: `?Init@CallStackContext@@QEAAXKK@Z`
- size: `121`
- prototype: `void __fastcall(CallStackContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a3064`

## callees

- `0x1800022b0`
- `0x1800b0b00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000230b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000230b`

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
  memset(this, 0, 0x7C0u);
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
0x1800022b0  mov     [rsp+arg_0], rbx
0x1800022b5  push    rdi
0x1800022b6  sub     rsp, 20h
0x1800022ba  mov     edi, edx
0x1800022bc  mov     rbx, rcx
0x1800022bf  cmp     r8d, 7Ch ; '|'
0x1800022c3  jnb     short loc_1800022CA
0x1800022c5  mov     eax, r8d
0x1800022c8  jmp     short loc_1800022CF
0x1800022ca  mov     eax, 7Ch ; '|'
0x1800022cf  xor     edx, edx; Val
0x1800022d1  mov     [rcx+7C8h], eax
0x1800022d7  mov     r8d, 7C0h; Size
0x1800022dd  call    memset
0x1800022e2  xor     eax, eax
0x1800022e4  mov     [rbx+7C4h], eax
0x1800022ea  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800022f1  mov     [rbx+7E0h], rax
0x1800022f8  mov     [rbx+7CCh], eax
0x1800022fe  movups  xmmword ptr [rbx+7D0h], xmm0
0x180002305  mov     [rbx+7E8h], eax
0x18000230b  call    cs:__imp_GetCurrentThreadId
0x180002312  nop     dword ptr [rax+rax+00h]
0x180002317  mov     [rbx+7C0h], edi
0x18000231d  mov     rbx, [rsp+28h+arg_0]
0x180002322  add     rsp, 20h
0x180002326  pop     rdi
0x180002327  retn
```
