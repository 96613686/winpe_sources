# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180005d30`
- end: `0x180005e34`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006700`
- `0x180006790`
- `0x1800067b0`

## callees

- `0x180005d30`
- `0x18000e010`

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
0x180005d30  push    rbx
0x180005d32  push    rbp
0x180005d33  push    rsi
0x180005d34  push    rdi
0x180005d35  push    r14
0x180005d37  sub     rsp, 30h
0x180005d3b  mov     rsi, r9
0x180005d3e  mov     rdi, r8
0x180005d41  mov     rbx, rdx
0x180005d44  mov     r14, rcx
0x180005d47  test    rcx, rcx
0x180005d4a  jz      loc_180005E24
0x180005d50  test    rdx, rdx
0x180005d53  jz      loc_180005E24
0x180005d59  test    r9, r9
0x180005d5c  jnz     short loc_180005D68
0x180005d5e  mov     eax, 80004003h
0x180005d63  jmp     loc_180005E29
0x180005d68  mov     qword ptr [r9], 0
0x180005d6f  cmp     dword ptr [r8], 0
0x180005d73  jnz     short loc_180005DAD
0x180005d75  cmp     dword ptr [r8+4], 0
0x180005d7a  jnz     short loc_180005DAD
0x180005d7c  cmp     dword ptr [r8+8], 0C0h
0x180005d84  jnz     short loc_180005DAD
0x180005d86  cmp     dword ptr [r8+0Ch], 46000000h
0x180005d8e  jnz     short loc_180005DAD
0x180005d90  mov     rbx, [rdx+8]
0x180005d94  add     rbx, r14
0x180005d97  mov     rcx, rbx
0x180005d9a  mov     rax, [rbx]
0x180005d9d  mov     rax, [rax+8]
0x180005da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da6  xor     eax, eax
0x180005da8  mov     [rsi], rbx
0x180005dab  jmp     short loc_180005E29
0x180005dad  cmp     qword ptr [rdx+10h], 0
0x180005db2  jz      short loc_180005E14
0x180005db4  mov     rcx, [rbx]
0x180005db7  test    rcx, rcx
0x180005dba  jnz     short loc_180005DC1
0x180005dbc  lea     ebp, [rcx+1]
0x180005dbf  jmp     short loc_180005DE1
0x180005dc1  mov     eax, [rdi]
0x180005dc3  cmp     [rcx], eax
0x180005dc5  jnz     short loc_180005E09
0x180005dc7  mov     eax, [rdi+4]
0x180005dca  cmp     [rcx+4], eax
0x180005dcd  jnz     short loc_180005E09
0x180005dcf  mov     eax, [rdi+8]
0x180005dd2  cmp     [rcx+8], eax
0x180005dd5  jnz     short loc_180005E09
0x180005dd7  mov     eax, [rdi+0Ch]
0x180005dda  cmp     [rcx+0Ch], eax
0x180005ddd  jnz     short loc_180005E09
0x180005ddf  xor     ebp, ebp
0x180005de1  mov     rax, [rbx+10h]
0x180005de5  cmp     rax, 1
0x180005de9  jz      short loc_180005E1B
0x180005deb  mov     r9, [rbx+8]
0x180005def  mov     r8, rsi
0x180005df2  mov     rdx, rdi
0x180005df5  mov     rcx, r14
0x180005df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfd  test    eax, eax
0x180005dff  jz      short loc_180005E29
0x180005e01  test    ebp, ebp
0x180005e03  jnz     short loc_180005E09
0x180005e05  test    eax, eax
0x180005e07  js      short loc_180005E29
0x180005e09  add     rbx, 18h
0x180005e0d  cmp     qword ptr [rbx+10h], 0
0x180005e12  jnz     short loc_180005DB4
0x180005e14  mov     eax, 80004002h
0x180005e19  jmp     short loc_180005E29
0x180005e1b  mov     rbx, [rbx+8]
0x180005e1f  jmp     loc_180005D94
0x180005e24  mov     eax, 80070057h
0x180005e29  add     rsp, 30h
0x180005e2d  pop     r14
0x180005e2f  pop     rdi
0x180005e30  pop     rsi
0x180005e31  pop     rbp
0x180005e32  pop     rbx
0x180005e33  retn
```
