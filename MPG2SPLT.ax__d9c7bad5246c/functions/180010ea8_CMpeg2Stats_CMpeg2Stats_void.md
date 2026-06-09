# CMpeg2Stats::~CMpeg2Stats(void)

- ea: `0x180010ea8`
- end: `0x180010f06`
- name: `??1CMpeg2Stats@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(CMpeg2Stats *__hidden this)`
- caller_count: `25`
- callee_count: `4`
- tags: ``

## callers

- `0x180013168`
- `0x18001a6ac`
- `0x18001d5d4`
- `0x18001d6c4`
- `0x18001d72c`
- `0x18001d788`
- `0x18001da60`
- `0x1800221c4`
- `0x1800254b8`
- `0x180025570`
- `0x1800256c8`
- `0x180025710`
- `0x18002851c`
- `0x18002858c`
- `0x180028640`
- `0x1800286ec`
- `0x180028870`
- `0x18002b26c`
- `0x18002b34c`
- `0x18002c688`
- `0x18002e084`
- `0x18002e144`
- `0x18002e198`
- `0x18002e424`
- `0x18003130c`

## callees

- `0x180010ea8`
- `0x180011010`
- `0x180011830`
- `0x180034010`

## pseudocode

```c
void __fastcall CMpeg2Stats::~CMpeg2Stats(CMpeg2Stats *this)
{
  __int64 v2; // rcx

  CMpeg2Stats::Free(this);
  v2 = *((_QWORD *)this + 1189);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1189) = 0;
  }
  Mpeg2DemuxTrace::CeHomeETWDemultiplexer::~CeHomeETWDemultiplexer((CMpeg2Stats *)((char *)this + 8256));
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180010ea8  push    rbx
0x180010eaa  sub     rsp, 20h
0x180010eae  mov     rbx, rcx
0x180010eb1  call    ?Free@CMpeg2Stats@@QEAAXXZ; CMpeg2Stats::Free(void)
0x180010eb6  mov     rcx, [rbx+2528h]
0x180010ebd  test    rcx, rcx
0x180010ec0  jz      short loc_180010ED9
0x180010ec2  mov     rax, [rcx]
0x180010ec5  mov     rax, [rax+10h]
0x180010ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ece  mov     qword ptr [rbx+2528h], 0
0x180010ed9  lea     rcx, [rbx+2040h]; this
0x180010ee0  call    ??1CeHomeETWDemultiplexer@Mpeg2DemuxTrace@@UEAA@XZ; Mpeg2DemuxTrace::CeHomeETWDemultiplexer::~CeHomeETWDemultiplexer(void)
0x180010ee5  mov     rcx, [rbx]
0x180010ee8  test    rcx, rcx
0x180010eeb  jz      short loc_180010F00
0x180010eed  mov     rax, [rcx]
0x180010ef0  mov     rax, [rax+10h]
0x180010ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef9  mov     qword ptr [rbx], 0
0x180010f00  add     rsp, 20h
0x180010f04  pop     rbx
0x180010f05  retn
```
