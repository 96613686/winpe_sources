# TsiFreeActionAccountInfoSecurityParameters(_UBPM_ACTION_ACCOUNT_INFO *)

- ea: `0x18000e2c0`
- end: `0x18000e341`
- name: `?TsiFreeActionAccountInfoSecurityParameters@@YAXPEAU_UBPM_ACTION_ACCOUNT_INFO@@@Z`
- size: `129`
- prototype: `void __fastcall(struct _UBPM_ACTION_ACCOUNT_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a7d8`
- `0x18001aba0`

## callees

- `0x18000e2c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e2e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e2e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e2da`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e2f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e316`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e32b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e2da`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e2f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e316`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e32b`

## pseudocode

```c
void __fastcall TsiFreeActionAccountInfoSecurityParameters(struct _UBPM_ACTION_ACCOUNT_INFO *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void **v4; // rdi
  unsigned int i; // esi

  v2 = *((_QWORD *)a1 + 1);
  if ( v2 )
  {
    operator delete[](*(void **)(v2 + 8));
    operator delete(*((void **)a1 + 1));
  }
  v3 = (void *)*((_QWORD *)a1 + 10);
  if ( v3 )
    operator delete[](v3);
  v4 = (void **)*((_QWORD *)a1 + 13);
  if ( v4 )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 24); v4 += 2 )
    {
      if ( *v4 )
        operator delete[](*v4);
      ++i;
    }
    operator delete[](*((void **)a1 + 13));
  }
}

```

## disassembly

```asm
0x18000e2c0  mov     [rsp+arg_8], rbx
0x18000e2c5  push    rdi
0x18000e2c6  sub     rsp, 20h
0x18000e2ca  mov     rbx, rcx
0x18000e2cd  mov     rcx, [rcx+8]
0x18000e2d1  test    rcx, rcx
0x18000e2d4  jz      short loc_18000E2EA
0x18000e2d6  mov     rcx, [rcx+8]
0x18000e2da  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e2e0  mov     rcx, [rbx+8]
0x18000e2e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e2ea  mov     rcx, [rbx+50h]
0x18000e2ee  test    rcx, rcx
0x18000e2f1  jz      short loc_18000E2F9
0x18000e2f3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e2f9  mov     rdi, [rbx+68h]
0x18000e2fd  test    rdi, rdi
0x18000e300  jz      short loc_18000E336
0x18000e302  mov     [rsp+28h+arg_0], rsi
0x18000e307  xor     esi, esi
0x18000e309  cmp     [rbx+60h], esi
0x18000e30c  jbe     short loc_18000E327
0x18000e30e  mov     rcx, [rdi]
0x18000e311  test    rcx, rcx
0x18000e314  jz      short loc_18000E31C
0x18000e316  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e31c  inc     esi
0x18000e31e  add     rdi, 10h
0x18000e322  cmp     esi, [rbx+60h]
0x18000e325  jb      short loc_18000E30E
0x18000e327  mov     rcx, [rbx+68h]
0x18000e32b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e331  mov     rsi, [rsp+28h+arg_0]
0x18000e336  mov     rbx, [rsp+28h+arg_8]
0x18000e33b  add     rsp, 20h
0x18000e33f  pop     rdi
0x18000e340  retn
```
