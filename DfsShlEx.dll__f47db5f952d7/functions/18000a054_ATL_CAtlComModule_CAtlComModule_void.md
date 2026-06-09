# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000a054`
- end: `0x18000a0c4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b2c0`

## callees

- `0x18000a054`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a0a8`
- `KERNEL32!DeleteCriticalSection` at `0x18000a0a8`

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
0x18000a054  mov     [rsp+arg_0], rbx
0x18000a059  mov     [rsp+arg_8], rsi
0x18000a05e  push    rdi
0x18000a05f  sub     rsp, 20h
0x18000a063  cmp     dword ptr [rcx], 0
0x18000a066  mov     rbx, rcx
0x18000a069  jz      short loc_18000A0B4
0x18000a06b  mov     rdi, [rcx+10h]
0x18000a06f  cmp     rdi, [rcx+18h]
0x18000a073  jnb     short loc_18000A0A4
0x18000a075  mov     rsi, [rdi]
0x18000a078  test    rsi, rsi
0x18000a07b  jz      short loc_18000A09A
0x18000a07d  mov     rcx, [rsi+20h]
0x18000a081  test    rcx, rcx
0x18000a084  jz      short loc_18000A092
0x18000a086  mov     rax, [rcx]
0x18000a089  mov     rax, [rax+10h]
0x18000a08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a092  mov     qword ptr [rsi+20h], 0
0x18000a09a  add     rdi, 8
0x18000a09e  cmp     rdi, [rbx+18h]
0x18000a0a2  jb      short loc_18000A075
0x18000a0a4  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000a0a8  call    cs:__imp_DeleteCriticalSection
0x18000a0ae  mov     dword ptr [rbx], 0
0x18000a0b4  mov     rbx, [rsp+28h+arg_0]
0x18000a0b9  mov     rsi, [rsp+28h+arg_8]
0x18000a0be  add     rsp, 20h
0x18000a0c2  pop     rdi
0x18000a0c3  retn
```
