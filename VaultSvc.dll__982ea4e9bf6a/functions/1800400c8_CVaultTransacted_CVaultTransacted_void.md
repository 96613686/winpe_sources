# CVaultTransacted::~CVaultTransacted(void)

- ea: `0x1800400c8`
- end: `0x1800400ff`
- name: `??1CVaultTransacted@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CVaultTransacted *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180040160`

## callees

- `0x1800400c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800400f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800400f3`
- `ktmw32!RollbackTransaction` at `0x1800400e9`
- `ktmw32!RollbackTransaction` at `0x1800400e9`

## pseudocode

```c
void __fastcall CVaultTransacted::~CVaultTransacted(CVaultTransacted *this)
{
  char *v2; // rcx

  *(_QWORD *)this = &CVaultTransacted::`vftable';
  v2 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RollbackTransaction(v2);
    CloseHandle(*((HANDLE *)this + 1));
  }
}

```

## disassembly

```asm
0x1800400c8  push    rbx
0x1800400ca  sub     rsp, 20h
0x1800400ce  lea     rax, ??_7CVaultTransacted@@6B@; const CVaultTransacted::`vftable'
0x1800400d5  mov     rbx, rcx
0x1800400d8  mov     [rcx], rax
0x1800400db  mov     rcx, [rcx+8]; TransactionHandle
0x1800400df  lea     rax, [rcx-1]
0x1800400e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800400e7  ja      short loc_1800400F9
0x1800400e9  call    cs:__imp_RollbackTransaction
0x1800400ef  mov     rcx, [rbx+8]; hObject
0x1800400f3  call    cs:__imp_CloseHandle
0x1800400f9  add     rsp, 20h
0x1800400fd  pop     rbx
0x1800400fe  retn
```
