# DiagHubCommon::AutoEvent::~AutoEvent(void)

- ea: `0x1400023c0`
- end: `0x1400023e2`
- name: `??1AutoEvent@DiagHubCommon@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(DiagHubCommon::AutoEvent *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014e8c`

## callees

- `0x1400023c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400023d7`
- `KERNEL32!CloseHandle` at `0x1400023d7`

## pseudocode

```c
void __fastcall DiagHubCommon::AutoEvent::~AutoEvent(void **this)
{
  void *v1; // rax

  v1 = *this;
  if ( *this != (void *)-1LL )
  {
    *this = (void *)-1LL;
    CloseHandle(v1);
  }
}

```

## disassembly

```asm
0x1400023c0  sub     rsp, 28h
0x1400023c4  mov     rax, [rcx]
0x1400023c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400023cb  jz      short loc_1400023DD
0x1400023cd  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1400023d4  mov     rcx, rax; hObject
0x1400023d7  call    cs:__imp_CloseHandle
0x1400023dd  add     rsp, 28h
0x1400023e1  retn
```
