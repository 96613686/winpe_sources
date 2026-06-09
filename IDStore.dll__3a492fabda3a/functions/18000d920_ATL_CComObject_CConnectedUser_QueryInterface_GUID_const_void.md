# ATL::CComObject<CConnectedUser>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000d920`
- end: `0x18000da45`
- name: `?QueryInterface@?$CComObject@VCConnectedUser@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d920`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUser>::QueryInterface(char *a1, _DWORD *a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  char *v10; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = 0;
    if ( !*a2 && !a2[1] && a2[2] == 192 && a2[3] == 1174405120 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
      *a3 = a1;
      return 0;
    }
    for ( i = &`CConnectedUser::_GetEntries'::`2'::_entries; ; i += 3 )
    {
      v7 = i[2];
      if ( !v7 )
        return 2147500034LL;
      v8 = *i;
      if ( *i )
      {
        if ( v8->Data1 != *a2
          || *(_DWORD *)&v8->Data2 != a2[1]
          || *(_DWORD *)v8->Data4 != a2[2]
          || *(_DWORD *)&v8->Data4[4] != a2[3] )
        {
          continue;
        }
        v9 = 0;
      }
      else
      {
        v9 = 1;
      }
      if ( v7 == (GUID *)1 )
      {
        v10 = (char *)i[1] + (_QWORD)a1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
        *a3 = v10;
        return 0;
      }
      result = ((__int64 (__fastcall *)(char *, _DWORD *, char **, GUID *))i[2])(a1, a2, a3, i[1]);
      if ( !(_DWORD)result || !v9 && (int)result < 0 )
        return result;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d920  push    rbx
0x18000d922  push    rbp
0x18000d923  push    rsi
0x18000d924  push    rdi
0x18000d925  push    r14
0x18000d927  sub     rsp, 30h
0x18000d92b  mov     rsi, r8
0x18000d92e  mov     rdi, rdx
0x18000d931  mov     r14, rcx
0x18000d934  test    rcx, rcx
0x18000d937  jz      loc_18000DA3B
0x18000d93d  test    r8, r8
0x18000d940  jz      loc_18000DA00
0x18000d946  mov     qword ptr [r8], 0
0x18000d94d  cmp     dword ptr [rdx], 0
0x18000d950  jz      short loc_18000D9C4
0x18000d952  lea     rbx, ?_entries@?1??_GetEntries@CConnectedUser@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CConnectedUser::_GetEntries(void)'::`2'::_entries
0x18000d959  mov     r10, [rbx+10h]
0x18000d95d  test    r10, r10
0x18000d960  jz      loc_18000DA31
0x18000d966  mov     rcx, [rbx]
0x18000d969  test    rcx, rcx
0x18000d96c  jz      loc_18000DA07
0x18000d972  mov     eax, [rdi]
0x18000d974  cmp     [rcx], eax
0x18000d976  jnz     short loc_18000D9BE
0x18000d978  mov     eax, [rdi+4]
0x18000d97b  cmp     [rcx+4], eax
0x18000d97e  jnz     short loc_18000D9BE
0x18000d980  mov     eax, [rdi+8]
0x18000d983  cmp     [rcx+8], eax
0x18000d986  jnz     short loc_18000D9BE
0x18000d988  mov     eax, [rdi+0Ch]
0x18000d98b  cmp     [rcx+0Ch], eax
0x18000d98e  jnz     short loc_18000D9BE
0x18000d990  xor     ebp, ebp
0x18000d992  cmp     r10, 1
0x18000d996  jnz     short loc_18000DA0E
0x18000d998  mov     rbx, [rbx+8]
0x18000d99c  add     rbx, r14
0x18000d99f  mov     rax, [rbx]
0x18000d9a2  mov     rcx, rbx
0x18000d9a5  mov     rax, [rax+8]
0x18000d9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9ae  mov     [rsi], rbx
0x18000d9b1  xor     eax, eax
0x18000d9b3  add     rsp, 30h
0x18000d9b7  pop     r14
0x18000d9b9  pop     rdi
0x18000d9ba  pop     rsi
0x18000d9bb  pop     rbp
0x18000d9bc  pop     rbx
0x18000d9bd  retn
0x18000d9be  add     rbx, 18h
0x18000d9c2  jmp     short loc_18000D959
0x18000d9c4  cmp     dword ptr [rdx+4], 0
0x18000d9c8  jnz     short loc_18000D952
0x18000d9ca  cmp     dword ptr [rdx+8], 0C0h
0x18000d9d1  jnz     loc_18000D952
0x18000d9d7  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000d9de  jnz     loc_18000D952
0x18000d9e4  mov     rax, [rcx]
0x18000d9e7  mov     rax, [rax+8]
0x18000d9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9f0  mov     [rsi], r14
0x18000d9f3  xor     eax, eax
0x18000d9f5  add     rsp, 30h
0x18000d9f9  pop     r14
0x18000d9fb  pop     rdi
0x18000d9fc  pop     rsi
0x18000d9fd  pop     rbp
0x18000d9fe  pop     rbx
0x18000d9ff  retn
0x18000da00  mov     eax, 80004003h
0x18000da05  jmp     short loc_18000D9B3
0x18000da07  mov     ebp, 1
0x18000da0c  jmp     short loc_18000D992
0x18000da0e  mov     r9, [rbx+8]
0x18000da12  mov     r8, rsi
0x18000da15  mov     rdx, rdi
0x18000da18  mov     rcx, r14
0x18000da1b  mov     rax, r10
0x18000da1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da23  test    eax, eax
0x18000da25  jz      short loc_18000D9B3
0x18000da27  test    ebp, ebp
0x18000da29  jnz     short loc_18000D9BE
0x18000da2b  test    eax, eax
0x18000da2d  js      short loc_18000D9B3
0x18000da2f  jmp     short loc_18000D9BE
0x18000da31  mov     eax, 80004002h
0x18000da36  jmp     loc_18000D9B3
0x18000da3b  mov     eax, 80070057h
0x18000da40  jmp     loc_18000D9B3
```
