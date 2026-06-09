# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000cb0c`
- end: `0x18000cb7c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x18000cb0c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb60`

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
0x18000cb0c  mov     [rsp+arg_0], rbx
0x18000cb11  mov     [rsp+arg_8], rsi
0x18000cb16  push    rdi
0x18000cb17  sub     rsp, 20h
0x18000cb1b  cmp     dword ptr [rcx], 0
0x18000cb1e  mov     rbx, rcx
0x18000cb21  jz      short loc_18000CB6C
0x18000cb23  mov     rdi, [rcx+10h]
0x18000cb27  cmp     rdi, [rcx+18h]
0x18000cb2b  jnb     short loc_18000CB5C
0x18000cb2d  mov     rsi, [rdi]
0x18000cb30  test    rsi, rsi
0x18000cb33  jz      short loc_18000CB52
0x18000cb35  mov     rcx, [rsi+20h]
0x18000cb39  test    rcx, rcx
0x18000cb3c  jz      short loc_18000CB4A
0x18000cb3e  mov     rax, [rcx]
0x18000cb41  mov     rax, [rax+10h]
0x18000cb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4a  mov     qword ptr [rsi+20h], 0
0x18000cb52  add     rdi, 8
0x18000cb56  cmp     rdi, [rbx+18h]
0x18000cb5a  jb      short loc_18000CB2D
0x18000cb5c  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000cb60  call    cs:__imp_DeleteCriticalSection
0x18000cb66  mov     dword ptr [rbx], 0
0x18000cb6c  mov     rbx, [rsp+28h+arg_0]
0x18000cb71  mov     rsi, [rsp+28h+arg_8]
0x18000cb76  add     rsp, 20h
0x18000cb7a  pop     rdi
0x18000cb7b  retn
```
