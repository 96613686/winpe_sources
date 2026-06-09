# AhcpCacheEntryFilterForReboot

- ea: `0x140028850`
- end: `0x140028b58`
- name: `AhcpCacheEntryFilterForReboot`
- size: `776`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140028b90`

## callees

- `0x140001b78`
- `0x140007b40`
- `0x140028850`
- `0x140028b60`
- `0x14003e364`
- `0x1400442a4`
- `0x140045c38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028b31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b31`

## string_xrefs

- `0x1400288c5`: `AhcpCacheEntryFilterForReboot`
- `0x140028aaa`: `AhcpCacheEntryFilterForReboot`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntryFilterForReboot(__int64 a1)
{
  void *v1; // rdx
  int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  char *v7; // r14
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r12
  int HasClearOnReboot; // eax
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r12
  int v24; // eax
  unsigned __int64 v25; // r15
  unsigned __int64 v26; // rax
  const char *v27; // r9
  __int64 v28; // r8
  __int64 v30; // [rsp+20h] [rbp-40h]
  __int64 v31; // [rsp+30h] [rbp-30h] BYREF
  __int128 v32; // [rsp+38h] [rbp-28h]
  __int64 v33; // [rsp+48h] [rbp-18h]
  PVOID P[2]; // [rsp+50h] [rbp-10h]
  bool v35; // [rsp+A0h] [rbp+40h] BYREF
  int v36; // [rsp+A8h] [rbp+48h] BYREF
  int v37; // [rsp+B0h] [rbp+50h] BYREF

  v1 = *(void **)(a1 + 24);
  v31 = 0;
  v33 = 4096;
  v37 = -44897;
  v36 = 0;
  v32 = 0;
  *(_OWORD *)P = 0;
  if ( !v1 )
  {
LABEL_49:
    v7 = (char *)P[1];
    goto LABEL_50;
  }
  v3 = RtlMemoryStream::InitializeFromBuffer((RtlMemoryStream *)&v31, v1, *(unsigned int *)(a1 + 16));
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = "InitializeFromBuffer failed [%x]";
    v6 = 496;
LABEL_4:
    LODWORD(v30) = v3;
    AslLogCallPrintf(1, "AhcpCacheEntryFilterForReboot", v6, v5, v30);
    v7 = (char *)P[1];
    goto LABEL_51;
  }
  v8 = v32;
  v9 = 0;
  v7 = (char *)P[1];
  v35 = 0;
  if ( (_QWORD)v32 )
  {
    v10 = v32;
    while ( 1 )
    {
      if ( v9 > v10 || (v11 = v9 + 8, v9 + 8 < v9) || v11 > v10 )
      {
        v4 = -1073741275;
        goto LABEL_37;
      }
      v12 = *(_QWORD *)&v7[v9];
      P[0] = (PVOID)(v9 + 8);
      v13 = HIDWORD(v12) + v11;
      if ( v13 < v11 || v13 + 3 < v13 || (v14 = (v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL, v10 = v8, v14 > v8) )
      {
        v4 = -1073741675;
        goto LABEL_37;
      }
      v35 = 0;
      HasClearOnReboot = AhcpCacheEntryGetIfHasClearOnReboot(
                           (unsigned int)&v35,
                           (int)v11 + (int)v7,
                           HIDWORD(v12),
                           v12,
                           (__int64)&v36);
      v4 = HasClearOnReboot;
      if ( HasClearOnReboot )
        break;
      if ( v35 )
      {
        v16 = v8 - v14;
        memmove(&v7[v9], &v7[v14], v8 - v14);
        v8 = v16 + v9;
        *(_QWORD *)&v32 = v16 + v9;
        v17 = v16 + v9;
        if ( v9 > v16 + v9 )
        {
          v4 = -1073741811;
          goto LABEL_37;
        }
        v10 = v16 + v9;
      }
      else
      {
        v9 = v14;
        v17 = v8;
      }
      if ( v9 >= v17 )
        goto LABEL_19;
    }
    if ( HasClearOnReboot >= 0 )
      goto LABEL_19;
LABEL_37:
    v27 = "Failed to get extra flags from params in stream [%x]";
    v28 = 502;
    goto LABEL_38;
  }
LABEL_19:
  if ( v36 )
  {
    v18 = 0;
    v35 = 0;
    P[0] = 0;
    if ( v8 )
    {
      v19 = v8;
      while ( 1 )
      {
        if ( v18 > v19 || (v20 = v18 + 8, v18 + 8 < v18) || v20 > v19 )
        {
          v4 = -1073741275;
          goto LABEL_48;
        }
        v21 = *(_QWORD *)&v7[v18];
        P[0] = (PVOID)(v18 + 8);
        v22 = HIDWORD(v21) + v20;
        if ( v22 < v20 || v22 + 3 < v22 || (v23 = (v22 + 3) & 0xFFFFFFFFFFFFFFFCuLL, v19 = v8, v23 > v8) )
        {
          v4 = -1073741675;
          goto LABEL_48;
        }
        v35 = 0;
        v24 = AhcpCacheEntryFilterParamIfSubset(&v35, (__int64)&v7[v20], HIDWORD(v21), v21, &v37);
        v4 = v24;
        if ( v24 )
          break;
        if ( v35 )
        {
          v25 = v8 - v23;
          memmove(&v7[v18], &v7[v23], v8 - v23);
          v8 = v25 + v18;
          *(_QWORD *)&v32 = v25 + v18;
          v26 = v25 + v18;
          if ( v18 > v25 + v18 )
          {
            v4 = -1073741811;
            goto LABEL_48;
          }
          v19 = v25 + v18;
        }
        else
        {
          v18 = v23;
          v26 = v8;
        }
        P[0] = (PVOID)v18;
        if ( v18 >= v26 )
          goto LABEL_41;
      }
      if ( v24 >= 0 )
        goto LABEL_41;
LABEL_48:
      v27 = "Failed to filter stream [%x]";
      v28 = 513;
LABEL_38:
      LODWORD(v30) = v4;
      AslLogCallPrintf(1, "AhcpCacheEntryFilterForReboot", v28, v27, v30);
      goto LABEL_51;
    }
LABEL_41:
    v3 = AhcpCacheEntrySetDataFromStream(a1, (__int64)&v31);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = "Failed to set data in entry [%x]";
      v6 = 523;
      goto LABEL_4;
    }
    goto LABEL_49;
  }
LABEL_50:
  v4 = 0;
LABEL_51:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x7274534Du);
  return v4;
}

```

