# CPropertyCache::DispatchAddProperty(ushort *,ulong *)

- ea: `0x18000ffe8`
- end: `0x180010096`
- name: `?DispatchAddProperty@CPropertyCache@@IEAAJPEAGPEAK@Z`
- size: `174`
- prototype: `int(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800102e0`

## callees

- `0x18000ffe8`
- `0x18001009c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010061`
- `msvcrt!wcscpy_s` at `0x180010061`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180010033`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x180010033`

## pseudocode

```c
int __fastcall CPropertyCache::DispatchAddProperty(CPropertyCache *this, unsigned __int16 *a2, unsigned int *a3)
{
  int result; // eax
  wchar_t *v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = -1;
  if ( !a2 )
    return -2147463160;
  result = CPropertyCache::DispatchFindProperty(this, a2, &v10);
  if ( result == -2147463155 )
  {
    v7 = (wchar_t *)ReallocADsMem(*((LPVOID *)this + 11), *((_DWORD *)this + 24), *((_DWORD *)this + 24) + 520);
    if ( !v7 )
      return -2147024882;
    v8 = *((unsigned int *)this + 25);
    *((_QWORD *)this + 11) = v7;
    wcscpy_s(&v7[260 * v8], 0x104u, a2);
    v9 = *((_DWORD *)this + 25);
    *((_DWORD *)this + 24) += 520;
    *((_DWORD *)this + 25) = v9 + 1;
    result = 0;
  }
  else
  {
    v9 = v10;
  }
  if ( a3 )
    *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18000ffe8  mov     [rsp+arg_0], rbx
0x18000ffed  mov     [rsp+arg_10], rsi
0x18000fff2  push    rdi
0x18000fff3  sub     rsp, 20h
0x18000fff7  mov     [rsp+28h+arg_8], 0FFFFFFFFh
0x18000ffff  mov     rdi, r8
0x180010002  mov     rsi, rdx
0x180010005  mov     rbx, rcx
0x180010008  test    rdx, rdx
0x18001000b  jnz     short loc_180010014
0x18001000d  mov     eax, 80005008h
0x180010012  jmp     short loc_180010086
0x180010014  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x180010019  call    ?DispatchFindProperty@CPropertyCache@@IEAAJPEAGPEAK@Z; CPropertyCache::DispatchFindProperty(ushort *,ulong *)
0x18001001e  cmp     eax, 8000500Dh
0x180010023  jnz     short loc_18001007B
0x180010025  mov     edx, [rbx+60h]; cbOld
0x180010028  mov     rcx, [rbx+58h]; pOldMem
0x18001002c  lea     r8d, [rdx+208h]; cbNew
0x180010033  call    cs:__imp_ReallocADsMem
0x180010039  mov     rdx, rax
0x18001003c  test    rax, rax
0x18001003f  jnz     short loc_180010048
0x180010041  mov     eax, 8007000Eh
0x180010046  jmp     short loc_180010086
0x180010048  mov     eax, [rbx+64h]
0x18001004b  mov     r8, rsi; Source
0x18001004e  imul    rcx, rax, 208h
0x180010055  mov     [rbx+58h], rdx
0x180010059  add     rcx, rdx; Destination
0x18001005c  mov     edx, 104h; SizeInWords
0x180010061  call    cs:__imp_wcscpy_s
0x180010067  mov     ecx, [rbx+64h]
0x18001006a  add     dword ptr [rbx+60h], 208h
0x180010071  lea     eax, [rcx+1]
0x180010074  mov     [rbx+64h], eax
0x180010077  xor     eax, eax
0x180010079  jmp     short loc_18001007F
0x18001007b  mov     ecx, [rsp+28h+arg_8]
0x18001007f  test    rdi, rdi
0x180010082  jz      short loc_180010086
0x180010084  mov     [rdi], ecx
0x180010086  mov     rbx, [rsp+28h+arg_0]
0x18001008b  mov     rsi, [rsp+28h+arg_10]
0x180010090  add     rsp, 20h
0x180010094  pop     rdi
0x180010095  retn
```
