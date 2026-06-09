# KERNEL_USER_CONTEXT::~KERNEL_USER_CONTEXT(void)

- ea: `0x180001ca8`
- end: `0x180001d95`
- name: `??1KERNEL_USER_CONTEXT@@AEAA@XZ`
- size: `237`
- prototype: `void __fastcall(KERNEL_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002020`

## callees

- `0x180001064`
- `0x180001ca8`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180001d44`
- `SspiCli!FreeCredentialsHandle` at `0x180001d44`
- `SspiCli!DeleteSecurityContext` at `0x180001d08`
- `SspiCli!DeleteSecurityContext` at `0x180001d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ce4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ce4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d8e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d5b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d75`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d5b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d75`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180001d51`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180001d51`

## pseudocode

```c
void __fastcall KERNEL_USER_CONTEXT::~KERNEL_USER_CONTEXT(KERNEL_USER_CONTEXT *this)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _SecHandle *v4; // rdi
  volatile signed __int32 *v5; // rdi

  *(_QWORD *)this = &KERNEL_USER_CONTEXT::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (struct _SecHandle *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) != -1 && *((_QWORD *)this + 13) != -1 )
    DeleteSecurityContext(v4);
  v4->dwLower = -1;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 13) = -1;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 1, 0xFFFFFFFF) == 1 )
    {
      *v5 = 1396917094;
      if ( *((_QWORD *)v5 + 25) != -1 && *((_QWORD *)v5 + 26) != -1 )
        FreeCredentialsHandle((PCredHandle)(v5 + 50));
      MULTISZ::~MULTISZ((MULTISZ *)(v5 + 36));
      STRA::~STRA((STRA *)(v5 + 2));
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 14) = 0;
  }
  STRA::~STRA((KERNEL_USER_CONTEXT *)((char *)this + 120));
  STRU::~STRU((KERNEL_USER_CONTEXT *)((char *)this + 40));
}

```

## disassembly

```asm
0x180001ca8  mov     [rsp+arg_0], rbx
0x180001cad  mov     [rsp+arg_8], rsi
0x180001cb2  push    rdi
0x180001cb3  sub     rsp, 20h
0x180001cb7  lea     rax, ??_7KERNEL_USER_CONTEXT@@6B@; const KERNEL_USER_CONTEXT::`vftable'
0x180001cbe  mov     rbx, rcx
0x180001cc1  mov     [rcx], rax
0x180001cc4  mov     rcx, [rcx+18h]; hObject
0x180001cc8  test    rcx, rcx
0x180001ccb  jz      short loc_180001CDB
0x180001ccd  call    cs:__imp_CloseHandle
0x180001cd3  mov     qword ptr [rbx+18h], 0
0x180001cdb  mov     rcx, [rbx+20h]; hObject
0x180001cdf  test    rcx, rcx
0x180001ce2  jz      short loc_180001CF2
0x180001ce4  call    cs:__imp_CloseHandle
0x180001cea  mov     qword ptr [rbx+20h], 0
0x180001cf2  lea     rdi, [rbx+60h]
0x180001cf6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180001cfa  cmp     [rdi], rsi
0x180001cfd  jz      short loc_180001D0E
0x180001cff  cmp     [rbx+68h], rsi
0x180001d03  jz      short loc_180001D0E
0x180001d05  mov     rcx, rdi; phContext
0x180001d08  call    cs:__imp_DeleteSecurityContext
0x180001d0e  mov     [rdi], rsi
0x180001d11  mov     rdi, [rbx+70h]
0x180001d15  mov     [rbx+68h], rsi
0x180001d19  test    rdi, rdi
0x180001d1c  jz      short loc_180001D71
0x180001d1e  mov     eax, esi
0x180001d20  lock xadd [rdi+4], eax
0x180001d25  add     eax, esi
0x180001d27  jnz     short loc_180001D69
0x180001d29  lea     rcx, [rdi+0C8h]; phCredential
0x180001d30  mov     dword ptr [rdi], 53434366h
0x180001d36  cmp     [rcx], rsi
0x180001d39  jz      short loc_180001D4A
0x180001d3b  cmp     [rdi+0D0h], rsi
0x180001d42  jz      short loc_180001D4A
0x180001d44  call    cs:__imp_FreeCredentialsHandle
0x180001d4a  lea     rcx, [rdi+90h]
0x180001d51  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180001d57  lea     rcx, [rdi+8]
0x180001d5b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001d61  mov     rcx, rdi; Block
0x180001d64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d69  mov     qword ptr [rbx+70h], 0
0x180001d71  lea     rcx, [rbx+78h]
0x180001d75  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001d7b  lea     rcx, [rbx+28h]
0x180001d7f  mov     rbx, [rsp+28h+arg_0]
0x180001d84  mov     rsi, [rsp+28h+arg_8]
0x180001d89  add     rsp, 20h
0x180001d8d  pop     rdi
0x180001d8e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
