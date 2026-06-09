# CopyBuffer(_UNICODE_STRING *,ushort const *,ushort,ulong)

- ea: `0x18001f4a0`
- end: `0x18001f57c`
- name: `?CopyBuffer@@YAJPEAU_UNICODE_STRING@@PEBGGK@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180018a10`
- `0x18001afb0`
- `0x18001d8b0`
- `0x1800245a0`
- `0x180024660`

## callees

- `0x1800152d4`
- `0x18001c968`
- `0x18001f218`
- `0x18001f4a0`

## pseudocode

```c
__int64 __fastcall CopyBuffer(struct _UNICODE_STRING *a1, const unsigned __int16 *a2, __int64 a3, unsigned int a4)
{
  __int16 v6; // ax
  __int64 MaximumLength; // rdi
  unsigned __int64 v8; // r11
  unsigned int v9; // ecx
  __int64 Length; // r10
  __int64 v11; // rax
  unsigned __int16 *v12; // rsi
  int v13; // eax
  __int16 v14; // r11
  unsigned int v15; // edi
  USHORT v17; // ax
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = wcsnlen_s(a2, a4);
  MaximumLength = a1->MaximumLength;
  v8 = (unsigned __int16)(2 * v6);
  if ( (int)v8 + 6 <= (unsigned int)MaximumLength )
  {
    Length = a1->Length;
    if ( (int)v8 + 6 + (int)Length <= (unsigned int)MaximumLength )
    {
      v11 = 0;
      v12 = (PWSTR)((char *)a1->Buffer + Length + 2);
      if ( !(_WORD)Length )
        v12 = (PWSTR)((char *)a1->Buffer + Length);
      LOBYTE(v11) = (_WORD)Length != 0;
      v13 = StringCchCopyNW(v12, ((unsigned __int64)(MaximumLength - Length) >> 1) - v11, a2, v8 >> 1);
      v15 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelershared.cpp",
          (const char *)(unsigned int)v13,
          v18);
        return v15;
      }
      v17 = a1->Length;
      v9 = 0;
      if ( a1->Length )
      {
        *(v12 - 1) = 124;
        v17 = a1->Length + 2;
      }
      a1->Length = v17 + v14;
    }
    else
    {
      return (unsigned int)-2147024774;
    }
  }
  else
  {
    return (unsigned int)-2147024785;
  }
  return v9;
}

```

## disassembly

```asm
0x18001f4a0  push    rbx
0x18001f4a2  push    rbp
0x18001f4a3  push    rsi
0x18001f4a4  push    rdi
0x18001f4a5  push    r14; int
0x18001f4a7  sub     rsp, 20h
0x18001f4ab  mov     rbp, rdx
0x18001f4ae  mov     rbx, rcx
0x18001f4b1  mov     rcx, rbp; Source
0x18001f4b4  mov     edx, r9d; MaxCount
0x18001f4b7  call    wcsnlen_s
0x18001f4bc  movzx   edi, word ptr [rbx+2]
0x18001f4c0  add     ax, ax
0x18001f4c3  movzx   r11d, ax
0x18001f4c7  lea     ecx, [r11+6]
0x18001f4cb  cmp     ecx, edi
0x18001f4cd  jbe     short loc_18001F4D9
0x18001f4cf  mov     ecx, 8007006Fh
0x18001f4d4  jmp     loc_18001F56F
0x18001f4d9  movzx   r10d, word ptr [rbx]
0x18001f4dd  lea     eax, [rcx+r10]
0x18001f4e1  cmp     eax, edi
0x18001f4e3  jbe     short loc_18001F4EF
0x18001f4e5  mov     ecx, 8007007Ah
0x18001f4ea  jmp     loc_18001F56F
0x18001f4ef  mov     rcx, [rbx+8]
0x18001f4f3  xor     r14d, r14d
0x18001f4f6  add     rcx, r10
0x18001f4f9  mov     eax, r14d
0x18001f4fc  test    r10w, r10w
0x18001f500  mov     rdx, rdi
0x18001f503  mov     r9, r11
0x18001f506  mov     r8, rbp; unsigned __int16 *
0x18001f509  lea     rsi, [rcx+2]
0x18001f50d  cmovz   rsi, rcx
0x18001f511  sub     rdx, r10
0x18001f514  shr     rdx, 1
0x18001f517  mov     rcx, rsi; unsigned __int16 *
0x18001f51a  shr     r9, 1; unsigned __int64
0x18001f51d  test    r10w, r10w
0x18001f521  setnz   al
0x18001f524  sub     rdx, rax; unsigned __int64
0x18001f527  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001f52c  mov     edi, eax
0x18001f52e  test    eax, eax
0x18001f530  jns     short loc_18001F54F
0x18001f532  mov     rcx, [rsp+48h]; this
0x18001f537  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001f53e  mov     r9d, eax; char *
0x18001f541  mov     edx, 0CDh; void *
0x18001f546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f54b  mov     eax, edi
0x18001f54d  jmp     short loc_18001F571
0x18001f54f  movzx   eax, word ptr [rbx]
0x18001f552  mov     ecx, r14d
0x18001f555  test    ax, ax
0x18001f558  jz      short loc_18001F567
0x18001f55a  mov     word ptr [rsi-2], 7Ch ; '|'
0x18001f560  movzx   eax, word ptr [rbx]
0x18001f563  add     ax, 2
0x18001f567  add     r11w, ax
0x18001f56b  mov     [rbx], r11w
0x18001f56f  mov     eax, ecx
0x18001f571  add     rsp, 20h
0x18001f575  pop     r14
0x18001f577  pop     rdi
0x18001f578  pop     rsi
0x18001f579  pop     rbp
0x18001f57a  pop     rbx
0x18001f57b  retn
```
