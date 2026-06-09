# CTieringEngineService::`vector deleting destructor'(uint)

- ea: `0x140002cd0`
- end: `0x140002d20`
- name: `??_ECTieringEngineService@@UEAAPEAXI@Z`
- size: `80`
- prototype: `CTieringEngineService *__fastcall(CTieringEngineService *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x140001a00`
- `0x1400027d0`
- `0x140002cd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002ceb`

## pseudocode

```c
CTieringEngineService *__fastcall CTieringEngineService::`vector deleting destructor'(
        CTieringEngineService *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 84);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 84) = 0;
  }
  ATL::CAtlExeModuleT<CTieringEngineService>::~CAtlExeModuleT<CTieringEngineService>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140002cd0  mov     [rsp+arg_0], rbx
0x140002cd5  push    rdi
0x140002cd6  sub     rsp, 20h
0x140002cda  mov     rbx, rcx
0x140002cdd  mov     edi, edx
0x140002cdf  mov     rcx, [rcx+2A0h]; hObject
0x140002ce6  test    rcx, rcx
0x140002ce9  jz      short loc_140002CFC
0x140002ceb  call    cs:__imp_CloseHandle
0x140002cf1  mov     qword ptr [rbx+2A0h], 0
0x140002cfc  mov     rcx, rbx; this
0x140002cff  call    ??1?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@UEAA@XZ; ATL::CAtlExeModuleT<CTieringEngineService>::~CAtlExeModuleT<CTieringEngineService>(void)
0x140002d04  test    dil, 1
0x140002d08  jz      short loc_140002D12
0x140002d0a  mov     rcx, rbx; Block
0x140002d0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002d12  mov     rax, rbx
0x140002d15  mov     rbx, [rsp+28h+arg_0]
0x140002d1a  add     rsp, 20h
0x140002d1e  pop     rdi
0x140002d1f  retn
```
