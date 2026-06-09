# ATL::CAtlComModule::Term(void)

- ea: `0x14000da50`
- end: `0x14000dac0`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cb68`
- `0x140016170`

## callees

- `0x14000da50`
- `0x140017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000daa4`
- `KERNEL32!DeleteCriticalSection` at `0x14000daa4`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::Term(ATL::CAtlComModule *this)
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
0x14000da50  mov     [rsp+arg_0], rbx
0x14000da55  mov     [rsp+arg_8], rsi
0x14000da5a  push    rdi
0x14000da5b  sub     rsp, 20h
0x14000da5f  cmp     dword ptr [rcx], 0
0x14000da62  mov     rbx, rcx
0x14000da65  jz      short loc_14000DAB0
0x14000da67  mov     rdi, [rcx+10h]
0x14000da6b  cmp     rdi, [rcx+18h]
0x14000da6f  jnb     short loc_14000DAA0
0x14000da71  mov     rsi, [rdi]
0x14000da74  test    rsi, rsi
0x14000da77  jz      short loc_14000DA96
0x14000da79  mov     rcx, [rsi+20h]
0x14000da7d  test    rcx, rcx
0x14000da80  jz      short loc_14000DA8E
0x14000da82  mov     rax, [rcx]
0x14000da85  mov     rax, [rax+10h]
0x14000da89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da8e  mov     qword ptr [rsi+20h], 0
0x14000da96  add     rdi, 8
0x14000da9a  cmp     rdi, [rbx+18h]
0x14000da9e  jb      short loc_14000DA71
0x14000daa0  lea     rcx, [rbx+20h]; lpCriticalSection
0x14000daa4  call    cs:__imp_DeleteCriticalSection
0x14000daaa  mov     dword ptr [rbx], 0
0x14000dab0  mov     rbx, [rsp+28h+arg_0]
0x14000dab5  mov     rsi, [rsp+28h+arg_8]
0x14000daba  add     rsp, 20h
0x14000dabe  pop     rdi
0x14000dabf  retn
```
