# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180011e98`
- end: `0x180011f08`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800126d0`

## callees

- `0x180011e98`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011eec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011eec`

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
0x180011e98  mov     [rsp+arg_0], rbx
0x180011e9d  mov     [rsp+arg_8], rsi
0x180011ea2  push    rdi
0x180011ea3  sub     rsp, 20h
0x180011ea7  cmp     dword ptr [rcx], 0
0x180011eaa  mov     rbx, rcx
0x180011ead  jz      short loc_180011EF8
0x180011eaf  mov     rdi, [rcx+10h]
0x180011eb3  cmp     rdi, [rcx+18h]
0x180011eb7  jnb     short loc_180011EE8
0x180011eb9  mov     rsi, [rdi]
0x180011ebc  test    rsi, rsi
0x180011ebf  jz      short loc_180011EDE
0x180011ec1  mov     rcx, [rsi+20h]
0x180011ec5  test    rcx, rcx
0x180011ec8  jz      short loc_180011ED6
0x180011eca  mov     rax, [rcx]
0x180011ecd  mov     rax, [rax+10h]
0x180011ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed6  mov     qword ptr [rsi+20h], 0
0x180011ede  add     rdi, 8
0x180011ee2  cmp     rdi, [rbx+18h]
0x180011ee6  jb      short loc_180011EB9
0x180011ee8  lea     rcx, [rbx+20h]; lpCriticalSection
0x180011eec  call    cs:__imp_DeleteCriticalSection
0x180011ef2  mov     dword ptr [rbx], 0
0x180011ef8  mov     rbx, [rsp+28h+arg_0]
0x180011efd  mov     rsi, [rsp+28h+arg_8]
0x180011f02  add     rsp, 20h
0x180011f06  pop     rdi
0x180011f07  retn
```
