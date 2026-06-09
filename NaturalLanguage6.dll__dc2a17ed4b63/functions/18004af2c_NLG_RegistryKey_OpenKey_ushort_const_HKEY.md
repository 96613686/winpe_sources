# NLG::RegistryKey::OpenKey(ushort const *,HKEY__ *)

- ea: `0x18004af2c`
- end: `0x18004afcb`
- name: `?OpenKey@RegistryKey@NLG@@KAPEAUHKEY__@@PEBGPEAU3@@Z`
- size: `159`
- prototype: `static HKEY(const unsigned __int16 *, HKEY)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016ea0`
- `0x18002e1b0`
- `0x1800499bc`

## callees

- `0x18004a99c`
- `0x18004af2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afae`

## pseudocode

```c
HKEY __fastcall NLG::RegistryKey::OpenKey(const unsigned __int16 *a1, HKEY a2)
{
  HKEY v2; // r10
  unsigned __int16 *v3; // rax
  const WCHAR *v4; // rbx
  unsigned __int16 v5; // cx
  bool v6; // zf
  HKEY result; // rax
  unsigned __int16 *v8; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  v3 = 0;
  v4 = a1;
  v8 = 0;
  if ( !a2 )
  {
    v2 = NLG::RegistryKey::MapHiveName(a1, (const unsigned __int16 **)&v8);
    v3 = v8;
    if ( v8 )
    {
      while ( 1 )
      {
        v5 = *v3;
        if ( !*v3 || v5 != 92 && v5 != 47 )
          break;
        ++v3;
      }
    }
    if ( !v2 )
      v2 = HKEY_LOCAL_MACHINE;
  }
  phkResult = 0;
  if ( v3 )
    v4 = v3;
  v6 = RegOpenKeyExW(v2, v4, 0, 9u, &phkResult) == 0;
  result = 0;
  if ( v6 )
    return phkResult;
  return result;
}

```

## disassembly

```asm
0x18004af2c  mov     [rsp+arg_0], rbx
0x18004af31  push    rdi
0x18004af32  sub     rsp, 30h
0x18004af36  xor     edi, edi
0x18004af38  mov     r10, rdx
0x18004af3b  mov     eax, edi
0x18004af3d  mov     rbx, rcx
0x18004af40  mov     [rsp+38h+arg_8], rax
0x18004af45  test    rdx, rdx
0x18004af48  jnz     short loc_18004AF89
0x18004af4a  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 **
0x18004af4f  call    ?MapHiveName@RegistryKey@NLG@@KAPEAUHKEY__@@PEBGPEAPEBG@Z; NLG::RegistryKey::MapHiveName(ushort const *,ushort const * *)
0x18004af54  mov     r10, rax
0x18004af57  mov     rax, [rsp+38h+arg_8]
0x18004af5c  test    rax, rax
0x18004af5f  jz      short loc_18004AF7B
0x18004af61  jmp     short loc_18004AF73
0x18004af63  cmp     cx, 5Ch ; '\'
0x18004af67  jz      short loc_18004AF6F
0x18004af69  cmp     cx, 2Fh ; '/'
0x18004af6d  jnz     short loc_18004AF7B
0x18004af6f  add     rax, 2
0x18004af73  movzx   ecx, word ptr [rax]
0x18004af76  test    cx, cx
0x18004af79  jnz     short loc_18004AF63
0x18004af7b  test    r10, r10
0x18004af7e  mov     rcx, 0FFFFFFFF80000002h
0x18004af85  cmovz   r10, rcx
0x18004af89  test    rax, rax
0x18004af8c  mov     [rsp+38h+arg_10], rdi
0x18004af91  mov     r9d, 9; samDesired
0x18004af97  mov     rcx, r10; hKey
0x18004af9a  cmovnz  rbx, rax
0x18004af9e  lea     rax, [rsp+38h+arg_10]
0x18004afa3  mov     rdx, rbx; lpSubKey
0x18004afa6  mov     [rsp+38h+phkResult], rax; phkResult
0x18004afab  xor     r8d, r8d; ulOptions
0x18004afae  call    cs:__imp_RegOpenKeyExW
0x18004afb4  test    eax, eax
0x18004afb6  mov     rax, rdi
0x18004afb9  jnz     short loc_18004AFC0
0x18004afbb  mov     rax, [rsp+38h+arg_10]
0x18004afc0  mov     rbx, [rsp+38h+arg_0]
0x18004afc5  add     rsp, 30h
0x18004afc9  pop     rdi
0x18004afca  retn
```
