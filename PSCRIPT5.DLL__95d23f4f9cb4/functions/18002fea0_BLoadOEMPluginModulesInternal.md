# BLoadOEMPluginModulesInternal

- ea: `0x18002fea0`
- end: `0x180030055`
- name: `BLoadOEMPluginModulesInternal`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ed78`

## callees

- `0x180022024`
- `0x180022454`
- `0x18002fea0`
- `0x180030540`
- `0x180030bcc`
- `0x18005d010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x18002fef6`
- `KERNEL32!SetErrorMode` at `0x18002fef6`
- `KERNEL32!LoadLibraryExW` at `0x18002ff05`
- `KERNEL32!LoadLibraryExW` at `0x18002ff05`

## pseudocode

```c
__int64 __fastcall BLoadOEMPluginModulesInternal(__int64 a1, __int64 a2, int a3)
{
  int v3; // edi
  __int64 v6; // r15
  __int64 v7; // rbx
  const WCHAR *v8; // rbp
  HMODULE Library; // rax
  unsigned int (__fastcall *v11)(__int64, int *, __int64, int *); // rbp
  unsigned int i; // ebx
  __int64 v13; // rdi
  unsigned int v14; // edx
  int v15; // [rsp+68h] [rbp+10h] BYREF
  int v16; // [rsp+70h] [rbp+18h] BYREF

  v16 = a3;
  v3 = *(_DWORD *)(a2 + 8);
  v15 = 0;
  v16 = 0;
  if ( v3 )
  {
    v6 = a2 + 24;
    v7 = a2 + 24;
    do
    {
      v8 = *(const WCHAR **)v7;
      if ( *(_QWORD *)v7 )
      {
        SetErrorMode(1u);
        Library = LoadLibraryExW(v8, 0, 8u);
        *(_QWORD *)(v7 + 32) = Library;
        if ( !Library )
          return 0;
        if ( !(unsigned int)BGetOemInterface(a1, v7) )
          *(_QWORD *)(v7 + 72) = 0;
        if ( *(_QWORD *)(v7 + 72) )
        {
          if ( (int)HComOEMGetInfo(v7, 1, (int)v7 + 24, 4, (__int64)&v16) < 0 || !*(_DWORD *)(v7 + 24) )
            return 0;
        }
        else
        {
          if ( (*(_BYTE *)(v7 + 100) & 1) != 0 )
            v11 = *(unsigned int (__fastcall **)(__int64, int *, __int64, int *))(v7 + 104);
          else
            v11 = (unsigned int (__fastcall *)(__int64, int *, __int64, int *))PGetOemEntrypointAddress(v7, 0);
          if ( !v11
            || !v11(2, &v15, 4, &v16)
            || v15 != 0x10000
            || !v11(1, (int *)(v7 + 24), 4, &v16)
            || !*(_DWORD *)(v7 + 24) )
          {
            return 0;
          }
        }
      }
      v7 += 176;
      --v3;
    }
    while ( v3 );
    for ( i = 1; i < *(_DWORD *)(a2 + 8); ++i )
    {
      v13 = v6 + 176LL * i;
      if ( *(_QWORD *)(v13 + 32) && i )
      {
        v14 = 0;
        while ( *(_DWORD *)(176LL * v14 + a2 + 48) != *(_DWORD *)(v13 + 24) )
        {
          if ( ++v14 >= i )
            goto LABEL_28;
        }
        VFreeSinglePluginEntry(v6 + 176LL * i);
        *(_DWORD *)(v13 + 24) = 0;
      }
LABEL_28:
      ;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002fea0  mov     rax, rsp
0x18002fea3  mov     [rax+8], rbx
0x18002fea7  mov     [rax+20h], rbp
0x18002feab  mov     [rax+18h], r8d
0x18002feaf  push    rsi
0x18002feb0  push    rdi
0x18002feb1  push    r12
0x18002feb3  push    r14
0x18002feb5  push    r15
0x18002feb7  sub     rsp, 30h
0x18002febb  mov     edi, [rdx+8]
0x18002febe  mov     rsi, rdx
0x18002fec1  mov     dword ptr [rax+10h], 0
0x18002fec8  mov     r12, rcx
0x18002fecb  mov     dword ptr [rax+18h], 0
0x18002fed2  mov     r14d, 1
0x18002fed8  test    edi, edi
0x18002feda  jz      loc_18003003B
0x18002fee0  lea     r15, [rdx+18h]
0x18002fee4  mov     rbx, r15
0x18002fee7  mov     rbp, [rbx]
0x18002feea  test    rbp, rbp
0x18002feed  jz      loc_18002FFD5
0x18002fef3  mov     ecx, r14d; uMode
0x18002fef6  call    cs:__imp_SetErrorMode
0x18002fefc  xor     edx, edx; hFile
0x18002fefe  mov     rcx, rbp; lpLibFileName
0x18002ff01  lea     r8d, [rdx+8]; dwFlags
0x18002ff05  call    cs:__imp_LoadLibraryExW
0x18002ff0b  mov     [rbx+20h], rax
0x18002ff0f  test    rax, rax
0x18002ff12  jz      short loc_18002FF5B
0x18002ff14  mov     rdx, rbx
0x18002ff17  mov     rcx, r12
0x18002ff1a  call    BGetOemInterface
0x18002ff1f  test    eax, eax
0x18002ff21  jnz     short loc_18002FF2B
0x18002ff23  mov     qword ptr [rbx+48h], 0
0x18002ff2b  cmp     qword ptr [rbx+48h], 0
0x18002ff30  jz      short loc_18002FF62
0x18002ff32  lea     rax, [rsp+58h+arg_10]
0x18002ff37  mov     r9d, 4
0x18002ff3d  lea     r8, [rbx+18h]
0x18002ff41  mov     [rsp+58h+var_38], rax
0x18002ff46  mov     edx, r14d
0x18002ff49  mov     rcx, rbx
0x18002ff4c  call    HComOEMGetInfo
0x18002ff51  test    eax, eax
0x18002ff53  js      short loc_18002FF5B
0x18002ff55  cmp     dword ptr [rbx+18h], 0
0x18002ff59  jnz     short loc_18002FFD5
0x18002ff5b  xor     eax, eax
0x18002ff5d  jmp     loc_18003003E
0x18002ff62  test    [rbx+64h], r14b
0x18002ff66  jz      short loc_18002FF6E
0x18002ff68  mov     rbp, [rbx+68h]
0x18002ff6c  jmp     short loc_18002FF7B
0x18002ff6e  xor     edx, edx
0x18002ff70  mov     rcx, rbx
0x18002ff73  call    PGetOemEntrypointAddress
0x18002ff78  mov     rbp, rax
0x18002ff7b  test    rbp, rbp
0x18002ff7e  jz      short loc_18002FF5B
0x18002ff80  mov     r8d, 4
0x18002ff86  lea     r9, [rsp+58h+arg_10]
0x18002ff8b  lea     rdx, [rsp+58h+arg_8]
0x18002ff90  mov     rax, rbp
0x18002ff93  lea     ecx, [r8-2]
0x18002ff97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff9c  test    eax, eax
0x18002ff9e  jz      short loc_18002FF5B
0x18002ffa0  cmp     [rsp+58h+arg_8], 10000h
0x18002ffa8  jnz     short loc_18002FF5B
0x18002ffaa  mov     r8d, 4
0x18002ffb0  lea     r9, [rsp+58h+arg_10]
0x18002ffb5  lea     rdx, [rbx+18h]
0x18002ffb9  mov     rax, rbp
0x18002ffbc  lea     ecx, [r8-3]
0x18002ffc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffc5  test    eax, eax
0x18002ffc7  jz      short loc_18002FF5B
0x18002ffc9  cmp     dword ptr [rbx+18h], 0
0x18002ffcd  jz      short loc_18002FF5B
0x18002ffcf  mov     r14d, 1
0x18002ffd5  add     rbx, 0B0h
0x18002ffdc  add     edi, 0FFFFFFFFh
0x18002ffdf  jnz     loc_18002FEE7
0x18002ffe5  mov     ebx, r14d
0x18002ffe8  cmp     [rsi+8], r14d
0x18002ffec  jbe     short loc_18003003B
0x18002ffee  mov     eax, ebx
0x18002fff0  imul    rdi, rax, 0B0h
0x18002fff7  add     rdi, r15
0x18002fffa  cmp     qword ptr [rdi+20h], 0
0x18002ffff  jz      short loc_180030033
0x180030001  test    ebx, ebx
0x180030003  jz      short loc_180030033
0x180030005  mov     r8d, [rdi+18h]
0x180030009  xor     edx, edx
0x18003000b  mov     eax, edx
0x18003000d  imul    rcx, rax, 0B0h
0x180030014  cmp     [rcx+rsi+30h], r8d
0x180030019  jz      short loc_180030024
0x18003001b  add     edx, r14d
0x18003001e  cmp     edx, ebx
0x180030020  jb      short loc_18003000B
0x180030022  jmp     short loc_180030033
0x180030024  mov     rcx, rdi
0x180030027  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x18003002c  mov     dword ptr [rdi+18h], 0
0x180030033  add     ebx, r14d
0x180030036  cmp     ebx, [rsi+8]
0x180030039  jb      short loc_18002FFEE
0x18003003b  mov     eax, r14d
0x18003003e  mov     rbx, [rsp+58h+arg_0]
0x180030043  mov     rbp, [rsp+58h+arg_18]
0x180030048  add     rsp, 30h
0x18003004c  pop     r15
0x18003004e  pop     r14
0x180030050  pop     r12
0x180030052  pop     rdi
0x180030053  pop     rsi
0x180030054  retn
```
