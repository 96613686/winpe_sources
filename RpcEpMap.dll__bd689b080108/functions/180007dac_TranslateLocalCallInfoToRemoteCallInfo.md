# TranslateLocalCallInfoToRemoteCallInfo

- ea: `0x180007dac`
- end: `0x180007e08`
- name: `TranslateLocalCallInfoToRemoteCallInfo`
- size: `92`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007600`
- `0x180007810`

## callees

- `0x180007dac`

## pseudocode

```c
__int64 __fastcall TranslateLocalCallInfoToRemoteCallInfo(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_BYTE *)a2 = *(_BYTE *)a1;
  *(_BYTE *)(a2 + 1) = *(_BYTE *)(a1 + 1);
  *(_WORD *)(a2 + 2) = *(_WORD *)(a1 + 2);
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(a2 + 20) = *(_DWORD *)(a1 + 20);
  if ( (*(_BYTE *)(a1 + 12) & 8) != 0 )
  {
    *(_DWORD *)(a2 + 24) = 1;
    result = *(unsigned int *)(a1 + 24);
    *(_DWORD *)(a2 + 28) = result;
  }
  else
  {
    *(_DWORD *)(a2 + 24) = 0;
    *(_WORD *)(a2 + 28) = *(_WORD *)(a1 + 24);
    result = *(unsigned __int16 *)(a1 + 26);
    *(_WORD *)(a2 + 30) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180007dac  mov     al, [rcx]
0x180007dae  mov     [rdx], al
0x180007db0  mov     al, [rcx+1]
0x180007db3  mov     [rdx+1], al
0x180007db6  movzx   eax, word ptr [rcx+2]
0x180007dba  mov     [rdx+2], ax
0x180007dbe  mov     eax, [rcx+4]
0x180007dc1  mov     [rdx+4], eax
0x180007dc4  mov     eax, [rcx+8]
0x180007dc7  mov     [rdx+8], eax
0x180007dca  mov     eax, [rcx+0Ch]
0x180007dcd  mov     [rdx+0Ch], eax
0x180007dd0  mov     eax, [rcx+10h]
0x180007dd3  mov     [rdx+10h], eax
0x180007dd6  mov     eax, [rcx+14h]
0x180007dd9  mov     [rdx+14h], eax
0x180007ddc  test    byte ptr [rcx+0Ch], 8
0x180007de0  jz      short loc_180007DF0
0x180007de2  mov     dword ptr [rdx+18h], 1
0x180007de9  mov     eax, [rcx+18h]
0x180007dec  mov     [rdx+1Ch], eax
0x180007def  retn
0x180007df0  mov     dword ptr [rdx+18h], 0
0x180007df7  movzx   eax, word ptr [rcx+18h]
0x180007dfb  mov     [rdx+1Ch], ax
0x180007dff  movzx   eax, word ptr [rcx+1Ah]
0x180007e03  mov     [rdx+1Eh], ax
0x180007e07  retn
```
