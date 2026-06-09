# __CodeAuthzpIdentifyOneCodeAuthzLevel

- ea: `0x1800118c0`
- end: `0x180011eac`
- name: `__CodeAuthzpIdentifyOneCodeAuthzLevel`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180010c00`

## callees

- `0x18000e4fc`
- `0x1800118c0`
- `0x180011eb4`
- `0x1800123dc`
- `0x18001318c`
- `0x18001333c`
- `0x1800138c4`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x180011aed`
- `ntdll!NtClose` at `0x180011aed`
- `ntdll!RtlIsGenericTableEmpty` at `0x180011c5a`
- `ntdll!RtlIsGenericTableEmpty` at `0x180011c5a`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180011c7d`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180011cbd`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180011c7d`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180011cbd`
- `ntdll!NtOpenFile` at `0x180011e19`
- `ntdll!NtOpenFile` at `0x180011e19`
- `ntdll!RtlCreateUnicodeString` at `0x180011e4c`
- `ntdll!RtlCreateUnicodeString` at `0x180011e4c`
- `ntdll!RtlFreeHeap` at `0x180011d38`
- `ntdll!RtlFreeHeap` at `0x180011d38`
- `ntdll!RtlFreeUnicodeString` at `0x180011ad8`
- `ntdll!RtlFreeUnicodeString` at `0x180011ad8`
- `ntdll!RtlInitUnicodeString` at `0x180011dd3`
- `ntdll!RtlInitUnicodeString` at `0x180011dd3`
- `KERNEL32!CloseHandle` at `0x180011e8c`
- `KERNEL32!CloseHandle` at `0x180011e8c`
- `KERNEL32!CreateFileW` at `0x180011b8d`
- `KERNEL32!CreateFileW` at `0x180011b8d`

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
  const WCHAR **v14; // rbx
  int v15; // eax
  int v16; // ebx
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
  char v36; // [rsp+40h] [rbp-C0h]
  unsigned int v37; // [rsp+44h] [rbp-BCh] BYREF
  PVOID RestartKey; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v39; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+64h] [rbp-9Ch]
  __int64 v43; // [rsp+68h] [rbp-98h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  int v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h]
  char v49; // [rsp+D0h] [rbp-30h]
  char v50; // [rsp+D1h] [rbp-2Fh]
  __int128 v51; // [rsp+D2h] [rbp-2Eh]
  __int128 v52; // [rsp+112h] [rbp+12h]
  __int128 v53; // [rsp+122h] [rbp+22h]
  HANDLE Handle; // [rsp+158h] [rbp+58h]
  char v55; // [rsp+160h] [rbp+60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+168h] [rbp+68h] BYREF
  HANDLE hObject; // [rsp+180h] [rbp+80h]
  __int64 v58; // [rsp+188h] [rbp+88h]

  v43 = a2;
  memset_0(&v47, 0, 0xD0u);
  RestartKey = 0;
  v37 = 0;
  if ( !a3 || !a4 || !a5 )
    return (unsigned int)-1073741819;
  if ( !a1 )
    goto LABEL_20;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( *(_DWORD *)a1 != 176 && *(_DWORD *)a1 != 136 )
    return (unsigned int)-1073741820;
  v8 = *(_DWORD *)(a1 + 4);
  v9 = 0;
  v42 = 0;
  v10 = 1;
  if ( (v8 & 0x20) != 0 )
  {
    if ( *(_DWORD *)a1 != 176 || v8 != 33 )
      return (unsigned int)-1073741811;
    v9 = 1;
    v42 = 1;
  }
  v11 = *(_QWORD *)(a1 + 96);
  v48 = a1;
  v47 = v8;
  v58 = v11;
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
          v49 = 1;
          v51 = v33;
        }
      }
      else if ( *(_DWORD *)(a1 + 104) == 32780 && v32 == 32 )
      {
        v34 = *(_OWORD *)(a1 + 28);
        v50 = 1;
        v35 = *(_OWORD *)(a1 + 44);
        v52 = v34;
        v53 = v35;
      }
    }
  }
  v12 = v8 & 0x1000;
  v36 = v12 != 0;
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
    v16 = CodeAuthzFullyQualifyFilename(0, v36, (const WCHAR *)RestartKey, &UnicodeString);
    if ( v16 < 0 )
      goto LABEL_25;
  }
  else
  {
    v13 = *(char **)(a1 + 16);
    v14 = (const WCHAR **)(a1 + 8);
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
          v55 = 1;
        }
      }
    }
    else
    {
      Handle = v13;
      v55 = 0;
    }
    if ( (int)CodeAuthzFullyQualifyFilename(Handle, v36, *v14, &UnicodeString) < 0
      && *v14
      && !v12
      && !RtlCreateUnicodeString(&UnicodeString, *v14) )
    {
      v16 = -1073741801;
      goto LABEL_25;
    }
    v15 = _CodeAuthzpCheckIdentityCertificateRules(&v47, v43, &v39);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v31 = v39;
      *a3 = v39;
      *a5 = *v31;
      v22 = xmmword_18007ABD8;
      goto LABEL_37;
    }
    if ( v15 != -1073741275 )
      goto LABEL_25;
    v17 = _CodeAuthzpCheckIdentityHashRules(&v47, &v39, &v40, &v37);
    v16 = v17;
    if ( v17 >= 0 )
    {
LABEL_46:
      *a3 = v39;
LABEL_36:
      *a5 = v37;
      v22 = *v40;
LABEL_37:
      *a4 = v22;
      goto LABEL_25;
    }
    if ( v17 != -1073741275 )
      goto LABEL_25;
  }
  v18 = _CodeAuthzpCheckIdentityPathRules((__int64)&v47, (__int64 *)&v39, &v41, &v40, &v37);
  v16 = v18;
  if ( v18 >= 0 )
  {
    if ( !v41 && v37 )
      goto LABEL_18;
    goto LABEL_46;
  }
  if ( v18 == -1073741275 )
  {
LABEL_18:
    if ( !v42 )
    {
      RestartKey = 0;
      if ( !v48 )
      {
        v16 = -1073741811;
        goto LABEL_25;
      }
      if ( (v47 & 0x10) != 0 && !RtlIsGenericTableEmpty(&g_CodeIdentitiesTable) )
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
              && *((_DWORD *)v28 + 8) == *(_DWORD *)(v48 + 24)
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
              if ( !v39 || *v30 < *v39 )
              {
                v39 = v30;
                v40 = v27;
                v37 = *((_DWORD *)v27 + 5);
              }
            }
          }
        }
      }
    }
    if ( !v39 )
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
        *a4 = xmmword_18007AA70;
      }
      else
      {
        v16 = -1073741275;
      }
      goto LABEL_25;
    }
    v16 = 0;
    *a3 = v39;
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
  if ( v55 && Handle )
    NtClose(Handle);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800118c0  push    rbp
