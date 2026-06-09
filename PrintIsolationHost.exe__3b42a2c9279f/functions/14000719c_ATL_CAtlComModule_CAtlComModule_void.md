# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x14000719c`
- end: `0x14000720c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007900`

## callees

- `0x14000719c`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400071f0`
- `KERNEL32!DeleteCriticalSection` at `0x1400071f0`

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
0x14000719c  mov     [rsp+arg_0], rbx
0x1400071a1  mov     [rsp+arg_8], rsi
0x1400071a6  push    rdi
0x1400071a7  sub     rsp, 20h
0x1400071ab  cmp     dword ptr [rcx], 0
0x1400071ae  mov     rbx, rcx
0x1400071b1  jz      short loc_1400071FC
0x1400071b3  mov     rdi, [rcx+10h]
0x1400071b7  cmp     rdi, [rcx+18h]
0x1400071bb  jnb     short loc_1400071EC
0x1400071bd  mov     rsi, [rdi]
0x1400071c0  test    rsi, rsi
0x1400071c3  jz      short loc_1400071E2
0x1400071c5  mov     rcx, [rsi+20h]
0x1400071c9  test    rcx, rcx
0x1400071cc  jz      short loc_1400071DA
0x1400071ce  mov     rax, [rcx]
0x1400071d1  mov     rax, [rax+10h]
0x1400071d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071da  mov     qword ptr [rsi+20h], 0
0x1400071e2  add     rdi, 8
0x1400071e6  cmp     rdi, [rbx+18h]
0x1400071ea  jb      short loc_1400071BD
0x1400071ec  lea     rcx, [rbx+20h]; lpCriticalSection
0x1400071f0  call    cs:__imp_DeleteCriticalSection
0x1400071f6  mov     dword ptr [rbx], 0
0x1400071fc  mov     rbx, [rsp+28h+arg_0]
0x140007201  mov     rsi, [rsp+28h+arg_8]
0x140007206  add     rsp, 20h
0x14000720a  pop     rdi
0x14000720b  retn
```
