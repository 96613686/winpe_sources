# checkPtrmap

- ea: `0x18006b070`
- end: `0x18006b112`
- name: `checkPtrmap`
- size: `162`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int8, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18006ae08`
- `0x18006b17c`
- `0x180081bdc`

## callees

- `0x18006636c`
- `0x18006ad60`
- `0x18006afbc`
- `0x18006b070`

## string_xrefs

- `0x18006b0bd`: `Failed to read ptrmap key=%u`

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
0x18006b070  mov     rax, rsp
0x18006b073  push    rbx
0x18006b074  push    rbp
0x18006b075  push    rsi
0x18006b076  push    rdi
0x18006b077  sub     rsp, 58h
0x18006b07b  mov     esi, r9d
0x18006b07e  movzx   ebp, r8b
0x18006b082  mov     rbx, rcx
0x18006b085  mov     byte ptr [rax+8], 0
0x18006b089  mov     rcx, [rcx]
0x18006b08c  lea     r9, [rax-38h]
0x18006b090  lea     r8, [rax+8]
0x18006b094  mov     dword ptr [rax-38h], 0
0x18006b09b  mov     edi, edx
0x18006b09d  call    ptrmapGet
0x18006b0a2  test    eax, eax
0x18006b0a4  jz      short loc_18006B0CE
0x18006b0a6  cmp     eax, 7
0x18006b0a9  jz      short loc_18006B0B2
0x18006b0ab  cmp     eax, 0C0Ah
0x18006b0b0  jnz     short loc_18006B0BA
0x18006b0b2  mov     rcx, rbx
0x18006b0b5  call    checkOom
0x18006b0ba  mov     r8d, edi
0x18006b0bd  lea     rdx, aFailedToReadPt; "Failed to read ptrmap key=%u"
0x18006b0c4  mov     rcx, rbx
0x18006b0c7  call    checkAppendMsg
0x18006b0cc  jmp     short loc_18006B109
0x18006b0ce  mov     ecx, [rsp+78h+var_38]
0x18006b0d2  cmp     [rsp+78h+arg_0], bpl
0x18006b0da  jnz     short loc_18006B0E0
0x18006b0dc  cmp     ecx, esi
0x18006b0de  jz      short loc_18006B109
0x18006b0e0  movzx   eax, [rsp+78h+arg_0]
0x18006b0e8  lea     rdx, aBadPtrMapEntry; "Bad ptr map entry key=%u expected=(%u,%"...
0x18006b0ef  mov     [rsp+78h+var_48], ecx
0x18006b0f3  mov     r9d, ebp
0x18006b0f6  mov     [rsp+78h+var_50], eax
0x18006b0fa  mov     r8d, edi
0x18006b0fd  mov     rcx, rbx
0x18006b100  mov     [rsp+78h+var_58], esi
0x18006b104  call    checkAppendMsg
0x18006b109  add     rsp, 58h
0x18006b10d  pop     rdi
0x18006b10e  pop     rsi
0x18006b10f  pop     rbp
0x18006b110  pop     rbx
0x18006b111  retn
```
