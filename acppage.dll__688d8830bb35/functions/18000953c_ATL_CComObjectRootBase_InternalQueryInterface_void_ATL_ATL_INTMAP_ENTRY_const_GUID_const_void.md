# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000953c`
- end: `0x180009640`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009920`
- `0x180009970`
- `0x18000dd90`
- `0x18000de40`

## callees

- `0x18000953c`
- `0x180017010`

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
0x18000953c  push    rbx
0x18000953e  push    rbp
0x18000953f  push    rsi
0x180009540  push    rdi
0x180009541  push    r14
0x180009543  sub     rsp, 30h
0x180009547  mov     rsi, r9
0x18000954a  mov     rdi, r8
0x18000954d  mov     rbx, rdx
0x180009550  mov     r14, rcx
0x180009553  test    rcx, rcx
0x180009556  jz      loc_180009630
0x18000955c  test    rdx, rdx
0x18000955f  jz      loc_180009630
0x180009565  test    r9, r9
0x180009568  jnz     short loc_180009574
0x18000956a  mov     eax, 80004003h
0x18000956f  jmp     loc_180009635
0x180009574  mov     qword ptr [r9], 0
0x18000957b  cmp     dword ptr [r8], 0
0x18000957f  jnz     short loc_1800095B9
0x180009581  cmp     dword ptr [r8+4], 0
0x180009586  jnz     short loc_1800095B9
0x180009588  cmp     dword ptr [r8+8], 0C0h
0x180009590  jnz     short loc_1800095B9
0x180009592  cmp     dword ptr [r8+0Ch], 46000000h
0x18000959a  jnz     short loc_1800095B9
0x18000959c  mov     rbx, [rdx+8]
0x1800095a0  add     rbx, r14
0x1800095a3  mov     rcx, rbx
0x1800095a6  mov     rax, [rbx]
0x1800095a9  mov     rax, [rax+8]
0x1800095ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b2  xor     eax, eax
0x1800095b4  mov     [rsi], rbx
0x1800095b7  jmp     short loc_180009635
0x1800095b9  cmp     qword ptr [rdx+10h], 0
0x1800095be  jz      short loc_180009620
0x1800095c0  mov     rcx, [rbx]
0x1800095c3  test    rcx, rcx
0x1800095c6  jnz     short loc_1800095CD
0x1800095c8  lea     ebp, [rcx+1]
0x1800095cb  jmp     short loc_1800095ED
0x1800095cd  mov     eax, [rdi]
0x1800095cf  cmp     [rcx], eax
0x1800095d1  jnz     short loc_180009615
0x1800095d3  mov     eax, [rdi+4]
0x1800095d6  cmp     [rcx+4], eax
0x1800095d9  jnz     short loc_180009615
0x1800095db  mov     eax, [rdi+8]
0x1800095de  cmp     [rcx+8], eax
0x1800095e1  jnz     short loc_180009615
0x1800095e3  mov     eax, [rdi+0Ch]
0x1800095e6  cmp     [rcx+0Ch], eax
0x1800095e9  jnz     short loc_180009615
0x1800095eb  xor     ebp, ebp
0x1800095ed  mov     rax, [rbx+10h]
0x1800095f1  cmp     rax, 1
0x1800095f5  jz      short loc_180009627
0x1800095f7  mov     r9, [rbx+8]
0x1800095fb  mov     r8, rsi
0x1800095fe  mov     rdx, rdi
0x180009601  mov     rcx, r14
0x180009604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009609  test    eax, eax
0x18000960b  jz      short loc_180009635
0x18000960d  test    ebp, ebp
0x18000960f  jnz     short loc_180009615
0x180009611  test    eax, eax
0x180009613  js      short loc_180009635
0x180009615  add     rbx, 18h
0x180009619  cmp     qword ptr [rbx+10h], 0
0x18000961e  jnz     short loc_1800095C0
0x180009620  mov     eax, 80004002h
0x180009625  jmp     short loc_180009635
0x180009627  mov     rbx, [rbx+8]
0x18000962b  jmp     loc_1800095A0
0x180009630  mov     eax, 80070057h
0x180009635  add     rsp, 30h
0x180009639  pop     r14
0x18000963b  pop     rdi
0x18000963c  pop     rsi
0x18000963d  pop     rbp
0x18000963e  pop     rbx
0x18000963f  retn
```