## disassembly

```asm
0x140028850  mov     [rsp-38h+arg_18], rbx
0x140028855  push    rbp
0x140028856  push    rsi
0x140028857  push    rdi
0x140028858  push    r12
0x14002885a  push    r13
0x14002885c  push    r14
0x14002885e  push    r15
0x140028860  mov     rbp, rsp
0x140028863  sub     rsp, 60h
0x140028867  mov     rdx, [rcx+18h]; void *
0x14002886b  xorps   xmm0, xmm0
0x14002886e  mov     [rbp+var_30], 0
0x140028876  xorps   xmm1, xmm1
0x140028879  mov     [rbp+var_18], 1000h
0x140028881  mov     r13, rcx
0x140028884  mov     [rbp+arg_10], 0FFFF509Fh
0x14002888b  mov     [rbp+arg_8], 0
0x140028892  movdqu  [rbp+var_28], xmm0
0x140028897  movdqu  xmmword ptr [rbp+P], xmm1
0x14002889c  test    rdx, rdx
0x14002889f  jz      loc_140028B1E
0x1400288a5  mov     r8d, [rcx+10h]; unsigned __int64
0x1400288a9  lea     rcx, [rbp+var_30]; this
0x1400288ad  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x1400288b2  mov     ebx, eax
0x1400288b4  test    eax, eax
0x1400288b6  jns     short loc_1400288E3
0x1400288b8  lea     r9, aInitializefrom; "InitializeFromBuffer failed [%x]"
0x1400288bf  mov     r8d, 1F0h
0x1400288c5  lea     rdx, aAhcpcacheentry_8; "AhcpCacheEntryFilterForReboot"
0x1400288cc  mov     dword ptr [rsp+60h+var_40], eax
0x1400288d0  mov     ecx, 1
0x1400288d5  call    AslLogCallPrintf
0x1400288da  mov     r14, [rbp+P+8]
0x1400288de  jmp     loc_140028B24
0x1400288e3  mov     rsi, qword ptr [rbp+var_28]
0x1400288e7  xor     edi, edi
0x1400288e9  mov     r14, [rbp+P+8]
0x1400288ed  mov     [rbp+arg_0], 0
0x1400288f1  test    rsi, rsi
0x1400288f4  jz      loc_1400289B9
0x1400288fa  mov     r15, rsi
0x1400288fd  cmp     rdi, r15
0x140028900  ja      loc_140028A98
0x140028906  lea     rcx, [rdi+8]
0x14002890a  cmp     rcx, rdi
0x14002890d  jb      loc_140028A98
0x140028913  cmp     rcx, r15
0x140028916  ja      loc_140028A98
0x14002891c  mov     r9, [rdi+r14]
0x140028920  mov     [rbp+P], rcx
0x140028924  mov     r8, r9
0x140028927  shr     r8, 20h
0x14002892b  lea     rax, [r8+rcx]
0x14002892f  cmp     rax, rcx
0x140028932  jb      loc_140028A91
0x140028938  lea     r12, [rax+3]
0x14002893c  cmp     r12, rax
0x14002893f  jb      loc_140028A91
0x140028945  and     r12, 0FFFFFFFFFFFFFFFCh
0x140028949  mov     r15, rsi
0x14002894c  cmp     r12, rsi
0x14002894f  ja      loc_140028A91
0x140028955  lea     rdx, [rcx+r14]
0x140028959  mov     [rbp+arg_0], 0
0x14002895d  lea     rax, [rbp+arg_8]
0x140028961  lea     rcx, [rbp+arg_0]
0x140028965  mov     [rsp+60h+var_40], rax
0x14002896a  call    AhcpCacheEntryGetIfHasClearOnReboot
0x14002896f  mov     ebx, eax
0x140028971  test    eax, eax
0x140028973  jnz     loc_140028A89
0x140028979  cmp     [rbp+arg_0], al
0x14002897c  jz      short loc_1400289AA
0x14002897e  sub     r15, r12
0x140028981  lea     rdx, [r12+r14]; Src
0x140028985  mov     r8, r15; Size
0x140028988  lea     rcx, [r14+rdi]; void *
0x14002898c  call    memmove
0x140028991  lea     rsi, [r15+rdi]
0x140028995  mov     qword ptr [rbp+var_28], rsi
0x140028999  mov     rax, rsi
0x14002899c  cmp     rdi, rsi
0x14002899f  ja      loc_140028A82
0x1400289a5  mov     r15, rsi
0x1400289a8  jmp     short loc_1400289B0
0x1400289aa  mov     rdi, r12
0x1400289ad  mov     rax, r15
0x1400289b0  cmp     rdi, rax
0x1400289b3  jb      loc_1400288FD
0x1400289b9  cmp     [rbp+arg_8], 0
0x1400289bd  jz      loc_140028B22
0x1400289c3  xor     edi, edi
0x1400289c5  mov     [rbp+arg_0], 0
0x1400289c9  mov     [rbp+P], rdi
0x1400289cd  test    rsi, rsi
0x1400289d0  jz      loc_140028AD4
0x1400289d6  mov     r15, rsi
0x1400289d9  cmp     rdi, r15
0x1400289dc  ja      loc_140028B0A
0x1400289e2  lea     rcx, [rdi+8]
0x1400289e6  cmp     rcx, rdi
0x1400289e9  jb      loc_140028B0A
0x1400289ef  cmp     rcx, r15
0x1400289f2  ja      loc_140028B0A
0x1400289f8  mov     r9, [rdi+r14]
0x1400289fc  mov     [rbp+P], rcx
0x140028a00  mov     r8, r9
0x140028a03  shr     r8, 20h
0x140028a07  lea     rax, [r8+rcx]
0x140028a0b  cmp     rax, rcx
0x140028a0e  jb      loc_140028B03
0x140028a14  lea     r12, [rax+3]
0x140028a18  cmp     r12, rax
0x140028a1b  jb      loc_140028B03
0x140028a21  and     r12, 0FFFFFFFFFFFFFFFCh
0x140028a25  mov     r15, rsi
0x140028a28  cmp     r12, rsi
0x140028a2b  ja      loc_140028B03
0x140028a31  lea     rdx, [rcx+r14]
0x140028a35  mov     [rbp+arg_0], 0
0x140028a39  lea     rax, [rbp+arg_10]
0x140028a3d  lea     rcx, [rbp+arg_0]
0x140028a41  mov     [rsp+60h+var_40], rax
0x140028a46  call    AhcpCacheEntryFilterParamIfSubset
0x140028a4b  mov     ebx, eax
0x140028a4d  test    eax, eax
0x140028a4f  jnz     loc_140028AFF
0x140028a55  cmp     [rbp+arg_0], al
0x140028a58  jz      short loc_140028AC1
0x140028a5a  sub     r15, r12
0x140028a5d  lea     rdx, [r12+r14]; Src
0x140028a61  mov     r8, r15; Size
0x140028a64  lea     rcx, [r14+rdi]; void *
0x140028a68  call    memmove
0x140028a6d  lea     rsi, [r15+rdi]
0x140028a71  mov     qword ptr [rbp+var_28], rsi
0x140028a75  mov     rax, rsi
0x140028a78  cmp     rdi, rsi
0x140028a7b  ja      short loc_140028AF8
0x140028a7d  mov     r15, rsi
0x140028a80  jmp     short loc_140028AC7
0x140028a82  mov     ebx, 0C000000Dh
0x140028a87  jmp     short loc_140028A9D
0x140028a89  jns     loc_1400289B9
0x140028a8f  jmp     short loc_140028A9D
0x140028a91  mov     ebx, 0C0000095h
0x140028a96  jmp     short loc_140028A9D
0x140028a98  mov     ebx, 0C0000225h
0x140028a9d  lea     r9, aFailedToGetExt; "Failed to get extra flags from params i"...
0x140028aa4  mov     r8d, 1F6h
0x140028aaa  lea     rdx, aAhcpcacheentry_8; "AhcpCacheEntryFilterForReboot"
0x140028ab1  mov     dword ptr [rsp+60h+var_40], ebx
0x140028ab5  mov     ecx, 1
0x140028aba  call    AslLogCallPrintf
0x140028abf  jmp     short loc_140028B24
0x140028ac1  mov     rdi, r12
0x140028ac4  mov     rax, r15
0x140028ac7  mov     [rbp+P], rdi
0x140028acb  cmp     rdi, rax
0x140028ace  jb      loc_1400289D9
0x140028ad4  lea     rdx, [rbp+var_30]
0x140028ad8  mov     rcx, r13
0x140028adb  call    AhcpCacheEntrySetDataFromStream
0x140028ae0  mov     ebx, eax
0x140028ae2  test    eax, eax
0x140028ae4  jns     short loc_140028B1E
0x140028ae6  lea     r9, aFailedToSetDat; "Failed to set data in entry [%x]"
0x140028aed  mov     r8d, 20Bh
0x140028af3  jmp     loc_1400288C5
0x140028af8  mov     ebx, 0C000000Dh
0x140028afd  jmp     short loc_140028B0F
0x140028aff  jns     short loc_140028AD4
0x140028b01  jmp     short loc_140028B0F
0x140028b03  mov     ebx, 0C0000095h
0x140028b08  jmp     short loc_140028B0F
0x140028b0a  mov     ebx, 0C0000225h
0x140028b0f  lea     r9, aFailedToFilter; "Failed to filter stream [%x]"
0x140028b16  mov     r8d, 201h
0x140028b1c  jmp     short loc_140028AAA
0x140028b1e  mov     r14, [rbp+P+8]
0x140028b22  xor     ebx, ebx
0x140028b24  test    r14, r14
0x140028b27  jz      short loc_140028B3D
0x140028b29  mov     edx, 7274534Dh; Tag
0x140028b2e  mov     rcx, r14; P
0x140028b31  call    cs:__imp_ExFreePoolWithTag
0x140028b38  nop     dword ptr [rax+rax+00h]
0x140028b3d  mov     eax, ebx
0x140028b3f  mov     rbx, [rsp+60h+arg_18]
0x140028b47  add     rsp, 60h
0x140028b4b  pop     r15
0x140028b4d  pop     r14
0x140028b4f  pop     r13
0x140028b51  pop     r12
0x140028b53  pop     rdi
0x140028b54  pop     rsi
0x140028b55  pop     rbp
0x140028b56  retn
```
