# CFSVPProvider::~CFSVPProvider(void)

- ea: `0x18021afc0`
- end: `0x18021b00c`
- name: `??1CFSVPProvider@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(CFSVPProvider *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801ab438`
- `0x180242f78`

## callees

- `0x1801ecf34`
- `0x18021afc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18021b005`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18021afe6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18021afe6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18021afd7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18021afd7`

## pseudocode

```c
void __fastcall CFSVPProvider::~CFSVPProvider(CFSVPProvider *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WORK *v3; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 3);
  if ( v2 )
    WaitForThreadpoolWorkCallbacks(v2, 1);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    CloseThreadpoolWork(v3);
    *((_QWORD *)this + 3) = 0;
  }
  CFSVPProvider::ReleaseWNFHandles(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x18021afc0  push    rbx
0x18021afc2  sub     rsp, 20h
0x18021afc6  mov     rbx, rcx
0x18021afc9  mov     rcx, [rcx+18h]; pwk
0x18021afcd  test    rcx, rcx
0x18021afd0  jz      short loc_18021AFDD
0x18021afd2  mov     edx, 1; fCancelPendingCallbacks
0x18021afd7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18021afdd  mov     rcx, [rbx+18h]; pwk
0x18021afe1  test    rcx, rcx
0x18021afe4  jz      short loc_18021AFF4
0x18021afe6  call    cs:__imp_CloseThreadpoolWork
0x18021afec  mov     qword ptr [rbx+18h], 0
0x18021aff4  mov     rcx, rbx; this
0x18021aff7  call    ?ReleaseWNFHandles@CFSVPProvider@@AEAAXXZ; CFSVPProvider::ReleaseWNFHandles(void)
0x18021affc  lea     rcx, [rbx+20h]
0x18021b000  add     rsp, 20h
0x18021b004  pop     rbx
0x18021b005  jmp     cs:__imp_DeleteCriticalSection
```
