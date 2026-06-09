# AhcpCacheBuildEnvironmentSafe

- ea: `0x140046f60`
- end: `0x140047662`
- name: `AhcpCacheBuildEnvironmentSafe`
- size: `1794`
- prototype: `__int64 __fastcall(__int64, _QWORD *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004c3a0`

## callees

- `0x1400014b4`
- `0x14000436d`
- `0x140004553`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x140046908`
- `0x140046f60`
- `0x140047668`
- `0x1400479a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004713e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047158`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047516`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004757a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004713e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047158`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047516`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004757a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400471cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004741b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400471cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004741b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400471f7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140047447`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400474d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004752d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400471f7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140047447`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400474d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004752d`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140047271`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140047271`

## string_xrefs

- `0x1400470c1`: `AhcpCacheBuildEnvironmentSafe`
- `0x140047199`: `AhcpCacheBuildEnvironmentSafe`
- `0x14004739a`: `AhcpCacheBuildEnvironmentSafe`
- `0x1400473c7`: `AhcpCacheBuildEnvironmentSafe`
- `0x1400473e8`: `AhcpCacheBuildEnvironmentSafe`
- `0x140047490`: `AhcpCacheBuildEnvironmentSafe`
- `0x1400474b1`: `AhcpCacheBuildEnvironmentSafe`
- `0x1400475fe`: `AhcpCacheBuildEnvironmentSafe`
- `0x140047631`: `AhcpCacheBuildEnvironmentSafe`
- `0x140047620`: `Failed to read passed in environment [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheBuildEnvironmentSafe(__int64 a1, _QWORD *a2, void *a3, unsigned int a4)
{
  int v6; // eax
  void *v7; // r9
  PVOID v8; // r14
  int v9; // ecx
  char *v10; // rdi
  size_t v11; // r15
  PVOID Pool2_0; // rbx
  size_t v13; // rdi
  void *v14; // rax
  PVOID v15; // rax
  int v16; // edi
  int v18; // eax
  SIZE_T v19; // rbx
  KIRQL CurrentIrql; // al
  POOL_TYPE v21; // ecx
  PVOID PoolWithTag; // rax
  int Environment; // eax
  unsigned int v24; // r15d
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rax
  char *v27; // r13
  char *v28; // rdi
  size_t v29; // rax
  unsigned __int64 v30; // rcx
  KIRQL v31; // al
  POOL_TYPE v32; // ecx
  PVOID v33; // rax
  PVOID v34; // rax
  size_t v35; // r8
  PVOID v36; // rax
  SIZE_T v37; // r8
  PVOID v38; // [rsp+38h] [rbp-79h] BYREF
  __int64 v39; // [rsp+40h] [rbp-71h] BYREF
  size_t Size[2]; // [rsp+48h] [rbp-69h]
  __int64 v41; // [rsp+58h] [rbp-59h]
  void *Src[2]; // [rsp+60h] [rbp-51h]
  void *v43[2]; // [rsp+70h] [rbp-41h]
  PVOID P[2]; // [rsp+80h] [rbp-31h]
  __int64 v45; // [rsp+90h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-19h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-9h] BYREF
  __int128 v48; // [rsp+B0h] [rbp-1h]
  __int64 v49; // [rsp+C0h] [rbp+Fh]
  __int128 v50; // [rsp+C8h] [rbp+17h]
  SIZE_T NumberOfBytes; // [rsp+118h] [rbp+67h] BYREF
  _QWORD *v52; // [rsp+120h] [rbp+6Fh]
  void *v53; // [rsp+128h] [rbp+77h]

  v53 = a3;
  v52 = a2;
  v6 = *(_DWORD *)(a1 + 672);
  v7 = a3;
  v39 = 0;
  v41 = 4096;
  v47 = 0;
  v49 = 4096;
  v45 = 0;
  v38 = 0;
  *(_OWORD *)Size = 0;
  *(_OWORD *)Src = 0;
  v48 = 0;
  v50 = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v43 = 0;
  if ( v6 < 2 )
  {
    v18 = AslEnvBuildBasic(&v38, &v45, a3, a3);
    v16 = v18;
    if ( v18 < 0 )
    {
      AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2188, "Failed to build environment [%x]", v18);
      Pool2_0 = P[1];
      v8 = v43[1];
      goto LABEL_16;
    }
    v8 = v38;
    LOWORD(v9) = 2 * v45;
    WORD1(v43[0]) = 2 * v45;
    LOWORD(v43[0]) = 2 * v45;
    v43[1] = v38;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 672), 1, 0) )
    {
      *(_OWORD *)(a1 + 680) = *(_OWORD *)v43;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 672));
    }
    v7 = v53;
  }
  else
  {
    v8 = *(PVOID *)(a1 + 688);
    v9 = *(_DWORD *)(a1 + 680);
  }
  if ( (unsigned __int16)v9 < 2u )
  {
    v16 = -1073741595;
    AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2206, "Bad environment [%x]", -1073741595);
    Pool2_0 = P[1];
    goto LABEL_16;
  }
  v10 = (char *)((unsigned __int16)v9 - 2LL);
  if ( (unsigned __int16)v9 == 2 )
    goto LABEL_10;
  v11 = Size[0];
  if ( v10 + 4095 < v10 )
    goto LABEL_14;
  v19 = (unsigned __int64)(v10 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  CurrentIrql = KeGetCurrentIrql();
  v21 = 512;
  if ( !Src[1] )
  {
    if ( CurrentIrql != 2 )
      v21 = PagedPool;
    PoolWithTag = ExAllocatePoolWithTag(v21, v19, 0x7274534Du);
    NumberOfBytes = (SIZE_T)PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v19);
      goto LABEL_34;
    }
