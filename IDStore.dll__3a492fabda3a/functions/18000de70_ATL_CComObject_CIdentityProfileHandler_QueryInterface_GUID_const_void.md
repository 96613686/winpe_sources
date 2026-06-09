# ATL::CComObject<CIdentityProfileHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000de70`
- end: `0x18000df87`
- name: `?QueryInterface@?$CComObject@VCIdentityProfileHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `279`
- prototype: `__int64 __fastcall(char *, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000de70`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityProfileHandler>::QueryInterface(char *a1, _DWORD *a2, char **a3)
{
  GUID **i; // rdi
  GUID *v7; // r10
  GUID *v8; // rcx
  int v9; // ebp
  char *v10; // rbx
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    for ( i = &`CIdentityProfileHandler::_GetEntries'::`2'::_entries; ; i += 3 )
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
  (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  *a3 = a1;
  return 0;
}

```

## disassembly

```asm
0x18000de70  push    rbx
0x18000de72  push    rbp
0x18000de73  push    rsi
0x18000de74  push    rdi
0x18000de75  push    r14
0x18000de77  sub     rsp, 30h
0x18000de7b  mov     r14, r8
0x18000de7e  mov     rbx, rdx
0x18000de81  mov     rsi, rcx
0x18000de84  test    rcx, rcx
0x18000de87  jz      loc_18000DF7D
0x18000de8d  test    r8, r8
0x18000de90  jz      loc_18000DF45
0x18000de96  mov     qword ptr [r8], 0
0x18000de9d  cmp     dword ptr [rdx], 0
0x18000dea0  jz      short loc_18000DF14
0x18000dea2  lea     rdi, ?_entries@?1??_GetEntries@CIdentityProfileHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIdentityProfileHandler::_GetEntries(void)'::`2'::_entries
0x18000dea9  mov     r10, [rdi+10h]
0x18000dead  test    r10, r10
0x18000deb0  jz      loc_18000DF76
0x18000deb6  mov     rcx, [rdi]
0x18000deb9  test    rcx, rcx
0x18000debc  jz      loc_18000DF4C
0x18000dec2  mov     eax, [rbx]
0x18000dec4  cmp     [rcx], eax
0x18000dec6  jnz     short loc_18000DF0E
0x18000dec8  mov     eax, [rbx+4]
0x18000decb  cmp     [rcx+4], eax
0x18000dece  jnz     short loc_18000DF0E
0x18000ded0  mov     eax, [rbx+8]
0x18000ded3  cmp     [rcx+8], eax
0x18000ded6  jnz     short loc_18000DF0E
0x18000ded8  mov     eax, [rbx+0Ch]
0x18000dedb  cmp     [rcx+0Ch], eax
0x18000dede  jnz     short loc_18000DF0E
0x18000dee0  xor     ebp, ebp
0x18000dee2  cmp     r10, 1
0x18000dee6  jnz     short loc_18000DF53
0x18000dee8  mov     rbx, [rdi+8]
0x18000deec  add     rbx, rsi
0x18000deef  mov     rax, [rbx]
0x18000def2  mov     rcx, rbx
0x18000def5  mov     rax, [rax+8]
0x18000def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defe  mov     [r14], rbx
0x18000df01  xor     eax, eax
0x18000df03  add     rsp, 30h
0x18000df07  pop     r14
0x18000df09  pop     rdi
0x18000df0a  pop     rsi
0x18000df0b  pop     rbp
0x18000df0c  pop     rbx
0x18000df0d  retn
0x18000df0e  add     rdi, 18h
0x18000df12  jmp     short loc_18000DEA9
0x18000df14  cmp     dword ptr [rdx+4], 0
0x18000df18  jnz     short loc_18000DEA2
0x18000df1a  cmp     dword ptr [rdx+8], 0C0h
0x18000df21  jnz     loc_18000DEA2
0x18000df27  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000df2e  jnz     loc_18000DEA2
0x18000df34  mov     rax, [rcx]
0x18000df37  mov     rax, [rax+8]
0x18000df3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df40  mov     [r14], rsi
0x18000df43  jmp     short loc_18000DF01
0x18000df45  mov     eax, 80004003h
0x18000df4a  jmp     short loc_18000DF03
0x18000df4c  mov     ebp, 1
0x18000df51  jmp     short loc_18000DEE2
0x18000df53  mov     r9, [rdi+8]
0x18000df57  mov     r8, r14
0x18000df5a  mov     rdx, rbx
0x18000df5d  mov     rcx, rsi
0x18000df60  mov     rax, r10
0x18000df63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df68  test    eax, eax
0x18000df6a  jz      short loc_18000DF03
0x18000df6c  test    ebp, ebp
0x18000df6e  jnz     short loc_18000DF0E
0x18000df70  test    eax, eax
0x18000df72  js      short loc_18000DF03
0x18000df74  jmp     short loc_18000DF0E
0x18000df76  mov     eax, 80004002h
0x18000df7b  jmp     short loc_18000DF03
0x18000df7d  mov     eax, 80070057h
0x18000df82  jmp     loc_18000DF03
```
