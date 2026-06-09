# ATL::CAxHostWindow::GetOptionKeyPath(ushort * *,ulong)

- ea: `0x18000d890`
- end: `0x18000d953`
- name: `?GetOptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAPEAGK@Z`
- size: `195`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000d890`
- `0x1800118b4`
- `0x180035010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000d90b`
- `ole32!CoTaskMemAlloc` at `0x18000d90b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d8ee`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d8ee`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000d8ff`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000d8ff`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetOptionKeyPath(ATL::CAxHostWindow *this, unsigned __int16 **a2)
{
  __int64 v5; // rcx
  int v6; // ebx
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r14

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 136LL))(v5);
    if ( v6 < 0 || !*a2 )
      return 1;
  }
  else
  {
    v6 = 1;
    if ( SysStringLen(*((BSTR *)this + 29)) )
    {
      v7 = SysStringByteLen(*((BSTR *)this + 29));
      v8 = (unsigned __int16 *)CoTaskMemAlloc(v7 + 2);
      v9 = v8;
      if ( !v8 )
        return 2147942414LL;
      if ( !ocscpy_s(v8, (v7 >> 1) + 1, *((const unsigned __int16 **)this + 29)) )
        return 2147500037LL;
      *a2 = v9;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d890  push    rbx
0x18000d892  push    rbp
0x18000d893  push    rsi
0x18000d894  push    rdi
0x18000d895  push    r14
0x18000d897  sub     rsp, 20h
0x18000d89b  mov     rdi, rdx
0x18000d89e  mov     rsi, rcx
0x18000d8a1  test    rdx, rdx
0x18000d8a4  jnz     short loc_18000D8B0
0x18000d8a6  mov     eax, 80004003h
0x18000d8ab  jmp     loc_18000D948
0x18000d8b0  mov     qword ptr [rdx], 0
0x18000d8b7  mov     rcx, [rcx+68h]
0x18000d8bb  test    rcx, rcx
0x18000d8be  jz      short loc_18000D8E2
0x18000d8c0  mov     rax, [rcx]
0x18000d8c3  mov     rax, [rax+88h]
0x18000d8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cf  mov     ebx, eax
0x18000d8d1  test    eax, eax
0x18000d8d3  js      short loc_18000D8DB
0x18000d8d5  cmp     qword ptr [rdi], 0
0x18000d8d9  jnz     short loc_18000D946
0x18000d8db  mov     ebx, 1
0x18000d8e0  jmp     short loc_18000D946
0x18000d8e2  mov     rcx, [rsi+0E8h]; pbstr
0x18000d8e9  mov     ebx, 1
0x18000d8ee  call    cs:__imp_SysStringLen
0x18000d8f4  test    eax, eax
0x18000d8f6  jz      short loc_18000D946
0x18000d8f8  mov     rcx, [rsi+0E8h]; bstr
0x18000d8ff  call    cs:__imp_SysStringByteLen
0x18000d905  mov     ebp, eax
0x18000d907  lea     rcx, [rbp+2]; cb
0x18000d90b  call    cs:__imp_CoTaskMemAlloc
0x18000d911  mov     r14, rax
0x18000d914  test    rax, rax
0x18000d917  jnz     short loc_18000D920
0x18000d919  mov     eax, 8007000Eh
0x18000d91e  jmp     short loc_18000D948
0x18000d920  mov     r8, [rsi+0E8h]; unsigned __int16 *
0x18000d927  mov     rcx, r14; unsigned __int16 *
0x18000d92a  shr     rbp, 1
0x18000d92d  lea     rdx, [rbx+rbp]; unsigned __int64
0x18000d931  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000d936  test    al, al
0x18000d938  jnz     short loc_18000D941
0x18000d93a  mov     eax, 80004005h
0x18000d93f  jmp     short loc_18000D948
0x18000d941  mov     [rdi], r14
0x18000d944  xor     ebx, ebx
0x18000d946  mov     eax, ebx
0x18000d948  add     rsp, 20h
0x18000d94c  pop     r14
0x18000d94e  pop     rdi
0x18000d94f  pop     rsi
0x18000d950  pop     rbp
0x18000d951  pop     rbx
0x18000d952  retn
```
