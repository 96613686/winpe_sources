# MemMallocAndCat(ushort const *,...)

- ea: `0x18000ede8`
- end: `0x18000eec8`
- name: `?MemMallocAndCat@@YAPEAGPEBGZZ`
- size: `224`
- prototype: `unsigned __int16 *(const unsigned __int16 *, ...)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b58`
- `0x180005198`
- `0x180005388`
- `0x180006320`
- `0x180006904`
- `0x180007380`
- `0x18000c880`
- `0x18000ca5c`
- `0x18000cc50`
- `0x18000d060`
- `0x18000d3e0`
- `0x18000d728`
- `0x18000dabc`
- `0x18000f4c8`

## callees

- `0x180004c44`
- `0x18000ede8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000ee66`
- `KERNEL32!HeapAlloc` at `0x18000ee66`
- `KERNEL32!GetProcessHeap` at `0x18000ee58`
- `KERNEL32!GetProcessHeap` at `0x18000eea1`
- `KERNEL32!GetProcessHeap` at `0x18000ee58`
- `KERNEL32!GetProcessHeap` at `0x18000eea1`
- `KERNEL32!HeapFree` at `0x18000eeaf`
- `KERNEL32!HeapFree` at `0x18000eeaf`

## pseudocode

```c
unsigned __int16 *MemMallocAndCat(unsigned __int16 *a1, ...)
{
  const unsigned __int16 **v1; // r9
  __int64 v2; // rsi
  __int64 v3; // rdx
  unsigned __int64 v4; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  const unsigned __int16 **v8; // rdi
  const unsigned __int16 *v9; // rax
  HANDLE v10; // rax
  unsigned __int16 *v12; // [rsp+60h] [rbp+8h]
  va_list va; // [rsp+68h] [rbp+10h] BYREF

  va_start(va, a1);
  v12 = a1;
  va_copy((va_list)v1, va);
  v2 = 0;
  if ( a1 )
  {
    while ( 1 )
    {
      v3 = 0x7FFFFFFF;
      do
      {
        if ( !*a1 )
          break;
        ++a1;
        --v3;
      }
      while ( v3 );
      if ( !v3 )
        break;
      a1 = (unsigned __int16 *)*v1++;
      v2 += (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
      if ( !a1 )
      {
        v4 = v2 + 1;
        ProcessHeap = GetProcessHeap();
        v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, (unsigned int)(2 * v4));
        v7 = v6;
        if ( !v6 )
          return 0;
        *v6 = 0;
        va_copy((va_list)v8, va);
        v9 = v12;
        while ( (int)StringCchCatW(v7, v4, v9) >= 0 )
        {
          v9 = *v8++;
          if ( !v9 )
            return v7;
        }
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v7);
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ede8  mov     rax, rsp
0x18000edeb  mov     [rax+8], rcx
0x18000edef  mov     [rax+10h], rdx
0x18000edf3  mov     [rax+18h], r8
0x18000edf7  mov     [rax+20h], r9
0x18000edfb  push    rbx
0x18000edfc  push    rbp
0x18000edfd  push    rsi
0x18000edfe  push    rdi
0x18000edff  sub     rsp, 38h
0x18000ee03  xor     ebp, ebp
0x18000ee05  lea     r9, [rax+10h]
0x18000ee09  mov     esi, ebp
0x18000ee0b  mov     r10d, 7FFFFFFFh
0x18000ee11  test    rcx, rcx
0x18000ee14  jz      loc_18000EEBD
0x18000ee1a  mov     rdx, r10
0x18000ee1d  cmp     [rcx], bp
0x18000ee20  jz      short loc_18000EE2C
0x18000ee22  add     rcx, 2
0x18000ee26  sub     rdx, 1
0x18000ee2a  jnz     short loc_18000EE1D
0x18000ee2c  mov     rcx, r10
0x18000ee2f  mov     rax, rdx
0x18000ee32  sub     rcx, rdx
0x18000ee35  neg     rax
0x18000ee38  sbb     r8, r8
0x18000ee3b  and     r8, rcx
0x18000ee3e  test    rdx, rdx
0x18000ee41  jz      short loc_18000EEBD
0x18000ee43  mov     rcx, [r9]
0x18000ee46  add     r9, 8
0x18000ee4a  add     rsi, r8
0x18000ee4d  test    rcx, rcx
0x18000ee50  jnz     short loc_18000EE1A
0x18000ee52  inc     rsi
0x18000ee55  lea     ebx, [rsi+rsi]
0x18000ee58  call    cs:__imp_GetProcessHeap
0x18000ee5e  mov     r8d, ebx; dwBytes
0x18000ee61  xor     edx, edx; dwFlags
0x18000ee63  mov     rcx, rax; hHeap
0x18000ee66  call    cs:__imp_HeapAlloc
0x18000ee6c  mov     rbx, rax
0x18000ee6f  test    rax, rax
0x18000ee72  jz      short loc_18000EEBD
0x18000ee74  mov     [rax], bp
0x18000ee77  lea     rdi, [rsp+58h+arg_8]
0x18000ee7c  mov     rax, [rsp+58h+arg_0]
0x18000ee81  mov     r8, rax; unsigned __int16 *
0x18000ee84  mov     rdx, rsi; unsigned __int64
0x18000ee87  mov     rcx, rbx; unsigned __int16 *
0x18000ee8a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee8f  test    eax, eax
0x18000ee91  js      short loc_18000EEA1
0x18000ee93  mov     rax, [rdi]
0x18000ee96  add     rdi, 8
0x18000ee9a  test    rax, rax
0x18000ee9d  jnz     short loc_18000EE81
0x18000ee9f  jmp     short loc_18000EEB8
0x18000eea1  call    cs:__imp_GetProcessHeap
0x18000eea7  mov     r8, rbx; lpMem
0x18000eeaa  xor     edx, edx; dwFlags
0x18000eeac  mov     rcx, rax; hHeap
0x18000eeaf  call    cs:__imp_HeapFree
0x18000eeb5  mov     rbx, rbp
0x18000eeb8  mov     rax, rbx
0x18000eebb  jmp     short loc_18000EEBF
0x18000eebd  xor     eax, eax
0x18000eebf  add     rsp, 38h
0x18000eec3  pop     rdi
0x18000eec4  pop     rsi
0x18000eec5  pop     rbp
0x18000eec6  pop     rbx
0x18000eec7  retn
```
