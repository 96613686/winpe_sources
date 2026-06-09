# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18001115c`
- end: `0x180011242`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `230`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fa4c`

## callees

- `0x18000a19a`
- `0x18001115c`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v4; // ebx

  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v4 = -2147024809;
LABEL_7:
    *a1 = 0;
    return v4;
  }
  if ( a4 < 0x7FFFFFFF )
  {
    v4 = 0;
    if ( a2 )
    {
      *a1 = 0;
      v4 = a2 == 0 ? 0x8007007A : 0;
      if ( a2 > 1 && 2 * a2 > 2 )
        memset_0(a1 + 1, 0, 2 * a2 - 2);
    }
  }
  else
  {
    v4 = -2147024809;
    if ( a2 )
      goto LABEL_7;
  }
  return v4;
}

```

## disassembly

```asm
0x18001115c  mov     [rsp+arg_0], rbx
0x180011161  push    rdi
0x180011162  sub     rsp, 20h
0x180011166  xor     edi, edi
0x180011168  mov     r10, rcx
0x18001116b  test    rcx, rcx
0x18001116e  jnz     short loc_180011175
0x180011170  test    rdx, rdx
0x180011173  jnz     short loc_18001117F
0x180011175  mov     eax, 7FFFFFFFh
0x18001117a  cmp     rdx, rax
0x18001117d  jbe     short loc_180011186
0x18001117f  mov     ebx, 80070057h
0x180011184  jmp     short loc_180011199
0x180011186  cmp     r9, rax
0x180011189  jb      short loc_1800111A1
0x18001118b  mov     ebx, 80070057h
0x180011190  test    rdx, rdx
0x180011193  jz      loc_180011235
0x180011199  mov     [rcx], di
0x18001119c  jmp     loc_180011235
0x1800111a1  mov     ebx, edi
0x1800111a3  test    rdx, rdx
0x1800111a6  jz      loc_180011235
0x1800111ac  mov     rcx, rdi
0x1800111af  lea     r9, qword_180015460
0x1800111b6  mov     r8, rdx
0x1800111b9  mov     rax, r10
0x1800111bc  mov     r11, rdi
0x1800111bf  test    rcx, rcx
0x1800111c2  jz      short loc_1800111E4
0x1800111c4  movzx   ebx, word ptr [r9]
0x1800111c8  test    bx, bx
0x1800111cb  jz      short loc_1800111E4
0x1800111cd  mov     [rax], bx
0x1800111d0  add     r9, 2
0x1800111d4  add     rax, 2
0x1800111d8  dec     rcx
0x1800111db  inc     r11
0x1800111de  sub     r8, 1
0x1800111e2  jnz     short loc_1800111BF
0x1800111e4  test    r8, r8
0x1800111e7  lea     rcx, [rax-2]
0x1800111eb  lea     r9, [r11-1]
0x1800111ef  cmovnz  rcx, rax
0x1800111f3  cmovnz  r9, r11
0x1800111f7  mov     rax, r8
0x1800111fa  neg     rax
0x1800111fd  sbb     ebx, ebx
0x1800111ff  mov     [rcx], di
0x180011202  not     ebx
0x180011204  and     ebx, 8007007Ah
0x18001120a  test    r8, r8
0x18001120d  jz      short loc_180011235
0x18001120f  sub     rdx, r9
0x180011212  cmp     rdx, 1
0x180011216  jbe     short loc_180011235
0x180011218  lea     r8, [rdx+rdx]
0x18001121c  cmp     r8, 2
0x180011220  jbe     short loc_180011235
0x180011222  add     r10, 2
0x180011226  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001122a  xor     edx, edx; Val
0x18001122c  lea     rcx, [r10+r9*2]; void *
0x180011230  call    memset_0
0x180011235  mov     eax, ebx
0x180011237  mov     rbx, [rsp+28h+arg_0]
0x18001123c  add     rsp, 20h
0x180011240  pop     rdi
0x180011241  retn
```
