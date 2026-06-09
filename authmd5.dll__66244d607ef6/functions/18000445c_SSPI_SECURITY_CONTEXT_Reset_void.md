# SSPI_SECURITY_CONTEXT::Reset(void)

- ea: `0x18000445c`
- end: `0x18000452e`
- name: `?Reset@SSPI_SECURITY_CONTEXT@@QEAAXXZ`
- size: `210`
- prototype: `void __fastcall(SSPI_SECURITY_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001a38`
- `0x180001c70`
- `0x180001e00`

## callees

- `0x180001064`
- `0x18000445c`
- `0x180007010`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x18000448a`
- `SspiCli!DeleteSecurityContext` at `0x18000448a`
- `SspiCli!FreeCredentialsHandle` at `0x1800044cd`
- `SspiCli!FreeCredentialsHandle` at `0x1800044cd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800044e4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800044e4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800044da`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800044da`

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
0x18000445c  mov     [rsp+arg_0], rbx
0x180004461  mov     [rsp+arg_8], rsi
0x180004466  push    rdi
0x180004467  sub     rsp, 20h
0x18000446b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000446f  mov     rbx, rcx
0x180004472  cmp     dword ptr [rcx+18h], 0
0x180004476  jz      short loc_18000449E
0x180004478  lea     rdi, [rcx+20h]
0x18000447c  cmp     [rdi], rsi
0x18000447f  jz      short loc_180004490
0x180004481  cmp     [rcx+28h], rsi
0x180004485  jz      short loc_180004490
0x180004487  mov     rcx, rdi; phContext
0x18000448a  call    cs:__imp_DeleteSecurityContext
0x180004490  mov     [rbx+28h], rsi
0x180004494  mov     [rdi], rsi
0x180004497  mov     dword ptr [rbx+18h], 0
0x18000449e  mov     rdi, [rbx+10h]
0x1800044a2  test    rdi, rdi
0x1800044a5  jz      short loc_1800044FA
0x1800044a7  mov     eax, esi
0x1800044a9  lock xadd [rdi+4], eax
0x1800044ae  add     eax, esi
0x1800044b0  jnz     short loc_1800044F2
0x1800044b2  lea     rcx, [rdi+0C8h]; phCredential
0x1800044b9  mov     dword ptr [rdi], 53434366h
0x1800044bf  cmp     [rcx], rsi
0x1800044c2  jz      short loc_1800044D3
0x1800044c4  cmp     [rdi+0D0h], rsi
0x1800044cb  jz      short loc_1800044D3
0x1800044cd  call    cs:__imp_FreeCredentialsHandle
0x1800044d3  lea     rcx, [rdi+90h]
0x1800044da  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800044e0  lea     rcx, [rdi+8]
0x1800044e4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800044ea  mov     rcx, rdi; Block
0x1800044ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800044f2  mov     qword ptr [rbx+10h], 0
0x1800044fa  mov     rcx, [rbx+38h]
0x1800044fe  test    rcx, rcx
0x180004501  jz      short loc_18000450F
0x180004503  mov     rax, [rcx]
0x180004506  mov     rax, [rax+38h]
0x18000450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450f  mov     rsi, [rsp+28h+arg_8]
0x180004514  mov     qword ptr [rbx+38h], 0
0x18000451c  mov     dword ptr [rbx+1Ch], 0
0x180004523  mov     rbx, [rsp+28h+arg_0]
0x180004528  add     rsp, 20h
0x18000452c  pop     rdi
0x18000452d  retn
```
