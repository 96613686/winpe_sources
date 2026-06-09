# SSPI_SECURITY_CONTEXT::Reset(void)

- ea: `0x180005dc4`
- end: `0x180005e96`
- name: `?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ`
- size: `210`
- prototype: `void __fastcall(SSPI_SECURITY_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001ea0`
- `0x1800021f0`
- `0x180004070`

## callees

- `0x180001064`
- `0x180005dc4`
- `0x180009010`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x180005e35`
- `SspiCli!FreeCredentialsHandle` at `0x180005e35`
- `SspiCli!DeleteSecurityContext` at `0x180005df2`
- `SspiCli!DeleteSecurityContext` at `0x180005df2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005e4c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005e4c`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005e42`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005e42`

## pseudocode

```c
void __fastcall SSPI_SECURITY_CONTEXT::Reset(struct _SecHandle *this)
{
  struct _SecHandle *v2; // rdi
  volatile signed __int32 *dwLower; // rdi
  ULONG_PTR dwUpper; // rcx

  if ( LODWORD(this[1].dwUpper) )
  {
    v2 = this + 2;
    if ( this[2].dwLower != -1 && this[2].dwUpper != -1 )
      DeleteSecurityContext(this + 2);
    this[2].dwUpper = -1;
    v2->dwLower = -1;
    LODWORD(this[1].dwUpper) = 0;
  }
  dwLower = (volatile signed __int32 *)this[1].dwLower;
  if ( dwLower )
  {
    if ( !_InterlockedDecrement(dwLower + 1) )
    {
      *dwLower = 1396917094;
      if ( *((_QWORD *)dwLower + 25) != -1 && *((_QWORD *)dwLower + 26) != -1 )
        FreeCredentialsHandle((PCredHandle)(dwLower + 50));
      MULTISZ::~MULTISZ((MULTISZ *)(dwLower + 36));
      STRA::~STRA((STRA *)(dwLower + 2));
      operator delete((void *)dwLower);
    }
    this[1].dwLower = 0;
  }
  dwUpper = this[3].dwUpper;
  if ( dwUpper )
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)dwUpper + 56LL))(dwUpper);
  this[3].dwUpper = 0;
  HIDWORD(this[1].dwUpper) = 0;
}

```

## disassembly

```asm
0x180005dc4  mov     [rsp+arg_0], rbx
0x180005dc9  mov     [rsp+arg_8], rsi
0x180005dce  push    rdi
0x180005dcf  sub     rsp, 20h
0x180005dd3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005dd7  mov     rbx, rcx
0x180005dda  cmp     dword ptr [rcx+18h], 0
0x180005dde  jz      short loc_180005E06
0x180005de0  lea     rdi, [rcx+20h]
0x180005de4  cmp     [rdi], rsi
0x180005de7  jz      short loc_180005DF8
0x180005de9  cmp     [rcx+28h], rsi
0x180005ded  jz      short loc_180005DF8
0x180005def  mov     rcx, rdi; phContext
0x180005df2  call    cs:__imp_DeleteSecurityContext
0x180005df8  mov     [rbx+28h], rsi
0x180005dfc  mov     [rdi], rsi
0x180005dff  mov     dword ptr [rbx+18h], 0
0x180005e06  mov     rdi, [rbx+10h]
0x180005e0a  test    rdi, rdi
0x180005e0d  jz      short loc_180005E62
0x180005e0f  mov     eax, esi
0x180005e11  lock xadd [rdi+4], eax
0x180005e16  add     eax, esi
0x180005e18  jnz     short loc_180005E5A
0x180005e1a  lea     rcx, [rdi+0C8h]; phCredential
0x180005e21  mov     dword ptr [rdi], 53434366h
0x180005e27  cmp     [rcx], rsi
0x180005e2a  jz      short loc_180005E3B
0x180005e2c  cmp     [rdi+0D0h], rsi
0x180005e33  jz      short loc_180005E3B
0x180005e35  call    cs:__imp_FreeCredentialsHandle
0x180005e3b  lea     rcx, [rdi+90h]
0x180005e42  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005e48  lea     rcx, [rdi+8]
0x180005e4c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005e52  mov     rcx, rdi; Block
0x180005e55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e5a  mov     qword ptr [rbx+10h], 0
0x180005e62  mov     rcx, [rbx+38h]
0x180005e66  test    rcx, rcx
0x180005e69  jz      short loc_180005E77
0x180005e6b  mov     rax, [rcx]
0x180005e6e  mov     rax, [rax+38h]
0x180005e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e77  mov     rsi, [rsp+28h+arg_8]
0x180005e7c  mov     qword ptr [rbx+38h], 0
0x180005e84  mov     dword ptr [rbx+1Ch], 0
0x180005e8b  mov     rbx, [rsp+28h+arg_0]
0x180005e90  add     rsp, 20h
0x180005e94  pop     rdi
0x180005e95  retn
```