LABEL_84:
    v16 = -1073741801;
    goto LABEL_15;
  }
  if ( CurrentIrql != 2 )
    v21 = PagedPool;
  v34 = ExAllocatePoolWithTag(v21, v19, 0x7274534Du);
  NumberOfBytes = (SIZE_T)v34;
  if ( !v34 )
    goto LABEL_84;
  memset(v34, 0, v19);
  v35 = v11;
  if ( v11 >= v19 )
    v35 = (unsigned __int64)(v10 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  memmove((void *)NumberOfBytes, Src[1], v35);
  ExFreePoolWithTag(Src[1], 0x7274534Du);
LABEL_34:
  Src[1] = (void *)NumberOfBytes;
  Size[1] = (unsigned __int64)(v10 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  memmove((char *)Src[0] + (unsigned __int64)Src[1], v8, (size_t)v10);
  if ( v10 < Src[0] )
  {
LABEL_14:
    v16 = -1073741675;
LABEL_15:
    AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2217, "Out of memory");
    Pool2_0 = P[1];
    goto LABEL_16;
  }
  v7 = v53;
  Src[0] = v10;
  if ( v11 <= (unsigned __int64)v10 )
    v11 = (size_t)v10;
  Size[0] = v11;
LABEL_10:
  if ( a4 )
  {
    Environment = AhcProbeAndReadEnvironment(v7, a4, (RtlMemoryStream *)&v47);
    v16 = Environment;
    if ( Environment < 0 )
    {
      AslLogCallPrintf(
        1,
        "AhcpCacheBuildEnvironmentSafe",
        2229,
        "Failed to read passed in environment [%x]",
        Environment);
      Pool2_0 = P[1];
    }
    else
    {
      v24 = 0;
      Pool2_0 = P[1];
      while ( 1 )
      {
        if ( v24 >= 3 )
          goto LABEL_12;
        RtlInitUnicodeStringEx(&DestinationString, (&off_14000A520)[2 * v24]);
        if ( Pool2_0 )
          ExFreePoolWithTag_0(Pool2_0, 0x74705041u);
        v25 = (unsigned __int16)(2 * *((_WORD *)&off_14000A520 + 8 * v24 + 4));
        Pool2_0 = (PVOID)ExAllocatePool2_0(256, v25, 1953517633);
        if ( !Pool2_0 )
          break;
        NumberOfBytes = 0;
        if ( (int)AslEnvVarQuery(
                    *((_QWORD *)&v50 + 1),
                    DestinationString.Buffer,
                    (unsigned __int64)DestinationString.Length >> 1,
                    Pool2_0,
                    v25 >> 1,
                    &NumberOfBytes) >= 0 )
        {
          v16 = RtlMemoryStream::WriteString((RtlMemoryStream *)&v39, (&off_14000A520)[2 * v24], L"=");
          if ( v16 < 0 )
          {
            AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2256, "Out of memory");
            goto LABEL_16;
          }
          v26 = (unsigned __int16)(2 * NumberOfBytes);
          P[0] = (PVOID)v26;
          if ( 2 * (_WORD)NumberOfBytes )
          {
            v27 = (char *)Src[0];
            v28 = (char *)Src[0] + v26;
            if ( (char *)Src[0] + v26 < Src[0] )
            {
              v16 = -1073741811;
LABEL_55:
              AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2262, "Out of memory");
              goto LABEL_16;
            }
            if ( (unsigned __int64)v28 > Size[1] )
            {
              v30 = (unsigned __int64)&v28[v41 - 1];
              if ( v30 < (unsigned __int64)v28 )
              {
LABEL_54:
                v16 = -1073741675;
                goto LABEL_55;
              }
              NumberOfBytes = v30 & ~(v41 - 1);
              v31 = KeGetCurrentIrql();
              v32 = 512;
              if ( Src[1] )
              {
                if ( v31 != 2 )
                  v32 = PagedPool;
                v36 = ExAllocatePoolWithTag(v32, NumberOfBytes, 0x7274534Du);
                v43[0] = v36;
                if ( !v36 )
                {
LABEL_86:
                  v16 = -1073741801;
                  goto LABEL_55;
                }
                memset(v36, 0, NumberOfBytes);
                v37 = NumberOfBytes;
                if ( Size[0] < NumberOfBytes )
                  v37 = Size[0];
                memmove(v43[0], Src[1], v37);
                ExFreePoolWithTag(Src[1], 0x7274534Du);
              }
              else
              {
                if ( v31 != 2 )
                  v32 = PagedPool;
                v33 = ExAllocatePoolWithTag(v32, NumberOfBytes, 0x7274534Du);
                v43[0] = v33;
                if ( !v33 )
                  goto LABEL_86;
                memset(v33, 0, NumberOfBytes);
              }
              Src[1] = v43[0];
              Size[1] = NumberOfBytes;
            }
            memmove(&v27[(unsigned __int64)Src[1]], Pool2_0, (size_t)P[0]);
            if ( v28 < v27 )
              goto LABEL_54;
            v29 = Size[0];
            Src[0] = v28;
            if ( Size[0] <= (unsigned __int64)v28 )
              v29 = (size_t)v28;
            Size[0] = v29;
          }
          v16 = RtlMemoryStream::WriteString((RtlMemoryStream *)&v39, &pszSrc, &dword_14000C47C);
          if ( v16 < 0 )
          {
            AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2268, "Out of memory");
            goto LABEL_16;
          }
        }
        ++v24;
      }
      v16 = -1073741801;
      AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2245, "Out of memory");
    }
  }
  else
  {
    Pool2_0 = P[1];
LABEL_12:
    v13 = Size[0];
    v14 = (void *)ExAllocatePool2_0(256, Size[0] + 2, 1953517633);
    v38 = v14;
    if ( v14 )
    {
      memmove(v14, Src[1], v13);
      v15 = v38;
      v16 = 0;
      v38 = 0;
      *v52 = v15;
    }
    else
    {
      v16 = -1073741801;
      AslLogCallPrintf(1, "AhcpCacheBuildEnvironmentSafe", 2281, "Out of memory");
    }
  }
