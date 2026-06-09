# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004b24`
- end: `0x180004c28`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050f0`
- `0x180005160`
- `0x180005220`
- `0x180005250`
- `0x180005270`

## callees

- `0x180004b24`
- `0x18000c010`

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
0x180004b24  push    rbx
0x180004b26  push    rbp
0x180004b27  push    rsi
0x180004b28  push    rdi
0x180004b29  push    r14
0x180004b2b  sub     rsp, 30h
0x180004b2f  mov     rsi, r9
0x180004b32  mov     rdi, r8
0x180004b35  mov     rbx, rdx
0x180004b38  mov     r14, rcx
0x180004b3b  test    rcx, rcx
0x180004b3e  jz      loc_180004C18
0x180004b44  test    rdx, rdx
0x180004b47  jz      loc_180004C18
0x180004b4d  test    r9, r9
0x180004b50  jnz     short loc_180004B5C
0x180004b52  mov     eax, 80004003h
0x180004b57  jmp     loc_180004C1D
0x180004b5c  mov     qword ptr [r9], 0
0x180004b63  cmp     dword ptr [r8], 0
0x180004b67  jnz     short loc_180004BA1
0x180004b69  cmp     dword ptr [r8+4], 0
0x180004b6e  jnz     short loc_180004BA1
0x180004b70  cmp     dword ptr [r8+8], 0C0h
0x180004b78  jnz     short loc_180004BA1
0x180004b7a  cmp     dword ptr [r8+0Ch], 46000000h
0x180004b82  jnz     short loc_180004BA1
0x180004b84  mov     rbx, [rdx+8]
0x180004b88  add     rbx, r14
0x180004b8b  mov     rcx, rbx
0x180004b8e  mov     rax, [rbx]
0x180004b91  mov     rax, [rax+8]
0x180004b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9a  xor     eax, eax
0x180004b9c  mov     [rsi], rbx
0x180004b9f  jmp     short loc_180004C1D
0x180004ba1  cmp     qword ptr [rdx+10h], 0
0x180004ba6  jz      short loc_180004C08
0x180004ba8  mov     rcx, [rbx]
0x180004bab  test    rcx, rcx
0x180004bae  jnz     short loc_180004BB5
0x180004bb0  lea     ebp, [rcx+1]
0x180004bb3  jmp     short loc_180004BD5
0x180004bb5  mov     eax, [rdi]
0x180004bb7  cmp     [rcx], eax
0x180004bb9  jnz     short loc_180004BFD
0x180004bbb  mov     eax, [rdi+4]
0x180004bbe  cmp     [rcx+4], eax
0x180004bc1  jnz     short loc_180004BFD
0x180004bc3  mov     eax, [rdi+8]
0x180004bc6  cmp     [rcx+8], eax
0x180004bc9  jnz     short loc_180004BFD
0x180004bcb  mov     eax, [rdi+0Ch]
0x180004bce  cmp     [rcx+0Ch], eax
0x180004bd1  jnz     short loc_180004BFD
0x180004bd3  xor     ebp, ebp
0x180004bd5  mov     rax, [rbx+10h]
0x180004bd9  cmp     rax, 1
0x180004bdd  jz      short loc_180004C0F
0x180004bdf  mov     r9, [rbx+8]
0x180004be3  mov     r8, rsi
0x180004be6  mov     rdx, rdi
0x180004be9  mov     rcx, r14
0x180004bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf1  test    eax, eax
0x180004bf3  jz      short loc_180004C1D
0x180004bf5  test    ebp, ebp
0x180004bf7  jnz     short loc_180004BFD
0x180004bf9  test    eax, eax
0x180004bfb  js      short loc_180004C1D
0x180004bfd  add     rbx, 18h
0x180004c01  cmp     qword ptr [rbx+10h], 0
0x180004c06  jnz     short loc_180004BA8
0x180004c08  mov     eax, 80004002h
0x180004c0d  jmp     short loc_180004C1D
0x180004c0f  mov     rbx, [rbx+8]
0x180004c13  jmp     loc_180004B88
0x180004c18  mov     eax, 80070057h
0x180004c1d  add     rsp, 30h
0x180004c21  pop     r14
0x180004c23  pop     rdi
0x180004c24  pop     rsi
0x180004c25  pop     rbp
0x180004c26  pop     rbx
0x180004c27  retn
```
