# AhcStoreSave

- ea: `0x14005344c`
- end: `0x140053915`
- name: `AhcStoreSave`
- size: `1225`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140024b68`
- `0x140027c9c`

## callees

- `0x140007ad0`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x14005344c`
- `0x14005391c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400535ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005377d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005377d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400534e7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005353e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400536e2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400534e7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005353e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400536e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005350b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053562`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005370a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005373b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005350b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140053562`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005370a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005373b`
- `ntoskrnl!RtlComputeCrc32` at `0x140053690`
- `ntoskrnl!RtlComputeCrc32` at `0x140053690`

## string_xrefs

- `0x1400538d4`: `Failed to write store entry header [%x]`
- `0x140053836`: `Failed to write header information to stream [%x]`
- `0x1400538ad`: `Failed to write key [%x]`

## pseudocode

```c
__int64 __fastcall AhcStoreSave(__int64 a1, _QWORD *a2)
{
  __int64 *v3; // rax
  unsigned __int16 *v4; // r13
  ULONG v5; // ebx
  __int64 v6; // rbp
  void **v7; // r12
  __int64 *v8; // r15
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r14
  __int64 v11; // rbx
  SIZE_T v12; // rbx
  KIRQL v13; // al
  POOL_TYPE v14; // ecx
  PVOID v15; // rax
  void *v16; // rbp
  KIRQL CurrentIrql; // al
  POOL_TYPE v18; // ecx
  PVOID PoolWithTag; // rax
  size_t v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  unsigned __int64 v28; // rbp
  unsigned __int64 v29; // rcx
  ULONG v30; // edx
  SIZE_T v31; // r15
  unsigned __int64 v32; // rsi
  __int64 v33; // rbx
  void *v34; // r14
  SIZE_T v35; // rbx
  KIRQL v36; // al
  POOL_TYPE v37; // ecx
  PVOID v38; // rax
  void *v39; // rsi
  PVOID v40; // rax
  size_t v41; // r8
  char *v42; // rcx
  __int64 v43; // rax
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rax
  const char *v47; // r9
  __int64 v48; // r8
  int v50; // [rsp+30h] [rbp-58h]
  void *Src; // [rsp+38h] [rbp-50h]
  size_t Size; // [rsp+40h] [rbp-48h]
  __int64 *v53; // [rsp+48h] [rbp-40h]
  ULONG v55; // [rsp+A0h] [rbp+18h]
  ULONG v56; // [rsp+A8h] [rbp+20h]

  v50 = 0;
  v3 = (__int64 *)(a1 + 104);
  v4 = *(unsigned __int16 **)(a1 + 104);
  v5 = 0;
  v55 = 0;
  v6 = a1;
  v7 = (void **)(a2 + 5);
  v56 = 0;
  v53 = (__int64 *)(a1 + 104);
  while ( 1 )
  {
    v8 = a2 + 5;
    if ( v4 == (unsigned __int16 *)v3 )
      return 0;
    v9 = a2[4];
    v10 = v9 + 12;
    if ( v9 + 12 < v9 )
    {
      v26 = -1073741811;
      v27 = -1073741811;
      goto LABEL_61;
    }
    if ( v10 > a2[2] )
    {
      v11 = a2[3] - 1LL;
      if ( v11 + v10 < v10 )
        goto LABEL_58;
      v8 = a2 + 5;
      v12 = (v11 + v10) & ~v11;
      Src = (void *)a2[5];
      if ( Src )
      {
        Size = a2[1];
        CurrentIrql = KeGetCurrentIrql();
        v18 = 512;
        if ( CurrentIrql != 2 )
          v18 = PagedPool;
        PoolWithTag = ExAllocatePoolWithTag(v18, v12, 0x7274534Du);
        v16 = PoolWithTag;
        if ( !PoolWithTag )
        {
LABEL_46:
          v27 = -1073741801;
          goto LABEL_59;
        }
        memset(PoolWithTag, 0, v12);
        v20 = v12;
        if ( Size < v12 )
          v20 = Size;
        memmove(v16, Src, v20);
        ExFreePoolWithTag(Src, 0x7274534Du);
      }
      else
      {
        v13 = KeGetCurrentIrql();
        v14 = 512;
        if ( v13 != 2 )
          v14 = PagedPool;
        v15 = ExAllocatePoolWithTag(v14, v12, 0x7274534Du);
        v16 = v15;
        if ( !v15 )
          goto LABEL_46;
        memset(v15, 0, v12);
      }
      *v8 = (__int64)v16;
      v6 = a1;
      a2[2] = v12;
      v5 = v55;
    }
    v21 = *v8;
    v22 = a2[4];
    *(_DWORD *)(v21 + v22) = v50;
    *(_DWORD *)(v21 + v22 + 4) = v56;
    *(_DWORD *)(v21 + v22 + 8) = v5;
    v23 = a2[4];
    v24 = v23 + 12;
    if ( v23 + 12 < v23 )
    {
      a2[4] = -1;
LABEL_58:
      v27 = -1073741675;
LABEL_59:
      v26 = v27;
LABEL_61:
      v47 = "Failed to write store entry header [%x]";
      v48 = 1364;
      goto LABEL_62;
    }
    a2[4] = v24;
    v25 = a2[1];
    if ( v25 <= v24 )
      v25 = v24;
    a2[1] = v25;
    v26 = AhcpStoreKeySave(v4 + 12, a2);
    v27 = v26;
    if ( v26 < 0 )
    {
      v47 = "Failed to write key [%x]";
      v48 = 1375;
      goto LABEL_62;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(v6 + 160))(*((_QWORD *)v4 + 5), a2);
    v27 = v26;
    if ( v26 < 0 )
    {
      v47 = "Failed to save item [%x]";
      v48 = 1382;
      goto LABEL_62;
    }
    v28 = a2[4];
    if ( v28 - v9 - 12 > 0xFFFFFFFF )
    {
      AslLogCallPrintf(1, "AhcStoreSave", 1394, "Incorrect stream buffer size");
      return (unsigned int)-1073741811;
    }
    v5 = v28 - v9 - 12;
    v29 = v10 + v5;
    v55 = v5;
    if ( v29 < v10 || v29 > a2[1] )
    {
      v27 = -1073741811;
      AslLogCallPrintf(1, "AhcStoreSave", 1406, "Failed to calculate checksum [%x]", -1073741811);
      return v27;
    }
    v30 = RtlComputeCrc32(0, (PUCHAR)*v7 + v10, v5);
    v56 = v30;
    v31 = a2[1];
    if ( v9 > v31 )
    {
      v26 = -1073741811;
      v47 = "Failed to set stream position to fill header information [%x]";
      v27 = -1073741811;
      v48 = 1416;
      goto LABEL_62;
    }
    a2[4] = v9;
    v32 = v9 + 12;
    if ( v32 > a2[2] )
    {
      v33 = a2[3] - 1LL;
      if ( v32 + v33 < v32 )
        goto LABEL_50;
      v34 = *v7;
      v35 = (v32 + v33) & ~v33;
      v36 = KeGetCurrentIrql();
      v37 = 512;
      if ( v34 )
      {
        if ( v36 != 2 )
          v37 = PagedPool;
        v40 = ExAllocatePoolWithTag(v37, v35, 0x7274534Du);
        v39 = v40;
        if ( !v40 )
        {
LABEL_47:
          v27 = -1073741801;
          goto LABEL_51;
        }
        memset(v40, 0, v35);
        v41 = v35;
        if ( v31 < v35 )
          v41 = v31;
        memmove(v39, v34, v41);
        ExFreePoolWithTag(v34, 0x7274534Du);
      }
      else
      {
        if ( v36 != 2 )
          v37 = PagedPool;
        v38 = ExAllocatePoolWithTag(v37, v35, 0x7274534Du);
        v39 = v38;
        if ( !v38 )
          goto LABEL_47;
        memset(v38, 0, v35);
      }
      v30 = v56;
      a2[2] = v35;
      v5 = v55;
      *v7 = v39;
    }
    v42 = (char *)*v7;
    v43 = a2[4];
    *(_DWORD *)&v42[v43] = 1936994353;
    *(_DWORD *)&v42[v43 + 4] = v30;
    *(_DWORD *)&v42[v43 + 8] = v5;
    v44 = a2[4];
    v45 = v44 + 12;
    if ( v44 + 12 < v44 )
    {
      a2[4] = -1;
LABEL_50:
      v27 = -1073741675;
LABEL_51:
      v26 = v27;
      v47 = "Failed to write header information to stream [%x]";
      v48 = 1422;
LABEL_62:
      AslLogCallPrintf(1, "AhcStoreSave", v48, v47, v26);
      return v27;
    }
    a2[4] = v45;
    v46 = a2[1];
    if ( v46 <= v45 )
      v46 = v45;
    a2[1] = v46;
    if ( v28 > v46 )
    {
      v26 = -1073741811;
      v47 = "Failed to set stream position after filling header information [%x]";
      v27 = -1073741811;
      v48 = 1433;
      goto LABEL_62;
    }
    v3 = v53;
    a2[4] = v28;
    v4 = *(unsigned __int16 **)v4;
    v6 = a1;
    v50 = 1936994353;
  }
}

```

