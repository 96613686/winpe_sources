# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180008978`
- end: `0x1800089e8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a670`

## callees

- `0x180008978`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089cc`

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
0x180008978  mov     [rsp+arg_0], rbx
0x18000897d  mov     [rsp+arg_8], rsi
0x180008982  push    rdi
0x180008983  sub     rsp, 20h
0x180008987  cmp     dword ptr [rcx], 0
0x18000898a  mov     rbx, rcx
0x18000898d  jz      short loc_1800089D8
0x18000898f  mov     rdi, [rcx+10h]
0x180008993  cmp     rdi, [rcx+18h]
0x180008997  jnb     short loc_1800089C8
0x180008999  mov     rsi, [rdi]
0x18000899c  test    rsi, rsi
0x18000899f  jz      short loc_1800089BE
0x1800089a1  mov     rcx, [rsi+20h]
0x1800089a5  test    rcx, rcx
0x1800089a8  jz      short loc_1800089B6
0x1800089aa  mov     rax, [rcx]
0x1800089ad  mov     rax, [rax+10h]
0x1800089b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b6  mov     qword ptr [rsi+20h], 0
0x1800089be  add     rdi, 8
0x1800089c2  cmp     rdi, [rbx+18h]
0x1800089c6  jb      short loc_180008999
0x1800089c8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800089cc  call    cs:__imp_DeleteCriticalSection
0x1800089d2  mov     dword ptr [rbx], 0
0x1800089d8  mov     rbx, [rsp+28h+arg_0]
0x1800089dd  mov     rsi, [rsp+28h+arg_8]
0x1800089e2  add     rsp, 20h
0x1800089e6  pop     rdi
0x1800089e7  retn
```
