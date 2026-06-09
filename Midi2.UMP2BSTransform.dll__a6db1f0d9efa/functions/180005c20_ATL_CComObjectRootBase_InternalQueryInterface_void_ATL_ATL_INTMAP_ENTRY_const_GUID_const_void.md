# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180005c20`
- end: `0x180005d24`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800065f0`
- `0x180006680`
- `0x1800066a0`

## callees

- `0x180005c20`
- `0x18000f010`

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
0x180005c20  push    rbx
0x180005c22  push    rbp
0x180005c23  push    rsi
0x180005c24  push    rdi
0x180005c25  push    r14
0x180005c27  sub     rsp, 30h
0x180005c2b  mov     rsi, r9
0x180005c2e  mov     rdi, r8
0x180005c31  mov     rbx, rdx
0x180005c34  mov     r14, rcx
0x180005c37  test    rcx, rcx
0x180005c3a  jz      loc_180005D14
0x180005c40  test    rdx, rdx
0x180005c43  jz      loc_180005D14
0x180005c49  test    r9, r9
0x180005c4c  jnz     short loc_180005C58
0x180005c4e  mov     eax, 80004003h
0x180005c53  jmp     loc_180005D19
0x180005c58  mov     qword ptr [r9], 0
0x180005c5f  cmp     dword ptr [r8], 0
0x180005c63  jnz     short loc_180005C9D
0x180005c65  cmp     dword ptr [r8+4], 0
0x180005c6a  jnz     short loc_180005C9D
0x180005c6c  cmp     dword ptr [r8+8], 0C0h
0x180005c74  jnz     short loc_180005C9D
0x180005c76  cmp     dword ptr [r8+0Ch], 46000000h
0x180005c7e  jnz     short loc_180005C9D
0x180005c80  mov     rbx, [rdx+8]
0x180005c84  add     rbx, r14
0x180005c87  mov     rcx, rbx
0x180005c8a  mov     rax, [rbx]
0x180005c8d  mov     rax, [rax+8]
0x180005c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c96  xor     eax, eax
0x180005c98  mov     [rsi], rbx
0x180005c9b  jmp     short loc_180005D19
0x180005c9d  cmp     qword ptr [rdx+10h], 0
0x180005ca2  jz      short loc_180005D04
0x180005ca4  mov     rcx, [rbx]
0x180005ca7  test    rcx, rcx
0x180005caa  jnz     short loc_180005CB1
0x180005cac  lea     ebp, [rcx+1]
0x180005caf  jmp     short loc_180005CD1
0x180005cb1  mov     eax, [rdi]
0x180005cb3  cmp     [rcx], eax
0x180005cb5  jnz     short loc_180005CF9
0x180005cb7  mov     eax, [rdi+4]
0x180005cba  cmp     [rcx+4], eax
0x180005cbd  jnz     short loc_180005CF9
0x180005cbf  mov     eax, [rdi+8]
0x180005cc2  cmp     [rcx+8], eax
0x180005cc5  jnz     short loc_180005CF9
0x180005cc7  mov     eax, [rdi+0Ch]
0x180005cca  cmp     [rcx+0Ch], eax
0x180005ccd  jnz     short loc_180005CF9
0x180005ccf  xor     ebp, ebp
0x180005cd1  mov     rax, [rbx+10h]
0x180005cd5  cmp     rax, 1
0x180005cd9  jz      short loc_180005D0B
0x180005cdb  mov     r9, [rbx+8]
0x180005cdf  mov     r8, rsi
0x180005ce2  mov     rdx, rdi
0x180005ce5  mov     rcx, r14
0x180005ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ced  test    eax, eax
0x180005cef  jz      short loc_180005D19
0x180005cf1  test    ebp, ebp
0x180005cf3  jnz     short loc_180005CF9
0x180005cf5  test    eax, eax
0x180005cf7  js      short loc_180005D19
0x180005cf9  add     rbx, 18h
0x180005cfd  cmp     qword ptr [rbx+10h], 0
0x180005d02  jnz     short loc_180005CA4
0x180005d04  mov     eax, 80004002h
0x180005d09  jmp     short loc_180005D19
0x180005d0b  mov     rbx, [rbx+8]
0x180005d0f  jmp     loc_180005C84
0x180005d14  mov     eax, 80070057h
0x180005d19  add     rsp, 30h
0x180005d1d  pop     r14
0x180005d1f  pop     rdi
0x180005d20  pop     rsi
0x180005d21  pop     rbp
0x180005d22  pop     rbx
0x180005d23  retn
```
