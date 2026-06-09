# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800043c4`
- end: `0x1800044c8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004520`
- `0x1800045b0`
- `0x1800045d0`

## callees

- `0x1800043c4`
- `0x18000b010`

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
0x1800043c4  push    rbx
0x1800043c6  push    rbp
0x1800043c7  push    rsi
0x1800043c8  push    rdi
0x1800043c9  push    r14
0x1800043cb  sub     rsp, 30h
0x1800043cf  mov     rsi, r9
0x1800043d2  mov     rdi, r8
0x1800043d5  mov     rbx, rdx
0x1800043d8  mov     r14, rcx
0x1800043db  test    rcx, rcx
0x1800043de  jz      loc_1800044B8
0x1800043e4  test    rdx, rdx
0x1800043e7  jz      loc_1800044B8
0x1800043ed  test    r9, r9
0x1800043f0  jnz     short loc_1800043FC
0x1800043f2  mov     eax, 80004003h
0x1800043f7  jmp     loc_1800044BD
0x1800043fc  mov     qword ptr [r9], 0
0x180004403  cmp     dword ptr [r8], 0
0x180004407  jnz     short loc_180004441
0x180004409  cmp     dword ptr [r8+4], 0
0x18000440e  jnz     short loc_180004441
0x180004410  cmp     dword ptr [r8+8], 0C0h
0x180004418  jnz     short loc_180004441
0x18000441a  cmp     dword ptr [r8+0Ch], 46000000h
0x180004422  jnz     short loc_180004441
0x180004424  mov     rbx, [rdx+8]
0x180004428  add     rbx, r14
0x18000442b  mov     rcx, rbx
0x18000442e  mov     rax, [rbx]
0x180004431  mov     rax, [rax+8]
0x180004435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443a  xor     eax, eax
0x18000443c  mov     [rsi], rbx
0x18000443f  jmp     short loc_1800044BD
0x180004441  cmp     qword ptr [rdx+10h], 0
0x180004446  jz      short loc_1800044A8
0x180004448  mov     rcx, [rbx]
0x18000444b  test    rcx, rcx
0x18000444e  jnz     short loc_180004455
0x180004450  lea     ebp, [rcx+1]
0x180004453  jmp     short loc_180004475
0x180004455  mov     eax, [rdi]
0x180004457  cmp     [rcx], eax
0x180004459  jnz     short loc_18000449D
0x18000445b  mov     eax, [rdi+4]
0x18000445e  cmp     [rcx+4], eax
0x180004461  jnz     short loc_18000449D
0x180004463  mov     eax, [rdi+8]
0x180004466  cmp     [rcx+8], eax
0x180004469  jnz     short loc_18000449D
0x18000446b  mov     eax, [rdi+0Ch]
0x18000446e  cmp     [rcx+0Ch], eax
0x180004471  jnz     short loc_18000449D
0x180004473  xor     ebp, ebp
0x180004475  mov     rax, [rbx+10h]
0x180004479  cmp     rax, 1
0x18000447d  jz      short loc_1800044AF
0x18000447f  mov     r9, [rbx+8]
0x180004483  mov     r8, rsi
0x180004486  mov     rdx, rdi
0x180004489  mov     rcx, r14
0x18000448c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004491  test    eax, eax
0x180004493  jz      short loc_1800044BD
0x180004495  test    ebp, ebp
0x180004497  jnz     short loc_18000449D
0x180004499  test    eax, eax
0x18000449b  js      short loc_1800044BD
0x18000449d  add     rbx, 18h
0x1800044a1  cmp     qword ptr [rbx+10h], 0
0x1800044a6  jnz     short loc_180004448
0x1800044a8  mov     eax, 80004002h
0x1800044ad  jmp     short loc_1800044BD
0x1800044af  mov     rbx, [rbx+8]
0x1800044b3  jmp     loc_180004428
0x1800044b8  mov     eax, 80070057h
0x1800044bd  add     rsp, 30h
0x1800044c1  pop     r14
0x1800044c3  pop     rdi
0x1800044c4  pop     rsi
0x1800044c5  pop     rbp
0x1800044c6  pop     rbx
0x1800044c7  retn
```
