# operator new(unsigned __int64)

- ea: `0x14001bf28`
- end: `0x14001bf64`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `49`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c258`
- `0x140025158`
- `0x1400251e8`
- `0x140026498`
- `0x140026868`
- `0x140027a5c`
- `0x140028510`
- `0x14002fdd4`
- `0x1400315f0`
- `0x1400320b4`
- `0x14003221c`
- `0x140032378`
- `0x1400325b4`
- `0x140035864`
- `0x140036858`
- `0x140037108`
- `0x14003760c`
- `0x140037710`
- `0x140037b54`
- `0x14003bbd8`
- `0x14003fbec`
- `0x14003ff70`
- `0x140041c60`
- `0x140043d0c`
- `0x140043ec0`
- `0x14004418c`
- `0x1400442b8`
- `0x1400443b8`
- `0x140044bb0`
- `0x140045690`
- `0x140045960`
- `0x1400464e8`
- `0x140049194`
- `0x140049364`
- `0x14004944c`
- `0x14004ab84`
- `0x14004afc0`
- `0x14004b7f8`
- `0x14004b968`
- `0x14004bf50`
- `0x14004cc1c`
- `0x14004d864`
- `0x1400a3c3c`
- `0x1400a3d90`
- `0x1400a40e8`
- `0x1400a4200`
- `0x1400a8f70`
- `0x1400a8fa0`
- `0x1400ac33c`

## callees

- `0x140015050`
- `0x14001bf28`
- `0x14001cd1c`
- `0x140022c30`
- `0x140026dbc`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = j__malloc_base(Size);
    if ( result )
      break;
    if ( !(unsigned int)sub_140015050(i) )
    {
      if ( i != -1 )
        sub_14001CD1C();
      sub_140026DBC();
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001bf28  push    rbx
0x14001bf2a  sub     rsp, 20h
0x14001bf2e  mov     rbx, rcx
0x14001bf31  jmp     short loc_14001BF42
0x14001bf33  mov     rcx, rbx
0x14001bf36  call    sub_140015050
0x14001bf3b  test    eax, eax
0x14001bf3d  jz      short loc_14001BF52
0x14001bf3f  mov     rcx, rbx; Size
0x14001bf42  call    j__malloc_base
0x14001bf47  test    rax, rax
0x14001bf4a  jz      short loc_14001BF33
0x14001bf4c  add     rsp, 20h
0x14001bf50  pop     rbx
0x14001bf51  retn
0x14001bf52  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001bf56  jz      short loc_14001BF5E
0x14001bf58  call    sub_14001CD1C
0x14001bf5e  call    sub_140026DBC
```
