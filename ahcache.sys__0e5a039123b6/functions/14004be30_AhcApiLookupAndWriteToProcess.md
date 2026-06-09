# AhcApiLookupAndWriteToProcess

- ea: `0x14004be30`
- end: `0x14004c082`
- name: `AhcApiLookupAndWriteToProcess`
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
- `0x14004be30`
- `0x14004c2e0`
- `0x14004c3a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004bfda`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bfda`
- `ntoskrnl!ZwClose` at `0x14004c028`
- `ntoskrnl!ZwClose` at `0x14004c028`

## string_xrefs

- `0x14004bf6c`: `AhcApiLookupAndWriteToProcess`
- `0x14004c070`: `Lookup failed to copy buffer back to params [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiLookupAndWriteToProcess(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6,
        void *a7)
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
    v15 = 386;
LABEL_8:
    LODWORD(v19) = Key;
    AslLogCallPrintf(1, "AhcApiLookupAndWriteToProcess", v15, v14, v19);
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
    v15 = 409;
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
      v15 = 430;
      goto LABEL_8;
    }
    v13 = -1073741789;
    LODWORD(v19) = -1073741789;
    AslLogCallPrintf(1, "AhcApiLookupAndWriteToProcess", 424, "Lookup failed because buffer was too small [%x]", v19);
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
0x14004be30  mov     [rsp-8+arg_0], rbx
0x14004be35  mov     [rsp-8+arg_8], rsi
0x14004be3a  push    rbp
0x14004be3b  push    rdi
0x14004be3c  push    r12
0x14004be3e  push    r14
0x14004be40  push    r15
0x14004be42  lea     rbp, [rsp-1Fh]
0x14004be47  sub     rsp, 0C0h
0x14004be4e  mov     rdi, r8
0x14004be51  mov     [rbp+3Fh+var_58], 0
0x14004be59  xorps   xmm0, xmm0
0x14004be5c  mov     [rbp+3Fh+var_40], 1000h
0x14004be64  mov     r14, r9
0x14004be67  mov     [rbp+3Fh+arg_10], 0
0x14004be6e  mov     r15, rdx
0x14004be71  mov     [rbp+3Fh+Handle], 0
0x14004be79  mov     rax, [rdi+18h]
0x14004be7d  lea     r9, [r8+30h]; int
0x14004be81  mov     r12, rcx
0x14004be84  mov     [rsp+0E0h+var_C0], rax; Handle
0x14004be89  xorps   xmm1, xmm1
0x14004be8c  lea     rdx, [rbp+3Fh+Handle]; int
0x14004be90  add     r8, 8; int
0x14004be94  lea     rcx, [rbp+3Fh+P]; int
0x14004be98  movdqu  xmmword ptr [rbp+3Fh+Size], xmm0
0x14004be9d  movdqu  xmmword ptr [rbp+3Fh+Src], xmm1
0x14004bea2  movups  xmmword ptr [rbp+3Fh+P], xmm0
0x14004bea6  call    AhcpApiGetKey
0x14004beab  mov     rsi, [rbp+3Fh+Handle]
0x14004beaf  mov     ebx, eax
0x14004beb1  test    eax, eax
0x14004beb3  js      loc_14004BF5B
0x14004beb9  mov     eax, [rdi]
0x14004bebb  xor     ecx, ecx
0x14004bebd  cmp     [rdi+10h], rcx
0x14004bec1  mov     r9, r14
0x14004bec4  movzx   edx, word ptr [rdi+50h]
0x14004bec8  mov     r8, r15
0x14004becb  mov     [rsp+0E0h+var_78], eax
0x14004becf  setnz   cl
0x14004bed2  mov     eax, [rdi+4]
0x14004bed5  mov     [rsp+0E0h+var_80], ecx
0x14004bed9  mov     rcx, r12
0x14004bedc  mov     [rsp+0E0h+var_88], eax
0x14004bee0  mov     rax, [rdi+58h]
0x14004bee4  mov     [rsp+0E0h+var_90], edx
0x14004bee8  lea     rdx, [rbp+3Fh+var_58]
0x14004beec  mov     [rsp+0E0h+var_98], rax
0x14004bef1  mov     eax, [rdi+48h]
0x14004bef4  mov     [rsp+0E0h+var_A0], eax
0x14004bef8  mov     rax, [rdi+40h]
0x14004befc  mov     [rsp+0E0h+var_A8], rax
0x14004bf01  movzx   eax, word ptr [rdi+28h]
0x14004bf05  mov     [rsp+0E0h+var_B0], ax
0x14004bf0a  lea     rax, [rbp+3Fh+P]
0x14004bf0e  mov     [rsp+0E0h+var_B8], rsi
0x14004bf13  mov     [rsp+0E0h+var_C0], rax
0x14004bf18  call    AhcCacheLookup
0x14004bf1d  mov     ebx, eax
0x14004bf1f  test    eax, eax
0x14004bf21  js      loc_14004C054
0x14004bf27  mov     r8, [rbp+3Fh+Size]; Size
0x14004bf2b  test    r8, r8
0x14004bf2e  jz      loc_14004C066
0x14004bf34  mov     eax, [rbp+3Fh+arg_28]
0x14004bf37  cmp     r8, rax
0x14004bf3a  ja      loc_14004C039
0x14004bf40  mov     rdx, [rbp+3Fh+Src+8]; Src
0x14004bf44  mov     rcx, [rbp+3Fh+arg_20]; void *
0x14004bf48  call    AhcSafeCopyMemoryToUserMode
0x14004bf4d  mov     ebx, eax
0x14004bf4f  test    eax, eax
0x14004bf51  js      loc_14004C070
0x14004bf57  xor     ebx, ebx
0x14004bf59  jmp     short loc_14004BF7D
0x14004bf5b  lea     r9, aFailedToGetKey_0; "Failed to get key [%x]"
0x14004bf62  mov     r8d, 182h
0x14004bf68  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14004bf6c  lea     rdx, aAhcapilookupan; "AhcApiLookupAndWriteToProcess"
0x14004bf73  mov     ecx, 1
0x14004bf78  call    AslLogCallPrintf
0x14004bf7d  test    rsi, rsi
0x14004bf80  jnz     loc_14004C025
0x14004bf86  mov     rcx, [rbp+3Fh+P+8]; void *
0x14004bf8a  test    rcx, rcx
0x14004bf8d  jz      short loc_14004BFB1
0x14004bf8f  movzx   r8d, word ptr [rbp+3Fh+P+2]; Size
0x14004bf94  mov     edx, 42h ; 'B'; Val
0x14004bf99  call    memset
0x14004bf9e  mov     rcx, [rbp+3Fh+P+8]; P
0x14004bfa2  test    rcx, rcx
0x14004bfa5  jz      short loc_14004BFB1
0x14004bfa7  mov     edx, 74705041h; Tag
0x14004bfac  call    ExFreePoolWithTag_0
0x14004bfb1  mov     ecx, 80000000h
0x14004bfb6  xorps   xmm0, xmm0
0x14004bfb9  movups  xmmword ptr [rbp+3Fh+P], xmm0
0x14004bfbd  lea     eax, [rbx+rcx]
0x14004bfc0  test    ecx, eax
0x14004bfc2  jnz     short loc_14004C005
0x14004bfc4  cmp     ebx, 0C0000023h
0x14004bfca  jz      short loc_14004C005
0x14004bfcc  mov     rcx, [rbp+3Fh+Src+8]; P
0x14004bfd0  test    rcx, rcx
0x14004bfd3  jz      short loc_14004BFE6
0x14004bfd5  mov     edx, 7274534Dh; Tag
0x14004bfda  call    cs:__imp_ExFreePoolWithTag
0x14004bfe1  nop     dword ptr [rax+rax+00h]
0x14004bfe6  lea     r11, [rsp+0E0h+var_20]
0x14004bfee  mov     eax, ebx
0x14004bff0  mov     rbx, [r11+30h]
0x14004bff4  mov     rsi, [r11+38h]
0x14004bff8  mov     rsp, r11
0x14004bffb  pop     r15
0x14004bffd  pop     r14
0x14004bfff  pop     r12
0x14004c001  pop     rdi
0x14004c002  pop     rbp
0x14004c003  retn
0x14004c005  mov     eax, dword ptr [rbp+3Fh+Size]
0x14004c008  lea     rdx, [rbp+3Fh+arg_10]; Src
0x14004c00c  mov     rcx, [rbp+3Fh+arg_30]; void *
0x14004c010  mov     r8d, 4; Size
0x14004c016  mov     [rbp+3Fh+arg_10], eax
0x14004c019  call    AhcSafeCopyMemoryToUserMode
0x14004c01e  test    eax, eax
0x14004c020  cmovs   ebx, eax
0x14004c023  jmp     short loc_14004BFCC
0x14004c025  mov     rcx, rsi; Handle
0x14004c028  call    cs:__imp_ZwClose
0x14004c02f  nop     dword ptr [rax+rax+00h]
0x14004c034  jmp     loc_14004BF86
0x14004c039  mov     ebx, 0C0000023h
0x14004c03e  lea     r9, aLookupFailedBe; "Lookup failed because buffer was too sm"...
0x14004c045  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14004c049  mov     r8d, 1A8h
0x14004c04f  jmp     loc_14004BF6C
0x14004c054  lea     r9, aLookupFailedX; "Lookup failed [%x]"
0x14004c05b  mov     r8d, 199h
0x14004c061  jmp     loc_14004BF68
0x14004c066  mov     ebx, 0C0000225h
0x14004c06b  jmp     loc_14004BF7D
0x14004c070  lea     r9, aLookupFailedTo; "Lookup failed to copy buffer back to pa"...
0x14004c077  mov     r8d, 1AEh
0x14004c07d  jmp     loc_14004BF68
```
