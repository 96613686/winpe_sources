# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180013490`
- end: `0x180013500`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013b90`

## callees

- `0x180013490`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800134e4`
- `KERNEL32!DeleteCriticalSection` at `0x1800134e4`

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
0x180013490  mov     [rsp+arg_0], rbx
0x180013495  mov     [rsp+arg_8], rsi
0x18001349a  push    rdi
0x18001349b  sub     rsp, 20h
0x18001349f  cmp     dword ptr [rcx], 0
0x1800134a2  mov     rbx, rcx
0x1800134a5  jz      short loc_1800134F0
0x1800134a7  mov     rdi, [rcx+10h]
0x1800134ab  cmp     rdi, [rcx+18h]
0x1800134af  jnb     short loc_1800134E0
0x1800134b1  mov     rsi, [rdi]
0x1800134b4  test    rsi, rsi
0x1800134b7  jz      short loc_1800134D6
0x1800134b9  mov     rcx, [rsi+20h]
0x1800134bd  test    rcx, rcx
0x1800134c0  jz      short loc_1800134CE
0x1800134c2  mov     rax, [rcx]
0x1800134c5  mov     rax, [rax+10h]
0x1800134c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ce  mov     qword ptr [rsi+20h], 0
0x1800134d6  add     rdi, 8
0x1800134da  cmp     rdi, [rbx+18h]
0x1800134de  jb      short loc_1800134B1
0x1800134e0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800134e4  call    cs:__imp_DeleteCriticalSection
0x1800134ea  mov     dword ptr [rbx], 0
0x1800134f0  mov     rbx, [rsp+28h+arg_0]
0x1800134f5  mov     rsi, [rsp+28h+arg_8]
0x1800134fa  add     rsp, 20h
0x1800134fe  pop     rdi
0x1800134ff  retn
```
