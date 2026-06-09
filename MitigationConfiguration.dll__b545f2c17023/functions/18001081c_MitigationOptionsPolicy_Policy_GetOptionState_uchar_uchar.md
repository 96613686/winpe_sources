# MitigationOptionsPolicy::Policy::GetOptionState(uchar,uchar)

- ea: `0x18001081c`
- end: `0x180010865`
- name: `?GetOptionState@Policy@MitigationOptionsPolicy@@KAEEE@Z`
- size: `73`
- prototype: `char __fastcall(char, char)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007918`
- `0x18001225c`
- `0x1800122c4`
- `0x180012334`
- `0x18001239c`
- `0x180012404`
- `0x18001246c`
- `0x1800124d4`
- `0x180012754`
- `0x180012fa4`

## callees

- `0x18001081c`

## pseudocode

```c
char __fastcall MitigationOptionsPolicy::Policy::GetOptionState(char a1, char a2)
{
  char v2; // r8

  v2 = 0;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v2 = 2;
    }
    else if ( a1 == 2 )
    {
      v2 = 4;
    }
  }
  else
  {
    v2 = 1;
  }
  switch ( a2 )
  {
    case 0:
      return v2 | 0x10;
    case 1:
      return v2 | 0x20;
    case 2:
      return v2 | 0x40;
  }
  return v2;
}

```

## disassembly

```asm
0x18001081c  xor     r8b, r8b
0x18001081f  movzx   r9d, cl
0x180010823  test    cl, cl
0x180010825  jz      short loc_18001083D
0x180010827  sub     r9d, 1
0x18001082b  jz      short loc_180010838
0x18001082d  cmp     r9d, 1
0x180010831  jnz     short loc_180010840
0x180010833  mov     r8b, 4
0x180010836  jmp     short loc_180010840
0x180010838  mov     r8b, 2
0x18001083b  jmp     short loc_180010840
0x18001083d  mov     r8b, 1
0x180010840  movzx   ecx, dl
0x180010843  test    dl, dl
0x180010845  jz      short loc_18001085D
0x180010847  sub     ecx, 1
0x18001084a  jz      short loc_180010857
0x18001084c  cmp     ecx, 1
0x18001084f  jnz     short loc_180010861
0x180010851  or      r8b, 40h
0x180010855  jmp     short loc_180010861
0x180010857  or      r8b, 20h
0x18001085b  jmp     short loc_180010861
0x18001085d  or      r8b, 10h
0x180010861  mov     al, r8b
0x180010864  retn
```
