# ZtWriteCertEku

- ea: `0x18000c608`
- end: `0x18000c6b5`
- name: `ZtWriteCertEku`
- size: `173`
- prototype: `__int64 __fastcall(__int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d0a0`

## callees

- `0x18000c37c`
- `0x18000c608`
- `0x180015008`
- `0x180015a18`

## pseudocode

```c
__int64 __fastcall ZtWriteCertEku(__int64 a1, wchar_t **a2, unsigned __int64 *a3)
{
  unsigned int v6; // ebx

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_Sqq(a1, 41, (_DWORD)a3, a1, (__int64)a2, (__int64)a3);
  if ( a1 && a2 && a3 )
    v6 = StringCchPrintfExW(*a2, *a3, a2, a3, 0x1000u, L"%s", a1);
  else
    v6 = 87;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x2Au, (ULONGLONG)WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000c608  mov     rax, rsp
0x18000c60b  mov     [rax+8], rbx
0x18000c60f  mov     [rax+10h], rsi
0x18000c613  push    rdi
0x18000c614  sub     rsp, 40h
0x18000c618  mov     rbx, r8
0x18000c61b  mov     rdi, rdx
0x18000c61e  mov     rsi, rcx
0x18000c621  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c628  jz      short loc_18000C63F
0x18000c62a  mov     [rax-20h], rbx
0x18000c62e  mov     edx, 29h ; ')'
0x18000c633  mov     r9, rcx
0x18000c636  mov     [rax-28h], rdi
0x18000c63a  call    WPP_SF_Sqq
0x18000c63f  test    rsi, rsi
0x18000c642  jnz     short loc_18000C64B
0x18000c644  mov     ebx, 57h ; 'W'
0x18000c649  jmp     short loc_18000C681
0x18000c64b  test    rdi, rdi
0x18000c64e  jz      short loc_18000C644
0x18000c650  test    rbx, rbx
0x18000c653  jz      short loc_18000C644
0x18000c655  mov     rdx, [rbx]; unsigned __int64
0x18000c658  lea     rax, aS; "%s"
0x18000c65f  mov     rcx, [rdi]; Buffer
0x18000c662  mov     r9, rbx; unsigned __int64 *
0x18000c665  mov     [rsp+48h+var_18], rsi
0x18000c66a  mov     r8, rdi; unsigned __int16 **
0x18000c66d  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18000c672  mov     [rsp+48h+var_28], 1000h; unsigned int
0x18000c67a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c67f  mov     ebx, eax
0x18000c681  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000c688  jz      short loc_18000C6A3
0x18000c68a  mov     edx, 2Ah ; '*'
0x18000c68f  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000c696  mov     ecx, 40Bh
0x18000c69b  mov     r9d, ebx
0x18000c69e  call    WPP_SF_d
0x18000c6a3  mov     rsi, [rsp+48h+arg_8]
0x18000c6a8  mov     eax, ebx
0x18000c6aa  mov     rbx, [rsp+48h+arg_0]
0x18000c6af  add     rsp, 40h
0x18000c6b3  pop     rdi
0x18000c6b4  retn
```
