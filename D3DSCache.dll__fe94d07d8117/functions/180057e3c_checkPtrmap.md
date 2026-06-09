# checkPtrmap

- ea: `0x180057e3c`
- end: `0x180057ede`
- name: `checkPtrmap`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180057bd4`
- `0x180057f48`
- `0x18007a3ec`

## callees

- `0x180057a90`
- `0x180057d88`
- `0x180057e3c`
- `0x18007134c`

## string_xrefs

- `0x180057e89`: `Failed to read ptrmap key=%u`

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
0x180057e3c  mov     rax, rsp
0x180057e3f  push    rbx
0x180057e40  push    rbp
0x180057e41  push    rsi
0x180057e42  push    rdi
0x180057e43  sub     rsp, 58h
0x180057e47  mov     esi, r9d
0x180057e4a  movzx   ebp, r8b
0x180057e4e  mov     rbx, rcx
0x180057e51  mov     byte ptr [rax+8], 0
0x180057e55  mov     rcx, [rcx]
0x180057e58  lea     r9, [rax-38h]
0x180057e5c  lea     r8, [rax+8]
0x180057e60  mov     dword ptr [rax-38h], 0
0x180057e67  mov     edi, edx
0x180057e69  call    ptrmapGet
0x180057e6e  test    eax, eax
0x180057e70  jz      short loc_180057E9A
0x180057e72  cmp     eax, 7
0x180057e75  jz      short loc_180057E7E
0x180057e77  cmp     eax, 0C0Ah
0x180057e7c  jnz     short loc_180057E86
0x180057e7e  mov     rcx, rbx
0x180057e81  call    checkOom
0x180057e86  mov     r8d, edi
0x180057e89  lea     rdx, aFailedToReadPt; "Failed to read ptrmap key=%u"
0x180057e90  mov     rcx, rbx
0x180057e93  call    checkAppendMsg
0x180057e98  jmp     short loc_180057ED5
0x180057e9a  mov     ecx, [rsp+78h+var_38]
0x180057e9e  cmp     [rsp+78h+arg_0], bpl
0x180057ea6  jnz     short loc_180057EAC
0x180057ea8  cmp     ecx, esi
0x180057eaa  jz      short loc_180057ED5
0x180057eac  movzx   eax, [rsp+78h+arg_0]
0x180057eb4  lea     rdx, aBadPtrMapEntry; "Bad ptr map entry key=%u expected=(%u,%"...
0x180057ebb  mov     [rsp+78h+var_48], ecx
0x180057ebf  mov     r9d, ebp
0x180057ec2  mov     [rsp+78h+var_50], eax
0x180057ec6  mov     r8d, edi
0x180057ec9  mov     rcx, rbx
0x180057ecc  mov     [rsp+78h+var_58], esi
0x180057ed0  call    checkAppendMsg
0x180057ed5  add     rsp, 58h
0x180057ed9  pop     rdi
0x180057eda  pop     rsi
0x180057edb  pop     rbp
0x180057edc  pop     rbx
0x180057edd  retn
```
