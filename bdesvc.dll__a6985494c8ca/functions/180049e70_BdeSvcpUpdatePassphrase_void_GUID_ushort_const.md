# BdeSvcpUpdatePassphrase(void *,_GUID *,ushort const *)

- ea: `0x180049e70`
- end: `0x18004a20f`
- name: `?BdeSvcpUpdatePassphrase@@YAJPEAXPEAU_GUID@@PEBG@Z`
- size: `927`
- prototype: `__int64 __fastcall(void *, struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004c830`

## callees

- `0x180009f60`
- `0x180034070`
- `0x180034d28`
- `0x180049e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049fa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a1d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049fa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a1d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049fcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049fcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049ee8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049f94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049ee8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049f94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1c2`
- `FVEAPI!FveAddAuthMethodInformation` at `0x18004a13e`
- `FVEAPI!FveAddAuthMethodInformation` at `0x18004a13e`
- `FVEAPI!FveDeleteAuthMethod` at `0x18004a0ed`
- `FVEAPI!FveDeleteAuthMethod` at `0x18004a0ed`
- `FVEAPI!FveAuthElementFromPassPhraseW` at `0x18004a064`
- `FVEAPI!FveAuthElementFromPassPhraseW` at `0x18004a064`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180049f7b`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18004a031`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180049f7b`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18004a031`
- `FVEAPI!FveCommitChanges` at `0x18004a181`
- `FVEAPI!FveCommitChanges` at `0x18004a181`

## pseudocode

```c
__int64 __fastcall BdeSvcpUpdatePassphrase(void *a1, struct _GUID *a2, const unsigned __int16 *a3)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rax
  _QWORD *v8; // rsi
  int AuthMethodInformation; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // rax
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  _DWORD *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  HANDLE v20; // rax
  __int128 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h]
  __int128 v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  SIZE_T dwBytes; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v28[148]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v29; // [rsp+2C0h] [rbp+1C0h] BYREF

  v25 = 0;
  dwBytes = 0;
  v29 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v28, 0, 0x248u);
  v27 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0x38u);
  v8 = v7;
  if ( !v7 )
  {
    AuthMethodInformation = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 140;
LABEL_5:
      WPP_SF_d(v10[2], v11, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, 2147942414LL);
      return (unsigned int)AuthMethodInformation;
    }
    return (unsigned int)AuthMethodInformation;
  }
  *v7 = 56;
  v7[1] = 1;
  v7[2] = 8388612;
  AuthMethodInformation = FveGetAuthMethodInformation(
                            a1,
                            v7,
                            56,
                            &dwBytes,
                            v22,
                            *((_QWORD *)&v22 + 1),
                            v23,
                            *((_QWORD *)&v23 + 1),
                            v24,
                            *((_QWORD *)&v24 + 1),
                            v25);
  if ( AuthMethodInformation != -2147024774 )
  {
LABEL_12:
    if ( AuthMethodInformation < 0 )
      goto LABEL_33;
    v28[0] = 578;
    v28[1] = 1;
    v28[3] = 8;
    v16 = FveAuthElementFromPassPhraseW(a3, v28);
    AuthMethodInformation = v16;
    if ( !v16 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v16);
    if ( AuthMethodInformation >= 0 )
    {
LABEL_18:
      *(_QWORD *)&v22 = 0x100000038LL;
      v29 = v28;
      *(_QWORD *)&v23 = &v29;
      *((_QWORD *)&v22 + 1) = 0x100800000LL;
      *((_QWORD *)&v23 + 1) = v8[3];
      v17 = FveDeleteAuthMethod(a1, a2);
      AuthMethodInformation = v17;
      if ( !v17 )
        goto LABEL_23;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v17);
      if ( AuthMethodInformation >= 0 )
      {
LABEL_23:
        v18 = FveAddAuthMethodInformation(a1, &v22, &v27);
        AuthMethodInformation = v18;
        if ( !v18 )
          goto LABEL_28;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v18);
        if ( AuthMethodInformation >= 0 )
        {
LABEL_28:
          v19 = FveCommitChanges(a1);
          AuthMethodInformation = v19;
          if ( v19 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v19);
        }
      }
    }
    if ( v8 )
    {
LABEL_33:
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v8);
    }
    return (unsigned int)AuthMethodInformation;
  }
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v8);
  v13 = dwBytes;
  v14 = GetProcessHeap();
  v15 = HeapAlloc(v14, 0, v13);
  v8 = v15;
  if ( v15 )
  {
    *v15 = 56;
    v15[1] = 1;
    v15[2] = 8388612;
    AuthMethodInformation = FveGetAuthMethodInformation(
                              a1,
                              v15,
                              v13,
                              &dwBytes,
                              v22,
                              *((_QWORD *)&v22 + 1),
                              v23,
                              *((_QWORD *)&v23 + 1),
                              v24,
                              *((_QWORD *)&v24 + 1),
                              v25);
    goto LABEL_12;
  }
  AuthMethodInformation = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v11 = 141;
    goto LABEL_5;
  }
  return (unsigned int)AuthMethodInformation;
}

```

