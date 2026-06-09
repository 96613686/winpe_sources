# PathIsInvalidW

- ea: `0x18004f650`
- end: `0x18004f6e8`
- name: `PathIsInvalidW`
- size: `152`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004f6f0`

## callees

- `0x180006900`
- `0x18000ebd0`
- `0x18000ecc4`
- `0x18004f650`

## import_xrefs

- `SHLWAPI!PathIsRelativeW` at `0x18004f66c`
- `SHLWAPI!PathIsRelativeW` at `0x18004f66c`
- `ntdll!RtlIsDosDeviceName_U` at `0x18004f6c1`
- `ntdll!RtlIsDosDeviceName_U` at `0x18004f6c1`

## pseudocode

```c
_BOOL8 __fastcall PathIsInvalidW(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int64 v2; // rax
  unsigned int v4; // r11d
  unsigned __int16 v5[16]; // [rsp+20h] [rbp-38h] BYREF

  v1 = a1;
  if ( !PathIsRelativeW(a1) )
  {
    v2 = -1;
    do
      ++v2;
    while ( v1[v2] );
    if ( v2 >= 0xE )
      return 0;
    StringCchCopyW(v5, 0x10u, L".\\");
    StringCchCatW(v5, v4, v1);
    v1 = v5;
  }
  return RtlIsDosDeviceName_U(v1) != 0;
}

```

## disassembly

```asm
0x18004f650  mov     [rsp+arg_8], rbx
0x18004f655  push    rdi
0x18004f656  sub     rsp, 50h
0x18004f65a  mov     rax, cs:__security_cookie
0x18004f661  xor     rax, rsp
0x18004f664  mov     [rsp+58h+var_18], rax
0x18004f669  mov     rbx, rcx
0x18004f66c  call    cs:__imp_PathIsRelativeW
0x18004f672  xor     edi, edi
0x18004f674  test    eax, eax
0x18004f676  jnz     short loc_18004F6BE
0x18004f678  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f67c  inc     rax
0x18004f67f  cmp     [rbx+rax*2], di
0x18004f683  jnz     short loc_18004F67C
0x18004f685  cmp     rax, 0Eh
0x18004f689  jb      short loc_18004F68F
0x18004f68b  xor     eax, eax
0x18004f68d  jmp     short loc_18004F6D0
0x18004f68f  mov     r11d, 10h
0x18004f695  lea     r8, asc_18005E090; ".\\"
0x18004f69c  mov     edx, r11d; unsigned __int64
0x18004f69f  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x18004f6a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f6a9  mov     r8, rbx; unsigned __int16 *
0x18004f6ac  lea     rcx, [rsp+58h+var_38]; unsigned __int16 *
0x18004f6b1  mov     edx, r11d; unsigned __int64
0x18004f6b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f6b9  lea     rbx, [rsp+58h+var_38]
0x18004f6be  mov     rcx, rbx; Name
0x18004f6c1  call    cs:__imp_RtlIsDosDeviceName_U
0x18004f6c7  test    eax, eax
0x18004f6c9  mov     ecx, edi
0x18004f6cb  setnz   cl
0x18004f6ce  mov     eax, ecx
0x18004f6d0  mov     rcx, [rsp+58h+var_18]
0x18004f6d5  xor     rcx, rsp; StackCookie
0x18004f6d8  call    __security_check_cookie
0x18004f6dd  mov     rbx, [rsp+58h+arg_8]
0x18004f6e2  add     rsp, 50h
0x18004f6e6  pop     rdi
0x18004f6e7  retn
```
