# CONFIG_OBJECT::SerializeText(ushort *,ulong)

- ea: `0x18001dfb0`
- end: `0x18001e012`
- name: `?SerializeText@CONFIG_OBJECT@@UEAAJPEAGK@Z`
- size: `98`
- prototype: `int(CONFIG_OBJECT *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000d654`
- `0x18001dfb0`
- `0x180036010`

## string_xrefs

- `0x18001dfc3`: `CONFIG.SECTION`
- `0x18001dfea`: `CONFIG`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT::SerializeText(CONFIG_OBJECT *this, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(CONFIG_OBJECT *, const unsigned __int16 *, __int64 *))(v3 + 80))(
             this,
             L"CONFIG.SECTION",
             &v7);
  if ( (int)result >= 0 )
    return StringCchPrintfW(a2, a3, L"%ws \"%ws\"", L"CONFIG", v7);
  return result;
}

```

## disassembly

```asm
0x18001dfb0  mov     [rsp+arg_8], rbx
0x18001dfb5  push    rdi
0x18001dfb6  sub     rsp, 30h
0x18001dfba  mov     rax, [rcx]
0x18001dfbd  mov     rdi, rdx
0x18001dfc0  mov     ebx, r8d
0x18001dfc3  lea     rdx, aConfigSection; "CONFIG.SECTION"
0x18001dfca  lea     r8, [rsp+38h+arg_0]
0x18001dfcf  mov     [rsp+38h+arg_0], 0
0x18001dfd8  mov     rax, [rax+50h]
0x18001dfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfe1  test    eax, eax
0x18001dfe3  js      short loc_18001E007
0x18001dfe5  mov     rax, [rsp+38h+arg_0]
0x18001dfea  lea     r9, aConfig; "CONFIG"
0x18001dff1  mov     edx, ebx; unsigned __int64
0x18001dff3  mov     [rsp+38h+var_18], rax
0x18001dff8  lea     r8, aWsWs; "%ws \"%ws\""
0x18001dfff  mov     rcx, rdi; unsigned __int16 *
0x18001e002  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e007  mov     rbx, [rsp+38h+arg_8]
0x18001e00c  add     rsp, 30h
0x18001e010  pop     rdi
0x18001e011  retn
```
