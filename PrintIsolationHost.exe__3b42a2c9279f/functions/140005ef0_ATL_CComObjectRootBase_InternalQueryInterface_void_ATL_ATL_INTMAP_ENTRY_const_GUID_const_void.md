# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x140005ef0`
- end: `0x140005ff4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006150`
- `0x140006170`

## callees

- `0x140005ef0`
- `0x140008010`

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
0x140005ef0  push    rbx
0x140005ef2  push    rbp
0x140005ef3  push    rsi
0x140005ef4  push    rdi
0x140005ef5  push    r14
0x140005ef7  sub     rsp, 30h
0x140005efb  mov     rsi, r9
0x140005efe  mov     rdi, r8
0x140005f01  mov     rbx, rdx
0x140005f04  mov     r14, rcx
0x140005f07  test    rcx, rcx
0x140005f0a  jz      loc_140005FE4
0x140005f10  test    rdx, rdx
0x140005f13  jz      loc_140005FE4
0x140005f19  test    r9, r9
0x140005f1c  jnz     short loc_140005F28
0x140005f1e  mov     eax, 80004003h
0x140005f23  jmp     loc_140005FE9
0x140005f28  mov     qword ptr [r9], 0
0x140005f2f  cmp     dword ptr [r8], 0
0x140005f33  jnz     short loc_140005F6D
0x140005f35  cmp     dword ptr [r8+4], 0
0x140005f3a  jnz     short loc_140005F6D
0x140005f3c  cmp     dword ptr [r8+8], 0C0h
0x140005f44  jnz     short loc_140005F6D
0x140005f46  cmp     dword ptr [r8+0Ch], 46000000h
0x140005f4e  jnz     short loc_140005F6D
0x140005f50  mov     rbx, [rdx+8]
0x140005f54  add     rbx, r14
0x140005f57  mov     rcx, rbx
0x140005f5a  mov     rax, [rbx]
0x140005f5d  mov     rax, [rax+8]
0x140005f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f66  xor     eax, eax
0x140005f68  mov     [rsi], rbx
0x140005f6b  jmp     short loc_140005FE9
0x140005f6d  cmp     qword ptr [rdx+10h], 0
0x140005f72  jz      short loc_140005FD4
0x140005f74  mov     rcx, [rbx]
0x140005f77  test    rcx, rcx
0x140005f7a  jnz     short loc_140005F81
0x140005f7c  lea     ebp, [rcx+1]
0x140005f7f  jmp     short loc_140005FA1
0x140005f81  mov     eax, [rdi]
0x140005f83  cmp     [rcx], eax
0x140005f85  jnz     short loc_140005FC9
0x140005f87  mov     eax, [rdi+4]
0x140005f8a  cmp     [rcx+4], eax
0x140005f8d  jnz     short loc_140005FC9
0x140005f8f  mov     eax, [rdi+8]
0x140005f92  cmp     [rcx+8], eax
0x140005f95  jnz     short loc_140005FC9
0x140005f97  mov     eax, [rdi+0Ch]
0x140005f9a  cmp     [rcx+0Ch], eax
0x140005f9d  jnz     short loc_140005FC9
0x140005f9f  xor     ebp, ebp
0x140005fa1  mov     rax, [rbx+10h]
0x140005fa5  cmp     rax, 1
0x140005fa9  jz      short loc_140005FDB
0x140005fab  mov     r9, [rbx+8]
0x140005faf  mov     r8, rsi
0x140005fb2  mov     rdx, rdi
0x140005fb5  mov     rcx, r14
0x140005fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fbd  test    eax, eax
0x140005fbf  jz      short loc_140005FE9
0x140005fc1  test    ebp, ebp
0x140005fc3  jnz     short loc_140005FC9
0x140005fc5  test    eax, eax
0x140005fc7  js      short loc_140005FE9
0x140005fc9  add     rbx, 18h
0x140005fcd  cmp     qword ptr [rbx+10h], 0
0x140005fd2  jnz     short loc_140005F74
0x140005fd4  mov     eax, 80004002h
0x140005fd9  jmp     short loc_140005FE9
0x140005fdb  mov     rbx, [rbx+8]
0x140005fdf  jmp     loc_140005F54
0x140005fe4  mov     eax, 80070057h
0x140005fe9  add     rsp, 30h
0x140005fed  pop     r14
0x140005fef  pop     rdi
0x140005ff0  pop     rsi
0x140005ff1  pop     rbp
0x140005ff2  pop     rbx
0x140005ff3  retn
```
