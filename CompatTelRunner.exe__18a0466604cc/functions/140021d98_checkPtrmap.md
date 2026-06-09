# checkPtrmap

- ea: `0x140021d98`
- end: `0x140021e4d`
- name: `checkPtrmap`
- size: `181`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int8, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140021b44`
- `0x140021eb8`
- `0x14004ea0c`

## callees

- `0x1400219f0`
- `0x140021d98`
- `0x14004109c`

## string_xrefs

- `0x140021df8`: `Failed to read ptrmap key=%u`

## pseudocode

```c
__int64 __fastcall checkPtrmap(__int64 *a1, __int64 a2, unsigned __int8 a3, int a4)
{
  int v5; // ebp
  __int64 v7; // rcx
  int v8; // edi
  __int64 result; // rax
  bool v10; // zf
  _DWORD v11[14]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 v12; // [rsp+80h] [rbp+8h] BYREF

  v5 = a3;
  v12 = 0;
  v7 = *a1;
  v11[0] = 0;
  v8 = a2;
  result = ptrmapGet(v7, a2, &v12, v11);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 7 || (_DWORD)result == 3082 )
    {
      v10 = *((_DWORD *)a1 + 8) == 0;
      *((_DWORD *)a1 + 9) = 7;
      *((_DWORD *)a1 + 7) = 0;
      if ( v10 )
        *((_DWORD *)a1 + 8) = 1;
    }
    return checkAppendMsg(a1, "Failed to read ptrmap key=%u", v8);
  }
  else if ( v12 != (_BYTE)v5 || v11[0] != a4 )
  {
    return checkAppendMsg(a1, "Bad ptr map entry key=%u expected=(%u,%u) got=(%u,%u)", v8, v5, a4, v12, v11[0]);
  }
  return result;
}

```

## disassembly

```asm
0x140021d98  mov     rax, rsp
0x140021d9b  push    rbx
0x140021d9c  push    rbp
0x140021d9d  push    rsi
0x140021d9e  push    rdi
0x140021d9f  sub     rsp, 58h
0x140021da3  mov     esi, r9d
0x140021da6  movzx   ebp, r8b
0x140021daa  mov     rbx, rcx
0x140021dad  mov     byte ptr [rax+8], 0
0x140021db1  mov     rcx, [rcx]
0x140021db4  lea     r9, [rax-38h]
0x140021db8  lea     r8, [rax+8]
0x140021dbc  mov     dword ptr [rax-38h], 0
0x140021dc3  mov     edi, edx
0x140021dc5  call    ptrmapGet
0x140021dca  test    eax, eax
0x140021dcc  jz      short loc_140021E09
0x140021dce  cmp     eax, 7
0x140021dd1  jz      short loc_140021DDA
0x140021dd3  cmp     eax, 0C0Ah
0x140021dd8  jnz     short loc_140021DF5
0x140021dda  cmp     dword ptr [rbx+20h], 0
0x140021dde  mov     dword ptr [rbx+24h], 7
0x140021de5  mov     dword ptr [rbx+1Ch], 0
0x140021dec  jnz     short loc_140021DF5
0x140021dee  mov     dword ptr [rbx+20h], 1
0x140021df5  mov     r8d, edi
0x140021df8  lea     rdx, aFailedToReadPt; "Failed to read ptrmap key=%u"
0x140021dff  mov     rcx, rbx
0x140021e02  call    checkAppendMsg
0x140021e07  jmp     short loc_140021E44
0x140021e09  mov     ecx, [rsp+78h+var_38]
0x140021e0d  cmp     [rsp+78h+arg_0], bpl
0x140021e15  jnz     short loc_140021E1B
0x140021e17  cmp     ecx, esi
0x140021e19  jz      short loc_140021E44
0x140021e1b  movzx   eax, [rsp+78h+arg_0]
0x140021e23  lea     rdx, aBadPtrMapEntry; "Bad ptr map entry key=%u expected=(%u,%"...
0x140021e2a  mov     [rsp+78h+var_48], ecx
0x140021e2e  mov     r9d, ebp
0x140021e31  mov     [rsp+78h+var_50], eax
0x140021e35  mov     r8d, edi
0x140021e38  mov     rcx, rbx
0x140021e3b  mov     [rsp+78h+var_58], esi
0x140021e3f  call    checkAppendMsg
0x140021e44  add     rsp, 58h
0x140021e48  pop     rdi
0x140021e49  pop     rsi
0x140021e4a  pop     rbp
0x140021e4b  pop     rbx
0x140021e4c  retn
```
