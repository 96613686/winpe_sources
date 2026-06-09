# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180014f68`
- end: `0x180014fd8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017dd0`

## callees

- `0x180014f68`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014fbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014fbc`

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
0x180014f68  mov     [rsp+arg_0], rbx
0x180014f6d  mov     [rsp+arg_8], rsi
0x180014f72  push    rdi
0x180014f73  sub     rsp, 20h
0x180014f77  cmp     dword ptr [rcx], 0
0x180014f7a  mov     rbx, rcx
0x180014f7d  jz      short loc_180014FC8
0x180014f7f  mov     rdi, [rcx+10h]
0x180014f83  cmp     rdi, [rcx+18h]
0x180014f87  jnb     short loc_180014FB8
0x180014f89  mov     rsi, [rdi]
0x180014f8c  test    rsi, rsi
0x180014f8f  jz      short loc_180014FAE
0x180014f91  mov     rcx, [rsi+20h]
0x180014f95  test    rcx, rcx
0x180014f98  jz      short loc_180014FA6
0x180014f9a  mov     rax, [rcx]
0x180014f9d  mov     rax, [rax+10h]
0x180014fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fa6  mov     qword ptr [rsi+20h], 0
0x180014fae  add     rdi, 8
0x180014fb2  cmp     rdi, [rbx+18h]
0x180014fb6  jb      short loc_180014F89
0x180014fb8  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014fbc  call    cs:__imp_DeleteCriticalSection
0x180014fc2  mov     dword ptr [rbx], 0
0x180014fc8  mov     rbx, [rsp+28h+arg_0]
0x180014fcd  mov     rsi, [rsp+28h+arg_8]
0x180014fd2  add     rsp, 20h
0x180014fd6  pop     rdi
0x180014fd7  retn
```
