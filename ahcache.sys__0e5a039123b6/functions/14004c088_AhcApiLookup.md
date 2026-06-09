# AhcApiLookup

- ea: `0x14004c088`
- end: `0x14004c2da`
- name: `AhcApiLookup`
- size: `594`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400497bc`

## callees

- `0x140003418`
- `0x14000436d`
- `0x140007e40`
- `0x14003e364`
- `0x14004c088`
- `0x14004c2e0`
- `0x14004c3a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004c232`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c232`
- `ntoskrnl!ZwClose` at `0x14004c280`
- `ntoskrnl!ZwClose` at `0x14004c280`

## string_xrefs

- `0x14004c2c8`: `Lookup failed to copy buffer back to params [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiLookup(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void *a5, unsigned int a6, void *a7)
{
  int Key; // eax
  HANDLE v12; // rsi
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  int v17; // eax
  HANDLE v18; // [rsp+20h] [rbp-81h]
  HANDLE v19; // [rsp+20h] [rbp-81h]
  HANDLE Handle; // [rsp+70h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v22; // [rsp+88h] [rbp-19h] BYREF
  size_t Size[2]; // [rsp+90h] [rbp-11h]
  __int64 v24; // [rsp+A0h] [rbp-1h]
  PVOID Src[2]; // [rsp+A8h] [rbp+7h]
  int v26; // [rsp+100h] [rbp+5Fh] BYREF

  v22 = 0;
  v24 = 4096;
  v26 = 0;
  Handle = 0;
  v18 = *(HANDLE *)(a3 + 24);
  *(_OWORD *)Size = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)P = 0;
  Key = AhcpApiGetKey((int)P, (int)&Handle, (int)a3 + 8, (int)a3 + 48, v18);
  v12 = Handle;
  v13 = Key;
  if ( Key < 0 )
  {
    v14 = "Failed to get key [%x]";
    v15 = 270;
LABEL_8:
    LODWORD(v19) = Key;
    AslLogCallPrintf(1, "AhcApiLookup", v15, v14, v19);
    goto LABEL_9;
  }
  Key = AhcCacheLookup(
          a1,
          &v22,
          a2,
          a4,
          P,
          Handle,
          *(_WORD *)(a3 + 40),
          *(_QWORD *)(a3 + 64),
          *(_DWORD *)(a3 + 72),
          *(_QWORD *)(a3 + 88),
          *(unsigned __int16 *)(a3 + 80),
          *(_DWORD *)(a3 + 4),
          *(_QWORD *)(a3 + 16) != 0,
          *(_DWORD *)a3);
  v13 = Key;
  if ( Key < 0 )
  {
    v14 = "Lookup failed [%x]";
    v15 = 293;
    goto LABEL_8;
  }
  if ( Size[0] )
  {
    if ( Size[0] <= a6 )
    {
      Key = AhcSafeCopyMemoryToUserMode(a5, Src[1], Size[0]);
      v13 = Key;
      if ( Key >= 0 )
      {
        v13 = 0;
        goto LABEL_9;
      }
      v14 = "Lookup failed to copy buffer back to params [%x]";
      v15 = 314;
      goto LABEL_8;
    }
    v13 = -1073741789;
    LODWORD(v19) = -1073741789;
    AslLogCallPrintf(1, "AhcApiLookup", 308, "Lookup failed because buffer was too small [%x]", v19);
  }
  else
  {
    v13 = -1073741275;
  }
LABEL_9:
  if ( v12 )
    ZwClose(v12);
  if ( P[1] )
  {
    memset(P[1], 66, WORD1(P[0]));
    if ( P[1] )
      ExFreePoolWithTag_0(P[1], 0x74705041u);
  }
  *(_OWORD *)P = 0;
  if ( (int)(v13 + 0x80000000) < 0 || v13 == -1073741789 )
  {
    v26 = Size[0];
    v17 = AhcSafeCopyMemoryToUserMode(a7, &v26, 4u);
    if ( v17 < 0 )
      v13 = v17;
  }
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x7274534Du);
  return v13;
}

```

## disassembly

