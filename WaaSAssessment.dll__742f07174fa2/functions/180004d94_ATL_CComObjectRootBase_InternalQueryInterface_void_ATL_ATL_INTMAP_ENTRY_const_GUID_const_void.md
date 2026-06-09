# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004d94`
- end: `0x180004e98`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005380`
- `0x1800053a0`

## callees

- `0x180004d94`
- `0x18001b010`

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
0x180004d94  push    rbx
0x180004d96  push    rbp
0x180004d97  push    rsi
0x180004d98  push    rdi
0x180004d99  push    r14
0x180004d9b  sub     rsp, 30h
0x180004d9f  mov     rsi, r9
0x180004da2  mov     rdi, r8
0x180004da5  mov     rbx, rdx
0x180004da8  mov     r14, rcx
0x180004dab  test    rcx, rcx
0x180004dae  jz      loc_180004E88
0x180004db4  test    rdx, rdx
0x180004db7  jz      loc_180004E88
0x180004dbd  test    r9, r9
0x180004dc0  jnz     short loc_180004DCC
0x180004dc2  mov     eax, 80004003h
0x180004dc7  jmp     loc_180004E8D
0x180004dcc  mov     qword ptr [r9], 0
0x180004dd3  cmp     dword ptr [r8], 0
0x180004dd7  jnz     short loc_180004E11
0x180004dd9  cmp     dword ptr [r8+4], 0
0x180004dde  jnz     short loc_180004E11
0x180004de0  cmp     dword ptr [r8+8], 0C0h
0x180004de8  jnz     short loc_180004E11
0x180004dea  cmp     dword ptr [r8+0Ch], 46000000h
0x180004df2  jnz     short loc_180004E11
0x180004df4  mov     rbx, [rdx+8]
0x180004df8  add     rbx, r14
0x180004dfb  mov     rcx, rbx
0x180004dfe  mov     rax, [rbx]
0x180004e01  mov     rax, [rax+8]
0x180004e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e0a  xor     eax, eax
0x180004e0c  mov     [rsi], rbx
0x180004e0f  jmp     short loc_180004E8D
0x180004e11  cmp     qword ptr [rdx+10h], 0
0x180004e16  jz      short loc_180004E78
0x180004e18  mov     rcx, [rbx]
0x180004e1b  test    rcx, rcx
0x180004e1e  jnz     short loc_180004E25
0x180004e20  lea     ebp, [rcx+1]
0x180004e23  jmp     short loc_180004E45
0x180004e25  mov     eax, [rdi]
0x180004e27  cmp     [rcx], eax
0x180004e29  jnz     short loc_180004E6D
0x180004e2b  mov     eax, [rdi+4]
0x180004e2e  cmp     [rcx+4], eax
0x180004e31  jnz     short loc_180004E6D
0x180004e33  mov     eax, [rdi+8]
0x180004e36  cmp     [rcx+8], eax
0x180004e39  jnz     short loc_180004E6D
0x180004e3b  mov     eax, [rdi+0Ch]
0x180004e3e  cmp     [rcx+0Ch], eax
0x180004e41  jnz     short loc_180004E6D
0x180004e43  xor     ebp, ebp
0x180004e45  mov     rax, [rbx+10h]
0x180004e49  cmp     rax, 1
0x180004e4d  jz      short loc_180004E7F
0x180004e4f  mov     r9, [rbx+8]
0x180004e53  mov     r8, rsi
0x180004e56  mov     rdx, rdi
0x180004e59  mov     rcx, r14
0x180004e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e61  test    eax, eax
0x180004e63  jz      short loc_180004E8D
0x180004e65  test    ebp, ebp
0x180004e67  jnz     short loc_180004E6D
0x180004e69  test    eax, eax
0x180004e6b  js      short loc_180004E8D
0x180004e6d  add     rbx, 18h
0x180004e71  cmp     qword ptr [rbx+10h], 0
0x180004e76  jnz     short loc_180004E18
0x180004e78  mov     eax, 80004002h
0x180004e7d  jmp     short loc_180004E8D
0x180004e7f  mov     rbx, [rbx+8]
0x180004e83  jmp     loc_180004DF8
0x180004e88  mov     eax, 80070057h
0x180004e8d  add     rsp, 30h
0x180004e91  pop     r14
0x180004e93  pop     rdi
0x180004e94  pop     rsi
0x180004e95  pop     rbp
0x180004e96  pop     rbx
0x180004e97  retn
```