## disassembly

```asm
0x14005344c  mov     [rsp+arg_8], rbx
0x140053451  mov     [rsp+arg_0], rcx
0x140053456  push    rbp
0x140053457  push    rsi
0x140053458  push    rdi
0x140053459  push    r12
0x14005345b  push    r13
0x14005345d  push    r14
0x14005345f  push    r15
0x140053461  sub     rsp, 50h
0x140053465  mov     rdi, rdx
0x140053468  mov     [rsp+88h+var_58], 0
0x140053470  xor     edx, edx
0x140053472  lea     rax, [rcx+68h]
0x140053476  mov     r13, [rax]
0x140053479  xor     ebx, ebx
0x14005347b  mov     [rsp+88h+arg_10], ebx
0x140053482  mov     rbp, rcx
0x140053485  lea     r12, [rdi+28h]
0x140053489  mov     [rsp+88h+arg_18], edx
0x140053490  mov     [rsp+88h+var_40], rax
0x140053495  mov     r15, r12
0x140053498  cmp     r13, rax
0x14005349b  jz      loc_1400538F8
0x1400534a1  mov     rsi, [rdi+20h]
0x1400534a5  lea     r14, [rsi+0Ch]
0x1400534a9  cmp     r14, rsi
0x1400534ac  jb      loc_1400538CD
0x1400534b2  cmp     r14, [rdi+10h]
0x1400534b6  jbe     loc_1400535CE
0x1400534bc  mov     rbx, [rdi+18h]
0x1400534c0  dec     rbx
0x1400534c3  lea     rax, [rbx+r14]
0x1400534c7  cmp     rax, r14
0x1400534ca  jb      loc_1400538C4
0x1400534d0  not     rbx
0x1400534d3  lea     r15, [rdi+28h]
0x1400534d7  and     rbx, rax
0x1400534da  mov     rax, [r15]
0x1400534dd  mov     [rsp+88h+Src], rax
0x1400534e2  test    rax, rax
0x1400534e5  jnz     short loc_140053535
0x1400534e7  call    cs:__imp_KeGetCurrentIrql
0x1400534ee  nop     dword ptr [rax+rax+00h]
0x1400534f3  mov     ecx, 200h
0x1400534f8  mov     r8d, 7274534Dh; Tag
0x1400534fe  cmp     al, 2
0x140053500  mov     rdx, rbx; NumberOfBytes
0x140053503  mov     eax, 1
0x140053508  cmovnz  ecx, eax; PoolType
0x14005350b  call    cs:__imp_ExAllocatePoolWithTag
0x140053512  nop     dword ptr [rax+rax+00h]
0x140053517  mov     rbp, rax
0x14005351a  test    rax, rax
0x14005351d  jz      loc_1400537FD
0x140053523  mov     r8, rbx; Size
0x140053526  xor     edx, edx; Val
0x140053528  mov     rcx, rax; void *
0x14005352b  call    memset
0x140053530  jmp     loc_1400535B8
0x140053535  mov     rax, [rdi+8]
0x140053539  mov     [rsp+88h+Size], rax
0x14005353e  call    cs:__imp_KeGetCurrentIrql
0x140053545  nop     dword ptr [rax+rax+00h]
0x14005354a  mov     ecx, 200h
0x14005354f  mov     r8d, 7274534Dh; Tag
0x140053555  cmp     al, 2
0x140053557  mov     rdx, rbx; NumberOfBytes
0x14005355a  mov     eax, 1
0x14005355f  cmovnz  ecx, eax; PoolType
0x140053562  call    cs:__imp_ExAllocatePoolWithTag
0x140053569  nop     dword ptr [rax+rax+00h]
0x14005356e  mov     rbp, rax
0x140053571  test    rax, rax
0x140053574  jz      loc_1400537FD
0x14005357a  mov     r8, rbx; Size
0x14005357d  xor     edx, edx; Val
0x14005357f  mov     rcx, rax; void *
0x140053582  call    memset
0x140053587  cmp     [rsp+88h+Size], rbx
0x14005358c  mov     r8, rbx
0x14005358f  mov     rdx, [rsp+88h+Src]; Src
0x140053594  mov     rcx, rbp; void *
0x140053597  cmovb   r8, [rsp+88h+Size]; Size
0x14005359d  call    memmove
0x1400535a2  mov     rcx, [rsp+88h+Src]; P
0x1400535a7  mov     edx, 7274534Dh; Tag
0x1400535ac  call    cs:__imp_ExFreePoolWithTag
0x1400535b3  nop     dword ptr [rax+rax+00h]
0x1400535b8  mov     [r15], rbp
0x1400535bb  mov     rbp, [rsp+88h+arg_0]
0x1400535c3  mov     [rdi+10h], rbx
0x1400535c7  mov     ebx, [rsp+88h+arg_10]
0x1400535ce  mov     rcx, [r15]
0x1400535d1  mov     rax, [rdi+20h]
0x1400535d5  mov     edx, [rsp+88h+var_58]
0x1400535d9  mov     [rcx+rax], edx
0x1400535dc  mov     edx, [rsp+88h+arg_18]
0x1400535e3  mov     [rcx+rax+4], edx
0x1400535e7  mov     [rcx+rax+8], ebx
0x1400535eb  mov     rax, [rdi+20h]
0x1400535ef  lea     rcx, [rax+0Ch]
0x1400535f3  cmp     rcx, rax
0x1400535f6  jb      loc_1400538BC
0x1400535fc  mov     [rdi+20h], rcx
0x140053600  mov     rdx, rdi
0x140053603  mov     rax, [rdi+8]
0x140053607  cmp     rax, rcx
0x14005360a  cmovbe  rax, rcx
0x14005360e  lea     rcx, [r13+18h]
0x140053612  mov     [rdi+8], rax
0x140053616  call    AhcpStoreKeySave
0x14005361b  mov     ebx, eax
0x14005361d  test    eax, eax
0x14005361f  js      loc_1400538AD
0x140053625  mov     rax, [rbp+0A0h]
0x14005362c  mov     rdx, rdi
0x14005362f  mov     rcx, [r13+28h]
0x140053633  call    _guard_dispatch_icall
0x140053638  mov     ebx, eax
0x14005363a  test    eax, eax
0x14005363c  js      loc_14005389E
0x140053642  mov     rbp, [rdi+20h]
0x140053646  mov     ecx, 0FFFFFFFFh
0x14005364b  mov     rax, rbp
0x14005364e  sub     rax, rsi
0x140053651  sub     rax, 0Ch
0x140053655  cmp     rax, rcx
0x140053658  ja      loc_140053879
0x14005365e  mov     ebx, ebp
0x140053660  sub     ebx, esi
0x140053662  add     ebx, 0FFFFFFF4h
0x140053665  mov     ecx, ebx
0x140053667  add     rcx, r14
0x14005366a  mov     [rsp+88h+arg_10], ebx
0x140053671  cmp     rcx, r14
0x140053674  jb      loc_140053861
0x14005367a  cmp     rcx, [rdi+8]
0x14005367e  ja      loc_140053861
0x140053684  mov     rdx, [r12]
0x140053688  mov     r8d, ebx; Length
0x14005368b  add     rdx, r14; Buffer
0x14005368e  xor     ecx, ecx; InitialCrc
0x140053690  call    cs:__imp_RtlComputeCrc32
0x140053697  nop     dword ptr [rax+rax+00h]
0x14005369c  mov     edx, eax
0x14005369e  mov     [rsp+88h+arg_18], eax
0x1400536a5  mov     r15, [rdi+8]
0x1400536a9  cmp     rsi, r15
0x1400536ac  ja      loc_140053848
0x1400536b2  mov     [rdi+20h], rsi
0x1400536b6  add     rsi, 0Ch
0x1400536ba  cmp     rsi, [rdi+10h]
0x1400536be  jbe     loc_14005379F
0x1400536c4  mov     rbx, [rdi+18h]
0x1400536c8  dec     rbx
0x1400536cb  lea     rcx, [rsi+rbx]
0x1400536cf  cmp     rcx, rsi
0x1400536d2  jb      loc_14005382F
0x1400536d8  mov     r14, [r12]
0x1400536dc  not     rbx
0x1400536df  and     rbx, rcx
0x1400536e2  call    cs:__imp_KeGetCurrentIrql
0x1400536e9  nop     dword ptr [rax+rax+00h]
0x1400536ee  mov     ecx, 200h
0x1400536f3  mov     r8d, 7274534Dh; Tag
0x1400536f9  mov     rdx, rbx; NumberOfBytes
0x1400536fc  test    r14, r14
0x1400536ff  jnz     short loc_140053731
0x140053701  cmp     al, 2
0x140053703  lea     eax, [r14+1]
0x140053707  cmovnz  ecx, eax; PoolType
0x14005370a  call    cs:__imp_ExAllocatePoolWithTag
0x140053711  nop     dword ptr [rax+rax+00h]
0x140053716  mov     rsi, rax
0x140053719  test    rax, rax
0x14005371c  jz      loc_140053807
0x140053722  mov     r8, rbx; Size
0x140053725  xor     edx, edx; Val
0x140053727  mov     rcx, rax; void *
0x14005372a  call    memset
0x14005372f  jmp     short loc_140053789
0x140053731  cmp     al, 2
0x140053733  mov     eax, 1
0x140053738  cmovnz  ecx, eax; PoolType
0x14005373b  call    cs:__imp_ExAllocatePoolWithTag
0x140053742  nop     dword ptr [rax+rax+00h]
0x140053747  mov     rsi, rax
0x14005374a  test    rax, rax
0x14005374d  jz      loc_140053807
0x140053753  mov     r8, rbx; Size
0x140053756  xor     edx, edx; Val
0x140053758  mov     rcx, rax; void *
0x14005375b  call    memset
0x140053760  cmp     r15, rbx
0x140053763  mov     r8, rbx
0x140053766  mov     rdx, r14; Src
0x140053769  mov     rcx, rsi; void *
0x14005376c  cmovb   r8, r15; Size
0x140053770  call    memmove
0x140053775  mov     edx, 7274534Dh; Tag
0x14005377a  mov     rcx, r14; P
0x14005377d  call    cs:__imp_ExFreePoolWithTag
0x140053784  nop     dword ptr [rax+rax+00h]
0x140053789  mov     edx, [rsp+88h+arg_18]
0x140053790  mov     [rdi+10h], rbx
0x140053794  mov     ebx, [rsp+88h+arg_10]
0x14005379b  mov     [r12], rsi
0x14005379f  mov     rcx, [r12]
0x1400537a3  mov     rax, [rdi+20h]
0x1400537a7  mov     dword ptr [rcx+rax], 73743031h
0x1400537ae  mov     [rcx+rax+4], edx
0x1400537b2  mov     [rcx+rax+8], ebx
0x1400537b6  mov     rax, [rdi+20h]
0x1400537ba  lea     rcx, [rax+0Ch]
0x1400537be  cmp     rcx, rax
0x1400537c1  jb      short loc_140053827
0x1400537c3  mov     [rdi+20h], rcx
0x1400537c7  mov     rax, [rdi+8]
0x1400537cb  cmp     rax, rcx
0x1400537ce  cmovbe  rax, rcx
0x1400537d2  mov     [rdi+8], rax
0x1400537d6  cmp     rbp, rax
0x1400537d9  ja      short loc_14005380E
0x1400537db  mov     rax, [rsp+88h+var_40]
0x1400537e0  mov     [rdi+20h], rbp
0x1400537e4  mov     r13, [r13+0]
0x1400537e8  mov     rbp, [rsp+88h+arg_0]
0x1400537f0  mov     [rsp+88h+var_58], 73743031h
0x1400537f8  jmp     loc_140053495
0x1400537fd  mov     ebx, 0C0000017h
0x140053802  jmp     loc_1400538C9
0x140053807  mov     ebx, 0C0000017h
0x14005380c  jmp     short loc_140053834
0x14005380e  mov     eax, 0C000000Dh
0x140053813  lea     r9, aFailedToSetStr_0; "Failed to set stream position after fil"...
0x14005381a  mov     ebx, eax
0x14005381c  mov     r8d, 599h
0x140053822  jmp     loc_1400538E1
0x140053827  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x14005382f  mov     ebx, 0C0000095h
0x140053834  mov     eax, ebx
0x140053836  lea     r9, aFailedToWriteH; "Failed to write header information to s"...
0x14005383d  mov     r8d, 58Eh
0x140053843  jmp     loc_1400538E1
0x140053848  mov     eax, 0C000000Dh
0x14005384d  lea     r9, aFailedToSetStr; "Failed to set stream position to fill h"...
0x140053854  mov     ebx, eax
0x140053856  mov     r8d, 588h
0x14005385c  jmp     loc_1400538E1
0x140053861  mov     ebx, 0C000000Dh
0x140053866  lea     r9, aFailedToCalcul; "Failed to calculate checksum [%x]"
0x14005386d  mov     [rsp+88h+var_68], ebx
0x140053871  mov     r8d, 57Eh
0x140053877  jmp     short loc_1400538E5
0x140053879  lea     r9, aIncorrectStrea; "Incorrect stream buffer size"
0x140053880  mov     r8d, 572h
0x140053886  lea     rdx, aAhcstoresave; "AhcStoreSave"
0x14005388d  mov     ecx, 1
0x140053892  call    AslLogCallPrintf
0x140053897  mov     ebx, 0C000000Dh
0x14005389c  jmp     short loc_1400538FA
0x14005389e  lea     r9, aFailedToSaveIt; "Failed to save item [%x]"
0x1400538a5  mov     r8d, 566h
0x1400538ab  jmp     short loc_1400538E1
0x1400538ad  lea     r9, aFailedToWriteK; "Failed to write key [%x]"
0x1400538b4  mov     r8d, 55Fh
0x1400538ba  jmp     short loc_1400538E1
0x1400538bc  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x1400538c4  mov     ebx, 0C0000095h
0x1400538c9  mov     eax, ebx
0x1400538cb  jmp     short loc_1400538D4
0x1400538cd  mov     eax, 0C000000Dh
0x1400538d2  mov     ebx, eax
0x1400538d4  lea     r9, aFailedToWriteS_2; "Failed to write store entry header [%x]"
0x1400538db  mov     r8d, 554h
0x1400538e1  mov     [rsp+88h+var_68], eax
0x1400538e5  lea     rdx, aAhcstoresave; "AhcStoreSave"
0x1400538ec  mov     ecx, 1
0x1400538f1  call    AslLogCallPrintf
0x1400538f6  jmp     short loc_1400538FA
0x1400538f8  xor     ebx, ebx
0x1400538fa  mov     eax, ebx
0x1400538fc  mov     rbx, [rsp+88h+arg_8]
0x140053904  add     rsp, 50h
0x140053908  pop     r15
0x14005390a  pop     r14
0x14005390c  pop     r13
0x14005390e  pop     r12
0x140053910  pop     rdi
0x140053911  pop     rsi
0x140053912  pop     rbp
0x140053913  retn
```
