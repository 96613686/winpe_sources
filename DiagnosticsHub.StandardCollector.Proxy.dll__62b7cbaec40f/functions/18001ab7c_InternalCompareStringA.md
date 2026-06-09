# InternalCompareStringA

- ea: `0x18001ab7c`
- end: `0x18001af0b`
- name: `InternalCompareStringA`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001af0c`

## callees

- `0x180002810`
- `0x180008040`
- `0x18000b67c`
- `0x18000d66c`
- `0x1800126d0`
- `0x18001a4c0`
- `0x18001ab7c`
- `0x180032a50`

## import_xrefs

- `KERNEL32!GetCPInfo` at `0x18001ac4f`
- `KERNEL32!GetCPInfo` at `0x18001ac4f`

## pseudocode

```c
__int64 __fastcall InternalCompareStringA(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        const char *a4,
        int a5,
        char *String,
        int a7,
        UINT CodePage)
{
  int v8; // edi
  int v11; // esi
  UINT v12; // r15d
  BYTE *LeadByte; // rax
  BYTE *v15; // rax
  signed int v16; // eax
  unsigned int v17; // r13d
  size_t v18; // rdx
  __int64 v19; // rax
  void *v20; // rsp
  const WCHAR *v21; // rbx
  WCHAR *v22; // rax
  int v23; // eax
  int v24; // r12d
  size_t v25; // rcx
  __int64 v26; // rax
  void *v27; // rsp
  const WCHAR *v28; // rdi
  WCHAR *v29; // rax
  WCHAR *v30; // r14
  WCHAR *v31; // rcx
  bool v32; // zf
  unsigned int v33; // edi
  _BYTE v34[32]; // [rsp+0h] [rbp-50h] BYREF
  DWORD v35; // [rsp+50h] [rbp+0h] BYREF
  char *v36; // [rsp+58h] [rbp+8h]
  __int64 v37; // [rsp+60h] [rbp+10h]
  struct _cpinfo CPInfo; // [rsp+68h] [rbp+18h] BYREF

  v8 = a5;
  v35 = a3;
  v37 = a2;
  v36 = String;
  if ( a5 <= 0 )
  {
    if ( a5 < -1 )
      return 0;
  }
  else
  {
    v8 = _strncnt(a4, a5);
  }
  v11 = a7;
  if ( a7 <= 0 )
  {
    if ( a7 < -1 )
      return 0;
  }
  else
  {
    v11 = _strncnt(String, a7);
  }
  v12 = CodePage;
  if ( !CodePage )
    v12 = *(_DWORD *)(*(_QWORD *)a1 + 12LL);
  if ( !v8 || !v11 )
  {
    memset(&CPInfo, 0, sizeof(CPInfo));
    if ( v8 == v11 )
      return 2;
    if ( v11 > 1 )
      return 1;
    if ( v8 > 1 )
      return 3;
    if ( !GetCPInfo(v12, &CPInfo) )
      return 0;
    if ( v8 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a4 >= *LeadByte && (unsigned int)*a4 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v11 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v15 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v15[1] )
          {
            if ( (unsigned __int8)*String >= *v15 && (unsigned __int8)*String <= v15[1] )
              return 2;
            v15 += 2;
            if ( !*v15 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v16 = _acrt_MultiByteToWideChar(v12, 9, a4, (unsigned int)v8, 0, 0);
  v17 = v16;
  if ( !v16 )
    return 0;
  v18 = (2LL * v16 + 16) & -(__int64)(2LL * v16 < (unsigned __int64)(2LL * v16 + 16));
  if ( !v18 )
    return 0;
  if ( v18 > 0x400 )
  {
    v22 = (WCHAR *)malloc_base(v18);
    v21 = v22;
    if ( !v22 )
      goto LABEL_41;
    *(_DWORD *)v22 = 56797;
  }
  else
  {
    v19 = v18 + 15;
    if ( v18 + 15 < v18 )
      v19 = 0xFFFFFFFFFFFFFF0LL;
    v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
    v21 = (const WCHAR *)&v35;
    if ( v34 == (_BYTE *)-80LL )
      return 0;
    v35 = 52428;
  }
  v21 += 8;
LABEL_41:
  if ( !v21 )
    return 0;
  if ( !(unsigned int)_acrt_MultiByteToWideChar(v12, 1, a4, (unsigned int)v8, v21, v17) )
    goto LABEL_63;
  v23 = _acrt_MultiByteToWideChar(v12, 9, String, (unsigned int)v11, 0, 0);
  v24 = v23;
  if ( !v23 )
    goto LABEL_63;
  v25 = (2LL * v23 + 16) & -(__int64)(2LL * v23 < (unsigned __int64)(2LL * v23 + 16));
  if ( !v25 )
    goto LABEL_63;
  if ( v25 > 0x400 )
  {
    v29 = (WCHAR *)malloc_base(v25);
    v28 = v29;
    if ( !v29 )
      goto LABEL_53;
    *(_DWORD *)v29 = 56797;
  }
  else
  {
    v26 = v25 + 15;
    if ( v25 + 15 < v25 )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
    v28 = (const WCHAR *)&v35;
    if ( v34 == (_BYTE *)-80LL )
      goto LABEL_63;
    v35 = 52428;
  }
  v28 += 8;
LABEL_53:
  if ( !v28 )
  {
LABEL_63:
    v31 = (WCHAR *)(v21 - 8);
    v32 = *((_DWORD *)v21 - 4) == 56797;
LABEL_64:
    if ( v32 )
      free_base(v31);
    return 0;
  }
  v30 = (WCHAR *)(v28 - 8);
  if ( !(unsigned int)_acrt_MultiByteToWideChar(v12, 1, v36, (unsigned int)v11, v28, v24) )
  {
    if ( *(_DWORD *)v30 == 56797 )
      free_base(v30);
    v31 = (WCHAR *)(v21 - 8);
    v32 = *((_DWORD *)v21 - 4) == 56797;
    goto LABEL_64;
  }
  v33 = _acrt_CompareStringEx(v37, v35, v21, v17, v28, v24, 0, 0, 0);
  if ( *(_DWORD *)v30 == 56797 )
    free_base(v30);
  if ( *((_DWORD *)v21 - 4) == 56797 )
    free_base((void *)(v21 - 8));
  return v33;
}

```

## disassembly

```asm
0x18001ab7c  push    rbp
0x18001ab7e  push    rbx
0x18001ab7f  push    rsi
0x18001ab80  push    rdi
0x18001ab81  push    r12
0x18001ab83  push    r13
0x18001ab85  push    r14
0x18001ab87  push    r15
0x18001ab89  sub     rsp, 98h
0x18001ab90  lea     rbp, [rsp+50h]
0x18001ab95  mov     rax, cs:__security_cookie
0x18001ab9c  xor     rax, rbp
0x18001ab9f  mov     [rbp+80h+var_50], rax
0x18001aba3  movsxd  rdi, [rbp+80h+arg_20]
0x18001abaa  xor     r13d, r13d
0x18001abad  mov     r12, [rbp+80h+String]
0x18001abb4  mov     r14, r9
0x18001abb7  mov     [rbp+80h+var_80], r8d
0x18001abbb  mov     rbx, rcx
0x18001abbe  mov     [rbp+80h+var_70], rdx
0x18001abc2  mov     [rbp+80h+var_78], r12
0x18001abc6  test    edi, edi
0x18001abc8  jle     short loc_18001ABDA
0x18001abca  mov     rdx, rdi; Count
0x18001abcd  mov     rcx, r9; String
0x18001abd0  call    __strncnt
0x18001abd5  mov     rdi, rax
0x18001abd8  jmp     short loc_18001ABE3
0x18001abda  cmp     edi, 0FFFFFFFFh
0x18001abdd  jl      loc_18001AEE5
0x18001abe3  movsxd  rsi, [rbp+80h+arg_30]
0x18001abea  test    esi, esi
0x18001abec  jle     short loc_18001ABFE
0x18001abee  mov     rdx, rsi; Count
0x18001abf1  mov     rcx, r12; String
0x18001abf4  call    __strncnt
0x18001abf9  mov     rsi, rax
0x18001abfc  jmp     short loc_18001AC07
0x18001abfe  cmp     esi, 0FFFFFFFFh
0x18001ac01  jl      loc_18001AEE5
0x18001ac07  mov     r15d, [rbp+80h+CodePage]
0x18001ac0e  test    r15d, r15d
0x18001ac11  jnz     short loc_18001AC1A
0x18001ac13  mov     rax, [rbx]
0x18001ac16  mov     r15d, [rax+0Ch]
0x18001ac1a  test    edi, edi
0x18001ac1c  jz      short loc_18001AC26
0x18001ac1e  test    esi, esi
0x18001ac20  jnz     loc_18001ACD8
0x18001ac26  xor     eax, eax
0x18001ac28  xorps   xmm0, xmm0
0x18001ac2b  mov     dword ptr [rbp+80h+CPInfo.LeadByte+0Ah], eax
0x18001ac2e  movups  xmmword ptr [rbp+80h+CPInfo.MaxCharSize], xmm0
0x18001ac32  cmp     edi, esi
0x18001ac34  jz      loc_18001AF04
0x18001ac3a  cmp     esi, 1
0x18001ac3d  jg      loc_18001ACCE
0x18001ac43  cmp     edi, 1
0x18001ac46  jg      short loc_18001AC90
0x18001ac48  lea     rdx, [rbp+80h+CPInfo]; lpCPInfo
0x18001ac4c  mov     ecx, r15d; CodePage
0x18001ac4f  call    cs:__imp_GetCPInfo
0x18001ac55  test    eax, eax
0x18001ac57  jz      loc_18001AEE5
0x18001ac5d  test    edi, edi
0x18001ac5f  jle     short loc_18001AC9A
0x18001ac61  cmp     [rbp+80h+CPInfo.MaxCharSize], 2
0x18001ac65  jb      short loc_18001AC90
0x18001ac67  lea     rax, [rbp+80h+CPInfo.LeadByte]
0x18001ac6b  cmp     [rbp+80h+CPInfo.LeadByte], r13b
0x18001ac6f  jz      short loc_18001AC90
0x18001ac71  cmp     [rax+1], r13b
0x18001ac75  jz      short loc_18001AC90
0x18001ac77  mov     cl, [r14]
0x18001ac7a  cmp     cl, [rax]
0x18001ac7c  jb      short loc_18001AC87
0x18001ac7e  cmp     cl, [rax+1]
0x18001ac81  jbe     loc_18001AF04
0x18001ac87  add     rax, 2
0x18001ac8b  cmp     [rax], r13b
0x18001ac8e  jnz     short loc_18001AC71
0x18001ac90  mov     eax, 3
0x18001ac95  jmp     loc_18001AEE7
0x18001ac9a  test    esi, esi
0x18001ac9c  jle     short loc_18001ACD8
0x18001ac9e  cmp     [rbp+80h+CPInfo.MaxCharSize], 2
0x18001aca2  jb      short loc_18001ACCE
0x18001aca4  lea     rax, [rbp+80h+CPInfo.LeadByte]
0x18001aca8  cmp     [rbp+80h+CPInfo.LeadByte], r13b
0x18001acac  jz      short loc_18001ACCE
0x18001acae  cmp     [rax+1], r13b
0x18001acb2  jz      short loc_18001ACCE
0x18001acb4  mov     cl, [r12]
0x18001acb8  cmp     cl, [rax]
0x18001acba  jb      short loc_18001ACC5
0x18001acbc  cmp     cl, [rax+1]
0x18001acbf  jbe     loc_18001AF04
0x18001acc5  add     rax, 2
0x18001acc9  cmp     [rax], r13b
0x18001accc  jnz     short loc_18001ACAE
0x18001acce  mov     eax, 1
0x18001acd3  jmp     loc_18001AEE7
0x18001acd8  mov     [rsp+0D0h+var_A8], r13d
0x18001acdd  mov     r9d, edi
0x18001ace0  mov     r8, r14
0x18001ace3  mov     [rsp+0D0h+var_B0], r13
0x18001ace8  mov     edx, 9
0x18001aced  mov     ecx, r15d
0x18001acf0  call    __acrt_MultiByteToWideChar
0x18001acf5  movsxd  r13, eax
0x18001acf8  test    eax, eax
0x18001acfa  jz      loc_18001AEE5
0x18001ad00  mov     rdx, r13
0x18001ad03  add     rdx, rdx
0x18001ad06  lea     rcx, [rdx+10h]
0x18001ad0a  cmp     rdx, rcx
0x18001ad0d  sbb     rdx, rdx
0x18001ad10  and     rdx, rcx
0x18001ad13  jz      loc_18001AEE5
0x18001ad19  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001ad23  cmp     rdx, 400h
0x18001ad2a  ja      short loc_18001AD5A
0x18001ad2c  lea     rax, [rdx+0Fh]
0x18001ad30  cmp     rax, rdx
0x18001ad33  ja      short loc_18001AD38
0x18001ad35  mov     rax, rcx
0x18001ad38  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001ad3c  call    _alloca_probe
0x18001ad41  sub     rsp, rax
0x18001ad44  lea     rbx, [rsp+0D0h+var_80]
0x18001ad49  test    rbx, rbx
0x18001ad4c  jz      loc_18001AEE5
0x18001ad52  mov     dword ptr [rbx], 0CCCCh
0x18001ad58  jmp     short loc_18001AD70
0x18001ad5a  mov     rcx, rdx; Size
0x18001ad5d  call    _malloc_base
0x18001ad62  mov     rbx, rax
0x18001ad65  test    rax, rax
0x18001ad68  jz      short loc_18001AD74
0x18001ad6a  mov     dword ptr [rax], 0DDDDh
0x18001ad70  add     rbx, 10h
0x18001ad74  test    rbx, rbx
0x18001ad77  jz      loc_18001AEE5
0x18001ad7d  mov     [rsp+0D0h+var_A8], r13d
0x18001ad82  mov     r9d, edi
0x18001ad85  mov     r8, r14
0x18001ad88  mov     [rsp+0D0h+var_B0], rbx
0x18001ad8d  mov     edx, 1
0x18001ad92  mov     ecx, r15d
0x18001ad95  call    __acrt_MultiByteToWideChar
0x18001ad9a  test    eax, eax
0x18001ad9c  jz      loc_18001AED4
0x18001ada2  and     [rsp+0D0h+var_A8], 0
0x18001ada7  mov     r9d, esi
0x18001adaa  and     [rsp+0D0h+var_B0], 0
0x18001adb0  mov     r8, r12
0x18001adb3  mov     edx, 9
0x18001adb8  mov     ecx, r15d
0x18001adbb  call    __acrt_MultiByteToWideChar
0x18001adc0  movsxd  r12, eax
0x18001adc3  test    eax, eax
0x18001adc5  jz      loc_18001AED4
0x18001adcb  mov     rcx, r12
0x18001adce  add     rcx, rcx
0x18001add1  lea     rax, [rcx+10h]
0x18001add5  cmp     rcx, rax
0x18001add8  sbb     rcx, rcx
0x18001addb  and     rcx, rax; Size
0x18001adde  jz      loc_18001AED4
0x18001ade4  cmp     rcx, 400h
0x18001adeb  ja      short loc_18001AE22
0x18001aded  lea     rax, [rcx+0Fh]
0x18001adf1  cmp     rax, rcx
0x18001adf4  ja      short loc_18001AE00
0x18001adf6  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001ae00  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001ae04  call    _alloca_probe
0x18001ae09  sub     rsp, rax
0x18001ae0c  lea     rdi, [rsp+0D0h+var_80]
0x18001ae11  test    rdi, rdi
0x18001ae14  jz      loc_18001AED4
0x18001ae1a  mov     dword ptr [rdi], 0CCCCh
0x18001ae20  jmp     short loc_18001AE35
0x18001ae22  call    _malloc_base
0x18001ae27  mov     rdi, rax
0x18001ae2a  test    rax, rax
0x18001ae2d  jz      short loc_18001AE39
0x18001ae2f  mov     dword ptr [rax], 0DDDDh
0x18001ae35  add     rdi, 10h
0x18001ae39  test    rdi, rdi
0x18001ae3c  jz      loc_18001AED4
0x18001ae42  mov     r8, [rbp+80h+var_78]
0x18001ae46  lea     r14, [rdi-10h]
0x18001ae4a  mov     [rsp+0D0h+var_A8], r12d
0x18001ae4f  mov     r9d, esi
0x18001ae52  mov     edx, 1
0x18001ae57  mov     [rsp+0D0h+var_B0], rdi
0x18001ae5c  mov     ecx, r15d
0x18001ae5f  call    __acrt_MultiByteToWideChar
0x18001ae64  xor     ecx, ecx
0x18001ae66  test    eax, eax
0x18001ae68  jnz     short loc_18001AE84
0x18001ae6a  mov     edi, 0DDDDh
0x18001ae6f  cmp     [r14], edi
0x18001ae72  jnz     short loc_18001AE7C
0x18001ae74  mov     rcx, r14; Block
0x18001ae77  call    _free_base
0x18001ae7c  lea     rcx, [rbx-10h]
0x18001ae80  cmp     [rcx], edi
0x18001ae82  jmp     short loc_18001AEDE
0x18001ae84  mov     edx, [rbp+80h+var_80]
0x18001ae87  mov     r9d, r13d
0x18001ae8a  mov     [rsp+0D0h+var_90], rcx
0x18001ae8f  mov     r8, rbx
0x18001ae92  mov     [rsp+0D0h+var_98], rcx
0x18001ae97  mov     [rsp+0D0h+var_A0], rcx
0x18001ae9c  mov     rcx, [rbp+80h+var_70]
0x18001aea0  mov     [rsp+0D0h+var_A8], r12d
0x18001aea5  mov     [rsp+0D0h+var_B0], rdi
0x18001aeaa  call    __acrt_CompareStringEx
0x18001aeaf  mov     esi, 0DDDDh
0x18001aeb4  mov     edi, eax
0x18001aeb6  cmp     [r14], esi
0x18001aeb9  jnz     short loc_18001AEC3
0x18001aebb  mov     rcx, r14; Block
0x18001aebe  call    _free_base
0x18001aec3  lea     rcx, [rbx-10h]; Block
0x18001aec7  cmp     [rcx], esi
0x18001aec9  jnz     short loc_18001AED0
0x18001aecb  call    _free_base
0x18001aed0  mov     eax, edi
0x18001aed2  jmp     short loc_18001AEE7
0x18001aed4  lea     rcx, [rbx-10h]; Block
0x18001aed8  cmp     dword ptr [rcx], 0DDDDh
0x18001aede  jnz     short loc_18001AEE5
0x18001aee0  call    _free_base
0x18001aee5  xor     eax, eax
0x18001aee7  mov     rcx, [rbp+80h+var_50]
0x18001aeeb  xor     rcx, rbp; StackCookie
0x18001aeee  call    __security_check_cookie
0x18001aef3  lea     rsp, [rbp+48h]
0x18001aef7  pop     r15
0x18001aef9  pop     r14
0x18001aefb  pop     r13
0x18001aefd  pop     r12
0x18001aeff  pop     rdi
0x18001af00  pop     rsi
0x18001af01  pop     rbx
0x18001af02  pop     rbp
0x18001af03  retn
0x18001af04  mov     eax, 2
0x18001af09  jmp     short loc_18001AEE7
```