0x1800118c2  push    rbx
0x1800118c3  push    rsi
0x1800118c4  push    rdi
0x1800118c5  push    r12
0x1800118c7  push    r13
0x1800118c9  push    r14
0x1800118cb  push    r15
0x1800118cd  lea     rbp, [rsp-0A8h]
0x1800118d5  sub     rsp, 1A8h
0x1800118dc  mov     rax, cs:__security_cookie
0x1800118e3  xor     rax, rsp
0x1800118e6  mov     [rbp+0E0h+var_50], rax
0x1800118ed  mov     r12, [rbp+0E0h+arg_20]
0x1800118f4  mov     r13, r8
0x1800118f7  mov     [rsp+1E0h+var_178], rdx
0x1800118fc  mov     rbx, rcx
0x1800118ff  xor     edx, edx; Val
0x180011901  lea     rcx, [rbp+0E0h+var_120]; void *
0x180011905  mov     r8d, 0D0h; Size
0x18001190b  mov     r15, r9
0x18001190e  call    memset_0
0x180011913  xor     r14d, r14d
0x180011916  mov     [rsp+1E0h+RestartKey], r14
0x18001191b  mov     [rsp+1E0h+var_19C], r14d
0x180011920  test    r13, r13
0x180011923  jz      loc_180011EA2
0x180011929  test    r15, r15
0x18001192c  jz      loc_180011EA2
0x180011932  test    r12, r12
0x180011935  jz      loc_180011EA2
0x18001193b  test    rbx, rbx
0x18001193e  jz      loc_180011A7B
0x180011944  mov     eax, 0B0h
0x180011949  mov     [rsp+1E0h+var_190], r14
0x18001194e  mov     [rsp+1E0h+var_188], r14
0x180011953  mov     [rsp+1E0h+var_180], r14d
0x180011958  cmp     [rbx], eax
0x18001195a  jnz     loc_180011B21
0x180011960  mov     edi, [rbx+4]
0x180011963  xor     edx, edx
0x180011965  mov     [rsp+1E0h+var_17C], edx
0x180011969  lea     esi, [rdx+1]
0x18001196c  test    dil, 20h
0x180011970  jnz     loc_180011C19
0x180011976  mov     rax, [rbx+60h]
0x18001197a  mov     [rbp+0E0h+var_118], rbx
0x18001197e  mov     [rbp+0E0h+var_120], edi
0x180011981  mov     [rbp+0E0h+var_58], rax
0x180011988  test    rax, rax
0x18001198b  jnz     loc_180011D4D
0x180011991  and     edi, 1000h
0x180011997  setnz   [rsp+1E0h+var_1A0]
0x18001199c  test    edx, edx
0x18001199e  jnz     loc_180011BD3
0x1800119a4  mov     rcx, [rbx+10h]
0x1800119a8  add     rbx, 8
0x1800119ac  lea     rax, [rcx-1]
0x1800119b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800119b4  ja      loc_180011B54
0x1800119ba  mov     [rbp+0E0h+Handle], rcx
0x1800119be  mov     [rbp+0E0h+var_80], r14b
0x1800119c2  mov     r8, [rbx]
0x1800119c5  lea     r9, [rbp+0E0h+UnicodeString]
0x1800119c9  mov     dl, [rsp+1E0h+var_1A0]
0x1800119cd  mov     rcx, [rbp+0E0h+Handle]; FileHandle
0x1800119d1  call    CodeAuthzFullyQualifyFilename
0x1800119d6  test    eax, eax
0x1800119d8  js      loc_180011E34
0x1800119de  mov     rdx, [rsp+1E0h+var_178]
0x1800119e3  lea     r8, [rsp+1E0h+var_190]
0x1800119e8  lea     rcx, [rbp+0E0h+var_120]
0x1800119ec  call    __CodeAuthzpCheckIdentityCertificateRules
0x1800119f1  mov     ebx, eax
0x1800119f3  test    eax, eax
0x1800119f5  jns     loc_180011D0B
0x1800119fb  mov     edi, 0C0000225h
0x180011a00  cmp     eax, edi
0x180011a02  jnz     loc_180011ABD
0x180011a08  lea     r9, [rsp+1E0h+var_19C]
0x180011a0d  lea     r8, [rsp+1E0h+var_188]
0x180011a12  lea     rdx, [rsp+1E0h+var_190]
0x180011a17  lea     rcx, [rbp+0E0h+var_120]
0x180011a1b  call    __CodeAuthzpCheckIdentityHashRules
0x180011a20  mov     ebx, eax
0x180011a22  test    eax, eax
0x180011a24  jns     loc_180011BC5
0x180011a2a  cmp     eax, edi
0x180011a2c  jnz     loc_180011ABD
0x180011a32  lea     rax, [rsp+1E0h+var_19C]
0x180011a37  lea     r9, [rsp+1E0h+var_188]
0x180011a3c  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rax
0x180011a41  lea     r8, [rsp+1E0h+var_180]
0x180011a46  lea     rdx, [rsp+1E0h+var_190]
0x180011a4b  lea     rcx, [rbp+0E0h+var_120]
0x180011a4f  call    __CodeAuthzpCheckIdentityPathRules
0x180011a54  mov     ebx, eax
0x180011a56  test    eax, eax
0x180011a58  jns     loc_180011BB3
0x180011a5e  cmp     eax, edi
0x180011a60  jnz     short loc_180011ABD
0x180011a62  cmp     [rsp+1E0h+var_17C], 0
0x180011a67  jz      loc_180011C35
0x180011a6d  mov     rcx, [rsp+1E0h+var_190]
0x180011a72  test    rcx, rcx
0x180011a75  jnz     loc_180011B34
0x180011a7b  mov     rcx, cs:g_DefaultCodeLevel
0x180011a82  test    rcx, rcx
0x180011a85  jz      loc_180011E82
0x180011a8b  mov     [r13+0], rcx
0x180011a8f  mov     ecx, [rcx]
0x180011a91  cmp     ecx, 40000h
0x180011a97  jnz     short loc_180011AAB
0x180011a99  test    cs:g_DefaultCodeLevelFlags, 1000h
0x180011aa3  mov     eax, 0
0x180011aa8  cmovnz  ecx, eax
0x180011aab  mov     [r12], ecx
0x180011aaf  xor     ebx, ebx
0x180011ab1  movups  xmm0, cs:xmmword_18007AA70
0x180011ab8  movdqu  xmmword ptr [r15], xmm0
0x180011abd  mov     rcx, [rbp+0E0h+hObject]; hObject
0x180011ac4  test    rcx, rcx
0x180011ac7  jnz     loc_180011E8C
0x180011acd  cmp     [rbp+0E0h+UnicodeString.Buffer], 0
0x180011ad2  jz      short loc_180011ADE
0x180011ad4  lea     rcx, [rbp+0E0h+UnicodeString]; UnicodeString
0x180011ad8  call    cs:__imp_RtlFreeUnicodeString
0x180011ade  cmp     [rbp+0E0h+var_80], 0
0x180011ae2  jz      short loc_180011AF3
0x180011ae4  mov     rcx, [rbp+0E0h+Handle]; Handle
0x180011ae8  test    rcx, rcx
0x180011aeb  jz      short loc_180011AF3
0x180011aed  call    cs:__imp_NtClose
0x180011af3  test    r14, r14
0x180011af6  jnz     loc_180011D26
0x180011afc  mov     eax, ebx
0x180011afe  mov     rcx, [rbp+0E0h+var_50]
0x180011b05  xor     rcx, rsp; StackCookie
0x180011b08  call    __security_check_cookie
0x180011b0d  add     rsp, 1A8h
0x180011b14  pop     r15
0x180011b16  pop     r14
0x180011b18  pop     r13
0x180011b1a  pop     r12
0x180011b1c  pop     rdi
0x180011b1d  pop     rsi
0x180011b1e  pop     rbx
0x180011b1f  pop     rbp
0x180011b20  retn
0x180011b21  cmp     dword ptr [rbx], 88h
0x180011b27  jz      loc_180011960
0x180011b2d  mov     ebx, 0C0000004h
0x180011b32  jmp     short loc_180011AFC
0x180011b34  xor     ebx, ebx
0x180011b36  mov     [r13+0], rcx
0x180011b3a  mov     eax, [rsp+1E0h+var_19C]
0x180011b3e  mov     [r12], eax
0x180011b42  mov     rax, [rsp+1E0h+var_188]
0x180011b47  movups  xmm0, xmmword ptr [rax]
0x180011b4a  movdqu  xmmword ptr [r15], xmm0
0x180011b4f  jmp     loc_180011ABD
0x180011b54  mov     rcx, [rbx]; lpFileName
0x180011b57  test    rcx, rcx
0x180011b5a  jz      loc_1800119C2
0x180011b60  mov     [rsp+1E0h+RestartKey], r14
0x180011b65  test    edi, edi
0x180011b67  jnz     loc_180011DAF
0x180011b6d  mov     [rsp+1E0h+hTemplateFile], r14; hTemplateFile
0x180011b72  xor     r9d, r9d; lpSecurityAttributes
0x180011b75  mov     [rsp+1E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180011b7d  mov     r8d, esi; dwShareMode
0x180011b80  mov     edx, 80000000h; dwDesiredAccess
0x180011b85  mov     [rsp+1E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180011b8d  call    cs:__imp_CreateFileW
0x180011b93  test    rax, rax
0x180011b96  jz      loc_1800119C2
0x180011b9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011ba0  jz      loc_1800119C2
0x180011ba6  mov     [rbp+0E0h+Handle], rax
0x180011baa  mov     [rbp+0E0h+var_80], sil
0x180011bae  jmp     loc_1800119C2
0x180011bb3  cmp     [rsp+1E0h+var_180], 0
0x180011bb8  jnz     short loc_180011BC5
0x180011bba  cmp     [rsp+1E0h+var_19C], 0
0x180011bbf  jnz     loc_180011A62
0x180011bc5  mov     rax, [rsp+1E0h+var_190]
0x180011bca  mov     [r13+0], rax
0x180011bce  jmp     loc_180011B3A
0x180011bd3  mov     rcx, [rbx+88h]; packageFullName
0x180011bda  lea     rdx, [rsp+1E0h+RestartKey]
0x180011bdf  call    GetPackagePathForMoniker
0x180011be4  mov     r14, [rsp+1E0h+RestartKey]
0x180011be9  mov     ebx, eax
0x180011beb  test    eax, eax
0x180011bed  jnz     loc_180011E64
0x180011bf3  mov     dl, [rsp+1E0h+var_1A0]
0x180011bf7  lea     r9, [rbp+0E0h+UnicodeString]
0x180011bfb  mov     r8, r14
0x180011bfe  xor     ecx, ecx; FileHandle
0x180011c00  call    CodeAuthzFullyQualifyFilename
0x180011c05  mov     ebx, eax
0x180011c07  test    eax, eax
0x180011c09  js      loc_180011ABD
0x180011c0f  mov     edi, 0C0000225h
0x180011c14  jmp     loc_180011A32
0x180011c19  cmp     [rbx], eax
0x180011c1b  jnz     loc_180011D43
0x180011c21  cmp     edi, 21h ; '!'
0x180011c24  jnz     loc_180011D43
0x180011c2a  mov     edx, esi
0x180011c2c  mov     [rsp+1E0h+var_17C], edx
0x180011c30  jmp     loc_180011976
0x180011c35  cmp     [rbp+0E0h+var_118], 0
0x180011c3a  mov     [rsp+1E0h+RestartKey], 0
0x180011c43  jz      loc_180011E78
0x180011c49  test    byte ptr [rbp+0E0h+var_120], 10h
0x180011c4d  jz      loc_180011A6D
0x180011c53  lea     rcx, g_CodeIdentitiesTable; Table
0x180011c5a  call    cs:__imp_RtlIsGenericTableEmpty
0x180011c60  test    al, al
0x180011c62  jnz     loc_180011A6D
0x180011c68  xor     ebx, ebx
0x180011c6a  lea     rdx, [rsp+1E0h+RestartKey]; RestartKey
0x180011c6f  lea     rcx, g_CodeIdentitiesTable; Table
0x180011c76  mov     [rsp+1E0h+RestartKey], rbx
0x180011c7b  xor     edi, edi
0x180011c7d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180011c83  test    rax, rax
0x180011c86  jz      loc_180011A6D
0x180011c8c  cmp     dword ptr [rax+10h], 3
0x180011c90  jnz     short loc_180011CB1
0x180011c92  mov     rcx, [rbp+0E0h+var_118]
0x180011c96  mov     edx, [rcx+18h]
0x180011c99  cmp     [rax+20h], edx
0x180011c9c  jnz     short loc_180011CB1
0x180011c9e  test    sil, sil
0x180011ca1  jnz     short loc_180011CA8
0x180011ca3  cmp     [rax+14h], ebx
0x180011ca6  jnb     short loc_180011CB1
0x180011ca8  mov     ebx, [rax+14h]
0x180011cab  mov     rdi, rax
0x180011cae  xor     sil, sil
0x180011cb1  lea     rdx, [rsp+1E0h+RestartKey]; RestartKey
0x180011cb6  lea     rcx, g_CodeIdentitiesTable; Table
0x180011cbd  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180011cc3  test    rax, rax
0x180011cc6  jnz     short loc_180011C8C
0x180011cc8  test    sil, sil
0x180011ccb  jnz     loc_180011A6D
0x180011cd1  mov     edx, ebx
0x180011cd3  call    CodeAuthzLevelObjpLookupByLevelId
0x180011cd8  test    rax, rax
0x180011cdb  jz      loc_180011A6D
0x180011ce1  mov     rcx, [rsp+1E0h+var_190]
0x180011ce6  test    rcx, rcx
0x180011ce9  jz      short loc_180011CF5
0x180011ceb  mov     ecx, [rcx]
0x180011ced  cmp     [rax], ecx
0x180011cef  jnb     loc_180011A6D
0x180011cf5  mov     [rsp+1E0h+var_190], rax
0x180011cfa  mov     [rsp+1E0h+var_188], rdi
0x180011cff  mov     eax, [rdi+14h]
0x180011d02  mov     [rsp+1E0h+var_19C], eax
0x180011d06  jmp     loc_180011A6D
0x180011d0b  mov     rcx, [rsp+1E0h+var_190]
0x180011d10  mov     [r13+0], rcx
0x180011d14  mov     ecx, [rcx]
0x180011d16  mov     [r12], ecx
0x180011d1a  movups  xmm0, cs:xmmword_18007ABD8
0x180011d21  jmp     loc_180011B4A
0x180011d26  mov     rcx, gs:60h
0x180011d2f  mov     r8, r14; P
0x180011d32  xor     edx, edx; Flags
0x180011d34  mov     rcx, [rcx+30h]; HeapHandle
0x180011d38  call    cs:__imp_RtlFreeHeap
0x180011d3e  jmp     loc_180011AFC
0x180011d43  mov     ebx, 0C000000Dh
0x180011d48  jmp     loc_180011AFC
0x180011d4d  mov     ecx, [rbx+5Ch]
0x180011d50  lea     eax, [rcx-1]
0x180011d53  cmp     eax, 3Fh ; '?'
0x180011d56  ja      loc_180011991
0x180011d5c  cmp     dword ptr [rbx+68h], 8003h
0x180011d63  jnz     short loc_180011D80
0x180011d65  cmp     ecx, 10h
0x180011d68  jnz     loc_180011991
0x180011d6e  movups  xmm0, xmmword ptr [rbx+1Ch]
0x180011d72  mov     [rbp+0E0h+var_110], sil
0x180011d76  movdqu  [rbp+0E0h+var_10E], xmm0
0x180011d7b  jmp     loc_180011991
0x180011d80  cmp     dword ptr [rbx+68h], 800Ch
0x180011d87  jnz     loc_180011991
0x180011d8d  cmp     ecx, 20h ; ' '
0x180011d90  jnz     loc_180011991
0x180011d96  movups  xmm0, xmmword ptr [rbx+1Ch]
0x180011d9a  mov     [rbp+0E0h+var_10F], sil
0x180011d9e  movups  xmm1, xmmword ptr [rbx+2Ch]
0x180011da2  movups  [rbp+0E0h+var_CE], xmm0
0x180011da6  movups  [rbp+0E0h+var_BE], xmm1
0x180011daa  jmp     loc_180011991
  ... truncated ...
```
