# ATL::CAtlComModule::Term(void)

- ea: `0x180033d7c`
- end: `0x180033dec`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b160`

## callees

- `0x180033d7c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dd0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033dd0`

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
0x180033d7c  mov     [rsp+arg_0], rbx
0x180033d81  mov     [rsp+arg_8], rsi
0x180033d86  push    rdi
0x180033d87  sub     rsp, 20h
0x180033d8b  cmp     dword ptr [rcx], 0
0x180033d8e  mov     rbx, rcx
0x180033d91  jz      short loc_180033DDC
0x180033d93  mov     rdi, [rcx+10h]
0x180033d97  cmp     rdi, [rcx+18h]
0x180033d9b  jnb     short loc_180033DCC
0x180033d9d  mov     rsi, [rdi]
0x180033da0  test    rsi, rsi
0x180033da3  jz      short loc_180033DC2
0x180033da5  mov     rcx, [rsi+20h]
0x180033da9  test    rcx, rcx
0x180033dac  jz      short loc_180033DBA
0x180033dae  mov     rax, [rcx]
0x180033db1  mov     rax, [rax+10h]
0x180033db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dba  mov     qword ptr [rsi+20h], 0
0x180033dc2  add     rdi, 8
0x180033dc6  cmp     rdi, [rbx+18h]
0x180033dca  jb      short loc_180033D9D
0x180033dcc  lea     rcx, [rbx+20h]; lpCriticalSection
0x180033dd0  call    cs:__imp_DeleteCriticalSection
0x180033dd6  mov     dword ptr [rbx], 0
0x180033ddc  mov     rbx, [rsp+28h+arg_0]
0x180033de1  mov     rsi, [rsp+28h+arg_8]
0x180033de6  add     rsp, 20h
0x180033dea  pop     rdi
0x180033deb  retn
```
