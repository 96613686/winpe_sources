# FaddSaveToBuffer

- ea: `0x18004dd68`
- end: `0x18004e12f`
- name: `FaddSaveToBuffer`
- size: `967`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004dadc`

## callees

- `0x1800197d4`
- `0x18004ba9c`
- `0x18004dd68`
- `0x180056b18`
- `0x18005a8bc`
- `0x180118400`
- `0x180125490`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18004df37`
- `ntdll!RtlComputeCrc32` at `0x18004df37`
- `ntdll!RtlFreeHeap` at `0x18004e10c`
- `ntdll!RtlFreeHeap` at `0x18004e10c`
- `ntdll!RtlReAllocateHeap` at `0x18004dfcb`
- `ntdll!RtlReAllocateHeap` at `0x18004dfcb`
- `ntdll!RtlAllocateHeap` at `0x18004de2b`
- `ntdll!RtlAllocateHeap` at `0x18004dfa8`
- `ntdll!RtlAllocateHeap` at `0x18004e045`
- `ntdll!RtlAllocateHeap` at `0x18004de2b`
- `ntdll!RtlAllocateHeap` at `0x18004dfa8`
- `ntdll!RtlAllocateHeap` at `0x18004e045`

## string_xrefs

- `0x18004e016`: `Failed to write Crc checksum to stream [%x]`
- `0x18004e0c6`: `RtlMemoryStream failed to write header [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall FaddSaveToBuffer(_QWORD *a1, _QWORD *a2, __int128 *a3)
{
  __int64 v3; // r13
  void *v4; // r12
  _QWORD *v6; // r15
  PVOID ProcessHeap; // rsi
  int v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  _OWORD *Heap; // rax
  _OWORD *v12; // rbx
  __int128 v13; // xmm0
  unsigned __int64 v14; // rsi
  __int64 v15; // r9
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  struct _FADD_FRAMEWORK *v18; // r8
  const char *v19; // r9
  int v20; // r8d
  SIZE_T v21; // rbx
  PVOID v22; // rax
  _DWORD *v23; // rdi
  int v24; // eax
  unsigned __int64 v25; // rax
  SIZE_T v26; // r14
  _DWORD *v27; // rax
  _DWORD *v28; // r15
  PVOID v29; // rax
  __int64 result; // rax
  PVOID HeapHandle[4]; // [rsp+30h] [rbp-38h] BYREF
  PVOID Ptr[3]; // [rsp+50h] [rbp-18h]
  unsigned __int64 v35; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+60h]

  v3 = 0;
  v4 = 0;
  v36 = 0;
  v6 = a2;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  memset(HeapHandle, 0, sizeof(HeapHandle));
  *(_OWORD *)Ptr = 0;
  if ( !a3 || !a1 || !a2 )
  {
    v8 = -2147024809;
    AslLogCallPrintf(1, (unsigned int)"FaddSaveToBuffer", 683, (unsigned int)"Invalid parameters");
    goto LABEL_42;
  }
  if ( !*((_QWORD *)a3 + 14) )
  {
    v8 = -2147019873;
    v9 = "No frameworks results have been retrieved or loaded [%x]";
    v10 = 691;
LABEL_6:
    AslLogCallPrintf(1, (unsigned int)"FaddSaveToBuffer", v10, (_DWORD)v9);
LABEL_42:
    v23 = Ptr[1];
    goto LABEL_43;
  }
  HeapHandle[3] = (PVOID)4096;
  *(_OWORD *)&HeapHandle[1] = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  HeapHandle[0] = ProcessHeap;
  *(_OWORD *)Ptr = 0;
  Heap = RtlAllocateHeap(ProcessHeap, 0, 0x1000u);
  v12 = Heap;
  if ( !Heap )
  {
    v8 = -1073741801;
    v9 = "RtlMemoryStream failed to write header [%x]";
    v10 = 703;
    goto LABEL_6;
  }
  memset_0(Heap, 0, 0x1000u);
  Ptr[1] = v12;
  HeapHandle[2] = (PVOID)4096;
  v13 = *a3;
  v14 = 0;
  Ptr[0] = (PVOID)112;
  *v12 = v13;
  HeapHandle[1] = (PVOID)112;
  v12[1] = a3[1];
  v12[2] = a3[2];
  v12[3] = a3[3];
  v12[4] = a3[4];
  v12[5] = a3[5];
  v12[6] = a3[6];
  while ( 1 )
  {
    v15 = *((_QWORD *)a3 + 14);
    if ( v14 >= *(_QWORD *)(v15 + 16) )
      break;
    v16 = *(_QWORD *)(v15 + 8);
    v35 = 0;
    if ( (int)ULongLongMult(v16, v14, &v35) < 0
      || (v18 = (struct _FADD_FRAMEWORK *)(*(_QWORD *)(v17 + 40) + v35), (unsigned __int64)v18 < *(_QWORD *)(v17 + 40)) )
    {
      v18 = 0;
    }
    v8 = FaddpWriteFrameworkToStream(v18, (struct RtlMemoryStream *)HeapHandle);
    if ( v8 < 0 )
    {
      v19 = "Failed to add framework to stream [%x]";
      v20 = 711;
LABEL_16:
      AslLogCallPrintf(1, (unsigned int)"FaddSaveToBuffer", v20, (_DWORD)v19);
      ProcessHeap = HeapHandle[0];
      goto LABEL_42;
    }
    ++v14;
  }
  v21 = (SIZE_T)HeapHandle[1];
  v22 = (PVOID)((unsigned int)(LODWORD(HeapHandle[1]) - 112) + 112LL);
  if ( (unsigned __int64)v22 < 0x70 || v22 > HeapHandle[1] )
  {
    v8 = -2147024809;
    v19 = "Failed to get Crc checksum for frameworks [%x]";
    v20 = 720;
    goto LABEL_16;
  }
  v23 = Ptr[1];
  v24 = RtlComputeCrc32(0, (PUCHAR)Ptr[1] + 112, LODWORD(HeapHandle[1]) - 112);
  LODWORD(v35) = v24;
  if ( v21 < 4 )
  {
    v8 = -2147024809;
    AslLogCallPrintf(
      1,
      (unsigned int)"FaddSaveToBuffer",
      726,
      (unsigned int)"Failed to seek to Crc checksum in stream [%x]");
    ProcessHeap = HeapHandle[0];
    goto LABEL_43;
  }
  ProcessHeap = HeapHandle[0];
  if ( HeapHandle[2] < (PVOID)8 )
  {
    v25 = (unsigned __int64)HeapHandle[3] + 7;
    if ( v25 < 8 )
    {
      v8 = -1073741675;
      goto LABEL_35;
    }
    v26 = v25 & ~((__int64)HeapHandle[3] - 1);
    if ( v23 )
    {
      v28 = RtlReAllocateHeap(HeapHandle[0], 0, v23, v26);
    }
    else
    {
      v27 = RtlAllocateHeap(HeapHandle[0], 0, v26);
      v28 = v27;
      if ( v27 )
        memset_0(v27, 0, v26);
    }
    if ( !v28 )
    {
      v6 = a2;
      v8 = -1073741801;
LABEL_35:
      AslLogCallPrintf(
        1,
        (unsigned int)"FaddSaveToBuffer",
        732,
        (unsigned int)"Failed to write Crc checksum to stream [%x]");
      goto LABEL_43;
    }
    v24 = v35;
    v23 = v28;
    v6 = a2;
  }
  v23[1] = v24;
  LODWORD(v36) = 0;
  if ( v21 <= 8 )
    v21 = 8;
  v29 = RtlAllocateHeap(ProcessHeap, 0, v21);
  v4 = v29;
  if ( v29 )
  {
    memset_0(v29, 0, v21);
    memcpy_0(v4, v23, v21);
    LODWORD(v36) = v21;
    v3 = v36;
    v8 = 0;
  }
  else
  {
    v8 = -2147024882;
    AslLogCallPrintf(1, (unsigned int)"FaddSaveToBuffer", 738, (unsigned int)"Failed to clone stream [%x]");
    FaddFrameworkBufferFree(0);
    v4 = 0;
  }
LABEL_43:
  if ( v23 )
    RtlFreeHeap(ProcessHeap, 0, v23);
  *a1 = v4;
  result = (unsigned int)v8;
  *v6 = v3;
  return result;
}

```

