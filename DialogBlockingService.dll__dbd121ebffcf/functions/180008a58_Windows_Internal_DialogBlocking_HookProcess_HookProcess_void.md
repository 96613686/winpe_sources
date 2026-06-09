# Windows::Internal::DialogBlocking::HookProcess::~HookProcess(void)

- ea: `0x180008a58`
- end: `0x180008ac9`
- name: `??1HookProcess@DialogBlocking@Internal@Windows@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(volatile signed __int32 **this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008658`
- `0x18000896c`
- `0x18000899c`

## callees

- `0x180008a58`
- `0x180009010`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ab8`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookProcess::~HookProcess(volatile signed __int32 **this)
{
  volatile signed __int32 *v2; // rbx
  volatile signed __int32 *v3; // rcx

  Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess((Windows::Internal::DialogBlocking::HookProcess *)this);
  v2 = this[4];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  v3 = this[2];
  if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v3);
}

```

## disassembly

```asm
0x180008a58  mov     [rsp+arg_0], rbx
0x180008a5d  push    rdi
0x180008a5e  sub     rsp, 20h
0x180008a62  mov     rdi, rcx
0x180008a65  call    ?ResetHookProcess@HookProcess@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookProcess::ResetHookProcess(void)
0x180008a6a  mov     rbx, [rdi+20h]
0x180008a6e  test    rbx, rbx
0x180008a71  jz      short loc_180008AAA
0x180008a73  or      eax, 0FFFFFFFFh
0x180008a76  lock xadd [rbx+8], eax
0x180008a7b  cmp     eax, 1
0x180008a7e  jnz     short loc_180008AAA
0x180008a80  mov     rax, [rbx]
0x180008a83  mov     rcx, rbx
0x180008a86  mov     rax, [rax]
0x180008a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8e  or      eax, 0FFFFFFFFh
0x180008a91  lock xadd [rbx+0Ch], eax
0x180008a96  cmp     eax, 1
0x180008a99  jnz     short loc_180008AAA
0x180008a9b  mov     rax, [rbx]
0x180008a9e  mov     rcx, rbx
0x180008aa1  mov     rax, [rax+8]
0x180008aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aaa  mov     rcx, [rdi+10h]; hObject
0x180008aae  lea     rax, [rcx-1]
0x180008ab2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008ab6  ja      short loc_180008ABE
0x180008ab8  call    cs:__imp_CloseHandle
0x180008abe  mov     rbx, [rsp+28h+arg_0]
0x180008ac3  add     rsp, 20h
0x180008ac7  pop     rdi
0x180008ac8  retn
```
