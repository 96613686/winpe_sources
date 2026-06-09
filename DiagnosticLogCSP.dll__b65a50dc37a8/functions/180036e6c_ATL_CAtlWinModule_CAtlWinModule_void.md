# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x180036e6c`
- end: `0x180036ed8`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800386f0`

## callees

- `0x1800025fc`
- `0x180036e6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036ea1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036ea1`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v2 = (void *)*((_QWORD *)this + 7);
    if ( v2 )
    {
      free(v2);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180036e6c  push    rbx
0x180036e6e  sub     rsp, 20h
0x180036e72  mov     rbx, rcx
0x180036e75  test    rcx, rcx
0x180036e78  jz      short loc_180036EB3
0x180036e7a  cmp     dword ptr [rcx], 48h ; 'H'
0x180036e7d  jnz     short loc_180036EB3
0x180036e7f  mov     rcx, [rcx+38h]; Block
0x180036e83  test    rcx, rcx
0x180036e86  jz      short loc_180036E95
0x180036e88  call    free
0x180036e8d  mov     qword ptr [rbx+38h], 0
0x180036e95  lea     rcx, [rbx+8]; lpCriticalSection
0x180036e99  mov     qword ptr [rbx+40h], 0
0x180036ea1  call    cs:__imp_DeleteCriticalSection
0x180036ea8  nop     dword ptr [rax+rax+00h]
0x180036ead  mov     dword ptr [rbx], 0
0x180036eb3  mov     rcx, [rbx+38h]; Block
0x180036eb7  test    rcx, rcx
0x180036eba  jz      short loc_180036EC9
0x180036ebc  call    free
0x180036ec1  mov     qword ptr [rbx+38h], 0
0x180036ec9  mov     qword ptr [rbx+40h], 0
0x180036ed1  add     rsp, 20h
0x180036ed5  pop     rbx
0x180036ed6  retn
```
