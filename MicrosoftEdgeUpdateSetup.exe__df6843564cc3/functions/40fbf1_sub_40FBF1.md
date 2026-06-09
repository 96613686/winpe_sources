# sub_40FBF1

- ea: `0x40fbf1`
- end: `0x40fc3a`
- name: `sub_40FBF1`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40fbf1`

## pseudocode

```c
int __cdecl sub_40FBF1(char a1)
{
  int result; // eax
  char v2; // zf
  _DWORD v3[3]; // [esp+0h] [ebp-20h] BYREF
  int v4; // [esp+Ch] [ebp-14h] BYREF
  int v5; // [esp+10h] [ebp-10h] BYREF
  int v6; // [esp+14h] [ebp-Ch] BYREF
  int v7; // [esp+18h] [ebp-8h] BYREF
  char v8; // [esp+1Fh] [ebp-1h] BYREF

  v7 = 0;
  v6 = 0;
  v3[0] = &v7;
  v3[1] = &a1;
  v3[2] = &v6;
  v5 = 8;
  v4 = 8;
  MEMORY[0x4979B0](&v8, &v4, v3, &v5);
  result = v7;
  if ( v2 )
    return v6;
  return result;
}

```

## disassembly

```asm
0x40fbf1  mov     edi, edi
0x40fbf3  push    ebp
0x40fbf4  mov     ebp, esp
0x40fbf6  sub     esp, 20h
0x40fbf9  and     [ebp+var_8], 0
0x40fbfd  lea     eax, [ebp+var_8]
0x40fc00  and     [ebp+var_C], 0
0x40fc04  lea     ecx, [ebp+var_1]
0x40fc07  mov     [ebp+var_20], eax
0x40fc0a  lea     eax, [ebp+arg_0]
0x40fc0d  mov     [ebp+var_1C], eax
0x40fc10  lea     eax, [ebp+var_C]
0x40fc13  push    8
0x40fc15  mov     [ebp+var_18], eax
0x40fc18  pop     eax
0x40fc19  mov     [ebp+var_10], eax
0x40fc1c  mov     [ebp+var_14], eax
0x40fc1f  lea     eax, [ebp+var_10]
0x40fc22  push    eax
0x40fc23  lea     eax, [ebp+var_20]
0x40fc26  push    eax
0x40fc27  lea     eax, [ebp+var_14]
0x40fc2a  push    eax
0x40fc2b  call    near ptr 4979B0h
0x40fc30  mov     eax, [ebp+var_8]
0x40fc33  jnz     short locret_40FC38
0x40fc35  mov     eax, [ebp+var_C]
0x40fc38  leave
0x40fc39  retn
```
