# EfsxStreamExtractDpapiNgFileKey(_EFSX_DATUM_FEK_INFO const *,_EFSX_DATUM_BLOB *,_EFS_FILE_KEY * *)

- ea: `0x18007ba08`
- end: `0x18007bd22`
- name: `?EfsxStreamExtractDpapiNgFileKey@@YAKPEBU_EFSX_DATUM_FEK_INFO@@PEAU_EFSX_DATUM_BLOB@@PEAPEAU_EFS_FILE_KEY@@@Z`
- size: `794`
- prototype: `unsigned int __fastcall(const struct _EFSX_DATUM_FEK_INFO *, struct _EFSX_DATUM_BLOB *, struct _EFS_FILE_KEY **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007c2ac`

## callees

- `0x18004a89c`
- `0x180063698`
- `0x180066d30`
- `0x180066fd0`
- `0x180069c6c`
- `0x18007a724`
- `0x18007ba08`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bc92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bce3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bc92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bce3`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18007bcf6`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18007bcf6`
- `ncrypt!NCryptUnprotectSecret` at `0x18007bac8`
- `ncrypt!NCryptUnprotectSecret` at `0x18007bac8`
- `ncrypt!NCryptGetProtectionDescriptorInfo` at `0x18007baf3`
- `ncrypt!NCryptGetProtectionDescriptorInfo` at `0x18007baf3`
- `bcrypt!BCryptDestroyKey` at `0x18007bca1`
- `bcrypt!BCryptDestroyKey` at `0x18007bca1`
- `bcrypt!BCryptImportKey` at `0x18007bbd7`
- `bcrypt!BCryptImportKey` at `0x18007bbd7`
- `ntdll!RtlNtStatusToDosError` at `0x18007bbe3`
- `ntdll!RtlNtStatusToDosError` at `0x18007bbe3`
- `ext-ms-win-feclient-encryptedfile-l1-1-2!EdpFree` at `0x18007bcd4`
- `ext-ms-win-feclient-encryptedfile-l1-1-2!EdpFree` at `0x18007bcd4`
- `ext-ms-win-feclient-encryptedfile-l1-1-2!EdpQueryCredServiceInfo` at `0x18007bb28`
- `ext-ms-win-feclient-encryptedfile-l1-1-2!EdpQueryCredServiceInfo` at `0x18007bb28`

## pseudocode

```c
__int64 __fastcall EfsxStreamExtractDpapiNgFileKey(
        const struct _EFSX_DATUM_FEK_INFO *a1,
        struct _EFSX_DATUM_BLOB *a2,
        struct _EFS_FILE_KEY **a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned __int16 v9; // ax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  PUCHAR v13; // rcx
  __int64 v14; // rax
  PUCHAR v15; // rcx
  __int64 v16; // rax
  char pbKeyObject; // [rsp+20h] [rbp-60h]
  PUCHAR v19; // [rsp+50h] [rbp-30h] BYREF
  PUCHAR pbInput; // [rsp+58h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-20h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-10h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF
  ULONG cbInput; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+48h] BYREF

  v24 = 0;
  hMem = 0;
  pbInput = 0;
  cbInput = 0;
  *a3 = 0;
  phKey = 0;
  v19 = 0;
  v26 = 0;
  v22 = 0;
  v6 = CEfsTokenManager::ModifyCallerContext((CEfsTokenManager *)&v24, 1);
  v7 = v6;
  if ( v6 )
  {
    pbKeyObject = -78;
LABEL_3:
    v8 = v6;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v8, 27, pbKeyObject);
    goto LABEL_23;
  }
  v9 = 0;
  if ( *(_WORD *)a2 >= 0xCu )
    v9 = *(_WORD *)a2 - 12;
  if ( (int)NCryptUnprotectSecret(&v22, 64, (char *)a2 + 12, v9, 0, 0, &pbInput, &cbInput) < 0 )
  {
    v8 = 87;
    pbKeyObject = -66;
    v7 = 87;
    goto LABEL_4;
  }
  if ( (int)NCryptGetProtectionDescriptorInfo(v22, 0, 1, &hMem) < 0 )
  {
    v8 = 87;
    pbKeyObject = -53;
    v7 = 87;
    goto LABEL_4;
  }
  v10 = EdpQueryCredServiceInfo(10, 0, hMem, 0, &v26);
  if ( v10 < 0 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v10, 27, 212);
    v7 = 5;
    pbKeyObject = -43;
    v8 = 5;
    goto LABEL_4;
  }
  v7 = EfsxLibAllocZero(g_cbAesObjectLen, (void **)&v19);
  if ( v7 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, g_cbAesObjectLen, 27, 220);
    goto LABEL_23;
  }
  v11 = BCryptImportKey(g_hAesAlg, 0, L"KeyDataBlob", &phKey, v19, g_cbAesObjectLen, pbInput, cbInput, 0);
  if ( v11 < 0 )
  {
    v6 = RtlNtStatusToDosError(v11);
    v7 = v6;
    pbKeyObject = -24;
    goto LABEL_3;
  }
  v6 = EfsxStreamDecryptFekInfoWithFmk(a1, &phKey, &v19, a3);
  v7 = v6;
  if ( v6 )
  {
    pbKeyObject = -13;
    goto LABEL_3;
  }
  *(_QWORD *)(*((_QWORD *)*a3 + 1) + 16LL) = *(_QWORD *)(v26 + 8);
  *(_QWORD *)(*((_QWORD *)*a3 + 1) + 24LL) = *(_QWORD *)(v26 + 16);
  *(_BYTE *)(*((_QWORD *)*a3 + 1) + 32LL) = *(_BYTE *)(v26 + 24);
  if ( *(_BYTE *)(v26 + 25) )
  {
    v12 = *((_QWORD *)*a3 + 1);
    if ( *(_DWORD *)(v12 + 8) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  }
LABEL_23:
  v13 = pbInput;
  if ( pbInput )
  {
    v14 = cbInput;
    if ( cbInput )
    {
      do
      {
        *v13++ = 0;
        --v14;
      }
      while ( v14 );
      v13 = pbInput;
    }
    LocalFree(v13);
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  v15 = v19;
  if ( v19 )
  {
    v16 = g_cbAesObjectLen;
    if ( g_cbAesObjectLen )
    {
      do
      {
        *v15++ = 0;
        --v16;
      }
      while ( v16 );
      v15 = v19;
    }
    EdppAuditSiteFree(v15);
  }
  EdpFree(v26);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v22 )
  {
    NCryptCloseProtectionDescriptor();
    v22 = 0;
  }
  CEfsTokenManager::RevertToOriginalToken((CEfsTokenManager *)&v24);
  return v7;
}

