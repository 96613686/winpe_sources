# sub_40C5ED

- ea: `0x40c5ed`
- end: `0x40c622`
- name: `sub_40C5ED`
- size: `53`
- prototype: `int __stdcall(int)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x40b190`
- `0x40b240`
- `0x40b2f0`
- `0x40b370`
- `0x40b3f0`
- `0x40b470`
- `0x40b4f0`
- `0x40b570`
- `0x40b5f0`

## callees

- `0x40c5ed`
- `0x40c8e3`
- `0x40c939`
- `0x41df9a`

## pseudocode

```c
int __stdcall sub_40C5ED(int a1)
{
  int v1; // esi
  _BYTE v3[8]; // [esp+4h] [ebp-Ch] BYREF
  int v4; // [esp+Ch] [ebp-4h]

  sub_40C8E3(v3, a1);
  v1 = v4;
  if ( !(unsigned __int8)sub_40C939(v4, a1) )
    sub_41DF9A("invalid map<K, T> key");
  return v1 + 32;
}

```

## disassembly

```asm
0x40c5ed  push    ebp
0x40c5ee  mov     ebp, esp
0x40c5f0  sub     esp, 0Ch
0x40c5f3  push    esi
0x40c5f4  push    [ebp+arg_0]
0x40c5f7  lea     eax, [ebp+var_C]
0x40c5fa  push    eax
0x40c5fb  call    sub_40C8E3
0x40c600  push    [ebp+arg_0]
0x40c603  mov     esi, [ebp+var_4]
0x40c606  push    esi
0x40c607  call    sub_40C939
0x40c60c  test    al, al
0x40c60e  jz      short loc_40C618
0x40c610  lea     eax, [esi+20h]
0x40c613  pop     esi
0x40c614  leave
0x40c615  retn    4
0x40c618  push    offset aInvalidMapKTKe; "invalid map<K, T> key"
0x40c61d  call    sub_41DF9A
```
