# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009620`
- end: `0x1800096db`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046b0`
- `0x180009bac`
- `0x18000fe60`

## callees

- `0x180009620`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180009620  mov     [rsp+arg_0], rbx
0x180009625  mov     [rsp+arg_8], rdi
0x18000962a  lea     rax, [rdx-1]
0x18000962e  mov     r10d, 7FFFFFFEh
0x180009634  mov     r9, rdx
0x180009637  mov     rbx, rcx
0x18000963a  cmp     rax, r10
0x18000963d  ja      loc_1800096C9
0x180009643  mov     r11, rdx
0x180009646  mov     rax, rcx
0x180009649  xor     edi, edi
0x18000964b  cmp     [rax], di
0x18000964e  jz      short loc_18000965A
0x180009650  add     rax, 2
0x180009654  sub     r11, 1
0x180009658  jnz     short loc_18000964B
0x18000965a  mov     rax, r11
0x18000965d  mov     rcx, r9
0x180009660  neg     rax
0x180009663  mov     rax, r11
0x180009666  sbb     edx, edx
0x180009668  sub     rcx, r11
0x18000966b  not     edx
0x18000966d  and     edx, 80070057h
0x180009673  neg     rax
0x180009676  sbb     rax, rax
0x180009679  and     rax, rcx
0x18000967c  test    r11, r11
0x18000967f  jz      short loc_1800096CE
0x180009681  sub     r9, rax
0x180009684  lea     rax, [rbx+rax*2]
0x180009688  jz      short loc_1800096AC
0x18000968a  test    r10, r10
0x18000968d  jz      short loc_1800096AC
0x18000968f  movzx   ecx, word ptr [r8]
0x180009693  test    cx, cx
0x180009696  jz      short loc_1800096AC
0x180009698  mov     [rax], cx
0x18000969b  add     r8, 2
0x18000969f  add     rax, 2
0x1800096a3  dec     r10
0x1800096a6  sub     r9, 1
0x1800096aa  jnz     short loc_18000968A
0x1800096ac  test    r9, r9
0x1800096af  lea     rcx, [rax-2]
0x1800096b3  cmovnz  rcx, rax
0x1800096b7  neg     r9
0x1800096ba  sbb     edx, edx
0x1800096bc  not     edx
0x1800096be  and     edx, 8007007Ah
0x1800096c4  mov     [rcx], di
0x1800096c7  jmp     short loc_1800096CE
0x1800096c9  mov     edx, 80070057h
0x1800096ce  mov     rbx, [rsp+arg_0]
0x1800096d3  mov     eax, edx
0x1800096d5  mov     rdi, [rsp+arg_8]
0x1800096da  retn
```
