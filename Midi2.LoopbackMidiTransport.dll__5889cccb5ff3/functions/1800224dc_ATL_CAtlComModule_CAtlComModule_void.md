# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800224dc`
- end: `0x18002254c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031f70`

## callees

- `0x1800224dc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022530`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022530`

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
0x1800224dc  mov     [rsp+arg_0], rbx
0x1800224e1  mov     [rsp+arg_8], rsi
0x1800224e6  push    rdi
0x1800224e7  sub     rsp, 20h
0x1800224eb  cmp     dword ptr [rcx], 0
0x1800224ee  mov     rbx, rcx
0x1800224f1  jz      short loc_18002253C
0x1800224f3  mov     rdi, [rcx+10h]
0x1800224f7  cmp     rdi, [rcx+18h]
0x1800224fb  jnb     short loc_18002252C
0x1800224fd  mov     rsi, [rdi]
0x180022500  test    rsi, rsi
0x180022503  jz      short loc_180022522
0x180022505  mov     rcx, [rsi+20h]
0x180022509  test    rcx, rcx
0x18002250c  jz      short loc_18002251A
0x18002250e  mov     rax, [rcx]
0x180022511  mov     rax, [rax+10h]
0x180022515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002251a  mov     qword ptr [rsi+20h], 0
0x180022522  add     rdi, 8
0x180022526  cmp     rdi, [rbx+18h]
0x18002252a  jb      short loc_1800224FD
0x18002252c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180022530  call    cs:__imp_DeleteCriticalSection
0x180022536  mov     dword ptr [rbx], 0
0x18002253c  mov     rbx, [rsp+28h+arg_0]
0x180022541  mov     rsi, [rsp+28h+arg_8]
0x180022546  add     rsp, 20h
0x18002254a  pop     rdi
0x18002254b  retn
```