LABEL_16:
  if ( v8 != *(PVOID *)(a1 + 688) && v8 )
    ExFreePoolWithTag_0(v8, 0x74705041u);
  if ( v38 )
    ExFreePoolWithTag_0(v38, 0x74705041u);
  if ( Pool2_0 )
    ExFreePoolWithTag_0(Pool2_0, 0x74705041u);
  if ( *((_QWORD *)&v50 + 1) )
    ExFreePoolWithTag(*((PVOID *)&v50 + 1), 0x7274534Du);
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x7274534Du);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140046f60  mov     rax, rsp
0x140046f63  mov     [rax+18h], r8
0x140046f67  mov     [rax+10h], rdx
0x140046f6b  push    rbp
0x140046f6c  push    rdi
0x140046f6d  lea     rbp, [rax-5Fh]
0x140046f71  sub     rsp, 0F8h
0x140046f78  mov     [rax+20h], rbx
0x140046f7c  xorps   xmm0, xmm0
0x140046f7f  mov     [rax-18h], rsi
0x140046f83  xor     ebx, ebx
0x140046f85  mov     [rax-20h], r12
0x140046f89  xorps   xmm1, xmm1
0x140046f8c  mov     [rax-28h], r13
0x140046f90  mov     rsi, rcx
0x140046f93  mov     [rax-30h], r14
0x140046f97  mov     r13d, r9d
0x140046f9a  mov     eax, [rcx+2A0h]
0x140046fa0  mov     r9, r8
0x140046fa3  mov     [rbp+57h+var_C8], rbx
0x140046fa7  mov     r12d, 1
0x140046fad  mov     [rbp+57h+var_B0], 1000h
0x140046fb5  mov     [rbp+57h+var_60], rbx
0x140046fb9  mov     [rbp+57h+var_48], 1000h
0x140046fc1  mov     [rbp+57h+var_78], rbx
0x140046fc5  mov     [rbp+57h+var_D0], rbx
0x140046fc9  movdqu  xmmword ptr [rbp+57h+Size], xmm0
0x140046fce  movdqu  xmmword ptr [rbp+57h+Src], xmm1
0x140046fd3  movdqu  [rbp+57h+var_58], xmm0
0x140046fd8  movdqu  xmmword ptr [rbp+17h], xmm1
0x140046fdd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140046fe1  movups  xmmword ptr [rbp+57h+P], xmm0
0x140046fe5  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x140046fe9  cmp     eax, 2
0x140046fec  jl      loc_140047171
0x140046ff2  mov     r14, [rcx+2B0h]
0x140046ff9  mov     edx, ebx
0x140046ffb  mov     ecx, [rcx+2A8h]
0x140047001  cmp     cx, 2
0x140047005  jb      loc_1400475E8
0x14004700b  movzx   edi, cx
0x14004700e  mov     [rsp+100h+var_30], r15
0x140047016  add     rdi, 0FFFFFFFFFFFFFFFEh
0x14004701a  jz      short loc_140047057
0x14004701c  mov     r15, [rbp+57h+Size]
0x140047020  cmp     rdi, rdx
0x140047023  ja      loc_1400471B5
0x140047029  mov     rcx, [rbp+57h+Src+8]
0x14004702d  mov     r8, rdi; Size
0x140047030  add     rcx, [rbp+57h+Src]; void *
0x140047034  mov     rdx, r14; Src
0x140047037  call    memmove
0x14004703c  cmp     rdi, [rbp+57h+Src]
0x140047040  jb      short loc_1400470AF
0x140047042  mov     r9, [rbp+57h+arg_10]
0x140047046  cmp     r15, rdi
0x140047049  mov     [rbp+57h+Src], rdi
0x14004704d  cmovbe  r15, rdi
0x140047051  xor     ebx, ebx
0x140047053  mov     [rbp+57h+Size], r15
0x140047057  test    r13d, r13d
0x14004705a  jnz     loc_14004722E
0x140047060  mov     rbx, [rbp+57h+P+8]
0x140047064  mov     rdi, [rbp+57h+Size]
0x140047068  mov     ecx, 100h
0x14004706d  mov     r8d, 74705041h
0x140047073  lea     rdx, [rdi+2]
0x140047077  call    ExAllocatePool2_0
0x14004707c  mov     [rbp+57h+var_D0], rax
0x140047080  test    rax, rax
0x140047083  jz      loc_1400473DB
0x140047089  mov     rdx, [rbp+57h+Src+8]; Src
0x14004708d  mov     r8, rdi; Size
0x140047090  mov     rcx, rax; void *
0x140047093  call    memmove
0x140047098  mov     rax, [rbp+57h+var_D0]
0x14004709c  xor     edi, edi
0x14004709e  mov     rcx, [rbp+57h+arg_8]
0x1400470a2  mov     [rbp+57h+var_D0], 0
0x1400470aa  mov     [rcx], rax
0x1400470ad  jmp     short loc_1400470D4
0x1400470af  mov     edi, 0C0000095h
0x1400470b4  lea     r9, aOutOfMemory; "Out of memory"
0x1400470bb  mov     r8d, 8A9h
0x1400470c1  lea     rdx, aAhcpcachebuild_0; "AhcpCacheBuildEnvironmentSafe"
0x1400470c8  mov     ecx, r12d
0x1400470cb  call    AslLogCallPrintf
0x1400470d0  mov     rbx, [rbp+57h+P+8]
0x1400470d4  mov     r15, [rsp+100h+var_30]
0x1400470dc  cmp     r14, [rsi+2B0h]
0x1400470e3  mov     rsi, [rsp+0F0h]
0x1400470eb  mov     r13, [rsp+100h+var_20]
0x1400470f3  mov     r12, [rsp+100h+var_18]
0x1400470fb  jnz     loc_14004758B
0x140047101  mov     rcx, [rbp+57h+var_D0]; P
0x140047105  mov     r14, [rsp+100h+var_28]
0x14004710d  test    rcx, rcx
0x140047110  jnz     loc_140047653
0x140047116  test    rbx, rbx
0x140047119  jz      short loc_140047128
0x14004711b  mov     edx, 74705041h; Tag
0x140047120  mov     rcx, rbx; P
0x140047123  call    ExFreePoolWithTag_0
0x140047128  mov     rcx, [rbp+57h+var_38]; P
0x14004712c  mov     rbx, [rsp+100h+arg_18]
0x140047134  test    rcx, rcx
0x140047137  jz      short loc_14004714A
0x140047139  mov     edx, 7274534Dh; Tag
0x14004713e  call    cs:__imp_ExFreePoolWithTag
0x140047145  nop     dword ptr [rax+rax+00h]
0x14004714a  mov     rcx, [rbp+57h+Src+8]; P
0x14004714e  test    rcx, rcx
0x140047151  jz      short loc_140047164
0x140047153  mov     edx, 7274534Dh; Tag
0x140047158  call    cs:__imp_ExFreePoolWithTag
0x14004715f  nop     dword ptr [rax+rax+00h]
0x140047164  mov     eax, edi
0x140047166  add     rsp, 0F8h
0x14004716d  pop     rdi
0x14004716e  pop     rbp
0x14004716f  retn
0x140047171  lea     rdx, [rbp+57h+var_78]
0x140047175  lea     rcx, [rbp+57h+var_D0]
0x140047179  call    AslEnvBuildBasic
0x14004717e  mov     edi, eax
0x140047180  test    eax, eax
0x140047182  jns     loc_1400475A6
0x140047188  lea     r9, aFailedToBuildE; "Failed to build environment [%x]"
0x14004718f  mov     dword ptr [rsp+100h+var_E0], eax
0x140047193  mov     r8d, 88Ch
0x140047199  lea     rdx, aAhcpcachebuild_0; "AhcpCacheBuildEnvironmentSafe"
0x1400471a0  mov     ecx, r12d
0x1400471a3  call    AslLogCallPrintf
0x1400471a8  mov     rbx, [rbp+57h+P+8]
0x1400471ac  mov     r14, [rbp+57h+var_98+8]
0x1400471b0  jmp     loc_1400470DC
0x1400471b5  lea     rbx, [rdi+0FFFh]
0x1400471bc  cmp     rbx, rdi
0x1400471bf  jb      loc_1400470AF
0x1400471c5  and     rbx, 0FFFFFFFFFFFFF000h
0x1400471cc  call    cs:__imp_KeGetCurrentIrql
0x1400471d3  nop     dword ptr [rax+rax+00h]
0x1400471d8  cmp     [rbp+57h+Src+8], 0
0x1400471dd  mov     ecx, 200h
0x1400471e2  mov     r8d, 7274534Dh; Tag
0x1400471e8  mov     rdx, rbx; NumberOfBytes
0x1400471eb  jnz     loc_1400474CA
0x1400471f1  cmp     al, 2
0x1400471f3  cmovnz  ecx, r12d; PoolType
0x1400471f7  call    cs:__imp_ExAllocatePoolWithTag
0x1400471fe  nop     dword ptr [rax+rax+00h]
0x140047203  mov     [rbp+57h+NumberOfBytes], rax
0x140047207  test    rax, rax
0x14004720a  jz      loc_140047616
0x140047210  mov     r8, rbx; Size
0x140047213  xor     edx, edx; Val
0x140047215  mov     rcx, rax; void *
0x140047218  call    memset
0x14004721d  mov     rax, [rbp+57h+NumberOfBytes]
0x140047221  mov     [rbp+57h+Src+8], rax
0x140047225  mov     [rbp+57h+Size+8], rbx
0x140047229  jmp     loc_140047029
0x14004722e  lea     r8, [rbp+57h+var_60]; this
0x140047232  mov     edx, r13d; Size
0x140047235  mov     rcx, r9; Src
0x140047238  call    AhcProbeAndReadEnvironment
0x14004723d  mov     edi, eax
0x14004723f  test    eax, eax
0x140047241  js      loc_140047620
0x140047247  mov     r15d, ebx
0x14004724a  mov     rbx, [rbp+57h+P+8]
0x14004724e  lea     rax, off_14000A520; "__COMPAT_LAYER"
0x140047255  cmp     r15d, 3
0x140047259  jnb     loc_140047064
0x14004725f  mov     edi, r15d
0x140047262  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140047266  add     rdi, rdi
0x140047269  mov     rdx, [rax+rdi*8]; SourceString
0x14004726d  lea     r13, [rax+rdi*8]
0x140047271  call    cs:__imp_RtlInitUnicodeStringEx
0x140047278  nop     dword ptr [rax+rax+00h]
0x14004727d  test    rbx, rbx
0x140047280  jz      short loc_14004728F
0x140047282  mov     edx, 74705041h; Tag
0x140047287  mov     rcx, rbx; P
0x14004728a  call    ExFreePoolWithTag_0
0x14004728f  lea     rax, off_14000A520; "__COMPAT_LAYER"
0x140047296  mov     r8d, 74705041h
0x14004729c  movzx   eax, word ptr [rax+rdi*8+8]
0x1400472a1  mov     ecx, 100h
0x1400472a6  add     ax, ax
0x1400472a9  movzx   edi, ax
0x1400472ac  mov     edx, edi
0x1400472ae  call    ExAllocatePool2_0
0x1400472b3  mov     rbx, rax
0x1400472b6  test    rax, rax
0x1400472b9  jz      loc_1400474A4
0x1400472bf  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1400472c4  lea     rax, [rbp+57h+NumberOfBytes]
0x1400472c8  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x1400472cc  mov     r9, rbx
0x1400472cf  mov     rcx, [rbp+57h+var_38]
0x1400472d3  mov     [rsp+28h], rax
0x1400472d8  shr     rdi, 1
0x1400472db  shr     r8, 1
0x1400472de  mov     [rsp+100h+var_E0], rdi
0x1400472e3  mov     [rbp+57h+NumberOfBytes], 0
0x1400472eb  call    AslEnvVarQuery
0x1400472f0  test    eax, eax
0x1400472f2  jns     short loc_1400472FC
0x1400472f4  inc     r15d
0x1400472f7  jmp     loc_14004724E
0x1400472fc  mov     rdx, [r13+0]; unsigned __int16 *
0x140047300  lea     r8, asc_14000C478; "="
0x140047307  lea     rcx, [rbp+57h+var_C8]; this
0x14004730b  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x140047310  mov     edi, eax
0x140047312  test    eax, eax
0x140047314  js      loc_140047483
0x14004731a  movzx   eax, word ptr [rbp+57h+NumberOfBytes]
0x14004731e  add     ax, ax
0x140047321  movzx   eax, ax
0x140047324  mov     [rbp+57h+P], rax
0x140047328  jz      short loc_14004736C
0x14004732a  mov     r13, [rbp+57h+Src]
0x14004732e  lea     rdi, [rax+r13]
0x140047332  cmp     rdi, r13
0x140047335  jb      short loc_1400473AE
0x140047337  cmp     rdi, [rbp+57h+Size+8]
0x14004733b  ja      loc_140047401
0x140047341  mov     rcx, [rbp+57h+Src+8]
0x140047345  mov     rdx, rbx; Src
0x140047348  mov     r8, [rbp+57h+P]; Size
0x14004734c  add     rcx, r13; void *
0x14004734f  call    memmove
0x140047354  cmp     rdi, r13
0x140047357  jb      short loc_1400473B5
0x140047359  mov     rax, [rbp+57h+Size]
0x14004735d  cmp     rax, rdi
0x140047360  mov     [rbp+57h+Src], rdi
0x140047364  cmovbe  rax, rdi
0x140047368  mov     [rbp+57h+Size], rax
0x14004736c  lea     r8, dword_14000C47C; unsigned __int16 *
0x140047373  lea     rdx, pszSrc; unsigned __int16 *
0x14004737a  lea     rcx, [rbp+57h+var_C8]; this
0x14004737e  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x140047383  mov     edi, eax
0x140047385  test    eax, eax
0x140047387  jns     loc_1400472F4
0x14004738d  lea     r9, aOutOfMemory; "Out of memory"
0x140047394  mov     r8d, 8DCh
0x14004739a  lea     rdx, aAhcpcachebuild_0; "AhcpCacheBuildEnvironmentSafe"
0x1400473a1  mov     ecx, r12d
0x1400473a4  call    AslLogCallPrintf
0x1400473a9  jmp     loc_1400470D4
0x1400473ae  mov     edi, 0C000000Dh
0x1400473b3  jmp     short loc_1400473BA
0x1400473b5  mov     edi, 0C0000095h
0x1400473ba  lea     r9, aOutOfMemory; "Out of memory"
0x1400473c1  mov     r8d, 8D6h
0x1400473c7  lea     rdx, aAhcpcachebuild_0; "AhcpCacheBuildEnvironmentSafe"
0x1400473ce  mov     ecx, r12d
0x1400473d1  call    AslLogCallPrintf
0x1400473d6  jmp     loc_1400470D4
0x1400473db  lea     r9, aOutOfMemory; "Out of memory"
0x1400473e2  mov     r8d, 8E9h
0x1400473e8  lea     rdx, aAhcpcachebuild_0; "AhcpCacheBuildEnvironmentSafe"
0x1400473ef  mov     ecx, r12d
0x1400473f2  mov     edi, 0C0000017h
0x1400473f7  call    AslLogCallPrintf
0x1400473fc  jmp     loc_1400470D4
0x140047401  mov     rax, [rbp+57h+var_B0]
0x140047405  dec     rax
0x140047408  lea     rcx, [rax+rdi]
0x14004740c  cmp     rcx, rdi
0x14004740f  jb      short loc_1400473B5
0x140047411  not     rax
0x140047414  and     rax, rcx
0x140047417  mov     [rbp+57h+NumberOfBytes], rax
0x14004741b  call    cs:__imp_KeGetCurrentIrql
0x140047422  nop     dword ptr [rax+rax+00h]
0x140047427  cmp     [rbp+57h+Src+8], 0
0x14004742c  mov     ecx, 200h
0x140047431  mov     rdx, [rbp+57h+NumberOfBytes]; NumberOfBytes
0x140047435  mov     r8d, 7274534Dh; Tag
0x14004743b  jnz     loc_140047527
0x140047441  cmp     al, 2
0x140047443  cmovnz  ecx, r12d; PoolType
0x140047447  call    cs:__imp_ExAllocatePoolWithTag
0x14004744e  nop     dword ptr [rax+rax+00h]
0x140047453  mov     [rbp+57h+var_98], rax
0x140047457  test    rax, rax
0x14004745a  jz      loc_140047649
0x140047460  mov     r8, [rbp+57h+NumberOfBytes]; Size
0x140047464  xor     edx, edx; Val
0x140047466  mov     rcx, rax; void *
0x140047469  call    memset
0x14004746e  mov     rax, [rbp+57h+var_98]
0x140047472  mov     [rbp+57h+Src+8], rax
0x140047476  mov     rax, [rbp+57h+NumberOfBytes]
  ... truncated ...
```
