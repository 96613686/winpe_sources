# CAxInstaller::VerifyFile(ushort *,ushort * *)

- ea: `0x180006dd0`
- end: `0x180006e2a`
- name: `?VerifyFile@CAxInstaller@@UEAAJPEAGPEAPEAG@Z`
- size: `90`
- prototype: `int __fastcall(CAxInstaller *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006dd0`
- `0x180011ee0`
- `0x180015010`

## pseudocode

```c
int __fastcall CAxInstaller::VerifyFile(CAxInstaller *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  char *v3; // rbx
  CAxisUrlCache *v5; // rcx
  int result; // eax

  v3 = (char *)this - 8;
  v5 = (CAxisUrlCache *)*((_QWORD *)this + 86);
  if ( !v5 )
    return -2147467259;
  result = CAxisUrlCache::GetFileForUrl(v5, a2, a3);
  if ( result < 0 )
    return (*(__int64 (__fastcall **)(char *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v3 + 64LL))(
             v3,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180006dd0  mov     [rsp+arg_0], rbx
0x180006dd5  mov     [rsp+arg_8], rsi
0x180006dda  push    rdi
0x180006ddb  sub     rsp, 20h
0x180006ddf  lea     rbx, [rcx-8]
0x180006de3  mov     rdi, r8
0x180006de6  mov     rcx, [rbx+2B8h]; this
0x180006ded  mov     rsi, rdx
0x180006df0  test    rcx, rcx
0x180006df3  jz      short loc_180006E15
0x180006df5  call    ?GetFileForUrl@CAxisUrlCache@@QEAAJPEAGPEAPEAG@Z; CAxisUrlCache::GetFileForUrl(ushort *,ushort * *)
0x180006dfa  test    eax, eax
0x180006dfc  jns     short loc_180006E1A
0x180006dfe  mov     rax, [rbx]
0x180006e01  mov     r8, rdi
0x180006e04  mov     rdx, rsi
0x180006e07  mov     rcx, rbx
0x180006e0a  mov     rax, [rax+40h]
0x180006e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e13  jmp     short loc_180006E1A
0x180006e15  mov     eax, 80004005h
0x180006e1a  mov     rbx, [rsp+28h+arg_0]
0x180006e1f  mov     rsi, [rsp+28h+arg_8]
0x180006e24  add     rsp, 20h
0x180006e28  pop     rdi
0x180006e29  retn
```
