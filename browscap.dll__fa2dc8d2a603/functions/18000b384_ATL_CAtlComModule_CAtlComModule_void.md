# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000b384`
- end: `0x18000b3f4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c2d0`

## callees

- `0x18000b384`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b3d8`
- `KERNEL32!DeleteCriticalSection` at `0x18000b3d8`

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
0x18000b384  mov     [rsp+arg_0], rbx
0x18000b389  mov     [rsp+arg_8], rsi
0x18000b38e  push    rdi
0x18000b38f  sub     rsp, 20h
0x18000b393  cmp     dword ptr [rcx], 0
0x18000b396  mov     rbx, rcx
0x18000b399  jz      short loc_18000B3E4
0x18000b39b  mov     rdi, [rcx+10h]
0x18000b39f  cmp     rdi, [rcx+18h]
0x18000b3a3  jnb     short loc_18000B3D4
0x18000b3a5  mov     rsi, [rdi]
0x18000b3a8  test    rsi, rsi
0x18000b3ab  jz      short loc_18000B3CA
0x18000b3ad  mov     rcx, [rsi+20h]
0x18000b3b1  test    rcx, rcx
0x18000b3b4  jz      short loc_18000B3C2
0x18000b3b6  mov     rax, [rcx]
0x18000b3b9  mov     rax, [rax+10h]
0x18000b3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c2  mov     qword ptr [rsi+20h], 0
0x18000b3ca  add     rdi, 8
0x18000b3ce  cmp     rdi, [rbx+18h]
0x18000b3d2  jb      short loc_18000B3A5
0x18000b3d4  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000b3d8  call    cs:__imp_DeleteCriticalSection
0x18000b3de  mov     dword ptr [rbx], 0
0x18000b3e4  mov     rbx, [rsp+28h+arg_0]
0x18000b3e9  mov     rsi, [rsp+28h+arg_8]
0x18000b3ee  add     rsp, 20h
0x18000b3f2  pop     rdi
0x18000b3f3  retn
```
