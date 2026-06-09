# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180006e00`
- end: `0x180006f04`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800077d0`
- `0x180007860`
- `0x180007880`

## callees

- `0x180006e00`
- `0x180013010`

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
0x180006e00  push    rbx
0x180006e02  push    rbp
0x180006e03  push    rsi
0x180006e04  push    rdi
0x180006e05  push    r14
0x180006e07  sub     rsp, 30h
0x180006e0b  mov     rsi, r9
0x180006e0e  mov     rdi, r8
0x180006e11  mov     rbx, rdx
0x180006e14  mov     r14, rcx
0x180006e17  test    rcx, rcx
0x180006e1a  jz      loc_180006EF4
0x180006e20  test    rdx, rdx
0x180006e23  jz      loc_180006EF4
0x180006e29  test    r9, r9
0x180006e2c  jnz     short loc_180006E38
0x180006e2e  mov     eax, 80004003h
0x180006e33  jmp     loc_180006EF9
0x180006e38  mov     qword ptr [r9], 0
0x180006e3f  cmp     dword ptr [r8], 0
0x180006e43  jnz     short loc_180006E7D
0x180006e45  cmp     dword ptr [r8+4], 0
0x180006e4a  jnz     short loc_180006E7D
0x180006e4c  cmp     dword ptr [r8+8], 0C0h
0x180006e54  jnz     short loc_180006E7D
0x180006e56  cmp     dword ptr [r8+0Ch], 46000000h
0x180006e5e  jnz     short loc_180006E7D
0x180006e60  mov     rbx, [rdx+8]
0x180006e64  add     rbx, r14
0x180006e67  mov     rcx, rbx
0x180006e6a  mov     rax, [rbx]
0x180006e6d  mov     rax, [rax+8]
0x180006e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e76  xor     eax, eax
0x180006e78  mov     [rsi], rbx
0x180006e7b  jmp     short loc_180006EF9
0x180006e7d  cmp     qword ptr [rdx+10h], 0
0x180006e82  jz      short loc_180006EE4
0x180006e84  mov     rcx, [rbx]
0x180006e87  test    rcx, rcx
0x180006e8a  jnz     short loc_180006E91
0x180006e8c  lea     ebp, [rcx+1]
0x180006e8f  jmp     short loc_180006EB1
0x180006e91  mov     eax, [rdi]
0x180006e93  cmp     [rcx], eax
0x180006e95  jnz     short loc_180006ED9
0x180006e97  mov     eax, [rdi+4]
0x180006e9a  cmp     [rcx+4], eax
0x180006e9d  jnz     short loc_180006ED9
0x180006e9f  mov     eax, [rdi+8]
0x180006ea2  cmp     [rcx+8], eax
0x180006ea5  jnz     short loc_180006ED9
0x180006ea7  mov     eax, [rdi+0Ch]
0x180006eaa  cmp     [rcx+0Ch], eax
0x180006ead  jnz     short loc_180006ED9
0x180006eaf  xor     ebp, ebp
0x180006eb1  mov     rax, [rbx+10h]
0x180006eb5  cmp     rax, 1
0x180006eb9  jz      short loc_180006EEB
0x180006ebb  mov     r9, [rbx+8]
0x180006ebf  mov     r8, rsi
0x180006ec2  mov     rdx, rdi
0x180006ec5  mov     rcx, r14
0x180006ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ecd  test    eax, eax
0x180006ecf  jz      short loc_180006EF9
0x180006ed1  test    ebp, ebp
0x180006ed3  jnz     short loc_180006ED9
0x180006ed5  test    eax, eax
0x180006ed7  js      short loc_180006EF9
0x180006ed9  add     rbx, 18h
0x180006edd  cmp     qword ptr [rbx+10h], 0
0x180006ee2  jnz     short loc_180006E84
0x180006ee4  mov     eax, 80004002h
0x180006ee9  jmp     short loc_180006EF9
0x180006eeb  mov     rbx, [rbx+8]
0x180006eef  jmp     loc_180006E64
0x180006ef4  mov     eax, 80070057h
0x180006ef9  add     rsp, 30h
0x180006efd  pop     r14
0x180006eff  pop     rdi
0x180006f00  pop     rsi
0x180006f01  pop     rbp
0x180006f02  pop     rbx
0x180006f03  retn
```