## disassembly

```asm
0x18004dd68  mov     [rsp-40h+arg_8], rdx
0x18004dd6d  mov     [rsp-40h+arg_0], rcx
0x18004dd72  push    rbp
0x18004dd73  push    rbx
0x18004dd74  push    rsi
0x18004dd75  push    rdi
0x18004dd76  push    r12
0x18004dd78  push    r13
0x18004dd7a  push    r14
0x18004dd7c  push    r15
0x18004dd7e  mov     rbp, rsp
0x18004dd81  sub     rsp, 68h
0x18004dd85  mov     rax, gs:60h
0x18004dd8e  xorps   xmm0, xmm0
0x18004dd91  xor     r13d, r13d
0x18004dd94  xor     r12d, r12d
0x18004dd97  mov     [rbp+arg_18], r13
0x18004dd9b  mov     rdi, r8
0x18004dd9e  mov     r15, rdx
0x18004dda1  mov     rsi, [rax+30h]
0x18004dda5  movups  xmmword ptr [rbp+HeapHandle], xmm0
0x18004dda9  movups  [rbp+var_28], xmm0
0x18004ddad  movups  xmmword ptr [rbp+Ptr], xmm0
0x18004ddb1  test    r8, r8
0x18004ddb4  jz      loc_18004E0D8
0x18004ddba  test    rcx, rcx
0x18004ddbd  jz      loc_18004E0D8
0x18004ddc3  test    rdx, rdx
0x18004ddc6  jz      loc_18004E0D8
0x18004ddcc  cmp     [r8+70h], r12
0x18004ddd0  jnz     short loc_18004DDFE
0x18004ddd2  mov     ebx, 8007139Fh
0x18004ddd7  lea     r9, aNoFrameworksRe; "No frameworks results have been retriev"...
0x18004ddde  mov     r8d, 2B3h
0x18004dde4  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004ddeb  mov     [rsp+68h+var_48], ebx
0x18004ddef  mov     ecx, 1
0x18004ddf4  call    AslLogCallPrintf
0x18004ddf9  jmp     loc_18004E0FB
0x18004ddfe  mov     rax, gs:60h
0x18004de07  mov     r14d, 1000h
0x18004de0d  mov     r8d, r14d; Size
0x18004de10  mov     qword ptr [rbp+var_28+8], r14
0x18004de14  xor     edx, edx; Flags
0x18004de16  movdqu  xmmword ptr [rbp+HeapHandle+8], xmm0
0x18004de1b  mov     rsi, [rax+30h]
0x18004de1f  mov     rcx, rsi; HeapHandle
0x18004de22  mov     [rbp+HeapHandle], rsi
0x18004de26  movdqu  xmmword ptr [rbp+Ptr], xmm0
0x18004de2b  call    cs:__imp_RtlAllocateHeap
0x18004de31  mov     rbx, rax
0x18004de34  test    rax, rax
0x18004de37  jz      loc_18004E0C1
0x18004de3d  mov     r8d, r14d; Size
0x18004de40  xor     edx, edx; Val
0x18004de42  mov     rcx, rax; void *
0x18004de45  call    memset_0
0x18004de4a  mov     [rbp+Ptr+8], rbx
0x18004de4e  mov     qword ptr [rbp+var_28], r14
0x18004de52  movups  xmm0, xmmword ptr [rdi]
0x18004de55  mov     r14d, 70h ; 'p'
0x18004de5b  xor     esi, esi
0x18004de5d  mov     [rbp+Ptr], r14
0x18004de61  movups  xmmword ptr [rbx], xmm0
0x18004de64  mov     [rbp+HeapHandle+8], r14
0x18004de68  movups  xmm1, xmmword ptr [rdi+10h]
0x18004de6c  movups  xmmword ptr [rbx+10h], xmm1
0x18004de70  movups  xmm0, xmmword ptr [rdi+20h]
0x18004de74  movups  xmmword ptr [rbx+20h], xmm0
0x18004de78  movups  xmm1, xmmword ptr [rdi+30h]
0x18004de7c  movups  xmmword ptr [rbx+30h], xmm1
0x18004de80  movups  xmm0, xmmword ptr [rdi+40h]
0x18004de84  movups  xmmword ptr [rbx+40h], xmm0
0x18004de88  movups  xmm1, xmmword ptr [rdi+50h]
0x18004de8c  movups  xmmword ptr [rbx+50h], xmm1
0x18004de90  movups  xmm0, xmmword ptr [rdi+60h]
0x18004de94  movups  xmmword ptr [rbx+60h], xmm0
0x18004de98  mov     r9, [rdi+70h]
0x18004de9c  cmp     rsi, [r9+10h]
0x18004dea0  jnb     short loc_18004DF0D
0x18004dea2  mov     rcx, [r9+8]; unsigned __int64
0x18004dea6  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18004deaa  mov     rdx, rsi; unsigned __int64
0x18004dead  mov     [rbp+arg_10], r12
0x18004deb1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004deb6  test    eax, eax
0x18004deb8  js      short loc_18004DEC8
0x18004deba  mov     r8, [rbp+arg_10]
0x18004debe  add     r8, [r9+28h]
0x18004dec2  cmp     r8, [r9+28h]
0x18004dec6  jnb     short loc_18004DECB
0x18004dec8  xor     r8d, r8d
0x18004decb  lea     rdx, [rbp+HeapHandle]; this
0x18004decf  mov     rcx, r8; struct _FADD_FRAMEWORK *
0x18004ded2  call    ?FaddpWriteFrameworkToStream@@YAJPEAU_FADD_FRAMEWORK@@PEAVRtlMemoryStream@@@Z; FaddpWriteFrameworkToStream(_FADD_FRAMEWORK *,RtlMemoryStream *)
0x18004ded7  mov     ebx, eax
0x18004ded9  test    eax, eax
0x18004dedb  js      short loc_18004DEE2
0x18004dedd  inc     rsi
0x18004dee0  jmp     short loc_18004DE98
0x18004dee2  mov     [rsp+68h+var_48], eax
0x18004dee6  lea     r9, aFailedToAddFra; "Failed to add framework to stream [%x]"
0x18004deed  mov     r8d, 2C7h
0x18004def3  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004defa  mov     ecx, 1
0x18004deff  call    AslLogCallPrintf
0x18004df04  mov     rsi, [rbp+HeapHandle]
0x18004df08  jmp     loc_18004E0FB
0x18004df0d  mov     rbx, [rbp+HeapHandle+8]
0x18004df11  lea     r8d, [rbx-70h]; Length
0x18004df15  mov     eax, r8d
0x18004df18  add     rax, r14
0x18004df1b  cmp     rax, r14
0x18004df1e  jb      loc_18004E0A6
0x18004df24  cmp     rax, rbx
0x18004df27  ja      loc_18004E0A6
0x18004df2d  mov     rdi, [rbp+Ptr+8]
0x18004df31  xor     ecx, ecx; InitialCrc
0x18004df33  lea     rdx, [rdi+70h]; Buffer
0x18004df37  call    cs:__imp_RtlComputeCrc32
0x18004df3d  mov     dword ptr [rbp+arg_10], eax
0x18004df40  cmp     rbx, 4
0x18004df44  jnb     short loc_18004DF76
0x18004df46  mov     ebx, 80070057h
0x18004df4b  lea     r9, aFailedToSeekTo; "Failed to seek to Crc checksum in strea"...
0x18004df52  mov     r8d, 2D6h
0x18004df58  mov     [rsp+68h+var_48], ebx
0x18004df5c  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004df63  mov     ecx, 1
0x18004df68  call    AslLogCallPrintf
0x18004df6d  mov     rsi, [rbp+HeapHandle]
0x18004df71  jmp     loc_18004E0FF
0x18004df76  mov     rsi, [rbp+HeapHandle]
0x18004df7a  mov     ecx, 8
0x18004df7f  cmp     qword ptr [rbp+var_28], rcx
0x18004df83  jnb     short loc_18004DFF3
0x18004df85  mov     r14, qword ptr [rbp+var_28+8]
0x18004df89  dec     r14
0x18004df8c  lea     rax, [r14+8]
0x18004df90  cmp     rax, rcx
0x18004df93  jb      short loc_18004E011
0x18004df95  not     r14
0x18004df98  xor     edx, edx; Flags
0x18004df9a  and     r14, rax
0x18004df9d  mov     rcx, rsi; Heap
0x18004dfa0  test    rdi, rdi
0x18004dfa3  jnz     short loc_18004DFC5
0x18004dfa5  mov     r8, r14; Size
0x18004dfa8  call    cs:__imp_RtlAllocateHeap
0x18004dfae  mov     r15, rax
0x18004dfb1  test    rax, rax
0x18004dfb4  jz      short loc_18004DFD4
0x18004dfb6  mov     r8, r14; Size
0x18004dfb9  xor     edx, edx; Val
0x18004dfbb  mov     rcx, rax; void *
0x18004dfbe  call    memset_0
0x18004dfc3  jmp     short loc_18004DFD4
0x18004dfc5  mov     r9, r14; Size
0x18004dfc8  mov     r8, rdi; Ptr
0x18004dfcb  call    cs:__imp_RtlReAllocateHeap
0x18004dfd1  mov     r15, rax
0x18004dfd4  test    r15, r15
0x18004dfd7  jnz     short loc_18004DFE4
0x18004dfd9  mov     r15, [rbp+arg_8]
0x18004dfdd  mov     ebx, 0C0000017h
0x18004dfe2  jmp     short loc_18004E016
0x18004dfe4  mov     eax, dword ptr [rbp+arg_10]
0x18004dfe7  mov     rdi, r15
0x18004dfea  mov     r15, [rbp+arg_8]
0x18004dfee  mov     ecx, 8
0x18004dff3  cmp     rbx, rcx
0x18004dff6  mov     [rdi+4], eax
0x18004dff9  mov     dword ptr [rbp+arg_18], r12d
0x18004dffd  cmovbe  rbx, rcx
0x18004e001  test    rbx, rbx
0x18004e004  jnz     short loc_18004E03D
0x18004e006  mov     r13, [rbp+arg_18]
0x18004e00a  xor     ebx, ebx
0x18004e00c  jmp     loc_18004E0FF
0x18004e011  mov     ebx, 0C0000095h
0x18004e016  lea     r9, aFailedToWriteC; "Failed to write Crc checksum to stream "...
0x18004e01d  mov     [rsp+68h+var_48], ebx
0x18004e021  mov     r8d, 2DCh
0x18004e027  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004e02e  mov     ecx, 1
0x18004e033  call    AslLogCallPrintf
0x18004e038  jmp     loc_18004E0FF
0x18004e03d  mov     r8, rbx; Size
0x18004e040  xor     edx, edx; Flags
0x18004e042  mov     rcx, rsi; HeapHandle
0x18004e045  call    cs:__imp_RtlAllocateHeap
0x18004e04b  mov     r12, rax
0x18004e04e  test    rax, rax
0x18004e051  jz      short loc_18004E073
0x18004e053  mov     r8, rbx; Size
0x18004e056  xor     edx, edx; Val
0x18004e058  mov     rcx, rax; void *
0x18004e05b  call    memset_0
0x18004e060  mov     r8, rbx; Size
0x18004e063  mov     rdx, rdi; Src
0x18004e066  mov     rcx, r12; void *
0x18004e069  call    memcpy_0
0x18004e06e  mov     dword ptr [rbp+arg_18], ebx
0x18004e071  jmp     short loc_18004E006
0x18004e073  mov     ebx, 8007000Eh
0x18004e078  lea     r9, aFailedToCloneS; "Failed to clone stream [%x]"
0x18004e07f  mov     r8d, 2E2h
0x18004e085  mov     [rsp+68h+var_48], ebx
0x18004e089  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004e090  mov     ecx, 1
0x18004e095  call    AslLogCallPrintf
0x18004e09a  xor     ecx, ecx
0x18004e09c  call    FaddFrameworkBufferFree
0x18004e0a1  xor     r12d, r12d
0x18004e0a4  jmp     short loc_18004E0FF
0x18004e0a6  mov     ebx, 80070057h
0x18004e0ab  lea     r9, aFailedToGetCrc; "Failed to get Crc checksum for framewor"...
0x18004e0b2  mov     [rsp+68h+var_48], ebx
0x18004e0b6  mov     r8d, 2D0h
0x18004e0bc  jmp     loc_18004DEF3
0x18004e0c1  mov     ebx, 0C0000017h
0x18004e0c6  lea     r9, aRtlmemorystrea; "RtlMemoryStream failed to write header "...
0x18004e0cd  mov     r8d, 2BFh
0x18004e0d3  jmp     loc_18004DDE4
0x18004e0d8  lea     r9, aInvalidParamet; "Invalid parameters"
0x18004e0df  mov     r8d, 2ABh
0x18004e0e5  lea     rdx, aFaddsavetobuff; "FaddSaveToBuffer"
0x18004e0ec  mov     ecx, 1
0x18004e0f1  mov     ebx, 80070057h
0x18004e0f6  call    AslLogCallPrintf
0x18004e0fb  mov     rdi, [rbp+Ptr+8]
0x18004e0ff  test    rdi, rdi
0x18004e102  jz      short loc_18004E112
0x18004e104  mov     r8, rdi; P
0x18004e107  xor     edx, edx; Flags
0x18004e109  mov     rcx, rsi; HeapHandle
0x18004e10c  call    cs:__imp_RtlFreeHeap
0x18004e112  mov     rax, [rbp+arg_0]
0x18004e116  mov     [rax], r12
0x18004e119  mov     eax, ebx
0x18004e11b  mov     [r15], r13
0x18004e11e  add     rsp, 68h
0x18004e122  pop     r15
0x18004e124  pop     r14
0x18004e126  pop     r13
0x18004e128  pop     r12
0x18004e12a  pop     rdi
0x18004e12b  pop     rsi
0x18004e12c  pop     rbx
0x18004e12d  pop     rbp
0x18004e12e  retn
```
