# SspirLogonSystemManagedAdmin

- ea: `0x180002bf0`
- end: `0x180002c60`
- name: `SspirLogonSystemManagedAdmin`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002bf0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirLogonSystemManagedAdmin(__int64 a1, __int128 *a2, __int64 a3, _QWORD *a4)
{
  __int64 (__fastcall *v5)(__int64, __int128 *, __int64, __int64 *); // rax
  __int64 result; // rax
  unsigned int v7; // ecx
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+38h] [rbp-20h] BYREF

  v8 = 0;
  if ( gLsapSspiExtension
    && (v5 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64 *))(gLsapSspiExtension + 136)) != 0 )
  {
    if ( a2 && a4 )
    {
      v9 = *a2;
      result = v5(a1, &v9, a3, &v8);
      v7 = result;
      if ( (int)result < 0 )
        return result;
      *a4 = v8;
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return v7;
}

```

## disassembly

```asm
0x180002bf0  push    rbx
0x180002bf2  sub     rsp, 50h
0x180002bf6  mov     rax, cs:gLsapSspiExtension
0x180002bfd  mov     rbx, r9
0x180002c00  mov     [rsp+58h+var_28], 0
0x180002c09  test    rax, rax
0x180002c0c  jz      short loc_180002C53
0x180002c0e  mov     rax, [rax+88h]
0x180002c15  test    rax, rax
0x180002c18  jz      short loc_180002C53
0x180002c1a  test    rdx, rdx
0x180002c1d  jz      short loc_180002C4C
0x180002c1f  test    rbx, rbx
0x180002c22  jz      short loc_180002C4C
0x180002c24  movups  xmm0, xmmword ptr [rdx]
0x180002c27  lea     r9, [rsp+58h+var_28]
0x180002c2c  lea     rdx, [rsp+58h+var_20]
0x180002c31  movdqu  [rsp+58h+var_20], xmm0
0x180002c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3c  mov     ecx, eax
0x180002c3e  test    eax, eax
0x180002c40  js      short loc_180002C5A
0x180002c42  mov     rax, [rsp+58h+var_28]
0x180002c47  mov     [rbx], rax
0x180002c4a  jmp     short loc_180002C58
0x180002c4c  mov     ecx, 0C000000Dh
0x180002c51  jmp     short loc_180002C58
0x180002c53  mov     ecx, 0C00000BBh
0x180002c58  mov     eax, ecx
0x180002c5a  add     rsp, 50h
0x180002c5e  pop     rbx
0x180002c5f  retn
```
