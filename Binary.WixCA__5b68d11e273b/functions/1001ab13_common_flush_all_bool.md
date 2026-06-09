# common_flush_all(bool)

- ea: `0x1001ab13`
- end: `0x1001ab62`
- name: `?common_flush_all@@YAH_N@Z`
- size: `79`
- prototype: `int __cdecl(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1001ac1f`
- `0x1001ac67`

## callees

- `0x1001aa71`
- `0x1001ab13`

## pseudocode

```c
int __cdecl common_flush_all(bool a1)
{
  int result; // eax
  _DWORD v2[3]; // [esp+0h] [ebp-20h] BYREF
  int v3; // [esp+Ch] [ebp-14h] BYREF
  int v4; // [esp+10h] [ebp-10h] BYREF
  int v5; // [esp+14h] [ebp-Ch] BYREF
  int v6; // [esp+18h] [ebp-8h] BYREF

  v6 = 0;
  v5 = 0;
  v2[0] = &v6;
  v2[1] = &a1;
  v2[2] = &v5;
  v4 = 8;
  v3 = 8;
  sub_1001AA71(&v3, v2, &v4);
  result = v6;
  if ( !a1 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x1001ab13  mov     edi, edi
0x1001ab15  push    ebp
0x1001ab16  mov     ebp, esp
0x1001ab18  sub     esp, 20h
0x1001ab1b  and     [ebp+var_8], 0
0x1001ab1f  lea     eax, [ebp+var_8]
0x1001ab22  and     [ebp+var_C], 0
0x1001ab26  lea     ecx, [ebp+var_1]
0x1001ab29  mov     [ebp+var_20], eax
0x1001ab2c  lea     eax, [ebp+arg_0]
0x1001ab2f  mov     [ebp+var_1C], eax
0x1001ab32  lea     eax, [ebp+var_C]
0x1001ab35  push    8
0x1001ab37  mov     [ebp+var_18], eax
0x1001ab3a  pop     eax
0x1001ab3b  mov     [ebp+var_10], eax
0x1001ab3e  mov     [ebp+var_14], eax
0x1001ab41  lea     eax, [ebp+var_10]
0x1001ab44  push    eax
0x1001ab45  lea     eax, [ebp+var_20]
0x1001ab48  push    eax
0x1001ab49  lea     eax, [ebp+var_14]
0x1001ab4c  push    eax
0x1001ab4d  call    sub_1001AA71
0x1001ab52  cmp     [ebp+arg_0], 0
0x1001ab56  mov     eax, [ebp+var_8]
0x1001ab59  jnz     short loc_1001AB5E
0x1001ab5b  mov     eax, [ebp+var_C]
0x1001ab5e  mov     esp, ebp
0x1001ab60  pop     ebp
0x1001ab61  retn
```
