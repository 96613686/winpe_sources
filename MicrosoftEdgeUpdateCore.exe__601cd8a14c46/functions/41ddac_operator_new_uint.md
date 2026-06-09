# operator new(uint)

- ea: `0x41ddac`
- end: `0x41dddc`
- name: `??2@YAPAXI@Z`
- size: `48`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x4033e3`
- `0x40342c`
- `0x403b59`
- `0x406d01`
- `0x406d60`
- `0x406e57`
- `0x40a793`
- `0x40b888`
- `0x40b905`
- `0x40c4c2`
- `0x40c744`
- `0x40cd6a`
- `0x40ce15`
- `0x41dddc`

## callees

- `0x4116f4`
- `0x4154e4`
- `0x41ddac`
- `0x41de63`
- `0x41de80`

## pseudocode

```c
void *__cdecl operator new(size_t Size)
{
  void *result; // eax

  while ( 1 )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !_callnewh(Size) )
    {
      if ( Size != -1 )
        sub_41DE63();
      sub_41DE80();
    }
  }
  return result;
}

```

## disassembly

```asm
0x41ddac  push    ebp
0x41ddad  mov     ebp, esp
0x41ddaf  jmp     short loc_41DDBE
0x41ddb1  push    [ebp+Size]; Size
0x41ddb4  call    __callnewh
0x41ddb9  pop     ecx
0x41ddba  test    eax, eax
0x41ddbc  jz      short loc_41DDCD
0x41ddbe  push    [ebp+Size]; Size
0x41ddc1  call    _malloc
0x41ddc6  pop     ecx
0x41ddc7  test    eax, eax
0x41ddc9  jz      short loc_41DDB1
0x41ddcb  pop     ebp
0x41ddcc  retn
0x41ddcd  cmp     [ebp+Size], 0FFFFFFFFh
0x41ddd1  jz      sub_41DE80
0x41ddd7  jmp     sub_41DE63
```
