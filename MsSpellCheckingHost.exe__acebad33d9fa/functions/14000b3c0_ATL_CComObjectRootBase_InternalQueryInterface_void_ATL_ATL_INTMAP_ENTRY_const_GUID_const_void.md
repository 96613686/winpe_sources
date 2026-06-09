# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x14000b3c0`
- end: `0x14000b4c4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000bdd0`
- `0x140010120`
- `0x140010740`
- `0x140010760`
- `0x140010780`

## callees

- `0x14000b3c0`
- `0x140013010`

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
0x14000b3c0  push    rbx
0x14000b3c2  push    rbp
0x14000b3c3  push    rsi
0x14000b3c4  push    rdi
0x14000b3c5  push    r14
0x14000b3c7  sub     rsp, 30h
0x14000b3cb  mov     rsi, r9
0x14000b3ce  mov     rdi, r8
0x14000b3d1  mov     rbx, rdx
0x14000b3d4  mov     r14, rcx
0x14000b3d7  test    rcx, rcx
0x14000b3da  jz      loc_14000B4B4
0x14000b3e0  test    rdx, rdx
0x14000b3e3  jz      loc_14000B4B4
0x14000b3e9  test    r9, r9
0x14000b3ec  jnz     short loc_14000B3F8
0x14000b3ee  mov     eax, 80004003h
0x14000b3f3  jmp     loc_14000B4B9
0x14000b3f8  mov     qword ptr [r9], 0
0x14000b3ff  cmp     dword ptr [r8], 0
0x14000b403  jnz     short loc_14000B43D
0x14000b405  cmp     dword ptr [r8+4], 0
0x14000b40a  jnz     short loc_14000B43D
0x14000b40c  cmp     dword ptr [r8+8], 0C0h
0x14000b414  jnz     short loc_14000B43D
0x14000b416  cmp     dword ptr [r8+0Ch], 46000000h
0x14000b41e  jnz     short loc_14000B43D
0x14000b420  mov     rbx, [rdx+8]
0x14000b424  add     rbx, r14
0x14000b427  mov     rcx, rbx
0x14000b42a  mov     rax, [rbx]
0x14000b42d  mov     rax, [rax+8]
0x14000b431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b436  xor     eax, eax
0x14000b438  mov     [rsi], rbx
0x14000b43b  jmp     short loc_14000B4B9
0x14000b43d  cmp     qword ptr [rdx+10h], 0
0x14000b442  jz      short loc_14000B4A4
0x14000b444  mov     rcx, [rbx]
0x14000b447  test    rcx, rcx
0x14000b44a  jnz     short loc_14000B451
0x14000b44c  lea     ebp, [rcx+1]
0x14000b44f  jmp     short loc_14000B471
0x14000b451  mov     eax, [rdi]
0x14000b453  cmp     [rcx], eax
0x14000b455  jnz     short loc_14000B499
0x14000b457  mov     eax, [rdi+4]
0x14000b45a  cmp     [rcx+4], eax
0x14000b45d  jnz     short loc_14000B499
0x14000b45f  mov     eax, [rdi+8]
0x14000b462  cmp     [rcx+8], eax
0x14000b465  jnz     short loc_14000B499
0x14000b467  mov     eax, [rdi+0Ch]
0x14000b46a  cmp     [rcx+0Ch], eax
0x14000b46d  jnz     short loc_14000B499
0x14000b46f  xor     ebp, ebp
0x14000b471  mov     rax, [rbx+10h]
0x14000b475  cmp     rax, 1
0x14000b479  jz      short loc_14000B4AB
0x14000b47b  mov     r9, [rbx+8]
0x14000b47f  mov     r8, rsi
0x14000b482  mov     rdx, rdi
0x14000b485  mov     rcx, r14
0x14000b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b48d  test    eax, eax
0x14000b48f  jz      short loc_14000B4B9
0x14000b491  test    ebp, ebp
0x14000b493  jnz     short loc_14000B499
0x14000b495  test    eax, eax
0x14000b497  js      short loc_14000B4B9
0x14000b499  add     rbx, 18h
0x14000b49d  cmp     qword ptr [rbx+10h], 0
0x14000b4a2  jnz     short loc_14000B444
0x14000b4a4  mov     eax, 80004002h
0x14000b4a9  jmp     short loc_14000B4B9
0x14000b4ab  mov     rbx, [rbx+8]
0x14000b4af  jmp     loc_14000B424
0x14000b4b4  mov     eax, 80070057h
0x14000b4b9  add     rsp, 30h
0x14000b4bd  pop     r14
0x14000b4bf  pop     rdi
0x14000b4c0  pop     rsi
0x14000b4c1  pop     rbp
0x14000b4c2  pop     rbx
0x14000b4c3  retn
```
