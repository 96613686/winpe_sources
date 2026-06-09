# BaseSrvSaveIniFileMapping

- ea: `0x180005200`
- end: `0x18000593c`
- name: `BaseSrvSaveIniFileMapping`
- size: `1852`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004d70`
- `0x180006170`

## callees

- `0x180005200`
- `0x180005950`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000531d`
- `ntdll!RtlAllocateHeap` at `0x1800053ad`
- `ntdll!RtlAllocateHeap` at `0x1800055d0`
- `ntdll!RtlAllocateHeap` at `0x180005774`
- `ntdll!RtlAllocateHeap` at `0x180005870`
- `ntdll!RtlAllocateHeap` at `0x18000531d`
- `ntdll!RtlAllocateHeap` at `0x1800053ad`
- `ntdll!RtlAllocateHeap` at `0x1800055d0`
- `ntdll!RtlAllocateHeap` at `0x180005774`
- `ntdll!RtlAllocateHeap` at `0x180005870`
- `ntdll!NtOpenKey` at `0x180005576`
- `ntdll!NtOpenKey` at `0x180005576`
- `ntdll!NtClose` at `0x180005608`
- `ntdll!NtClose` at `0x180005608`
- `ntdll!RtlFreeHeap` at `0x180005899`
- `ntdll!RtlFreeHeap` at `0x180005915`
- `ntdll!RtlFreeHeap` at `0x180005899`
- `ntdll!RtlFreeHeap` at `0x180005915`
- `ntdll!_wcsnicmp` at `0x180005650`
- `ntdll!_wcsnicmp` at `0x1800058d4`
- `ntdll!_wcsnicmp` at `0x180005650`
- `ntdll!_wcsnicmp` at `0x1800058d4`
- `ntdll!RtlCopyUnicodeString` at `0x180005357`
- `ntdll!RtlCopyUnicodeString` at `0x180005447`
- `ntdll!RtlCopyUnicodeString` at `0x18000547a`
- `ntdll!RtlCopyUnicodeString` at `0x1800056b8`
- `ntdll!RtlCopyUnicodeString` at `0x1800057de`
- `ntdll!RtlCopyUnicodeString` at `0x180005357`
- `ntdll!RtlCopyUnicodeString` at `0x180005447`
- `ntdll!RtlCopyUnicodeString` at `0x18000547a`
- `ntdll!RtlCopyUnicodeString` at `0x1800056b8`
- `ntdll!RtlCopyUnicodeString` at `0x1800057de`
- `ntdll!NtEnumerateKey` at `0x1800054df`
- `ntdll!NtEnumerateKey` at `0x1800054df`
- `ntdll!RtlEqualUnicodeString` at `0x180005837`
- `ntdll!RtlEqualUnicodeString` at `0x180005837`
- `ntdll!NtEnumerateValueKey` at `0x1800052a2`
- `ntdll!NtEnumerateValueKey` at `0x1800056f3`
- `ntdll!NtEnumerateValueKey` at `0x1800052a2`
- `ntdll!NtEnumerateValueKey` at `0x1800056f3`
- `ntdll!RtlInitUnicodeString` at `0x18000526b`
- `ntdll!RtlInitUnicodeString` at `0x180005810`
- `ntdll!RtlInitUnicodeString` at `0x18000526b`
- `ntdll!RtlInitUnicodeString` at `0x180005810`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveIniFileMapping(__int64 a1, void *a2)
{
  void *v2; // rdi
  __int64 v3; // rsi
  ULONG i; // r12d
  NTSTATUS v5; // ebx
  _QWORD *v6; // rax
  _QWORD *j; // rbx
  char *Heap; // rax
  char *v9; // rdi
  __int64 v10; // rbx
  _QWORD *v11; // rax
  _QWORD *k; // r14
  char *v13; // rsi
  const wchar_t *v14; // rbx
  unsigned __int64 v15; // rax
  int v16; // r15d
  const WCHAR *v17; // rdx
  ULONG n; // r15d
  NTSTATUS v19; // eax
  _QWORD *v21; // rax
  _QWORD *ii; // rbx
  char *v23; // rax
  char *v24; // r13
  wchar_t v25; // cx
  ULONG jj; // r14d
  __int64 v27; // rbx
  _QWORD *v28; // rax
  _QWORD *kk; // rdi
  char *v30; // rsi
  __int64 *m; // rdi
  char *v32; // rbx
  char *v33; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+58h] [rbp-A8h]
  UNICODE_STRING String1; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING v40; // [rsp+70h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v45; // [rsp+D4h] [rbp-2Ch]
  unsigned int v46; // [rsp+D8h] [rbp-28h]
  USHORT v47; // [rsp+DCh] [rbp-24h]
  USHORT v48; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v49[1002]; // [rsp+E4h] [rbp-1Ch] BYREF
  __int16 v50; // [rsp+4CEh] [rbp+3CEh]

  v35 = a2;
  v36 = a1;
  v2 = a2;
  KeyHandle = 0;
  v3 = a1;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  SourceString = 0;
  v40 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  for ( i = 0; ; ++i )
  {
    v5 = NtEnumerateValueKey(v2, i, KeyValueFullInformation, KeyValueInformation, 0x400u, &ResultLength);
    v50 = 0;
    if ( v5 < 0 )
      break;
    SourceString.Buffer = (PWSTR)v49;
    SourceString.Length = v48;
    SourceString.MaximumLength = v48;
    if ( v45 != 1 )
      continue;
    if ( v48 )
    {
      v6 = *(_QWORD **)(v3 + 24);
      for ( j = (_QWORD *)(v3 + 24); v6; v6 = (_QWORD *)*v6 )
        j = v6;
    }
    else
    {
      j = (_QWORD *)(v3 + 32);
    }
    Heap = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v48 + 40LL);
    v9 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    if ( SourceString.Length )
    {
      *((_QWORD *)Heap + 2) = Heap + 40;
      *((_WORD *)Heap + 5) = SourceString.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), &SourceString);
    }
    *j = v9;
    v10 = v46;
    if ( DestinationString.Length )
    {
      v11 = (_QWORD *)*((_QWORD *)v9 + 3);
      for ( k = v9 + 24; v11; v11 = (_QWORD *)*v11 )
        k = v11;
    }
    else
    {
      k = v9 + 32;
    }
    v13 = (char *)RtlAllocateHeap(
                    BaseSrvSharedHeap,
                    (BaseSrvSharedTag + 0x40000) | 8,
                    DestinationString.MaximumLength + 40LL);
    if ( !v13 )
      return (unsigned int)-1073741801;
    v14 = (const wchar_t *)&KeyValueInformation[v10];
    v15 = -1;
    v16 = 0;
    String1 = 0;
    do
      ++v15;
    while ( v14[v15] );
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v15 )
          goto LABEL_19;
        v25 = *v14;
        if ( *v14 != 33 )
          break;
        v16 |= 1u;
        ++v14;
        --v15;
      }
      if ( v25 == 35 )
      {
        v16 |= 2u;
        goto LABEL_59;
      }
      if ( v25 != 64 )
        break;
      v16 |= 4u;
