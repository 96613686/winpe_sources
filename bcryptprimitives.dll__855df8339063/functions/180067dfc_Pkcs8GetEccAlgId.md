# Pkcs8GetEccAlgId

- ea: `0x180067dfc`
- end: `0x180067f40`
- name: `Pkcs8GetEccAlgId`
- size: `324`
- prototype: `__int64 __fastcall(int, int *, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800679b8`

## callees

- `0x18000ecb0`
- `0x1800631a8`
- `0x180067dfc`

## string_xrefs

- `0x180067f20`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\pkcsblob.c`

## pseudocode

```c
__int64 __fastcall Pkcs8GetEccAlgId(int a1, int *a2, int *a3, int *a4)
{
  const void *v6; // rax
  unsigned int v7; // esi
  __int64 v8; // rdi
  const void *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx

  if ( !a2 || !a3 || !a4 )
  {
    v10 = -1073741811;
    v11 = 294;
    v12 = 3221225485LL;
    goto LABEL_33;
  }
  v6 = (const void *)*((_QWORD *)a3 + 1);
  if ( *a3 && v6 || (v7 = *a2) == 0 || (v8 = *((_QWORD *)a2 + 1)) == 0 )
  {
    v7 = *a3;
    v8 = *((_QWORD *)a3 + 1);
    if ( *a3 )
    {
      if ( v6 )
      {
        if ( *a2 )
        {
          v9 = (const void *)*((_QWORD *)a2 + 1);
          if ( v9 )
          {
            if ( v7 != *a2 || memcmp_0(v9, v6, v7) )
            {
              v10 = -1073739509;
              v11 = 313;
              v12 = 3221227787LL;
LABEL_33:
              DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\pkcsblob.c", v11);
              return v10;
            }
          }
        }
      }
    }
  }
  if ( v7 == 8 )
  {
    if ( *(_QWORD *)v8 == 0x701033DCE48862ALL )
    {
      v13 = 196612;
      v14 = 196615;
      goto LABEL_27;
    }
  }
  else if ( v7 == 5 )
  {
    v15 = *(_DWORD *)v8 - 295211;
    if ( *(_DWORD *)v8 == 295211 )
      v15 = *(unsigned __int8 *)(v8 + 4) - 34;
    if ( v15 )
    {
      v16 = *(_DWORD *)v8 - 295211;
      if ( *(_DWORD *)v8 == 295211 )
        v16 = *(unsigned __int8 *)(v8 + 4) - 35;
      if ( v16 )
        goto LABEL_30;
      v13 = 196614;
      v14 = 196617;
    }
    else
    {
      v13 = 196613;
      v14 = 196616;
    }
LABEL_27:
    if ( a1 != 5 )
      v13 = v14;
    goto LABEL_31;
  }
LABEL_30:
  v13 = 196619 - (a1 != 5);
LABEL_31:
  *a4 = v13;
  return 0;
}

