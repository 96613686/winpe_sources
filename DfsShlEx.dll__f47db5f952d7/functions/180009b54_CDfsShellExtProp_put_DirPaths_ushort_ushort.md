# CDfsShellExtProp::put_DirPaths(ushort *,ushort *)

- ea: `0x180009b54`
- end: `0x180009c10`
- name: `?put_DirPaths@CDfsShellExtProp@@QEAAJPEAG0@Z`
- size: `188`
- prototype: `int(CDfsShellExtProp *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007be0`

## callees

- `0x180004328`
- `0x180009b54`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009b8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bb9`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b84`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bab`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b84`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bab`

## pseudocode

```c
__int64 __fastcall CDfsShellExtProp::put_DirPaths(CDfsShellExtProp *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  OLECHAR *v7; // rcx
  BSTR v8; // rax
  unsigned __int16 *v9; // rcx
  BSTR v10; // rax

  if ( !a2 )
    return 2147942487LL;
  v7 = (OLECHAR *)*((_QWORD *)this + 24);
  if ( a2 != v7 )
  {
    SysFreeString(v7);
    v8 = SysAllocString(a2);
    *((_QWORD *)this + 24) = v8;
    if ( !v8 )
      goto LABEL_13;
  }
  v9 = (unsigned __int16 *)*((_QWORD *)this + 25);
  if ( a3 == v9 )
    goto LABEL_10;
  SysFreeString(v9);
  if ( !a3 )
  {
    *((_QWORD *)this + 25) = 0;
    goto LABEL_10;
  }
  v10 = SysAllocString(a3);
  *((_QWORD *)this + 25) = v10;
  if ( !v10 )
LABEL_13:
    ATL::AtlThrowImpl(-2147024882);
LABEL_10:
  if ( *((_QWORD *)this + 24) )
    return a3 == 0 ? 0x8007000E : 0;
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x180009b54  mov     [rsp+arg_0], rbx
0x180009b59  mov     [rsp+arg_8], rsi
0x180009b5e  push    rdi
0x180009b5f  sub     rsp, 20h
0x180009b63  mov     rdi, r8
0x180009b66  mov     rsi, rdx
0x180009b69  mov     rbx, rcx
0x180009b6c  test    rdx, rdx
0x180009b6f  jnz     short loc_180009B78
0x180009b71  mov     eax, 80070057h
0x180009b76  jmp     short loc_180009BF5
0x180009b78  mov     rcx, [rcx+0C0h]; bstrString
0x180009b7f  cmp     rsi, rcx
0x180009b82  jz      short loc_180009B9F
0x180009b84  call    cs:__imp_SysFreeString
0x180009b8a  mov     rcx, rsi; psz
0x180009b8d  call    cs:__imp_SysAllocString
0x180009b93  mov     [rbx+0C0h], rax
0x180009b9a  test    rax, rax
0x180009b9d  jz      short loc_180009C05
0x180009b9f  mov     rcx, [rbx+0C8h]; bstrString
0x180009ba6  cmp     rdi, rcx
0x180009ba9  jz      short loc_180009BD8
0x180009bab  call    cs:__imp_SysFreeString
0x180009bb1  test    rdi, rdi
0x180009bb4  jz      short loc_180009BCD
0x180009bb6  mov     rcx, rdi; psz
0x180009bb9  call    cs:__imp_SysAllocString
0x180009bbf  mov     [rbx+0C8h], rax
0x180009bc6  test    rax, rax
0x180009bc9  jz      short loc_180009C05
0x180009bcb  jmp     short loc_180009BD8
0x180009bcd  mov     qword ptr [rbx+0C8h], 0
0x180009bd8  cmp     qword ptr [rbx+0C0h], 0
0x180009be0  jz      short loc_180009BF0
0x180009be2  neg     rdi
0x180009be5  sbb     eax, eax
0x180009be7  not     eax
0x180009be9  and     eax, 8007000Eh
0x180009bee  jmp     short loc_180009BF5
0x180009bf0  mov     eax, 8007000Eh
0x180009bf5  mov     rbx, [rsp+28h+arg_0]
0x180009bfa  mov     rsi, [rsp+28h+arg_8]
0x180009bff  add     rsp, 20h
0x180009c03  pop     rdi
0x180009c04  retn
0x180009c05  mov     ecx, 8007000Eh; int
0x180009c0a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
