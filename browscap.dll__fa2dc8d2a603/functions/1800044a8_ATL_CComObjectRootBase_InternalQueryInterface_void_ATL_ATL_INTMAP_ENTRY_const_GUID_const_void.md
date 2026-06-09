# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800044a8`
- end: `0x1800045ac`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004cf0`
- `0x180004d90`
- `0x180004dc0`

## callees

- `0x1800044a8`
- `0x18000d010`

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
0x1800044a8  push    rbx
0x1800044aa  push    rbp
0x1800044ab  push    rsi
0x1800044ac  push    rdi
0x1800044ad  push    r14
0x1800044af  sub     rsp, 30h
0x1800044b3  mov     rsi, r9
0x1800044b6  mov     rdi, r8
0x1800044b9  mov     rbx, rdx
0x1800044bc  mov     r14, rcx
0x1800044bf  test    rcx, rcx
0x1800044c2  jz      loc_18000459C
0x1800044c8  test    rdx, rdx
0x1800044cb  jz      loc_18000459C
0x1800044d1  test    r9, r9
0x1800044d4  jnz     short loc_1800044E0
0x1800044d6  mov     eax, 80004003h
0x1800044db  jmp     loc_1800045A1
0x1800044e0  mov     qword ptr [r9], 0
0x1800044e7  cmp     dword ptr [r8], 0
0x1800044eb  jnz     short loc_180004525
0x1800044ed  cmp     dword ptr [r8+4], 0
0x1800044f2  jnz     short loc_180004525
0x1800044f4  cmp     dword ptr [r8+8], 0C0h
0x1800044fc  jnz     short loc_180004525
0x1800044fe  cmp     dword ptr [r8+0Ch], 46000000h
0x180004506  jnz     short loc_180004525
0x180004508  mov     rbx, [rdx+8]
0x18000450c  add     rbx, r14
0x18000450f  mov     rcx, rbx
0x180004512  mov     rax, [rbx]
0x180004515  mov     rax, [rax+8]
0x180004519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451e  xor     eax, eax
0x180004520  mov     [rsi], rbx
0x180004523  jmp     short loc_1800045A1
0x180004525  cmp     qword ptr [rdx+10h], 0
0x18000452a  jz      short loc_18000458C
0x18000452c  mov     rcx, [rbx]
0x18000452f  test    rcx, rcx
0x180004532  jnz     short loc_180004539
0x180004534  lea     ebp, [rcx+1]
0x180004537  jmp     short loc_180004559
0x180004539  mov     eax, [rdi]
0x18000453b  cmp     [rcx], eax
0x18000453d  jnz     short loc_180004581
0x18000453f  mov     eax, [rdi+4]
0x180004542  cmp     [rcx+4], eax
0x180004545  jnz     short loc_180004581
0x180004547  mov     eax, [rdi+8]
0x18000454a  cmp     [rcx+8], eax
0x18000454d  jnz     short loc_180004581
0x18000454f  mov     eax, [rdi+0Ch]
0x180004552  cmp     [rcx+0Ch], eax
0x180004555  jnz     short loc_180004581
0x180004557  xor     ebp, ebp
0x180004559  mov     rax, [rbx+10h]
0x18000455d  cmp     rax, 1
0x180004561  jz      short loc_180004593
0x180004563  mov     r9, [rbx+8]
0x180004567  mov     r8, rsi
0x18000456a  mov     rdx, rdi
0x18000456d  mov     rcx, r14
0x180004570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004575  test    eax, eax
0x180004577  jz      short loc_1800045A1
0x180004579  test    ebp, ebp
0x18000457b  jnz     short loc_180004581
0x18000457d  test    eax, eax
0x18000457f  js      short loc_1800045A1
0x180004581  add     rbx, 18h
0x180004585  cmp     qword ptr [rbx+10h], 0
0x18000458a  jnz     short loc_18000452C
0x18000458c  mov     eax, 80004002h
0x180004591  jmp     short loc_1800045A1
0x180004593  mov     rbx, [rbx+8]
0x180004597  jmp     loc_18000450C
0x18000459c  mov     eax, 80070057h
0x1800045a1  add     rsp, 30h
0x1800045a5  pop     r14
0x1800045a7  pop     rdi
0x1800045a8  pop     rsi
0x1800045a9  pop     rbp
0x1800045aa  pop     rbx
0x1800045ab  retn
```
