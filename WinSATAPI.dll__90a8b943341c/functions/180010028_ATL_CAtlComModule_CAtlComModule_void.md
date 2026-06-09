# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180010028`
- end: `0x180010099`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032880`

## callees

- `0x180010028`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010079`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010079`

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
0x180010028  mov     [rsp+arg_0], rbx
0x18001002d  mov     [rsp+arg_8], rsi
0x180010032  push    rdi
0x180010033  sub     rsp, 20h
0x180010037  cmp     dword ptr [rcx], 0
0x18001003a  mov     rbx, rcx
0x18001003d  jz      short loc_180010088
0x18001003f  mov     rdi, [rcx+10h]
0x180010043  cmp     rdi, [rcx+18h]
0x180010047  jnb     short loc_180010075
0x180010049  mov     rsi, [rdi]
0x18001004c  test    rsi, rsi
0x18001004f  jz      short loc_18001006B
0x180010051  mov     rcx, [rsi+20h]
0x180010055  test    rcx, rcx
0x180010058  jz      short loc_180010066
0x18001005a  mov     rax, [rcx]
0x18001005d  mov     rax, [rax+10h]
0x180010061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010066  and     qword ptr [rsi+20h], 0
0x18001006b  add     rdi, 8
0x18001006f  cmp     rdi, [rbx+18h]
0x180010073  jb      short loc_180010049
0x180010075  lea     rcx, [rbx+20h]; lpCriticalSection
0x180010079  call    cs:__imp_DeleteCriticalSection
0x180010080  nop     dword ptr [rax+rax+00h]
0x180010085  and     dword ptr [rbx], 0
0x180010088  mov     rbx, [rsp+28h+arg_0]
0x18001008d  mov     rsi, [rsp+28h+arg_8]
0x180010092  add     rsp, 20h
0x180010096  pop     rdi
0x180010097  retn
```
