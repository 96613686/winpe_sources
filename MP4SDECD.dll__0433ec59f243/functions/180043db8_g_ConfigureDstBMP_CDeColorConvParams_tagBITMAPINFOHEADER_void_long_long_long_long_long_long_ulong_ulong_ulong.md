# g_ConfigureDstBMP(CDeColorConvParams *,tagBITMAPINFOHEADER *,void *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x180043db8`
- end: `0x180043f7d`
- name: `?g_ConfigureDstBMP@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@PEAXJJJJJJKKK@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct CDeColorConvParams *, struct tagBITMAPINFOHEADER *, void *, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012114`

## callees

- `0x1800439b4`
- `0x180043cb0`
- `0x180043db8`
- `0x180043f84`

## pseudocode

```c
__int64 __fastcall g_ConfigureDstBMP(
        struct CDeColorConvParams *a1,
        struct tagBITMAPINFOHEADER *a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v9; // r10d
  int v13; // r11d
  WORD *p_biBitCount; // rbp
  LONG *p_biWidth; // rsi
  int v16; // ecx
  __int64 result; // rax
  unsigned int v18; // [rsp+28h] [rbp-80h]
  unsigned int v19; // [rsp+30h] [rbp-78h]
  unsigned int v20; // [rsp+38h] [rbp-70h]
  unsigned int v21; // [rsp+40h] [rbp-68h]
  unsigned int v22; // [rsp+48h] [rbp-60h]
  unsigned int v23; // [rsp+50h] [rbp-58h]

  v9 = *((_DWORD *)a1 + 48);
  if ( __PAIR64__(a2->biBitCount, a2->biCompression) == *((_QWORD *)a1 + 24) )
  {
    v13 = a8;
    if ( a2->biWidth == *((_DWORD *)a1 + 50)
      && a2->biHeight == *((_DWORD *)a1 + 51)
      && a8 == *((_DWORD *)a1 + 52)
      && a9 == *((_DWORD *)a1 + 53)
      && a6 == *((_DWORD *)a1 + 54)
      && a7 == *((_DWORD *)a1 + 55)
      && *((void **)a1 + 15) == a3 )
    {
      *((_DWORD *)a1 + 15) = 0;
      return 0;
    }
  }
  else
  {
    v13 = a8;
  }
  p_biBitCount = &a2->biBitCount;
  p_biWidth = &a2->biWidth;
  v16 = ((unsigned __int8)a3 & 0x1F) == 0 && (((int)((*p_biWidth * *p_biBitCount + 31) & 0xFFFFFFE0) / 8) & 0x1F) == 0;
  if ( a2->biCompression == v9
    && *p_biWidth == *((_DWORD *)a1 + 50)
    && a2->biHeight == *((_DWORD *)a1 + 51)
    && *p_biBitCount == *((_DWORD *)a1 + 49)
    && v16 == *((_DWORD *)a1 + 16)
    || (*((_DWORD *)a1 + 16) = v16, result = g_ConfigureDstBMPProperty(a1, a2), !(_DWORD)result) )
  {
    if ( v13 == *p_biWidth || !*((_DWORD *)a1 + 13) || *((_DWORD *)a1 + 14) )
      g_ConfigureBMPSizeAndPointersInfo(a1, a4, (int)a3, a6, a7, v18, v19, v20);
    else
      g_ConfigureBMPSizeAndPointersInfo_OnScreen(a2, a1, (int)a3, a4, a6, a7, v19, a9, v21, v22, v23);
    *((_DWORD *)a1 + 15) = 1;
    *((_QWORD *)a1 + 15) = a3;
    *((_DWORD *)a1 + 50) = *p_biWidth;
    *((_DWORD *)a1 + 51) = a2->biHeight;
    *((_DWORD *)a1 + 48) = a2->biCompression;
    *((_DWORD *)a1 + 49) = *p_biBitCount;
    *((_DWORD *)a1 + 52) = a8;
    *((_DWORD *)a1 + 53) = a9;
    *((_DWORD *)a1 + 54) = a6;
    *((_DWORD *)a1 + 55) = a7;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180043db8  mov     [rsp+arg_18], r9d
0x180043dbd  push    rbx
0x180043dbe  push    rbp
0x180043dbf  push    rsi
0x180043dc0  push    rdi
0x180043dc1  push    r12
0x180043dc3  push    r13
0x180043dc5  push    r14
0x180043dc7  push    r15
0x180043dc9  sub     rsp, 68h
0x180043dcd  mov     r10d, [rcx+0C0h]
0x180043dd4  mov     r12, r8
0x180043dd7  mov     rdi, rdx
0x180043dda  mov     r13d, [rsp+0A8h+arg_40]
0x180043de2  mov     rbx, rcx
0x180043de5  mov     r14d, [rsp+0A8h+arg_30]
0x180043ded  mov     r15d, [rsp+0A8h+arg_28]
0x180043df5  cmp     [rdx+10h], r10d
0x180043df9  jnz     short loc_180043E5B
0x180043dfb  movzx   eax, word ptr [rdx+0Eh]
0x180043dff  cmp     eax, [rcx+0C4h]
0x180043e05  jnz     short loc_180043E5B
0x180043e07  mov     eax, [rcx+0C8h]
0x180043e0d  mov     r11d, [rsp+0A8h+arg_38]
0x180043e15  cmp     [rdx+4], eax
0x180043e18  jnz     short loc_180043E63
0x180043e1a  mov     eax, [rcx+0CCh]
0x180043e20  cmp     [rdx+8], eax
0x180043e23  jnz     short loc_180043E63
0x180043e25  cmp     r11d, [rcx+0D0h]
0x180043e2c  jnz     short loc_180043E63
0x180043e2e  cmp     r13d, [rcx+0D4h]
0x180043e35  jnz     short loc_180043E63
0x180043e37  cmp     r15d, [rcx+0D8h]
0x180043e3e  jnz     short loc_180043E63
0x180043e40  cmp     r14d, [rcx+0DCh]
0x180043e47  jnz     short loc_180043E63
0x180043e49  cmp     [rcx+78h], r8
0x180043e4d  jnz     short loc_180043E63
0x180043e4f  mov     dword ptr [rcx+3Ch], 0
0x180043e56  jmp     loc_180043F6A
0x180043e5b  mov     r11d, [rsp+0A8h+arg_38]
0x180043e63  lea     rbp, [rdx+0Eh]
0x180043e67  lea     rsi, [rdx+4]
0x180043e6b  test    r12b, 1Fh
0x180043e6f  jnz     short loc_180043E91
0x180043e71  movzx   eax, word ptr [rbp+0]
0x180043e75  mov     ecx, 8
0x180043e7a  imul    eax, [rsi]
0x180043e7d  add     eax, 1Fh
0x180043e80  and     eax, 0FFFFFFE0h
0x180043e83  cdq
0x180043e84  idiv    ecx
0x180043e86  test    al, 1Fh
0x180043e88  jnz     short loc_180043E91
0x180043e8a  mov     ecx, 1
0x180043e8f  jmp     short loc_180043E93
0x180043e91  xor     ecx, ecx
0x180043e93  cmp     [rdi+10h], r10d
0x180043e97  jnz     short loc_180043EBF
0x180043e99  mov     eax, [rbx+0C8h]
0x180043e9f  cmp     [rsi], eax
0x180043ea1  jnz     short loc_180043EBF
0x180043ea3  mov     eax, [rbx+0CCh]
0x180043ea9  cmp     [rdi+8], eax
0x180043eac  jnz     short loc_180043EBF
0x180043eae  movzx   eax, word ptr [rbp+0]
0x180043eb2  cmp     eax, [rbx+0C4h]
0x180043eb8  jnz     short loc_180043EBF
0x180043eba  cmp     ecx, [rbx+40h]
0x180043ebd  jz      short loc_180043ED5
0x180043ebf  mov     [rbx+40h], ecx
0x180043ec2  mov     rdx, rdi; struct tagBITMAPINFOHEADER *
0x180043ec5  mov     rcx, rbx; struct CDeColorConvParams *
0x180043ec8  call    ?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z; g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)
0x180043ecd  test    eax, eax
0x180043ecf  jnz     loc_180043F6C
0x180043ed5  cmp     r11d, [rsi]
0x180043ed8  jz      short loc_180043F02
0x180043eda  cmp     dword ptr [rbx+34h], 0
0x180043ede  jz      short loc_180043F02
0x180043ee0  cmp     dword ptr [rbx+38h], 0
0x180043ee4  jnz     short loc_180043F02
0x180043ee6  mov     [rsp+0A8h+var_70], r13d; int
0x180043eeb  mov     rdx, rbx; struct CDeColorConvParams *
0x180043eee  mov     [rsp+0A8h+var_80], r14d; int
0x180043ef3  mov     rcx, rdi; struct tagBITMAPINFOHEADER *
0x180043ef6  mov     [rsp+0A8h+var_88], r15d; int
0x180043efb  call    ?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z; g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)
0x180043f00  jmp     short loc_180043F19
0x180043f02  mov     edx, [rsp+0A8h+arg_18]; int
0x180043f09  mov     r9d, r15d; int
0x180043f0c  mov     rcx, rbx; struct CDeColorConvParams *
0x180043f0f  mov     [rsp+0A8h+var_88], r14d; int
0x180043f14  call    ?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJJJKKK@Z; g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,long,long,ulong,ulong,ulong)
0x180043f19  mov     dword ptr [rbx+3Ch], 1
0x180043f20  mov     [rbx+78h], r12
0x180043f24  mov     eax, [rsi]
0x180043f26  mov     [rbx+0C8h], eax
0x180043f2c  mov     eax, [rdi+8]
0x180043f2f  mov     [rbx+0CCh], eax
0x180043f35  mov     eax, [rdi+10h]
0x180043f38  mov     [rbx+0C0h], eax
0x180043f3e  movzx   eax, word ptr [rbp+0]
0x180043f42  mov     [rbx+0C4h], eax
0x180043f48  mov     eax, [rsp+0A8h+arg_38]
0x180043f4f  mov     [rbx+0D0h], eax
0x180043f55  mov     [rbx+0D4h], r13d
0x180043f5c  mov     [rbx+0D8h], r15d
0x180043f63  mov     [rbx+0DCh], r14d
0x180043f6a  xor     eax, eax
0x180043f6c  add     rsp, 68h
0x180043f70  pop     r15
0x180043f72  pop     r14
0x180043f74  pop     r13
0x180043f76  pop     r12
0x180043f78  pop     rdi
0x180043f79  pop     rsi
0x180043f7a  pop     rbp
0x180043f7b  pop     rbx
0x180043f7c  retn
```
