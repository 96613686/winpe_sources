# FaddLoadFromBuffer

- ea: `0x18005911c`
- end: `0x180059462`
- name: `FaddLoadFromBuffer`
- size: `838`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058fd0`

## callees

- `0x1800197d4`
- `0x18004ba9c`
- `0x180058350`
- `0x18005911c`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x180117898`
- `0x180118204`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18005932b`
- `ntdll!RtlComputeCrc32` at `0x18005932b`
- `ntdll!RtlFreeHeap` at `0x180059442`
- `ntdll!RtlFreeHeap` at `0x180059442`
- `KERNEL32!GetProcessHeap` at `0x1800593af`
- `KERNEL32!GetProcessHeap` at `0x1800593af`
- `KERNEL32!HeapFree` at `0x18005939b`
- `KERNEL32!HeapFree` at `0x18005939b`

## string_xrefs

- `0x18005922f`: `Failed to read header from stream [%x]`
- `0x18005930d`: `Failed to compute Crc checksum from stream [%x]`
- `0x1800592e1`: `Failed to read buffer with header version %d.%d.%d.%d [%x]`
- `0x1800593fe`: `FaddpReadNextFrameworkFromStream failed to read framework from stream [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FaddLoadFromBuffer(__int64 a1, void *a2, unsigned int a3)
{
  unsigned __int64 v4; // rsi
  __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  int v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  char *v13; // rax
  void *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  void *v17; // r8
  int NextFrameworkFromStream; // eax
  HANDLE HeapHandle; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  __int64 v23; // [rsp+68h] [rbp-18h]
  unsigned __int64 v24; // [rsp+70h] [rbp-10h]
  PVOID P; // [rsp+78h] [rbp-8h]
  size_t Size; // [rsp+A0h] [rbp+20h] BYREF

  v4 = a3;
  v21 = 0;
  v22 = 0;
  HeapHandle = NtCurrentPeb()->ProcessHeap;
  v24 = 0;
  P = 0;
  v23 = 4096;
  if ( !a1 || !a2 || a3 < 0x70 )
  {
    v8 = -2147024809;
    v9 = "Invalid parameters";
    v10 = 427;
    goto LABEL_31;
  }
  v6 = *(_QWORD *)(a1 + 112);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 16);
    Size = 0;
    if ( v7 )
    {
      if ( (int)ULongLongMult(v7, *(_QWORD *)(v6 + 8), &Size) >= 0 )
      {
        memset_0(*(void **)(v6 + 40), 0, Size);
        *(_QWORD *)(v6 + 16) = 0;
      }
    }
  }
  v8 = RtlMemoryStream::InitializeFromBuffer((RtlMemoryStream *)&HeapHandle, a2, v4);
  if ( v8 >= 0 )
  {
    v11 = v24;
    v12 = v21;
    if ( v24 <= v21 && v24 + 112 >= v24 && v24 + 112 <= v21 )
    {
      v13 = (char *)P;
      v24 += 112LL;
      *(_OWORD *)a1 = *(_OWORD *)((char *)P + v11);
      *(_OWORD *)(a1 + 16) = *(_OWORD *)&v13[v11 + 16];
      *(_OWORD *)(a1 + 32) = *(_OWORD *)&v13[v11 + 32];
      *(_OWORD *)(a1 + 48) = *(_OWORD *)&v13[v11 + 48];
      *(_OWORD *)(a1 + 64) = *(_OWORD *)&v13[v11 + 64];
      *(_OWORD *)(a1 + 80) = *(_OWORD *)&v13[v11 + 80];
      *(_OWORD *)(a1 + 96) = *(_OWORD *)&v13[v11 + 96];
      if ( *(_QWORD *)(a1 + 8) != 0x1000000000000LL )
      {
        v8 = -2089418747;
        AslLogCallPrintf(
          1,
          (unsigned int)"FaddLoadFromBuffer",
          456,
          (unsigned int)"Failed to read buffer with header version %d.%d.%d.%d [%x]");
        goto LABEL_32;
      }
      if ( (unsigned __int64)(unsigned int)(v4 - 112) + 112 <= v12 )
      {
        if ( RtlComputeCrc32(0, (PUCHAR)P + 112, v4 - 112) == *(_DWORD *)(a1 + 4) )
        {
          if ( !*(_QWORD *)(a1 + 112) )
          {
            v14 = operator new(0x30u);
            v15 = RtlArray<_FADD_FRAMEWORK>::RtlArray<_FADD_FRAMEWORK>(v14);
            *(_QWORD *)(a1 + 112) = v15;
            v16 = v15;
            if ( !v15 )
            {
              v8 = -2147024882;
              v9 = "Out of memory";
              v10 = 476;
              goto LABEL_31;
            }
            v17 = *(void **)(v15 + 40);
            if ( v17 )
              HeapFree(*(HANDLE *)v15, 0, v17);
            *(_OWORD *)v16 = 0;
            *(_OWORD *)(v16 + 16) = 0;
            *(_OWORD *)(v16 + 32) = 0;
            *(_QWORD *)v16 = GetProcessHeap();
            *(_QWORD *)(v16 + 32) = 16;
            *(_QWORD *)(v16 + 16) = 0;
            *(_QWORD *)(v16 + 24) = 0;
            *(_QWORD *)(v16 + 40) = 0;
            *(_QWORD *)(v16 + 8) = 2088;
          }
          do
          {
            NextFrameworkFromStream = FaddpReadNextFrameworkFromStream(
                                        *(_QWORD *)(a1 + 112),
                                        (RtlMemoryStream *)&HeapHandle);
            v8 = NextFrameworkFromStream;
          }
          while ( NextFrameworkFromStream >= 0 );
          if ( NextFrameworkFromStream == -2147024637 )
          {
            v8 = 0;
            goto LABEL_32;
          }
          v9 = "FaddpReadNextFrameworkFromStream failed to read framework from stream [%x]";
          v10 = 494;
        }
        else
        {
          v8 = -2147024873;
          v9 = "Crc checksums did not match";
          v10 = 468;
        }
      }
      else
      {
        v8 = -2147024809;
        v9 = "Failed to compute Crc checksum from stream [%x]";
        v10 = 462;
      }
    }
    else
    {
      v8 = -2147024809;
      v9 = "Failed to read header from stream [%x]";
      v10 = 445;
    }
  }
  else
  {
    v9 = "Failed to initialize memory stream from buffer [%x]";
    v10 = 439;
  }
