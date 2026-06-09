# ShaderCacheStatisticsContainer::~ShaderCacheStatisticsContainer(void)

- ea: `0x180041724`
- end: `0x180041782`
- name: `??1ShaderCacheStatisticsContainer@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(__int64 this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018a4`
- `0x1800a71f0`

## callees

- `0x180041724`
- `0x1800516a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004177b`

## pseudocode

```c
void __fastcall ShaderCacheStatisticsContainer::~ShaderCacheStatisticsContainer(__int64 this)
{
  __int64 v1; // rbx

  v1 = this;
  if ( (unsigned int)(*(_DWORD *)(this + 8) + *(_DWORD *)(this + 24)) >= 0x14
    || *(_DWORD *)off_1800C6660
    && (this = 0x400000000000LL, (off_1800C6660[2] & 0x400000000000LL) != 0)
    && (off_1800C6660[3] & 0x400000000000LL) == off_1800C6660[3] )
  {
    ShaderCacheTelemetryHelper::LogShaderCacheStatistics(
      (ShaderCacheTelemetryHelper *)this,
      (const struct ShaderCacheStatistics *)v1);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 160));
}

```

## disassembly

```asm
0x180041724  push    rbx
0x180041726  sub     rsp, 20h
0x18004172a  mov     eax, [rcx+18h]
0x18004172d  mov     rbx, rcx
0x180041730  add     eax, [rcx+8]
0x180041733  cmp     eax, 14h
0x180041736  jnb     short loc_180041767
0x180041738  mov     rcx, cs:off_1800C6660
0x18004173f  mov     eax, [rcx]
0x180041741  test    eax, eax
0x180041743  jz      short loc_18004176F
0x180041745  mov     rdx, [rcx+18h]
0x180041749  mov     rax, [rcx+10h]
0x18004174d  mov     rcx, 400000000000h; this
0x180041757  test    rcx, rax
0x18004175a  jz      short loc_18004176F
0x18004175c  mov     rax, rdx
0x18004175f  and     rax, rcx
0x180041762  cmp     rax, rdx
0x180041765  jnz     short loc_18004176F
0x180041767  mov     rdx, rbx; struct ShaderCacheStatistics *
0x18004176a  call    ?LogShaderCacheStatistics@ShaderCacheTelemetryHelper@@QEAAXAEBUShaderCacheStatistics@@@Z; ShaderCacheTelemetryHelper::LogShaderCacheStatistics(ShaderCacheStatistics const &)
0x18004176f  lea     rcx, [rbx+0A0h]
0x180041776  add     rsp, 20h
0x18004177a  pop     rbx
0x18004177b  jmp     cs:__imp_DeleteCriticalSection
```
