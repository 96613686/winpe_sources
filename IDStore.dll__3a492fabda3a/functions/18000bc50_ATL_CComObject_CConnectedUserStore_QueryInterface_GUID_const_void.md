# ATL::CComObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000bc50`
- end: `0x18000bd75`
- name: `?QueryInterface@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011860`
- `0x180011a10`

## callees

- `0x18000bc50`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::QueryInterface(char *a1, _DWORD *a2, char **a3)
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
    for ( i = &`CConnectedUserStore::_GetEntries'::`2'::_entries; ; i += 3 )
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
0x18000bc50  push    rbx
0x18000bc52  push    rbp
0x18000bc53  push    rsi
0x18000bc54  push    rdi
0x18000bc55  push    r14
0x18000bc57  sub     rsp, 30h
0x18000bc5b  mov     rsi, r8
0x18000bc5e  mov     rdi, rdx
0x18000bc61  mov     r14, rcx
0x18000bc64  test    rcx, rcx
0x18000bc67  jz      loc_18000BD6B
0x18000bc6d  test    r8, r8
0x18000bc70  jz      loc_18000BD30
0x18000bc76  mov     qword ptr [r8], 0
0x18000bc7d  cmp     dword ptr [rdx], 0
0x18000bc80  jz      short loc_18000BCF4
0x18000bc82  lea     rbx, ?_entries@?1??_GetEntries@CConnectedUserStore@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CConnectedUserStore::_GetEntries(void)'::`2'::_entries
0x18000bc89  mov     r10, [rbx+10h]
0x18000bc8d  test    r10, r10
0x18000bc90  jz      loc_18000BD61
0x18000bc96  mov     rcx, [rbx]
0x18000bc99  test    rcx, rcx
0x18000bc9c  jz      loc_18000BD37
0x18000bca2  mov     eax, [rdi]
0x18000bca4  cmp     [rcx], eax
0x18000bca6  jnz     short loc_18000BCEE
0x18000bca8  mov     eax, [rdi+4]
0x18000bcab  cmp     [rcx+4], eax
0x18000bcae  jnz     short loc_18000BCEE
0x18000bcb0  mov     eax, [rdi+8]
0x18000bcb3  cmp     [rcx+8], eax
0x18000bcb6  jnz     short loc_18000BCEE
0x18000bcb8  mov     eax, [rdi+0Ch]
0x18000bcbb  cmp     [rcx+0Ch], eax
0x18000bcbe  jnz     short loc_18000BCEE
0x18000bcc0  xor     ebp, ebp
0x18000bcc2  cmp     r10, 1
0x18000bcc6  jnz     short loc_18000BD3E
0x18000bcc8  mov     rbx, [rbx+8]
0x18000bccc  add     rbx, r14
0x18000bccf  mov     rax, [rbx]
0x18000bcd2  mov     rcx, rbx
0x18000bcd5  mov     rax, [rax+8]
0x18000bcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcde  mov     [rsi], rbx
0x18000bce1  xor     eax, eax
0x18000bce3  add     rsp, 30h
0x18000bce7  pop     r14
0x18000bce9  pop     rdi
0x18000bcea  pop     rsi
0x18000bceb  pop     rbp
0x18000bcec  pop     rbx
0x18000bced  retn
0x18000bcee  add     rbx, 18h
0x18000bcf2  jmp     short loc_18000BC89
0x18000bcf4  cmp     dword ptr [rdx+4], 0
0x18000bcf8  jnz     short loc_18000BC82
0x18000bcfa  cmp     dword ptr [rdx+8], 0C0h
0x18000bd01  jnz     loc_18000BC82
0x18000bd07  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000bd0e  jnz     loc_18000BC82
0x18000bd14  mov     rax, [rcx]
0x18000bd17  mov     rax, [rax+8]
0x18000bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd20  mov     [rsi], r14
0x18000bd23  xor     eax, eax
0x18000bd25  add     rsp, 30h
0x18000bd29  pop     r14
0x18000bd2b  pop     rdi
0x18000bd2c  pop     rsi
0x18000bd2d  pop     rbp
0x18000bd2e  pop     rbx
0x18000bd2f  retn
0x18000bd30  mov     eax, 80004003h
0x18000bd35  jmp     short loc_18000BCE3
0x18000bd37  mov     ebp, 1
0x18000bd3c  jmp     short loc_18000BCC2
0x18000bd3e  mov     r9, [rbx+8]
0x18000bd42  mov     r8, rsi
0x18000bd45  mov     rdx, rdi
0x18000bd48  mov     rcx, r14
0x18000bd4b  mov     rax, r10
0x18000bd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd53  test    eax, eax
0x18000bd55  jz      short loc_18000BCE3
0x18000bd57  test    ebp, ebp
0x18000bd59  jnz     short loc_18000BCEE
0x18000bd5b  test    eax, eax
0x18000bd5d  js      short loc_18000BCE3
0x18000bd5f  jmp     short loc_18000BCEE
0x18000bd61  mov     eax, 80004002h
0x18000bd66  jmp     loc_18000BCE3
0x18000bd6b  mov     eax, 80070057h
0x18000bd70  jmp     loc_18000BCE3
```