LABEL_59:
      ++v14;
      --v15;
    }
    if ( v15 < 4 )
      goto LABEL_19;
    if ( !_wcsnicmp(v14, L"USR:", 4u) )
    {
      v16 |= 0x80000000;
LABEL_55:
      v14 += 4;
      goto LABEL_19;
    }
    if ( !_wcsnicmp(v14, L"SYS:", 4u) )
    {
      v16 |= 0x40000000u;
      goto LABEL_55;
    }
LABEL_19:
    if ( (v16 & 0xC0000000) != 0 )
    {
      if ( *v14 != 92 )
      {
LABEL_78:
        v17 = v14;
        goto LABEL_79;
      }
LABEL_91:
      v5 = -1073741773;
LABEL_85:
      RtlFreeHeap(BaseSrvSharedHeap, 0, v13);
      if ( v5 != -1073741801 )
      {
        v2 = v35;
        goto LABEL_29;
      }
      return (unsigned int)v5;
    }
    if ( *v14 == 92 )
      goto LABEL_78;
    if ( *v14 )
      goto LABEL_91;
    v17 = 0;
LABEL_79:
    RtlInitUnicodeString(&String1, v17);
    for ( m = &BaseSrvMappingTargetHead; ; m = (__int64 *)v32 )
    {
      v32 = (char *)*m;
      if ( !*m )
        break;
      if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v32 + 8), 1u) )
        goto LABEL_25;
    }
    v33 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, String1.MaximumLength + 24LL);
    v32 = v33;
    if ( !v33 )
    {
      v5 = -1073741801;
      goto LABEL_85;
    }
    *m = (__int64)v33;
    if ( String1.Length )
    {
      *((_QWORD *)v33 + 2) = v33 + 24;
      *((_WORD *)v33 + 4) = 0;
      *((_WORD *)v33 + 5) = String1.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(v33 + 8), &String1);
    }
