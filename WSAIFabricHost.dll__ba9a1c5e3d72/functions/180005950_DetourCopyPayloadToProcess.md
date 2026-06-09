# DetourCopyPayloadToProcess

- ea: `0x180005950`
- end: `0x180005bee`
- name: `DetourCopyPayloadToProcess`
- size: `670`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800105b0`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x180005950`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800059f7`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005a60`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005ad5`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005b3a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005b85`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005bb1`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800059f7`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005a60`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005ad5`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005b3a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005b85`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180005bb1`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800059a0`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x1800059a0`

## pseudocode

```c
__int64 __fastcall DetourCopyPayloadToProcess(HANDLE hProcess, __int128 *a2, const void *a3, unsigned int a4)
{
  __int64 v4; // rsi
  char *v8; // rdi
  __int128 v9; // xmm0
  SIZE_T NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v12[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h]
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  int v17; // [rsp+60h] [rbp-A0h]
  __int128 v18; // [rsp+64h] [rbp-9Ch]
  int v19; // [rsp+74h] [rbp-8Ch]
  _DWORD v20[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+B0h] [rbp-50h]
  _OWORD Buffer[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v25; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+100h] [rbp+0h] BYREF
  __int16 v27; // [rsp+106h] [rbp+6h]
  int v28; // [rsp+114h] [rbp+14h]
  __int16 v29; // [rsp+118h] [rbp+18h]

  v4 = a4;
  v8 = (char *)VirtualAllocEx(hProcess, 0, a4 + 456, 0x1000u, 4u);
  if ( !v8 )
    return 0;
  memset(Buffer, 0, sizeof(Buffer));
  LOWORD(Buffer[0]) = 23117;
  NumberOfBytesWritten = 0;
  v25 = 0;
  HIDWORD(v25) = 64;
  if ( !WriteProcessMemory(hProcess, v8, Buffer, 0x40u, &NumberOfBytesWritten) )
    return 0;
  if ( NumberOfBytesWritten != 64 )
    return 0;
  memset_0(&v26, 0, 0x108u);
  v26 = 17744;
  v27 = 1;
  v28 = 536871152;
  v29 = 523;
  if ( !WriteProcessMemory(hProcess, v8 + 64, &v26, 0x108u, &NumberOfBytesWritten) )
    return 0;
  if ( NumberOfBytesWritten != 264 )
    return 0;
  v15 = 0;
  v14 = 0x72756F7465642ELL;
  v19 = 0;
  v16 = 368;
  v17 = v4 + 88;
  v18 = 0;
  if ( !WriteProcessMemory(hProcess, v8 + 328, &v14, 0x28u, &NumberOfBytesWritten) )
    return 0;
  if ( NumberOfBytesWritten != 40 )
    return 0;
  v20[0] = 64;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v20[1] = 7500868;
  v20[2] = 64;
  v20[3] = v4 + 88;
  if ( !WriteProcessMemory(hProcess, v8 + 368, v20, 0x40u, &NumberOfBytesWritten) )
    return 0;
  if ( NumberOfBytesWritten == 64
    && (v9 = *a2,
        v12[1] = 0,
        v12[0] = v4 + 24,
        v13 = v9,
        WriteProcessMemory(hProcess, v8 + 432, v12, 0x18u, &NumberOfBytesWritten))
    && NumberOfBytesWritten == 24
    && WriteProcessMemory(hProcess, v8 + 456, a3, (unsigned int)v4, &NumberOfBytesWritten)
    && NumberOfBytesWritten == v4 )
  {
    return 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180005950  push    rbp
0x180005952  push    rbx
0x180005953  push    rsi
0x180005954  push    rdi
0x180005955  push    r12
0x180005957  push    r13
0x180005959  push    r14
0x18000595b  push    r15
0x18000595d  lea     rbp, [rsp-128h]
0x180005965  sub     rsp, 228h
0x18000596c  mov     rax, cs:__security_cookie
0x180005973  xor     rax, rsp
0x180005976  mov     [rbp+160h+var_50], rax
0x18000597d  mov     esi, r9d
0x180005980  mov     r15, r8
0x180005983  mov     r12, rdx
0x180005986  mov     [rsp+260h+flProtect], 4; flProtect
0x18000598e  xor     edx, edx; lpAddress
0x180005990  mov     r9d, 1000h; flAllocationType
0x180005996  mov     rbx, rcx
0x180005999  lea     r8d, [rsi+1C8h]; dwSize
0x1800059a0  call    cs:__imp_VirtualAllocEx
0x1800059a6  mov     rdi, rax
0x1800059a9  test    rax, rax
0x1800059ac  jz      loc_180005BC9
0x1800059b2  xorps   xmm0, xmm0
0x1800059b5  lea     r8, [rbp+160h+Buffer]; lpBuffer
0x1800059b9  mov     eax, 5A4Dh
0x1800059be  xor     r13d, r13d
0x1800059c1  movups  [rbp+160h+Buffer], xmm0
0x1800059c5  mov     word ptr [rbp+160h+Buffer], ax
0x1800059c9  mov     r9d, 40h ; '@'; nSize
0x1800059cf  lea     rax, [rsp+260h+NumberOfBytesWritten]
0x1800059d4  mov     [rsp+260h+NumberOfBytesWritten], r13
0x1800059d9  movups  [rbp+160h+var_170], xmm0
0x1800059dd  mov     rdx, rdi; lpBaseAddress
0x1800059e0  mov     qword ptr [rsp+260h+flProtect], rax; lpNumberOfBytesWritten
0x1800059e5  mov     rcx, rbx; hProcess
0x1800059e8  mov     dword ptr [rbp+160h+var_170+0Ch], 40h ; '@'
0x1800059ef  movups  [rbp+160h+var_190], xmm0
0x1800059f3  movups  [rbp+160h+var_180], xmm0
0x1800059f7  call    cs:__imp_WriteProcessMemory
0x1800059fd  test    eax, eax
0x1800059ff  jz      loc_180005BC9
0x180005a05  cmp     [rsp+260h+NumberOfBytesWritten], 40h ; '@'
0x180005a0b  jnz     loc_180005BC9
0x180005a11  xor     edx, edx; Val
0x180005a13  lea     rcx, [rbp+160h+var_160]; void *
0x180005a17  mov     r8d, 108h; Size
0x180005a1d  lea     r14, [rdi+40h]
0x180005a21  call    memset_0
0x180005a26  mov     eax, 1
0x180005a2b  mov     [rbp+160h+var_160], 4550h
0x180005a32  mov     [rbp+160h+var_15A], ax
0x180005a36  lea     r8, [rbp+160h+var_160]; lpBuffer
0x180005a3a  mov     eax, 20Bh
0x180005a3f  mov     [rbp+160h+var_14C], 200000F0h
0x180005a46  mov     [rbp+160h+var_148], ax
0x180005a4a  mov     r9d, 108h; nSize
0x180005a50  lea     rax, [rsp+260h+NumberOfBytesWritten]
0x180005a55  mov     rdx, r14; lpBaseAddress
0x180005a58  mov     rcx, rbx; hProcess
0x180005a5b  mov     qword ptr [rsp+260h+flProtect], rax; lpNumberOfBytesWritten
0x180005a60  call    cs:__imp_WriteProcessMemory
0x180005a66  test    eax, eax
0x180005a68  jz      loc_180005BC9
0x180005a6e  cmp     [rsp+260h+NumberOfBytesWritten], 108h
0x180005a77  jnz     loc_180005BC9
0x180005a7d  mov     rax, 72756F7465642Eh
0x180005a87  mov     [rsp+260h+var_208], r13d
0x180005a8c  mov     [rsp+260h+var_210], rax
0x180005a91  lea     r8, [rsp+260h+var_210]; lpBuffer
0x180005a96  lea     eax, [r14+108h]
0x180005a9d  mov     [rsp+260h+var_1EC], r13d
0x180005aa2  sub     eax, edi
0x180005aa4  lea     rdx, [r14+108h]; lpBaseAddress
0x180005aab  add     eax, 28h ; '('
0x180005aae  lea     edi, [rsi+58h]
0x180005ab1  mov     [rsp+260h+var_204], eax
0x180005ab5  xorps   xmm0, xmm0
0x180005ab8  lea     rax, [rsp+260h+NumberOfBytesWritten]
0x180005abd  mov     [rsp+260h+var_200], edi
0x180005ac1  mov     r9d, 28h ; '('; nSize
0x180005ac7  mov     qword ptr [rsp+260h+flProtect], rax; lpNumberOfBytesWritten
0x180005acc  mov     rcx, rbx; hProcess
0x180005acf  movdqu  [rsp+260h+var_1FC], xmm0
0x180005ad5  call    cs:__imp_WriteProcessMemory
0x180005adb  test    eax, eax
0x180005add  jz      loc_180005BC9
0x180005ae3  cmp     [rsp+260h+NumberOfBytesWritten], 28h ; '('
0x180005ae9  jnz     loc_180005BC9
0x180005aef  xorps   xmm0, xmm0
0x180005af2  mov     [rbp+160h+var_1E0], 40h ; '@'
0x180005af9  xorps   xmm1, xmm1
0x180005afc  movdqa  [rbp+160h+var_1D0], xmm0
0x180005b01  lea     rax, [rsp+260h+NumberOfBytesWritten]
0x180005b06  movdqa  [rbp+160h+var_1C0], xmm1
0x180005b0b  mov     r9d, 40h ; '@'; nSize
0x180005b11  movdqa  [rbp+160h+var_1B0], xmm0
0x180005b16  lea     r8, [rbp+160h+var_1E0]; lpBuffer
0x180005b1a  mov     qword ptr [rsp+260h+flProtect], rax; lpNumberOfBytesWritten
0x180005b1f  lea     rdx, [r14+130h]; lpBaseAddress
0x180005b26  mov     [rbp+160h+var_1DC], 727444h
0x180005b2d  mov     rcx, rbx; hProcess
0x180005b30  mov     [rbp+160h+var_1D8], 40h ; '@'
0x180005b37  mov     [rbp+160h+var_1D4], edi
0x180005b3a  call    cs:__imp_WriteProcessMemory
0x180005b40  test    eax, eax
0x180005b42  jz      loc_180005BC9
0x180005b48  cmp     [rsp+260h+NumberOfBytesWritten], 40h ; '@'
0x180005b4e  jnz     short loc_180005BC9
0x180005b50  movups  xmm0, xmmword ptr [r12]
0x180005b55  lea     eax, [rsi+18h]
0x180005b58  mov     [rsp+260h+var_224], r13d
0x180005b5d  mov     [rsp+260h+var_228], eax
0x180005b61  lea     r8, [rsp+260h+var_228]; lpBuffer
0x180005b66  lea     rax, [rsp+260h+NumberOfBytesWritten]
0x180005b6b  mov     r9d, 18h; nSize
0x180005b71  lea     rdx, [r14+170h]; lpBaseAddress
0x180005b78  mov     qword ptr [rsp+260h+flProtect], rax; lpNumberOfBytesWritten
0x180005b7d  mov     rcx, rbx; hProcess
0x180005b80  movups  [rsp+260h+var_220], xmm0
0x180005b85  call    cs:__imp_WriteProcessMemory
0x180005b8b  test    eax, eax
0x180005b8d  jz      short loc_180005BC9
0x180005b8f  cmp     [rsp+260h+NumberOfBytesWritten], 18h
0x180005b95  jnz     short loc_180005BC9
0x180005b97  lea     rcx, [rsp+260h+NumberOfBytesWritten]
0x180005b9c  mov     r9d, esi; nSize
0x180005b9f  mov     qword ptr [rsp+260h+flProtect], rcx; lpNumberOfBytesWritten
0x180005ba4  lea     rdx, [r14+188h]; lpBaseAddress
0x180005bab  mov     rcx, rbx; hProcess
0x180005bae  mov     r8, r15; lpBuffer
0x180005bb1  call    cs:__imp_WriteProcessMemory
0x180005bb7  test    eax, eax
0x180005bb9  jz      short loc_180005BC9
0x180005bbb  cmp     [rsp+260h+NumberOfBytesWritten], rsi
0x180005bc0  jnz     short loc_180005BC9
0x180005bc2  mov     eax, 1
0x180005bc7  jmp     short loc_180005BCB
0x180005bc9  xor     eax, eax
0x180005bcb  mov     rcx, [rbp+160h+var_50]
0x180005bd2  xor     rcx, rsp; StackCookie
0x180005bd5  call    __security_check_cookie
0x180005bda  add     rsp, 228h
0x180005be1  pop     r15
0x180005be3  pop     r14
0x180005be5  pop     r13
0x180005be7  pop     r12
0x180005be9  pop     rdi
0x180005bea  pop     rsi
0x180005beb  pop     rbx
0x180005bec  pop     rbp
0x180005bed  retn
```
