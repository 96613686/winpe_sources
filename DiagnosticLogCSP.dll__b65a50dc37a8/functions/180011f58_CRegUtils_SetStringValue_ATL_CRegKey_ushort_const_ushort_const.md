# CRegUtils::SetStringValue(ATL::CRegKey &,ushort const *,ushort const *)

- ea: `0x180011f58`
- end: `0x180011fd9`
- name: `?SetStringValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG1@Z`
- size: `129`
- prototype: `static int(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e858`
- `0x18000ea88`
- `0x18000fd38`
- `0x18000fecc`
- `0x180013f4c`

## callees

- `0x180011648`
- `0x180011f58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fa1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fa1`

## pseudocode

```c
__int64 __fastcall CRegUtils::SetStringValue(HKEY *a1, const unsigned __int16 *a2, const BYTE *lpData)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  LSTATUS v5; // eax

  if ( a2 )
  {
    if ( !lpData )
      ATL::AtlThrowImpl(-2147467259);
    v3 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&lpData[2 * v4] );
    v5 = RegSetValueExW(*a1, a2, 0, 1u, lpData, 2 * v4 + 2);
    if ( v5 )
    {
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
      else
        return (unsigned int)v5;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180011f58  mov     [rsp+arg_0], rbx
0x180011f5d  push    rdi
0x180011f5e  sub     rsp, 30h
0x180011f62  xor     edi, edi
0x180011f64  test    rdx, rdx
0x180011f67  jnz     short loc_180011F70
0x180011f69  mov     ebx, 80070057h
0x180011f6e  jmp     short loc_180011FC0
0x180011f70  test    r8, r8
0x180011f73  jz      short loc_180011FCE
0x180011f75  mov     ebx, edi
0x180011f77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f7b  inc     rax
0x180011f7e  cmp     [r8+rax*2], di
0x180011f83  jnz     short loc_180011F7B
0x180011f85  mov     rcx, [rcx]; hKey
0x180011f88  lea     eax, ds:2[rax*2]
0x180011f8f  mov     [rsp+38h+cbData], eax; cbData
0x180011f93  mov     r9d, 1; dwType
0x180011f99  mov     [rsp+38h+lpData], r8; lpData
0x180011f9e  xor     r8d, r8d; Reserved
0x180011fa1  call    cs:__imp_RegSetValueExW
0x180011fa8  nop     dword ptr [rax+rax+00h]
0x180011fad  test    eax, eax
0x180011faf  jz      short loc_180011FC0
0x180011fb1  jg      short loc_180011FB7
0x180011fb3  mov     ebx, eax
0x180011fb5  jmp     short loc_180011FC0
0x180011fb7  movzx   ebx, ax
0x180011fba  or      ebx, 80070000h
0x180011fc0  mov     eax, ebx
0x180011fc2  mov     rbx, [rsp+38h+arg_0]
0x180011fc7  add     rsp, 30h
0x180011fcb  pop     rdi
0x180011fcc  retn
0x180011fce  mov     ecx, 80004005h; int
0x180011fd3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
