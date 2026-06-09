# GetPackageFamilyAndPraid(ushort const *,ushort * *,ushort * *)

- ea: `0x180026090`
- end: `0x1800263db`
- name: `?GetPackageFamilyAndPraid@@YAJPEBGPEAPEAG1@Z`
- size: `843`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025e20`
- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x180026090`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800261b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800262a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800261b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800262a0`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800260e0`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800260e0`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyAndPraid(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  LONG v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r14
  int v10; // esi
  unsigned __int16 *v12; // rax
  int v13; // ebp
  WCHAR *v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int16 *v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // rbx
  unsigned __int16 *v20; // rax
  WCHAR *v21; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int16 *v23; // r8
  __int64 v24; // r9
  unsigned __int64 v25; // rbx
  int packageRelativeApplicationId; // [rsp+20h] [rbp-188h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+30h] [rbp-178h] BYREF
  UINT32 packageFamilyNameLength[3]; // [rsp+34h] [rbp-174h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-168h] BYREF
  WCHAR v30[72]; // [rsp+D0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  packageFamilyNameLength[0] = 65;
  packageRelativeApplicationIdLength = 66;
  v5 = ParseApplicationUserModelId(
         a1,
         packageFamilyNameLength,
         packageFamilyName,
         &packageRelativeApplicationIdLength,
         v30);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( packageFamilyName[v8] );
    v9 = v8 + 1;
    *a2 = 0;
    if ( v8 + 1 >= v8 && is_mul_ok(v9, 2u) )
    {
      v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
      *a2 = v12;
      v13 = -2147024882;
      v10 = -2147024882;
      if ( v12 )
        v10 = 0;
      if ( v10 >= 0 )
      {
        if ( (v12 || v8 == -1) && v9 <= 0x7FFFFFFF )
        {
          if ( v8 >= 0x7FFFFFFF )
          {
            if ( v8 != -1 )
              *v12 = 0;
          }
          else
          {
            v14 = packageFamilyName;
            v15 = v8 + 1;
            v16 = v12;
            v17 = 0;
            while ( v8 )
            {
              if ( !*v14 )
              {
                if ( !v15 )
                {
LABEL_18:
                  *(v16 - 1) = 0;
                  goto LABEL_21;
                }
                break;
              }
              *v16++ = *v14++;
              --v8;
              ++v17;
              if ( !--v15 )
                goto LABEL_18;
            }
            v18 = v9 - v17;
            *v16 = 0;
            if ( v18 > 1 && 2 * v18 > 2 )
              memset_0(&v12[v17 + 1], 0, 2 * v18 - 2);
          }
        }
        else
        {
          *v12 = 0;
        }
        do
LABEL_21:
          ++v7;
        while ( v30[v7] );
        v19 = v7 + 1;
        *a3 = 0;
        if ( v7 + 1 < v7 || !is_mul_ok(v19, 2u) )
        {
          v13 = -2147024362;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EF,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
            (const char *)(unsigned int)v13,
            packageRelativeApplicationId);
          return (unsigned int)v13;
        }
        v20 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
        *a3 = v20;
        if ( v20 )
          v13 = 0;
        if ( v13 < 0 )
          goto LABEL_25;
        if ( !v20 && v7 != -1 || v19 > 0x7FFFFFFF )
          goto LABEL_52;
        if ( v7 < 0x7FFFFFFF )
        {
          v21 = v30;
          v22 = v7 + 1;
          v23 = v20;
          v24 = 0;
          while ( v7 )
          {
            if ( !*v21 )
            {
              if ( !v22 )
              {
LABEL_36:
                *(v23 - 1) = 0;
                return 0;
              }
              break;
            }
            *v23++ = *v21++;
            --v7;
            ++v24;
            if ( !--v22 )
              goto LABEL_36;
          }
          v25 = v19 - v24;
          *v23 = 0;
          if ( v25 > 1 && 2 * v25 > 2 )
            memset_0(&v20[v24 + 1], 0, 2 * v25 - 2);
          return 0;
        }
        if ( v7 != -1 )
LABEL_52:
          *v20 = 0;
        return 0;
      }
    }
    else
    {
      v10 = -2147024362;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
      (const char *)(unsigned int)v10,
      packageRelativeApplicationId);
    return (unsigned int)v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
    (const char *)(unsigned int)v5,
    packageRelativeApplicationId);
  return v6;
}

```

## disassembly

