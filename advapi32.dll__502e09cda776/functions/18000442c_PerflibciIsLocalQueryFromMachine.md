# PerflibciIsLocalQueryFromMachine

- ea: `0x18000442c`
- end: `0x180004558`
- name: `PerflibciIsLocalQueryFromMachine`
- size: `300`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ed0`
- `0x180004290`
- `0x180004830`
- `0x180009e60`

## callees

- `0x18000442c`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180004474`
- `KERNEL32!InitOnceBeginInitialize` at `0x180004474`
- `KERNEL32!CompareStringOrdinal` at `0x1800044a5`
- `KERNEL32!CompareStringOrdinal` at `0x1800044e4`
- `KERNEL32!CompareStringOrdinal` at `0x1800044a5`
- `KERNEL32!CompareStringOrdinal` at `0x1800044e4`
- `KERNEL32!InitOnceComplete` at `0x18000453d`
- `KERNEL32!InitOnceComplete` at `0x18000453d`
- `KERNEL32!GetComputerNameW` at `0x18000451c`
- `KERNEL32!GetComputerNameW` at `0x18000451c`

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
      Context = byte_1800B18C8;
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
0x18000442c  mov     [rsp-18h+arg_18], rbx
0x180004431  push    rbp
0x180004432  push    rsi
0x180004433  push    rdi
0x180004434  mov     rbp, rsp
0x180004437  sub     rsp, 30h
0x18000443b  xor     esi, esi
0x18000443d  mov     rbx, rcx
0x180004440  mov     edi, esi
0x180004442  test    rcx, rcx
0x180004445  jnz     short loc_180004457
0x180004447  mov     rbx, [rsp+30h+arg_18]
0x18000444c  mov     eax, edi
0x18000444e  add     rsp, 30h
0x180004452  pop     rdi
0x180004453  pop     rsi
0x180004454  pop     rbp
0x180004455  retn
0x180004457  cmp     [rcx], si
0x18000445a  jz      short loc_180004447
0x18000445c  lea     r9, [rbp+Context]; lpContext
0x180004460  mov     [rbp+fPending], esi
0x180004463  lea     r8, [rbp+fPending]; fPending
0x180004467  mov     [rbp+Context], rsi
0x18000446b  xor     edx, edx; dwFlags
0x18000446d  lea     rcx, InitOnce; lpInitOnce
0x180004474  call    cs:__imp_InitOnceBeginInitialize
0x18000447b  nop     dword ptr [rax+rax+00h]
0x180004480  cmp     [rbp+fPending], esi
0x180004483  jnz     short loc_1800044FF
0x180004485  mov     r8, [rbp+Context]
0x180004489  cmp     [r8], esi
0x18000448c  jz      short loc_180004447
0x18000448e  or      esi, 0FFFFFFFFh
0x180004491  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x180004499  mov     r9d, esi; cchCount2
0x18000449c  mov     edx, esi; cchCount1
0x18000449e  add     r8, 4; lpString2
0x1800044a2  mov     rcx, rbx; lpString1
0x1800044a5  call    cs:__imp_CompareStringOrdinal
0x1800044ac  nop     dword ptr [rax+rax+00h]
0x1800044b1  cmp     eax, 2
0x1800044b4  jz      short loc_180004447
0x1800044b6  cmp     word ptr [rbx], 5Ch ; '\'
0x1800044ba  jnz     loc_18000454E
0x1800044c0  cmp     word ptr [rbx+2], 5Ch ; '\'
0x1800044c5  jnz     loc_18000454E
0x1800044cb  mov     r8, [rbp+Context]
0x1800044cf  lea     rcx, [rbx+4]; lpString1
0x1800044d3  add     r8, 4; lpString2
0x1800044d7  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x1800044df  mov     r9d, esi; cchCount2
0x1800044e2  mov     edx, esi; cchCount1
0x1800044e4  call    cs:__imp_CompareStringOrdinal
0x1800044eb  nop     dword ptr [rax+rax+00h]
0x1800044f0  sub     eax, 2
0x1800044f3  neg     eax
0x1800044f5  sbb     edi, edi
0x1800044f7  and     edi, 0Dh
0x1800044fa  jmp     loc_180004447
0x1800044ff  lea     rax, byte_1800B18C8
0x180004506  mov     [rbp+nSize], 10h
0x18000450d  lea     rdx, [rbp+nSize]; nSize
0x180004511  mov     [rbp+Context], rax
0x180004515  lea     rcx, Buffer; lpBuffer
0x18000451c  call    cs:__imp_GetComputerNameW
0x180004523  nop     dword ptr [rax+rax+00h]
0x180004528  mov     edx, eax
0x18000452a  lea     rcx, InitOnce; lpInitOnce
0x180004531  mov     rax, [rbp+Context]
0x180004535  mov     [rax], edx
0x180004537  xor     edx, edx; dwFlags
0x180004539  mov     r8, [rbp+Context]; lpContext
0x18000453d  call    cs:__imp_InitOnceComplete
0x180004544  nop     dword ptr [rax+rax+00h]
0x180004549  jmp     loc_180004485
0x18000454e  mov     edi, 0Dh
0x180004553  jmp     loc_180004447
```
