# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180005b90`
- end: `0x180005c94`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006560`
- `0x1800065f0`
- `0x180006610`

## callees

- `0x180005b90`
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
0x180005b90  push    rbx
0x180005b92  push    rbp
0x180005b93  push    rsi
0x180005b94  push    rdi
0x180005b95  push    r14
0x180005b97  sub     rsp, 30h
0x180005b9b  mov     rsi, r9
0x180005b9e  mov     rdi, r8
0x180005ba1  mov     rbx, rdx
0x180005ba4  mov     r14, rcx
0x180005ba7  test    rcx, rcx
0x180005baa  jz      loc_180005C84
0x180005bb0  test    rdx, rdx
0x180005bb3  jz      loc_180005C84
0x180005bb9  test    r9, r9
0x180005bbc  jnz     short loc_180005BC8
0x180005bbe  mov     eax, 80004003h
0x180005bc3  jmp     loc_180005C89
0x180005bc8  mov     qword ptr [r9], 0
0x180005bcf  cmp     dword ptr [r8], 0
0x180005bd3  jnz     short loc_180005C0D
0x180005bd5  cmp     dword ptr [r8+4], 0
0x180005bda  jnz     short loc_180005C0D
0x180005bdc  cmp     dword ptr [r8+8], 0C0h
0x180005be4  jnz     short loc_180005C0D
0x180005be6  cmp     dword ptr [r8+0Ch], 46000000h
0x180005bee  jnz     short loc_180005C0D
0x180005bf0  mov     rbx, [rdx+8]
0x180005bf4  add     rbx, r14
0x180005bf7  mov     rcx, rbx
0x180005bfa  mov     rax, [rbx]
0x180005bfd  mov     rax, [rax+8]
0x180005c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c06  xor     eax, eax
0x180005c08  mov     [rsi], rbx
0x180005c0b  jmp     short loc_180005C89
0x180005c0d  cmp     qword ptr [rdx+10h], 0
0x180005c12  jz      short loc_180005C74
0x180005c14  mov     rcx, [rbx]
0x180005c17  test    rcx, rcx
0x180005c1a  jnz     short loc_180005C21
0x180005c1c  lea     ebp, [rcx+1]
0x180005c1f  jmp     short loc_180005C41
0x180005c21  mov     eax, [rdi]
0x180005c23  cmp     [rcx], eax
0x180005c25  jnz     short loc_180005C69
0x180005c27  mov     eax, [rdi+4]
0x180005c2a  cmp     [rcx+4], eax
0x180005c2d  jnz     short loc_180005C69
0x180005c2f  mov     eax, [rdi+8]
0x180005c32  cmp     [rcx+8], eax
0x180005c35  jnz     short loc_180005C69
0x180005c37  mov     eax, [rdi+0Ch]
0x180005c3a  cmp     [rcx+0Ch], eax
0x180005c3d  jnz     short loc_180005C69
0x180005c3f  xor     ebp, ebp
0x180005c41  mov     rax, [rbx+10h]
0x180005c45  cmp     rax, 1
0x180005c49  jz      short loc_180005C7B
0x180005c4b  mov     r9, [rbx+8]
0x180005c4f  mov     r8, rsi
0x180005c52  mov     rdx, rdi
0x180005c55  mov     rcx, r14
0x180005c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5d  test    eax, eax
0x180005c5f  jz      short loc_180005C89
0x180005c61  test    ebp, ebp
0x180005c63  jnz     short loc_180005C69
0x180005c65  test    eax, eax
0x180005c67  js      short loc_180005C89
0x180005c69  add     rbx, 18h
0x180005c6d  cmp     qword ptr [rbx+10h], 0
0x180005c72  jnz     short loc_180005C14
0x180005c74  mov     eax, 80004002h
0x180005c79  jmp     short loc_180005C89
0x180005c7b  mov     rbx, [rbx+8]
0x180005c7f  jmp     loc_180005BF4
0x180005c84  mov     eax, 80070057h
0x180005c89  add     rsp, 30h
0x180005c8d  pop     r14
0x180005c8f  pop     rdi
0x180005c90  pop     rsi
0x180005c91  pop     rbp
0x180005c92  pop     rbx
0x180005c93  retn
```
