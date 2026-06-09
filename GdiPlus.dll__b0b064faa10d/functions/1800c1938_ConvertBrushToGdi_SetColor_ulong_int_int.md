# ConvertBrushToGdi::SetColor(ulong,int,int)

- ea: `0x1800c1938`
- end: `0x1800c19f9`
- name: `?SetColor@ConvertBrushToGdi@@QEAAXKHH@Z`
- size: `193`
- prototype: `void(ConvertBrushToGdi *__hidden this, unsigned int, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180050220`
- `0x1800d4420`
- `0x1800eabe0`
- `0x1800efc08`
- `0x18013a7c0`
- `0x18013ac6c`

## callees

- `0x18004ff14`
- `0x1800c1938`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800c198e`
- `GDI32!CreateSolidBrush` at `0x1800c198e`
- `GDI32!GetStockObject` at `0x1800c19ba`
- `GDI32!GetStockObject` at `0x1800c19ba`
- `GDI32!DeleteObject` at `0x1800c19cc`
- `GDI32!DeleteObject` at `0x1800c19db`
- `GDI32!DeleteObject` at `0x1800c19cc`
- `GDI32!DeleteObject` at `0x1800c19db`

## pseudocode

```c
void __fastcall ConvertBrushToGdi::SetColor(ConvertBrushToGdi *this, COLORREF a2, int a3, int a4)
{
  _DWORD *v4; // rdi
  COLORREF v5; // ebp
  _QWORD *v9; // rsi
  HBRUSH SolidBrush; // rax

  v4 = (_DWORD *)((char *)this + 4);
  v5 = a2 | 0x2000000;
  if ( !a4 )
    v5 = a2;
  if ( *(_DWORD *)this == 1198932785 )
  {
    if ( !*v4 && v5 == *((_DWORD *)this + 5) )
      return;
    v9 = (_QWORD *)((char *)this + 8);
    DeleteObject(*((HGDIOBJ *)this + 1));
    if ( *v4 == 2 )
    {
      DeleteObject(*((HGDIOBJ *)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
  }
  else
  {
    v9 = (_QWORD *)((char *)this + 8);
  }
  *v4 = 0;
  if ( a4 || !a3 )
    SolidBrush = CreateSolidBrush(v5);
  else
    SolidBrush = ConvertBrushToGdi::CreateHalftoneBrush(v5);
  *v9 = SolidBrush;
  *((_DWORD *)this + 5) = v5;
  *(_DWORD *)this = SolidBrush != 0 ? 1198932785 : 1279869254;
  if ( !SolidBrush )
    *v9 = GetStockObject(2);
}

```

## disassembly

```asm
0x1800c1938  push    rbx
0x1800c193a  push    rbp
0x1800c193b  push    rsi
0x1800c193c  push    rdi
0x1800c193d  push    r14
0x1800c193f  push    r15
0x1800c1941  sub     rsp, 28h
0x1800c1945  mov     ebp, edx
0x1800c1947  lea     rdi, [rcx+4]
0x1800c194b  bts     ebp, 19h
0x1800c194f  mov     r14d, r9d
0x1800c1952  test    r9d, r9d
0x1800c1955  mov     r15d, r8d
0x1800c1958  mov     rbx, rcx
0x1800c195b  cmovz   ebp, edx
0x1800c195e  cmp     dword ptr [rcx], 47764331h
0x1800c1964  jnz     short loc_1800C197D
0x1800c1966  cmp     dword ptr [rdi], 0
0x1800c1969  jnz     short loc_1800C19C5
0x1800c196b  cmp     ebp, [rcx+14h]
0x1800c196e  jnz     short loc_1800C19C5
0x1800c1970  add     rsp, 28h
0x1800c1974  pop     r15
0x1800c1976  pop     r14
0x1800c1978  pop     rdi
0x1800c1979  pop     rsi
0x1800c197a  pop     rbp
0x1800c197b  pop     rbx
0x1800c197c  retn
0x1800c197d  lea     rsi, [rcx+8]
0x1800c1981  mov     dword ptr [rdi], 0
0x1800c1987  test    r14d, r14d
0x1800c198a  jz      short loc_1800C19EB
0x1800c198c  mov     ecx, ebp; color
0x1800c198e  call    cs:__imp_CreateSolidBrush
0x1800c1994  mov     [rsi], rax
0x1800c1997  mov     rcx, rax
0x1800c199a  neg     rax
0x1800c199d  mov     [rbx+14h], ebp
0x1800c19a0  sbb     edx, edx
0x1800c19a2  and     edx, 0FB2D01EBh
0x1800c19a8  add     edx, 4C494146h
0x1800c19ae  mov     [rbx], edx
0x1800c19b0  test    rcx, rcx
0x1800c19b3  jnz     short loc_1800C1970
0x1800c19b5  mov     ecx, 2; i
0x1800c19ba  call    cs:__imp_GetStockObject
0x1800c19c0  mov     [rsi], rax
0x1800c19c3  jmp     short loc_1800C1970
0x1800c19c5  lea     rsi, [rcx+8]
0x1800c19c9  mov     rcx, [rsi]; ho
0x1800c19cc  call    cs:__imp_DeleteObject
0x1800c19d2  cmp     dword ptr [rdi], 2
0x1800c19d5  jnz     short loc_1800C1981
0x1800c19d7  mov     rcx, [rbx+18h]; ho
0x1800c19db  call    cs:__imp_DeleteObject
0x1800c19e1  mov     qword ptr [rbx+18h], 0
0x1800c19e9  jmp     short loc_1800C1981
0x1800c19eb  test    r15d, r15d
0x1800c19ee  jz      short loc_1800C198C
0x1800c19f0  mov     ecx, ebp; unsigned int
0x1800c19f2  call    ?CreateHalftoneBrush@ConvertBrushToGdi@@SAPEAUHBRUSH__@@K@Z; ConvertBrushToGdi::CreateHalftoneBrush(ulong)
0x1800c19f7  jmp     short loc_1800C1994
```
