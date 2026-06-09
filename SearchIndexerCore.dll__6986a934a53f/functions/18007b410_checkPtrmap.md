# checkPtrmap

- ea: `0x18007b410`
- end: `0x18007b4b2`
- name: `checkPtrmap`
- size: `162`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int8, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18007b1a8`
- `0x18007b51c`
- `0x180090694`

## callees

- `0x1800630c4`
- `0x18007b100`
- `0x18007b35c`
- `0x18007b410`

## string_xrefs

- `0x18007b45d`: `Failed to read ptrmap key=%u`

## pseudocode

```c
__int64 __fastcall checkPtrmap(__int64 *a1, __int64 a2, unsigned __int8 a3, int a4)
{
  int v5; // ebp
  __int64 v7; // rcx
  int v8; // edi
  __int64 result; // rax
  _DWORD v10[14]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 v11; // [rsp+80h] [rbp+8h] BYREF

  v5 = a3;
  v11 = 0;
  v7 = *a1;
  v10[0] = 0;
  v8 = a2;
  result = ptrmapGet(v7, a2, &v11, v10);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 7 || (_DWORD)result == 3082 )
      checkOom(a1);
    return checkAppendMsg(a1, "Failed to read ptrmap key=%u", v8);
  }
  else if ( v11 != (_BYTE)v5 || v10[0] != a4 )
  {
    return checkAppendMsg(a1, "Bad ptr map entry key=%u expected=(%u,%u) got=(%u,%u)", v8, v5, a4, v11, v10[0]);
  }
  return result;
}

```

## disassembly

```asm
0x18007b410  mov     rax, rsp
0x18007b413  push    rbx
0x18007b414  push    rbp
0x18007b415  push    rsi
0x18007b416  push    rdi
0x18007b417  sub     rsp, 58h
0x18007b41b  mov     esi, r9d
0x18007b41e  movzx   ebp, r8b
0x18007b422  mov     rbx, rcx
0x18007b425  mov     byte ptr [rax+8], 0
0x18007b429  mov     rcx, [rcx]
0x18007b42c  lea     r9, [rax-38h]
0x18007b430  lea     r8, [rax+8]
0x18007b434  mov     dword ptr [rax-38h], 0
0x18007b43b  mov     edi, edx
0x18007b43d  call    ptrmapGet
0x18007b442  test    eax, eax
0x18007b444  jz      short loc_18007B46E
0x18007b446  cmp     eax, 7
0x18007b449  jz      short loc_18007B452
0x18007b44b  cmp     eax, 0C0Ah
0x18007b450  jnz     short loc_18007B45A
0x18007b452  mov     rcx, rbx
0x18007b455  call    checkOom
0x18007b45a  mov     r8d, edi
0x18007b45d  lea     rdx, aFailedToReadPt; "Failed to read ptrmap key=%u"
0x18007b464  mov     rcx, rbx
0x18007b467  call    checkAppendMsg
0x18007b46c  jmp     short loc_18007B4A9
0x18007b46e  mov     ecx, [rsp+78h+var_38]
0x18007b472  cmp     [rsp+78h+arg_0], bpl
0x18007b47a  jnz     short loc_18007B480
0x18007b47c  cmp     ecx, esi
0x18007b47e  jz      short loc_18007B4A9
0x18007b480  movzx   eax, [rsp+78h+arg_0]
0x18007b488  lea     rdx, aBadPtrMapEntry; "Bad ptr map entry key=%u expected=(%u,%"...
0x18007b48f  mov     [rsp+78h+var_48], ecx
0x18007b493  mov     r9d, ebp
0x18007b496  mov     [rsp+78h+var_50], eax
0x18007b49a  mov     r8d, edi
0x18007b49d  mov     rcx, rbx
0x18007b4a0  mov     [rsp+78h+var_58], esi
0x18007b4a4  call    checkAppendMsg
0x18007b4a9  add     rsp, 58h
0x18007b4ad  pop     rdi
0x18007b4ae  pop     rsi
0x18007b4af  pop     rbp
0x18007b4b0  pop     rbx
0x18007b4b1  retn
```
