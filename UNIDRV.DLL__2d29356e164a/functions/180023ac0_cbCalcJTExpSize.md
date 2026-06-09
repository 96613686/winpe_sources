# cbCalcJTExpSize

- ea: `0x180023ac0`
- end: `0x180023c59`
- name: `cbCalcJTExpSize`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002540c`

## callees

- `0x180023ac0`
- `0x180049128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023adf`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180023adf`

## string_xrefs

- `0x180023afc`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall cbCalcJTExpSize(__int64 a1, __int64 a2, __int64 a3)
{
  const wchar_t *v3; // rdi
  wchar_t *v6; // rax
  const wchar_t *v7; // rax
  __int64 v8; // rax
  bool v9; // zf
  int v10; // r14d
  unsigned int v11; // r15d
  unsigned int *v12; // rbx
  unsigned int i; // ebp
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edi
  _DWORD *v17; // r9
  __int64 v18; // r8
  unsigned int v19; // r11d
  unsigned int v20; // r10d
  __int64 v21; // rdx
  __int64 v22; // rax

  v3 = *(const wchar_t **)(a3 + 40);
  v6 = wcsrchr(v3, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = v3;
  if ( v7 && !wcsicmp(v7, L"PrintConfig.dll") )
  {
    v10 = 94;
  }
  else
  {
    v8 = -1;
    do
      v9 = *(_WORD *)(*(_QWORD *)(a3 + 8) + 2 * v8++ + 2) == 0;
    while ( !v9 );
    v10 = 2 * v8 + 18;
  }
  v11 = *(_DWORD *)(a2 + 24) + *(_DWORD *)(a2 + 28);
  if ( !v11 )
    return 0;
  v12 = (unsigned int *)(*(_QWORD *)(a2 + 328) + *(unsigned int *)(a2 + 32));
  if ( !v12 )
    return 0;
  for ( i = 0; i < v11; ++i )
  {
    if ( v12[11] != 2 )
    {
      v14 = *v12;
      if ( (_DWORD)v14 )
        v15 = *(_QWORD *)(a2 + 320) + v14;
      else
        v15 = 0;
      v16 = v12[13];
      if ( v16 )
        v17 = (_DWORD *)(*(_QWORD *)(a2 + 328) + v12[14]);
      else
        v17 = 0;
      if ( !v15 || !v16 || !v17 )
        return 0;
      v18 = -1;
      do
        v9 = *(_BYTE *)(v15 + v18++ + 1) == 0;
      while ( !v9 );
      v19 = 0;
      v20 = 0;
      while ( v20 < v16 )
      {
        if ( !*v17 )
          return 0;
        v21 = *(_QWORD *)(a2 + 320) + (unsigned int)*v17;
        if ( !v21 )
          return 0;
        v22 = -1;
        do
          ++v22;
        while ( *(_BYTE *)(v21 + v22) );
        ++v20;
        v17 = (_DWORD *)((char *)v17 + v12[12]);
        if ( v19 >= (unsigned int)v22 )
          LODWORD(v22) = v19;
        v19 = v22;
      }
      v10 += v19 + v18 + 2;
    }
    v12 += 21;
  }
  return (v10 + 9) & 0xFFFFFFF8;
}

```

## disassembly

```asm
0x180023ac0  mov     [rsp+arg_10], rbx
0x180023ac5  push    rsi
0x180023ac6  push    rdi
0x180023ac7  push    r15
0x180023ac9  sub     rsp, 20h
0x180023acd  mov     rdi, [r8+28h]
0x180023ad1  mov     rsi, rdx
0x180023ad4  mov     rcx, rdi; Str
0x180023ad7  mov     edx, 5Ch ; '\'; Ch
0x180023adc  mov     rbx, r8
0x180023adf  call    cs:__imp_wcsrchr
0x180023ae5  test    rax, rax
0x180023ae8  jz      loc_180023C35
0x180023aee  add     rax, 2
0x180023af2  mov     [rsp+38h+arg_8], r14
0x180023af7  test    rax, rax
0x180023afa  jz      short loc_180023B13
0x180023afc  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180023b03  mov     rcx, rax; String1
0x180023b06  call    _wcsicmp
0x180023b0b  test    eax, eax
0x180023b0d  jz      loc_180023C3D
0x180023b13  mov     rcx, [rbx+8]
0x180023b17  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023b1e  xchg    ax, ax
0x180023b20  cmp     word ptr [rcx+rax*2+2], 0
0x180023b26  lea     rax, [rax+1]
0x180023b2a  jnz     short loc_180023B20
0x180023b2c  lea     r14d, ds:12h[rax*2]
0x180023b34  mov     r15d, [rsi+1Ch]
0x180023b38  mov     [rsp+38h+arg_0], rbp
0x180023b3d  add     r15d, [rsi+18h]
0x180023b41  jz      loc_180023C14
0x180023b47  mov     ebx, [rsi+20h]
0x180023b4a  add     rbx, [rsi+148h]
0x180023b51  jz      loc_180023C14
0x180023b57  xor     ebp, ebp
0x180023b59  nop     dword ptr [rax+00000000h]
0x180023b60  cmp     ebp, r15d
0x180023b63  jnb     loc_180023C50
0x180023b69  cmp     dword ptr [rbx+2Ch], 2
0x180023b6d  jz      loc_180023C09
0x180023b73  mov     eax, [rbx]
0x180023b75  test    eax, eax
0x180023b77  jz      loc_180023C2E
0x180023b7d  add     rax, [rsi+140h]
0x180023b84  mov     edi, [rbx+34h]
0x180023b87  test    edi, edi
0x180023b89  jz      loc_180023C48
0x180023b8f  mov     r9d, [rbx+38h]
0x180023b93  add     r9, [rsi+148h]
0x180023b9a  test    rax, rax
0x180023b9d  jz      short loc_180023C14
0x180023b9f  test    edi, edi
0x180023ba1  jz      short loc_180023C14
0x180023ba3  test    r9, r9
0x180023ba6  jz      short loc_180023C14
0x180023ba8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180023baf  nop
0x180023bb0  cmp     byte ptr [rax+r8+1], 0
0x180023bb6  lea     r8, [r8+1]
0x180023bba  jnz     short loc_180023BB0
0x180023bbc  xor     r11d, r11d
0x180023bbf  xor     r10d, r10d
0x180023bc2  cmp     r10d, edi
0x180023bc5  jnb     short loc_180023BFE
0x180023bc7  mov     eax, [r9]
0x180023bca  test    eax, eax
0x180023bcc  jz      short loc_180023C14
0x180023bce  mov     edx, eax
0x180023bd0  add     rdx, [rsi+140h]
0x180023bd7  jz      short loc_180023C14
0x180023bd9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023be0  inc     rax
0x180023be3  cmp     byte ptr [rdx+rax], 0
0x180023be7  jnz     short loc_180023BE0
0x180023be9  mov     ecx, [rbx+30h]
0x180023bec  inc     r10d
0x180023bef  add     r9, rcx
0x180023bf2  cmp     r11d, eax
0x180023bf5  cmovnb  eax, r11d
0x180023bf9  mov     r11d, eax
0x180023bfc  jmp     short loc_180023BC2
0x180023bfe  lea     eax, [r11+r8]
0x180023c02  add     r14d, 2
0x180023c06  add     r14d, eax
0x180023c09  inc     ebp
0x180023c0b  add     rbx, 54h ; 'T'
0x180023c0f  jmp     loc_180023B60
0x180023c14  xor     eax, eax
0x180023c16  mov     r14, [rsp+38h+arg_8]
0x180023c1b  mov     rbp, [rsp+38h+arg_0]
0x180023c20  mov     rbx, [rsp+38h+arg_10]
0x180023c25  add     rsp, 20h
0x180023c29  pop     r15
0x180023c2b  pop     rdi
0x180023c2c  pop     rsi
0x180023c2d  retn
0x180023c2e  xor     eax, eax
0x180023c30  jmp     loc_180023B84
0x180023c35  mov     rax, rdi
0x180023c38  jmp     loc_180023AF2
0x180023c3d  mov     r14d, 5Eh ; '^'
0x180023c43  jmp     loc_180023B34
0x180023c48  xor     r9d, r9d
0x180023c4b  jmp     loc_180023B9A
0x180023c50  lea     eax, [r14+9]
0x180023c54  and     eax, 0FFFFFFF8h
0x180023c57  jmp     short loc_180023C16
```
