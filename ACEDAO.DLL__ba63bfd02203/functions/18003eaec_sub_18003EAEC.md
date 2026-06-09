# sub_18003EAEC

- ea: `0x18003eaec`
- end: `0x18003ec0b`
- name: `sub_18003EAEC`
- size: `287`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `23`
- callee_count: `5`
- tags: ``

## callers

- `0x18003ec0c`
- `0x18003f504`
- `0x180040b80`
- `0x1800421b0`
- `0x1800469ec`
- `0x180046d5c`
- `0x180047694`
- `0x180047b74`
- `0x18004855c`
- `0x18004869c`
- `0x180049130`
- `0x1800492a0`
- `0x18004945c`
- `0x1800498b0`
- `0x18005241c`
- `0x1800540b8`
- `0x180055318`
- `0x180055480`
- `0x18005ba68`
- `0x18005d220`
- `0x18005dee0`
- `0x18005f370`
- `0x1800620b0`

## callees

- `0x18003eaec`
- `0x18004f430`
- `0x180063a24`
- `0x180063c84`
- `0x18007c380`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18003eb13`
- `KERNEL32!TlsGetValue` at `0x18003eb3d`
- `KERNEL32!TlsGetValue` at `0x18003ebae`
- `KERNEL32!TlsGetValue` at `0x18003ebc9`
- `KERNEL32!TlsGetValue` at `0x18003ebe1`
- `KERNEL32!TlsGetValue` at `0x18003eb13`
- `KERNEL32!TlsGetValue` at `0x18003eb3d`
- `KERNEL32!TlsGetValue` at `0x18003ebae`
- `KERNEL32!TlsGetValue` at `0x18003ebc9`
- `KERNEL32!TlsGetValue` at `0x18003ebe1`

## pseudocode

```c
__int64 __fastcall sub_18003EAEC(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rbx
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  void *v11; // rdi
  const void **Value; // rax
  _QWORD *v13; // rax

  if ( *((_QWORD *)TlsGetValue(dwTlsIndex) + 12) )
  {
    v9 = *(unsigned __int16 *)(a1 + 88);
    if ( v9 < a3 )
    {
      v10 = v9 + 1024;
      if ( a3 - v9 > 0x400 )
        v10 = a3;
      v11 = (void *)sub_180063A24(a1, v10);
      if ( !v11 )
        return sub_18004F430(4294966285LL, a2, 0, 1);
      if ( v10 < v9 )
        v9 = v10;
      Value = (const void **)TlsGetValue(dwTlsIndex);
      memcpy(v11, Value[12], v9);
      v13 = TlsGetValue(dwTlsIndex);
      sub_180063C84(a1, v13[12]);
      *((_QWORD *)TlsGetValue(dwTlsIndex) + 12) = v11;
      *(_WORD *)(a1 + 88) = v10;
    }
  }
  else
  {
    v6 = 1024;
    if ( a3 > 0x400 )
      v6 = a3;
    v7 = sub_180063A24(a1, v6);
    *((_QWORD *)TlsGetValue(dwTlsIndex) + 12) = v7;
    if ( !v7 )
      return sub_18004F430(4294966285LL, a2, 0, 1);
    *(_WORD *)(a1 + 88) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18003eaec  mov     [rsp+arg_0], rbx
0x18003eaf1  mov     [rsp+arg_8], rbp
0x18003eaf6  mov     [rsp+arg_10], rsi
0x18003eafb  push    rdi
0x18003eafc  push    r14
0x18003eafe  push    r15
0x18003eb00  sub     rsp, 20h
0x18003eb04  mov     rsi, rcx
0x18003eb07  mov     ebx, r8d
0x18003eb0a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003eb10  mov     r15, rdx
0x18003eb13  call    cs:TlsGetValue
0x18003eb19  cmp     qword ptr [rax+60h], 0
0x18003eb1e  jnz     short loc_18003EB70
0x18003eb20  mov     edi, 400h
0x18003eb25  mov     rcx, rsi
0x18003eb28  cmp     ebx, edi
0x18003eb2a  cmova   edi, ebx
0x18003eb2d  mov     edx, edi
0x18003eb2f  call    sub_180063A24
0x18003eb34  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003eb3a  mov     rbx, rax
0x18003eb3d  call    cs:TlsGetValue
0x18003eb43  mov     [rax+60h], rbx
0x18003eb47  test    rbx, rbx
0x18003eb4a  jnz     short loc_18003EB67
0x18003eb4c  mov     r9d, 1
0x18003eb52  xor     r8d, r8d
0x18003eb55  mov     rdx, r15
0x18003eb58  mov     ecx, 0FFFFFC0Dh
0x18003eb5d  call    sub_18004F430
0x18003eb62  jmp     loc_18003EBF2
0x18003eb67  mov     [rsi+58h], di
0x18003eb6b  jmp     loc_18003EBF0
0x18003eb70  movzx   ebp, word ptr [rsi+58h]
0x18003eb74  cmp     ebp, ebx
0x18003eb76  jnb     short loc_18003EBF0
0x18003eb78  mov     eax, ebx
0x18003eb7a  lea     r14d, [rbp+400h]
0x18003eb81  sub     eax, ebp
0x18003eb83  mov     edi, 400h
0x18003eb88  cmp     eax, edi
0x18003eb8a  mov     rcx, rsi
0x18003eb8d  cmova   r14d, ebx
0x18003eb91  mov     edx, r14d
0x18003eb94  call    sub_180063A24
0x18003eb99  mov     rdi, rax
0x18003eb9c  test    rax, rax
0x18003eb9f  jz      short loc_18003EB4C
0x18003eba1  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003eba7  cmp     r14d, ebp
0x18003ebaa  cmovb   ebp, r14d
0x18003ebae  call    cs:TlsGetValue
0x18003ebb4  mov     r8d, ebp; Size
0x18003ebb7  mov     rcx, rdi; void *
0x18003ebba  mov     rdx, [rax+60h]; Src
0x18003ebbe  call    memcpy
0x18003ebc3  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003ebc9  call    cs:TlsGetValue
0x18003ebcf  mov     rcx, rsi
0x18003ebd2  mov     rdx, [rax+60h]
0x18003ebd6  call    sub_180063C84
0x18003ebdb  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003ebe1  call    cs:TlsGetValue
0x18003ebe7  mov     [rax+60h], rdi
0x18003ebeb  mov     [rsi+58h], r14w
0x18003ebf0  xor     eax, eax
0x18003ebf2  mov     rbx, [rsp+38h+arg_0]
0x18003ebf7  mov     rbp, [rsp+38h+arg_8]
0x18003ebfc  mov     rsi, [rsp+38h+arg_10]
0x18003ec01  add     rsp, 20h
0x18003ec05  pop     r15
0x18003ec07  pop     r14
0x18003ec09  pop     rdi
0x18003ec0a  retn
```
