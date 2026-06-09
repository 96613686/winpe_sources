# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180006e08`
- end: `0x180006e78`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x180006e08`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006e5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006e5c`

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
0x180006e08  mov     [rsp+arg_0], rbx
0x180006e0d  mov     [rsp+arg_8], rsi
0x180006e12  push    rdi
0x180006e13  sub     rsp, 20h
0x180006e17  cmp     dword ptr [rcx], 0
0x180006e1a  mov     rbx, rcx
0x180006e1d  jz      short loc_180006E68
0x180006e1f  mov     rdi, [rcx+10h]
0x180006e23  cmp     rdi, [rcx+18h]
0x180006e27  jnb     short loc_180006E58
0x180006e29  mov     rsi, [rdi]
0x180006e2c  test    rsi, rsi
0x180006e2f  jz      short loc_180006E4E
0x180006e31  mov     rcx, [rsi+20h]
0x180006e35  test    rcx, rcx
0x180006e38  jz      short loc_180006E46
0x180006e3a  mov     rax, [rcx]
0x180006e3d  mov     rax, [rax+10h]
0x180006e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e46  mov     qword ptr [rsi+20h], 0
0x180006e4e  add     rdi, 8
0x180006e52  cmp     rdi, [rbx+18h]
0x180006e56  jb      short loc_180006E29
0x180006e58  lea     rcx, [rbx+20h]; lpCriticalSection
0x180006e5c  call    cs:__imp_DeleteCriticalSection
0x180006e62  mov     dword ptr [rbx], 0
0x180006e68  mov     rbx, [rsp+28h+arg_0]
0x180006e6d  mov     rsi, [rsp+28h+arg_8]
0x180006e72  add     rsp, 20h
0x180006e76  pop     rdi
0x180006e77  retn
```
