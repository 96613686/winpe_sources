# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180020824`
- end: `0x180020928`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020e10`
- `0x180020ed0`
- `0x180020f10`

## callees

- `0x180020824`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x180020824  push    rbx
0x180020826  push    rbp
0x180020827  push    rsi
0x180020828  push    rdi
0x180020829  push    r14
0x18002082b  sub     rsp, 30h
0x18002082f  mov     rsi, r9
0x180020832  mov     rdi, r8
0x180020835  mov     rbx, rdx
0x180020838  mov     r14, rcx
0x18002083b  test    rcx, rcx
0x18002083e  jz      loc_180020918
0x180020844  test    rdx, rdx
0x180020847  jz      loc_180020918
0x18002084d  test    r9, r9
0x180020850  jnz     short loc_18002085C
0x180020852  mov     eax, 80004003h
0x180020857  jmp     loc_18002091D
0x18002085c  mov     qword ptr [r9], 0
0x180020863  cmp     dword ptr [r8], 0
0x180020867  jnz     short loc_1800208A1
0x180020869  cmp     dword ptr [r8+4], 0
0x18002086e  jnz     short loc_1800208A1
0x180020870  cmp     dword ptr [r8+8], 0C0h
0x180020878  jnz     short loc_1800208A1
0x18002087a  cmp     dword ptr [r8+0Ch], 46000000h
0x180020882  jnz     short loc_1800208A1
0x180020884  mov     rbx, [rdx+8]
0x180020888  add     rbx, r14
0x18002088b  mov     rcx, rbx
0x18002088e  mov     rax, [rbx]
0x180020891  mov     rax, [rax+8]
0x180020895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089a  xor     eax, eax
0x18002089c  mov     [rsi], rbx
0x18002089f  jmp     short loc_18002091D
0x1800208a1  cmp     qword ptr [rdx+10h], 0
0x1800208a6  jz      short loc_180020908
0x1800208a8  mov     rcx, [rbx]
0x1800208ab  test    rcx, rcx
0x1800208ae  jnz     short loc_1800208B5
0x1800208b0  lea     ebp, [rcx+1]
0x1800208b3  jmp     short loc_1800208D5
0x1800208b5  mov     eax, [rdi]
0x1800208b7  cmp     [rcx], eax
0x1800208b9  jnz     short loc_1800208FD
0x1800208bb  mov     eax, [rdi+4]
0x1800208be  cmp     [rcx+4], eax
0x1800208c1  jnz     short loc_1800208FD
0x1800208c3  mov     eax, [rdi+8]
0x1800208c6  cmp     [rcx+8], eax
0x1800208c9  jnz     short loc_1800208FD
0x1800208cb  mov     eax, [rdi+0Ch]
0x1800208ce  cmp     [rcx+0Ch], eax
0x1800208d1  jnz     short loc_1800208FD
0x1800208d3  xor     ebp, ebp
0x1800208d5  mov     rax, [rbx+10h]
0x1800208d9  cmp     rax, 1
0x1800208dd  jz      short loc_18002090F
0x1800208df  mov     r9, [rbx+8]
0x1800208e3  mov     r8, rsi
0x1800208e6  mov     rdx, rdi
0x1800208e9  mov     rcx, r14
0x1800208ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208f1  test    eax, eax
0x1800208f3  jz      short loc_18002091D
0x1800208f5  test    ebp, ebp
0x1800208f7  jnz     short loc_1800208FD
0x1800208f9  test    eax, eax
0x1800208fb  js      short loc_18002091D
0x1800208fd  add     rbx, 18h
0x180020901  cmp     qword ptr [rbx+10h], 0
0x180020906  jnz     short loc_1800208A8
0x180020908  mov     eax, 80004002h
0x18002090d  jmp     short loc_18002091D
0x18002090f  mov     rbx, [rbx+8]
0x180020913  jmp     loc_180020888
0x180020918  mov     eax, 80070057h
0x18002091d  add     rsp, 30h
0x180020921  pop     r14
0x180020923  pop     rdi
0x180020924  pop     rsi
0x180020925  pop     rbp
0x180020926  pop     rbx
0x180020927  retn
```
