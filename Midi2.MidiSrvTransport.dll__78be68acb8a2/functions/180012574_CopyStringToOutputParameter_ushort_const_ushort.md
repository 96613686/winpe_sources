# CopyStringToOutputParameter(ushort const *,ushort * *)

- ea: `0x180012574`
- end: `0x180012607`
- name: `?CopyStringToOutputParameter@@YAJPEBGPEAPEAG@Z`
- size: `147`
- prototype: `__int64 __fastcall(const unsigned __int16 *Block, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800126e4`
- `0x180012964`
- `0x180013bf4`

## callees

- `0x180002494`
- `0x180007e24`
- `0x180012574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800125e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800125e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125c6`

## pseudocode

```c
__int64 __fastcall CopyStringToOutputParameter(unsigned __int16 *Block, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rax
  __int64 v8; // rsi
  unsigned __int16 *v9; // rax
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 404;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)v4,
      v10);
    return v4;
  }
  if ( Block )
  {
    v7 = -1;
    do
      ++v7;
    while ( Block[v7] );
    v8 = v7 + 1;
    v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v7 + 1));
    *a2 = v9;
    if ( !v9 )
    {
      v4 = -2147024882;
      v5 = 414;
      goto LABEL_3;
    }
    _o_wcscpy_s(v9, v8, Block);
    operator delete(Block);
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180012574  push    rbx
0x180012576  push    rbp
0x180012577  push    rsi
0x180012578  push    rdi
0x180012579  sub     rsp, 28h
0x18001257d  xor     ebp, ebp
0x18001257f  mov     rdi, rdx
0x180012582  mov     rbx, rcx
0x180012585  test    rdx, rdx
0x180012588  jnz     short loc_1800125AC
0x18001258a  mov     ebx, 80070057h
0x18001258f  mov     edx, 194h; void *
0x180012594  mov     rcx, [rsp+48h]; this
0x180012599  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x1800125a0  mov     r9d, ebx; char *
0x1800125a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125a8  mov     eax, ebx
0x1800125aa  jmp     short loc_1800125FE
0x1800125ac  test    rbx, rbx
0x1800125af  jz      short loc_1800125F9
0x1800125b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800125b5  inc     rax
0x1800125b8  cmp     [rcx+rax*2], bp
0x1800125bc  jnz     short loc_1800125B5
0x1800125be  lea     rsi, [rax+1]
0x1800125c2  lea     rcx, [rsi+rsi]; cb
0x1800125c6  call    cs:__imp_CoTaskMemAlloc
0x1800125cc  mov     [rdi], rax
0x1800125cf  test    rax, rax
0x1800125d2  jnz     short loc_1800125E0
0x1800125d4  mov     ebx, 8007000Eh
0x1800125d9  mov     edx, 19Eh
0x1800125de  jmp     short loc_180012594
0x1800125e0  mov     r8, rbx
0x1800125e3  mov     rdx, rsi
0x1800125e6  mov     rcx, rax
0x1800125e9  call    cs:__imp__o_wcscpy_s
0x1800125ef  mov     rcx, rbx; Block
0x1800125f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800125f7  jmp     short loc_1800125FC
0x1800125f9  mov     [rdx], rbp
0x1800125fc  xor     eax, eax
0x1800125fe  add     rsp, 28h
0x180012602  pop     rdi
0x180012603  pop     rsi
0x180012604  pop     rbp
0x180012605  pop     rbx
0x180012606  retn
```
