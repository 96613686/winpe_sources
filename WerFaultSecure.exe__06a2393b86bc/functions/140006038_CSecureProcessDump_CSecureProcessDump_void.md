# CSecureProcessDump::~CSecureProcessDump(void)

- ea: `0x140006038`
- end: `0x14000609e`
- name: `??1CSecureProcessDump@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CSecureProcessDump *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400068c0`
- `0x140011458`

## callees

- `0x140006038`
- `0x1400060a4`
- `0x14000e750`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006080`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140006052`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140006052`

## pseudocode

```c
void __fastcall CSecureProcessDump::~CSecureProcessDump(CSecureProcessDump *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  CSecureProcessDump::Cleanup((LPCRITICAL_SECTION)this);
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 314);
  if ( v2 )
    CloseThreadpoolWait(v2);
  v3 = (void *)*((_QWORD *)this + 313);
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 312);
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  CDumpCollection::~CDumpCollection((HMODULE *)this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x140006038  push    rbx
0x14000603a  sub     rsp, 20h
0x14000603e  mov     rbx, rcx
0x140006041  call    ?Cleanup@CSecureProcessDump@@QEAAXXZ; CSecureProcessDump::Cleanup(void)
0x140006046  mov     rcx, [rbx+9D0h]; pwa
0x14000604d  test    rcx, rcx
0x140006050  jz      short loc_140006058
0x140006052  call    cs:__imp_CloseThreadpoolWait
0x140006058  mov     rcx, [rbx+9C8h]; hObject
0x14000605f  lea     rax, [rcx+1]
0x140006063  cmp     rax, 1
0x140006067  jbe     short loc_14000606F
0x140006069  call    cs:__imp_CloseHandle
0x14000606f  mov     rcx, [rbx+9C0h]; hObject
0x140006076  lea     rax, [rcx+1]
0x14000607a  cmp     rax, 1
0x14000607e  jbe     short loc_140006086
0x140006080  call    cs:__imp_CloseHandle
0x140006086  lea     rcx, [rbx+30h]; this
0x14000608a  call    ??1CDumpCollection@@QEAA@XZ; CDumpCollection::~CDumpCollection(void)
0x14000608f  mov     rcx, rbx
0x140006092  add     rsp, 20h
0x140006096  pop     rbx
0x140006097  jmp     cs:__imp_DeleteCriticalSection
```
