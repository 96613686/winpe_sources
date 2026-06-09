# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18005562c`
- end: `0x18005569c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005dae0`

## callees

- `0x18005562c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055680`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055680`

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
0x18005562c  mov     [rsp+arg_0], rbx
0x180055631  mov     [rsp+arg_8], rsi
0x180055636  push    rdi
0x180055637  sub     rsp, 20h
0x18005563b  cmp     dword ptr [rcx], 0
0x18005563e  mov     rbx, rcx
0x180055641  jz      short loc_18005568C
0x180055643  mov     rdi, [rcx+10h]
0x180055647  cmp     rdi, [rcx+18h]
0x18005564b  jnb     short loc_18005567C
0x18005564d  mov     rsi, [rdi]
0x180055650  test    rsi, rsi
0x180055653  jz      short loc_180055672
0x180055655  mov     rcx, [rsi+20h]
0x180055659  test    rcx, rcx
0x18005565c  jz      short loc_18005566A
0x18005565e  mov     rax, [rcx]
0x180055661  mov     rax, [rax+10h]
0x180055665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005566a  mov     qword ptr [rsi+20h], 0
0x180055672  add     rdi, 8
0x180055676  cmp     rdi, [rbx+18h]
0x18005567a  jb      short loc_18005564D
0x18005567c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180055680  call    cs:__imp_DeleteCriticalSection
0x180055686  mov     dword ptr [rbx], 0
0x18005568c  mov     rbx, [rsp+28h+arg_0]
0x180055691  mov     rsi, [rsp+28h+arg_8]
0x180055696  add     rsp, 20h
0x18005569a  pop     rdi
0x18005569b  retn
```
