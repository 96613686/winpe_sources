# DpContext::~DpContext(void)

- ea: `0x1800277fc`
- end: `0x1800279cc`
- name: `??1DpContext@@QEAA@XZ`
- size: `464`
- prototype: `void __fastcall(DpContext *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cbf0`
- `0x1800275d0`
- `0x1800275fc`

## callees

- `0x18001ec80`
- `0x1800275d0`
- `0x1800277fc`
- `0x1800279d4`
- `0x180113a84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800278bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027907`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800278bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027907`
- `GDI32!DeleteObject` at `0x1800279a4`
- `GDI32!DeleteObject` at `0x1800279a4`

## pseudocode

```c
void __fastcall DpContext::~DpContext(DpContext *this, unsigned int a2)
{
  DpContext *v3; // rcx
  void *v4; // rcx
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8
  EpPaletteMap *v8; // rcx
  __int64 v9; // rcx

  v3 = (DpContext *)*((_QWORD *)this + 1);
  if ( v3 )
    DpContext::`scalar deleting destructor'(v3, 1u);
  v4 = (void *)*((_QWORD *)this + 85);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 85) = 0;
  }
  if ( !*(_QWORD *)this )
  {
    v8 = (EpPaletteMap *)*((_QWORD *)this + 84);
    if ( v8 )
    {
      EpPaletteMap::`scalar deleting destructor'(v8, a2);
      *((_QWORD *)this + 84) = 0;
    }
    v9 = *((_QWORD *)this + 83);
    if ( v9 )
    {
      GpFree(v9);
      *((_QWORD *)this + 83) = 0;
    }
  }
  *((_QWORD *)this + 88) = &GpMatrix::`vftable';
  *((_DWORD *)this + 178) = 1279869254;
  GpRegion::~GpRegion((DpContext *)((char *)this + 448));
  if ( (*((_BYTE *)this + 412) & 4) == 0 )
  {
    v5 = (void *)*((_QWORD *)this + 54);
    if ( v5 )
      HeapFree(GpRuntime::GpMemHeap, 0, v5);
  }
  *((_DWORD *)this + 103) &= ~4u;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 102) = 1279869254;
  if ( (*((_BYTE *)this + 356) & 4) == 0 )
  {
    v6 = (void *)*((_QWORD *)this + 47);
    if ( v6 )
      HeapFree(GpRuntime::GpMemHeap, 0, v6);
  }
  *((_DWORD *)this + 89) &= ~4u;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 88) = 1279869254;
  *((_QWORD *)this + 37) = &DpOutputSpan::`vftable';
  if ( (*((_BYTE *)this + 308) & 4) == 0 )
  {
    v7 = (void *)*((_QWORD *)this + 41);
    if ( v7 )
      HeapFree(GpRuntime::GpMemHeap, 0, v7);
  }
  *((_DWORD *)this + 77) &= ~4u;
  *((_DWORD *)this + 76) = 1279869254;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 62) = 1279869254;
  *((_QWORD *)this + 30) = &GpMatrix::`vftable';
  *((_DWORD *)this + 50) = 1279869254;
  *((_QWORD *)this + 24) = &GpMatrix::`vftable';
  *((_DWORD *)this + 38) = 1279869254;
  *((_QWORD *)this + 18) = &GpMatrix::`vftable';
  *((_DWORD *)this + 26) = 1279869254;
  *((_QWORD *)this + 12) = &GpMatrix::`vftable';
}

