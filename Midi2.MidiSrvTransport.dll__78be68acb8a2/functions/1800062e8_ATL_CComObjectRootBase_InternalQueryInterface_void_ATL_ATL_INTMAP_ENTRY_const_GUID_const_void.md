# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800062e8`
- end: `0x1800063ec`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006cc0`
- `0x180006d50`
- `0x180006d70`

## callees

- `0x1800062e8`
- `0x180015010`

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
0x1800062e8  push    rbx
0x1800062ea  push    rbp
0x1800062eb  push    rsi
0x1800062ec  push    rdi
0x1800062ed  push    r14
0x1800062ef  sub     rsp, 30h
0x1800062f3  mov     rsi, r9
0x1800062f6  mov     rdi, r8
0x1800062f9  mov     rbx, rdx
0x1800062fc  mov     r14, rcx
0x1800062ff  test    rcx, rcx
0x180006302  jz      loc_1800063DC
0x180006308  test    rdx, rdx
0x18000630b  jz      loc_1800063DC
0x180006311  test    r9, r9
0x180006314  jnz     short loc_180006320
0x180006316  mov     eax, 80004003h
0x18000631b  jmp     loc_1800063E1
0x180006320  mov     qword ptr [r9], 0
0x180006327  cmp     dword ptr [r8], 0
0x18000632b  jnz     short loc_180006365
0x18000632d  cmp     dword ptr [r8+4], 0
0x180006332  jnz     short loc_180006365
0x180006334  cmp     dword ptr [r8+8], 0C0h
0x18000633c  jnz     short loc_180006365
0x18000633e  cmp     dword ptr [r8+0Ch], 46000000h
0x180006346  jnz     short loc_180006365
0x180006348  mov     rbx, [rdx+8]
0x18000634c  add     rbx, r14
0x18000634f  mov     rcx, rbx
0x180006352  mov     rax, [rbx]
0x180006355  mov     rax, [rax+8]
0x180006359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635e  xor     eax, eax
0x180006360  mov     [rsi], rbx
0x180006363  jmp     short loc_1800063E1
0x180006365  cmp     qword ptr [rdx+10h], 0
0x18000636a  jz      short loc_1800063CC
0x18000636c  mov     rcx, [rbx]
0x18000636f  test    rcx, rcx
0x180006372  jnz     short loc_180006379
0x180006374  lea     ebp, [rcx+1]
0x180006377  jmp     short loc_180006399
0x180006379  mov     eax, [rdi]
0x18000637b  cmp     [rcx], eax
0x18000637d  jnz     short loc_1800063C1
0x18000637f  mov     eax, [rdi+4]
0x180006382  cmp     [rcx+4], eax
0x180006385  jnz     short loc_1800063C1
0x180006387  mov     eax, [rdi+8]
0x18000638a  cmp     [rcx+8], eax
0x18000638d  jnz     short loc_1800063C1
0x18000638f  mov     eax, [rdi+0Ch]
0x180006392  cmp     [rcx+0Ch], eax
0x180006395  jnz     short loc_1800063C1
0x180006397  xor     ebp, ebp
0x180006399  mov     rax, [rbx+10h]
0x18000639d  cmp     rax, 1
0x1800063a1  jz      short loc_1800063D3
0x1800063a3  mov     r9, [rbx+8]
0x1800063a7  mov     r8, rsi
0x1800063aa  mov     rdx, rdi
0x1800063ad  mov     rcx, r14
0x1800063b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b5  test    eax, eax
0x1800063b7  jz      short loc_1800063E1
0x1800063b9  test    ebp, ebp
0x1800063bb  jnz     short loc_1800063C1
0x1800063bd  test    eax, eax
0x1800063bf  js      short loc_1800063E1
0x1800063c1  add     rbx, 18h
0x1800063c5  cmp     qword ptr [rbx+10h], 0
0x1800063ca  jnz     short loc_18000636C
0x1800063cc  mov     eax, 80004002h
0x1800063d1  jmp     short loc_1800063E1
0x1800063d3  mov     rbx, [rbx+8]
0x1800063d7  jmp     loc_18000634C
0x1800063dc  mov     eax, 80070057h
0x1800063e1  add     rsp, 30h
0x1800063e5  pop     r14
0x1800063e7  pop     rdi
0x1800063e8  pop     rsi
0x1800063e9  pop     rbp
0x1800063ea  pop     rbx
0x1800063eb  retn
```
