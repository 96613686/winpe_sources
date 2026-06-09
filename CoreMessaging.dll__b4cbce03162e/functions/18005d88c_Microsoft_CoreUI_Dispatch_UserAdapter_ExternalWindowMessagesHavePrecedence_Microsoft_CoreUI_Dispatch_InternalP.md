# Microsoft::CoreUI::Dispatch::UserAdapter::ExternalWindowMessagesHavePrecedence(Microsoft::CoreUI::Dispatch::InternalPriority,int)

- ea: `0x18005d88c`
- end: `0x18005d947`
- name: `?ExternalWindowMessagesHavePrecedence@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAA_NW4InternalPriority@234@H@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005cf60`

## callees

- `0x18005d88c`
- `0x18008ae1c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18005d8df`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x18005d8df`

## pseudocode

```c
char __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::ExternalWindowMessagesHavePrecedence(
        __int64 a1,
        int a2,
        __int16 a3)
{
  int v3; // r9d
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  bool v10; // zf
  bool v11; // sf
  bool v12; // of
  char result; // al
  unsigned int v14; // ecx
  __int16 v15; // dx
  __int16 v16; // ax
  bool v17; // zf
  bool v18; // sf
  bool v19; // of

  v3 = *(_DWORD *)(a1 + 48);
  if ( !v3 || *(_BYTE *)(a1 + 80) )
    return 0;
  v6 = v3 - 1;
  if ( v6 && (v7 = v6 - 1) != 0 && (v8 = v7 - 1) != 0 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        CFlat::Abandonment::Fail((const char16_t *)a1);
      v12 = __OFSUB__(a2, 10);
      v10 = a2 == 10;
      v11 = a2 - 10 < 0;
    }
    else
    {
      v12 = __OFSUB__(a2, 6);
      v10 = a2 == 6;
      v11 = a2 - 6 < 0;
    }
    result = v11 ^ v12 | v10;
  }
  else
  {
    result = 0;
  }
  if ( !result && *(_BYTE *)(a1 + 77) )
  {
    v14 = (unsigned int)GetQueueStatusReadonly(7423) >> 16;
    v15 = v14 & 0xFFBF;
    if ( (a3 & 0x2000) != 0 )
      v15 = v14;
    v16 = v15 & 0xE370;
    if ( (a3 & 0x80u) != 0 )
      v16 = v15;
    if ( (v16 & 0x40) != 0 )
    {
      v19 = __OFSUB__(a2, 10);
      v17 = a2 == 10;
      v18 = a2 - 10 < 0;
    }
    else if ( (v16 & 8) != 0 )
    {
      v19 = __OFSUB__(a2, 6);
      v17 = a2 == 6;
      v18 = a2 - 6 < 0;
    }
    else
    {
      if ( (v16 & 0x1C87) == 0 )
        return 0;
      v19 = __OFSUB__(a2, 4);
      v17 = a2 == 4;
      v18 = a2 - 4 < 0;
    }
    return v18 ^ v19 | v17;
  }
  return result;
}

```

## disassembly

```asm
0x18005d88c  mov     [rsp+arg_0], rbx
0x18005d891  push    rdi
0x18005d892  sub     rsp, 20h
0x18005d896  mov     r9d, [rcx+30h]
0x18005d89a  mov     edi, r8d
0x18005d89d  mov     ebx, edx
0x18005d89f  test    r9d, r9d
0x18005d8a2  jz      short loc_18005D913
0x18005d8a4  cmp     byte ptr [rcx+50h], 0
0x18005d8a8  jnz     short loc_18005D913
0x18005d8aa  test    r9d, r9d
0x18005d8ad  jz      loc_18005D941
0x18005d8b3  sub     r9d, 1
0x18005d8b7  jz      short loc_18005D920
0x18005d8b9  sub     r9d, 1
0x18005d8bd  jz      short loc_18005D920
0x18005d8bf  sub     r9d, 1
0x18005d8c3  jz      short loc_18005D920
0x18005d8c5  sub     r9d, 1
0x18005d8c9  jnz     short loc_18005D936
0x18005d8cb  cmp     edx, 6
0x18005d8ce  setle   al
0x18005d8d1  test    al, al
0x18005d8d3  jnz     short loc_18005D915
0x18005d8d5  cmp     [rcx+4Dh], al
0x18005d8d8  jz      short loc_18005D915
0x18005d8da  mov     ecx, 1CFFh
0x18005d8df  call    cs:__imp_GetQueueStatusReadonly
0x18005d8e5  mov     ecx, eax
0x18005d8e7  shr     ecx, 10h; char16_t *
0x18005d8ea  mov     edx, ecx
0x18005d8ec  and     edx, 0FFFFFFBFh
0x18005d8ef  bt      edi, 0Dh
0x18005d8f3  cmovb   edx, ecx
0x18005d8f6  mov     eax, edx
0x18005d8f8  and     eax, 0FFFFE370h
0x18005d8fd  test    dil, 80h
0x18005d901  cmovnz  eax, edx
0x18005d904  test    al, 40h
0x18005d906  jnz     short loc_18005D924
0x18005d908  test    al, 8
0x18005d90a  jnz     short loc_18005D92C
0x18005d90c  test    eax, 1C87h
0x18005d911  jnz     short loc_18005D931
0x18005d913  xor     al, al
0x18005d915  mov     rbx, [rsp+28h+arg_0]
0x18005d91a  add     rsp, 20h
0x18005d91e  pop     rdi
0x18005d91f  retn
0x18005d920  xor     al, al
0x18005d922  jmp     short loc_18005D8D1
0x18005d924  cmp     ebx, 0Ah
0x18005d927  setle   al
0x18005d92a  jmp     short loc_18005D915
0x18005d92c  cmp     ebx, 6
0x18005d92f  jmp     short loc_18005D927
0x18005d931  cmp     ebx, 4
0x18005d934  jmp     short loc_18005D927
0x18005d936  cmp     r9d, 1
0x18005d93a  jnz     short loc_18005D941
0x18005d93c  cmp     ebx, 0Ah
0x18005d93f  jmp     short loc_18005D8CE
0x18005d941  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
```
