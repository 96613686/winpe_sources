# UbpmpTokenCheckHarden

- ea: `0x18000f284`
- end: `0x18000f874`
- name: `UbpmpTokenCheckHarden`
- size: `1520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001eaf4`

## callees

- `0x18000f284`
- `0x18000fbf0`
- `0x1800150c0`
- `0x18001af64`
- `0x18001d1d8`
- `0x180023b50`
- `0x1800298c4`
- `0x180029bd0`
- `0x18002ac90`
- `0x18002af20`
- `0x18003ea60`
- `0x18003f074`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f3bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f4de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f3bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f4de`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f3e9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f50c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f3e9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f863`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f527`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f31c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f31c`

## pseudocode

```c
__int64 __fastcall UbpmpTokenCheckHarden(
        int *a1,
        __int64 a2,
        struct _TOKEN_GROUPS *a3,
        __int64 a4,
        unsigned __int64 *a5,
        char a6,
        HANDLE *a7,
        unsigned int *a8,
        void ***a9,
        _QWORD *a10)
{
  unsigned int *v10; // r12
  struct _TOKEN_GROUPS *v11; // r15
  unsigned int NonInteractiveToken; // ebx
  void **v14; // r14
  unsigned __int64 *v15; // rsi
  char v16; // r13
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v24; // ecx
  unsigned int TokenGroups; // eax
  SID_AND_ATTRIBUTES *Groups; // r15
  DWORD LengthSid; // ebx
  void **v28; // rax
  unsigned int v29; // r12d
  unsigned int ConsumerSids; // eax
  __int64 v31; // rax
  DWORD v32; // ebx
  void *v33; // rax
  void *v34; // r12
  HANDLE *v35; // rbx
  int v36; // r8d
  __int64 v37; // rax
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // rdx
  char v40; // r15
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // rax
  _QWORD *v43; // rcx
  int v44; // edx
  void *v45; // [rsp+30h] [rbp-20h]
  HANDLE hObject; // [rsp+38h] [rbp-18h] BYREF
  void **v47; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-8h] BYREF
  struct _TOKEN_GROUPS *v50; // [rsp+A0h] [rbp+50h] BYREF
  int v51; // [rsp+A8h] [rbp+58h]

  v51 = a4;
  v10 = a8;
  v50 = 0;
  v11 = a3;
  v47 = 0;
  hObject = 0;
  NonInteractiveToken = 0;
  *a8 = 0;
  v14 = 0;
  hMem = 0;
  v45 = 0;
  if ( !a3 || (v15 = a5) == 0 || (v16 = a6, !*a5) && !a6 )
  {
    *a9 = 0;
    *a10 = 0;
    goto LABEL_6;
  }
  if ( !UbpmUtilsSidSupportsHardening(a3) )
  {
    *a9 = 0;
    *a10 = 0;
    goto LABEL_6;
  }
  v24 = *a1;
  if ( v16 != 1 )
  {
    if ( v24 == 2 )
      UbpmpGetNoSidConsumerPrivMask(v11);
    v35 = a7;
    v34 = 0;
LABEL_30:
    v37 = *v15;
    if ( (*v15 & 0x8000000000000000uLL) == 0LL )
    {
      v41 = 0;
      v40 = 0;
      v38 = 0;
      v39 = *v15;
    }
    else
    {
      v38 = v37 & 0x7FFFFFFFFFFFFFFFLL;
      v39 = 0;
      v40 = 1;
      v41 = ~(_DWORD)v37 & 0x20000000;
    }
    TokenGroups = UbpmUtilsRemoveProcessPrivileges(*v35, v39, v41, v38, v15);
    NonInteractiveToken = TokenGroups;
    if ( !TokenGroups )
    {
      *a9 = v14;
      v14 = 0;
      v45 = 0;
      *a10 = v34;
      v42 = *v15 | 0x8000000000000000uLL;
      if ( !v40 )
        v42 = *v15;
      *v15 = v42;
      goto LABEL_6;
    }
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v44 = 223;
LABEL_42:
    WPP_SF_Sd(v43[2], v44, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, a2, TokenGroups);
    goto LABEL_6;
  }
  if ( ((v24 - 1) & 0xFFFFFFFC) != 0 || v24 == 2 )
  {
    ConsumerSids = UbpmpGetConsumerSids(v11, v51, v10, &v47, v15);
    NonInteractiveToken = ConsumerSids;
    if ( ConsumerSids )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          a2,
          ConsumerSids);
      v14 = v47;
      goto LABEL_6;
    }
    v14 = v47;
    TokenGroups = UbpmUtilsGetTokenGroups(
                    *(const unsigned __int16 **)(*((_QWORD *)a1 + 4) + 64LL),
                    *(unsigned int *)(*((_QWORD *)a1 + 4) + 72LL),
                    *v10,
                    v47,
                    &v50);
    NonInteractiveToken = TokenGroups;
    if ( TokenGroups )
    {
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v44 = 217;
      goto LABEL_42;
    }
    v29 = *v10;
    Groups = (SID_AND_ATTRIBUTES *)v14;
  }
  else
  {
    TokenGroups = UbpmUtilsGetTokenGroups(
                    *(const unsigned __int16 **)(*((_QWORD *)a1 + 4) + 64LL),
                    *(unsigned int *)(*((_QWORD *)a1 + 4) + 72LL),
                    0,
                    0,
                    &v50);
    NonInteractiveToken = TokenGroups;
    if ( TokenGroups )
    {
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v44 = 213;
      goto LABEL_42;
    }
    Groups = v50->Groups;
    LengthSid = GetLengthSid(v50->Groups[0].Sid);
    v28 = (void **)UbpmAlloc(LengthSid + 8);
    v14 = v28;
    if ( !v28 )
    {
      TokenGroups = GetLastError();
      NonInteractiveToken = TokenGroups;
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v44 = 214;
      goto LABEL_42;
    }
    *v28 = v28 + 1;
    if ( !CopySid(LengthSid, v28 + 1, Groups->Sid) )
    {
      TokenGroups = GetLastError();
      NonInteractiveToken = TokenGroups;
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v44 = 215;
      goto LABEL_42;
    }
    *v10 = 1;
    v29 = 1;
  }
  v31 = *((_QWORD *)a1 + 4);
  if ( v31 && (unsigned int)(*(_DWORD *)(v31 + 32) - 4) <= 1 && (a3 = v50) != 0 )
  {
    NonInteractiveToken = UbpmpTokenGetNonInteractiveToken(a1, 0, v50, a2, &hObject, &hMem);
    if ( !NonInteractiveToken )
    {
      TokenGroups = UbpmUtilsAdjustTokenDefaultDacl(hObject, pSid, &Groups->Sid, v29);
      NonInteractiveToken = TokenGroups;
      if ( TokenGroups )
      {
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v44 = 219;
        goto LABEL_42;
      }
      v32 = GetLengthSid(hMem);
      v33 = UbpmAlloc(v32);
      v45 = v33;
      v34 = v33;
      if ( !v33 )
      {
        TokenGroups = GetLastError();
        NonInteractiveToken = TokenGroups;
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v44 = 220;
        goto LABEL_42;
      }
      if ( !CopySid(v32, v33, hMem) )
      {
        TokenGroups = GetLastError();
        NonInteractiveToken = TokenGroups;
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_6;
        v44 = 221;
        goto LABEL_42;
      }
      v35 = a7;
      CloseHandle(*a7);
      *v35 = hObject;
      hObject = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_Sid(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, v36, a2, *v15, 1);
      goto LABEL_30;
    }
  }
  else
  {
    NonInteractiveToken = 87;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      218,
      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
      a2,
      NonInteractiveToken);
LABEL_6:
  UBPM_MIDL_user_free(v50, a2, a3, a4);
  UBPM_MIDL_user_free(v14, v17, v18, v19);
  UBPM_MIDL_user_free(v45, v20, v21, v22);
  LocalFree(hMem);
  if ( hObject )
    CloseHandle(hObject);
  return NonInteractiveToken;
}

```

