# RouterGetKeyDataBlob

- ea: `0x180015db4`
- end: `0x180015f4c`
- name: `RouterGetKeyDataBlob`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e910`

## callees

- `0x1800041d0`
- `0x180004200`
- `0x180005060`
- `0x180015db4`
- `0x18001b79d`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x180015e40`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x180015ecc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterGetKeyDataBlob(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // r15
  __int64 (__fastcall *v6)(__int64, _QWORD, const wchar_t *, char *, unsigned int, unsigned int *, _DWORD); // r12
  size_t v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  unsigned int v11; // eax
  _BYTE *v12; // rdi
  char *v13; // rsi
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  _BYTE *v18; // rcx
  unsigned int v20; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD v21[3]; // [rsp+44h] [rbp-A4h] BYREF
  char v22; // [rsp+50h] [rbp-98h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 16);
  v20 = 0;
  v21[0] = 0;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, char *, unsigned int, unsigned int *, _DWORD))(v3 + 120);
  v7 = a3;
  v8 = v6(v5, 0, L"KeyDataBlob", 0, 0, &v20, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
LABEL_3:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    return v9;
  }
  v11 = v20;
  if ( v20 > 0x4C )
  {
    v14 = SafeAllocaAllocateFromHeap(v20);
    v12 = (_BYTE *)v14;
    if ( !v14 )
    {
      v9 = -1073741801;
      v10 = 3221225495LL;
      goto LABEL_3;
    }
    v13 = (char *)v14;
    v11 = v20;
  }
  else
  {
    v12 = 0;
    v13 = &v22;
  }
  v15 = v6(v5, 0, L"KeyDataBlob", v13, v11, v21, 0);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
LABEL_11:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c");
    goto LABEL_15;
  }
  if ( (_DWORD)v7 != *((_DWORD *)v13 + 2) )
  {
    v9 = -1073741811;
    v16 = 3221225485LL;
    goto LABEL_11;
  }
  memcpy_0(a2, v13 + 12, v7);
  v9 = 0;
LABEL_15:
  if ( v12 )
  {
    v17 = v20;
    v18 = v12;
    if ( v20 )
    {
      do
      {
        *v18++ = 0;
        --v17;
      }
      while ( v17 );
    }
    BCryptFree(v12);
  }
  return v9;
}

