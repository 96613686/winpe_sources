# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180029438`
- end: `0x1800294a8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003e400`

## callees

- `0x180029438`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002948c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002948c`

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
0x180029438  mov     [rsp+arg_0], rbx
0x18002943d  mov     [rsp+arg_8], rsi
0x180029442  push    rdi
0x180029443  sub     rsp, 20h
0x180029447  cmp     dword ptr [rcx], 0
0x18002944a  mov     rbx, rcx
0x18002944d  jz      short loc_180029498
0x18002944f  mov     rdi, [rcx+10h]
0x180029453  cmp     rdi, [rcx+18h]
0x180029457  jnb     short loc_180029488
0x180029459  mov     rsi, [rdi]
0x18002945c  test    rsi, rsi
0x18002945f  jz      short loc_18002947E
0x180029461  mov     rcx, [rsi+20h]
0x180029465  test    rcx, rcx
0x180029468  jz      short loc_180029476
0x18002946a  mov     rax, [rcx]
0x18002946d  mov     rax, [rax+10h]
0x180029471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029476  mov     qword ptr [rsi+20h], 0
0x18002947e  add     rdi, 8
0x180029482  cmp     rdi, [rbx+18h]
0x180029486  jb      short loc_180029459
0x180029488  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002948c  call    cs:__imp_DeleteCriticalSection
0x180029492  mov     dword ptr [rbx], 0
0x180029498  mov     rbx, [rsp+28h+arg_0]
0x18002949d  mov     rsi, [rsp+28h+arg_8]
0x1800294a2  add     rsp, 20h
0x1800294a6  pop     rdi
0x1800294a7  retn
```
