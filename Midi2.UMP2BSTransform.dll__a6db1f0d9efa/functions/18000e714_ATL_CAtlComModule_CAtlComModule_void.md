# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000e714`
- end: `0x18000e784`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000edb0`

## callees

- `0x18000e714`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e768`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e768`

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
0x18000e714  mov     [rsp+arg_0], rbx
0x18000e719  mov     [rsp+arg_8], rsi
0x18000e71e  push    rdi
0x18000e71f  sub     rsp, 20h
0x18000e723  cmp     dword ptr [rcx], 0
0x18000e726  mov     rbx, rcx
0x18000e729  jz      short loc_18000E774
0x18000e72b  mov     rdi, [rcx+10h]
0x18000e72f  cmp     rdi, [rcx+18h]
0x18000e733  jnb     short loc_18000E764
0x18000e735  mov     rsi, [rdi]
0x18000e738  test    rsi, rsi
0x18000e73b  jz      short loc_18000E75A
0x18000e73d  mov     rcx, [rsi+20h]
0x18000e741  test    rcx, rcx
0x18000e744  jz      short loc_18000E752
0x18000e746  mov     rax, [rcx]
0x18000e749  mov     rax, [rax+10h]
0x18000e74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e752  mov     qword ptr [rsi+20h], 0
0x18000e75a  add     rdi, 8
0x18000e75e  cmp     rdi, [rbx+18h]
0x18000e762  jb      short loc_18000E735
0x18000e764  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000e768  call    cs:__imp_DeleteCriticalSection
0x18000e76e  mov     dword ptr [rbx], 0
0x18000e774  mov     rbx, [rsp+28h+arg_0]
0x18000e779  mov     rsi, [rsp+28h+arg_8]
0x18000e77e  add     rsp, 20h
0x18000e782  pop     rdi
0x18000e783  retn
```
