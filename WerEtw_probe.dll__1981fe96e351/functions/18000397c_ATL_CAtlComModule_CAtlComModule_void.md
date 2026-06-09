# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000397c`
- end: `0x1800039ec`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028e50`

## callees

- `0x18000397c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039d0`

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
0x18000397c  mov     [rsp+arg_0], rbx
0x180003981  mov     [rsp+arg_8], rsi
0x180003986  push    rdi
0x180003987  sub     rsp, 20h
0x18000398b  cmp     dword ptr [rcx], 0
0x18000398e  mov     rbx, rcx
0x180003991  jz      short loc_1800039DC
0x180003993  mov     rdi, [rcx+10h]
0x180003997  cmp     rdi, [rcx+18h]
0x18000399b  jnb     short loc_1800039CC
0x18000399d  mov     rsi, [rdi]
0x1800039a0  test    rsi, rsi
0x1800039a3  jz      short loc_1800039C2
0x1800039a5  mov     rcx, [rsi+20h]
0x1800039a9  test    rcx, rcx
0x1800039ac  jz      short loc_1800039BA
0x1800039ae  mov     rax, [rcx]
0x1800039b1  mov     rax, [rax+10h]
0x1800039b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ba  mov     qword ptr [rsi+20h], 0
0x1800039c2  add     rdi, 8
0x1800039c6  cmp     rdi, [rbx+18h]
0x1800039ca  jb      short loc_18000399D
0x1800039cc  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800039d0  call    cs:__imp_DeleteCriticalSection
0x1800039d6  mov     dword ptr [rbx], 0
0x1800039dc  mov     rbx, [rsp+28h+arg_0]
0x1800039e1  mov     rsi, [rsp+28h+arg_8]
0x1800039e6  add     rsp, 20h
0x1800039ea  pop     rdi
0x1800039eb  retn
```
