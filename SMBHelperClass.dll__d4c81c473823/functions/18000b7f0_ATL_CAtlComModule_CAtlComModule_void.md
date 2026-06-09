# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000b7f0`
- end: `0x18000b860`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011610`

## callees

- `0x18000b7f0`
- `0x180012010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b844`
- `KERNEL32!DeleteCriticalSection` at `0x18000b844`

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
0x18000b7f0  mov     [rsp+arg_0], rbx
0x18000b7f5  mov     [rsp+arg_8], rsi
0x18000b7fa  push    rdi
0x18000b7fb  sub     rsp, 20h
0x18000b7ff  cmp     dword ptr [rcx], 0
0x18000b802  mov     rbx, rcx
0x18000b805  jz      short loc_18000B850
0x18000b807  mov     rdi, [rcx+10h]
0x18000b80b  cmp     rdi, [rcx+18h]
0x18000b80f  jnb     short loc_18000B840
0x18000b811  mov     rsi, [rdi]
0x18000b814  test    rsi, rsi
0x18000b817  jz      short loc_18000B836
0x18000b819  mov     rcx, [rsi+20h]
0x18000b81d  test    rcx, rcx
0x18000b820  jz      short loc_18000B82E
0x18000b822  mov     rax, [rcx]
0x18000b825  mov     rax, [rax+10h]
0x18000b829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82e  mov     qword ptr [rsi+20h], 0
0x18000b836  add     rdi, 8
0x18000b83a  cmp     rdi, [rbx+18h]
0x18000b83e  jb      short loc_18000B811
0x18000b840  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000b844  call    cs:__imp_DeleteCriticalSection
0x18000b84a  mov     dword ptr [rbx], 0
0x18000b850  mov     rbx, [rsp+28h+arg_0]
0x18000b855  mov     rsi, [rsp+28h+arg_8]
0x18000b85a  add     rsp, 20h
0x18000b85e  pop     rdi
0x18000b85f  retn
```
