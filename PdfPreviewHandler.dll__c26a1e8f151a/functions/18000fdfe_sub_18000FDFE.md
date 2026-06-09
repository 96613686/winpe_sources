# sub_18000FDFE

- ea: `0x18000fdfe`
- end: `0x18000feba`
- name: `sub_18000FDFE`
- size: `188`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c150`
- `0x18000fede`
- `0x18001c46a`
- `0x18001d52c`
- `0x180024260`
- `0x180025750`
- `0x180026bec`
- `0x18002a836`
- `0x18002acee`

## callees

- `0x18000fdfe`
- `0x180010c68`
- `0x180010f44`
- `0x180010ffc`
- `0x180011068`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_18000FDFE(__int64 a1)
{
  if ( dword_18003C118 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                   + 4LL) )
  {
    sub_180010F44(&dword_18003C118);
    if ( dword_18003C118 == -1 )
    {
      sub_180010C68(&Locale, 63, dword_18003053C);
      atexit(sub_180026CC0);
      sub_180010FFC(&dword_18003C118);
    }
  }
  *(_OWORD *)a1 = *(_OWORD *)&Locale;
  *(_QWORD *)(a1 + 16) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000fdfe  push    rbp
0x18000fdff  push    rsi
0x18000fe00  sub     rsp, 48h
0x18000fe04  lea     rbp, [rsp+40h]
0x18000fe09  mov     [rbp+10h+var_10], 0FFFFFFFFFFFFFFFEh
0x18000fe11  mov     rsi, rcx
0x18000fe14  mov     eax, cs:dword_18003C118
0x18000fe1a  mov     ecx, cs:TlsIndex
0x18000fe20  mov     rdx, gs:58h
0x18000fe29  mov     rcx, [rdx+rcx*8]
0x18000fe2d  cmp     eax, [rcx+4]
0x18000fe33  jg      short loc_18000FE5C
0x18000fe35  mov     rax, qword ptr cs:Locale
0x18000fe3c  mov     [rsi], rax
0x18000fe3f  mov     rax, qword ptr cs:Locale+8
0x18000fe46  mov     [rsi+8], rax
0x18000fe4a  mov     qword ptr [rsi+10h], 0
0x18000fe52  mov     rax, rsi
0x18000fe55  add     rsp, 48h
0x18000fe59  pop     rsi
0x18000fe5a  pop     rbp
0x18000fe5b  retn
0x18000fe5c  lea     rcx, dword_18003C118
0x18000fe63  call    sub_180010F44
0x18000fe68  cmp     cs:dword_18003C118, 0FFFFFFFFh
0x18000fe6f  jnz     short loc_18000FE35
0x18000fe71  xorps   xmm0, xmm0
0x18000fe74  lea     r9, [rbp+10h+var_30]
0x18000fe78  movaps  xmmword ptr [r9], xmm0
0x18000fe7c  mov     qword ptr [r9+10h], 0
0x18000fe84  lea     rcx, Locale
0x18000fe8b  lea     r8, dword_18003053C
0x18000fe92  mov     edx, 3Fh ; '?'
0x18000fe97  call    sub_180010C68
0x18000fe9c  nop
0x18000fe9d  lea     rcx, sub_180026CC0; void (__cdecl *)()
0x18000fea4  call    atexit
0x18000fea9  lea     rcx, dword_18003C118
0x18000feb0  call    sub_180010FFC
0x18000feb5  jmp     loc_18000FE35
```
