# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180005b60`
- end: `0x180005bd0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009c70`

## callees

- `0x180005b60`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005bb4`
- `KERNEL32!DeleteCriticalSection` at `0x180005bb4`

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
0x180005b60  mov     [rsp+arg_0], rbx
0x180005b65  mov     [rsp+arg_8], rsi
0x180005b6a  push    rdi
0x180005b6b  sub     rsp, 20h
0x180005b6f  cmp     dword ptr [rcx], 0
0x180005b72  mov     rbx, rcx
0x180005b75  jz      short loc_180005BC0
0x180005b77  mov     rdi, [rcx+10h]
0x180005b7b  cmp     rdi, [rcx+18h]
0x180005b7f  jnb     short loc_180005BB0
0x180005b81  mov     rsi, [rdi]
0x180005b84  test    rsi, rsi
0x180005b87  jz      short loc_180005BA6
0x180005b89  mov     rcx, [rsi+20h]
0x180005b8d  test    rcx, rcx
0x180005b90  jz      short loc_180005B9E
0x180005b92  mov     rax, [rcx]
0x180005b95  mov     rax, [rax+10h]
0x180005b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b9e  mov     qword ptr [rsi+20h], 0
0x180005ba6  add     rdi, 8
0x180005baa  cmp     rdi, [rbx+18h]
0x180005bae  jb      short loc_180005B81
0x180005bb0  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005bb4  call    cs:__imp_DeleteCriticalSection
0x180005bba  mov     dword ptr [rbx], 0
0x180005bc0  mov     rbx, [rsp+28h+arg_0]
0x180005bc5  mov     rsi, [rsp+28h+arg_8]
0x180005bca  add     rsp, 20h
0x180005bce  pop     rdi
0x180005bcf  retn
```
