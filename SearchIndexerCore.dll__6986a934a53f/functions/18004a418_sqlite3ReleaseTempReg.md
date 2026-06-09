# sqlite3ReleaseTempReg

- ea: `0x18004a418`
- end: `0x18004a432`
- name: `sqlite3ReleaseTempReg`
- size: `26`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x180005650`
- `0x18000f0fc`
- `0x180016ef0`
- `0x180017938`
- `0x180019470`
- `0x18001cb6c`
- `0x18004a34c`
- `0x18004a3f8`
- `0x18004b7cc`
- `0x1800504a8`
- `0x1800544ac`
- `0x18005a538`
- `0x180062494`
- `0x180064df4`
- `0x180067500`
- `0x18006a950`
- `0x18006cc88`
- `0x18006fafc`
- `0x1800711f4`
- `0x180072020`
- `0x18007406c`
- `0x1800751b0`
- `0x18007ee44`
- `0x18007f9a0`
- `0x18007fcec`
- `0x180081778`
- `0x18008f958`
- `0x180090b7c`
- `0x1800a514c`
- `0x1800a55d4`
- `0x1800a5744`
- `0x1800a5a50`
- `0x1800a5eb8`
- `0x1800a6344`

## callees

- `0x18004a418`

## pseudocode

```c
__int64 __fastcall sqlite3ReleaseTempReg(__int64 a1, int a2)
{
  __int64 result; // rax

  if ( a2 )
  {
    if ( *(_BYTE *)(a1 + 31) < 8u )
    {
      result = *(unsigned __int8 *)(a1 + 31);
      *(_DWORD *)(a1 + 4 * result + 232) = a2;
      ++*(_BYTE *)(a1 + 31);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004a418  test    edx, edx
0x18004a41a  jnz     short loc_18004A41D
0x18004a41c  retn
0x18004a41d  cmp     byte ptr [rcx+1Fh], 8
0x18004a421  jnb     short locret_18004A41C
0x18004a423  movzx   eax, byte ptr [rcx+1Fh]
0x18004a427  mov     [rcx+rax*4+0E8h], edx
0x18004a42e  inc     byte ptr [rcx+1Fh]
0x18004a431  retn
```
