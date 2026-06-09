# Base::Thread::Create(_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x180060bc0`
- end: `0x180060c2a`
- name: `?Create@Thread@Base@@QEAAXPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `106`
- prototype: `void __fastcall(Base::Thread *__hidden this, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180061010`
- `0x180061fa0`

## callees

- `0x1800378c0`
- `0x180060bc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180060c0e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180060c0e`
- `KERNEL32!CloseHandle` at `0x180060be9`
- `KERNEL32!CloseHandle` at `0x180060be9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180060bde`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180060bde`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180060c1d`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180060c1d`

## pseudocode

```c
void __fastcall Base::Thread::Create(HANDLE *this, struct _SECURITY_ATTRIBUTES *a2)
{
  int v3; // edx
  __int64 v4; // rax
  Base *v5; // rcx

  if ( this[1] )
  {
    if ( Base::Thread::IsActive((Base::Thread *)this) )
    {
      Base::Throw((Base *)0x80070006LL, v3);
      __debugbreak();
    }
    CloseHandle(this[1]);
  }
  v4 = _o__beginthreadex(0, 0, BasePrivate::ThreadProcHook, this, 0, this + 2);
  this[1] = (HANDLE)v4;
  if ( !v4 )
  {
    Base::ThrowLastError(v5);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180060bc0  push    rbx
0x180060bc2  sub     rsp, 30h
0x180060bc6  cmp     qword ptr [rcx+8], 0
0x180060bcb  mov     rbx, rcx
0x180060bce  jz      short loc_180060BEF
0x180060bd0  call    ?IsActive@Thread@Base@@QEBA_NXZ; Base::Thread::IsActive(void)
0x180060bd5  test    al, al
0x180060bd7  jz      short loc_180060BE5
0x180060bd9  mov     ecx, 80070006h
0x180060bde  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180060be4  int     3; Trap to Debugger
0x180060be5  mov     rcx, [rbx+8]; hObject
0x180060be9  call    cs:__imp_CloseHandle
0x180060bef  lea     rax, [rbx+10h]
0x180060bf3  mov     r9, rbx
0x180060bf6  mov     [rsp+38h+var_10], rax
0x180060bfb  lea     r8, ?ThreadProcHook@BasePrivate@@YAIPEAX@Z; BasePrivate::ThreadProcHook(void *)
0x180060c02  xor     edx, edx
0x180060c04  mov     [rsp+38h+var_18], 0
0x180060c0c  xor     ecx, ecx
0x180060c0e  call    cs:__imp__o__beginthreadex
0x180060c14  mov     [rbx+8], rax
0x180060c18  test    rax, rax
0x180060c1b  jnz     short loc_180060C24
0x180060c1d  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180060c23  int     3; Trap to Debugger
0x180060c24  add     rsp, 30h
0x180060c28  pop     rbx
0x180060c29  retn
```
