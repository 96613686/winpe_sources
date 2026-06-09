# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180013878`
- end: `0x1800138e8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014ce0`

## callees

- `0x180013878`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800138cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800138cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013878  mov     [rsp+arg_0], rbx
0x18001387d  mov     [rsp+arg_8], rsi
0x180013882  push    rdi
0x180013883  sub     rsp, 20h
0x180013887  cmp     dword ptr [rcx], 0
0x18001388a  mov     rbx, rcx
0x18001388d  jz      short loc_1800138D8
0x18001388f  mov     rdi, [rcx+10h]
0x180013893  cmp     rdi, [rcx+18h]
0x180013897  jnb     short loc_1800138C8
0x180013899  mov     rsi, [rdi]
0x18001389c  test    rsi, rsi
0x18001389f  jz      short loc_1800138BE
0x1800138a1  mov     rcx, [rsi+20h]
0x1800138a5  test    rcx, rcx
0x1800138a8  jz      short loc_1800138B6
0x1800138aa  mov     rax, [rcx]
0x1800138ad  mov     rax, [rax+10h]
0x1800138b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b6  mov     qword ptr [rsi+20h], 0
0x1800138be  add     rdi, 8
0x1800138c2  cmp     rdi, [rbx+18h]
0x1800138c6  jb      short loc_180013899
0x1800138c8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800138cc  call    cs:__imp_DeleteCriticalSection
0x1800138d2  mov     dword ptr [rbx], 0
0x1800138d8  mov     rbx, [rsp+28h+arg_0]
0x1800138dd  mov     rsi, [rsp+28h+arg_8]
0x1800138e2  add     rsp, 20h
0x1800138e6  pop     rdi
0x1800138e7  retn
```
