# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180046130`
- end: `0x1800461a0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005cfa0`

## callees

- `0x180046130`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046184`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046184`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180046130  mov     [rsp+arg_0], rbx
0x180046135  mov     [rsp+arg_8], rsi
0x18004613a  push    rdi
0x18004613b  sub     rsp, 20h
0x18004613f  cmp     dword ptr [rcx], 0
0x180046142  mov     rbx, rcx
0x180046145  jz      short loc_180046190
0x180046147  mov     rdi, [rcx+10h]
0x18004614b  cmp     rdi, [rcx+18h]
0x18004614f  jnb     short loc_180046180
0x180046151  mov     rsi, [rdi]
0x180046154  test    rsi, rsi
0x180046157  jz      short loc_180046176
0x180046159  mov     rcx, [rsi+20h]
0x18004615d  test    rcx, rcx
0x180046160  jz      short loc_18004616E
0x180046162  mov     rax, [rcx]
0x180046165  mov     rax, [rax+10h]
0x180046169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004616e  mov     qword ptr [rsi+20h], 0
0x180046176  add     rdi, 8
0x18004617a  cmp     rdi, [rbx+18h]
0x18004617e  jb      short loc_180046151
0x180046180  lea     rcx, [rbx+20h]; lpCriticalSection
0x180046184  call    cs:__imp_DeleteCriticalSection
0x18004618a  mov     dword ptr [rbx], 0
0x180046190  mov     rbx, [rsp+28h+arg_0]
0x180046195  mov     rsi, [rsp+28h+arg_8]
0x18004619a  add     rsp, 20h
0x18004619e  pop     rdi
0x18004619f  retn
```
