# Execution::ActivationManagerShim::GetPsmKey(ushort const *,ushort const *,_GUID const *,ushort * *)

- ea: `0x18000abf0`
- end: `0x18000ae68`
- name: `?GetPsmKey@ActivationManagerShim@Execution@@CAJPEBG0PEBU_GUID@@PEAPEAG@Z`
- size: `632`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006bcf8`
- `0x180071540`

## callees

- `0x18000abf0`
- `0x18000b5c0`
- `0x180044514`
- `0x1800445ac`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad5e`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000acd1`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18000acd1`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18000ac99`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18000ac99`

## pseudocode

```c
int __fastcall Execution::ActivationManagerShim::GetPsmKey(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned __int16 **a4)
{
  unsigned int v6; // eax
  int Key; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rsi
  int v10; // edi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
  __int64 v16; // r9
  unsigned __int64 v17; // rsi
  unsigned int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+34h] [rbp-CCh] BYREF
  int v21[6]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR v22[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  __int128 v24; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int128 v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+C0h] [rbp-40h]
  int v30; // [rsp+D0h] [rbp-30h]
  WCHAR packageFamilyName[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+F0h] [rbp-10h]
  __int128 v33; // [rsp+100h] [rbp+0h]
  __int128 v34; // [rsp+110h] [rbp+10h]
  __int128 v35; // [rsp+120h] [rbp+20h]
  __int128 v36; // [rsp+130h] [rbp+30h]
  __int128 v37; // [rsp+140h] [rbp+40h]
  __int128 v38; // [rsp+150h] [rbp+50h]
  __int16 v39; // [rsp+160h] [rbp+60h]
  _WORD v40[232]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  packageRelativeApplicationIdLength = 66;
  packageFamilyNameLength = 65;
  v30 = 0;
  v39 = 0;
  *a4 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  *(_OWORD *)packageFamilyName = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v6 = ParseApplicationUserModelId(
         a1,
         &packageFamilyNameLength,
         packageFamilyName,
         &packageRelativeApplicationIdLength,
         v22);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x705,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
             (const char *)v6,
             packageRelativeApplicationId);
  memset_0(v40, 0, sizeof(v40));
  v21[0] = 464;
  Key = PsmCreateKey(a2, v22, v40, v21);
  if ( Key >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v40[v8] );
    v9 = v8 + 1;
    *a4 = 0;
    if ( v8 + 1 < v8 || !is_mul_ok(v9, 2u) )
    {
      v10 = -2147024362;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x712,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v10,
        packageRelativeApplicationId);
      return v10;
    }
    v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
    *a4 = v12;
    v10 = -2147024882;
    if ( v12 )
      v10 = 0;
    if ( v10 < 0 )
      goto LABEL_8;
    if ( !v12 && v8 != -1 || v9 > 0x7FFFFFFF )
      goto LABEL_30;
    if ( v8 < 0x7FFFFFFF )
    {
      v13 = v40;
      v14 = v8 + 1;
      v15 = v12;
      v16 = 0;
      while ( v8 )
      {
        if ( !*v13 )
        {
          if ( !v14 )
          {
LABEL_19:
            *(v15 - 1) = 0;
            return 0;
          }
          break;
        }
        *v15++ = *v13++;
        --v8;
        ++v16;
        if ( !--v14 )
          goto LABEL_19;
      }
      v17 = v9 - v16;
      *v15 = 0;
      if ( v17 > 1 && 2 * v17 > 2 )
        memset_0(&v12[v16 + 1], 0, 2 * v17 - 2);
      return 0;
    }
    if ( v8 != -1 )
LABEL_30:
      *v12 = 0;
    return 0;
  }
  return wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x70F,
           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
           (const char *)(unsigned int)Key,
           packageRelativeApplicationId);
}

```

## disassembly