```

## disassembly

```asm
0x1800277fc  mov     [rsp+arg_0], rbx
0x180027801  mov     [rsp+arg_8], rsi
0x180027806  push    r14
0x180027808  sub     rsp, 20h
0x18002780c  mov     rbx, rcx
0x18002780f  mov     rcx, [rcx+8]; this
0x180027813  test    rcx, rcx
0x180027816  jnz     loc_180027995
0x18002781c  mov     rcx, [rbx+2A8h]; ho
0x180027823  mov     qword ptr [rbx+8], 0
0x18002782b  test    rcx, rcx
0x18002782e  jnz     loc_1800279A4
0x180027834  cmp     qword ptr [rbx], 0
0x180027838  jz      loc_180027964
0x18002783e  lea     r14, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x180027845  mov     esi, 4C494146h
0x18002784a  lea     rcx, [rbx+1C0h]; this
0x180027851  mov     [rbx+2C0h], r14
0x180027858  mov     [rbx+2C8h], esi
0x18002785e  call    ??1GpRegion@@UEAA@XZ; GpRegion::~GpRegion(void)
0x180027863  test    byte ptr [rbx+19Ch], 4
0x18002786a  jnz     short loc_180027887
0x18002786c  mov     r8, [rbx+1B0h]; lpMem
0x180027873  test    r8, r8
0x180027876  jz      short loc_180027887
0x180027878  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18002787f  xor     edx, edx; dwFlags
0x180027881  call    cs:__imp_HeapFree
0x180027887  and     dword ptr [rbx+19Ch], 0FFFFFFFBh
0x18002788e  mov     qword ptr [rbx+1B0h], 0
0x180027899  mov     [rbx+198h], esi
0x18002789f  test    byte ptr [rbx+164h], 4
0x1800278a6  jnz     short loc_1800278C3
0x1800278a8  mov     r8, [rbx+178h]; lpMem
0x1800278af  test    r8, r8
0x1800278b2  jz      short loc_1800278C3
0x1800278b4  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800278bb  xor     edx, edx; dwFlags
0x1800278bd  call    cs:__imp_HeapFree
0x1800278c3  and     dword ptr [rbx+164h], 0FFFFFFFBh
0x1800278ca  lea     rax, ??_7DpOutputSpan@@6B@; const DpOutputSpan::`vftable'
0x1800278d1  mov     qword ptr [rbx+178h], 0
0x1800278dc  mov     [rbx+160h], esi
0x1800278e2  mov     [rbx+128h], rax
0x1800278e9  test    byte ptr [rbx+134h], 4
0x1800278f0  jnz     short loc_18002790D
0x1800278f2  mov     r8, [rbx+148h]; lpMem
0x1800278f9  test    r8, r8
0x1800278fc  jz      short loc_18002790D
0x1800278fe  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180027905  xor     edx, edx; dwFlags
0x180027907  call    cs:__imp_HeapFree
0x18002790d  and     dword ptr [rbx+134h], 0FFFFFFFBh
0x180027914  mov     [rbx+130h], esi
0x18002791a  mov     qword ptr [rbx+148h], 0
0x180027925  mov     [rbx+0F8h], esi
0x18002792b  mov     [rbx+0F0h], r14
0x180027932  mov     [rbx+0C8h], esi
0x180027938  mov     [rbx+0C0h], r14
0x18002793f  mov     [rbx+98h], esi
0x180027945  mov     [rbx+90h], r14
0x18002794c  mov     [rbx+68h], esi
0x18002794f  mov     rsi, [rsp+28h+arg_8]
0x180027954  mov     [rbx+60h], r14
0x180027958  mov     rbx, [rsp+28h+arg_0]
0x18002795d  add     rsp, 20h
0x180027961  pop     r14
0x180027963  retn
0x180027964  mov     rcx, [rbx+2A0h]; this
0x18002796b  test    rcx, rcx
0x18002796e  jnz     short loc_1800279BA
0x180027970  mov     rcx, [rbx+298h]
0x180027977  test    rcx, rcx
0x18002797a  jz      loc_18002783E
0x180027980  call    GpFree
0x180027985  mov     qword ptr [rbx+298h], 0
0x180027990  jmp     loc_18002783E
0x180027995  mov     edx, 1; unsigned int
0x18002799a  call    ??_GDpContext@@QEAAPEAXI@Z; DpContext::`scalar deleting destructor'(uint)
0x18002799f  jmp     loc_18002781C
0x1800279a4  call    cs:__imp_DeleteObject
0x1800279aa  mov     qword ptr [rbx+2A8h], 0
0x1800279b5  jmp     loc_180027834
0x1800279ba  call    ??_GEpPaletteMap@@QEAAPEAXI@Z; EpPaletteMap::`scalar deleting destructor'(uint)
0x1800279bf  mov     qword ptr [rbx+2A0h], 0
0x1800279ca  jmp     short loc_180027970
```
