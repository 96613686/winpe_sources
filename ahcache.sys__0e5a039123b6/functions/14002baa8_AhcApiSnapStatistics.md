# AhcApiSnapStatistics

- ea: `0x14002baa8`
- end: `0x14002bb43`
- name: `AhcApiSnapStatistics`
- size: `155`
- prototype: `__int64 __fastcall(void *Src, void *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400497bc`

## callees

- `0x14002baa8`
- `0x14003e364`
- `0x140045d6c`
- `0x14004c2e0`

## string_xrefs

- `0x14002bac9`: `Failed to pass security check [%x]`
- `0x14002bafd`: `AhcSafeCopyMemoryToUserMode failed [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiSnapStatistics(void *Src, void *a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax

  v6 = AhcVerifyAdminContext();
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( a2 && a3 == 52 )
    {
      v8 = AhcSafeCopyMemoryToUserMode(a2, Src, 0x34u);
      v7 = v8;
      if ( v8 >= 0 )
        return 0;
      else
        AslLogCallPrintf(1, "AhcApiSnapStatistics", 889, "AhcSafeCopyMemoryToUserMode failed [%x]", v8);
    }
    else
    {
      v7 = -1073741811;
      AslLogCallPrintf(1, "AhcApiSnapStatistics", 879, "SnapStatistics bad parameters [%x]", -1073741811);
    }
  }
  else
  {
    AslLogCallPrintf(1, "AhcApiSnapStatistics", 869, "Failed to pass security check [%x]", v6);
  }
  return v7;
}

```

## disassembly

```asm
0x14002baa8  push    rbx
0x14002baaa  push    rbp
0x14002baab  push    rsi
0x14002baac  push    rdi
0x14002baad  sub     rsp, 38h
0x14002bab1  mov     esi, r8d
0x14002bab4  mov     rdi, rdx
0x14002bab7  mov     rbp, rcx
0x14002baba  call    AhcVerifyAdminContext
0x14002babf  mov     ebx, eax
0x14002bac1  test    eax, eax
0x14002bac3  jns     short loc_14002BAD8
0x14002bac5  mov     [rsp+58h+var_38], eax
0x14002bac9  lea     r9, aFailedToPassSe; "Failed to pass security check [%x]"
0x14002bad0  mov     r8d, 365h
0x14002bad6  jmp     short loc_14002BB26
0x14002bad8  test    rdi, rdi
0x14002badb  jz      short loc_14002BB10
0x14002badd  mov     r8d, 34h ; '4'; Size
0x14002bae3  cmp     esi, r8d
0x14002bae6  jnz     short loc_14002BB10
0x14002bae8  mov     rdx, rbp; Src
0x14002baeb  mov     rcx, rdi; void *
0x14002baee  call    AhcSafeCopyMemoryToUserMode
0x14002baf3  mov     ebx, eax
0x14002baf5  test    eax, eax
0x14002baf7  jns     short loc_14002BB0C
0x14002baf9  mov     [rsp+58h+var_38], eax
0x14002bafd  lea     r9, aAhcsafecopymem_1; "AhcSafeCopyMemoryToUserMode failed [%x]"
0x14002bb04  mov     r8d, 379h
0x14002bb0a  jmp     short loc_14002BB26
0x14002bb0c  xor     ebx, ebx
0x14002bb0e  jmp     short loc_14002BB37
0x14002bb10  mov     ebx, 0C000000Dh
0x14002bb15  lea     r9, aSnapstatistics; "SnapStatistics bad parameters [%x]"
0x14002bb1c  mov     [rsp+58h+var_38], ebx
0x14002bb20  mov     r8d, 36Fh
0x14002bb26  lea     rdx, aAhcapisnapstat; "AhcApiSnapStatistics"
0x14002bb2d  mov     ecx, 1
0x14002bb32  call    AslLogCallPrintf
0x14002bb37  mov     eax, ebx
0x14002bb39  add     rsp, 38h
0x14002bb3d  pop     rdi
0x14002bb3e  pop     rsi
0x14002bb3f  pop     rbp
0x14002bb40  pop     rbx
0x14002bb41  retn
```