```

## disassembly

```asm
0x180067dfc  push    rbx
0x180067dfe  push    rsi
0x180067dff  push    rdi
0x180067e00  push    r14
0x180067e02  sub     rsp, 28h
0x180067e06  mov     r14, r9
0x180067e09  mov     ebx, ecx
0x180067e0b  test    rdx, rdx
0x180067e0e  jz      loc_180067F10
0x180067e14  test    r8, r8
0x180067e17  jz      loc_180067F10
0x180067e1d  test    r9, r9
0x180067e20  jz      loc_180067F10
0x180067e26  cmp     dword ptr [r8], 0
0x180067e2a  mov     rax, [r8+8]
0x180067e2e  jbe     short loc_180067E35
0x180067e30  test    rax, rax
0x180067e33  jnz     short loc_180067E44
0x180067e35  mov     esi, [rdx]
0x180067e37  test    esi, esi
0x180067e39  jz      short loc_180067E44
0x180067e3b  mov     rdi, [rdx+8]
0x180067e3f  test    rdi, rdi
0x180067e42  jnz     short loc_180067E8D
0x180067e44  mov     esi, [r8]
0x180067e47  mov     rdi, rax
0x180067e4a  test    esi, esi
0x180067e4c  jz      short loc_180067E8D
0x180067e4e  test    rax, rax
0x180067e51  jz      short loc_180067E8D
0x180067e53  mov     r9d, [rdx]
0x180067e56  test    r9d, r9d
0x180067e59  jz      short loc_180067E8D
0x180067e5b  mov     rcx, [rdx+8]; Buf1
0x180067e5f  test    rcx, rcx
0x180067e62  jz      short loc_180067E8D
0x180067e64  cmp     esi, r9d
0x180067e67  jnz     short loc_180067E78
0x180067e69  mov     r8d, esi; Size
0x180067e6c  mov     rdx, rax; Buf2
0x180067e6f  call    memcmp_0
0x180067e74  test    eax, eax
0x180067e76  jz      short loc_180067E8D
0x180067e78  mov     ebx, 0C000090Bh
0x180067e7d  mov     r9d, 139h
0x180067e83  mov     ecx, 0C000090Bh
0x180067e88  jmp     loc_180067F20
0x180067e8d  cmp     esi, 8
0x180067e90  jnz     short loc_180067EA8
0x180067e92  mov     rax, [rdi]
0x180067e95  cmp     rax, cs:qword_180091210
0x180067e9c  jnz     short loc_180067EFD
0x180067e9e  mov     eax, 30004h
0x180067ea3  lea     ecx, [rax+3]
0x180067ea6  jmp     short loc_180067EF5
0x180067ea8  cmp     esi, 5
0x180067eab  jnz     short loc_180067EFD
0x180067ead  mov     ecx, [rdi]
0x180067eaf  sub     ecx, cs:dword_180091204
0x180067eb5  jnz     short loc_180067EC4
0x180067eb7  movzx   ecx, byte ptr [rdi+4]
0x180067ebb  movzx   eax, cs:byte_180091208
0x180067ec2  sub     ecx, eax
0x180067ec4  test    ecx, ecx
0x180067ec6  jnz     short loc_180067ED2
0x180067ec8  mov     eax, 30005h
0x180067ecd  lea     ecx, [rax+3]
0x180067ed0  jmp     short loc_180067EF5
0x180067ed2  mov     ecx, [rdi]
0x180067ed4  sub     ecx, cs:dword_1800911EC
0x180067eda  jnz     short loc_180067EE9
0x180067edc  movzx   ecx, byte ptr [rdi+4]
0x180067ee0  movzx   eax, cs:byte_1800911F0
0x180067ee7  sub     ecx, eax
0x180067ee9  test    ecx, ecx
0x180067eeb  jnz     short loc_180067EFD
0x180067eed  mov     eax, 30006h
0x180067ef2  lea     ecx, [rax+3]
0x180067ef5  cmp     ebx, 5
0x180067ef8  cmovnz  eax, ecx
0x180067efb  jmp     short loc_180067F09
0x180067efd  sub     ebx, 5
0x180067f00  neg     ebx
0x180067f02  sbb     eax, eax
0x180067f04  add     eax, 3000Bh
0x180067f09  mov     [r14], eax
0x180067f0c  xor     ebx, ebx
0x180067f0e  jmp     short loc_180067F33
0x180067f10  mov     ebx, 0C000000Dh
0x180067f15  mov     r9d, 126h
0x180067f1b  mov     ecx, 0C000000Dh
0x180067f20  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067f27  lea     rdx, aStatus; "Status"
0x180067f2e  call    DebugTraceError
0x180067f33  mov     eax, ebx
0x180067f35  add     rsp, 28h
0x180067f39  pop     r14
0x180067f3b  pop     rdi
0x180067f3c  pop     rsi
0x180067f3d  pop     rbx
0x180067f3e  retn
```
