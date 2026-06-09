# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180005db8`
- end: `0x180005e28`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800063c0`

## callees

- `0x180005db8`
- `0x180007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005e0c`
- `KERNEL32!DeleteCriticalSection` at `0x180005e0c`

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
0x180005db8  mov     [rsp+arg_0], rbx
0x180005dbd  mov     [rsp+arg_8], rsi
0x180005dc2  push    rdi
0x180005dc3  sub     rsp, 20h
0x180005dc7  cmp     dword ptr [rcx], 0
0x180005dca  mov     rbx, rcx
0x180005dcd  jz      short loc_180005E18
0x180005dcf  mov     rdi, [rcx+10h]
0x180005dd3  cmp     rdi, [rcx+18h]
0x180005dd7  jnb     short loc_180005E08
0x180005dd9  mov     rsi, [rdi]
0x180005ddc  test    rsi, rsi
0x180005ddf  jz      short loc_180005DFE
0x180005de1  mov     rcx, [rsi+20h]
0x180005de5  test    rcx, rcx
0x180005de8  jz      short loc_180005DF6
0x180005dea  mov     rax, [rcx]
0x180005ded  mov     rax, [rax+10h]
0x180005df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df6  mov     qword ptr [rsi+20h], 0
0x180005dfe  add     rdi, 8
0x180005e02  cmp     rdi, [rbx+18h]
0x180005e06  jb      short loc_180005DD9
0x180005e08  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005e0c  call    cs:__imp_DeleteCriticalSection
0x180005e12  mov     dword ptr [rbx], 0
0x180005e18  mov     rbx, [rsp+28h+arg_0]
0x180005e1d  mov     rsi, [rsp+28h+arg_8]
0x180005e22  add     rsp, 20h
0x180005e26  pop     rdi
0x180005e27  retn
```
