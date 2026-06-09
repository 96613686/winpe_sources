# __CodeAuthzpIdentifyOneCodeAuthzLevel

- ea: `0x180016e28`
- end: `0x180017457`
- name: `__CodeAuthzpIdentifyOneCodeAuthzLevel`
- size: `1583`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int128 *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800160c0`

## callees

- `0x180013f20`
- `0x180016e28`
- `0x180017460`
- `0x1800179fc`
- `0x1800187b8`
- `0x180018980`
- `0x180018f50`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x18001705b`
- `ntdll!NtClose` at `0x18001705b`
- `ntdll!RtlIsGenericTableEmpty` at `0x1800171d5`
- `ntdll!RtlIsGenericTableEmpty` at `0x1800171d5`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800171fe`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017244`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x1800171fe`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180017244`
- `ntdll!NtOpenFile` at `0x1800173b2`
- `ntdll!NtOpenFile` at `0x1800173b2`
- `ntdll!RtlCreateUnicodeString` at `0x1800173eb`
- `ntdll!RtlCreateUnicodeString` at `0x1800173eb`
- `ntdll!RtlFreeHeap` at `0x1800172c5`
- `ntdll!RtlFreeHeap` at `0x1800172c5`
- `ntdll!RtlFreeUnicodeString` at `0x180017040`
- `ntdll!RtlFreeUnicodeString` at `0x180017040`
- `ntdll!RtlInitUnicodeString` at `0x180017366`
- `ntdll!RtlInitUnicodeString` at `0x180017366`
- `KERNEL32!CloseHandle` at `0x180017431`
- `KERNEL32!CloseHandle` at `0x180017431`
- `KERNEL32!CreateFileW` at `0x180017102`
- `KERNEL32!CreateFileW` at `0x180017102`

## pseudocode

