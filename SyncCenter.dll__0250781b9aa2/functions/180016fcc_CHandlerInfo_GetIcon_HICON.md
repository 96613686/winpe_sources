# CHandlerInfo::GetIcon(HICON__ * *)

- ea: `0x180016fcc`
- end: `0x180017015`
- name: `?GetIcon@CHandlerInfo@@QEAAJPEAPEAUHICON__@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(CHandlerInfo *__hidden this, HICON *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004a60`
- `0x1800142c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017002`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016fe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016fe0`
- `USER32!CopyIcon` at `0x180016fed`
- `USER32!CopyIcon` at `0x180016fed`

## pseudocode

```c
__int64 __fastcall CHandlerInfo::GetIcon(CHandlerInfo *this, HICON *a2)
{
  HICON v4; // rax

  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
  v4 = CopyIcon(*((HICON *)this + 114));
  *a2 = v4;
  LODWORD(a2) = v4 == 0;
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 1));
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180016fcc  mov     [rsp+arg_0], rbx
0x180016fd1  push    rdi
0x180016fd2  sub     rsp, 20h
0x180016fd6  mov     rdi, rcx
0x180016fd9  mov     rbx, rdx
0x180016fdc  mov     rcx, [rcx+8]; lpCriticalSection
0x180016fe0  call    cs:__imp_EnterCriticalSection
0x180016fe6  mov     rcx, [rdi+390h]; hIcon
0x180016fed  call    cs:__imp_CopyIcon
0x180016ff3  mov     [rbx], rax
0x180016ff6  xor     ebx, ebx
0x180016ff8  mov     rcx, [rdi+8]; lpCriticalSection
0x180016ffc  test    rax, rax
0x180016fff  setz    bl
0x180017002  call    cs:__imp_LeaveCriticalSection
0x180017008  mov     eax, ebx
0x18001700a  mov     rbx, [rsp+28h+arg_0]
0x18001700f  add     rsp, 20h
0x180017013  pop     rdi
0x180017014  retn
```
