# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000e1ac`
- end: `0x18000e21c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e950`

## callees

- `0x18000e1ac`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e200`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e200`

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
0x18000e1ac  mov     [rsp+arg_0], rbx
0x18000e1b1  mov     [rsp+arg_8], rsi
0x18000e1b6  push    rdi
0x18000e1b7  sub     rsp, 20h
0x18000e1bb  cmp     dword ptr [rcx], 0
0x18000e1be  mov     rbx, rcx
0x18000e1c1  jz      short loc_18000E20C
0x18000e1c3  mov     rdi, [rcx+10h]
0x18000e1c7  cmp     rdi, [rcx+18h]
0x18000e1cb  jnb     short loc_18000E1FC
0x18000e1cd  mov     rsi, [rdi]
0x18000e1d0  test    rsi, rsi
0x18000e1d3  jz      short loc_18000E1F2
0x18000e1d5  mov     rcx, [rsi+20h]
0x18000e1d9  test    rcx, rcx
0x18000e1dc  jz      short loc_18000E1EA
0x18000e1de  mov     rax, [rcx]
0x18000e1e1  mov     rax, [rax+10h]
0x18000e1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ea  mov     qword ptr [rsi+20h], 0
0x18000e1f2  add     rdi, 8
0x18000e1f6  cmp     rdi, [rbx+18h]
0x18000e1fa  jb      short loc_18000E1CD
0x18000e1fc  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000e200  call    cs:__imp_DeleteCriticalSection
0x18000e206  mov     dword ptr [rbx], 0
0x18000e20c  mov     rbx, [rsp+28h+arg_0]
0x18000e211  mov     rsi, [rsp+28h+arg_8]
0x18000e216  add     rsp, 20h
0x18000e21a  pop     rdi
0x18000e21b  retn
```
