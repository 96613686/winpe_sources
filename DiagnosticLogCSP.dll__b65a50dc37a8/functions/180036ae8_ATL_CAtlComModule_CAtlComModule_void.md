# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180036ae8`
- end: `0x180036b5f`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180038650`

## callees

- `0x180036ae8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036b3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036b3c`

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
0x180036ae8  mov     [rsp+arg_0], rbx
0x180036aed  mov     [rsp+arg_8], rsi
0x180036af2  push    rdi
0x180036af3  sub     rsp, 20h
0x180036af7  cmp     dword ptr [rcx], 0
0x180036afa  mov     rbx, rcx
0x180036afd  jz      short loc_180036B4E
0x180036aff  mov     rdi, [rcx+10h]
0x180036b03  cmp     rdi, [rcx+18h]
0x180036b07  jnb     short loc_180036B38
0x180036b09  mov     rsi, [rdi]
0x180036b0c  test    rsi, rsi
0x180036b0f  jz      short loc_180036B2E
0x180036b11  mov     rcx, [rsi+20h]
0x180036b15  test    rcx, rcx
0x180036b18  jz      short loc_180036B26
0x180036b1a  mov     rax, [rcx]
0x180036b1d  mov     rax, [rax+10h]
0x180036b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b26  mov     qword ptr [rsi+20h], 0
0x180036b2e  add     rdi, 8
0x180036b32  cmp     rdi, [rbx+18h]
0x180036b36  jb      short loc_180036B09
0x180036b38  lea     rcx, [rbx+20h]; lpCriticalSection
0x180036b3c  call    cs:__imp_DeleteCriticalSection
0x180036b43  nop     dword ptr [rax+rax+00h]
0x180036b48  mov     dword ptr [rbx], 0
0x180036b4e  mov     rbx, [rsp+28h+arg_0]
0x180036b53  mov     rsi, [rsp+28h+arg_8]
0x180036b58  add     rsp, 20h
0x180036b5c  pop     rdi
0x180036b5d  retn
```
