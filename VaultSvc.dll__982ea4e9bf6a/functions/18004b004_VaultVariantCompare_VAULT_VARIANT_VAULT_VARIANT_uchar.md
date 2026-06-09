# VaultVariantCompare(_VAULT_VARIANT *,_VAULT_VARIANT *,uchar)

- ea: `0x18004b004`
- end: `0x18004b106`
- name: `?VaultVariantCompare@@YAEPEAU_VAULT_VARIANT@@0E@Z`
- size: `258`
- prototype: `unsigned __int8 __fastcall(struct _VAULT_VARIANT *, struct _VAULT_VARIANT *, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004a4d8`

## callees

- `0x18004b004`
- `0x18004b430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b0dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b0dc`

## pseudocode

```c
bool __fastcall VaultVariantCompare(struct _VAULT_VARIANT *a1, struct _VAULT_VARIANT *a2, char a3)
{
  int v3; // r9d
  int v4; // r9d
  int v5; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  unsigned int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // r8d
  __int64 v17; // rax

  v3 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 != *(_DWORD *)a2 )
    return 0;
  if ( v3 <= 5 )
  {
    if ( v3 == 5 )
    {
      return *((double *)a1 + 1) == *((double *)a2 + 1);
    }
    else if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 && (v5 = v4 - 1) != 0 )
      {
        if ( (unsigned int)(v5 - 1) > 1 )
          return 0;
        return *((_DWORD *)a1 + 2) == *((_DWORD *)a2 + 2);
      }
      else
      {
        return *((_WORD *)a1 + 4) == *((_WORD *)a2 + 4);
      }
    }
    else
    {
      return *((_BYTE *)a1 + 8) == *((_BYTE *)a2 + 8);
    }
  }
  v8 = v3 - 6;
  if ( !v8 )
  {
    v17 = *((_QWORD *)a1 + 1) - *((_QWORD *)a2 + 1);
    if ( !v17 )
      v17 = *((_QWORD *)a1 + 2) - *((_QWORD *)a2 + 2);
    return v17 == 0;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 && v10 != 2 )
      return 0;
    v11 = *((_DWORD *)a1 + 2);
    if ( v11 != *((_DWORD *)a2 + 2) )
      return 0;
    v12 = memcmp_0(*((const void **)a1 + 2), *((const void **)a2 + 2), v11);
    return v12 == 0;
  }
  v13 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v14 = *((_QWORD *)a2 + 1);
  if ( v13 )
  {
    if ( !v14 )
      return 0;
    if ( a3 )
    {
      v15 = v14 - (_QWORD)v13;
      do
      {
        v16 = *(unsigned __int16 *)((char *)v13 + v15);
        v12 = *v13 - v16;
        if ( v12 )
          break;
        ++v13;
      }
      while ( v16 );
    }
    else
    {
      v12 = _o__wcsicmp(v13, v14);
    }
    return v12 == 0;
  }
  return !v14;
}

```

## disassembly

```asm
0x18004b004  sub     rsp, 28h
0x18004b008  mov     r9d, [rcx]
0x18004b00b  cmp     r9d, [rdx]
0x18004b00e  jnz     short loc_18004B068
0x18004b010  cmp     r9d, 5
0x18004b014  jg      short loc_18004B06F
0x18004b016  jz      short loc_18004B058
0x18004b018  test    r9d, r9d
0x18004b01b  jz      short loc_18004B04D
0x18004b01d  sub     r9d, 1
0x18004b021  jz      short loc_18004B040
0x18004b023  sub     r9d, 1
0x18004b027  jz      short loc_18004B040
0x18004b029  sub     r9d, 1
0x18004b02d  jz      short loc_18004B035
0x18004b02f  cmp     r9d, 1
0x18004b033  jnz     short loc_18004B068
0x18004b035  mov     eax, [rdx+8]
0x18004b038  cmp     [rcx+8], eax
0x18004b03b  jmp     loc_18004B0F9
0x18004b040  movzx   eax, word ptr [rdx+8]
0x18004b044  cmp     [rcx+8], ax
0x18004b048  jmp     loc_18004B0F9
0x18004b04d  mov     al, [rdx+8]
0x18004b050  cmp     [rcx+8], al
0x18004b053  jmp     loc_18004B0F9
0x18004b058  movsd   xmm0, qword ptr [rcx+8]
0x18004b05d  ucomisd xmm0, qword ptr [rdx+8]
0x18004b062  jnp     loc_18004B0F9
0x18004b068  xor     al, al
0x18004b06a  add     rsp, 28h
0x18004b06e  retn
0x18004b06f  sub     r9d, 6
0x18004b073  jz      short loc_18004B0E4
0x18004b075  sub     r9d, 1
0x18004b079  jz      short loc_18004B0A3
0x18004b07b  sub     r9d, 1
0x18004b07f  jz      short loc_18004B087
0x18004b081  cmp     r9d, 2
0x18004b085  jnz     short loc_18004B068
0x18004b087  mov     eax, [rcx+8]
0x18004b08a  cmp     eax, [rdx+8]
0x18004b08d  jnz     short loc_18004B068
0x18004b08f  mov     rdx, [rdx+10h]; Buf2
0x18004b093  mov     r8d, eax; Size
0x18004b096  mov     rcx, [rcx+10h]; Buf1
0x18004b09a  call    memcmp_0
0x18004b09f  test    eax, eax
0x18004b0a1  jmp     short loc_18004B0F9
0x18004b0a3  mov     rcx, [rcx+8]
0x18004b0a7  mov     rdx, [rdx+8]
0x18004b0ab  test    rcx, rcx
0x18004b0ae  jnz     short loc_18004B0B7
0x18004b0b0  test    rdx, rdx
0x18004b0b3  jz      short loc_18004B0FF
0x18004b0b5  jmp     short loc_18004B068
0x18004b0b7  test    rdx, rdx
0x18004b0ba  jz      short loc_18004B068
0x18004b0bc  test    r8b, r8b
0x18004b0bf  jz      short loc_18004B0DC
0x18004b0c1  sub     rdx, rcx
0x18004b0c4  movzx   eax, word ptr [rcx]
0x18004b0c7  movzx   r8d, word ptr [rcx+rdx]
0x18004b0cc  sub     eax, r8d
0x18004b0cf  jnz     short loc_18004B09F
0x18004b0d1  add     rcx, 2
0x18004b0d5  test    r8d, r8d
0x18004b0d8  jnz     short loc_18004B0C4
0x18004b0da  jmp     short loc_18004B09F
0x18004b0dc  call    cs:__imp__o__wcsicmp
0x18004b0e2  jmp     short loc_18004B09F
0x18004b0e4  mov     rax, [rcx+8]
0x18004b0e8  sub     rax, [rdx+8]
0x18004b0ec  jnz     short loc_18004B0F6
0x18004b0ee  mov     rax, [rcx+10h]
0x18004b0f2  sub     rax, [rdx+10h]
0x18004b0f6  test    rax, rax
0x18004b0f9  jnz     loc_18004B068
0x18004b0ff  mov     al, 1
0x18004b101  jmp     loc_18004B06A
```
