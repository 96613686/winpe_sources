# ATL::CComObject<CIconOverlayHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003200`
- end: `0x1800032fd`
- name: `?QueryInterface@?$CComObject@VCIconOverlayHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003200`
- `0x180003310`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIconOverlayHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  GUID **i; // rbx
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  __int64 result; // rax
  char *v11; // rbx

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)ATL::InlineIsEqualUnknown((const struct _GUID *)a2) )
  {
    for ( i = &`CIconOverlayHandler::_GetEntries'::`2'::_entries; ; i += 3 )
    {
      v7 = i[2];
      if ( !v7 )
        return 2147500034LL;
      v8 = *i;
      if ( *i )
      {
        if ( v8->Data1 != *(_DWORD *)a2
          || *(_DWORD *)&v8->Data2 != *(_DWORD *)(a2 + 4)
          || *(_DWORD *)v8->Data4 != *(_DWORD *)(a2 + 8)
          || *(_DWORD *)&v8->Data4[4] != *(_DWORD *)(a2 + 12) )
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
        v11 = (char *)i[1] + (_QWORD)a1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
        *a3 = v11;
        return 0;
      }
      result = ((__int64 (__fastcall *)(char *, __int64, char **, GUID *))i[2])(a1, a2, a3, i[1]);
      if ( !(_DWORD)result || !v9 && (int)result < 0 )
        return result;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  *a3 = a1;
  return 0;
}

```

## disassembly

```asm
0x180003200  push    rbx
0x180003202  push    rbp
0x180003203  push    rsi
0x180003204  push    rdi
0x180003205  push    r14
0x180003207  sub     rsp, 30h
0x18000320b  mov     r14, r8
0x18000320e  mov     rdi, rdx
0x180003211  mov     rsi, rcx
0x180003214  test    rcx, rcx
0x180003217  jz      loc_1800032F6
0x18000321d  test    r8, r8
0x180003220  jz      loc_1800032B1
0x180003226  mov     qword ptr [r8], 0
0x18000322d  mov     rcx, rdx; struct _GUID *
0x180003230  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180003235  test    eax, eax
0x180003237  jnz     short loc_1800032B8
0x180003239  lea     rbx, ?_entries@?1??_GetEntries@CIconOverlayHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIconOverlayHandler::_GetEntries(void)'::`2'::_entries
0x180003240  mov     r10, [rbx+10h]
0x180003244  test    r10, r10
0x180003247  jz      short loc_180003279
0x180003249  mov     rcx, [rbx]
0x18000324c  test    rcx, rcx
0x18000324f  jz      short loc_180003280
0x180003251  mov     eax, [rdi]
0x180003253  cmp     [rcx], eax
0x180003255  jz      short loc_18000325D
0x180003257  add     rbx, 18h
0x18000325b  jmp     short loc_180003240
0x18000325d  mov     eax, [rdi+4]
0x180003260  cmp     [rcx+4], eax
0x180003263  jnz     short loc_180003257
0x180003265  mov     eax, [rdi+8]
0x180003268  cmp     [rcx+8], eax
0x18000326b  jnz     short loc_180003257
0x18000326d  mov     eax, [rdi+0Ch]
0x180003270  cmp     [rcx+0Ch], eax
0x180003273  jnz     short loc_180003257
0x180003275  xor     ebp, ebp
0x180003277  jmp     short loc_180003285
0x180003279  mov     eax, 80004002h
0x18000327e  jmp     short loc_1800032A6
0x180003280  mov     ebp, 1
0x180003285  cmp     r10, 1
0x180003289  jnz     short loc_1800032CC
0x18000328b  mov     rbx, [rbx+8]
0x18000328f  add     rbx, rsi
0x180003292  mov     rax, [rbx]
0x180003295  mov     rcx, rbx
0x180003298  mov     rax, [rax+8]
0x18000329c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a1  mov     [r14], rbx
0x1800032a4  xor     eax, eax
0x1800032a6  add     rsp, 30h
0x1800032aa  pop     r14
0x1800032ac  pop     rdi
0x1800032ad  pop     rsi
0x1800032ae  pop     rbp
0x1800032af  pop     rbx
0x1800032b0  retn
0x1800032b1  mov     eax, 80004003h
0x1800032b6  jmp     short loc_1800032A6
0x1800032b8  mov     rax, [rsi]
0x1800032bb  mov     rcx, rsi
0x1800032be  mov     rax, [rax+8]
0x1800032c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c7  mov     [r14], rsi
0x1800032ca  jmp     short loc_1800032A4
0x1800032cc  mov     r9, [rbx+8]
0x1800032d0  mov     r8, r14
0x1800032d3  mov     rdx, rdi
0x1800032d6  mov     rcx, rsi
0x1800032d9  mov     rax, r10
0x1800032dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e1  test    eax, eax
0x1800032e3  jz      short loc_1800032A6
0x1800032e5  test    ebp, ebp
0x1800032e7  jnz     loc_180003257
0x1800032ed  test    eax, eax
0x1800032ef  js      short loc_1800032A6
0x1800032f1  jmp     loc_180003257
0x1800032f6  mov     eax, 80070057h
0x1800032fb  jmp     short loc_1800032A6
```