LABEL_25:
    *((_DWORD *)v13 + 6) = v16;
    *((_QWORD *)v13 + 4) = v32;
    if ( DestinationString.Length )
    {
      *((_QWORD *)v13 + 2) = v13 + 40;
      *((_WORD *)v13 + 5) = DestinationString.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(v13 + 8), &DestinationString);
    }
    v2 = v35;
    *k = v13;
    if ( !SourceString.Length )
      *((_DWORD *)v13 + 6) |= 0x20000000u;
LABEL_29:
    v3 = v36;
  }
  if ( v5 == -2147483622 )
  {
    for ( n = 0; ; ++n )
    {
      v19 = NtEnumerateKey(v2, n, KeyBasicInformation, KeyValueInformation, 0x400u, &ResultLength);
      v5 = v19;
      if ( v19 >= 0 )
      {
        ObjectAttributes.Length = 48;
        v40.Buffer = &v48;
        v40.Length = v47;
        v40.MaximumLength = v47;
        ObjectAttributes.RootDirectory = v2;
        ObjectAttributes.ObjectName = &v40;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v5 = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
        if ( v5 < 0 )
          return (unsigned int)v5;
        if ( v40.Length )
        {
          v21 = *(_QWORD **)(v3 + 24);
          for ( ii = (_QWORD *)(v3 + 24); v21; v21 = (_QWORD *)*v21 )
            ii = v21;
        }
        else
        {
          ii = (_QWORD *)(v3 + 32);
        }
        v23 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v40.MaximumLength + 40LL);
        v24 = v23;
        if ( v23 )
        {
          if ( v40.Length )
          {
            *((_QWORD *)v23 + 2) = v23 + 40;
            *((_WORD *)v23 + 5) = v40.MaximumLength;
            RtlCopyUnicodeString((PUNICODE_STRING)(v23 + 8), &v40);
          }
          *ii = v24;
          for ( jj = 0; ; ++jj )
          {
            v5 = NtEnumerateValueKey(KeyHandle, jj, KeyValueFullInformation, KeyValueInformation, 0x400u, &ResultLength);
            if ( v5 < 0 )
              break;
            SourceString.Buffer = (PWSTR)v49;
            SourceString.Length = v48;
            SourceString.MaximumLength = v48;
            if ( v45 == 1 )
            {
              v27 = v46;
              *(_QWORD *)&String1.Length = 0;
              v38 = 0;
              if ( v48 )
              {
                v28 = (_QWORD *)*((_QWORD *)v24 + 3);
                for ( kk = v24 + 24; v28; v28 = (_QWORD *)*v28 )
                  kk = v28;
              }
              else
              {
                kk = v24 + 32;
              }
              v30 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v48 + 40LL);
              if ( !v30 )
              {
                v5 = -1073741801;
                goto LABEL_47;
              }
              v5 = BaseSrvSaveMappingTarget((wchar_t *)&KeyValueInformation[v27]);
              if ( v5 < 0 )
              {
                RtlFreeHeap(BaseSrvSharedHeap, 0, v30);
                if ( v5 == -1073741801 )
                  goto LABEL_47;
              }
              else
              {
                *((_DWORD *)v30 + 6) = v38;
                *((_QWORD *)v30 + 4) = *(_QWORD *)&String1.Length;
                if ( SourceString.Length )
                {
                  *((_QWORD *)v30 + 2) = v30 + 40;
                  *((_WORD *)v30 + 5) = SourceString.MaximumLength;
                  RtlCopyUnicodeString((PUNICODE_STRING)(v30 + 8), &SourceString);
                }
                *kk = v30;
              }
            }
          }
          if ( v5 == -2147483622 )
            v5 = 0;
LABEL_47:
          v2 = v35;
          v3 = v36;
        }
        else
        {
          v5 = -1073741801;
        }
        NtClose(KeyHandle);
      }
      else if ( v19 == -2147483622 )
      {
        return 0;
      }
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005200  push    rbp
0x180005202  push    rbx
0x180005203  push    rsi
0x180005204  push    rdi
0x180005205  push    r12
0x180005207  push    r14
0x180005209  push    r15
0x18000520b  lea     rbp, [rsp-3E0h]
0x180005213  sub     rsp, 4E0h
0x18000521a  mov     rax, cs:__security_cookie
0x180005221  xor     rax, rsp
0x180005224  mov     [rbp+410h+var_40], rax
0x18000522b  xorps   xmm0, xmm0
0x18000522e  mov     [rsp+510h+var_4D8], rdx
0x180005233  xor     eax, eax
0x180005235  mov     [rsp+510h+var_4D0], rcx
0x18000523a  mov     rdi, rdx
0x18000523d  mov     [rbp+410h+KeyHandle], rax
0x180005241  mov     rsi, rcx
0x180005244  mov     [rsp+510h+var_4E0], eax
0x180005248  xorps   xmm1, xmm1
0x18000524b  lea     rcx, [rbp+410h+DestinationString]; DestinationString
0x18000524f  movups  xmmword ptr [rbp+410h+ObjectAttributes.ObjectName], xmm0
0x180005253  xor     edx, edx; SourceString
0x180005255  movups  xmmword ptr [rbp+410h+ObjectAttributes+1Ch], xmm0
0x180005259  movups  xmmword ptr [rbp+410h+ObjectAttributes.Length], xmm0
0x18000525d  movups  xmmword ptr [rsp+510h+SourceString.Length], xmm0
0x180005262  movups  xmmword ptr [rsp+510h+var_4A0.Length], xmm1
0x180005267  movups  xmmword ptr [rbp+410h+DestinationString.Length], xmm0
0x18000526b  call    cs:__imp_RtlInitUnicodeString
0x180005272  nop     dword ptr [rax+rax+00h]
0x180005277  xor     r12d, r12d
0x18000527a  nop     word ptr [rax+rax+00h]
0x180005280  lea     rax, [rsp+510h+var_4E0]
0x180005285  mov     r8d, 1; KeyValueInformationClass
0x18000528b  mov     [rsp+510h+ResultLength], rax; ResultLength
0x180005290  lea     r9, [rbp+410h+KeyValueInformation]; KeyValueInformation
0x180005294  mov     edx, r12d; Index
0x180005297  mov     [rsp+510h+Length], 400h; Length
0x18000529f  mov     rcx, rdi; KeyHandle
0x1800052a2  call    cs:__imp_NtEnumerateValueKey
0x1800052a9  nop     dword ptr [rax+rax+00h]
0x1800052ae  mov     ebx, eax
0x1800052b0  xor     eax, eax
0x1800052b2  mov     [rbp+410h+var_42], ax
0x1800052b9  test    ebx, ebx
0x1800052bb  js      loc_1800054AA
0x1800052c1  cmp     [rbp+410h+var_43C], 1
0x1800052c5  lea     rax, [rbp+410h+var_42C]
0x1800052c9  movzx   ecx, [rbp+410h+var_430]
0x1800052cd  mov     [rsp+510h+SourceString.Buffer], rax
0x1800052d2  mov     [rsp+510h+SourceString.Length], cx
0x1800052d7  mov     [rsp+510h+SourceString.MaximumLength], cx
0x1800052dc  jnz     loc_1800054A2
0x1800052e2  test    cx, cx
0x1800052e5  jz      loc_18000567C
0x1800052eb  mov     rax, [rsi+18h]
0x1800052ef  lea     rbx, [rsi+18h]
0x1800052f3  test    rax, rax
0x1800052f6  jz      short loc_180005303
0x1800052f8  mov     rbx, rax
0x1800052fb  mov     rax, [rax]
0x1800052fe  test    rax, rax
0x180005301  jnz     short loc_1800052F8
0x180005303  mov     edx, cs:BaseSrvSharedTag
0x180005309  lea     r8, [rcx+28h]; Size
0x18000530d  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005314  add     edx, 40000h
0x18000531a  or      edx, 8; Flags
0x18000531d  call    cs:__imp_RtlAllocateHeap
0x180005324  nop     dword ptr [rax+rax+00h]
0x180005329  mov     rdi, rax
0x18000532c  test    rax, rax
0x18000532f  jz      loc_180005672
0x180005335  cmp     [rsp+510h+SourceString.Length], 0
0x18000533b  jz      short loc_180005363
0x18000533d  add     rax, 28h ; '('
0x180005341  lea     rcx, [rdi+8]; DestinationString
0x180005345  mov     [rdi+10h], rax
0x180005349  lea     rdx, [rsp+510h+SourceString]; SourceString
0x18000534e  movzx   eax, [rsp+510h+SourceString.MaximumLength]
0x180005353  mov     [rdi+0Ah], ax
0x180005357  call    cs:__imp_RtlCopyUnicodeString
0x18000535e  nop     dword ptr [rax+rax+00h]
0x180005363  mov     [rbx], rdi
0x180005366  cmp     [rbp+410h+DestinationString.Length], 0
0x18000536b  mov     ebx, [rbp+410h+var_438]
0x18000536e  jz      short loc_18000538A
0x180005370  mov     rax, [rdi+18h]
0x180005374  lea     r14, [rdi+18h]
0x180005378  test    rax, rax
0x18000537b  jz      short loc_18000538E
0x18000537d  mov     r14, rax
0x180005380  mov     rax, [rax]
0x180005383  test    rax, rax
0x180005386  jnz     short loc_18000537D
0x180005388  jmp     short loc_18000538E
0x18000538a  lea     r14, [rdi+20h]
0x18000538e  mov     edx, cs:BaseSrvSharedTag
0x180005394  movzx   r8d, [rbp+410h+DestinationString.MaximumLength]
0x180005399  add     edx, 40000h
0x18000539f  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800053a6  or      edx, 8; Flags
0x1800053a9  add     r8, 28h ; '('; Size
0x1800053ad  call    cs:__imp_RtlAllocateHeap
0x1800053b4  nop     dword ptr [rax+rax+00h]
0x1800053b9  mov     rsi, rax
0x1800053bc  test    rax, rax
0x1800053bf  jz      loc_180005672
0x1800053c5  lea     rax, [rbp+410h+KeyValueInformation]
0x1800053c9  xorps   xmm0, xmm0
0x1800053cc  add     rbx, rax
0x1800053cf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800053d6  xor     r15d, r15d
0x1800053d9  movups  xmmword ptr [rsp+510h+String1.Length], xmm0
0x1800053de  xchg    ax, ax
0x1800053e0  inc     rax
0x1800053e3  cmp     [rbx+rax*2], r15w
0x1800053e8  jnz     short loc_1800053E0
0x1800053ea  test    rax, rax
0x1800053ed  jnz     loc_180005619
0x1800053f3  test    r15d, 0C0000000h
0x1800053fa  jnz     loc_1800057FE
0x180005400  movzx   eax, word ptr [rbx]
0x180005403  cmp     ax, 5Ch ; '\'
0x180005407  jz      loc_180005808
0x18000540d  test    ax, ax
0x180005410  jnz     loc_180005902
0x180005416  xor     edx, edx
0x180005418  jmp     loc_18000580B
0x18000541d  mov     [rdi], rbx
0x180005420  cmp     [rsp+510h+String1.Length], 0
0x180005426  jz      short loc_180005453
0x180005428  add     rax, 18h
0x18000542c  lea     rcx, [rbx+8]; DestinationString
0x180005430  mov     [rbx+10h], rax
0x180005434  lea     rdx, [rsp+510h+String1]; SourceString
0x180005439  xor     eax, eax
0x18000543b  mov     [rcx], ax
0x18000543e  movzx   eax, [rsp+510h+String1.MaximumLength]
0x180005443  mov     [rbx+0Ah], ax
0x180005447  call    cs:__imp_RtlCopyUnicodeString
0x18000544e  nop     dword ptr [rax+rax+00h]
0x180005453  mov     [rsi+18h], r15d
0x180005457  mov     [rsi+20h], rbx
0x18000545b  cmp     [rbp+410h+DestinationString.Length], 0
0x180005460  jz      short loc_180005486
0x180005462  lea     rax, [rsi+28h]
0x180005466  mov     [rsi+10h], rax
0x18000546a  lea     rcx, [rsi+8]; DestinationString
0x18000546e  movzx   eax, [rbp+410h+DestinationString.MaximumLength]
0x180005472  lea     rdx, [rbp+410h+DestinationString]; SourceString
0x180005476  mov     [rsi+0Ah], ax
0x18000547a  call    cs:__imp_RtlCopyUnicodeString
0x180005481  nop     dword ptr [rax+rax+00h]
0x180005486  mov     rdi, [rsp+510h+var_4D8]
0x18000548b  mov     [r14], rsi
0x18000548e  cmp     [rsp+510h+SourceString.Length], 0
0x180005494  jnz     short loc_18000549D
0x180005496  or      dword ptr [rsi+18h], 20000000h
0x18000549d  mov     rsi, [rsp+510h+var_4D0]
0x1800054a2  inc     r12d
0x1800054a5  jmp     loc_180005280
0x1800054aa  cmp     ebx, 8000001Ah
0x1800054b0  jnz     short loc_18000550B
0x1800054b2  mov     [rsp+510h+arg_10], r13
0x1800054ba  xor     r15d, r15d
0x1800054bd  nop     dword ptr [rax]
0x1800054c0  lea     rax, [rsp+510h+var_4E0]
0x1800054c5  xor     r8d, r8d; KeyInformationClass
0x1800054c8  mov     [rsp+510h+ResultLength], rax; ResultLength
0x1800054cd  lea     r9, [rbp+410h+KeyValueInformation]; KeyInformation
0x1800054d1  mov     edx, r15d; Index
0x1800054d4  mov     [rsp+510h+Length], 400h; Length
0x1800054dc  mov     rcx, rdi; KeyHandle
0x1800054df  call    cs:__imp_NtEnumerateKey
0x1800054e6  nop     dword ptr [rax+rax+00h]
0x1800054eb  mov     ebx, eax
0x1800054ed  test    eax, eax
0x1800054ef  jns     short loc_18000552F
0x1800054f1  cmp     eax, 8000001Ah
0x1800054f6  jz      short loc_180005501
0x1800054f8  test    ebx, ebx
0x1800054fa  js      short loc_180005503
0x1800054fc  inc     r15d
0x1800054ff  jmp     short loc_1800054C0
0x180005501  xor     ebx, ebx
0x180005503  mov     r13, [rsp+510h+arg_10]
0x18000550b  mov     eax, ebx
0x18000550d  mov     rcx, [rbp+410h+var_40]
0x180005514  xor     rcx, rsp; StackCookie
0x180005517  call    __security_check_cookie
0x18000551c  add     rsp, 4E0h
0x180005523  pop     r15
0x180005525  pop     r14
0x180005527  pop     r12
0x180005529  pop     rdi
0x18000552a  pop     rsi
0x18000552b  pop     rbx
0x18000552c  pop     rbp
0x18000552d  retn
0x18000552f  lea     rax, [rbp+410h+var_430]
0x180005533  mov     [rbp+410h+ObjectAttributes.Length], 30h ; '0'
0x18000553a  mov     [rsp+510h+var_4A0.Buffer], rax
0x18000553f  lea     r8, [rbp+410h+ObjectAttributes]; ObjectAttributes
0x180005543  movzx   eax, [rbp+410h+var_434]
0x180005547  lea     rcx, [rbp+410h+KeyHandle]; KeyHandle
0x18000554b  mov     [rsp+510h+var_4A0.Length], ax
0x180005550  xorps   xmm0, xmm0
0x180005553  mov     [rsp+510h+var_4A0.MaximumLength], ax
0x180005558  mov     edx, 80000000h; DesiredAccess
0x18000555d  lea     rax, [rsp+510h+var_4A0]
0x180005562  mov     [rbp+410h+ObjectAttributes.RootDirectory], rdi
0x180005566  mov     [rbp+410h+ObjectAttributes.ObjectName], rax
0x18000556a  mov     [rbp+410h+ObjectAttributes.Attributes], 40h ; '@'
0x180005571  movdqu  xmmword ptr [rbp+410h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005576  call    cs:__imp_NtOpenKey
0x18000557d  nop     dword ptr [rax+rax+00h]
0x180005582  mov     ebx, eax
0x180005584  test    eax, eax
0x180005586  js      loc_180005503
0x18000558c  cmp     [rsp+510h+var_4A0.Length], 0
0x180005592  jz      loc_1800057F5
0x180005598  mov     rax, [rsi+18h]
0x18000559c  lea     rbx, [rsi+18h]
0x1800055a0  test    rax, rax
0x1800055a3  jz      short loc_1800055B0
0x1800055a5  mov     rbx, rax
0x1800055a8  mov     rax, [rax]
0x1800055ab  test    rax, rax
0x1800055ae  jnz     short loc_1800055A5
0x1800055b0  mov     edx, cs:BaseSrvSharedTag
0x1800055b6  movzx   r8d, [rsp+510h+var_4A0.MaximumLength]
0x1800055bc  add     edx, 40000h
0x1800055c2  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800055c9  or      edx, 8; Flags
0x1800055cc  add     r8, 28h ; '('; Size
0x1800055d0  call    cs:__imp_RtlAllocateHeap
0x1800055d7  nop     dword ptr [rax+rax+00h]
0x1800055dc  mov     r13, rax
0x1800055df  test    rax, rax
0x1800055e2  jnz     loc_180005695
0x1800055e8  mov     ebx, 0C0000017h
0x1800055ed  jmp     short loc_180005604
0x1800055ef  xor     eax, eax
0x1800055f1  cmp     ebx, 8000001Ah
0x1800055f7  cmovz   ebx, eax
0x1800055fa  mov     rdi, [rsp+510h+var_4D8]
0x1800055ff  mov     rsi, [rsp+510h+var_4D0]
0x180005604  mov     rcx, [rbp+410h+KeyHandle]; Handle
0x180005608  call    cs:__imp_NtClose
0x18000560f  nop     dword ptr [rax+rax+00h]
0x180005614  jmp     loc_1800054F8
0x180005619  movzx   ecx, word ptr [rbx]
0x18000561c  cmp     cx, 21h ; '!'
0x180005620  jz      loc_1800058F2
0x180005626  cmp     cx, 23h ; '#'
0x18000562a  jz      short loc_180005685
0x18000562c  cmp     cx, 40h ; '@'
0x180005630  jz      loc_1800058BB
0x180005636  cmp     rax, 4
0x18000563a  jb      loc_1800053F3
0x180005640  mov     r8d, 4; MaxCount
0x180005646  lea     rdx, aUsr; "USR:"
0x18000564d  mov     rcx, rbx; String1
0x180005650  call    cs:__imp__wcsnicmp
0x180005657  nop     dword ptr [rax+rax+00h]
0x18000565c  test    eax, eax
0x18000565e  jnz     loc_1800058C4
0x180005664  bts     r15d, 1Fh
0x180005669  add     rbx, 8
0x18000566d  jmp     loc_1800053F3
0x180005672  mov     ebx, 0C0000017h
0x180005677  jmp     loc_18000550B
0x18000567c  lea     rbx, [rsi+20h]
0x180005680  jmp     loc_180005303
0x180005685  or      r15d, 2
0x180005689  add     rbx, 2
0x18000568d  dec     rax
0x180005690  jmp     loc_1800053EA
0x180005695  cmp     [rsp+510h+var_4A0.Length], 0
0x18000569b  jz      short loc_1800056C4
0x18000569d  add     rax, 28h ; '('
0x1800056a1  lea     rcx, [r13+8]; DestinationString
0x1800056a5  mov     [r13+10h], rax
0x1800056a9  lea     rdx, [rsp+510h+var_4A0]; SourceString
0x1800056ae  movzx   eax, [rsp+510h+var_4A0.MaximumLength]
0x1800056b3  mov     [r13+0Ah], ax
0x1800056b8  call    cs:__imp_RtlCopyUnicodeString
0x1800056bf  nop     dword ptr [rax+rax+00h]
0x1800056c4  xor     r12d, r12d
0x1800056c7  mov     [rbx], r13
0x1800056ca  mov     r14d, r12d
0x1800056cd  nop     dword ptr [rax]
0x1800056d0  mov     rcx, [rbp+410h+KeyHandle]; KeyHandle
0x1800056d4  lea     rax, [rsp+510h+var_4E0]
0x1800056d9  mov     [rsp+510h+ResultLength], rax; ResultLength
0x1800056de  lea     r9, [rbp+410h+KeyValueInformation]; KeyValueInformation
0x1800056e2  mov     r8d, 1; KeyValueInformationClass
0x1800056e8  mov     [rsp+510h+Length], 400h; Length
  ... truncated ...
```