## disassembly

```asm
0x18000f284  mov     [rsp-38h+arg_8], rbx
0x18000f289  mov     [rsp-38h+arg_18], r9d
0x18000f28e  mov     [rsp-38h+arg_0], rcx
0x18000f293  push    rbp
0x18000f294  push    rsi
0x18000f295  push    rdi
0x18000f296  push    r12
0x18000f298  push    r13
0x18000f29a  push    r14
0x18000f29c  push    r15
0x18000f29e  mov     rbp, rsp
0x18000f2a1  sub     rsp, 50h
0x18000f2a5  mov     r12, [rbp+arg_38]
0x18000f2a9  xor     ecx, ecx
0x18000f2ab  mov     [rbp+arg_10], rcx
0x18000f2af  mov     r15, r8
0x18000f2b2  mov     [rbp+var_10], rcx
0x18000f2b6  mov     rdi, rdx
0x18000f2b9  mov     [rbp+hObject], rcx
0x18000f2bd  mov     ebx, ecx
0x18000f2bf  mov     [r12], ecx
0x18000f2c3  mov     r14d, ecx
0x18000f2c6  mov     [rbp+hMem], rcx
0x18000f2ca  mov     [rbp+var_20], rcx
0x18000f2ce  test    r8, r8
0x18000f2d1  jz      short loc_18000F2EA
0x18000f2d3  mov     rsi, [rbp+arg_20]
0x18000f2d7  test    rsi, rsi
0x18000f2da  jz      short loc_18000F2EA
0x18000f2dc  mov     r13b, [rbp+arg_28]
0x18000f2e0  cmp     [rsi], rcx
0x18000f2e3  jnz     short loc_18000F350
0x18000f2e5  test    r13b, r13b
0x18000f2e8  jnz     short loc_18000F350
0x18000f2ea  mov     rax, [rbp+arg_40]
0x18000f2f1  mov     [rax], rcx
0x18000f2f4  mov     rax, [rbp+arg_48]
0x18000f2fb  mov     [rax], rcx
0x18000f2fe  mov     rcx, [rbp+arg_10]
0x18000f302  call    UBPM_MIDL_user_free
0x18000f307  mov     rcx, r14
0x18000f30a  call    UBPM_MIDL_user_free
0x18000f30f  mov     rcx, [rbp+var_20]
0x18000f313  call    UBPM_MIDL_user_free
0x18000f318  mov     rcx, [rbp+hMem]; hMem
0x18000f31c  call    cs:__imp_LocalFree
0x18000f323  nop     dword ptr [rax+rax+00h]
0x18000f328  mov     rcx, [rbp+hObject]; hObject
0x18000f32c  test    rcx, rcx
0x18000f32f  jnz     loc_18000F863
0x18000f335  mov     eax, ebx
0x18000f337  mov     rbx, [rsp+50h+arg_8]
0x18000f33f  add     rsp, 50h
0x18000f343  pop     r15
0x18000f345  pop     r14
0x18000f347  pop     r13
0x18000f349  pop     r12
0x18000f34b  pop     rdi
0x18000f34c  pop     rsi
0x18000f34d  pop     rbp
0x18000f34e  retn
0x18000f350  mov     rcx, r15; pSid1
0x18000f353  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x18000f358  test    al, al
0x18000f35a  jz      loc_18000F62A
0x18000f360  mov     rdx, [rbp+arg_0]
0x18000f364  mov     ecx, [rdx]
0x18000f366  cmp     r13b, 1
0x18000f36a  jnz     loc_18000F5D8
0x18000f370  lea     eax, [rcx-1]
0x18000f373  test    eax, 0FFFFFFFCh
0x18000f378  jnz     loc_18000F40D
0x18000f37e  cmp     ecx, 2
0x18000f381  jz      loc_18000F40D
0x18000f387  mov     rcx, [rdx+20h]
0x18000f38b  lea     rax, [rbp+arg_10]
0x18000f38f  xor     r9d, r9d; void **
0x18000f392  mov     [rsp+50h+var_30], rax; struct _TOKEN_GROUPS **
0x18000f397  xor     r8d, r8d; unsigned int
0x18000f39a  mov     edx, [rcx+48h]; unsigned int
0x18000f39d  mov     rcx, [rcx+40h]; unsigned __int16 *
0x18000f3a1  call    ?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z; UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)
0x18000f3a6  mov     ebx, eax
0x18000f3a8  test    eax, eax
0x18000f3aa  jnz     loc_18000F68A
0x18000f3b0  mov     r15, [rbp+arg_10]
0x18000f3b4  add     r15, 8
0x18000f3b8  mov     rcx, [r15]; pSid
0x18000f3bb  call    cs:__imp_GetLengthSid
0x18000f3c2  nop     dword ptr [rax+rax+00h]
0x18000f3c7  mov     ebx, eax
0x18000f3c9  lea     ecx, [rax+8]; Size
0x18000f3cc  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000f3d1  mov     r14, rax
0x18000f3d4  test    rax, rax
0x18000f3d7  jz      loc_18000F6B5
0x18000f3dd  lea     rdx, [rax+8]; pDestinationSid
0x18000f3e1  mov     ecx, ebx; nDestinationSidLength
0x18000f3e3  mov     [rax], rdx
0x18000f3e6  mov     r8, [r15]; pSourceSid
0x18000f3e9  call    cs:__imp_CopySid
0x18000f3f0  nop     dword ptr [rax+rax+00h]
0x18000f3f5  test    eax, eax
0x18000f3f7  jz      loc_18000F6EE
0x18000f3fd  mov     dword ptr [r12], 1
0x18000f405  mov     r12d, 1
0x18000f40b  jmp     short loc_18000F467
0x18000f40d  mov     edx, [rbp+arg_18]
0x18000f410  lea     r9, [rbp+var_10]
0x18000f414  mov     r8, r12
0x18000f417  mov     [rsp+50h+var_30], rsi; __int64
0x18000f41c  mov     rcx, r15; pSid1
0x18000f41f  call    UbpmpGetConsumerSids
0x18000f424  mov     ebx, eax
0x18000f426  test    eax, eax
0x18000f428  jnz     loc_18000F727
0x18000f42e  mov     rcx, [rbp+arg_0]
0x18000f432  lea     rax, [rbp+arg_10]
0x18000f436  mov     r14, [rbp+var_10]
0x18000f43a  mov     r8d, [r12]; unsigned int
0x18000f43e  mov     r9, r14; void **
0x18000f441  mov     [rsp+50h+var_30], rax; struct _TOKEN_GROUPS **
0x18000f446  mov     rcx, [rcx+20h]
0x18000f44a  mov     edx, [rcx+48h]; unsigned int
0x18000f44d  mov     rcx, [rcx+40h]; unsigned __int16 *
0x18000f451  call    ?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z; UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)
0x18000f456  mov     ebx, eax
0x18000f458  test    eax, eax
0x18000f45a  jnz     loc_18000F765
0x18000f460  mov     r12d, [r12]
0x18000f464  mov     r15, r14
0x18000f467  mov     rcx, [rbp+arg_0]
0x18000f46b  mov     rax, [rcx+20h]
0x18000f46f  test    rax, rax
0x18000f472  jz      loc_18000F643
0x18000f478  mov     eax, [rax+20h]
0x18000f47b  sub     eax, 4
0x18000f47e  cmp     eax, 1
0x18000f481  ja      loc_18000F643
0x18000f487  mov     r8, [rbp+arg_10]
0x18000f48b  test    r8, r8
0x18000f48e  jz      loc_18000F643
0x18000f494  lea     rax, [rbp+hMem]
0x18000f498  mov     r9, rdi
0x18000f49b  mov     [rsp+50h+var_28], rax
0x18000f4a0  xor     edx, edx
0x18000f4a2  lea     rax, [rbp+hObject]
0x18000f4a6  mov     [rsp+50h+var_30], rax
0x18000f4ab  call    UbpmpTokenGetNonInteractiveToken
0x18000f4b0  mov     ebx, eax
0x18000f4b2  test    eax, eax
0x18000f4b4  jnz     loc_18000F648
0x18000f4ba  mov     rdx, cs:pSid; pSid
0x18000f4c1  mov     r9d, r12d; unsigned int
0x18000f4c4  mov     rcx, [rbp+hObject]; TokenHandle
0x18000f4c8  mov     r8, r15; void **
0x18000f4cb  call    ?UbpmUtilsAdjustTokenDefaultDacl@@YAKPEAX0PEAPEAXK@Z; UbpmUtilsAdjustTokenDefaultDacl(void *,void *,void * *,ulong)
0x18000f4d0  mov     ebx, eax
0x18000f4d2  test    eax, eax
0x18000f4d4  jnz     loc_18000F790
0x18000f4da  mov     rcx, [rbp+hMem]; pSid
0x18000f4de  call    cs:__imp_GetLengthSid
0x18000f4e5  nop     dword ptr [rax+rax+00h]
0x18000f4ea  mov     ecx, eax; Size
0x18000f4ec  mov     ebx, eax
0x18000f4ee  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000f4f3  mov     [rbp+var_20], rax
0x18000f4f7  mov     r12, rax
0x18000f4fa  test    rax, rax
0x18000f4fd  jz      loc_18000F7BB
0x18000f503  mov     r8, [rbp+hMem]; pSourceSid
0x18000f507  mov     rdx, rax; pDestinationSid
0x18000f50a  mov     ecx, ebx; nDestinationSidLength
0x18000f50c  call    cs:__imp_CopySid
0x18000f513  nop     dword ptr [rax+rax+00h]
0x18000f518  test    eax, eax
0x18000f51a  jz      loc_18000F7F4
0x18000f520  mov     rbx, [rbp+arg_30]
0x18000f524  mov     rcx, [rbx]; hObject
0x18000f527  call    cs:__imp_CloseHandle
0x18000f52e  nop     dword ptr [rax+rax+00h]
0x18000f533  mov     rax, [rbp+hObject]
0x18000f537  mov     [rbx], rax
0x18000f53a  mov     [rbp+hObject], 0
0x18000f542  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f549  lea     r13, WPP_GLOBAL_Control
0x18000f550  cmp     rcx, r13
0x18000f553  jz      short loc_18000F55F
0x18000f555  test    byte ptr [rcx+1Ch], 80h
0x18000f559  jnz     loc_18000F82D
0x18000f55f  mov     rax, [rsi]
0x18000f562  test    rax, rax
0x18000f565  jns     loc_18000F619
0x18000f56b  mov     r9, rax
0x18000f56e  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18000f578  not     rax
0x18000f57b  and     r9, rcx; unsigned __int64
0x18000f57e  xor     edx, edx; unsigned __int64
0x18000f580  mov     r15b, 1
0x18000f583  and     eax, 20000000h
0x18000f588  mov     r8d, eax; unsigned __int64
0x18000f58b  mov     rcx, [rbx]; TokenHandle
0x18000f58e  mov     [rsp+50h+var_30], rsi; unsigned __int64 *
0x18000f593  call    ?UbpmUtilsRemoveProcessPrivileges@@YAKPEAX_K11PEA_K@Z; UbpmUtilsRemoveProcessPrivileges(void *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000f598  mov     ebx, eax
0x18000f59a  test    eax, eax
0x18000f59c  jnz     short loc_18000F5F4
0x18000f59e  mov     rax, [rbp+arg_40]
0x18000f5a5  mov     rcx, 8000000000000000h
0x18000f5af  mov     [rax], r14
0x18000f5b2  xor     r14d, r14d
0x18000f5b5  mov     rax, [rbp+arg_48]
0x18000f5bc  mov     [rbp+var_20], r14
0x18000f5c0  mov     [rax], r12
0x18000f5c3  mov     rax, [rsi]
0x18000f5c6  or      rax, rcx
0x18000f5c9  test    r15b, r15b
0x18000f5cc  cmovz   rax, [rsi]
0x18000f5d0  mov     [rsi], rax
0x18000f5d3  jmp     loc_18000F2FE
0x18000f5d8  cmp     ecx, 2
0x18000f5db  jz      loc_18000F853
0x18000f5e1  mov     rbx, [rbp+arg_30]
0x18000f5e5  lea     r13, WPP_GLOBAL_Control
0x18000f5ec  mov     r12, r14
0x18000f5ef  jmp     loc_18000F55F
0x18000f5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5fb  cmp     rcx, r13
0x18000f5fe  jz      loc_18000F2FE
0x18000f604  test    byte ptr [rcx+1Ch], 1
0x18000f608  jz      loc_18000F2FE
0x18000f60e  mov     edx, 0DFh
0x18000f613  mov     dword ptr [rsp+50h+var_30], eax
0x18000f617  jmp     short loc_18000F672
0x18000f619  xor     r8d, r8d
0x18000f61c  xor     r15b, r15b
0x18000f61f  xor     r9d, r9d
0x18000f622  mov     rdx, rax
0x18000f625  jmp     loc_18000F58B
0x18000f62a  mov     rax, [rbp+arg_40]
0x18000f631  mov     [rax], rbx
0x18000f634  mov     rax, [rbp+arg_48]
0x18000f63b  mov     [rax], rbx
0x18000f63e  jmp     loc_18000F2FE
0x18000f643  mov     ebx, 57h ; 'W'
0x18000f648  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f64f  lea     r13, WPP_GLOBAL_Control
0x18000f656  cmp     rcx, r13
0x18000f659  jz      loc_18000F2FE
0x18000f65f  test    byte ptr [rcx+1Ch], 1
0x18000f663  jz      loc_18000F2FE
0x18000f669  mov     edx, 0DAh
0x18000f66e  mov     dword ptr [rsp+50h+var_30], ebx
0x18000f672  mov     rcx, [rcx+10h]
0x18000f676  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000f67d  mov     r9, rdi
0x18000f680  call    WPP_SF_Sd
0x18000f685  jmp     loc_18000F2FE
0x18000f68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f691  lea     r13, WPP_GLOBAL_Control
0x18000f698  cmp     rcx, r13
0x18000f69b  jz      loc_18000F2FE
0x18000f6a1  test    byte ptr [rcx+1Ch], 1
0x18000f6a5  jz      loc_18000F2FE
0x18000f6ab  mov     edx, 0D5h
0x18000f6b0  jmp     loc_18000F613
0x18000f6b5  call    cs:__imp_GetLastError
0x18000f6bc  nop     dword ptr [rax+rax+00h]
0x18000f6c1  mov     ebx, eax
0x18000f6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6ca  lea     r13, WPP_GLOBAL_Control
0x18000f6d1  cmp     rcx, r13
0x18000f6d4  jz      loc_18000F2FE
0x18000f6da  test    byte ptr [rcx+1Ch], 1
0x18000f6de  jz      loc_18000F2FE
0x18000f6e4  mov     edx, 0D6h
0x18000f6e9  jmp     loc_18000F613
0x18000f6ee  call    cs:__imp_GetLastError
0x18000f6f5  nop     dword ptr [rax+rax+00h]
0x18000f6fa  mov     ebx, eax
0x18000f6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f703  lea     r13, WPP_GLOBAL_Control
0x18000f70a  cmp     rcx, r13
0x18000f70d  jz      loc_18000F2FE
0x18000f713  test    byte ptr [rcx+1Ch], 1
0x18000f717  jz      loc_18000F2FE
0x18000f71d  mov     edx, 0D7h
0x18000f722  jmp     loc_18000F613
0x18000f727  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f72e  lea     r13, WPP_GLOBAL_Control
0x18000f735  cmp     rcx, r13
0x18000f738  jz      short loc_18000F75C
0x18000f73a  test    byte ptr [rcx+1Ch], 1
0x18000f73e  jz      short loc_18000F75C
0x18000f740  mov     rcx, [rcx+10h]
0x18000f744  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000f74b  mov     edx, 0D8h
0x18000f750  mov     dword ptr [rsp+50h+var_30], eax
0x18000f754  mov     r9, rdi
0x18000f757  call    WPP_SF_Sd
  ... truncated ...
```