## disassembly

```asm
0x180049e70  mov     [rsp-8+arg_18], rbx
0x180049e75  push    rbp
0x180049e76  push    rsi
0x180049e77  push    rdi
0x180049e78  push    r12
0x180049e7a  push    r13
0x180049e7c  push    r14
0x180049e7e  push    r15
0x180049e80  lea     rbp, [rsp-1D0h]
0x180049e88  sub     rsp, 2D0h
0x180049e8f  mov     rax, cs:__security_cookie
0x180049e96  xor     rax, rsp
0x180049e99  mov     [rbp+200h+var_38], rax
0x180049ea0  xorps   xmm0, xmm0
0x180049ea3  xor     eax, eax
0x180049ea5  mov     rdi, r8
0x180049ea8  mov     [rsp+300h+var_2B0], rax
0x180049ead  mov     r15, rdx
0x180049eb0  mov     [rsp+300h+dwBytes], rax
0x180049eb5  mov     r14, rcx
0x180049eb8  mov     [rbp+200h+var_40], rax
0x180049ebf  xor     edx, edx; Val
0x180049ec1  lea     rcx, [rsp+300h+var_290]; void *
0x180049ec6  mov     r8d, 248h; Size
0x180049ecc  movups  [rsp+300h+var_2E0], xmm0
0x180049ed1  movups  [rsp+300h+var_2D0], xmm0
0x180049ed6  movups  [rsp+300h+var_2C0], xmm0
0x180049edb  call    memset_0
0x180049ee0  xorps   xmm0, xmm0
0x180049ee3  movups  [rsp+300h+var_2A0], xmm0
0x180049ee8  call    cs:__imp_GetProcessHeap
0x180049eef  nop     dword ptr [rax+rax+00h]
0x180049ef4  mov     r13d, 38h ; '8'
0x180049efa  xor     edx, edx; dwFlags
0x180049efc  mov     rcx, rax; hHeap
0x180049eff  mov     r8d, r13d; dwBytes
0x180049f02  call    cs:__imp_HeapAlloc
0x180049f09  nop     dword ptr [rax+rax+00h]
0x180049f0e  mov     rsi, rax
0x180049f11  test    rax, rax
0x180049f14  jnz     short loc_180049F59
0x180049f16  mov     r9d, 8007000Eh
0x180049f1c  mov     ebx, r9d
0x180049f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f26  lea     rdi, WPP_GLOBAL_Control
0x180049f2d  cmp     rcx, rdi
0x180049f30  jz      loc_18004A1E2
0x180049f36  test    byte ptr [rcx+1Ch], 40h
0x180049f3a  jz      loc_18004A1E2
0x180049f40  lea     edx, [r13+54h]
0x180049f44  mov     rcx, [rcx+10h]
0x180049f48  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180049f4f  call    WPP_SF_d
0x180049f54  jmp     loc_18004A1E2
0x180049f59  mov     r12d, 1
0x180049f5f  mov     [rax], r13d
0x180049f62  lea     r9, [rsp+300h+dwBytes]
0x180049f67  mov     [rax+4], r12d
0x180049f6b  mov     r8, r13
0x180049f6e  mov     dword ptr [rax+8], 800004h
0x180049f75  mov     rdx, rsi
0x180049f78  mov     rcx, r14
0x180049f7b  call    cs:__imp_FveGetAuthMethodInformation
0x180049f82  nop     dword ptr [rax+rax+00h]
0x180049f87  mov     ebx, eax
0x180049f89  cmp     eax, 8007007Ah
0x180049f8e  jnz     loc_18004A03F
0x180049f94  call    cs:__imp_GetProcessHeap
0x180049f9b  nop     dword ptr [rax+rax+00h]
0x180049fa0  mov     r8, rsi; lpMem
0x180049fa3  xor     edx, edx; dwFlags
0x180049fa5  mov     rcx, rax; hHeap
0x180049fa8  call    cs:__imp_HeapFree
0x180049faf  nop     dword ptr [rax+rax+00h]
0x180049fb4  mov     rbx, [rsp+300h+dwBytes]
0x180049fb9  call    cs:__imp_GetProcessHeap
0x180049fc0  nop     dword ptr [rax+rax+00h]
0x180049fc5  mov     r8, rbx; dwBytes
0x180049fc8  xor     edx, edx; dwFlags
0x180049fca  mov     rcx, rax; hHeap
0x180049fcd  call    cs:__imp_HeapAlloc
0x180049fd4  nop     dword ptr [rax+rax+00h]
0x180049fd9  mov     rsi, rax
0x180049fdc  test    rax, rax
0x180049fdf  jnz     short loc_18004A015
0x180049fe1  mov     r9d, 8007000Eh
0x180049fe7  mov     ebx, r9d
0x180049fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ff1  lea     rdi, WPP_GLOBAL_Control
0x180049ff8  cmp     rcx, rdi
0x180049ffb  jz      loc_18004A1E2
0x18004a001  test    byte ptr [rcx+1Ch], 40h
0x18004a005  jz      loc_18004A1E2
0x18004a00b  mov     edx, 8Dh
0x18004a010  jmp     loc_180049F44
0x18004a015  lea     r9, [rsp+300h+dwBytes]
0x18004a01a  mov     [rax], r13d
0x18004a01d  mov     r8, rbx
0x18004a020  mov     [rax+4], r12d
0x18004a024  mov     rdx, rax
0x18004a027  mov     dword ptr [rax+8], 800004h
0x18004a02e  mov     rcx, r14
0x18004a031  call    cs:__imp_FveGetAuthMethodInformation
0x18004a038  nop     dword ptr [rax+rax+00h]
0x18004a03d  mov     ebx, eax
0x18004a03f  test    ebx, ebx
0x18004a041  js      loc_18004A1C2
0x18004a047  lea     rdx, [rsp+300h+var_290]
0x18004a04c  mov     [rsp+300h+var_290], 242h
0x18004a054  mov     rcx, rdi
0x18004a057  mov     [rsp+300h+var_28C], r12d
0x18004a05c  mov     [rsp+300h+var_284], 8
0x18004a064  call    cs:__imp_FveAuthElementFromPassPhraseW
0x18004a06b  nop     dword ptr [rax+rax+00h]
0x18004a070  lea     rdi, WPP_GLOBAL_Control
0x18004a077  mov     ebx, eax
0x18004a079  test    eax, eax
0x18004a07b  jz      short loc_18004A0AF
0x18004a07d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a084  cmp     rcx, rdi
0x18004a087  jz      short loc_18004A0A7
0x18004a089  test    byte ptr [rcx+1Ch], 40h
0x18004a08d  jz      short loc_18004A0A7
0x18004a08f  mov     rcx, [rcx+10h]
0x18004a093  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004a09a  mov     edx, 8Eh
0x18004a09f  mov     r9d, eax
0x18004a0a2  call    WPP_SF_d
0x18004a0a7  test    ebx, ebx
0x18004a0a9  js      loc_18004A1BD
0x18004a0af  lea     rax, [rsp+300h+var_290]
0x18004a0b4  mov     dword ptr [rsp+300h+var_2E0], r13d
0x18004a0b9  mov     [rbp+200h+var_40], rax
0x18004a0c0  mov     rdx, r15
0x18004a0c3  lea     rax, [rbp+200h+var_40]
0x18004a0ca  mov     dword ptr [rsp+300h+var_2E0+4], r12d
0x18004a0cf  mov     qword ptr [rsp+300h+var_2D0], rax
0x18004a0d4  mov     rcx, r14
0x18004a0d7  mov     dword ptr [rsp+300h+var_2E0+8], 800000h
0x18004a0df  mov     dword ptr [rsp+300h+var_2E0+0Ch], r12d
0x18004a0e4  mov     rax, [rsi+18h]
0x18004a0e8  mov     qword ptr [rsp+300h+var_2D0+8], rax
0x18004a0ed  call    cs:__imp_FveDeleteAuthMethod
0x18004a0f4  nop     dword ptr [rax+rax+00h]
0x18004a0f9  mov     ebx, eax
0x18004a0fb  test    eax, eax
0x18004a0fd  jz      short loc_18004A131
0x18004a0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a106  cmp     rcx, rdi
0x18004a109  jz      short loc_18004A129
0x18004a10b  test    byte ptr [rcx+1Ch], 40h
0x18004a10f  jz      short loc_18004A129
0x18004a111  mov     rcx, [rcx+10h]
0x18004a115  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004a11c  mov     edx, 8Fh
0x18004a121  mov     r9d, eax
0x18004a124  call    WPP_SF_d
0x18004a129  test    ebx, ebx
0x18004a12b  js      loc_18004A1BD
0x18004a131  lea     r8, [rsp+300h+var_2A0]
0x18004a136  mov     rcx, r14
0x18004a139  lea     rdx, [rsp+300h+var_2E0]
0x18004a13e  call    cs:__imp_FveAddAuthMethodInformation
0x18004a145  nop     dword ptr [rax+rax+00h]
0x18004a14a  mov     ebx, eax
0x18004a14c  test    eax, eax
0x18004a14e  jz      short loc_18004A17E
0x18004a150  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a157  cmp     rcx, rdi
0x18004a15a  jz      short loc_18004A17A
0x18004a15c  test    byte ptr [rcx+1Ch], 40h
0x18004a160  jz      short loc_18004A17A
0x18004a162  mov     rcx, [rcx+10h]
0x18004a166  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004a16d  mov     edx, 90h
0x18004a172  mov     r9d, eax
0x18004a175  call    WPP_SF_d
0x18004a17a  test    ebx, ebx
0x18004a17c  js      short loc_18004A1BD
0x18004a17e  mov     rcx, r14
0x18004a181  call    cs:__imp_FveCommitChanges
0x18004a188  nop     dword ptr [rax+rax+00h]
0x18004a18d  mov     ebx, eax
0x18004a18f  test    eax, eax
0x18004a191  jz      short loc_18004A1BD
0x18004a193  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a19a  cmp     rcx, rdi
0x18004a19d  jz      short loc_18004A1BD
0x18004a19f  test    byte ptr [rcx+1Ch], 40h
0x18004a1a3  jz      short loc_18004A1BD
0x18004a1a5  mov     rcx, [rcx+10h]
0x18004a1a9  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004a1b0  mov     edx, 91h
0x18004a1b5  mov     r9d, eax
0x18004a1b8  call    WPP_SF_d
0x18004a1bd  test    rsi, rsi
0x18004a1c0  jz      short loc_18004A1E2
0x18004a1c2  call    cs:__imp_GetProcessHeap
0x18004a1c9  nop     dword ptr [rax+rax+00h]
0x18004a1ce  mov     r8, rsi; lpMem
0x18004a1d1  xor     edx, edx; dwFlags
0x18004a1d3  mov     rcx, rax; hHeap
0x18004a1d6  call    cs:__imp_HeapFree
0x18004a1dd  nop     dword ptr [rax+rax+00h]
0x18004a1e2  mov     eax, ebx
0x18004a1e4  mov     rcx, [rbp+200h+var_38]
0x18004a1eb  xor     rcx, rsp; StackCookie
0x18004a1ee  call    __security_check_cookie
0x18004a1f3  mov     rbx, [rsp+300h+arg_18]
0x18004a1fb  add     rsp, 2D0h
0x18004a202  pop     r15
0x18004a204  pop     r14
0x18004a206  pop     r13
0x18004a208  pop     r12
0x18004a20a  pop     rdi
0x18004a20b  pop     rsi
0x18004a20c  pop     rbp
0x18004a20d  retn
```
