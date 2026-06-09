# g_ConfigureDstBMP(CDeColorConvParams *,tagBITMAPINFOHEADER *,void *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x18001e208`
- end: `0x18001e33e`
- name: `?g_ConfigureDstBMP@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@PEAXJJJJJJKKK@Z`
- size: `310`
- prototype: `__int64 __usercall@<rax>(struct CDeColorConvParams *@<rcx>, struct tagBITMAPINFOHEADER *@<rdx>, void *@<r8>, int@<r9d>, int, int, int, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a6bc`

## callees

- `0x18001de8c`
- `0x18001e110`
- `0x18001e208`
- `0x18001e344`

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
0x18001e208  push    rbx
0x18001e20a  push    rbp
0x18001e20b  push    rsi
0x18001e20c  push    rdi
0x18001e20d  push    r12
0x18001e20f  push    r14
0x18001e211  push    r15
0x18001e213  sub     rsp, 60h
0x18001e217  mov     eax, [rcx+0A8h]
0x18001e21d  mov     r12, r8
0x18001e220  mov     rdi, rdx
0x18001e223  mov     esi, [rsp+98h+arg_40]
0x18001e22a  mov     rbx, rcx
0x18001e22d  mov     ebp, [rsp+98h+arg_38]
0x18001e234  mov     r14d, [rsp+98h+arg_30]
0x18001e23c  mov     r15d, [rsp+98h+arg_28]
0x18001e244  cmp     [rdx+10h], eax
0x18001e247  jnz     short loc_18001E2A5
0x18001e249  movzx   ecx, word ptr [rdx+0Eh]
0x18001e24d  mov     edx, [rbx+0ACh]
0x18001e253  cmp     ecx, edx
0x18001e255  jnz     short loc_18001E296
0x18001e257  mov     eax, [rbx+0B0h]
0x18001e25d  cmp     [rdi+8], eax
0x18001e260  jnz     short loc_18001E296
0x18001e262  cmp     ebp, [rbx+0B4h]
0x18001e268  jnz     short loc_18001E296
0x18001e26a  cmp     esi, [rbx+0B8h]
0x18001e270  jnz     short loc_18001E296
0x18001e272  cmp     r15d, [rbx+0BCh]
0x18001e279  jnz     short loc_18001E296
0x18001e27b  cmp     r14d, [rbx+0C0h]
0x18001e282  jnz     short loc_18001E296
0x18001e284  cmp     [rbx+60h], r8
0x18001e288  jnz     short loc_18001E296
0x18001e28a  mov     dword ptr [rbx+3Ch], 0
0x18001e291  jmp     loc_18001E32D
0x18001e296  mov     eax, [rbx+0B0h]
0x18001e29c  cmp     [rdi+8], eax
0x18001e29f  jnz     short loc_18001E2A5
0x18001e2a1  cmp     ecx, edx
0x18001e2a3  jz      short loc_18001E2B4
0x18001e2a5  mov     rdx, rdi; struct tagBITMAPINFOHEADER *
0x18001e2a8  mov     rcx, rbx; struct CDeColorConvParams *
0x18001e2ab  call    ?g_ConfigureDstBMPProperty@@YAJPEAVCDeColorConvParams@@PEAUtagBITMAPINFOHEADER@@@Z; g_ConfigureDstBMPProperty(CDeColorConvParams *,tagBITMAPINFOHEADER *)
0x18001e2b0  test    eax, eax
0x18001e2b2  jnz     short loc_18001E32F
0x18001e2b4  cmp     ebp, [rdi+4]
0x18001e2b7  jz      short loc_18001E2E1
0x18001e2b9  cmp     dword ptr [rbx+34h], 0
0x18001e2bd  jnz     short loc_18001E2C6
0x18001e2bf  mov     eax, 0FFFFFF9Ch
0x18001e2c4  jmp     short loc_18001E32F
0x18001e2c6  mov     [rsp+98h+var_60], esi; int
0x18001e2ca  mov     rdx, rbx; struct CDeColorConvParams *
0x18001e2cd  mov     [rsp+98h+var_70], r14d; int
0x18001e2d2  mov     rcx, rdi; struct tagBITMAPINFOHEADER *
0x18001e2d5  mov     [rsp+98h+var_78], r15d; int
0x18001e2da  call    ?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z; g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)
0x18001e2df  jmp     short loc_18001E2EC
0x18001e2e1  mov     edx, r9d; int
0x18001e2e4  mov     rcx, rbx; struct CDeColorConvParams *
0x18001e2e7  call    ?g_ConfigureBMPSizeAndPointersInfo@@YAXPEAVCDeColorConvParams@@JJKKK@Z; g_ConfigureBMPSizeAndPointersInfo(CDeColorConvParams *,long,long,ulong,ulong,ulong)
0x18001e2ec  mov     dword ptr [rbx+3Ch], 1
0x18001e2f3  mov     [rbx+60h], r12
0x18001e2f7  mov     eax, [rdi+8]
0x18001e2fa  mov     [rbx+0B0h], eax
0x18001e300  mov     eax, [rdi+10h]
0x18001e303  mov     [rbx+0A8h], eax
0x18001e309  movzx   eax, word ptr [rdi+0Eh]
0x18001e30d  mov     [rbx+0ACh], eax
0x18001e313  mov     [rbx+0B4h], ebp
0x18001e319  mov     [rbx+0B8h], esi
0x18001e31f  mov     [rbx+0BCh], r15d
0x18001e326  mov     [rbx+0C0h], r14d
0x18001e32d  xor     eax, eax
0x18001e32f  add     rsp, 60h
0x18001e333  pop     r15
0x18001e335  pop     r14
0x18001e337  pop     r12
0x18001e339  pop     rdi
0x18001e33a  pop     rsi
0x18001e33b  pop     rbp
0x18001e33c  pop     rbx
0x18001e33d  retn
```
