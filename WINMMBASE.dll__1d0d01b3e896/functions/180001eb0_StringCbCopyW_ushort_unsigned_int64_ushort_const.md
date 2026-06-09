# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001eb0`
- end: `0x180001f1d`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002460`
- `0x180007dd0`
- `0x18000e1c0`
- `0x180019c9c`

## callees

- `0x180001eb0`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  unsigned __int16 *v4; // r9
  __int64 v5; // rax
  unsigned __int16 *v6; // rax
  __int64 result; // rax

  v3 = a2 >> 1;
  v4 = a1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v4++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = v4 - 1;
    if ( v3 )
      v6 = v4;
    *v6 = 0;
    result = 2147942522LL;
    if ( v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001eb0  shr     rdx, 1
0x180001eb3  mov     r9, rcx
0x180001eb6  jz      short loc_180001F0C
0x180001eb8  cmp     rdx, 7FFFFFFFh
0x180001ebf  ja      short loc_180001F05
0x180001ec1  mov     eax, 7FFFFFFEh
0x180001ec6  test    rax, rax
0x180001ec9  jz      short loc_180001EE9
0x180001ecb  movzx   ecx, word ptr [r8]
0x180001ecf  test    cx, cx
0x180001ed2  jz      short loc_180001EE9
0x180001ed4  mov     [r9], cx
0x180001ed8  add     r8, 2
0x180001edc  add     r9, 2
0x180001ee0  dec     rax
0x180001ee3  sub     rdx, 1
0x180001ee7  jnz     short loc_180001EC6
0x180001ee9  test    rdx, rdx
0x180001eec  lea     rax, [r9-2]
0x180001ef0  cmovnz  rax, r9
0x180001ef4  xor     ecx, ecx
0x180001ef6  test    rdx, rdx
0x180001ef9  mov     [rax], cx
0x180001efc  mov     eax, 8007007Ah
0x180001f01  cmovnz  eax, ecx
0x180001f04  retn
0x180001f05  mov     eax, 80070057h
0x180001f0a  jmp     short loc_180001F16
0x180001f0c  mov     eax, 80070057h
0x180001f11  test    rdx, rdx
0x180001f14  jz      short locret_180001F04
0x180001f16  xor     ecx, ecx
0x180001f18  mov     [r9], cx
0x180001f1c  retn
```
