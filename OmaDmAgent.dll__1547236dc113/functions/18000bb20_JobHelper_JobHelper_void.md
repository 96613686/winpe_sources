# JobHelper::~JobHelper(void)

- ea: `0x18000bb20`
- end: `0x18000bb4f`
- name: `??1JobHelper@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(JobHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c2e8`

## callees

- `0x18000b9e0`
- `0x18000ba84`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000bb2d`
- `KERNEL32!DeleteCriticalSection` at `0x18000bb2d`

## pseudocode

```c
void __fastcall JobHelper::~JobHelper(JobHelper *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  std::list<_DeployJob>::~list<_DeployJob>((char *)this + 72);
  CBitsDownloader::~CBitsDownloader(this);
}

```

## disassembly

```asm
0x18000bb20  push    rbx
0x18000bb22  sub     rsp, 20h
0x18000bb26  mov     rbx, rcx
0x18000bb29  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18000bb2d  call    cs:__imp_DeleteCriticalSection
0x18000bb34  nop     dword ptr [rax+rax+00h]
0x18000bb39  lea     rcx, [rbx+48h]
0x18000bb3d  call    ??1?$list@U_DeployJob@@V?$allocator@U_DeployJob@@@std@@@std@@QEAA@XZ; std::list<_DeployJob>::~list<_DeployJob>(void)
0x18000bb42  mov     rcx, rbx; this
0x18000bb45  add     rsp, 20h
0x18000bb49  pop     rbx
0x18000bb4a  jmp     ??1CBitsDownloader@@UEAA@XZ; CBitsDownloader::~CBitsDownloader(void)
```
