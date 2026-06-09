# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180010cb0`
- end: `0x180010d23`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007410`
- `0x180011800`

## callees

- `0x180010c70`
- `0x180010cb0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010cc7`
- `KERNEL32!GetCurrentThreadId` at `0x180010cc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    v6 = *v5;
    if ( *v5 )
    {
      while ( v6 != this )
      {
        v5 = (wil::details::ThreadFailureCallbackHolder **)((char *)v6 + 16);
        *(_QWORD *)this = (char *)v6 + 16;
        v6 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v6 + 2);
        if ( !v6 )
        {
          *(_QWORD *)this = 0;
          return;
        }
      }
      *v5 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180010cb0  push    rdi; int
0x180010cb2  sub     rsp, 20h
0x180010cb6  cmp     dword ptr [rcx+18h], 0
0x180010cba  mov     rdi, rcx
0x180010cbd  jz      short loc_180010D1D
0x180010cbf  mov     [rsp+28h+arg_0], rbx
0x180010cc4  mov     ebx, [rcx+18h]
0x180010cc7  call    cs:__imp_GetCurrentThreadId
0x180010ccd  cmp     ebx, eax
0x180010ccf  mov     rbx, [rsp+28h+arg_0]
0x180010cd4  jz      short loc_180010CE6
0x180010cd6  mov     rcx, [rsp+28h]; this
0x180010cdb  mov     r9d, 8007029Ch; char *
0x180010ce1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010ce6  mov     rcx, [rdi]
0x180010ce9  xor     edx, edx
0x180010ceb  mov     [rdi+18h], edx
0x180010cee  mov     rax, [rcx]
0x180010cf1  test    rax, rax
0x180010cf4  jz      short loc_180010D1A
0x180010cf6  cmp     rax, rdi
0x180010cf9  jz      short loc_180010D13
0x180010cfb  lea     rcx, [rax+10h]
0x180010cff  mov     [rdi], rcx
0x180010d02  mov     rax, [rcx]
0x180010d05  test    rax, rax
0x180010d08  jnz     short loc_180010CF6
0x180010d0a  mov     [rdi], rdx
0x180010d0d  add     rsp, 20h
0x180010d11  pop     rdi
0x180010d12  retn
0x180010d13  mov     rax, [rdi+10h]
0x180010d17  mov     [rcx], rax
0x180010d1a  mov     [rdi], rdx
0x180010d1d  add     rsp, 20h
0x180010d21  pop     rdi
0x180010d22  retn
```