```asm
0x18000abf0  push    rbp
0x18000abf2  push    rbx
0x18000abf3  push    rdi
0x18000abf4  push    r14
0x18000abf6  lea     rbp, [rsp-258h]
0x18000abfe  sub     rsp, 358h
0x18000ac05  mov     rax, cs:__security_cookie
0x18000ac0c  xor     rax, rsp
0x18000ac0f  mov     [rbp+270h+var_30], rax
0x18000ac16  xorps   xmm0, xmm0
0x18000ac19  mov     [rsp+370h+packageRelativeApplicationIdLength], 42h ; 'B'
0x18000ac21  xor     eax, eax
0x18000ac23  mov     [rsp+370h+packageFamilyNameLength], 41h ; 'A'
0x18000ac2b  mov     [rbp+270h+var_2A0], eax
0x18000ac2e  lea     r8, [rbp+270h+packageFamilyName]; packageFamilyName
0x18000ac32  mov     [rbp+270h+var_210], ax
0x18000ac36  mov     rdi, r9
0x18000ac39  lea     rax, [rsp+370h+var_320]
0x18000ac3e  mov     rbx, rdx
0x18000ac41  xor     r14d, r14d
0x18000ac44  mov     qword ptr [rsp+370h+packageRelativeApplicationId], rax; int
0x18000ac49  mov     [r9], r14
0x18000ac4c  lea     rdx, [rsp+370h+packageFamilyNameLength]; packageFamilyNameLength
0x18000ac51  lea     r9, [rsp+370h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18000ac56  movups  xmmword ptr [rsp+370h+var_320], xmm0
0x18000ac5b  movups  [rsp+370h+var_310], xmm0
0x18000ac60  movups  [rsp+370h+var_300], xmm0
0x18000ac65  movups  [rbp+270h+var_2F0], xmm0
0x18000ac69  movups  [rbp+270h+var_2E0], xmm0
0x18000ac6d  movups  [rbp+270h+var_2D0], xmm0
0x18000ac71  movups  [rbp+270h+var_2C0], xmm0
0x18000ac75  movups  [rbp+270h+var_2B0], xmm0
0x18000ac79  movups  xmmword ptr [rbp+270h+packageFamilyName], xmm0
0x18000ac7d  movups  [rbp+270h+var_280], xmm0
0x18000ac81  movups  [rbp+270h+var_270], xmm0
0x18000ac85  movups  [rbp+270h+var_260], xmm0
0x18000ac89  movups  [rbp+270h+var_250], xmm0
0x18000ac8d  movups  [rbp+270h+var_240], xmm0
0x18000ac91  movups  [rbp+270h+var_230], xmm0
0x18000ac95  movups  [rbp+270h+var_220], xmm0
0x18000ac99  call    cs:__imp_ParseApplicationUserModelId
0x18000ac9f  test    eax, eax
0x18000aca1  jnz     loc_18000AE13
0x18000aca7  xor     edx, edx; Val
0x18000aca9  lea     rcx, [rbp+270h+var_200]; void *
0x18000acad  mov     r8d, 1D0h; Size
0x18000acb3  call    memset_0
0x18000acb8  lea     r9, [rsp+370h+var_338]
0x18000acbd  mov     [rsp+370h+var_338], 1D0h
0x18000acc5  lea     r8, [rbp+270h+var_200]
0x18000acc9  mov     rcx, rbx
0x18000accc  lea     rdx, [rsp+370h+var_320]
0x18000acd1  call    cs:__imp_PsmCreateKey
0x18000acd7  test    eax, eax
0x18000acd9  js      loc_18000AE33
0x18000acdf  mov     [rsp+370h+var_20], rsi
0x18000ace7  lea     rax, [rbp+270h+var_200]
0x18000aceb  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000acf2  inc     rbx
0x18000acf5  cmp     [rax+rbx*2], r14w
0x18000acfa  jnz     short loc_18000ACF2
0x18000acfc  lea     rsi, [rbx+1]
0x18000ad00  mov     [rdi], r14
0x18000ad03  cmp     rsi, rbx
0x18000ad06  jb      short loc_18000AD15
0x18000ad08  mov     eax, 2
0x18000ad0d  mul     rsi
0x18000ad10  test    rdx, rdx
0x18000ad13  jz      short loc_18000AD5B
0x18000ad15  mov     edi, 80070216h
0x18000ad1a  mov     rcx, [rbp+278h]; this
0x18000ad21  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ad28  mov     r9d, edi; char *
0x18000ad2b  mov     edx, 712h; void *
0x18000ad30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad35  mov     eax, edi
0x18000ad37  mov     rsi, [rsp+370h+var_20]
0x18000ad3f  mov     rcx, [rbp+270h+var_30]
0x18000ad46  xor     rcx, rsp; StackCookie
0x18000ad49  call    __security_check_cookie
0x18000ad4e  add     rsp, 358h
0x18000ad55  pop     r14
0x18000ad57  pop     rdi
0x18000ad58  pop     rbx
0x18000ad59  pop     rbp
0x18000ad5a  retn
0x18000ad5b  mov     rcx, rax; cb
0x18000ad5e  call    cs:__imp_CoTaskMemAlloc
0x18000ad64  mov     [rdi], rax
0x18000ad67  test    rax, rax
0x18000ad6a  mov     edi, 8007000Eh
0x18000ad6f  mov     r10, rax
0x18000ad72  cmovnz  edi, r14d
0x18000ad76  test    edi, edi
0x18000ad78  js      short loc_18000AD1A
0x18000ad7a  test    rax, rax
0x18000ad7d  jz      loc_18000AE53
0x18000ad83  cmp     rsi, 7FFFFFFFh
0x18000ad8a  ja      loc_18000AE62
0x18000ad90  cmp     rbx, 7FFFFFFFh
0x18000ad97  jnb     loc_18000AE5D
0x18000ad9d  test    rsi, rsi
0x18000ada0  jz      short loc_18000ADEE
0x18000ada2  lea     rcx, [rbp+270h+var_200]
0x18000ada6  mov     rdx, rsi
0x18000ada9  mov     r8, r10
0x18000adac  mov     r9, r14
0x18000adaf  nop
0x18000adb0  test    rbx, rbx
0x18000adb3  jz      short loc_18000ADE1
0x18000adb5  movzx   eax, word ptr [rcx]
0x18000adb8  test    ax, ax
0x18000adbb  jz      short loc_18000ADDC
0x18000adbd  mov     [r8], ax
0x18000adc1  add     rcx, 2
0x18000adc5  add     r8, 2
0x18000adc9  dec     rbx
0x18000adcc  inc     r9
0x18000adcf  sub     rdx, 1
0x18000add3  jnz     short loc_18000ADB0
0x18000add5  mov     [r8-2], r14w
0x18000adda  jmp     short loc_18000ADEE
0x18000addc  test    rdx, rdx
0x18000addf  jz      short loc_18000ADD5
0x18000ade1  sub     rsi, r9
0x18000ade4  mov     [r8], r14w
0x18000ade8  cmp     rsi, 1
0x18000adec  ja      short loc_18000ADF5
0x18000adee  xor     eax, eax
0x18000adf0  jmp     loc_18000AD37
0x18000adf5  lea     r8, [rsi+rsi]
0x18000adf9  cmp     r8, 2
0x18000adfd  jbe     short loc_18000ADEE
0x18000adff  inc     r9
0x18000ae02  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000ae06  xor     edx, edx; Val
0x18000ae08  lea     rcx, [r10+r9*2]; void *
0x18000ae0c  call    memset_0
0x18000ae11  jmp     short loc_18000ADEE
0x18000ae13  mov     rcx, [rbp+278h]; this
0x18000ae1a  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ae21  mov     r9d, eax; char *
0x18000ae24  mov     edx, 705h; void *
0x18000ae29  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ae2e  jmp     loc_18000AD3F
0x18000ae33  mov     rcx, [rbp+278h]; this
0x18000ae3a  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ae41  mov     r9d, eax; char *
0x18000ae44  mov     edx, 70Fh; void *
0x18000ae49  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000ae4e  jmp     loc_18000AD3F
0x18000ae53  test    rsi, rsi
0x18000ae56  jnz     short loc_18000AE62
0x18000ae58  jmp     loc_18000AD83
0x18000ae5d  test    rsi, rsi
0x18000ae60  jz      short loc_18000ADEE
0x18000ae62  mov     [rax], r14w
0x18000ae66  jmp     short loc_18000ADEE
```