LABEL_31:
  AslLogCallPrintf(1, (unsigned int)"FaddLoadFromBuffer", v10, (_DWORD)v9);
LABEL_32:
  if ( P )
    RtlFreeHeap(HeapHandle, 0, P);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005911c  mov     [rsp-18h+arg_8], rbx
0x180059121  mov     [rsp-18h+arg_10], rsi
0x180059126  push    rbp
0x180059127  push    rdi
0x180059128  push    r14
0x18005912a  mov     rbp, rsp
0x18005912d  sub     rsp, 80h
0x180059134  mov     rax, gs:60h
0x18005913d  mov     r14, rdx
0x180059140  mov     esi, r8d
0x180059143  mov     rdi, rcx
0x180059146  mov     [rbp+var_28], 0
0x18005914e  mov     [rbp+var_20], 0
0x180059156  mov     r9, [rax+30h]
0x18005915a  mov     [rbp+HeapHandle], r9
0x18005915e  mov     [rbp+var_10], 0
0x180059166  mov     [rbp+P], 0
0x18005916e  mov     [rbp+var_18], 1000h
0x180059176  test    rcx, rcx
0x180059179  jz      loc_180059410
0x18005917f  test    rdx, rdx
0x180059182  jz      loc_180059410
0x180059188  cmp     esi, 70h ; 'p'
0x18005918b  jb      loc_180059410
0x180059191  mov     rbx, [rcx+70h]
0x180059195  test    rbx, rbx
0x180059198  jz      short loc_1800591D3
0x18005919a  mov     rcx, [rbx+10h]; unsigned __int64
0x18005919e  mov     [rbp+Size], 0
0x1800591a6  test    rcx, rcx
0x1800591a9  jz      short loc_1800591D3
0x1800591ab  mov     rdx, [rbx+8]; unsigned __int64
0x1800591af  lea     r8, [rbp+Size]; unsigned __int64 *
0x1800591b3  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800591b8  test    eax, eax
0x1800591ba  js      short loc_1800591D3
0x1800591bc  mov     r8, [rbp+Size]; Size
0x1800591c0  xor     edx, edx; Val
0x1800591c2  mov     rcx, [rbx+28h]; void *
0x1800591c6  call    memset_0
0x1800591cb  mov     qword ptr [rbx+10h], 0
0x1800591d3  mov     r8, rsi; unsigned __int64
0x1800591d6  lea     rcx, [rbp+HeapHandle]; this
0x1800591da  mov     rdx, r14; void *
0x1800591dd  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x1800591e2  mov     ebx, eax
0x1800591e4  test    eax, eax
0x1800591e6  jns     short loc_18005920F
0x1800591e8  lea     r9, aFailedToInitia_0; "Failed to initialize memory stream from"...
0x1800591ef  mov     r8d, 1B7h
0x1800591f5  lea     rdx, aFaddloadfrombu; "FaddLoadFromBuffer"
0x1800591fc  mov     [rsp+80h+var_60], eax
0x180059200  mov     ecx, 1
0x180059205  call    AslLogCallPrintf
0x18005920a  jmp     loc_180059433
0x18005920f  mov     rcx, [rbp+var_10]
0x180059213  mov     rdx, [rbp+var_28]
0x180059217  cmp     rcx, rdx
0x18005921a  ja      short loc_18005922A
0x18005921c  lea     r8, [rcx+70h]
0x180059220  cmp     r8, rcx
0x180059223  jb      short loc_18005922A
0x180059225  cmp     r8, rdx
0x180059228  jbe     short loc_180059240
0x18005922a  mov     ebx, 80070057h
0x18005922f  lea     r9, aFailedToReadHe; "Failed to read header from stream [%x]"
0x180059236  mov     eax, ebx
0x180059238  mov     r8d, 1BDh
0x18005923e  jmp     short loc_1800591F5
0x180059240  mov     rax, [rbp+P]
0x180059244  mov     [rbp+var_10], r8
0x180059248  movups  xmm0, xmmword ptr [rcx+rax]
0x18005924c  movups  xmmword ptr [rdi], xmm0
0x18005924f  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180059254  movups  xmmword ptr [rdi+10h], xmm1
0x180059258  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x18005925d  movups  xmmword ptr [rdi+20h], xmm0
0x180059261  movups  xmm1, xmmword ptr [rcx+rax+30h]
0x180059266  movups  xmmword ptr [rdi+30h], xmm1
0x18005926a  movups  xmm0, xmmword ptr [rcx+rax+40h]
0x18005926f  movups  xmmword ptr [rdi+40h], xmm0
0x180059273  movups  xmm1, xmmword ptr [rcx+rax+50h]
0x180059278  movups  xmmword ptr [rdi+50h], xmm1
0x18005927c  movups  xmm0, xmmword ptr [rcx+rax+60h]
0x180059281  mov     rax, 1000000000000h
0x18005928b  movups  xmmword ptr [rdi+60h], xmm0
0x18005928f  mov     r9, [rdi+8]
0x180059293  cmp     r9, rax
0x180059296  jz      short loc_1800592F2
0x180059298  movzx   r8d, r9w
0x18005929c  mov     rax, r9
0x18005929f  shr     rax, 10h
0x1800592a3  mov     ebx, 83760005h
0x1800592a8  movzx   edx, ax
0x1800592ab  mov     rax, r9
0x1800592ae  mov     [rsp+80h+var_40], ebx
0x1800592b2  mov     [rsp+80h+var_48], r8d
0x1800592b7  mov     r8d, 1C8h
0x1800592bd  mov     [rsp+80h+var_50], edx
0x1800592c1  lea     rdx, aFaddloadfrombu; "FaddLoadFromBuffer"
0x1800592c8  shr     r9, 30h
0x1800592cc  shr     rax, 20h
0x1800592d0  movzx   ecx, ax
0x1800592d3  mov     [rsp+80h+var_58], ecx
0x1800592d7  mov     ecx, 1
0x1800592dc  mov     [rsp+80h+var_60], r9d
0x1800592e1  lea     r9, aFailedToReadBu; "Failed to read buffer with header versi"...
0x1800592e8  call    AslLogCallPrintf
0x1800592ed  jmp     loc_180059433
0x1800592f2  lea     r8d, [rsi-70h]; Length
0x1800592f6  mov     eax, r8d
0x1800592f9  add     rax, 70h ; 'p'
0x1800592fd  cmp     rax, 70h ; 'p'
0x180059301  jb      short loc_180059308
0x180059303  cmp     rax, rdx
0x180059306  jbe     short loc_180059321
0x180059308  mov     ebx, 80070057h
0x18005930d  lea     r9, aFailedToComput_1; "Failed to compute Crc checksum from str"...
0x180059314  mov     eax, ebx
0x180059316  mov     r8d, 1CEh
0x18005931c  jmp     loc_1800591F5
0x180059321  mov     rdx, [rbp+P]
0x180059325  xor     ecx, ecx; InitialCrc
0x180059327  add     rdx, 70h ; 'p'; Buffer
0x18005932b  call    cs:__imp_RtlComputeCrc32
0x180059331  cmp     eax, [rdi+4]
0x180059334  jz      short loc_18005934D
0x180059336  mov     ebx, 80070017h
0x18005933b  lea     r9, aCrcChecksumsDi; "Crc checksums did not match"
0x180059342  mov     r8d, 1D4h
0x180059348  jmp     loc_180059422
0x18005934d  cmp     qword ptr [rdi+70h], 0
0x180059352  jnz     loc_1800593E0
0x180059358  mov     ecx, 30h ; '0'; Size
0x18005935d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059362  mov     rcx, rax
0x180059365  call    ??0?$RtlArray@U_FADD_FRAMEWORK@@@@QEAA@XZ; RtlArray<_FADD_FRAMEWORK>::RtlArray<_FADD_FRAMEWORK>(void)
0x18005936a  mov     [rdi+70h], rax
0x18005936e  mov     rbx, rax
0x180059371  test    rax, rax
0x180059374  jnz     short loc_18005938D
0x180059376  mov     ebx, 8007000Eh
0x18005937b  lea     r9, aOutOfMemory_0; "Out of memory"
0x180059382  mov     r8d, 1DCh
0x180059388  jmp     loc_180059422
0x18005938d  mov     r8, [rax+28h]; lpMem
0x180059391  test    r8, r8
0x180059394  jz      short loc_1800593A1
0x180059396  mov     rcx, [rax]; hHeap
0x180059399  xor     edx, edx; dwFlags
0x18005939b  call    cs:__imp_HeapFree
0x1800593a1  xorps   xmm0, xmm0
0x1800593a4  movups  xmmword ptr [rbx], xmm0
0x1800593a7  movups  xmmword ptr [rbx+10h], xmm0
0x1800593ab  movups  xmmword ptr [rbx+20h], xmm0
0x1800593af  call    cs:__imp_GetProcessHeap
0x1800593b5  mov     [rbx], rax
0x1800593b8  mov     qword ptr [rbx+20h], 10h
0x1800593c0  mov     qword ptr [rbx+10h], 0
0x1800593c8  mov     qword ptr [rbx+18h], 0
0x1800593d0  mov     qword ptr [rbx+28h], 0
0x1800593d8  mov     qword ptr [rbx+8], 828h
0x1800593e0  mov     rcx, [rdi+70h]
0x1800593e4  lea     rdx, [rbp+HeapHandle]
0x1800593e8  call    ?FaddpReadNextFrameworkFromStream@@YAJPEAV?$RtlArray@U_FADD_FRAMEWORK@@@@PEAVRtlMemoryStream@@@Z; FaddpReadNextFrameworkFromStream(RtlArray<_FADD_FRAMEWORK> *,RtlMemoryStream *)
0x1800593ed  mov     ebx, eax
0x1800593ef  test    eax, eax
0x1800593f1  jns     short loc_1800593E0
0x1800593f3  cmp     eax, 80070103h
0x1800593f8  jnz     short loc_1800593FE
0x1800593fa  xor     ebx, ebx
0x1800593fc  jmp     short loc_180059433
0x1800593fe  lea     r9, aFaddpreadnextf; "FaddpReadNextFrameworkFromStream failed"...
0x180059405  mov     r8d, 1EEh
0x18005940b  jmp     loc_1800591F5
0x180059410  mov     ebx, 80070057h
0x180059415  lea     r9, aInvalidParamet; "Invalid parameters"
0x18005941c  mov     r8d, 1ABh
0x180059422  lea     rdx, aFaddloadfrombu; "FaddLoadFromBuffer"
0x180059429  mov     ecx, 1
0x18005942e  call    AslLogCallPrintf
0x180059433  mov     r8, [rbp+P]; P
0x180059437  test    r8, r8
0x18005943a  jz      short loc_180059448
0x18005943c  mov     rcx, [rbp+HeapHandle]; HeapHandle
0x180059440  xor     edx, edx; Flags
0x180059442  call    cs:__imp_RtlFreeHeap
0x180059448  lea     r11, [rsp+80h+var_s0]
0x180059450  mov     eax, ebx
0x180059452  mov     rbx, [r11+28h]
0x180059456  mov     rsi, [r11+30h]
0x18005945a  mov     rsp, r11
0x18005945d  pop     r14
0x18005945f  pop     rdi
0x180059460  pop     rbp
0x180059461  retn
```
