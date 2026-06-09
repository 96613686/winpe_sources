# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180003180`
- end: `0x180003211`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `145`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a5c`
- `0x18000631c`
- `0x1800071c0`
- `0x1800079c0`
- `0x180008cf0`
- `0x18000ae68`
- `0x18000ced8`
- `0x180010050`
- `0x180010d50`
- `0x1800115b0`
- `0x180011940`
- `0x1800126c0`
- `0x1800127bc`
- `0x1800151d8`
- `0x1800152d8`
- `0x180015d34`
- `0x180016094`
- `0x180016ad0`
- `0x180016c0c`
- `0x180016e3c`
- `0x180018ca8`
- `0x18001ad74`

## callees

- `0x180003180`
- `0x180003654`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // r9
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // r8

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
    if ( v5 )
    {
      v8 = (a2 - v5) & -(__int64)(v5 != 0);
      return (unsigned int)StringCopyWorkerW_0(&a1[v8], a2 - v8, 0, a3, 0x7FFFFFFEu);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003180  mov     [rsp+arg_0], rbx
0x180003185  push    rdi
0x180003186  sub     rsp, 30h
0x18000318a  lea     rax, [rdx-1]
0x18000318e  mov     rbx, r8
0x180003191  mov     r10, rdx
0x180003194  mov     r11, rcx
0x180003197  cmp     rax, 7FFFFFFEh
0x18000319d  ja      short loc_1800031FF
0x18000319f  mov     r9, rdx
0x1800031a2  mov     rax, rcx
0x1800031a5  xor     edi, edi
0x1800031a7  cmp     [rax], di
0x1800031aa  jz      short loc_1800031B6
0x1800031ac  add     rax, 2
0x1800031b0  sub     r9, 1
0x1800031b4  jnz     short loc_1800031A7
0x1800031b6  mov     rax, r9
0x1800031b9  mov     rcx, r10
0x1800031bc  neg     rax
0x1800031bf  mov     rax, r9
0x1800031c2  sbb     edx, edx
0x1800031c4  sub     rcx, r9
0x1800031c7  not     edx
0x1800031c9  and     edx, 80070057h
0x1800031cf  neg     rax
0x1800031d2  sbb     r8, r8
0x1800031d5  and     r8, rcx
0x1800031d8  test    r9, r9
0x1800031db  jz      short loc_180003204
0x1800031dd  sub     r10, r8
0x1800031e0  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800031e9  lea     rcx, [r11+r8*2]; pszDest
0x1800031ed  mov     rdx, r10; cchDest
0x1800031f0  mov     r9, rbx; pszSrc
0x1800031f3  xor     r8d, r8d; pcchNewDestLength
0x1800031f6  call    StringCopyWorkerW_0
0x1800031fb  mov     edx, eax
0x1800031fd  jmp     short loc_180003204
0x1800031ff  mov     edx, 80070057h
0x180003204  mov     rbx, [rsp+38h+arg_0]
0x180003209  mov     eax, edx
0x18000320b  add     rsp, 30h
0x18000320f  pop     rdi
0x180003210  retn
```
