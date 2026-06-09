# g_ConfigureDstBMP(CDeColorConvParams *,tagBITMAPINFOHEADER *,void *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x18001e2c8`
- end: `0x18001e3fe`
- name: `?g_ConfigureDstBMP@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@PEAXJJJJJJKKK@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct CDeColorConvParams *, struct tagBITMAPINFOHEADER *, void *, unsigned int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a77c`

## callees

- `0x18001df4c`
- `0x18001e1d0`
- `0x18001e2c8`
- `0x18001e404`

## pseudocode

```c
__int64 __fastcall g_ConfigureDstBMP(
        struct CDeColorConvParams *a1,
        struct tagBITMAPINFOHEADER *a2,
        void *a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int biBitCount; // ecx
  int v13; // edx
  __int64 result; // rax
  unsigned int v15; // [rsp+20h] [rbp-78h]
  unsigned int v16; // [rsp+28h] [rbp-70h]
  int v17; // [rsp+30h] [rbp-68h]
  unsigned int v18; // [rsp+40h] [rbp-58h]
  unsigned int v19; // [rsp+48h] [rbp-50h]
  unsigned int v20; // [rsp+50h] [rbp-48h]

  if ( a2->biCompression != *((_DWORD *)a1 + 42) )
    goto LABEL_12;
  biBitCount = a2->biBitCount;
  v13 = *((_DWORD *)a1 + 43);
  if ( biBitCount == v13
    && a2->biHeight == *((_DWORD *)a1 + 44)
    && a8 == *((_DWORD *)a1 + 45)
    && a9 == *((_DWORD *)a1 + 46)
    && a6 == *((_DWORD *)a1 + 47)
    && a7 == *((_DWORD *)a1 + 48)
    && *((void **)a1 + 12) == a3 )
  {
    *((_DWORD *)a1 + 15) = 0;
    return 0;
  }
  if ( a2->biHeight != *((_DWORD *)a1 + 44) || biBitCount != v13 )
  {
LABEL_12:
    result = g_ConfigureDstBMPProperty(a1, a2);
    if ( (_DWORD)result )
      return result;
  }
  if ( a8 == a2->biWidth )
  {
    g_ConfigureBMPSizeAndPointersInfo(a1, a4, (int)a3, a4, v15, v16);
  }
  else
  {
    if ( !*((_DWORD *)a1 + 13) )
      return 4294967196LL;
    g_ConfigureBMPSizeAndPointersInfo_OnScreen(a2, a1, (int)a3, a4, a6, a7, v17, a9, v18, v19, v20);
  }
  *((_DWORD *)a1 + 15) = 1;
  *((_QWORD *)a1 + 12) = a3;
  *((_DWORD *)a1 + 44) = a2->biHeight;
  *((_DWORD *)a1 + 42) = a2->biCompression;
  *((_DWORD *)a1 + 43) = a2->biBitCount;
  *((_DWORD *)a1 + 45) = a8;
  *((_DWORD *)a1 + 46) = a9;
  *((_DWORD *)a1 + 47) = a6;
  *((_DWORD *)a1 + 48) = a7;
  return 0;
}

```

## disassembly

