# WwanProfileGetPath

- ea: `0x18000e050`
- end: `0x18000e0cb`
- name: `WwanProfileGetPath`
- size: `123`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000dd90`
- `0x18000e2f0`

## callees

- `0x180008458`
- `0x18000e050`
- `0x18000e0e0`

## pseudocode

```c
__int64 __fastcall WwanProfileGetPath(__int64 a1, unsigned __int16 *a2, unsigned __int64 a3)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ecx

  result = WwanProfileGetRootPath(a2, a3);
  if ( !(_DWORD)result )
  {
    v7 = StringCchPrintfW(a2, a3, L"%s\\%s.%s", a2, a1, L"xml");
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v7;
    }
    else
    {
      return 0;
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000e050  mov     [rsp+arg_0], rbx
0x18000e055  mov     [rsp+arg_8], rsi
0x18000e05a  push    rdi
0x18000e05b  sub     rsp, 30h
0x18000e05f  mov     rdi, r8
0x18000e062  mov     rbx, rdx
0x18000e065  mov     rsi, rcx
0x18000e068  mov     rdx, rdi; unsigned __int64
0x18000e06b  mov     rcx, rbx; unsigned __int16 *
0x18000e06e  mov     r8d, r9d
0x18000e071  call    WwanProfileGetRootPath
0x18000e076  test    eax, eax
0x18000e078  jnz     short loc_18000E0BB
0x18000e07a  lea     rax, psz; "xml"
0x18000e081  mov     r9, rbx
0x18000e084  mov     [rsp+38h+var_10], rax
0x18000e089  lea     r8, aSSS_0; "%s\\%s.%s"
0x18000e090  mov     rdx, rdi; unsigned __int64
0x18000e093  mov     [rsp+38h+var_18], rsi
0x18000e098  mov     rcx, rbx; unsigned __int16 *
0x18000e09b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e0a0  mov     ecx, eax
0x18000e0a2  test    eax, eax
0x18000e0a4  js      short loc_18000E0AA
0x18000e0a6  xor     ecx, ecx
0x18000e0a8  jmp     short loc_18000E0B9
0x18000e0aa  and     eax, 1FFF0000h
0x18000e0af  cmp     eax, 70000h
0x18000e0b4  jnz     short loc_18000E0B9
0x18000e0b6  movzx   ecx, cx
0x18000e0b9  mov     eax, ecx
0x18000e0bb  mov     rbx, [rsp+38h+arg_0]
0x18000e0c0  mov     rsi, [rsp+38h+arg_8]
0x18000e0c5  add     rsp, 30h
0x18000e0c9  pop     rdi
0x18000e0ca  retn
```
