# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180010580`
- end: `0x1800105f0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016990`

## callees

- `0x180010580`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800105d4`
- `KERNEL32!DeleteCriticalSection` at `0x1800105d4`

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
0x180010580  mov     [rsp+arg_0], rbx
0x180010585  mov     [rsp+arg_8], rsi
0x18001058a  push    rdi
0x18001058b  sub     rsp, 20h
0x18001058f  cmp     dword ptr [rcx], 0
0x180010592  mov     rbx, rcx
0x180010595  jz      short loc_1800105E0
0x180010597  mov     rdi, [rcx+10h]
0x18001059b  cmp     rdi, [rcx+18h]
0x18001059f  jnb     short loc_1800105D0
0x1800105a1  mov     rsi, [rdi]
0x1800105a4  test    rsi, rsi
0x1800105a7  jz      short loc_1800105C6
0x1800105a9  mov     rcx, [rsi+20h]
0x1800105ad  test    rcx, rcx
0x1800105b0  jz      short loc_1800105BE
0x1800105b2  mov     rax, [rcx]
0x1800105b5  mov     rax, [rax+10h]
0x1800105b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105be  mov     qword ptr [rsi+20h], 0
0x1800105c6  add     rdi, 8
0x1800105ca  cmp     rdi, [rbx+18h]
0x1800105ce  jb      short loc_1800105A1
0x1800105d0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800105d4  call    cs:__imp_DeleteCriticalSection
0x1800105da  mov     dword ptr [rbx], 0
0x1800105e0  mov     rbx, [rsp+28h+arg_0]
0x1800105e5  mov     rsi, [rsp+28h+arg_8]
0x1800105ea  add     rsp, 20h
0x1800105ee  pop     rdi
0x1800105ef  retn
```
