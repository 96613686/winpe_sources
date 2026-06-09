# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180009d4c`
- end: `0x180009dbc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a250`

## callees

- `0x180009d4c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009da0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009da0`

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
0x180009d4c  mov     [rsp+arg_0], rbx
0x180009d51  mov     [rsp+arg_8], rsi
0x180009d56  push    rdi
0x180009d57  sub     rsp, 20h
0x180009d5b  cmp     dword ptr [rcx], 0
0x180009d5e  mov     rbx, rcx
0x180009d61  jz      short loc_180009DAC
0x180009d63  mov     rdi, [rcx+10h]
0x180009d67  cmp     rdi, [rcx+18h]
0x180009d6b  jnb     short loc_180009D9C
0x180009d6d  mov     rsi, [rdi]
0x180009d70  test    rsi, rsi
0x180009d73  jz      short loc_180009D92
0x180009d75  mov     rcx, [rsi+20h]
0x180009d79  test    rcx, rcx
0x180009d7c  jz      short loc_180009D8A
0x180009d7e  mov     rax, [rcx]
0x180009d81  mov     rax, [rax+10h]
0x180009d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8a  mov     qword ptr [rsi+20h], 0
0x180009d92  add     rdi, 8
0x180009d96  cmp     rdi, [rbx+18h]
0x180009d9a  jb      short loc_180009D6D
0x180009d9c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180009da0  call    cs:__imp_DeleteCriticalSection
0x180009da6  mov     dword ptr [rbx], 0
0x180009dac  mov     rbx, [rsp+28h+arg_0]
0x180009db1  mov     rsi, [rsp+28h+arg_8]
0x180009db6  add     rsp, 20h
0x180009dba  pop     rdi
0x180009dbb  retn
```
