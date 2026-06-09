# g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x180043cb0`
- end: `0x180043db1`
- name: `?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z`
- size: `257`
- prototype: `void __fastcall(struct tagBITMAPINFOHEADER *, struct CDeColorConvParams *, int, int, int, int, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180043db8`

## callees

- `0x180043cb0`

## pseudocode

```c
void __fastcall g_ConfigureBMPSizeAndPointersInfo_OnScreen(
        struct tagBITMAPINFOHEADER *a1,
        struct CDeColorConvParams *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  int v8; // r8d
  unsigned int v10; // r11d
  int v11; // eax
  unsigned int v12; // r11d
  int v13; // eax
  int v14; // ecx
  int v15; // r10d
  int v16; // ebx
  LONG biHeight; // eax
  int v18; // r8d
  int v19; // r11d
  int v20; // r10d
  int v21; // ecx
  int v22; // eax

  v8 = *((_DWORD *)a2 + 2);
  v10 = *((unsigned __int16 *)a2 + 7);
  v11 = *((_DWORD *)a2 + 1) * v10;
  v12 = v10 >> 3;
  *((_DWORD *)a2 + 20) = v12;
  v13 = (int)((v11 + 31) & 0xFFFFFFE0) / 8;
  v14 = -v8;
  v15 = v13;
  *((_DWORD *)a2 + 19) = v13;
  if ( v8 > 0 )
    v14 = v8;
  *((_DWORD *)a2 + 21) = v13 * v14;
  if ( v8 > 0 )
  {
    v15 = -v13;
    *((_DWORD *)a2 + 19) = -v13;
  }
  *((_DWORD *)a2 + 22) = 16 * v12;
  *((_DWORD *)a2 + 23) = 8 * v12;
  *((_DWORD *)a2 + 24) = 16 * v15;
  *((_DWORD *)a2 + 25) = 8 * (v15 - v12);
  v16 = (int)((a1->biWidth * a1->biBitCount + 31) & 0xFFFFFFE0) / 8;
  biHeight = -a1->biHeight;
  if ( a1->biHeight > 0 )
    biHeight = a1->biHeight;
  v18 = a6 * ((int)((a1->biWidth * a1->biBitCount + 31) & 0xFFFFFFE0) / 8);
  v19 = a5 * v12;
  v20 = v16 * (a8 - 1);
  if ( a1->biHeight >= 0 )
  {
    v21 = v18 + v19 + v20;
    v22 = v21;
  }
  else
  {
    v21 = 0;
    v22 = v19 + v16 * (biHeight - 1) - v20 - v18;
  }
  *((_DWORD *)a2 + 32) = v22;
  *((_DWORD *)a2 + 33) = v21;
  *((_DWORD *)a2 + 34) = v21;
  *((_DWORD *)a2 + 35) = v21;
}

```

## disassembly

```asm
0x180043cb0  mov     [rsp+arg_0], rbx
0x180043cb5  mov     [rsp+arg_8], rdi
0x180043cba  mov     r8d, [rdx+8]
0x180043cbe  mov     r9, rdx
0x180043cc1  movzx   eax, word ptr [rdx+0Eh]
0x180043cc5  mov     rdi, rcx
0x180043cc8  mov     r11d, eax
0x180043ccb  mov     ebx, 8
0x180043cd0  imul    eax, [rdx+4]
0x180043cd4  mov     ecx, r8d
0x180043cd7  shr     r11d, 3
0x180043cdb  mov     [rdx+50h], r11d
0x180043cdf  add     eax, 1Fh
0x180043ce2  and     eax, 0FFFFFFE0h
0x180043ce5  cdq
0x180043ce6  idiv    ebx
0x180043ce8  neg     ecx
0x180043cea  mov     r10d, eax
0x180043ced  mov     [r9+4Ch], eax
0x180043cf1  cmovs   ecx, r8d
0x180043cf5  imul    ecx, eax
0x180043cf8  mov     [r9+54h], ecx
0x180043cfc  test    r8d, r8d
0x180043cff  jle     short loc_180043D08
0x180043d01  neg     r10d
0x180043d04  mov     [r9+4Ch], r10d
0x180043d08  mov     eax, r11d
0x180043d0b  shl     eax, 4
0x180043d0e  mov     [r9+58h], eax
0x180043d12  lea     eax, ds:0[r11*8]
0x180043d1a  mov     [r9+5Ch], eax
0x180043d1e  mov     eax, r10d
0x180043d21  shl     eax, 4
0x180043d24  sub     r10d, r11d
0x180043d27  mov     [r9+60h], eax
0x180043d2b  shl     r10d, 3
0x180043d2f  mov     [r9+64h], r10d
0x180043d33  movzx   eax, word ptr [rdi+0Eh]
0x180043d37  imul    eax, [rdi+4]
0x180043d3b  mov     r10d, [rsp+arg_38]
0x180043d40  add     eax, 1Fh
0x180043d43  and     eax, 0FFFFFFE0h
0x180043d46  cdq
0x180043d47  idiv    ebx
0x180043d49  mov     edx, [rdi+8]
0x180043d4c  mov     ebx, eax
0x180043d4e  mov     eax, edx
0x180043d50  neg     eax
0x180043d52  mov     r8d, ebx
0x180043d55  cmovs   eax, edx
0x180043d58  imul    r8d, [rsp+arg_28]
0x180043d5e  imul    r11d, [rsp+arg_20]
0x180043d64  dec     r10d
0x180043d67  imul    r10d, ebx
0x180043d6b  test    edx, edx
0x180043d6d  jns     short loc_180043D81
0x180043d6f  xor     ecx, ecx
0x180043d71  dec     eax
0x180043d73  imul    eax, ebx
0x180043d76  sub     eax, r10d
0x180043d79  sub     eax, r8d
0x180043d7c  add     eax, r11d
0x180043d7f  jmp     short loc_180043D8A
0x180043d81  lea     ecx, [r11+r10]
0x180043d85  add     ecx, r8d
0x180043d88  mov     eax, ecx
0x180043d8a  mov     [r9+80h], eax
0x180043d91  mov     [r9+84h], ecx
0x180043d98  mov     [r9+88h], ecx
0x180043d9f  mov     [r9+8Ch], ecx
0x180043da6  mov     rbx, [rsp+arg_0]
0x180043dab  mov     rdi, [rsp+arg_8]
0x180043db0  retn
```
