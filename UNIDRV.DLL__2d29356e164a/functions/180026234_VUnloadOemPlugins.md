# VUnloadOemPlugins

- ea: `0x180026234`
- end: `0x180026396`
- name: `VUnloadOemPlugins`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025e4c`

## callees

- `0x180026234`
- `0x1800263fc`
- `0x18003a224`
- `0x18003e210`
- `0x18004ec64`
- `0x180075010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002638b`
- `KERNEL32!LocalFree` at `0x18002638b`

## pseudocode

```c
_DWORD *__fastcall VUnloadOemPlugins(_QWORD *a1, DWORD a2)
{
  _DWORD *result; // rax
  int v4; // esi
  char *v5; // rdi
  __int64 v6; // rax
  int v7; // esi
  __int64 v8; // rdi
  void *v9; // rcx
  _DWORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  void (__fastcall *v13)(_QWORD *); // rax
  void (*v14)(void); // rax

  result = (_DWORD *)a1[235];
  if ( result )
  {
    v4 = result[2];
    v5 = (char *)(result + 6);
    while ( v4 )
    {
      v11 = *((_QWORD *)v5 + 4);
      --v4;
      if ( v11 )
      {
        a1[4] = v11;
        a1[1] = *((_QWORD *)v5 + 5);
        a1[6] = *((_QWORD *)v5 + 7);
        if ( (v5[48] & 2) != 0 )
        {
          if ( *((_QWORD *)v5 + 9) )
          {
            HComOEMDisablePDEV(v5, a1);
          }
          else
          {
            if ( (v5[100] & 0x20) != 0 )
              v13 = (void (__fastcall *)(_QWORD *))*((_QWORD *)v5 + 18);
            else
              v13 = (void (__fastcall *)(_QWORD *))PGetOemEntrypointAddress(v5, 5);
            if ( v13 )
              v13(a1);
          }
        }
      }
      v5 += 176;
    }
    v6 = a1[235];
    v7 = *(_DWORD *)(v6 + 8);
    v8 = v6 + 24;
    while ( v7 )
    {
      v12 = *(_QWORD *)(v8 + 32);
      --v7;
      if ( v12 )
      {
        a1[4] = v12;
        a1[1] = *(_QWORD *)(v8 + 40);
        a1[6] = *(_QWORD *)(v8 + 56);
        if ( (*(_BYTE *)(v8 + 48) & 1) != 0 )
        {
          if ( *(_QWORD *)(v8 + 72) )
          {
            HComOEMDisableDriver(v8);
          }
          else
          {
            if ( (*(_BYTE *)(v8 + 100) & 8) != 0 )
              v14 = *(void (**)(void))(v8 + 128);
            else
              v14 = (void (*)(void))PGetOemEntrypointAddress(v8, 3);
            if ( v14 )
              v14();
          }
        }
      }
      v8 += 176;
    }
    v9 = (void *)a1[237];
    if ( v9 )
      LocalFree(v9);
    v10 = (_DWORD *)a1[235];
    a1[237] = 0;
    result = VFreeOemPluginInfoInternal(v10, a2);
    a1[235] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180026234  mov     [rsp+arg_0], rbx
0x180026239  mov     [rsp+arg_8], rsi
0x18002623e  push    rdi
0x18002623f  sub     rsp, 20h
0x180026243  mov     rax, [rcx+758h]
0x18002624a  mov     rbx, rcx
0x18002624d  test    rax, rax
0x180026250  jz      short loc_1800262A5
0x180026252  mov     esi, [rax+8]
0x180026255  lea     rdi, [rax+18h]
0x180026259  test    esi, esi
0x18002625b  jnz     short loc_1800262B5
0x18002625d  mov     rax, [rbx+758h]
0x180026264  mov     esi, [rax+8]
0x180026267  lea     rdi, [rax+18h]
0x18002626b  test    esi, esi
0x18002626d  jnz     loc_1800262F8
0x180026273  mov     rcx, [rbx+768h]; hMem
0x18002627a  test    rcx, rcx
0x18002627d  jnz     loc_18002638B
0x180026283  mov     rcx, [rbx+758h]
0x18002628a  mov     qword ptr [rbx+768h], 0
0x180026295  call    VFreeOemPluginInfoInternal
0x18002629a  mov     qword ptr [rbx+758h], 0
0x1800262a5  mov     rbx, [rsp+28h+arg_0]
0x1800262aa  mov     rsi, [rsp+28h+arg_8]
0x1800262af  add     rsp, 20h
0x1800262b3  pop     rdi
0x1800262b4  retn
0x1800262b5  mov     rax, [rdi+20h]
0x1800262b9  dec     esi
0x1800262bb  test    rax, rax
0x1800262be  jz      short loc_1800262EC
0x1800262c0  mov     [rbx+20h], rax
0x1800262c4  mov     rax, [rdi+28h]
0x1800262c8  mov     [rbx+8], rax
0x1800262cc  mov     rax, [rdi+38h]
0x1800262d0  mov     [rbx+30h], rax
0x1800262d4  test    byte ptr [rdi+30h], 2
0x1800262d8  jz      short loc_1800262EC
0x1800262da  cmp     qword ptr [rdi+48h], 0
0x1800262df  jz      short loc_180026338
0x1800262e1  mov     rdx, rbx
0x1800262e4  mov     rcx, rdi
0x1800262e7  call    HComOEMDisablePDEV
0x1800262ec  add     rdi, 0B0h
0x1800262f3  jmp     loc_180026259
0x1800262f8  mov     rax, [rdi+20h]
0x1800262fc  dec     esi
0x1800262fe  test    rax, rax
0x180026301  jz      short loc_18002632C
0x180026303  mov     [rbx+20h], rax
0x180026307  mov     rax, [rdi+28h]
0x18002630b  mov     [rbx+8], rax
0x18002630f  mov     rax, [rdi+38h]
0x180026313  mov     [rbx+30h], rax
0x180026317  test    byte ptr [rdi+30h], 1
0x18002631b  jz      short loc_18002632C
0x18002631d  cmp     qword ptr [rdi+48h], 0
0x180026322  jz      short loc_180026363
0x180026324  mov     rcx, rdi
0x180026327  call    HComOEMDisableDriver
0x18002632c  add     rdi, 0B0h
0x180026333  jmp     loc_18002626B
0x180026338  test    byte ptr [rdi+64h], 20h
0x18002633c  jz      short loc_180026347
0x18002633e  mov     rax, [rdi+90h]
0x180026345  jmp     short loc_180026354
0x180026347  mov     edx, 5
0x18002634c  mov     rcx, rdi
0x18002634f  call    PGetOemEntrypointAddress
0x180026354  test    rax, rax
0x180026357  jz      short loc_1800262EC
0x180026359  mov     rcx, rbx
0x18002635c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026361  jmp     short loc_1800262EC
0x180026363  test    byte ptr [rdi+64h], 8
0x180026367  jz      short loc_180026372
0x180026369  mov     rax, [rdi+80h]
0x180026370  jmp     short loc_18002637F
0x180026372  mov     edx, 3
0x180026377  mov     rcx, rdi
0x18002637a  call    PGetOemEntrypointAddress
0x18002637f  test    rax, rax
0x180026382  jz      short loc_18002632C
0x180026384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026389  jmp     short loc_18002632C
0x18002638b  call    cs:__imp_LocalFree
0x180026391  jmp     loc_180026283
```