```c
__int64 __fastcall _CodeAuthzpIdentifyOneCodeAuthzLevel(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4, _DWORD *a5)
{
  int v8; // edi
  int v9; // edx
  char v10; // si
  __int64 v11; // rax
  int v12; // edi
  char *v13; // rcx
  PCWSTR *v14; // rbx
  int v15; // eax
  signed int v16; // ebx
  int v17; // eax
  int v18; // eax
  int *v19; // rcx
  int v20; // ecx
  __int128 v22; // xmm0
  const WCHAR *v23; // rcx
  HANDLE FileW; // rax
  int PackagePathForMoniker; // eax
  unsigned int v26; // ebx
  __int128 *v27; // rdi
  __int128 *v28; // rax
  __int64 v29; // rcx
  _DWORD *v30; // rax
  _DWORD *v31; // rcx
  int v32; // ecx
  __int128 v33; // xmm0
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  int v36; // [rsp+44h] [rbp-BCh] BYREF
  PVOID RestartKey; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v38; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch]
  __int64 v42; // [rsp+68h] [rbp-98h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  int v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h]
  char v48; // [rsp+D0h] [rbp-30h]
  char v49; // [rsp+D1h] [rbp-2Fh]
  __int128 v50; // [rsp+D2h] [rbp-2Eh]
  __int128 v51; // [rsp+112h] [rbp+12h]
  __int128 v52; // [rsp+122h] [rbp+22h]
  HANDLE Handle; // [rsp+158h] [rbp+58h]
  char v54; // [rsp+160h] [rbp+60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+168h] [rbp+68h] BYREF
  HANDLE hObject; // [rsp+180h] [rbp+80h]
  __int64 v57; // [rsp+188h] [rbp+88h]

  v42 = a2;
  memset_0(&v46, 0, 0xD0u);
  RestartKey = 0;
  v36 = 0;
  if ( !a3 || !a4 || !a5 )
    return (unsigned int)-1073741819;
  if ( !a1 )
    goto LABEL_20;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  if ( *(_DWORD *)a1 != 176 && *(_DWORD *)a1 != 136 )
    return (unsigned int)-1073741820;
  v8 = *(_DWORD *)(a1 + 4);
  v9 = 0;
  v41 = 0;
  v10 = 1;
  if ( (v8 & 0x20) != 0 )
  {
    if ( *(_DWORD *)a1 != 176 || v8 != 33 )
      return (unsigned int)-1073741811;
    v9 = 1;
    v41 = 1;
  }
  v11 = *(_QWORD *)(a1 + 96);
  v47 = a1;
  v46 = v8;
  v57 = v11;
  if ( v11 )
  {
    v32 = *(_DWORD *)(a1 + 92);
    if ( (unsigned int)(v32 - 1) <= 0x3F )
    {
      if ( *(_DWORD *)(a1 + 104) == 32771 )
      {
        if ( v32 == 16 )
        {
          v33 = *(_OWORD *)(a1 + 28);
          v48 = 1;
          v50 = v33;
        }
      }
      else if ( *(_DWORD *)(a1 + 104) == 32780 && v32 == 32 )
      {
        v34 = *(_OWORD *)(a1 + 28);
        v49 = 1;
        v35 = *(_OWORD *)(a1 + 44);
        v51 = v34;
        v52 = v35;
      }
    }
  }
  v12 = v8 & 0x1000;
  if ( v9 )
  {
    PackagePathForMoniker = GetPackagePathForMoniker(*(PCWSTR *)(a1 + 136));
    v16 = PackagePathForMoniker;
    if ( PackagePathForMoniker )
    {
      if ( PackagePathForMoniker > 0 )
        v16 = (unsigned __int16)PackagePathForMoniker | 0xC0070000;
      goto LABEL_25;
    }
    v16 = CodeAuthzFullyQualifyFilename(0);
    if ( v16 < 0 )
      goto LABEL_25;
  }
  else
  {
    v13 = *(char **)(a1 + 16);
    v14 = (PCWSTR *)(a1 + 8);
    if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v23 = *v14;
      if ( *v14 )
      {
        RestartKey = 0;
        if ( v12 )
        {
          memset(&ObjectAttributes.Attributes + 1, 0, 20);
          DestinationString = 0;
          IoStatusBlock = 0;
          *(&ObjectAttributes.Length + 1) = 0;
          RtlInitUnicodeString(&DestinationString, v23);
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.ObjectName = &DestinationString;
          FileW = NtOpenFile(&RestartKey, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0x40u) >= 0
                ? RestartKey
                : 0LL;
        }
        else
        {
          FileW = CreateFileW(v23, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        }
        if ( FileW && FileW != (HANDLE)-1LL )
        {
          Handle = FileW;
          v54 = 1;
        }
      }
    }
    else
    {
      Handle = v13;
      v54 = 0;
    }
    if ( (int)CodeAuthzFullyQualifyFilename(Handle) < 0 && *v14 && !v12 && !RtlCreateUnicodeString(&UnicodeString, *v14) )
    {
      v16 = -1073741801;
      goto LABEL_25;
    }
    v15 = _CodeAuthzpCheckIdentityCertificateRules(&v46, v42, &v38);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v31 = v38;
      *a3 = v38;
      *a5 = *v31;
      v22 = xmmword_180088D48;
      goto LABEL_37;
    }
    if ( v15 != -1073741275 )
      goto LABEL_25;
    v17 = _CodeAuthzpCheckIdentityHashRules(&v46, &v38, &v39, &v36);
    v16 = v17;
    if ( v17 >= 0 )
    {
LABEL_46:
      *a3 = v38;
LABEL_36:
      *a5 = v36;
      v22 = *v39;
LABEL_37:
      *a4 = v22;
      goto LABEL_25;
    }
    if ( v17 != -1073741275 )
      goto LABEL_25;
  }
  v18 = _CodeAuthzpCheckIdentityPathRules(
          (unsigned int)&v46,
          (unsigned int)&v38,
          (unsigned int)&v40,
          (unsigned int)&v39,
          (__int64)&v36);
  v16 = v18;
  if ( v18 >= 0 )
  {
    if ( !v40 && v36 )
      goto LABEL_18;
    goto LABEL_46;
  }
  if ( v18 == -1073741275 )
  {
LABEL_18:
    if ( !v41 )
    {
      RestartKey = 0;
      if ( !v47 )
      {
        v16 = -1073741811;
        goto LABEL_25;
      }
      if ( (v46 & 0x10) != 0 && !RtlIsGenericTableEmpty(&g_CodeIdentitiesTable) )
      {
        v26 = 0;
        RestartKey = 0;
        v27 = 0;
        v28 = (__int128 *)RtlEnumerateGenericTableWithoutSplaying(&g_CodeIdentitiesTable, &RestartKey);
        if ( v28 )
        {
          do
          {
            if ( *((_DWORD *)v28 + 4) == 3
              && *((_DWORD *)v28 + 8) == *(_DWORD *)(v47 + 24)
              && (v10 || *((_DWORD *)v28 + 5) < v26) )
            {
              v26 = *((_DWORD *)v28 + 5);
              v27 = v28;
              v10 = 0;
            }
            v28 = (__int128 *)RtlEnumerateGenericTableWithoutSplaying(&g_CodeIdentitiesTable, &RestartKey);
          }
          while ( v28 );
          if ( !v10 )
          {
            v30 = (_DWORD *)CodeAuthzLevelObjpLookupByLevelId(v29, v26);
            if ( v30 )
            {
              if ( !v38 || *v30 < *v38 )
              {
                v38 = v30;
                v39 = v27;
                v36 = *((_DWORD *)v27 + 5);
              }
            }
          }
        }
      }
    }
    if ( !v38 )
    {
LABEL_20:
      v19 = (int *)g_DefaultCodeLevel;
      if ( g_DefaultCodeLevel )
      {
        *a3 = g_DefaultCodeLevel;
        v20 = *v19;
        if ( v20 == 0x40000 && (g_DefaultCodeLevelFlags & 0x1000) != 0 )
          v20 = 0;
        *a5 = v20;
        v16 = 0;
        *a4 = xmmword_180088BD8;
      }
      else
      {
        v16 = -1073741275;
      }
      goto LABEL_25;
    }
    v16 = 0;
    *a3 = v38;
    goto LABEL_36;
  }
LABEL_25:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v54 && Handle )
    NtClose(Handle);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180016e28  push    rbp
0x180016e2a  push    rbx
0x180016e2b  push    rsi
0x180016e2c  push    rdi
0x180016e2d  push    r12
0x180016e2f  push    r13
0x180016e31  push    r14
0x180016e33  push    r15
0x180016e35  lea     rbp, [rsp-0A8h]
0x180016e3d  sub     rsp, 1A8h
0x180016e44  mov     rax, cs:__security_cookie
0x180016e4b  xor     rax, rsp
0x180016e4e  mov     [rbp+0E0h+var_50], rax
0x180016e55  mov     r12, [rbp+0E0h+arg_20]
0x180016e5c  mov     r13, r8
0x180016e5f  mov     [rsp+1E0h+var_178], rdx
0x180016e64  mov     rbx, rcx
0x180016e67  xor     edx, edx; Val
0x180016e69  lea     rcx, [rbp+0E0h+var_120]; void *
0x180016e6d  mov     r8d, 0D0h; Size
0x180016e73  mov     r15, r9
0x180016e76  call    memset_0
0x180016e7b  xor     r14d, r14d
0x180016e7e  mov     [rsp+1E0h+RestartKey], r14
0x180016e83  mov     [rsp+1E0h+var_19C], r14d
0x180016e88  test    r13, r13
0x180016e8b  jz      loc_18001744D
0x180016e91  test    r15, r15
0x180016e94  jz      loc_18001744D
0x180016e9a  test    r12, r12
0x180016e9d  jz      loc_18001744D
0x180016ea3  test    rbx, rbx
0x180016ea6  jz      loc_180016FE3
0x180016eac  mov     eax, 0B0h
0x180016eb1  mov     [rsp+1E0h+var_190], r14
0x180016eb6  mov     [rsp+1E0h+var_188], r14
0x180016ebb  mov     [rsp+1E0h+var_180], r14d
0x180016ec0  cmp     [rbx], eax
0x180016ec2  jnz     loc_180017096
0x180016ec8  mov     edi, [rbx+4]
0x180016ecb  xor     edx, edx
0x180016ecd  mov     [rsp+1E0h+var_17C], edx
0x180016ed1  lea     esi, [rdx+1]
0x180016ed4  test    dil, 20h
0x180016ed8  jnz     loc_180017194
0x180016ede  mov     rax, [rbx+60h]
0x180016ee2  mov     [rbp+0E0h+var_118], rbx
0x180016ee6  mov     [rbp+0E0h+var_120], edi
0x180016ee9  mov     [rbp+0E0h+var_58], rax
0x180016ef0  test    rax, rax
0x180016ef3  jnz     loc_1800172E0
0x180016ef9  and     edi, 1000h
0x180016eff  setnz   [rsp+1E0h+var_1A0]
0x180016f04  test    edx, edx
0x180016f06  jnz     loc_18001714E
0x180016f0c  mov     rcx, [rbx+10h]
0x180016f10  add     rbx, 8
0x180016f14  lea     rax, [rcx-1]
0x180016f18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016f1c  ja      loc_1800170C9
0x180016f22  mov     [rbp+0E0h+Handle], rcx
0x180016f26  mov     [rbp+0E0h+var_80], r14b
0x180016f2a  mov     r8, [rbx]
0x180016f2d  lea     r9, [rbp+0E0h+UnicodeString]
0x180016f31  mov     dl, [rsp+1E0h+var_1A0]
0x180016f35  mov     rcx, [rbp+0E0h+Handle]; FileHandle
0x180016f39  call    CodeAuthzFullyQualifyFilename
0x180016f3e  test    eax, eax
0x180016f40  js      loc_1800173D3
0x180016f46  mov     rdx, [rsp+1E0h+var_178]
0x180016f4b  lea     r8, [rsp+1E0h+var_190]
0x180016f50  lea     rcx, [rbp+0E0h+var_120]
0x180016f54  call    __CodeAuthzpCheckIdentityCertificateRules
0x180016f59  mov     ebx, eax
0x180016f5b  test    eax, eax
0x180016f5d  jns     loc_180017298
0x180016f63  mov     edi, 0C0000225h
0x180016f68  cmp     eax, edi
0x180016f6a  jnz     loc_180017025
0x180016f70  lea     r9, [rsp+1E0h+var_19C]
0x180016f75  lea     r8, [rsp+1E0h+var_188]
0x180016f7a  lea     rdx, [rsp+1E0h+var_190]
0x180016f7f  lea     rcx, [rbp+0E0h+var_120]
0x180016f83  call    __CodeAuthzpCheckIdentityHashRules
0x180016f88  mov     ebx, eax
0x180016f8a  test    eax, eax
0x180016f8c  jns     loc_180017140
0x180016f92  cmp     eax, edi
0x180016f94  jnz     loc_180017025
0x180016f9a  lea     rax, [rsp+1E0h+var_19C]
0x180016f9f  lea     r9, [rsp+1E0h+var_188]
0x180016fa4  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rax
0x180016fa9  lea     r8, [rsp+1E0h+var_180]
0x180016fae  lea     rdx, [rsp+1E0h+var_190]
0x180016fb3  lea     rcx, [rbp+0E0h+var_120]
0x180016fb7  call    __CodeAuthzpCheckIdentityPathRules
0x180016fbc  mov     ebx, eax
0x180016fbe  test    eax, eax
0x180016fc0  jns     loc_18001712E
0x180016fc6  cmp     eax, edi
0x180016fc8  jnz     short loc_180017025
0x180016fca  cmp     [rsp+1E0h+var_17C], 0
0x180016fcf  jz      loc_1800171B0
0x180016fd5  mov     rcx, [rsp+1E0h+var_190]
0x180016fda  test    rcx, rcx
0x180016fdd  jnz     loc_1800170A9
0x180016fe3  mov     rcx, cs:g_DefaultCodeLevel
0x180016fea  test    rcx, rcx
0x180016fed  jz      loc_180017427
0x180016ff3  mov     [r13+0], rcx
0x180016ff7  mov     ecx, [rcx]
0x180016ff9  cmp     ecx, 40000h
0x180016fff  jnz     short loc_180017013
0x180017001  test    cs:g_DefaultCodeLevelFlags, 1000h
0x18001700b  mov     eax, 0
0x180017010  cmovnz  ecx, eax
0x180017013  mov     [r12], ecx
0x180017017  xor     ebx, ebx
0x180017019  movups  xmm0, cs:xmmword_180088BD8
0x180017020  movdqu  xmmword ptr [r15], xmm0
0x180017025  mov     rcx, [rbp+0E0h+hObject]; hObject
0x18001702c  test    rcx, rcx
0x18001702f  jnz     loc_180017431
0x180017035  cmp     [rbp+0E0h+UnicodeString.Buffer], 0
0x18001703a  jz      short loc_18001704C
0x18001703c  lea     rcx, [rbp+0E0h+UnicodeString]; UnicodeString
0x180017040  call    cs:__imp_RtlFreeUnicodeString
0x180017047  nop     dword ptr [rax+rax+00h]
0x18001704c  cmp     [rbp+0E0h+var_80], 0
0x180017050  jz      short loc_180017067
0x180017052  mov     rcx, [rbp+0E0h+Handle]; Handle
0x180017056  test    rcx, rcx
0x180017059  jz      short loc_180017067
0x18001705b  call    cs:__imp_NtClose
0x180017062  nop     dword ptr [rax+rax+00h]
0x180017067  test    r14, r14
0x18001706a  jnz     loc_1800172B3
0x180017070  mov     eax, ebx
0x180017072  mov     rcx, [rbp+0E0h+var_50]
0x180017079  xor     rcx, rsp; StackCookie
0x18001707c  call    __security_check_cookie
0x180017081  add     rsp, 1A8h
0x180017088  pop     r15
0x18001708a  pop     r14
0x18001708c  pop     r13
0x18001708e  pop     r12
0x180017090  pop     rdi
0x180017091  pop     rsi
0x180017092  pop     rbx
0x180017093  pop     rbp
0x180017094  retn
0x180017096  cmp     dword ptr [rbx], 88h
0x18001709c  jz      loc_180016EC8
0x1800170a2  mov     ebx, 0C0000004h
0x1800170a7  jmp     short loc_180017070
0x1800170a9  xor     ebx, ebx
0x1800170ab  mov     [r13+0], rcx
0x1800170af  mov     eax, [rsp+1E0h+var_19C]
0x1800170b3  mov     [r12], eax
0x1800170b7  mov     rax, [rsp+1E0h+var_188]
0x1800170bc  movups  xmm0, xmmword ptr [rax]
0x1800170bf  movdqu  xmmword ptr [r15], xmm0
0x1800170c4  jmp     loc_180017025
0x1800170c9  mov     rcx, [rbx]; lpFileName
0x1800170cc  test    rcx, rcx
0x1800170cf  jz      loc_180016F2A
0x1800170d5  mov     [rsp+1E0h+RestartKey], r14
0x1800170da  test    edi, edi
0x1800170dc  jnz     loc_180017342
0x1800170e2  mov     [rsp+1E0h+hTemplateFile], r14; hTemplateFile
0x1800170e7  xor     r9d, r9d; lpSecurityAttributes
0x1800170ea  mov     [rsp+1E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800170f2  mov     r8d, esi; dwShareMode
0x1800170f5  mov     edx, 80000000h; dwDesiredAccess
0x1800170fa  mov     [rsp+1E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180017102  call    cs:__imp_CreateFileW
0x180017109  nop     dword ptr [rax+rax+00h]
0x18001710e  test    rax, rax
0x180017111  jz      loc_180016F2A
0x180017117  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001711b  jz      loc_180016F2A
0x180017121  mov     [rbp+0E0h+Handle], rax
0x180017125  mov     [rbp+0E0h+var_80], sil
0x180017129  jmp     loc_180016F2A
0x18001712e  cmp     [rsp+1E0h+var_180], 0
0x180017133  jnz     short loc_180017140
0x180017135  cmp     [rsp+1E0h+var_19C], 0
0x18001713a  jnz     loc_180016FCA
0x180017140  mov     rax, [rsp+1E0h+var_190]
0x180017145  mov     [r13+0], rax
0x180017149  jmp     loc_1800170AF
0x18001714e  mov     rcx, [rbx+88h]; packageFullName
0x180017155  lea     rdx, [rsp+1E0h+RestartKey]
0x18001715a  call    GetPackagePathForMoniker
0x18001715f  mov     r14, [rsp+1E0h+RestartKey]
0x180017164  mov     ebx, eax
0x180017166  test    eax, eax
0x180017168  jnz     loc_180017409
0x18001716e  mov     dl, [rsp+1E0h+var_1A0]
0x180017172  lea     r9, [rbp+0E0h+UnicodeString]
0x180017176  mov     r8, r14
0x180017179  xor     ecx, ecx; FileHandle
0x18001717b  call    CodeAuthzFullyQualifyFilename
0x180017180  mov     ebx, eax
0x180017182  test    eax, eax
0x180017184  js      loc_180017025
0x18001718a  mov     edi, 0C0000225h
0x18001718f  jmp     loc_180016F9A
0x180017194  cmp     [rbx], eax
0x180017196  jnz     loc_1800172D6
0x18001719c  cmp     edi, 21h ; '!'
0x18001719f  jnz     loc_1800172D6
0x1800171a5  mov     edx, esi
0x1800171a7  mov     [rsp+1E0h+var_17C], edx
0x1800171ab  jmp     loc_180016EDE
0x1800171b0  cmp     [rbp+0E0h+var_118], 0
0x1800171b5  mov     [rsp+1E0h+RestartKey], 0
0x1800171be  jz      loc_18001741D
0x1800171c4  test    byte ptr [rbp+0E0h+var_120], 10h
0x1800171c8  jz      loc_180016FD5
0x1800171ce  lea     rcx, g_CodeIdentitiesTable; Table
0x1800171d5  call    cs:__imp_RtlIsGenericTableEmpty
0x1800171dc  nop     dword ptr [rax+rax+00h]
0x1800171e1  test    al, al
0x1800171e3  jnz     loc_180016FD5
0x1800171e9  xor     ebx, ebx
0x1800171eb  lea     rdx, [rsp+1E0h+RestartKey]; RestartKey
0x1800171f0  lea     rcx, g_CodeIdentitiesTable; Table
0x1800171f7  mov     [rsp+1E0h+RestartKey], rbx
0x1800171fc  xor     edi, edi
0x1800171fe  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180017205  nop     dword ptr [rax+rax+00h]
0x18001720a  test    rax, rax
0x18001720d  jz      loc_180016FD5
0x180017213  cmp     dword ptr [rax+10h], 3
0x180017217  jnz     short loc_180017238
0x180017219  mov     rcx, [rbp+0E0h+var_118]
0x18001721d  mov     edx, [rcx+18h]
0x180017220  cmp     [rax+20h], edx
0x180017223  jnz     short loc_180017238
0x180017225  test    sil, sil
0x180017228  jnz     short loc_18001722F
0x18001722a  cmp     [rax+14h], ebx
0x18001722d  jnb     short loc_180017238
0x18001722f  mov     ebx, [rax+14h]
0x180017232  mov     rdi, rax
0x180017235  xor     sil, sil
0x180017238  lea     rdx, [rsp+1E0h+RestartKey]; RestartKey
0x18001723d  lea     rcx, g_CodeIdentitiesTable; Table
0x180017244  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x18001724b  nop     dword ptr [rax+rax+00h]
0x180017250  test    rax, rax
0x180017253  jnz     short loc_180017213
0x180017255  test    sil, sil
0x180017258  jnz     loc_180016FD5
0x18001725e  mov     edx, ebx
0x180017260  call    CodeAuthzLevelObjpLookupByLevelId
0x180017265  test    rax, rax
0x180017268  jz      loc_180016FD5
0x18001726e  mov     rcx, [rsp+1E0h+var_190]
0x180017273  test    rcx, rcx
0x180017276  jz      short loc_180017282
0x180017278  mov     ecx, [rcx]
0x18001727a  cmp     [rax], ecx
0x18001727c  jnb     loc_180016FD5
0x180017282  mov     [rsp+1E0h+var_190], rax
0x180017287  mov     [rsp+1E0h+var_188], rdi
0x18001728c  mov     eax, [rdi+14h]
0x18001728f  mov     [rsp+1E0h+var_19C], eax
0x180017293  jmp     loc_180016FD5
0x180017298  mov     rcx, [rsp+1E0h+var_190]
0x18001729d  mov     [r13+0], rcx
0x1800172a1  mov     ecx, [rcx]
0x1800172a3  mov     [r12], ecx
0x1800172a7  movups  xmm0, cs:xmmword_180088D48
0x1800172ae  jmp     loc_1800170BF
0x1800172b3  mov     rcx, gs:60h
0x1800172bc  mov     r8, r14; P
0x1800172bf  xor     edx, edx; Flags
0x1800172c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800172c5  call    cs:__imp_RtlFreeHeap
0x1800172cc  nop     dword ptr [rax+rax+00h]
0x1800172d1  jmp     loc_180017070
0x1800172d6  mov     ebx, 0C000000Dh
0x1800172db  jmp     loc_180017070
0x1800172e0  mov     ecx, [rbx+5Ch]
0x1800172e3  lea     eax, [rcx-1]
0x1800172e6  cmp     eax, 3Fh ; '?'
0x1800172e9  ja      loc_180016EF9
0x1800172ef  cmp     dword ptr [rbx+68h], 8003h
0x1800172f6  jnz     short loc_180017313
0x1800172f8  cmp     ecx, 10h
0x1800172fb  jnz     loc_180016EF9
0x180017301  movups  xmm0, xmmword ptr [rbx+1Ch]
0x180017305  mov     [rbp+0E0h+var_110], sil
0x180017309  movdqu  [rbp+0E0h+var_10E], xmm0
0x18001730e  jmp     loc_180016EF9
0x180017313  cmp     dword ptr [rbx+68h], 800Ch
0x18001731a  jnz     loc_180016EF9
0x180017320  cmp     ecx, 20h ; ' '
  ... truncated ...
```
