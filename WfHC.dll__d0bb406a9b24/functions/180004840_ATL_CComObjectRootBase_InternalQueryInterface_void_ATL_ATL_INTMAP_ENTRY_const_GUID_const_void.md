# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004840`
- end: `0x18000498a`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800057c0`
- `0x180005800`

## callees

- `0x180004840`
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
  char *v9; // rbx
  _DWORD *v10; // rcx
  int v11; // esi
  __int64 (__fastcall *v12)(char *, const struct _GUID *, char **, _QWORD); // rax
  char *v13; // rbx

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = &a1[*((_QWORD *)a2 + 1)];
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
    result = 0;
    *a4 = v9;
    return result;
  }
  if ( *((_QWORD *)a2 + 2) )
  {
    do
    {
      v10 = *(_DWORD **)v6;
      if ( *(_QWORD *)v6 )
      {
        if ( *v10 != a3->Data1
          || v10[1] != *(_DWORD *)&a3->Data2
          || v10[2] != *(_DWORD *)a3->Data4
          || v10[3] != *(_DWORD *)&a3->Data4[4] )
        {
          goto LABEL_21;
        }
        v11 = 0;
      }
      else
      {
        v11 = 1;
      }
      v12 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
      if ( v12 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      {
        v13 = &a1[*((_QWORD *)v6 + 1)];
        (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
        result = 0;
        *a4 = v13;
        return result;
      }
      result = v12(a1, a3, a4, *((_QWORD *)v6 + 1));
      if ( !(_DWORD)result || !v11 && (int)result < 0 )
        return result;
LABEL_21:
      v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    }
    while ( *((_QWORD *)v6 + 2) );
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180004840  push    rbx
0x180004842  push    rdi
0x180004843  push    r14
0x180004845  push    r15
0x180004847  sub     rsp, 38h
0x18000484b  mov     r14, r9
0x18000484e  mov     rdi, r8
0x180004851  mov     rbx, rdx
0x180004854  mov     r15, rcx
0x180004857  test    rcx, rcx
0x18000485a  jz      loc_18000497A
0x180004860  test    rdx, rdx
0x180004863  jz      loc_18000497A
0x180004869  test    r9, r9
0x18000486c  jnz     short loc_18000487E
0x18000486e  mov     eax, 80004003h
0x180004873  add     rsp, 38h
0x180004877  pop     r15
0x180004879  pop     r14
0x18000487b  pop     rdi
0x18000487c  pop     rbx
0x18000487d  retn
0x18000487e  mov     qword ptr [r9], 0
0x180004885  cmp     dword ptr [r8], 0
0x180004889  jnz     short loc_1800048CC
0x18000488b  cmp     dword ptr [r8+4], 0
0x180004890  jnz     short loc_1800048CC
0x180004892  cmp     dword ptr [r8+8], 0C0h
0x18000489a  jnz     short loc_1800048CC
0x18000489c  cmp     dword ptr [r8+0Ch], 46000000h
0x1800048a4  jnz     short loc_1800048CC
0x1800048a6  mov     rbx, [rdx+8]
0x1800048aa  add     rbx, r15
0x1800048ad  mov     rcx, rbx
0x1800048b0  mov     rax, [rbx]
0x1800048b3  mov     rax, [rax+8]
0x1800048b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048bc  xor     eax, eax
0x1800048be  mov     [r14], rbx
0x1800048c1  add     rsp, 38h
0x1800048c5  pop     r15
0x1800048c7  pop     r14
0x1800048c9  pop     rdi
0x1800048ca  pop     rbx
0x1800048cb  retn
0x1800048cc  cmp     qword ptr [rdx+10h], 0
0x1800048d1  mov     [rsp+58h+arg_0], rsi
0x1800048d6  jz      short loc_18000493A
0x1800048d8  mov     rcx, [rbx]
0x1800048db  test    rcx, rcx
0x1800048de  jnz     short loc_1800048E7
0x1800048e0  mov     esi, 1
0x1800048e5  jmp     short loc_180004907
0x1800048e7  mov     eax, [rdi]
0x1800048e9  cmp     [rcx], eax
0x1800048eb  jnz     short loc_18000492F
0x1800048ed  mov     eax, [rdi+4]
0x1800048f0  cmp     [rcx+4], eax
0x1800048f3  jnz     short loc_18000492F
0x1800048f5  mov     eax, [rdi+8]
0x1800048f8  cmp     [rcx+8], eax
0x1800048fb  jnz     short loc_18000492F
0x1800048fd  mov     eax, [rdi+0Ch]
0x180004900  cmp     [rcx+0Ch], eax
0x180004903  jnz     short loc_18000492F
0x180004905  xor     esi, esi
0x180004907  mov     rax, [rbx+10h]
0x18000490b  cmp     rax, 1
0x18000490f  jz      short loc_18000494F
0x180004911  mov     r9, [rbx+8]
0x180004915  mov     r8, r14
0x180004918  mov     rdx, rdi
0x18000491b  mov     rcx, r15
0x18000491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004923  test    eax, eax
0x180004925  jz      short loc_18000493F
0x180004927  test    esi, esi
0x180004929  jnz     short loc_18000492F
0x18000492b  test    eax, eax
0x18000492d  js      short loc_18000493F
0x18000492f  add     rbx, 18h
0x180004933  cmp     qword ptr [rbx+10h], 0
0x180004938  jnz     short loc_1800048D8
0x18000493a  mov     eax, 80004002h
0x18000493f  mov     rsi, [rsp+58h+arg_0]
0x180004944  add     rsp, 38h
0x180004948  pop     r15
0x18000494a  pop     r14
0x18000494c  pop     rdi
0x18000494d  pop     rbx
0x18000494e  retn
0x18000494f  mov     rbx, [rbx+8]
0x180004953  add     rbx, r15
0x180004956  mov     rcx, rbx
0x180004959  mov     rax, [rbx]
0x18000495c  mov     rax, [rax+8]
0x180004960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004965  mov     rsi, [rsp+58h+arg_0]
0x18000496a  xor     eax, eax
0x18000496c  mov     [r14], rbx
0x18000496f  add     rsp, 38h
0x180004973  pop     r15
0x180004975  pop     r14
0x180004977  pop     rdi
0x180004978  pop     rbx
0x180004979  retn
0x18000497a  mov     eax, 80070057h
0x18000497f  add     rsp, 38h
0x180004983  pop     r15
0x180004985  pop     r14
0x180004987  pop     rdi
0x180004988  pop     rbx
0x180004989  retn
```
