# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800043b8`
- end: `0x1800044bc`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800046c0`
- `0x1800046e0`
- `0x180004700`
- `0x180006c10`
- `0x180007270`
- `0x180008020`
- `0x18000a310`

## callees

- `0x1800043b8`
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
0x1800043b8  push    rbx
0x1800043ba  push    rbp
0x1800043bb  push    rsi
0x1800043bc  push    rdi
0x1800043bd  push    r14
0x1800043bf  sub     rsp, 30h
0x1800043c3  mov     rsi, r9
0x1800043c6  mov     rdi, r8
0x1800043c9  mov     rbx, rdx
0x1800043cc  mov     r14, rcx
0x1800043cf  test    rcx, rcx
0x1800043d2  jz      loc_1800044AC
0x1800043d8  test    rdx, rdx
0x1800043db  jz      loc_1800044AC
0x1800043e1  test    r9, r9
0x1800043e4  jnz     short loc_1800043F0
0x1800043e6  mov     eax, 80004003h
0x1800043eb  jmp     loc_1800044B1
0x1800043f0  mov     qword ptr [r9], 0
0x1800043f7  cmp     dword ptr [r8], 0
0x1800043fb  jnz     short loc_180004435
0x1800043fd  cmp     dword ptr [r8+4], 0
0x180004402  jnz     short loc_180004435
0x180004404  cmp     dword ptr [r8+8], 0C0h
0x18000440c  jnz     short loc_180004435
0x18000440e  cmp     dword ptr [r8+0Ch], 46000000h
0x180004416  jnz     short loc_180004435
0x180004418  mov     rbx, [rdx+8]
0x18000441c  add     rbx, r14
0x18000441f  mov     rcx, rbx
0x180004422  mov     rax, [rbx]
0x180004425  mov     rax, [rax+8]
0x180004429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000442e  xor     eax, eax
0x180004430  mov     [rsi], rbx
0x180004433  jmp     short loc_1800044B1
0x180004435  cmp     qword ptr [rdx+10h], 0
0x18000443a  jz      short loc_18000449C
0x18000443c  mov     rcx, [rbx]
0x18000443f  test    rcx, rcx
0x180004442  jnz     short loc_180004449
0x180004444  lea     ebp, [rcx+1]
0x180004447  jmp     short loc_180004469
0x180004449  mov     eax, [rdi]
0x18000444b  cmp     [rcx], eax
0x18000444d  jnz     short loc_180004491
0x18000444f  mov     eax, [rdi+4]
0x180004452  cmp     [rcx+4], eax
0x180004455  jnz     short loc_180004491
0x180004457  mov     eax, [rdi+8]
0x18000445a  cmp     [rcx+8], eax
0x18000445d  jnz     short loc_180004491
0x18000445f  mov     eax, [rdi+0Ch]
0x180004462  cmp     [rcx+0Ch], eax
0x180004465  jnz     short loc_180004491
0x180004467  xor     ebp, ebp
0x180004469  mov     rax, [rbx+10h]
0x18000446d  cmp     rax, 1
0x180004471  jz      short loc_1800044A3
0x180004473  mov     r9, [rbx+8]
0x180004477  mov     r8, rsi
0x18000447a  mov     rdx, rdi
0x18000447d  mov     rcx, r14
0x180004480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004485  test    eax, eax
0x180004487  jz      short loc_1800044B1
0x180004489  test    ebp, ebp
0x18000448b  jnz     short loc_180004491
0x18000448d  test    eax, eax
0x18000448f  js      short loc_1800044B1
0x180004491  add     rbx, 18h
0x180004495  cmp     qword ptr [rbx+10h], 0
0x18000449a  jnz     short loc_18000443C
0x18000449c  mov     eax, 80004002h
0x1800044a1  jmp     short loc_1800044B1
0x1800044a3  mov     rbx, [rbx+8]
0x1800044a7  jmp     loc_18000441C
0x1800044ac  mov     eax, 80070057h
0x1800044b1  add     rsp, 30h
0x1800044b5  pop     r14
0x1800044b7  pop     rdi
0x1800044b8  pop     rsi
0x1800044b9  pop     rbp
0x1800044ba  pop     rbx
0x1800044bb  retn
```
