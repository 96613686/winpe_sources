# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180035f0c`
- end: `0x180035f77`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `107`
- prototype: `void(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b41c`
- `0x18003e1a8`

## callees

- `0x180035ec8`
- `0x180035f0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035f22`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  void *v3; // rdx
  unsigned int v4; // r8d
  wil::details::ThreadFailureCallbackHolder **v5; // rcx
  wil::details::ThreadFailureCallbackHolder *v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v3, v4, (const char *)0x8007029CLL, v7);
    v5 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
    while ( 1 )
    {
      v6 = *v5;
      if ( !*v5 )
        break;
      if ( v6 == this )
      {
        *v5 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v5 = (wil::details::ThreadFailureCallbackHolder **)((char *)v6 + 16);
      *(_QWORD *)this = (char *)v6 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180035f0c  mov     [rsp+arg_0], rbx
0x180035f11  push    rdi; int
0x180035f12  sub     rsp, 20h
0x180035f16  cmp     dword ptr [rcx+18h], 0
0x180035f1a  mov     rdi, rcx
0x180035f1d  jz      short loc_180035F6C
0x180035f1f  mov     ebx, [rcx+18h]
0x180035f22  call    cs:__imp_GetCurrentThreadId
0x180035f28  cmp     ebx, eax
0x180035f2a  jz      short loc_180035F3C
0x180035f2c  mov     rcx, [rsp+28h]; this
0x180035f31  mov     r9d, 8007029Ch; char *
0x180035f37  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180035f3c  mov     rcx, [rdi]
0x180035f3f  mov     dword ptr [rdi+18h], 0
0x180035f46  jmp     short loc_180035F54
0x180035f48  cmp     rax, rdi
0x180035f4b  jz      short loc_180035F5E
0x180035f4d  lea     rcx, [rax+10h]
0x180035f51  mov     [rdi], rcx
0x180035f54  mov     rax, [rcx]
0x180035f57  test    rax, rax
0x180035f5a  jnz     short loc_180035F48
0x180035f5c  jmp     short loc_180035F65
0x180035f5e  mov     rax, [rdi+10h]
0x180035f62  mov     [rcx], rax
0x180035f65  mov     qword ptr [rdi], 0
0x180035f6c  mov     rbx, [rsp+28h+arg_0]
0x180035f71  add     rsp, 20h
0x180035f75  pop     rdi
0x180035f76  retn
```
