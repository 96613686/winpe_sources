# CNgscbToken::GetRestrictedToken(long const *,ulong,CNgscbToken &)

- ea: `0x18001a1d0`
- end: `0x18001a501`
- name: `?GetRestrictedToken@CNgscbToken@@QEBAJPEBJKAEAV1@@Z`
- size: `817`
- prototype: `__int64 __fastcall(CNgscbToken *__hidden this, const int *, unsigned int, struct CNgscbToken *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x18001a1d0`
- `0x18001a508`
- `0x1800345ec`
- `0x180034610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a4eb`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001a426`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001a426`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a224`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a2df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a224`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a2df`

## pseudocode

```c
__int64 __fastcall CNgscbToken::GetRestrictedToken(HANDLE *this, const int *a2, DWORD a3, struct CNgscbToken *a4)
{
  HANDLE v6; // rcx
  unsigned int *v8; // rsi
  struct _LUID_AND_ATTRIBUTES *PrivilegesToDelete; // rbp
  unsigned int v10; // edi
  unsigned __int64 v12; // rax
  DWORD v13; // edi
  int v14; // r8d
  unsigned int v15; // r10d
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rcx
  HANDLE v19; // rbx
  bool v20; // r11
  signed int LastError; // eax
  HANDLE hObject; // [rsp+50h] [rbp-48h] BYREF
  DWORD TokenInformationLength; // [rsp+B0h] [rbp+18h] BYREF

  TokenInformationLength = a3;
  v6 = *this;
  hObject = 0;
  TokenInformationLength = 0;
  v8 = 0;
  PrivilegesToDelete = 0;
  if ( GetTokenInformation(v6, TokenPrivileges, 0, 0, &TokenInformationLength) )
  {
    v10 = -2147418113;
    goto LABEL_3;
  }
  if ( GetLastError() == 122 )
  {
    v8 = (unsigned int *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v8 )
    {
      v10 = -2147024882;
      goto LABEL_3;
    }
    if ( GetTokenInformation(*this, TokenPrivileges, v8, TokenInformationLength, &TokenInformationLength) )
    {
      v12 = 12LL * *v8;
      if ( !is_mul_ok(*v8, 0xCu) )
        v12 = -1;
      PrivilegesToDelete = (struct _LUID_AND_ATTRIBUTES *)operator new[](
                                                            v12,
                                                            (const struct std::nothrow_t *)&std::nothrow);
      if ( !PrivilegesToDelete )
      {
        v10 = -2147024882;
        goto LABEL_3;
      }
      v13 = 0;
      if ( *v8 )
      {
        v14 = a2[2];
        v15 = 0;
        do
        {
          v16 = 3LL * v15;
          v20 = *(_QWORD *)&v8[v16 + 1] == *a2;
          if ( *(_QWORD *)&v8[v16 + 1] == a2[1] )
            v20 = 1;
          if ( *(_QWORD *)&v8[v16 + 1] != v14 && !v20 )
          {
            v17 = v13++;
            v18 = v17;
            PrivilegesToDelete[v18].Luid = *(LUID *)&v8[v16 + 1];
            PrivilegesToDelete[v18].Attributes = v8[v16 + 3];
            v14 = a2[2];
          }
          ++v15;
        }
        while ( v15 < *v8 );
      }
      if ( CreateRestrictedToken(*this, 0, 0, 0, v13, PrivilegesToDelete, 0, 0, &hObject) )
      {
        v19 = hObject;
        v10 = 0;
        SH<void *,SH_HANDLE>::Reset(a4);
        *(_QWORD *)a4 = v19;
        hObject = 0;
LABEL_25:
        operator delete(PrivilegesToDelete);
        goto LABEL_6;
      }
    }
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_3:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( PrivilegesToDelete )
    goto LABEL_25;
LABEL_6:
  if ( v8 )
    operator delete(v8);
  return v10;
}

```

## disassembly

```asm
0x18001a1d0  mov     r11, rsp
0x18001a1d3  mov     [r11+18h], r8d
0x18001a1d7  push    rsi
0x18001a1d8  push    rdi
0x18001a1d9  sub     rsp, 88h
0x18001a1e0  mov     [r11+10h], rbx
0x18001a1e4  lea     rax, [r11+18h]
0x18001a1e8  mov     [r11-18h], rbp
0x18001a1ec  mov     rbx, rdx
0x18001a1ef  mov     [r11-20h], r12
0x18001a1f3  xor     r8d, r8d; TokenInformation
0x18001a1f6  xor     r12d, r12d
0x18001a1f9  mov     [r11-30h], r14
0x18001a1fd  mov     [r11-38h], r15
0x18001a201  mov     r14, rcx
0x18001a204  mov     rcx, [rcx]; TokenHandle
0x18001a207  mov     r15, r9
0x18001a20a  xor     r9d, r9d; TokenInformationLength
0x18001a20d  mov     [r11-48h], r12
0x18001a211  mov     edx, 3; TokenInformationClass
0x18001a216  mov     [r11+18h], r12d
0x18001a21a  mov     esi, r12d
0x18001a21d  mov     [r11-78h], rax
0x18001a221  mov     ebp, r12d
0x18001a224  call    cs:__imp_GetTokenInformation
0x18001a22b  nop     dword ptr [rax+rax+00h]
0x18001a230  test    eax, eax
0x18001a232  jz      short loc_18001A28B
0x18001a234  mov     edi, 8000FFFFh
0x18001a239  mov     rcx, [rsp+98h+hObject]; hObject
0x18001a23e  test    rcx, rcx
0x18001a241  jnz     loc_18001A4EB
0x18001a247  test    rbp, rbp
0x18001a24a  jnz     loc_18001A44E
0x18001a250  mov     r15, [rsp+98h+var_38]
0x18001a255  mov     r14, [rsp+98h+var_30]
0x18001a25a  mov     r12, [rsp+98h+var_20]
0x18001a25f  mov     rbp, [rsp+98h+var_18]
0x18001a267  mov     rbx, [rsp+98h+arg_8]
0x18001a26f  test    rsi, rsi
0x18001a272  jnz     short loc_18001A281
0x18001a274  mov     eax, edi
0x18001a276  add     rsp, 88h
0x18001a27d  pop     rdi
0x18001a27e  pop     rsi
0x18001a27f  retn
0x18001a281  mov     rcx, rsi; Block
0x18001a284  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a289  jmp     short loc_18001A274
0x18001a28b  call    cs:__imp_GetLastError
0x18001a292  nop     dword ptr [rax+rax+00h]
0x18001a297  cmp     eax, 7Ah ; 'z'
0x18001a29a  jnz     loc_18001A4B3
0x18001a2a0  mov     ecx, [rsp+98h+TokenInformationLength]; unsigned __int64
0x18001a2a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a2ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a2b3  mov     rsi, rax
0x18001a2b6  test    rax, rax
0x18001a2b9  jz      loc_18001A4D7
0x18001a2bf  mov     r9d, [rsp+98h+TokenInformationLength]; TokenInformationLength
0x18001a2c7  lea     rax, [rsp+98h+TokenInformationLength]
0x18001a2cf  mov     rcx, [r14]; TokenHandle
0x18001a2d2  mov     r8, rsi; TokenInformation
0x18001a2d5  mov     edx, 3; TokenInformationClass
0x18001a2da  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x18001a2df  call    cs:__imp_GetTokenInformation
0x18001a2e6  nop     dword ptr [rax+rax+00h]
0x18001a2eb  test    eax, eax
0x18001a2ed  jz      loc_18001A4B3
0x18001a2f3  mov     ecx, [rsi]
0x18001a2f5  mov     eax, 0Ch
0x18001a2fa  mul     rcx
0x18001a2fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a304  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a30b  cmovb   rax, rcx
0x18001a30f  mov     rcx, rax; unsigned __int64
0x18001a312  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a317  mov     rbp, rax
0x18001a31a  test    rax, rax
0x18001a31d  jz      loc_18001A4E1
0x18001a323  mov     edi, r12d
0x18001a326  cmp     [rsi], r12d
0x18001a329  jbe     loc_18001A3FE
0x18001a32f  mov     r8d, [rbx+8]
0x18001a333  mov     r10d, r12d
0x18001a336  mov     [rsp+98h+var_28], r13
0x18001a33b  mov     r13d, 1
0x18001a341  nop     dword ptr [rax+00h]
0x18001a345  nop     word ptr [rax+rax+00000000h]
0x18001a350  movsxd  rdx, dword ptr [rbx]
0x18001a353  xor     r11b, r11b
0x18001a356  mov     eax, r10d
0x18001a359  lea     rcx, [rax+rax*2]
0x18001a35d  mov     rax, rdx
0x18001a360  mov     dword ptr [rsp+98h+arg_0], eax
0x18001a367  lea     r9, ds:0[rcx*4]
0x18001a36f  mov     ecx, [r9+rsi+4]
0x18001a374  shr     rax, 20h
0x18001a378  mov     dword ptr [rsp+98h+arg_0+4], eax
0x18001a37f  cmp     ecx, edx
0x18001a381  jz      loc_18001A45B
0x18001a387  movsxd  rdx, dword ptr [rbx+4]
0x18001a38b  mov     rax, rdx
0x18001a38e  mov     dword ptr [rsp+98h+arg_0], eax
0x18001a395  shr     rax, 20h
0x18001a399  mov     dword ptr [rsp+98h+arg_0+4], eax
0x18001a3a0  cmp     ecx, edx
0x18001a3a2  jz      loc_18001A479
0x18001a3a8  movsxd  rax, r8d
0x18001a3ab  mov     dword ptr [rsp+98h+arg_0], eax
0x18001a3b2  shr     rax, 20h
0x18001a3b6  mov     dword ptr [rsp+98h+arg_0+4], eax
0x18001a3bd  cmp     ecx, r8d
0x18001a3c0  jz      loc_18001A497
0x18001a3c6  test    r11b, r11b
0x18001a3c9  jnz     short loc_18001A3ED
0x18001a3cb  movsd   xmm0, qword ptr [r9+rsi+4]
0x18001a3d2  mov     eax, edi
0x18001a3d4  inc     edi
0x18001a3d6  lea     rcx, [rax+rax*2]
0x18001a3da  movsd   qword ptr [rbp+rcx*4+0], xmm0
0x18001a3e0  mov     eax, [r9+rsi+0Ch]
0x18001a3e5  mov     [rbp+rcx*4+8], eax
0x18001a3e9  mov     r8d, [rbx+8]
0x18001a3ed  inc     r10d
0x18001a3f0  cmp     r10d, [rsi]
0x18001a3f3  jb      loc_18001A350
0x18001a3f9  mov     r13, [rsp+98h+var_28]
0x18001a3fe  mov     rcx, [r14]; ExistingTokenHandle
0x18001a401  lea     rax, [rsp+98h+hObject]
0x18001a406  mov     [rsp+98h+NewTokenHandle], rax; NewTokenHandle
0x18001a40b  xor     r9d, r9d; SidsToDisable
0x18001a40e  mov     [rsp+98h+SidsToRestrict], r12; SidsToRestrict
0x18001a413  xor     r8d, r8d; DisableSidCount
0x18001a416  mov     [rsp+98h+RestrictedSidCount], r12d; RestrictedSidCount
0x18001a41b  xor     edx, edx; Flags
0x18001a41d  mov     [rsp+98h+PrivilegesToDelete], rbp; PrivilegesToDelete
0x18001a422  mov     dword ptr [rsp+98h+ReturnLength], edi; DeletePrivilegeCount
0x18001a426  call    cs:__imp_CreateRestrictedToken
0x18001a42d  nop     dword ptr [rax+rax+00h]
0x18001a432  test    eax, eax
0x18001a434  jz      short loc_18001A4B3
0x18001a436  mov     rbx, [rsp+98h+hObject]
0x18001a43b  mov     rcx, r15
0x18001a43e  mov     edi, r12d
0x18001a441  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18001a446  mov     [r15], rbx
0x18001a449  mov     [rsp+98h+hObject], r12
0x18001a44e  mov     rcx, rbp; Block
0x18001a451  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a456  jmp     loc_18001A250
0x18001a45b  mov     rax, [rsp+98h+arg_0]
0x18001a463  shr     rax, 20h
0x18001a467  cmp     [r9+rsi+8], eax
0x18001a46c  movzx   r11d, r11b
0x18001a470  cmovz   r11d, r13d
0x18001a474  jmp     loc_18001A387
0x18001a479  mov     rax, [rsp+98h+arg_0]
0x18001a481  shr     rax, 20h
0x18001a485  cmp     [r9+rsi+8], eax
0x18001a48a  movzx   r11d, r11b
0x18001a48e  cmovz   r11d, r13d
0x18001a492  jmp     loc_18001A3A8
0x18001a497  mov     rax, [rsp+98h+arg_0]
0x18001a49f  shr     rax, 20h
0x18001a4a3  cmp     [r9+rsi+8], eax
0x18001a4a8  jnz     loc_18001A3C6
0x18001a4ae  jmp     loc_18001A3ED
0x18001a4b3  call    cs:__imp_GetLastError
0x18001a4ba  nop     dword ptr [rax+rax+00h]
0x18001a4bf  mov     edi, eax
0x18001a4c1  test    eax, eax
0x18001a4c3  jle     loc_18001A239
0x18001a4c9  movzx   edi, ax
0x18001a4cc  or      edi, 80070000h
0x18001a4d2  jmp     loc_18001A239
0x18001a4d7  mov     edi, 8007000Eh
0x18001a4dc  jmp     loc_18001A239
0x18001a4e1  mov     edi, 8007000Eh
0x18001a4e6  jmp     loc_18001A239
0x18001a4eb  call    cs:__imp_CloseHandle
0x18001a4f2  nop     dword ptr [rax+rax+00h]
0x18001a4f7  mov     [rsp+98h+hObject], r12
0x18001a4fc  jmp     loc_18001A247
```
