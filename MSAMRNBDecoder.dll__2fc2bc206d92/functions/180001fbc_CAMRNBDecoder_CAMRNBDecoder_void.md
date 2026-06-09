# CAMRNBDecoder::~CAMRNBDecoder(void)

- ea: `0x180001fbc`
- end: `0x18000205a`
- name: `??1CAMRNBDecoder@@IEAA@XZ`
- size: `158`
- prototype: `void __fastcall(CAMRNBDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003030`

## callees

- `0x180001f8c`
- `0x180001fbc`
- `0x180014010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001fdb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001fdb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002047`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002047`

## pseudocode

```c
void __fastcall CAMRNBDecoder::~CAMRNBDecoder(CAMRNBDecoder *this)
{
  void *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx

  *(_QWORD *)this = &CAMRNBDecoder::`vftable';
  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 )
  {
    free(v2);
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
  }
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(_QWORD))(v3 + 24))(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  SafeRelease<IMFMediaType>((char *)this + 24);
  SafeRelease<IMFMediaType>((char *)this + 32);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 5) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  _InterlockedDecrement(&g_cRefModule);
}

```

## disassembly

```asm
0x180001fbc  push    rbx
0x180001fbe  sub     rsp, 20h
0x180001fc2  lea     rax, ??_7CAMRNBDecoder@@6B@; const CAMRNBDecoder::`vftable'
0x180001fc9  mov     rbx, rcx
0x180001fcc  mov     [rcx], rax
0x180001fcf  mov     rcx, [rcx+80h]; Block
0x180001fd6  test    rcx, rcx
0x180001fd9  jz      short loc_180001FF7
0x180001fdb  call    cs:__imp_free
0x180001fe1  mov     qword ptr [rbx+80h], 0
0x180001fec  mov     qword ptr [rbx+88h], 0
0x180001ff7  mov     rax, [rbx+8]
0x180001ffb  test    rax, rax
0x180001ffe  jz      short loc_180002014
0x180002000  mov     rcx, rax
0x180002003  mov     rax, [rax+18h]
0x180002007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200c  mov     qword ptr [rbx+8], 0
0x180002014  lea     rcx, [rbx+18h]
0x180002018  call    ??$SafeRelease@UIMFMediaType@@@@YAXPEAPEAUIMFMediaType@@@Z; SafeRelease<IMFMediaType>(IMFMediaType * *)
0x18000201d  lea     rcx, [rbx+20h]
0x180002021  call    ??$SafeRelease@UIMFMediaType@@@@YAXPEAPEAUIMFMediaType@@@Z; SafeRelease<IMFMediaType>(IMFMediaType * *)
0x180002026  mov     rcx, [rbx+28h]
0x18000202a  test    rcx, rcx
0x18000202d  jz      short loc_180002043
0x18000202f  mov     rax, [rcx]
0x180002032  mov     rax, [rax+10h]
0x180002036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203b  mov     qword ptr [rbx+28h], 0
0x180002043  lea     rcx, [rbx+30h]; lpCriticalSection
0x180002047  call    cs:__imp_DeleteCriticalSection
0x18000204d  lock dec cs:?g_cRefModule@@3JA; long g_cRefModule
0x180002054  add     rsp, 20h
0x180002058  pop     rbx
0x180002059  retn
```