```asm
0x18001e2c8  push    rbx
0x18001e2ca  push    rbp
0x18001e2cb  push    rsi
0x18001e2cc  push    rdi
0x18001e2cd  push    r12
0x18001e2cf  push    r14
0x18001e2d1  push    r15
0x18001e2d3  sub     rsp, 60h
0x18001e2d7  mov     eax, [rcx+0A8h]
0x18001e2dd  mov     r12, r8
0x18001e2e0  mov     rdi, rdx
0x18001e2e3  mov     esi, [rsp+98h+arg_40]
0x18001e2ea  mov     rbx, rcx
0x18001e2ed  mov     ebp, [rsp+98h+arg_38]
0x18001e2f4  mov     r14d, [rsp+98h+arg_30]
0x18001e2fc  mov     r15d, [rsp+98h+arg_28]
0x18001e304  cmp     [rdx+10h], eax
0x18001e307  jnz     short loc_18001E365
0x18001e309  movzx   ecx, word ptr [rdx+0Eh]
0x18001e30d  mov     edx, [rbx+0ACh]
0x18001e313  cmp     ecx, edx
0x18001e315  jnz     short loc_18001E356
0x18001e317  mov     eax, [rbx+0B0h]
0x18001e31d  cmp     [rdi+8], eax
0x18001e320  jnz     short loc_18001E356
0x18001e322  cmp     ebp, [rbx+0B4h]
0x18001e328  jnz     short loc_18001E356
0x18001e32a  cmp     esi, [rbx+0B8h]
0x18001e330  jnz     short loc_18001E356
0x18001e332  cmp     r15d, [rbx+0BCh]
0x18001e339  jnz     short loc_18001E356
0x18001e33b  cmp     r14d, [rbx+0C0h]
0x18001e342  jnz     short loc_18001E356
0x18001e344  cmp     [rbx+60h], r8
0x18001e348  jnz     short loc_18001E356
0x18001e34a  mov     dword ptr [rbx+3Ch], 0
0x18001e351  jmp     loc_18001E3ED
0x18001e356  mov     eax, [rbx+0B0h]
0x18001e35c  cmp     [rdi+8], eax
0x18001e35f  jnz     short loc_18001E365
0x18001e361  cmp     ecx, edx
0x18001e363  jz      short loc_18001E374
0x18001e365  mov     rdx, rdi; struct tagBITMAPINFOHEADER *
0x18001e368  mov     rcx, rbx; struct CDeColorConvParams *
0x18001e36b  call    ?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z; g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)
0x18001e370  test    eax, eax
0x18001e372  jnz     short loc_18001E3EF
0x18001e374  cmp     ebp, [rdi+4]
0x18001e377  jz      short loc_18001E3A1
0x18001e379  cmp     dword ptr [rbx+34h], 0
0x18001e37d  jnz     short loc_18001E386
0x18001e37f  mov     eax, 0FFFFFF9Ch
0x18001e384  jmp     short loc_18001E3EF
0x18001e386  mov     [rsp+98h+var_60], esi; int
0x18001e38a  mov     rdx, rbx; struct CDeColorConvParams *
0x18001e38d  mov     [rsp+98h+var_70], r14d; int
0x18001e392  mov     rcx, rdi; struct tagBITMAPINFOHEADER *
0x18001e395  mov     [rsp+98h+var_78], r15d; int
0x18001e39a  call    ?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z; g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)
0x18001e39f  jmp     short loc_18001E3AC
0x18001e3a1  mov     edx, r9d; int
0x18001e3a4  mov     rcx, rbx; struct CDeColorConvParams *
0x18001e3a7  call    ?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJKKK@Z; g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,ulong,ulong,ulong)
0x18001e3ac  mov     dword ptr [rbx+3Ch], 1
0x18001e3b3  mov     [rbx+60h], r12
0x18001e3b7  mov     eax, [rdi+8]
0x18001e3ba  mov     [rbx+0B0h], eax
0x18001e3c0  mov     eax, [rdi+10h]
0x18001e3c3  mov     [rbx+0A8h], eax
0x18001e3c9  movzx   eax, word ptr [rdi+0Eh]
0x18001e3cd  mov     [rbx+0ACh], eax
0x18001e3d3  mov     [rbx+0B4h], ebp
0x18001e3d9  mov     [rbx+0B8h], esi
0x18001e3df  mov     [rbx+0BCh], r15d
0x18001e3e6  mov     [rbx+0C0h], r14d
0x18001e3ed  xor     eax, eax
0x18001e3ef  add     rsp, 60h
0x18001e3f3  pop     r15
0x18001e3f5  pop     r14
0x18001e3f7  pop     r12
0x18001e3f9  pop     rdi
0x18001e3fa  pop     rsi
0x18001e3fb  pop     rbp
0x18001e3fc  pop     rbx
0x18001e3fd  retn
```
