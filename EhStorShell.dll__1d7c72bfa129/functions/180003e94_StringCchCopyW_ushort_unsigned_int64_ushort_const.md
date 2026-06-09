# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180003e94`
- end: `0x180003eff`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adb4`

## callees

- `0x180003e94`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
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
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180003e94  xor     r10d, r10d
0x180003e97  mov     r9, rcx
0x180003e9a  test    rdx, rdx
0x180003e9d  jz      short loc_180003EF3
0x180003e9f  cmp     rdx, 7FFFFFFFh
0x180003ea6  ja      short loc_180003EEC
0x180003ea8  mov     eax, 7FFFFFFEh
0x180003ead  test    rax, rax
0x180003eb0  jz      short loc_180003ED0
0x180003eb2  movzx   ecx, word ptr [r8]
0x180003eb6  test    cx, cx
0x180003eb9  jz      short loc_180003ED0
0x180003ebb  mov     [r9], cx
0x180003ebf  add     r8, 2
0x180003ec3  add     r9, 2
0x180003ec7  dec     rax
0x180003eca  sub     rdx, 1
0x180003ece  jnz     short loc_180003EAD
0x180003ed0  test    rdx, rdx
0x180003ed3  lea     rcx, [r9-2]
0x180003ed7  cmovnz  rcx, r9
0x180003edb  neg     rdx
0x180003ede  sbb     eax, eax
0x180003ee0  not     eax
0x180003ee2  and     eax, 8007007Ah
0x180003ee7  mov     [rcx], r10w
0x180003eeb  retn
0x180003eec  mov     eax, 80070057h
0x180003ef1  jmp     short loc_180003EE7
0x180003ef3  mov     eax, 80070057h
0x180003ef8  test    rdx, rdx
0x180003efb  jz      short locret_180003EEB
0x180003efd  jmp     short loc_180003EE7
```
