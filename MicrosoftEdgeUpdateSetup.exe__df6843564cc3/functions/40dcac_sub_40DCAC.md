# sub_40DCAC

- ea: `0x40dcac`
- end: `0x40dd0d`
- name: `sub_40DCAC`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40dcac`

## pseudocode

```c
int __cdecl sub_40DCAC(_DWORD *a1)
{
  _BYTE *v1; // esi
  int result; // eax
  int v3; // ecx
  int v4; // ecx
  int v5; // edi
  _BYTE *v6; // ecx
  int v7; // edx

  v1 = a1 + 6;
  result = MEMORY[0x33455851](a1 + 6, 0, 257);
  *(_BYTE *)(v3 - 998045573) = __ROR1__(*(_BYTE *)(v3 - 998045573), 12);
  a1[135] = 0;
  v4 = 257;
  a1[3] = result;
  a1[4] = result;
  a1[5] = result;
  v5 = &unk_426060 - (_UNKNOWN *)a1;
  do
  {
    *v1 = v1[v5];
    ++v1;
    --v4;
  }
  while ( v4 );
  v6 = (char *)a1 + 281;
  v7 = 256;
  do
  {
    LOBYTE(result) = v6[v5];
    *v6++ = result;
    --v7;
  }
  while ( v7 );
  return result;
}

```

## disassembly

```asm
0x40dcac  mov     edi, edi
0x40dcae  push    ebp
0x40dcaf  mov     ebp, esp
0x40dcb1  push    ebx
0x40dcb2  mov     ebx, [ebp+arg_0]
0x40dcb5  push    esi
0x40dcb6  push    edi
0x40dcb7  push    101h
0x40dcbc  xor     edi, edi
0x40dcbe  lea     esi, [ebx+18h]
0x40dcc1  push    edi
0x40dcc2  push    esi
0x40dcc3  call    near ptr 33455851h
0x40dcc8  ror     byte ptr [ecx-3B7CF785h], 0Ch
0x40dccf  mov     [ebx+21Ch], edi
0x40dcd5  mov     ecx, 101h
0x40dcda  lea     edi, [ebx+0Ch]
0x40dcdd  stosd
0x40dcde  stosd
0x40dcdf  stosd
0x40dce0  mov     edi, offset unk_426060
0x40dce5  sub     edi, ebx
0x40dce7  mov     al, [edi+esi]
0x40dcea  mov     [esi], al
0x40dcec  inc     esi
0x40dced  sub     ecx, 1
0x40dcf0  jnz     short loc_40DCE7
0x40dcf2  lea     ecx, [ebx+119h]
0x40dcf8  mov     edx, 100h
0x40dcfd  mov     al, [ecx+edi]
0x40dd00  mov     [ecx], al
0x40dd02  inc     ecx
0x40dd03  sub     edx, 1
0x40dd06  jnz     short loc_40DCFD
0x40dd08  pop     edi
0x40dd09  pop     esi
0x40dd0a  pop     ebx
0x40dd0b  pop     ebp
0x40dd0c  retn
```
