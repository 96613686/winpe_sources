# TXmlReader::IsNodeQName(ushort const *,ushort const *)

- ea: `0x1800108d8`
- end: `0x18001099e`
- name: `?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z`
- size: `198`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000838c`
- `0x180008d8c`
- `0x18000913c`
- `0x18000a200`
- `0x18000a4c4`
- `0x18000dabc`
- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010e08`

## callees

- `0x1800108d8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::IsNodeQName(TXmlReader *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  unsigned int v7; // edx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // r8d
  __int64 v15; // [rsp+30h] [rbp+8h] BYREF
  __int64 v16; // [rsp+48h] [rbp+20h] BYREF

  v15 = 0;
  v4 = *(_QWORD *)this;
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v4 + 112LL))(v4, &v15, 0);
  if ( !v7 )
  {
    v8 = v15 - (_QWORD)a2;
    do
    {
      v9 = *(const unsigned __int16 *)((char *)a2 + v8);
      v10 = *a2 - v9;
      if ( v10 )
        break;
      ++a2;
    }
    while ( v9 );
    if ( v10 )
    {
      return 1;
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)this + 104LL))(*(_QWORD *)this, &v16, 0);
      if ( !v7 )
      {
        v11 = v16 - (_QWORD)a3;
        do
        {
          v12 = *(const unsigned __int16 *)((char *)a3 + v11);
          v13 = *a3 - v12;
          if ( v13 )
            break;
          ++a3;
        }
        while ( v12 );
        return v13 != 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800108d8  mov     r11, rsp
0x1800108db  mov     [r11+10h], rbx
0x1800108df  mov     [r11+18h], rsi
0x1800108e3  push    rdi
0x1800108e4  sub     rsp, 20h
0x1800108e8  mov     rsi, rcx
0x1800108eb  mov     qword ptr [r11+8], 0
0x1800108f3  mov     rcx, [rcx]
0x1800108f6  mov     rdi, r8
0x1800108f9  mov     qword ptr [r11+20h], 0
0x180010901  mov     rbx, rdx
0x180010904  xor     r8d, r8d
0x180010907  lea     rdx, [r11+8]
0x18001090b  mov     rax, [rcx]
0x18001090e  mov     rax, [rax+70h]
0x180010912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010917  mov     edx, eax
0x180010919  test    eax, eax
0x18001091b  jnz     short loc_18001098C
0x18001091d  mov     rdx, [rsp+28h+arg_0]
0x180010922  sub     rdx, rbx
0x180010925  movzx   eax, word ptr [rbx]
0x180010928  movzx   ecx, word ptr [rbx+rdx]
0x18001092c  sub     eax, ecx
0x18001092e  jnz     short loc_180010938
0x180010930  add     rbx, 2
0x180010934  test    ecx, ecx
0x180010936  jnz     short loc_180010925
0x180010938  test    eax, eax
0x18001093a  jz      short loc_180010943
0x18001093c  mov     edx, 1
0x180010941  jmp     short loc_18001098C
0x180010943  mov     rcx, [rsi]
0x180010946  lea     rdx, [rsp+28h+arg_18]
0x18001094b  xor     r8d, r8d
0x18001094e  mov     rax, [rcx]
0x180010951  mov     rax, [rax+68h]
0x180010955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001095a  mov     edx, eax
0x18001095c  test    eax, eax
0x18001095e  jnz     short loc_18001098C
0x180010960  mov     rcx, [rsp+28h+arg_18]
0x180010965  sub     rcx, rdi
0x180010968  movzx   r8d, word ptr [rdi]
0x18001096c  movzx   eax, word ptr [rdi+rcx]
0x180010970  sub     r8d, eax
0x180010973  jnz     short loc_18001097D
0x180010975  add     rdi, 2
0x180010979  test    eax, eax
0x18001097b  jnz     short loc_180010968
0x18001097d  mov     eax, edx
0x18001097f  test    r8d, r8d
0x180010982  mov     edx, 1
0x180010987  cmovnz  eax, edx
0x18001098a  mov     edx, eax
0x18001098c  mov     rbx, [rsp+28h+arg_8]
0x180010991  mov     eax, edx
0x180010993  mov     rsi, [rsp+28h+arg_10]
0x180010998  add     rsp, 20h
0x18001099c  pop     rdi
0x18001099d  retn
```
