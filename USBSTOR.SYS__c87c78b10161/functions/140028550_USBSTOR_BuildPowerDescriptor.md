# USBSTOR_BuildPowerDescriptor

- ea: `0x140028550`
- end: `0x14002861f`
- name: `USBSTOR_BuildPowerDescriptor`
- size: `207`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400232d0`

## callees

- `0x1400090a8`
- `0x140010664`
- `0x140013a40`
- `0x140028550`

## pseudocode

```c
__int64 __fastcall USBSTOR_BuildPowerDescriptor(__int64 a1, void *a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  bool v8; // zf
  unsigned int v9; // edx
  __int128 Src; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+30h] [rbp-18h]

  v3 = *(_QWORD *)(a1 + 64);
  Src = 0;
  v6 = *(_QWORD *)(v3 + 16);
  v12 = 0;
  v7 = *(_QWORD *)(v6 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v8 = *(_QWORD *)(v7 + 1968) == 0;
  *(_QWORD *)&Src = 0x1400000014LL;
  BYTE10(Src) = !v8;
  if ( (unsigned __int8)USBSTOR_IsDeviceAsyncCapable(v7) || (*(_DWORD *)(v7 + 132) & 0x800) != 0 )
  {
    BYTE9(Src) = 1;
    BYTE13(Src) = 1;
  }
  if ( *a3 <= v9 )
    v9 = *a3;
  else
    *a3 = v9;
  memmove(a2, &Src, v9);
  return 0;
}

```

## disassembly

```asm
0x140028550  mov     [rsp+arg_0], rbx
0x140028555  mov     [rsp+arg_8], rsi
0x14002855a  push    rdi
0x14002855b  sub     rsp, 40h
0x14002855f  mov     rax, [rcx+40h]
0x140028563  xorps   xmm0, xmm0
0x140028566  mov     rdi, r8
0x140028569  mov     rsi, rdx
0x14002856c  movups  [rsp+48h+Src], xmm0
0x140028571  mov     rcx, [rax+10h]
0x140028575  xor     eax, eax
0x140028577  mov     [rsp+48h+var_18], eax
0x14002857b  mov     rbx, [rcx+40h]
0x14002857f  mov     rcx, cs:WPP_GLOBAL_Control
0x140028586  lea     rax, WPP_GLOBAL_Control
0x14002858d  cmp     rcx, rax
0x140028590  jz      short loc_1400285B4
0x140028592  mov     eax, [rcx+2Ch]
0x140028595  test    al, 10h
0x140028597  jz      short loc_1400285B4
0x140028599  cmp     byte ptr [rcx+29h], 4
0x14002859d  jb      short loc_1400285B4
0x14002859f  mov     rcx, [rcx+18h]
0x1400285a3  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400285aa  mov     edx, 2Eh ; '.'
0x1400285af  call    WPP_SF_
0x1400285b4  cmp     qword ptr [rbx+7B0h], 0
0x1400285bc  mov     edx, 14h
0x1400285c1  mov     rcx, rbx
0x1400285c4  mov     dword ptr [rsp+48h+Src], edx
0x1400285c8  setnz   byte ptr [rsp+48h+Src+0Ah]
0x1400285cd  mov     dword ptr [rsp+48h+Src+4], edx
0x1400285d1  call    USBSTOR_IsDeviceAsyncCapable
0x1400285d6  test    al, al
0x1400285d8  jnz     short loc_1400285E6
0x1400285da  test    dword ptr [rbx+84h], 800h
0x1400285e4  jz      short loc_1400285F0
0x1400285e6  mov     byte ptr [rsp+48h+Src+9], 1
0x1400285eb  mov     byte ptr [rsp+48h+Src+0Dh], 1
0x1400285f0  mov     eax, [rdi]
0x1400285f2  cmp     eax, edx
0x1400285f4  jbe     short loc_1400285FA
0x1400285f6  mov     [rdi], edx
0x1400285f8  jmp     short loc_1400285FC
0x1400285fa  mov     edx, eax
0x1400285fc  mov     r8d, edx; Size
0x1400285ff  mov     rcx, rsi; void *
0x140028602  lea     rdx, [rsp+48h+Src]; Src
0x140028607  call    memmove
0x14002860c  mov     rbx, [rsp+48h+arg_0]
0x140028611  xor     eax, eax
0x140028613  mov     rsi, [rsp+48h+arg_8]
0x140028618  add     rsp, 40h
0x14002861c  pop     rdi
0x14002861d  retn
```