```asm
0x180026090  push    rbx
0x180026092  push    rsi
0x180026093  push    r15
0x180026095  sub     rsp, 190h
0x18002609c  mov     rax, cs:__security_cookie
0x1800260a3  xor     rax, rsp
0x1800260a6  mov     [rsp+1A8h+var_48], rax
0x1800260ae  mov     r15, r8
0x1800260b1  mov     [rsp+1A8h+packageFamilyNameLength], 41h ; 'A'
0x1800260b9  mov     rsi, rdx
0x1800260bc  mov     [rsp+1A8h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800260c4  lea     rax, [rsp+1A8h+var_D8]
0x1800260cc  lea     r8, [rsp+1A8h+packageFamilyName]; packageFamilyName
0x1800260d1  mov     qword ptr [rsp+1A8h+packageRelativeApplicationId], rax; int
0x1800260d6  lea     rdx, [rsp+1A8h+packageFamilyNameLength]; packageFamilyNameLength
0x1800260db  lea     r9, [rsp+1A8h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800260e0  call    cs:__imp_ParseApplicationUserModelId
0x1800260e6  mov     ebx, eax
0x1800260e8  test    eax, eax
0x1800260ea  js      loc_180026335
0x1800260f0  mov     [rsp+1A8h+var_28], rdi
0x1800260f8  lea     rax, [rsp+1A8h+packageFamilyName]
0x1800260fd  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180026104  mov     [rsp+1A8h+var_30], r12
0x18002610c  mov     rbx, rdi
0x18002610f  mov     [rsp+1A8h+var_38], r14
0x180026117  nop     word ptr [rax+rax+00000000h]
0x180026120  inc     rbx
0x180026123  cmp     word ptr [rax+rbx*2], 0
0x180026128  jnz     short loc_180026120
0x18002612a  xor     r12d, r12d
0x18002612d  mov     [rsp+1A8h+var_20], rbp
0x180026135  lea     r14, [rbx+1]
0x180026139  mov     [rsi], r12
0x18002613c  cmp     r14, rbx
0x18002613f  jnb     short loc_1800261A0
0x180026141  mov     esi, 80070216h
0x180026146  mov     rcx, [rsp+1A8h]; this
0x18002614e  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180026155  mov     r9d, esi; char *
0x180026158  mov     edx, 1EEh; void *
0x18002615d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026162  mov     eax, esi
0x180026164  mov     rbp, [rsp+1A8h+var_20]
0x18002616c  mov     rdi, [rsp+1A8h+var_28]
0x180026174  mov     r12, [rsp+1A8h+var_30]
0x18002617c  mov     r14, [rsp+1A8h+var_38]
0x180026184  mov     rcx, [rsp+1A8h+var_48]
0x18002618c  xor     rcx, rsp; StackCookie
0x18002618f  call    __security_check_cookie
0x180026194  add     rsp, 190h
0x18002619b  pop     r15
0x18002619d  pop     rsi
0x18002619e  pop     rbx
0x18002619f  retn
0x1800261a0  mov     eax, 2
0x1800261a5  mul     r14
0x1800261a8  test    rdx, rdx
0x1800261ab  jnz     short loc_180026141
0x1800261ad  mov     rcx, rax; cb
0x1800261b0  call    cs:__imp_CoTaskMemAlloc
0x1800261b6  mov     [rsi], rax
0x1800261b9  test    rax, rax
0x1800261bc  mov     ebp, 8007000Eh
0x1800261c1  mov     r10, rax
0x1800261c4  mov     esi, ebp
0x1800261c6  cmovnz  esi, r12d
0x1800261ca  test    esi, esi
0x1800261cc  js      loc_180026146
0x1800261d2  test    rax, rax
0x1800261d5  jz      loc_18002639B
0x1800261db  cmp     r14, 7FFFFFFFh
0x1800261e2  ja      loc_1800263A4
0x1800261e8  cmp     rbx, 7FFFFFFFh
0x1800261ef  jnb     loc_1800263AD
0x1800261f5  test    r14, r14
0x1800261f8  jz      short loc_18002624A
0x1800261fa  lea     rcx, [rsp+1A8h+packageFamilyName]
0x1800261ff  mov     rdx, r14
0x180026202  mov     r8, r10
0x180026205  mov     r9, r12
0x180026208  test    rbx, rbx
0x18002620b  jz      short loc_180026239
0x18002620d  movzx   eax, word ptr [rcx]
0x180026210  test    ax, ax
0x180026213  jz      short loc_180026234
0x180026215  mov     [r8], ax
0x180026219  add     rcx, 2
0x18002621d  add     r8, 2
0x180026221  dec     rbx
0x180026224  inc     r9
0x180026227  sub     rdx, 1
0x18002622b  jnz     short loc_180026208
0x18002622d  mov     [r8-2], r12w
0x180026232  jmp     short loc_18002624A
0x180026234  test    rdx, rdx
0x180026237  jz      short loc_18002622D
0x180026239  sub     r14, r9
0x18002623c  mov     [r8], r12w
0x180026240  cmp     r14, 1
0x180026244  ja      loc_180026358
0x18002624a  lea     rcx, [rsp+1A8h+var_D8]
0x180026252  inc     rdi
0x180026255  cmp     [rcx+rdi*2], r12w
0x18002625a  jnz     short loc_180026252
0x18002625c  lea     rbx, [rdi+1]
0x180026260  mov     [r15], r12
0x180026263  cmp     rbx, rdi
0x180026266  jb      short loc_180026275
0x180026268  mov     eax, 2
0x18002626d  mul     rbx
0x180026270  test    rdx, rdx
0x180026273  jz      short loc_18002629D
0x180026275  mov     ebp, 80070216h
0x18002627a  mov     rcx, [rsp+1A8h]; this
0x180026282  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180026289  mov     r9d, ebp; char *
0x18002628c  mov     edx, 1EFh; void *
0x180026291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026296  mov     eax, ebp
0x180026298  jmp     loc_180026164
0x18002629d  mov     rcx, rax; cb
0x1800262a0  call    cs:__imp_CoTaskMemAlloc
0x1800262a6  test    rax, rax
0x1800262a9  mov     [r15], rax
0x1800262ac  mov     r10, rax
0x1800262af  cmovnz  ebp, r12d
0x1800262b3  test    ebp, ebp
0x1800262b5  js      short loc_18002627A
0x1800262b7  test    rax, rax
0x1800262ba  jz      loc_1800263BF
0x1800262c0  cmp     rbx, 7FFFFFFFh
0x1800262c7  ja      loc_1800263D2
0x1800262cd  cmp     rdi, 7FFFFFFFh
0x1800262d4  jnb     loc_1800263C9
0x1800262da  test    rbx, rbx
0x1800262dd  jz      short loc_18002632E
0x1800262df  lea     rcx, [rsp+1A8h+var_D8]
0x1800262e7  mov     rdx, rbx
0x1800262ea  mov     r8, r10
0x1800262ed  mov     r9, r12
0x1800262f0  test    rdi, rdi
0x1800262f3  jz      short loc_180026321
0x1800262f5  movzx   eax, word ptr [rcx]
0x1800262f8  test    ax, ax
0x1800262fb  jz      short loc_18002631C
0x1800262fd  mov     [r8], ax
0x180026301  add     rcx, 2
0x180026305  add     r8, 2
0x180026309  dec     rdi
0x18002630c  inc     r9
0x18002630f  sub     rdx, 1
0x180026313  jnz     short loc_1800262F0
0x180026315  mov     [r8-2], r12w
0x18002631a  jmp     short loc_18002632E
0x18002631c  test    rdx, rdx
0x18002631f  jz      short loc_180026315
0x180026321  sub     rbx, r9
0x180026324  mov     [r8], r12w
0x180026328  cmp     rbx, 1
0x18002632c  ja      short loc_18002637D
0x18002632e  xor     eax, eax
0x180026330  jmp     loc_180026164
0x180026335  mov     rcx, [rsp+1A8h]; this
0x18002633d  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180026344  mov     r9d, ebx; char *
0x180026347  mov     edx, 1EDh; void *
0x18002634c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026351  mov     eax, ebx
0x180026353  jmp     loc_180026184
0x180026358  lea     r8, [r14+r14]
0x18002635c  cmp     r8, 2
0x180026360  jbe     loc_18002624A
0x180026366  inc     r9
0x180026369  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002636d  xor     edx, edx; Val
0x18002636f  lea     rcx, [r10+r9*2]; void *
0x180026373  call    memset_0
0x180026378  jmp     loc_18002624A
0x18002637d  lea     r8, [rbx+rbx]
0x180026381  cmp     r8, 2
0x180026385  jbe     short loc_18002632E
0x180026387  inc     r9
0x18002638a  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002638e  xor     edx, edx; Val
0x180026390  lea     rcx, [r10+r9*2]; void *
0x180026394  call    memset_0
0x180026399  jmp     short loc_18002632E
0x18002639b  test    r14, r14
0x18002639e  jz      loc_1800261DB
0x1800263a4  mov     [rax], r12w
0x1800263a8  jmp     loc_18002624A
0x1800263ad  test    r14, r14
0x1800263b0  jz      loc_18002624A
0x1800263b6  mov     [rax], r12w
0x1800263ba  jmp     loc_18002624A
0x1800263bf  test    rbx, rbx
0x1800263c2  jnz     short loc_1800263D2
0x1800263c4  jmp     loc_1800262C0
0x1800263c9  test    rbx, rbx
0x1800263cc  jz      loc_18002632E
0x1800263d2  mov     [rax], r12w
0x1800263d6  jmp     loc_18002632E
```
