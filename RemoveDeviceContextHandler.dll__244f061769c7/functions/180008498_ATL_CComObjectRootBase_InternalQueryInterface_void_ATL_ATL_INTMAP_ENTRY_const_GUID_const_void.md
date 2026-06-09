# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180008498`
- end: `0x18000859c`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009230`
- `0x1800092a0`
- `0x180009360`
- `0x180009390`
- `0x1800093b0`

## callees

- `0x180008498`
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
0x180008498  push    rbx
0x18000849a  push    rbp
0x18000849b  push    rsi
0x18000849c  push    rdi
0x18000849d  push    r14
0x18000849f  sub     rsp, 30h
0x1800084a3  mov     rsi, r9
0x1800084a6  mov     rdi, r8
0x1800084a9  mov     rbx, rdx
0x1800084ac  mov     r14, rcx
0x1800084af  test    rcx, rcx
0x1800084b2  jz      loc_18000858C
0x1800084b8  test    rdx, rdx
0x1800084bb  jz      loc_18000858C
0x1800084c1  test    r9, r9
0x1800084c4  jnz     short loc_1800084D0
0x1800084c6  mov     eax, 80004003h
0x1800084cb  jmp     loc_180008591
0x1800084d0  mov     qword ptr [r9], 0
0x1800084d7  cmp     dword ptr [r8], 0
0x1800084db  jnz     short loc_180008515
0x1800084dd  cmp     dword ptr [r8+4], 0
0x1800084e2  jnz     short loc_180008515
0x1800084e4  cmp     dword ptr [r8+8], 0C0h
0x1800084ec  jnz     short loc_180008515
0x1800084ee  cmp     dword ptr [r8+0Ch], 46000000h
0x1800084f6  jnz     short loc_180008515
0x1800084f8  mov     rbx, [rdx+8]
0x1800084fc  add     rbx, r14
0x1800084ff  mov     rcx, rbx
0x180008502  mov     rax, [rbx]
0x180008505  mov     rax, [rax+8]
0x180008509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000850e  xor     eax, eax
0x180008510  mov     [rsi], rbx
0x180008513  jmp     short loc_180008591
0x180008515  cmp     qword ptr [rdx+10h], 0
0x18000851a  jz      short loc_18000857C
0x18000851c  mov     rcx, [rbx]
0x18000851f  test    rcx, rcx
0x180008522  jnz     short loc_180008529
0x180008524  lea     ebp, [rcx+1]
0x180008527  jmp     short loc_180008549
0x180008529  mov     eax, [rdi]
0x18000852b  cmp     [rcx], eax
0x18000852d  jnz     short loc_180008571
0x18000852f  mov     eax, [rdi+4]
0x180008532  cmp     [rcx+4], eax
0x180008535  jnz     short loc_180008571
0x180008537  mov     eax, [rdi+8]
0x18000853a  cmp     [rcx+8], eax
0x18000853d  jnz     short loc_180008571
0x18000853f  mov     eax, [rdi+0Ch]
0x180008542  cmp     [rcx+0Ch], eax
0x180008545  jnz     short loc_180008571
0x180008547  xor     ebp, ebp
0x180008549  mov     rax, [rbx+10h]
0x18000854d  cmp     rax, 1
0x180008551  jz      short loc_180008583
0x180008553  mov     r9, [rbx+8]
0x180008557  mov     r8, rsi
0x18000855a  mov     rdx, rdi
0x18000855d  mov     rcx, r14
0x180008560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008565  test    eax, eax
0x180008567  jz      short loc_180008591
0x180008569  test    ebp, ebp
0x18000856b  jnz     short loc_180008571
0x18000856d  test    eax, eax
0x18000856f  js      short loc_180008591
0x180008571  add     rbx, 18h
0x180008575  cmp     qword ptr [rbx+10h], 0
0x18000857a  jnz     short loc_18000851C
0x18000857c  mov     eax, 80004002h
0x180008581  jmp     short loc_180008591
0x180008583  mov     rbx, [rbx+8]
0x180008587  jmp     loc_1800084FC
0x18000858c  mov     eax, 80070057h
0x180008591  add     rsp, 30h
0x180008595  pop     r14
0x180008597  pop     rdi
0x180008598  pop     rsi
0x180008599  pop     rbp
0x18000859a  pop     rbx
0x18000859b  retn
```