```

## disassembly

```asm
0x18007ba08  mov     [rsp-28h+arg_0], rbx
0x18007ba0d  push    rbp
0x18007ba0e  push    rsi
0x18007ba0f  push    rdi
0x18007ba10  push    r14
0x18007ba12  push    r15
0x18007ba14  mov     rbp, rsp
0x18007ba17  sub     rsp, 80h
0x18007ba1e  xor     r15d, r15d
0x18007ba21  mov     rsi, rdx
0x18007ba24  mov     r14, rcx
0x18007ba27  mov     [rbp+var_8], r15
0x18007ba2b  lea     rcx, [rbp+var_8]; this
0x18007ba2f  mov     [rbp+hMem], r15
0x18007ba33  mov     rdi, r8
0x18007ba36  mov     [rbp+var_28], r15
0x18007ba3a  lea     edx, [r15+1]; unsigned int
0x18007ba3e  mov     [rbp+arg_10], r15d
0x18007ba42  mov     [r8], r15
0x18007ba45  mov     [rbp+phKey], r15
0x18007ba49  mov     [rbp+var_30], r15
0x18007ba4d  mov     [rbp+arg_18], r15
0x18007ba51  mov     [rbp+var_18], r15
0x18007ba55  call    ?ModifyCallerContext@CEfsTokenManager@@QEAAKK@Z; CEfsTokenManager::ModifyCallerContext(ulong)
0x18007ba5a  mov     ebx, eax
0x18007ba5c  test    eax, eax
0x18007ba5e  jz      short loc_18007BA89
0x18007ba60  mov     dword ptr [rsp+80h+pbKeyObject], 11B2h
0x18007ba68  mov     r8d, eax
0x18007ba6b  lea     rdx, EFS_API_ERROR
0x18007ba72  mov     rcx, cs:g_hPublisher
0x18007ba79  mov     r9d, 1Bh
0x18007ba7f  call    fnEfsLogTrace1
0x18007ba84  jmp     loc_18007BC71
0x18007ba89  movzx   ecx, word ptr [rsi]
0x18007ba8c  lea     r8, [rsi+0Ch]
0x18007ba90  sub     cx, 0Ch
0x18007ba94  mov     eax, r15d
0x18007ba97  cmp     word ptr [rsi], 0Ch
0x18007ba9b  mov     edx, 40h ; '@'
0x18007baa0  cmovnb  ax, cx
0x18007baa4  lea     rcx, [rbp+var_18]
0x18007baa8  movzx   r9d, ax
0x18007baac  lea     rax, [rbp+arg_10]
0x18007bab0  mov     qword ptr [rsp+80h+cbInput], rax
0x18007bab5  lea     rax, [rbp+var_28]
0x18007bab9  mov     [rsp+80h+pbInput], rax
0x18007babe  mov     qword ptr [rsp+80h+cbKeyObject], r15
0x18007bac3  mov     [rsp+80h+pbKeyObject], r15
0x18007bac8  call    cs:__imp_NCryptUnprotectSecret
0x18007bace  test    eax, eax
0x18007bad0  jns     short loc_18007BAE5
0x18007bad2  mov     r8d, 57h ; 'W'
0x18007bad8  mov     dword ptr [rsp+80h+pbKeyObject], 11BEh
0x18007bae0  mov     ebx, r8d
0x18007bae3  jmp     short loc_18007BA6B
0x18007bae5  mov     rcx, [rbp+var_18]
0x18007bae9  lea     r9, [rbp+hMem]
0x18007baed  xor     edx, edx
0x18007baef  lea     r8d, [rdx+1]
0x18007baf3  call    cs:__imp_NCryptGetProtectionDescriptorInfo
0x18007baf9  test    eax, eax
0x18007bafb  jns     short loc_18007BB13
0x18007bafd  mov     r8d, 57h ; 'W'
0x18007bb03  mov     dword ptr [rsp+80h+pbKeyObject], 11CBh
0x18007bb0b  mov     ebx, r8d
0x18007bb0e  jmp     loc_18007BA6B
0x18007bb13  mov     r8, [rbp+hMem]
0x18007bb17  lea     rax, [rbp+arg_18]
0x18007bb1b  xor     edx, edx
0x18007bb1d  mov     [rsp+80h+pbKeyObject], rax
0x18007bb22  xor     r9d, r9d
0x18007bb25  lea     ecx, [rdx+0Ah]
0x18007bb28  call    cs:__imp_EdpQueryCredServiceInfo
0x18007bb2e  test    eax, eax
0x18007bb30  jns     short loc_18007BB6B
0x18007bb32  mov     rcx, cs:g_hPublisher
0x18007bb39  lea     rdx, EFS_API_ERROR
0x18007bb40  mov     r9d, 1Bh
0x18007bb46  mov     dword ptr [rsp+80h+pbKeyObject], 11D4h
0x18007bb4e  mov     r8d, eax
0x18007bb51  call    fnEfsLogTrace1
0x18007bb56  mov     ebx, 5
0x18007bb5b  mov     dword ptr [rsp+80h+pbKeyObject], 11D5h
0x18007bb63  mov     r8d, ebx
0x18007bb66  jmp     loc_18007BA6B
0x18007bb6b  mov     ecx, cs:?g_cbAesObjectLen@@3KA; unsigned __int64
0x18007bb71  lea     rdx, [rbp+var_30]; void **
0x18007bb75  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x18007bb7a  mov     ebx, eax
0x18007bb7c  test    eax, eax
0x18007bb7e  jz      short loc_18007BB9B
0x18007bb80  mov     r8d, cs:?g_cbAesObjectLen@@3KA; ulong g_cbAesObjectLen
0x18007bb87  lea     rdx, EFS_ERROR_MEMORY
0x18007bb8e  mov     dword ptr [rsp+80h+pbKeyObject], 11DCh
0x18007bb96  jmp     loc_18007BA72
0x18007bb9b  mov     eax, [rbp+arg_10]
0x18007bb9e  lea     r9, [rbp+phKey]; phKey
0x18007bba2  mov     rcx, cs:?g_hAesAlg@@3PEAXEA; hAlgorithm
0x18007bba9  lea     r8, pszBlobType; "KeyDataBlob"
0x18007bbb0  mov     [rsp+80h+dwFlags], r15d; dwFlags
0x18007bbb5  xor     edx, edx; hImportKey
0x18007bbb7  mov     [rsp+80h+cbInput], eax; cbInput
0x18007bbbb  mov     rax, [rbp+var_28]
0x18007bbbf  mov     [rsp+80h+pbInput], rax; pbInput
0x18007bbc4  mov     eax, cs:?g_cbAesObjectLen@@3KA; ulong g_cbAesObjectLen
0x18007bbca  mov     [rsp+80h+cbKeyObject], eax; cbKeyObject
0x18007bbce  mov     rax, [rbp+var_30]
0x18007bbd2  mov     [rsp+80h+pbKeyObject], rax; pbKeyObject
0x18007bbd7  call    cs:__imp_BCryptImportKey
0x18007bbdd  test    eax, eax
0x18007bbdf  jns     short loc_18007BBF8
0x18007bbe1  mov     ecx, eax; Status
0x18007bbe3  call    cs:__imp_RtlNtStatusToDosError
0x18007bbe9  mov     ebx, eax
0x18007bbeb  mov     dword ptr [rsp+80h+pbKeyObject], 11E8h
0x18007bbf3  jmp     loc_18007BA68
0x18007bbf8  mov     r9, rdi; struct _EFS_FILE_KEY **
0x18007bbfb  lea     r8, [rbp+var_30]; unsigned __int8 **
0x18007bbff  lea     rdx, [rbp+phKey]; void **
0x18007bc03  mov     rcx, r14; struct _EFSX_DATUM_FEK_INFO *
0x18007bc06  call    ?EfsxStreamDecryptFekInfoWithFmk@@YAKPEBU_EFSX_DATUM_FEK_INFO@@PEAPEAXPEAPEAEPEAPEAU_EFS_FILE_KEY@@@Z; EfsxStreamDecryptFekInfoWithFmk(_EFSX_DATUM_FEK_INFO const *,void * *,uchar * *,_EFS_FILE_KEY * *)
0x18007bc0b  mov     ebx, eax
0x18007bc0d  test    eax, eax
0x18007bc0f  jz      short loc_18007BC1E
0x18007bc11  mov     dword ptr [rsp+80h+pbKeyObject], 11F3h
0x18007bc19  jmp     loc_18007BA68
0x18007bc1e  mov     rax, [rdi]
0x18007bc21  mov     rdx, [rax+8]
0x18007bc25  mov     rax, [rbp+arg_18]
0x18007bc29  mov     rcx, [rax+8]
0x18007bc2d  mov     [rdx+10h], rcx
0x18007bc31  mov     rax, [rdi]
0x18007bc34  mov     rdx, [rax+8]
0x18007bc38  mov     rax, [rbp+arg_18]
0x18007bc3c  mov     rcx, [rax+10h]
0x18007bc40  mov     [rdx+18h], rcx
0x18007bc44  mov     rax, [rdi]
0x18007bc47  mov     rdx, [rax+8]
0x18007bc4b  mov     rax, [rbp+arg_18]
0x18007bc4f  mov     cl, [rax+18h]
0x18007bc52  mov     [rdx+20h], cl
0x18007bc55  mov     rax, [rbp+arg_18]
0x18007bc59  cmp     [rax+19h], r15b
0x18007bc5d  jz      short loc_18007BC71
0x18007bc5f  mov     rax, [rdi]
0x18007bc62  mov     rcx, [rax+8]
0x18007bc66  cmp     dword ptr [rcx+8], 1
0x18007bc6a  jz      short loc_18007BC71
0x18007bc6c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "((*FileKey)->Fek->IVGenerationMode == EFS_AES_IV_GEN_BITLOCKER)")
0x18007bc71  mov     rcx, [rbp+var_28]
0x18007bc75  test    rcx, rcx
0x18007bc78  jz      short loc_18007BC98
0x18007bc7a  mov     eax, [rbp+arg_10]
0x18007bc7d  test    rax, rax
0x18007bc80  jz      short loc_18007BC92
0x18007bc82  mov     [rcx], r15b
0x18007bc85  inc     rcx
0x18007bc88  sub     rax, 1
0x18007bc8c  jnz     short loc_18007BC82
0x18007bc8e  mov     rcx, [rbp+var_28]; hMem
0x18007bc92  call    cs:__imp_LocalFree
0x18007bc98  mov     rcx, [rbp+phKey]; hKey
0x18007bc9c  test    rcx, rcx
0x18007bc9f  jz      short loc_18007BCA7
0x18007bca1  call    cs:__imp_BCryptDestroyKey
0x18007bca7  mov     rcx, [rbp+var_30]
0x18007bcab  test    rcx, rcx
0x18007bcae  jz      short loc_18007BCD0
0x18007bcb0  mov     eax, cs:?g_cbAesObjectLen@@3KA; ulong g_cbAesObjectLen
0x18007bcb6  test    rax, rax
0x18007bcb9  jz      short loc_18007BCCB
0x18007bcbb  mov     [rcx], r15b
0x18007bcbe  inc     rcx
0x18007bcc1  sub     rax, 1
0x18007bcc5  jnz     short loc_18007BCBB
0x18007bcc7  mov     rcx, [rbp+var_30]; void *
0x18007bccb  call    ?EdppAuditSiteFree@@YAXPEAX@Z; EdppAuditSiteFree(void *)
0x18007bcd0  mov     rcx, [rbp+arg_18]
0x18007bcd4  call    cs:__imp_EdpFree
0x18007bcda  mov     rcx, [rbp+hMem]; hMem
0x18007bcde  test    rcx, rcx
0x18007bce1  jz      short loc_18007BCED
0x18007bce3  call    cs:__imp_LocalFree
0x18007bce9  mov     [rbp+hMem], r15
0x18007bced  mov     rcx, [rbp+var_18]
0x18007bcf1  test    rcx, rcx
0x18007bcf4  jz      short loc_18007BD00
0x18007bcf6  call    cs:__imp_NCryptCloseProtectionDescriptor
0x18007bcfc  mov     [rbp+var_18], r15
0x18007bd00  lea     rcx, [rbp+var_8]; this
0x18007bd04  call    ?RevertToOriginalToken@CEfsTokenManager@@QEAAXXZ; CEfsTokenManager::RevertToOriginalToken(void)
0x18007bd09  mov     eax, ebx
0x18007bd0b  mov     rbx, [rsp+80h+arg_0]
0x18007bd13  add     rsp, 80h
0x18007bd1a  pop     r15
0x18007bd1c  pop     r14
0x18007bd1e  pop     rdi
0x18007bd1f  pop     rsi
0x18007bd20  pop     rbp
0x18007bd21  retn
```
