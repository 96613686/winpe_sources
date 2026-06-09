# PerflibciIsLocalQueryFromMachine

- ea: `0x180003f84`
- end: `0x180004089`
- name: `PerflibciIsLocalQueryFromMachine`
- size: `261`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001220`
- `0x180003a70`
- `0x180003e00`
- `0x180004310`

## callees

- `0x180003f84`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180003fcb`
- `KERNEL32!InitOnceBeginInitialize` at `0x180003fcb`
- `KERNEL32!CompareStringOrdinal` at `0x180003ff6`
- `KERNEL32!CompareStringOrdinal` at `0x180004027`
- `KERNEL32!CompareStringOrdinal` at `0x180003ff6`
- `KERNEL32!CompareStringOrdinal` at `0x180004027`
- `KERNEL32!InitOnceComplete` at `0x180004074`
- `KERNEL32!InitOnceComplete` at `0x180004074`
- `KERNEL32!GetComputerNameW` at `0x180004059`
- `KERNEL32!GetComputerNameW` at `0x180004059`

## pseudocode

```c
__int64 __fastcall PerflibciIsLocalQueryFromMachine(LPCWCH lpString1)
{
  unsigned int v2; // edi
  BOOL ComputerNameW; // eax
  WINBOOL fPending; // [rsp+50h] [rbp+20h] BYREF
  DWORD nSize; // [rsp+58h] [rbp+28h] BYREF
  LPVOID Context; // [rsp+60h] [rbp+30h] BYREF

  v2 = 0;
  if ( lpString1 && *lpString1 )
  {
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&InitOnce, 0, &fPending, &Context);
    if ( fPending )
    {
      nSize = 16;
      Context = byte_1800A28C8;
      ComputerNameW = GetComputerNameW(&Buffer, &nSize);
      *(_DWORD *)Context = ComputerNameW;
      InitOnceComplete(&InitOnce, 0, Context);
    }
    if ( *(_DWORD *)Context && CompareStringOrdinal(lpString1, -1, (LPCWCH)Context + 2, -1, 1) != 2 )
    {
      if ( *lpString1 == 92 && lpString1[1] == 92 )
        return CompareStringOrdinal(lpString1 + 2, -1, (LPCWCH)Context + 2, -1, 1) != 2 ? 0xD : 0;
      else
        return 13;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003f84  mov     [rsp-18h+arg_18], rbx
0x180003f89  push    rbp
0x180003f8a  push    rsi
0x180003f8b  push    rdi
0x180003f8c  mov     rbp, rsp
0x180003f8f  sub     rsp, 30h
0x180003f93  xor     esi, esi
0x180003f95  mov     rbx, rcx
0x180003f98  mov     edi, esi
0x180003f9a  test    rcx, rcx
0x180003f9d  jnz     short loc_180003FAE
0x180003f9f  mov     rbx, [rsp+30h+arg_18]
0x180003fa4  mov     eax, edi
0x180003fa6  add     rsp, 30h
0x180003faa  pop     rdi
0x180003fab  pop     rsi
0x180003fac  pop     rbp
0x180003fad  retn
0x180003fae  cmp     [rcx], si
0x180003fb1  jz      short loc_180003F9F
0x180003fb3  lea     r9, [rbp+Context]; lpContext
0x180003fb7  mov     [rbp+fPending], esi
0x180003fba  lea     r8, [rbp+fPending]; fPending
0x180003fbe  mov     [rbp+Context], rsi
0x180003fc2  xor     edx, edx; dwFlags
0x180003fc4  lea     rcx, InitOnce; lpInitOnce
0x180003fcb  call    cs:__imp_InitOnceBeginInitialize
0x180003fd1  cmp     [rbp+fPending], esi
0x180003fd4  jnz     short loc_18000403C
0x180003fd6  mov     r8, [rbp+Context]
0x180003fda  cmp     [r8], esi
0x180003fdd  jz      short loc_180003F9F
0x180003fdf  or      esi, 0FFFFFFFFh
0x180003fe2  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x180003fea  mov     r9d, esi; cchCount2
0x180003fed  mov     edx, esi; cchCount1
0x180003fef  add     r8, 4; lpString2
0x180003ff3  mov     rcx, rbx; lpString1
0x180003ff6  call    cs:__imp_CompareStringOrdinal
0x180003ffc  cmp     eax, 2
0x180003fff  jz      short loc_180003F9F
0x180004001  cmp     word ptr [rbx], 5Ch ; '\'
0x180004005  jnz     short loc_18000407F
0x180004007  cmp     word ptr [rbx+2], 5Ch ; '\'
0x18000400c  jnz     short loc_18000407F
0x18000400e  mov     r8, [rbp+Context]
0x180004012  lea     rcx, [rbx+4]; lpString1
0x180004016  add     r8, 4; lpString2
0x18000401a  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x180004022  mov     r9d, esi; cchCount2
0x180004025  mov     edx, esi; cchCount1
0x180004027  call    cs:__imp_CompareStringOrdinal
0x18000402d  sub     eax, 2
0x180004030  neg     eax
0x180004032  sbb     edi, edi
0x180004034  and     edi, 0Dh
0x180004037  jmp     loc_180003F9F
0x18000403c  lea     rax, byte_1800A28C8
0x180004043  mov     [rbp+nSize], 10h
0x18000404a  lea     rdx, [rbp+nSize]; nSize
0x18000404e  mov     [rbp+Context], rax
0x180004052  lea     rcx, Buffer; lpBuffer
0x180004059  call    cs:__imp_GetComputerNameW
0x18000405f  mov     edx, eax
0x180004061  lea     rcx, InitOnce; lpInitOnce
0x180004068  mov     rax, [rbp+Context]
0x18000406c  mov     [rax], edx
0x18000406e  xor     edx, edx; dwFlags
0x180004070  mov     r8, [rbp+Context]; lpContext
0x180004074  call    cs:__imp_InitOnceComplete
0x18000407a  jmp     loc_180003FD6
0x18000407f  mov     edi, 0Dh
0x180004084  jmp     loc_180003F9F
```