```asm
0x14004c088  mov     [rsp-8+arg_0], rbx
0x14004c08d  mov     [rsp-8+arg_8], rsi
0x14004c092  push    rbp
0x14004c093  push    rdi
0x14004c094  push    r12
0x14004c096  push    r14
0x14004c098  push    r15
0x14004c09a  lea     rbp, [rsp-1Fh]
0x14004c09f  sub     rsp, 0C0h
0x14004c0a6  mov     rdi, r8
0x14004c0a9  mov     [rbp+3Fh+var_58], 0
0x14004c0b1  xorps   xmm0, xmm0
0x14004c0b4  mov     [rbp+3Fh+var_40], 1000h
0x14004c0bc  mov     r14, r9
0x14004c0bf  mov     [rbp+3Fh+arg_10], 0
0x14004c0c6  mov     r15, rdx
0x14004c0c9  mov     [rbp+3Fh+Handle], 0
0x14004c0d1  mov     rax, [rdi+18h]
0x14004c0d5  lea     r9, [r8+30h]; int
0x14004c0d9  mov     r12, rcx
0x14004c0dc  mov     [rsp+0E0h+var_C0], rax; Handle
0x14004c0e1  xorps   xmm1, xmm1
0x14004c0e4  lea     rdx, [rbp+3Fh+Handle]; int
0x14004c0e8  add     r8, 8; int
0x14004c0ec  lea     rcx, [rbp+3Fh+P]; int
0x14004c0f0  movdqu  xmmword ptr [rbp+3Fh+Size], xmm0
0x14004c0f5  movdqu  xmmword ptr [rbp+3Fh+Src], xmm1
0x14004c0fa  movups  xmmword ptr [rbp+3Fh+P], xmm0
0x14004c0fe  call    AhcpApiGetKey
0x14004c103  mov     rsi, [rbp+3Fh+Handle]
0x14004c107  mov     ebx, eax
0x14004c109  test    eax, eax
0x14004c10b  js      loc_14004C1B3
0x14004c111  mov     eax, [rdi]
0x14004c113  xor     ecx, ecx
0x14004c115  cmp     [rdi+10h], rcx
0x14004c119  mov     r9, r14
0x14004c11c  movzx   edx, word ptr [rdi+50h]
0x14004c120  mov     r8, r15
0x14004c123  mov     [rsp+0E0h+var_78], eax
0x14004c127  setnz   cl
0x14004c12a  mov     eax, [rdi+4]
0x14004c12d  mov     [rsp+0E0h+var_80], ecx
0x14004c131  mov     rcx, r12
0x14004c134  mov     [rsp+0E0h+var_88], eax
0x14004c138  mov     rax, [rdi+58h]
0x14004c13c  mov     [rsp+0E0h+var_90], edx
0x14004c140  lea     rdx, [rbp+3Fh+var_58]
0x14004c144  mov     [rsp+0E0h+var_98], rax
0x14004c149  mov     eax, [rdi+48h]
0x14004c14c  mov     [rsp+0E0h+var_A0], eax
0x14004c150  mov     rax, [rdi+40h]
0x14004c154  mov     [rsp+0E0h+var_A8], rax
0x14004c159  movzx   eax, word ptr [rdi+28h]
0x14004c15d  mov     [rsp+0E0h+var_B0], ax
0x14004c162  lea     rax, [rbp+3Fh+P]
0x14004c166  mov     [rsp+0E0h+var_B8], rsi
0x14004c16b  mov     [rsp+0E0h+var_C0], rax
0x14004c170  call    AhcCacheLookup
0x14004c175  mov     ebx, eax
0x14004c177  test    eax, eax
0x14004c179  js      loc_14004C2AC
0x14004c17f  mov     r8, [rbp+3Fh+Size]; Size
0x14004c183  test    r8, r8
0x14004c186  jz      loc_14004C2BE
0x14004c18c  mov     eax, [rbp+3Fh+arg_28]
0x14004c18f  cmp     r8, rax
0x14004c192  ja      loc_14004C291
0x14004c198  mov     rdx, [rbp+3Fh+Src+8]; Src
0x14004c19c  mov     rcx, [rbp+3Fh+arg_20]; void *
0x14004c1a0  call    AhcSafeCopyMemoryToUserMode
0x14004c1a5  mov     ebx, eax
0x14004c1a7  test    eax, eax
0x14004c1a9  js      loc_14004C2C8
0x14004c1af  xor     ebx, ebx
0x14004c1b1  jmp     short loc_14004C1D5
0x14004c1b3  lea     r9, aFailedToGetKey_0; "Failed to get key [%x]"
0x14004c1ba  mov     r8d, 10Eh
0x14004c1c0  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14004c1c4  lea     rdx, aAhcapilookup; "AhcApiLookup"
0x14004c1cb  mov     ecx, 1
0x14004c1d0  call    AslLogCallPrintf
0x14004c1d5  test    rsi, rsi
0x14004c1d8  jnz     loc_14004C27D
0x14004c1de  mov     rcx, [rbp+3Fh+P+8]; void *
0x14004c1e2  test    rcx, rcx
0x14004c1e5  jz      short loc_14004C209
0x14004c1e7  movzx   r8d, word ptr [rbp+3Fh+P+2]; Size
0x14004c1ec  mov     edx, 42h ; 'B'; Val
0x14004c1f1  call    memset
0x14004c1f6  mov     rcx, [rbp+3Fh+P+8]; P
0x14004c1fa  test    rcx, rcx
0x14004c1fd  jz      short loc_14004C209
0x14004c1ff  mov     edx, 74705041h; Tag
0x14004c204  call    ExFreePoolWithTag_0
0x14004c209  mov     ecx, 80000000h
0x14004c20e  xorps   xmm0, xmm0
0x14004c211  movups  xmmword ptr [rbp+3Fh+P], xmm0
0x14004c215  lea     eax, [rbx+rcx]
0x14004c218  test    ecx, eax
0x14004c21a  jnz     short loc_14004C25D
0x14004c21c  cmp     ebx, 0C0000023h
0x14004c222  jz      short loc_14004C25D
0x14004c224  mov     rcx, [rbp+3Fh+Src+8]; P
0x14004c228  test    rcx, rcx
0x14004c22b  jz      short loc_14004C23E
0x14004c22d  mov     edx, 7274534Dh; Tag
0x14004c232  call    cs:__imp_ExFreePoolWithTag
0x14004c239  nop     dword ptr [rax+rax+00h]
0x14004c23e  lea     r11, [rsp+0E0h+var_20]
0x14004c246  mov     eax, ebx
0x14004c248  mov     rbx, [r11+30h]
0x14004c24c  mov     rsi, [r11+38h]
0x14004c250  mov     rsp, r11
0x14004c253  pop     r15
0x14004c255  pop     r14
0x14004c257  pop     r12
0x14004c259  pop     rdi
0x14004c25a  pop     rbp
0x14004c25b  retn
0x14004c25d  mov     eax, dword ptr [rbp+3Fh+Size]
0x14004c260  lea     rdx, [rbp+3Fh+arg_10]; Src
0x14004c264  mov     rcx, [rbp+3Fh+arg_30]; void *
0x14004c268  mov     r8d, 4; Size
0x14004c26e  mov     [rbp+3Fh+arg_10], eax
0x14004c271  call    AhcSafeCopyMemoryToUserMode
0x14004c276  test    eax, eax
0x14004c278  cmovs   ebx, eax
0x14004c27b  jmp     short loc_14004C224
0x14004c27d  mov     rcx, rsi; Handle
0x14004c280  call    cs:__imp_ZwClose
0x14004c287  nop     dword ptr [rax+rax+00h]
0x14004c28c  jmp     loc_14004C1DE
0x14004c291  mov     ebx, 0C0000023h
0x14004c296  lea     r9, aLookupFailedBe; "Lookup failed because buffer was too sm"...
0x14004c29d  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14004c2a1  mov     r8d, 134h
0x14004c2a7  jmp     loc_14004C1C4
0x14004c2ac  lea     r9, aLookupFailedX; "Lookup failed [%x]"
0x14004c2b3  mov     r8d, 125h
0x14004c2b9  jmp     loc_14004C1C0
0x14004c2be  mov     ebx, 0C0000225h
0x14004c2c3  jmp     loc_14004C1D5
0x14004c2c8  lea     r9, aLookupFailedTo; "Lookup failed to copy buffer back to pa"...
0x14004c2cf  mov     r8d, 13Ah
0x14004c2d5  jmp     loc_14004C1C0
```
