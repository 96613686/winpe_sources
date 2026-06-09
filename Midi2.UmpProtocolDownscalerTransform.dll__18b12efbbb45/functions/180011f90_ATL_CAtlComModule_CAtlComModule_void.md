# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180011f90`
- end: `0x180012000`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012c80`

## callees

- `0x180011f90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fe4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fe4`

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
0x180011f90  mov     [rsp+arg_0], rbx
0x180011f95  mov     [rsp+arg_8], rsi
0x180011f9a  push    rdi
0x180011f9b  sub     rsp, 20h
0x180011f9f  cmp     dword ptr [rcx], 0
0x180011fa2  mov     rbx, rcx
0x180011fa5  jz      short loc_180011FF0
0x180011fa7  mov     rdi, [rcx+10h]
0x180011fab  cmp     rdi, [rcx+18h]
0x180011faf  jnb     short loc_180011FE0
0x180011fb1  mov     rsi, [rdi]
0x180011fb4  test    rsi, rsi
0x180011fb7  jz      short loc_180011FD6
0x180011fb9  mov     rcx, [rsi+20h]
0x180011fbd  test    rcx, rcx
0x180011fc0  jz      short loc_180011FCE
0x180011fc2  mov     rax, [rcx]
0x180011fc5  mov     rax, [rax+10h]
0x180011fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fce  mov     qword ptr [rsi+20h], 0
0x180011fd6  add     rdi, 8
0x180011fda  cmp     rdi, [rbx+18h]
0x180011fde  jb      short loc_180011FB1
0x180011fe0  lea     rcx, [rbx+20h]; lpCriticalSection
0x180011fe4  call    cs:__imp_DeleteCriticalSection
0x180011fea  mov     dword ptr [rbx], 0
0x180011ff0  mov     rbx, [rsp+28h+arg_0]
0x180011ff5  mov     rsi, [rsp+28h+arg_8]
0x180011ffa  add     rsp, 20h
0x180011ffe  pop     rdi
0x180011fff  retn
```
