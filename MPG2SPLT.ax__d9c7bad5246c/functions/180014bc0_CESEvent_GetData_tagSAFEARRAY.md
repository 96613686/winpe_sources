# CESEvent::GetData(tagSAFEARRAY * *)

- ea: `0x180014bc0`
- end: `0x180014c9e`
- name: `?GetData@CESEvent@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CESEvent *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180014bc0`
- `0x180033dfd`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014c13`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180014c13`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014c74`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014c74`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180014c39`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180014c39`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180014c62`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180014c62`

## pseudocode

```c
__int64 __fastcall CESEvent::GetData(CESEvent *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v5; // rax
  HRESULT v6; // edi
  void *ppvData; // [rsp+38h] [rbp+10h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( *((_QWORD *)this + 4) && *((_DWORD *)this + 10) )
  {
    rgsabound.cElements = *((_DWORD *)this + 10);
    rgsabound.lLbound = 0;
    v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
    *a2 = v5;
    ppvData = 0;
    if ( v5 )
    {
      v6 = SafeArrayAccessData(v5, &ppvData);
      if ( v6 >= 0 )
        memcpy_0(ppvData, *((const void **)this + 4), *((unsigned int *)this + 10));
      if ( ppvData )
        SafeArrayUnaccessData(*a2);
      if ( v6 >= 0 )
        return (unsigned int)v6;
    }
    else
    {
      v6 = -2147024882;
    }
    if ( *a2 )
    {
      SafeArrayDestroy(*a2);
      *a2 = 0;
    }
    return (unsigned int)v6;
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180014bc0  mov     [rsp+arg_0], rbx
0x180014bc5  mov     [rsp+arg_18], rsi
0x180014bca  push    rdi
0x180014bcb  sub     rsp, 20h
0x180014bcf  mov     rbx, rdx
0x180014bd2  mov     rsi, rcx
0x180014bd5  test    rdx, rdx
0x180014bd8  jnz     short loc_180014BE4
0x180014bda  mov     eax, 80004003h
0x180014bdf  jmp     loc_180014C8E
0x180014be4  cmp     qword ptr [rcx+20h], 0
0x180014be9  jz      loc_180014C85
0x180014bef  mov     eax, [rcx+28h]
0x180014bf2  test    eax, eax
0x180014bf4  jz      loc_180014C85
0x180014bfa  mov     ecx, 11h; vt
0x180014bff  mov     [rsp+28h+rgsabound.cElements], eax
0x180014c03  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180014c08  mov     [rsp+28h+rgsabound.lLbound], 0
0x180014c10  lea     edx, [rcx-10h]; cDims
0x180014c13  call    cs:__imp_SafeArrayCreate
0x180014c19  mov     [rbx], rax
0x180014c1c  mov     [rsp+28h+ppvData], 0
0x180014c25  test    rax, rax
0x180014c28  jnz     short loc_180014C31
0x180014c2a  mov     edi, 8007000Eh
0x180014c2f  jmp     short loc_180014C6C
0x180014c31  lea     rdx, [rsp+28h+ppvData]; ppvData
0x180014c36  mov     rcx, rax; psa
0x180014c39  call    cs:__imp_SafeArrayAccessData
0x180014c3f  mov     edi, eax
0x180014c41  test    eax, eax
0x180014c43  js      short loc_180014C57
0x180014c45  mov     r8d, [rsi+28h]; Size
0x180014c49  mov     rdx, [rsi+20h]; Src
0x180014c4d  mov     rcx, [rsp+28h+ppvData]; void *
0x180014c52  call    memcpy_0
0x180014c57  cmp     [rsp+28h+ppvData], 0
0x180014c5d  jz      short loc_180014C68
0x180014c5f  mov     rcx, [rbx]; psa
0x180014c62  call    cs:__imp_SafeArrayUnaccessData
0x180014c68  test    edi, edi
0x180014c6a  jns     short loc_180014C81
0x180014c6c  mov     rcx, [rbx]; psa
0x180014c6f  test    rcx, rcx
0x180014c72  jz      short loc_180014C81
0x180014c74  call    cs:__imp_SafeArrayDestroy
0x180014c7a  mov     qword ptr [rbx], 0
0x180014c81  mov     eax, edi
0x180014c83  jmp     short loc_180014C8E
0x180014c85  mov     qword ptr [rdx], 0
0x180014c8c  xor     eax, eax
0x180014c8e  mov     rbx, [rsp+28h+arg_0]
0x180014c93  mov     rsi, [rsp+28h+arg_18]
0x180014c98  add     rsp, 20h
0x180014c9c  pop     rdi
0x180014c9d  retn
```
