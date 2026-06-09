# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180006d10`
- end: `0x180006d80`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019f40`

## callees

- `0x180006d10`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d64`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006d64`

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
0x180006d10  mov     [rsp+arg_0], rbx
0x180006d15  mov     [rsp+arg_8], rsi
0x180006d1a  push    rdi
0x180006d1b  sub     rsp, 20h
0x180006d1f  cmp     dword ptr [rcx], 0
0x180006d22  mov     rbx, rcx
0x180006d25  jz      short loc_180006D70
0x180006d27  mov     rdi, [rcx+10h]
0x180006d2b  cmp     rdi, [rcx+18h]
0x180006d2f  jnb     short loc_180006D60
0x180006d31  mov     rsi, [rdi]
0x180006d34  test    rsi, rsi
0x180006d37  jz      short loc_180006D56
0x180006d39  mov     rcx, [rsi+20h]
0x180006d3d  test    rcx, rcx
0x180006d40  jz      short loc_180006D4E
0x180006d42  mov     rax, [rcx]
0x180006d45  mov     rax, [rax+10h]
0x180006d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4e  mov     qword ptr [rsi+20h], 0
0x180006d56  add     rdi, 8
0x180006d5a  cmp     rdi, [rbx+18h]
0x180006d5e  jb      short loc_180006D31
0x180006d60  lea     rcx, [rbx+20h]; lpCriticalSection
0x180006d64  call    cs:__imp_DeleteCriticalSection
0x180006d6a  mov     dword ptr [rbx], 0
0x180006d70  mov     rbx, [rsp+28h+arg_0]
0x180006d75  mov     rsi, [rsp+28h+arg_8]
0x180006d7a  add     rsp, 20h
0x180006d7e  pop     rdi
0x180006d7f  retn
```
