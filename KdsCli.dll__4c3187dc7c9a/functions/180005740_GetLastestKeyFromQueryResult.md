# GetLastestKeyFromQueryResult

- ea: `0x180005740`
- end: `0x180005899`
- name: `GetLastestKeyFromQueryResult`
- size: `345`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800058a0`

## callees

- `0x180003e08`
- `0x180003e30`
- `0x180004e20`
- `0x180005740`
- `0x180005a24`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_first_entry` at `0x180005755`
- `WLDAP32!__imp_ldap_first_entry` at `0x180005755`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800057c8`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800057c8`

## string_xrefs

- `0x18000581c`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180005841`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall GetLastestKeyFromQueryResult(LDAP *ld, LDAPMessage *a2, struct _ROOT_KEY_HEADER **a3)
{
  struct _ROOT_KEY_HEADER *v5; // rdi
  LDAPMessage *entry; // rbp
  unsigned int v7; // ebx
  unsigned __int64 v8; // rsi
  signed int v9; // eax
  struct _ROOT_KEY_HEADER *lpMem; // [rsp+70h] [rbp+18h] BYREF

  v5 = 0;
  entry = ldap_first_entry(ld, a2);
  if ( entry )
  {
    v8 = 0;
    while ( 1 )
    {
      lpMem = 0;
      v9 = ParseRootKey(ld, entry, &lpMem);
      v7 = v9;
      if ( v9 < 0 )
        break;
      entry = ldap_next_entry(ld, entry);
      if ( v8 )
      {
        if ( *((_QWORD *)lpMem + 16) <= v8 )
        {
          FreeRootKey(lpMem);
        }
        else
        {
          v8 = *((_QWORD *)lpMem + 16);
          FreeRootKey(v5);
          v5 = lpMem;
        }
      }
      else
      {
        v5 = lpMem;
        v8 = *((_QWORD *)lpMem + 16);
      }
      if ( !entry )
      {
        if ( !v5 )
        {
          v7 = -2147024864;
          SidKeyDebugTraceError(
            0x80070020,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
            0x4D7u);
        }
        goto LABEL_18;
      }
    }
    SidKeyDebugTraceError(v9, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x4B8u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v7);
  }
  else
  {
    v7 = -2147024864;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids);
  }
LABEL_18:
  *a3 = v5;
  return v7;
}

```

## disassembly

```asm
0x180005740  push    rbx
0x180005742  push    rbp
0x180005743  push    rsi
0x180005744  push    rdi
0x180005745  push    r14
0x180005747  push    r15
0x180005749  sub     rsp, 28h
0x18000574d  mov     r15, r8
0x180005750  mov     r14, rcx
0x180005753  xor     edi, edi
0x180005755  call    cs:__imp_ldap_first_entry
0x18000575b  mov     rbp, rax
0x18000575e  test    rax, rax
0x180005761  jnz     short loc_1800057A1
0x180005763  mov     ebx, 80070020h
0x180005768  mov     rcx, cs:WPP_GLOBAL_Control
0x18000576f  lea     rax, WPP_GLOBAL_Control
0x180005776  cmp     rcx, rax
0x180005779  jz      loc_180005887
0x18000577f  test    byte ptr [rcx+1Ch], 4
0x180005783  jz      loc_180005887
0x180005789  mov     rcx, [rcx+10h]
0x18000578d  lea     edx, [rdi+1Dh]
0x180005790  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x180005797  call    WPP_SF_
0x18000579c  jmp     loc_180005887
0x1800057a1  xor     esi, esi
0x1800057a3  lea     r8, [rsp+58h+lpMem]
0x1800057a8  mov     [rsp+58h+lpMem], 0
0x1800057b1  mov     rdx, rbp; entry
0x1800057b4  mov     rcx, r14; ld
0x1800057b7  call    ParseRootKey
0x1800057bc  mov     ebx, eax
0x1800057be  test    eax, eax
0x1800057c0  js      short loc_18000583B
0x1800057c2  mov     rdx, rbp; entry
0x1800057c5  mov     rcx, r14; ld
0x1800057c8  call    cs:__imp_ldap_next_entry
0x1800057ce  mov     rbp, rax
0x1800057d1  test    rsi, rsi
0x1800057d4  jnz     short loc_1800057E4
0x1800057d6  mov     rdi, [rsp+58h+lpMem]
0x1800057db  mov     rsi, [rdi+80h]
0x1800057e2  jmp     short loc_18000580C
0x1800057e4  mov     rcx, [rsp+58h+lpMem]; lpMem
0x1800057e9  mov     rax, [rcx+80h]
0x1800057f0  cmp     rax, rsi
0x1800057f3  jbe     short loc_180005807
0x1800057f5  mov     rcx, rdi; lpMem
0x1800057f8  mov     rsi, rax
0x1800057fb  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x180005800  mov     rdi, [rsp+58h+lpMem]
0x180005805  jmp     short loc_18000580C
0x180005807  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x18000580c  test    rbp, rbp
0x18000580f  jnz     short loc_1800057A3
0x180005811  test    rdi, rdi
0x180005814  jnz     short loc_180005887
0x180005816  mov     r9d, 4D7h; unsigned int
0x18000581c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005823  lea     rdx, aHr; "hr"
0x18000582a  mov     ecx, 80070020h; unsigned int
0x18000582f  mov     ebx, 80070020h
0x180005834  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005839  jmp     short loc_180005887
0x18000583b  mov     r9d, 4B8h; unsigned int
0x180005841  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005848  lea     rdx, aHr; "hr"
0x18000584f  mov     ecx, ebx; unsigned int
0x180005851  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005856  mov     rcx, cs:WPP_GLOBAL_Control
0x18000585d  lea     rax, WPP_GLOBAL_Control
0x180005864  cmp     rcx, rax
0x180005867  jz      short loc_180005887
0x180005869  test    byte ptr [rcx+1Ch], 1
0x18000586d  jz      short loc_180005887
0x18000586f  mov     rcx, [rcx+10h]
0x180005873  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x18000587a  mov     edx, 1Eh
0x18000587f  mov     r9d, ebx
0x180005882  call    WPP_SF_D
0x180005887  mov     [r15], rdi
0x18000588a  mov     eax, ebx
0x18000588c  add     rsp, 28h
0x180005890  pop     r15
0x180005892  pop     r14
0x180005894  pop     rdi
0x180005895  pop     rsi
0x180005896  pop     rbp
0x180005897  pop     rbx
0x180005898  retn
```
