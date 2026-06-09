# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180022c8c`
- end: `0x180022cfc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800231b0`

## callees

- `0x180022c8c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ce0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022ce0`

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
0x180022c8c  mov     [rsp+arg_0], rbx
0x180022c91  mov     [rsp+arg_8], rsi
0x180022c96  push    rdi
0x180022c97  sub     rsp, 20h
0x180022c9b  cmp     dword ptr [rcx], 0
0x180022c9e  mov     rbx, rcx
0x180022ca1  jz      short loc_180022CEC
0x180022ca3  mov     rdi, [rcx+10h]
0x180022ca7  cmp     rdi, [rcx+18h]
0x180022cab  jnb     short loc_180022CDC
0x180022cad  mov     rsi, [rdi]
0x180022cb0  test    rsi, rsi
0x180022cb3  jz      short loc_180022CD2
0x180022cb5  mov     rcx, [rsi+20h]
0x180022cb9  test    rcx, rcx
0x180022cbc  jz      short loc_180022CCA
0x180022cbe  mov     rax, [rcx]
0x180022cc1  mov     rax, [rax+10h]
0x180022cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cca  mov     qword ptr [rsi+20h], 0
0x180022cd2  add     rdi, 8
0x180022cd6  cmp     rdi, [rbx+18h]
0x180022cda  jb      short loc_180022CAD
0x180022cdc  lea     rcx, [rbx+20h]; lpCriticalSection
0x180022ce0  call    cs:__imp_DeleteCriticalSection
0x180022ce6  mov     dword ptr [rbx], 0
0x180022cec  mov     rbx, [rsp+28h+arg_0]
0x180022cf1  mov     rsi, [rsp+28h+arg_8]
0x180022cf6  add     rsp, 20h
0x180022cfa  pop     rdi
0x180022cfb  retn
```
