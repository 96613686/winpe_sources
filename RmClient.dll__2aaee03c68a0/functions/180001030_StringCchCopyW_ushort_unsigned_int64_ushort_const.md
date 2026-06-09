# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001030`
- end: `0x18000109d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b50`
- `0x18001607c`

## callees

- `0x180001030`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001030  mov     r9, rcx
0x180001033  test    rdx, rdx
0x180001036  jz      short loc_18000108C
0x180001038  cmp     rdx, 7FFFFFFFh
0x18000103f  ja      short loc_180001085
0x180001041  mov     eax, 7FFFFFFEh
0x180001046  test    rax, rax
0x180001049  jz      short loc_180001069
0x18000104b  movzx   ecx, word ptr [r8]
0x18000104f  test    cx, cx
0x180001052  jz      short loc_180001069
0x180001054  mov     [r9], cx
0x180001058  add     r8, 2
0x18000105c  add     r9, 2
0x180001060  dec     rax
0x180001063  sub     rdx, 1
0x180001067  jnz     short loc_180001046
0x180001069  test    rdx, rdx
0x18000106c  lea     rax, [r9-2]
0x180001070  cmovnz  rax, r9
0x180001074  xor     ecx, ecx
0x180001076  test    rdx, rdx
0x180001079  mov     [rax], cx
0x18000107c  mov     eax, 8007007Ah
0x180001081  cmovnz  eax, ecx
0x180001084  retn
0x180001085  mov     eax, 80070057h
0x18000108a  jmp     short loc_180001096
0x18000108c  mov     eax, 80070057h
0x180001091  test    rdx, rdx
0x180001094  jz      short locret_180001084
0x180001096  xor     ecx, ecx
0x180001098  mov     [r9], cx
0x18000109c  retn
```
