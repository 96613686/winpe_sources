# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004144`
- end: `0x1400041ed`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002898`
- `0x140004570`

## callees

- `0x140004144`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140004144  mov     [rsp+arg_0], rbx
0x140004149  mov     [rsp+arg_8], rdi
0x14000414e  mov     r9d, 104h
0x140004154  mov     rbx, rcx
0x140004157  mov     r10d, r9d
0x14000415a  mov     rax, rcx
0x14000415d  xor     edi, edi
0x14000415f  cmp     [rax], di
0x140004162  jz      short loc_14000416E
0x140004164  add     rax, 2
0x140004168  sub     r10, 1
0x14000416c  jnz     short loc_14000415F
0x14000416e  mov     rax, r10
0x140004171  mov     rcx, r9
0x140004174  neg     rax
0x140004177  mov     rax, r10
0x14000417a  sbb     edx, edx
0x14000417c  sub     rcx, r10
0x14000417f  not     edx
0x140004181  and     edx, 80070057h
0x140004187  neg     rax
0x14000418a  sbb     r11, r11
0x14000418d  and     r11, rcx
0x140004190  test    r10, r10
0x140004193  jz      short loc_1400041E0
0x140004195  lea     rax, [rbx+r11*2]
0x140004199  mov     ecx, 7FFFFFFEh
0x14000419e  sub     r9, r11
0x1400041a1  jz      short loc_1400041C5
0x1400041a3  test    rcx, rcx
0x1400041a6  jz      short loc_1400041C5
0x1400041a8  movzx   edx, word ptr [r8]
0x1400041ac  test    dx, dx
0x1400041af  jz      short loc_1400041C5
0x1400041b1  mov     [rax], dx
0x1400041b4  add     r8, 2
0x1400041b8  add     rax, 2
0x1400041bc  dec     rcx
0x1400041bf  sub     r9, 1
0x1400041c3  jnz     short loc_1400041A3
0x1400041c5  test    r9, r9
0x1400041c8  lea     rcx, [rax-2]
0x1400041cc  cmovnz  rcx, rax
0x1400041d0  neg     r9
0x1400041d3  sbb     edx, edx
0x1400041d5  not     edx
0x1400041d7  and     edx, 8007007Ah
0x1400041dd  mov     [rcx], di
0x1400041e0  mov     rbx, [rsp+arg_0]
0x1400041e5  mov     eax, edx
0x1400041e7  mov     rdi, [rsp+arg_8]
0x1400041ec  retn
```
