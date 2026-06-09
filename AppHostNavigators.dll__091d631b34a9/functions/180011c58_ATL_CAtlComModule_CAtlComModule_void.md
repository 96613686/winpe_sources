# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180011c58`
- end: `0x180011cc8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013f30`

## callees

- `0x180011c58`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011cac`
- `KERNEL32!DeleteCriticalSection` at `0x180011cac`

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
0x180011c58  mov     [rsp+arg_0], rbx
0x180011c5d  mov     [rsp+arg_8], rsi
0x180011c62  push    rdi
0x180011c63  sub     rsp, 20h
0x180011c67  cmp     dword ptr [rcx], 0
0x180011c6a  mov     rbx, rcx
0x180011c6d  jz      short loc_180011CB8
0x180011c6f  mov     rdi, [rcx+10h]
0x180011c73  cmp     rdi, [rcx+18h]
0x180011c77  jnb     short loc_180011CA8
0x180011c79  mov     rsi, [rdi]
0x180011c7c  test    rsi, rsi
0x180011c7f  jz      short loc_180011C9E
0x180011c81  mov     rcx, [rsi+20h]
0x180011c85  test    rcx, rcx
0x180011c88  jz      short loc_180011C96
0x180011c8a  mov     rax, [rcx]
0x180011c8d  mov     rax, [rax+10h]
0x180011c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c96  mov     qword ptr [rsi+20h], 0
0x180011c9e  add     rdi, 8
0x180011ca2  cmp     rdi, [rbx+18h]
0x180011ca6  jb      short loc_180011C79
0x180011ca8  lea     rcx, [rbx+20h]; lpCriticalSection
0x180011cac  call    cs:__imp_DeleteCriticalSection
0x180011cb2  mov     dword ptr [rbx], 0
0x180011cb8  mov     rbx, [rsp+28h+arg_0]
0x180011cbd  mov     rsi, [rsp+28h+arg_8]
0x180011cc2  add     rsp, 20h
0x180011cc6  pop     rdi
0x180011cc7  retn
```
