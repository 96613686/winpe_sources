# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180008500`
- end: `0x180008604`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008ed0`
- `0x180008f60`
- `0x180008f80`

## callees

- `0x180008500`
- `0x180032010`

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
0x180008500  push    rbx
0x180008502  push    rbp
0x180008503  push    rsi
0x180008504  push    rdi
0x180008505  push    r14
0x180008507  sub     rsp, 30h
0x18000850b  mov     rsi, r9
0x18000850e  mov     rdi, r8
0x180008511  mov     rbx, rdx
0x180008514  mov     r14, rcx
0x180008517  test    rcx, rcx
0x18000851a  jz      loc_1800085F4
0x180008520  test    rdx, rdx
0x180008523  jz      loc_1800085F4
0x180008529  test    r9, r9
0x18000852c  jnz     short loc_180008538
0x18000852e  mov     eax, 80004003h
0x180008533  jmp     loc_1800085F9
0x180008538  mov     qword ptr [r9], 0
0x18000853f  cmp     dword ptr [r8], 0
0x180008543  jnz     short loc_18000857D
0x180008545  cmp     dword ptr [r8+4], 0
0x18000854a  jnz     short loc_18000857D
0x18000854c  cmp     dword ptr [r8+8], 0C0h
0x180008554  jnz     short loc_18000857D
0x180008556  cmp     dword ptr [r8+0Ch], 46000000h
0x18000855e  jnz     short loc_18000857D
0x180008560  mov     rbx, [rdx+8]
0x180008564  add     rbx, r14
0x180008567  mov     rcx, rbx
0x18000856a  mov     rax, [rbx]
0x18000856d  mov     rax, [rax+8]
0x180008571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008576  xor     eax, eax
0x180008578  mov     [rsi], rbx
0x18000857b  jmp     short loc_1800085F9
0x18000857d  cmp     qword ptr [rdx+10h], 0
0x180008582  jz      short loc_1800085E4
0x180008584  mov     rcx, [rbx]
0x180008587  test    rcx, rcx
0x18000858a  jnz     short loc_180008591
0x18000858c  lea     ebp, [rcx+1]
0x18000858f  jmp     short loc_1800085B1
0x180008591  mov     eax, [rdi]
0x180008593  cmp     [rcx], eax
0x180008595  jnz     short loc_1800085D9
0x180008597  mov     eax, [rdi+4]
0x18000859a  cmp     [rcx+4], eax
0x18000859d  jnz     short loc_1800085D9
0x18000859f  mov     eax, [rdi+8]
0x1800085a2  cmp     [rcx+8], eax
0x1800085a5  jnz     short loc_1800085D9
0x1800085a7  mov     eax, [rdi+0Ch]
0x1800085aa  cmp     [rcx+0Ch], eax
0x1800085ad  jnz     short loc_1800085D9
0x1800085af  xor     ebp, ebp
0x1800085b1  mov     rax, [rbx+10h]
0x1800085b5  cmp     rax, 1
0x1800085b9  jz      short loc_1800085EB
0x1800085bb  mov     r9, [rbx+8]
0x1800085bf  mov     r8, rsi
0x1800085c2  mov     rdx, rdi
0x1800085c5  mov     rcx, r14
0x1800085c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085cd  test    eax, eax
0x1800085cf  jz      short loc_1800085F9
0x1800085d1  test    ebp, ebp
0x1800085d3  jnz     short loc_1800085D9
0x1800085d5  test    eax, eax
0x1800085d7  js      short loc_1800085F9
0x1800085d9  add     rbx, 18h
0x1800085dd  cmp     qword ptr [rbx+10h], 0
0x1800085e2  jnz     short loc_180008584
0x1800085e4  mov     eax, 80004002h
0x1800085e9  jmp     short loc_1800085F9
0x1800085eb  mov     rbx, [rbx+8]
0x1800085ef  jmp     loc_180008564
0x1800085f4  mov     eax, 80070057h
0x1800085f9  add     rsp, 30h
0x1800085fd  pop     r14
0x1800085ff  pop     rdi
0x180008600  pop     rsi
0x180008601  pop     rbp
0x180008602  pop     rbx
0x180008603  retn
```