```

## disassembly

```asm
0x180015db4  push    rbx
0x180015db6  push    rbp
0x180015db7  push    rsi
0x180015db8  push    rdi
0x180015db9  push    r12
0x180015dbb  push    r14
0x180015dbd  push    r15
0x180015dbf  sub     rsp, 0B0h
0x180015dc6  mov     rax, cs:__security_cookie
0x180015dcd  xor     rax, rsp
0x180015dd0  mov     [rsp+0E8h+var_48], rax
0x180015dd8  mov     rax, [rcx+8]
0x180015ddc  mov     r14, rdx
0x180015ddf  mov     r15, [rcx+10h]
0x180015de3  xor     r9d, r9d
0x180015de6  mov     [rsp+0E8h+var_A8], 0
0x180015dee  xor     edx, edx
0x180015df0  mov     [rsp+0E8h+var_A4], 0
0x180015df8  mov     rcx, r15
0x180015dfb  mov     r12, [rax+78h]
0x180015dff  lea     rax, [rsp+0E8h+var_A8]
0x180015e04  mov     [rsp+0E8h+var_B8], 0
0x180015e0c  mov     [rsp+0E8h+var_C0], rax
0x180015e11  mov     rax, r12
0x180015e14  mov     ebp, r8d
0x180015e17  lea     r8, aKeydatablob; "KeyDataBlob"
0x180015e1e  mov     [rsp+0E8h+var_C8], 0
0x180015e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2b  mov     ebx, eax
0x180015e2d  test    eax, eax
0x180015e2f  jns     short loc_180015E51
0x180015e31  mov     r9d, 46h ; 'F'
0x180015e37  mov     ecx, eax
0x180015e39  lea     rdx, aStatus; "Status"
0x180015e40  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015e47  call    DebugTraceError
0x180015e4c  jmp     loc_180015F27
0x180015e51  mov     eax, [rsp+0E8h+var_A8]
0x180015e55  cmp     eax, 4Ch ; 'L'
0x180015e58  ja      short loc_180015E63
0x180015e5a  xor     edi, edi
0x180015e5c  lea     rsi, [rsp+0E8h+var_98]
0x180015e61  jmp     short loc_180015E8A
0x180015e63  mov     rcx, rax
0x180015e66  call    SafeAllocaAllocateFromHeap
0x180015e6b  mov     rdi, rax
0x180015e6e  test    rax, rax
0x180015e71  jnz     short loc_180015E83
0x180015e73  mov     ebx, 0C0000017h
0x180015e78  lea     r9d, [rax+57h]
0x180015e7c  mov     ecx, 0C0000017h
0x180015e81  jmp     short loc_180015E39
0x180015e83  mov     rsi, rax
0x180015e86  mov     eax, [rsp+0E8h+var_A8]
0x180015e8a  lea     rcx, [rsp+0E8h+var_A4]
0x180015e8f  mov     [rsp+0E8h+var_B8], 0
0x180015e97  mov     [rsp+0E8h+var_C0], rcx
0x180015e9c  lea     r8, aKeydatablob; "KeyDataBlob"
0x180015ea3  mov     [rsp+0E8h+var_C8], eax
0x180015ea7  mov     r9, rsi
0x180015eaa  mov     rax, r12
0x180015ead  xor     edx, edx
0x180015eaf  mov     rcx, r15
0x180015eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb7  mov     ebx, eax
0x180015eb9  test    eax, eax
0x180015ebb  jns     short loc_180015EDA
0x180015ebd  mov     r9d, 6Bh ; 'k'
0x180015ec3  mov     ecx, eax
0x180015ec5  lea     rdx, aStatus; "Status"
0x180015ecc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015ed3  call    DebugTraceError
0x180015ed8  jmp     short loc_180015F02
0x180015eda  cmp     ebp, [rsi+8]
0x180015edd  jz      short loc_180015EF1
0x180015edf  mov     ebx, 0C000000Dh
0x180015ee4  mov     r9d, 74h ; 't'
0x180015eea  mov     ecx, 0C000000Dh
0x180015eef  jmp     short loc_180015EC5
0x180015ef1  mov     r8, rbp; Size
0x180015ef4  lea     rdx, [rsi+0Ch]; Src
0x180015ef8  mov     rcx, r14; void *
0x180015efb  call    memcpy_0
0x180015f00  xor     ebx, ebx
0x180015f02  test    rdi, rdi
0x180015f05  jz      short loc_180015F27
0x180015f07  mov     eax, [rsp+0E8h+var_A8]
0x180015f0b  mov     rcx, rdi
0x180015f0e  test    rax, rax
0x180015f11  jz      short loc_180015F1F
0x180015f13  mov     byte ptr [rcx], 0
0x180015f16  inc     rcx
0x180015f19  sub     rax, 1
0x180015f1d  jnz     short loc_180015F13
0x180015f1f  mov     rcx, rdi
0x180015f22  call    BCryptFree
0x180015f27  mov     eax, ebx
0x180015f29  mov     rcx, [rsp+0E8h+var_48]
0x180015f31  xor     rcx, rsp; StackCookie
0x180015f34  call    __security_check_cookie
0x180015f39  add     rsp, 0B0h
0x180015f40  pop     r15
0x180015f42  pop     r14
0x180015f44  pop     r12
0x180015f46  pop     rdi
0x180015f47  pop     rsi
0x180015f48  pop     rbp
0x180015f49  pop     rbx
0x180015f4a  retn
```
