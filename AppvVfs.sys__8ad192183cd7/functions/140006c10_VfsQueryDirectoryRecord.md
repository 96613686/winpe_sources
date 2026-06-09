# VfsQueryDirectoryRecord

- ea: `0x140006c10`
- end: `0x14000711c`
- name: `VfsQueryDirectoryRecord`
- size: `1292`
- prototype: `__int64 __fastcall(__int64, BOOLEAN, char, __int64 *, _DWORD *, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000652c`
- `0x140006a60`

## callees

- `0x1400063dc`
- `0x140006c10`
- `0x14000f984`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140006ee9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140007005`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000707e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006ee9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140007005`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000707e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140006e81`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140006e81`
- `ntoskrnl!ObfDereferenceObject` at `0x140006f7c`
- `ntoskrnl!ObfDereferenceObject` at `0x140006f7c`
- `FLTMGR!FltClose` at `0x140006f8d`
- `FLTMGR!FltClose` at `0x140006f8d`
- `FLTMGR!FltQueryDirectoryFile` at `0x140006d03`
- `FLTMGR!FltQueryDirectoryFile` at `0x140006d03`

## string_xrefs

- `0x14000704a`: `VfsQueryDirectoryRecord() - Failed to query directory namespace for fileobject: %p\n InfoClass: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsQueryDirectoryRecord(
        __int64 a1,
        BOOLEAN a2,
        char a3,
        __int64 *a4,
        _DWORD *a5,
        _DWORD *a6,
        _QWORD *a7)
{
  const UNICODE_STRING *v7; // r14
  __int64 v8; // r9
  const UNICODE_STRING *v9; // rax
  const UNICODE_STRING *v10; // rsi
  const UNICODE_STRING *v11; // rbx
  int v12; // edi
  int v13; // r15d
  __int64 v14; // rdx
  const UNICODE_STRING *v15; // r12
  __int64 v16; // r8
  int *v17; // r10
  _DWORD *v18; // r13
  wchar_t **p_Buffer; // r11
  FILE_INFORMATION_CLASS v20; // ebp
  struct _UNICODE_STRING *FileName; // rcx
  BOOLEAN RestartScan; // dl
  int v23; // eax
  NTSTATUS DirectoryFile; // eax
  ULONG Buffer; // r9d
  void *v26; // r8
  ULONG v27; // eax
  wchar_t *v28; // rdx
  bool v29; // zf
  wchar_t *v30; // rax
  int v31; // eax
  int v32; // ecx
  const UNICODE_STRING *v33; // rbx
  __int64 *v34; // rdi
  unsigned int v35; // r12d
  LONG v36; // eax
  unsigned int v37; // ebp
  const UNICODE_STRING *v38; // r15
  struct _FLT_INSTANCE *v39; // rbx
  wchar_t *v40; // rdx
  int Tombstone; // ebx
  unsigned int v42; // ebx
  const UNICODE_STRING *v43; // rbx
  unsigned int v44; // r15d
  int v45; // eax
  int v47; // eax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-78h]
  BOOLEAN ReturnSingleEntry[8]; // [rsp+28h] [rbp-70h]
  ULONG LengthReturned[2]; // [rsp+50h] [rbp-48h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-40h] BYREF

  v7 = (const UNICODE_STRING *)(a1 + 8);
  v8 = a1;
  v9 = *(const UNICODE_STRING **)(a1 + 8);
  v10 = 0;
  while ( v9 != v7 )
  {
    *((_BYTE *)&v9[7].MaximumLength + 2) = a3;
    v9 = *(const UNICODE_STRING **)&v9->Length;
  }
LABEL_4:
  v11 = *(const UNICODE_STRING **)&v7->Length;
  v12 = 0;
  v13 = 0;
  if ( *(const UNICODE_STRING **)&v7->Length == v7 )
    goto LABEL_36;
  v14 = v8 + 40;
  while ( 2 )
  {
    v15 = v11 + 6;
    v16 = (__int64)&v11[6];
    v17 = (int *)&v11[5];
    v18 = &v11[5].MaximumLength + 1;
    p_Buffer = &v11[5].Buffer;
    while ( 1 )
    {
      v20 = *(_DWORD *)(v8 + 32);
      FileName = (struct _UNICODE_STRING *)(v14 & -(__int64)(*(_QWORD *)(v8 + 48) != 0));
      RestartScan = *((_BYTE *)&v11[7].MaximumLength + 2);
      *v17 = 0;
      *v18 = 0;
      *(_DWORD *)p_Buffer = 0;
      HIDWORD(v11[5].Buffer) = 0;
      v11[6].Buffer = 0;
      if ( RestartScan )
      {
        *(wchar_t **)((char *)&v11[3].Buffer + 4) = 0;
        v16 = (__int64)&v11[6];
        *(_DWORD *)(&v11[4].MaximumLength + 1) = 0;
      }
      else
      {
        v23 = *(_DWORD *)(&v11[4].MaximumLength + 1);
        if ( (v23 & 2) != 0 )
        {
          DirectoryFile = (v23 & 1) != 0 ? -2147483642 : -1073741809;
          goto LABEL_18;
        }
      }
      if ( HIDWORD(v11[3].Buffer) )
        goto LABEL_16;
      Buffer = (ULONG)v11[3].Buffer;
      v26 = *(void **)&v11[3].Length;
      LengthReturned[0] = 0;
      DirectoryFile = FltQueryDirectoryFile(
                        (PFLT_INSTANCE)v11[1].Buffer,
                        *(PFILE_OBJECT *)&v11[2].Length,
                        v26,
                        Buffer,
                        v20,
                        a2,
                        FileName,
                        RestartScan,
                        LengthReturned);
      if ( DirectoryFile != -1073741809 && DirectoryFile != -2147483642 )
      {
        v17 = (int *)&v11[5];
        p_Buffer = &v11[5].Buffer;
        if ( DirectoryFile >= 0 )
        {
          v27 = LengthReturned[0];
          v16 = (__int64)&v11[6];
          *(_DWORD *)(&v11[4].MaximumLength + 1) |= 1u;
          *(wchar_t **)((char *)&v11[3].Buffer + 4) = (wchar_t *)v27;
LABEL_16:
          v28 = (wchar_t *)(*(_QWORD *)&v11[3].Length + *(unsigned int *)&v11[4].Length);
          v11[4].Buffer = v28;
          VfsGetDirQueryRecordInformation(
            v20,
            (_DWORD)v28,
            (_DWORD)v11 + 84,
            (_DWORD)v17,
            (__int64)p_Buffer,
            (__int64)&v11[5].Buffer + 4,
            v16);
          DirectoryFile = 0;
          v17 = (int *)&v11[5];
          p_Buffer = &v11[5].Buffer;
        }
        v8 = a1;
        goto LABEL_18;
      }
      v8 = a1;
      v17 = (int *)&v11[5];
      p_Buffer = &v11[5].Buffer;
      *(_DWORD *)(&v11[4].MaximumLength + 1) |= 2u;
LABEL_18:
      *(_DWORD *)&v11[7].Length = DirectoryFile;
      *((_BYTE *)&v11[7].MaximumLength + 2) = 0;
      if ( DirectoryFile == -1073741809 )
        break;
      if ( DirectoryFile == -2147483642 )
      {
        ++v13;
        goto LABEL_35;
      }
      if ( DirectoryFile < 0 )
      {
        *(_DWORD *)ReturnSingleEntry = DirectoryFile;
        FileInformationClass[0] = *(FILE_INFORMATION_CLASS *)(v8 + 32);
        LogWrite(
          1,
          0,
          L"VfsQueryDirectoryRecord() - Failed to query directory namespace for fileobject: %p\n"
           " InfoClass: %d\n"
           " Status: 0x%08X",
          *(_QWORD *)&v11[2].Length,
          *(_QWORD *)FileInformationClass,
          *(_QWORD *)ReturnSingleEntry);
        return *(unsigned int *)&v11[7].Length;
      }
      if ( (*(_DWORD *)v8 & 2) == 0 )
        goto LABEL_35;
      if ( v15->Length == 2 )
      {
        v29 = *v11[6].Buffer == 46;
      }
      else
      {
        if ( v15->Length != 4 )
          goto LABEL_35;
        v30 = v11[6].Buffer;
        if ( *v30 != 46 )
          goto LABEL_35;
        v29 = v30[1] == 46;
      }
      if ( !v29 )
        goto LABEL_35;
      v16 = (__int64)&v11[6];
      if ( *v18 )
      {
        v31 = *v17;
        HIDWORD(v11[3].Buffer) -= *v17;
        *(_DWORD *)&v11[4].Length += v31;
      }
      else
      {
        *(wchar_t **)((char *)&v11[3].Buffer + 4) = 0;
      }
      v14 = v8 + 40;
    }
    ++v12;
LABEL_35:
    v11 = *(const UNICODE_STRING **)&v11->Length;
    v14 = v8 + 40;
    if ( v11 != v7 )
      continue;
    break;
  }
LABEL_36:
  v32 = *(_DWORD *)(v8 + 28);
  if ( v12 == v32 )
    return 3221225487LL;
  if ( v13 + v12 == v32 )
    return 2147483654LL;
  v33 = *(const UNICODE_STRING **)&v7->Length;
  v34 = 0;
  v35 = 0;
  if ( *(const UNICODE_STRING **)&v7->Length != v7 )
  {
    do
    {
      if ( v33[6].Buffer )
      {
        if ( v34 )
        {
          v36 = RtlCompareUnicodeString((PCUNICODE_STRING)(v34 + 3), v33 + 6, 1u);
          if ( v36 <= 0 )
          {
            if ( !v36 )
              ++v35;
          }
          else
          {
            v34 = (__int64 *)&v33[4].Buffer;
            v10 = v33;
          }
        }
        else
        {
          v34 = (__int64 *)&v33[4].Buffer;
          v10 = v33;
          v35 = 1;
        }
      }
      v33 = *(const UNICODE_STRING **)&v33->Length;
    }
    while ( v33 != v7 );
    if ( v34 )
    {
      v37 = 0;
      v38 = v10;
      if ( v10 == v7 )
      {
LABEL_74:
        v42 = 0;
        goto LABEL_80;
      }
      while ( 1 )
      {
        if ( v37 >= v35 )
          goto LABEL_74;
        if ( v38[6].Buffer
          && (&v38[4].Buffer == (wchar_t **)v34 || RtlEqualUnicodeString((PCUNICODE_STRING)(v34 + 3), v38 + 6, 1u)) )
        {
          ++v37;
          if ( (*(_DWORD *)&v38[1].Length & 1) != 0 )
          {
            if ( HIDWORD(v38[5].Buffer) )
            {
              v39 = (struct _FLT_INSTANCE *)v38[1].Buffer;
              v40 = v38[2].Buffer;
              FileHandle = 0;
              *(_QWORD *)LengthReturned = 0;
              if ( VfsOpenFile(
                     v39,
                     v40,
                     (struct _UNICODE_STRING *)&v38[6],
                     0x100008u,
                     1u,
                     0x4020u,
                     &FileHandle,
                     (PFILE_OBJECT *)LengthReturned) >= 0 )
              {
                Tombstone = VfsQueryTombstone(v39, *(PFILE_OBJECT *)LengthReturned);
                ObfDereferenceObject(*(PVOID *)LengthReturned);
                FltClose(FileHandle);
                if ( Tombstone >= 0 )
                  break;
              }
            }
          }
        }
        v38 = *(const UNICODE_STRING **)&v38->Length;
        if ( v38 == v7 )
        {
          v42 = 0;
          do
          {
            if ( v42 >= v35 )
              break;
            if ( v10[6].Buffer )
            {
              if ( &v10[4].Buffer == (wchar_t **)v34 )
              {
                ++v42;
              }
              else if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v34 + 3), v10 + 6, 1u) )
              {
                ++v42;
                if ( *(_DWORD *)(&v10[5].MaximumLength + 1) )
                {
                  v47 = *(_DWORD *)&v10[5].Length;
                  HIDWORD(v10[3].Buffer) -= v47;
                  *(_DWORD *)&v10[4].Length += v47;
                }
                else
                {
                  *(wchar_t **)((char *)&v10[3].Buffer + 4) = 0;
                }
              }
            }
            v10 = *(const UNICODE_STRING **)&v10->Length;
LABEL_80:
            ;
          }
          while ( v10 != v7 );
          *a4 = *v34;
          *a5 = *((_DWORD *)v34 + 2);
          *a6 = *((_DWORD *)v34 + 3);
          *a7 = v34 - 9;
          return 0;
        }
      }
      v43 = v10;
      v44 = 0;
      while ( 1 )
      {
        v8 = a1;
        if ( v44 >= v35 )
          goto LABEL_4;
        if ( v43[6].Buffer
          && (&v43[4].Buffer == (wchar_t **)v34 || RtlEqualUnicodeString((PCUNICODE_STRING)(v34 + 3), v43 + 6, 1u)) )
        {
          ++v44;
          if ( *(_DWORD *)(&v43[5].MaximumLength + 1) )
          {
            v45 = *(_DWORD *)&v43[5].Length;
            HIDWORD(v43[3].Buffer) -= v45;
            *(_DWORD *)&v43[4].Length += v45;
          }
          else
          {
            *(wchar_t **)((char *)&v43[3].Buffer + 4) = 0;
          }
        }
        v43 = *(const UNICODE_STRING **)&v43->Length;
        if ( v43 == v7 )
        {
          v8 = a1;
          goto LABEL_4;
        }
      }
    }
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x140006c10  mov     rax, rsp
0x140006c13  mov     [rax+18h], rbx
0x140006c17  mov     [rax+20h], r9
0x140006c1b  mov     [rax+10h], dl
0x140006c1e  mov     [rax+8], rcx
0x140006c22  push    rbp
0x140006c23  push    rsi
0x140006c24  push    rdi
0x140006c25  push    r12
0x140006c27  push    r13
0x140006c29  push    r14
0x140006c2b  push    r15
0x140006c2d  sub     rsp, 60h
0x140006c31  lea     r14, [rcx+8]
0x140006c35  mov     r9, rcx
0x140006c38  mov     rax, [r14]
0x140006c3b  xor     esi, esi
0x140006c3d  jmp     short loc_140006C46
0x140006c3f  mov     [rax+74h], r8b
0x140006c43  mov     rax, [rax]
0x140006c46  cmp     rax, r14
0x140006c49  jnz     short loc_140006C3F
0x140006c4b  mov     rbx, [r14]
0x140006c4e  xor     edi, edi
0x140006c50  xor     r15d, r15d
0x140006c53  cmp     rbx, r14
0x140006c56  jz      loc_140006E32
0x140006c5c  lea     rdx, [r9+28h]
0x140006c60  lea     r12, [rbx+60h]
0x140006c64  mov     r8, r12
0x140006c67  lea     r10, [rbx+50h]
0x140006c6b  lea     r13, [rbx+54h]
0x140006c6f  lea     r11, [rbx+58h]
0x140006c73  mov     rax, [r9+30h]
0x140006c77  mov     ebp, [r9+20h]
0x140006c7b  neg     rax
0x140006c7e  sbb     rcx, rcx
0x140006c81  xor     eax, eax
0x140006c83  and     rcx, rdx
0x140006c86  mov     dl, [rbx+74h]
0x140006c89  mov     [r10], eax
0x140006c8c  mov     [r13+0], eax
0x140006c90  mov     [r11], eax
0x140006c93  mov     [rbx+5Ch], eax
0x140006c96  mov     [rbx+68h], rax
0x140006c9a  test    dl, dl
0x140006c9c  jz      short loc_140006CAA
0x140006c9e  mov     [rbx+3Ch], rax
0x140006ca2  mov     r8, r12
0x140006ca5  mov     [rbx+44h], eax
0x140006ca8  jmp     short loc_140006CC8
0x140006caa  mov     eax, [rbx+44h]
0x140006cad  test    al, 2
0x140006caf  jz      short loc_140006CC6
0x140006cb1  and     al, 1
0x140006cb3  neg     al
0x140006cb5  sbb     eax, eax
0x140006cb7  and     eax, 0BFFFFFF7h
0x140006cbc  add     eax, 0C000000Fh
0x140006cc1  jmp     loc_140006D83
0x140006cc6  xor     eax, eax
0x140006cc8  cmp     [rbx+3Ch], eax
0x140006ccb  jnz     short loc_140006D46
0x140006ccd  mov     r9d, [rbx+38h]; Length
0x140006cd1  mov     r8, [rbx+30h]; FileInformation
0x140006cd5  mov     [rsp+98h+var_48], eax
0x140006cd9  lea     rax, [rsp+98h+var_48]
0x140006cde  mov     [rsp+98h+LengthReturned], rax; LengthReturned
0x140006ce3  mov     al, [rsp+98h+arg_8]
0x140006cea  mov     [rsp+98h+RestartScan], dl; RestartScan
0x140006cee  mov     rdx, [rbx+20h]; FileObject
0x140006cf2  mov     [rsp+98h+FileName], rcx; FileName
0x140006cf7  mov     rcx, [rbx+18h]; Instance
0x140006cfb  mov     [rsp+98h+ReturnSingleEntry], al; ReturnSingleEntry
0x140006cff  mov     [rsp+98h+FileInformationClass], ebp; FileInformationClass
0x140006d03  call    cs:__imp_FltQueryDirectoryFile
0x140006d0a  nop     dword ptr [rax+rax+00h]
0x140006d0f  cmp     eax, 0C000000Fh
0x140006d14  jz      loc_140006DC4
0x140006d1a  cmp     eax, 80000006h
0x140006d1f  jz      loc_140006DC4
0x140006d25  lea     r10, [rbx+50h]
0x140006d29  lea     r11, [rbx+58h]
0x140006d2d  test    eax, eax
0x140006d2f  js      short loc_140006D7B
0x140006d31  mov     eax, [rsp+98h+var_48]
0x140006d35  mov     r8, r12
0x140006d38  or      dword ptr [rbx+44h], 1
0x140006d3c  mov     [rbx+3Ch], eax
0x140006d3f  mov     dword ptr [rbx+40h], 0
0x140006d46  mov     edx, [rbx+40h]
0x140006d49  lea     rax, [rbx+5Ch]
0x140006d4d  add     rdx, [rbx+30h]
0x140006d51  mov     r9, r10
0x140006d54  mov     [rsp+98h+FileName], r8
0x140006d59  mov     ecx, ebp
0x140006d5b  mov     qword ptr [rsp+98h+ReturnSingleEntry], rax
0x140006d60  mov     r8, r13
0x140006d63  mov     [rbx+48h], rdx
0x140006d67  mov     qword ptr [rsp+98h+FileInformationClass], r11
0x140006d6c  call    VfsGetDirQueryRecordInformation
0x140006d71  xor     eax, eax
0x140006d73  lea     r10, [rbx+50h]
0x140006d77  lea     r11, [rbx+58h]
0x140006d7b  mov     r9, [rsp+98h+arg_0]
0x140006d83  mov     ecx, 2
0x140006d88  mov     [rbx+70h], eax
0x140006d8b  mov     byte ptr [rbx+74h], 0
0x140006d8f  cmp     eax, 0C000000Fh
0x140006d94  jz      loc_140006E20
0x140006d9a  cmp     eax, 80000006h
0x140006d9f  jz      short loc_140006E1B
0x140006da1  test    eax, eax
0x140006da3  js      loc_140007046
0x140006da9  mov     eax, [r9]
0x140006dac  test    cl, al
0x140006dae  jz      short loc_140006E22
0x140006db0  movzx   eax, word ptr [r12]
0x140006db5  cmp     ax, cx
0x140006db8  jnz     short loc_140006DDE
0x140006dba  mov     rax, [rbx+68h]
0x140006dbe  cmp     word ptr [rax], 2Eh ; '.'
0x140006dc2  jmp     short loc_140006DF3
0x140006dc4  mov     r9, [rsp+98h+arg_0]
0x140006dcc  lea     r10, [rbx+50h]
0x140006dd0  mov     ecx, 2
0x140006dd5  lea     r11, [rbx+58h]
0x140006dd9  or      [rbx+44h], ecx
0x140006ddc  jmp     short loc_140006D88
0x140006dde  cmp     ax, 4
0x140006de2  jnz     short loc_140006E22
0x140006de4  mov     rax, [rbx+68h]
0x140006de8  cmp     word ptr [rax], 2Eh ; '.'
0x140006dec  jnz     short loc_140006E22
0x140006dee  cmp     word ptr [rax+2], 2Eh ; '.'
0x140006df3  jnz     short loc_140006E22
0x140006df5  cmp     dword ptr [r13+0], 0
0x140006dfa  mov     r8, r12
0x140006dfd  jnz     short loc_140006E09
0x140006dff  mov     qword ptr [rbx+3Ch], 0
0x140006e07  jmp     short loc_140006E12
0x140006e09  mov     eax, [r10]
0x140006e0c  sub     [rbx+3Ch], eax
0x140006e0f  add     [rbx+40h], eax
0x140006e12  lea     rdx, [r9+28h]
0x140006e16  jmp     loc_140006C73
0x140006e1b  inc     r15d
0x140006e1e  jmp     short loc_140006E22
0x140006e20  inc     edi
0x140006e22  mov     rbx, [rbx]
0x140006e25  lea     rdx, [r9+28h]
0x140006e29  cmp     rbx, r14
0x140006e2c  jnz     loc_140006C60
0x140006e32  mov     ecx, [r9+1Ch]
0x140006e36  cmp     edi, ecx
0x140006e38  jz      loc_1400070FE
0x140006e3e  lea     eax, [r15+rdi]
0x140006e42  cmp     eax, ecx
0x140006e44  jz      loc_1400070F7
0x140006e4a  mov     rbx, [r14]
0x140006e4d  xor     edi, edi
0x140006e4f  xor     r12d, r12d
0x140006e52  cmp     rbx, r14
0x140006e55  jz      loc_1400070F0
0x140006e5b  cmp     qword ptr [rbx+68h], 0
0x140006e60  jz      short loc_140006E9F
0x140006e62  test    rdi, rdi
0x140006e65  jnz     short loc_140006E76
0x140006e67  lea     rdi, [rbx+48h]
0x140006e6b  mov     rsi, rbx
0x140006e6e  mov     r12d, 1
0x140006e74  jmp     short loc_140006E9F
0x140006e76  lea     rdx, [rbx+60h]; String2
0x140006e7a  mov     r8b, 1; CaseInSensitive
0x140006e7d  lea     rcx, [rdi+18h]; String1
0x140006e81  call    cs:__imp_RtlCompareUnicodeString
0x140006e88  nop     dword ptr [rax+rax+00h]
0x140006e8d  test    eax, eax
0x140006e8f  jle     short loc_140006E9A
0x140006e91  lea     rdi, [rbx+48h]
0x140006e95  mov     rsi, rbx
0x140006e98  jmp     short loc_140006E9F
0x140006e9a  jnz     short loc_140006E9F
0x140006e9c  inc     r12d
0x140006e9f  mov     rbx, [rbx]
0x140006ea2  cmp     rbx, r14
0x140006ea5  jnz     short loc_140006E5B
0x140006ea7  test    rdi, rdi
0x140006eaa  jz      loc_1400070F0
0x140006eb0  xor     ebp, ebp
0x140006eb2  mov     r15, rsi
0x140006eb5  cmp     rsi, r14
0x140006eb8  jz      loc_14000706F
0x140006ebe  cmp     ebp, r12d
0x140006ec1  jnb     loc_14000706F
0x140006ec7  lea     rbx, [r15+48h]
0x140006ecb  cmp     qword ptr [rbx+20h], 0
0x140006ed0  jz      loc_140006F9D
0x140006ed6  lea     r13, [rbx+18h]
0x140006eda  cmp     rbx, rdi
0x140006edd  jz      short loc_140006EFD
0x140006edf  lea     rcx, [rdi+18h]; String1
0x140006ee3  mov     r8b, 1; CaseInSensitive
0x140006ee6  mov     rdx, r13; String2
0x140006ee9  call    cs:__imp_RtlEqualUnicodeString
0x140006ef0  nop     dword ptr [rax+rax+00h]
0x140006ef5  test    al, al
0x140006ef7  jz      loc_140006F9D
0x140006efd  mov     eax, [r15+10h]
0x140006f01  inc     ebp
0x140006f03  test    al, 1
0x140006f05  jz      loc_140006F9D
0x140006f0b  cmp     dword ptr [rbx+14h], 0
0x140006f0f  jz      loc_140006F9D
0x140006f15  mov     rbx, [r15+18h]
0x140006f19  lea     rax, [rsp+98h+var_48]
0x140006f1e  mov     rdx, [r15+28h]
0x140006f22  mov     r9d, 100008h
0x140006f28  mov     qword ptr [rsp+98h+RestartScan], rax; FileObject
0x140006f2d  mov     r8, r13
0x140006f30  lea     rax, [rsp+98h+FileHandle]
0x140006f35  mov     [rsp+98h+FileHandle], 0
0x140006f3e  mov     [rsp+98h+FileName], rax; FileHandle
0x140006f43  mov     rcx, rbx; Instance
0x140006f46  mov     dword ptr [rsp+98h+ReturnSingleEntry], 4020h; ULONG
0x140006f4e  mov     [rsp+98h+FileInformationClass], 1; ULONG
0x140006f56  mov     qword ptr [rsp+98h+var_48], 0
0x140006f5f  call    VfsOpenFile
0x140006f64  test    eax, eax
0x140006f66  js      short loc_140006F9D
0x140006f68  mov     rdx, qword ptr [rsp+98h+var_48]; FileObject
0x140006f6d  mov     rcx, rbx; Instance
0x140006f70  call    VfsQueryTombstone
0x140006f75  mov     rcx, qword ptr [rsp+98h+var_48]; Object
0x140006f7a  mov     ebx, eax
0x140006f7c  call    cs:__imp_ObfDereferenceObject
0x140006f83  nop     dword ptr [rax+rax+00h]
0x140006f88  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x140006f8d  call    cs:__imp_FltClose
0x140006f94  nop     dword ptr [rax+rax+00h]
0x140006f99  test    ebx, ebx
0x140006f9b  jns     short loc_140006FD3
0x140006f9d  mov     r15, [r15]
0x140006fa0  cmp     r15, r14
0x140006fa3  jnz     loc_140006EBE
0x140006fa9  xor     ebx, ebx
0x140006fab  cmp     ebx, r12d
0x140006fae  jnb     loc_1400070B5
0x140006fb4  lea     rbp, [rsi+48h]
0x140006fb8  cmp     qword ptr [rbp+20h], 0
0x140006fbd  jz      loc_1400070A9
0x140006fc3  cmp     rbp, rdi
0x140006fc6  jnz     loc_140007073
0x140006fcc  inc     ebx
0x140006fce  jmp     loc_1400070A9
0x140006fd3  mov     rbx, rsi
0x140006fd6  xor     r15d, r15d
0x140006fd9  mov     r9, [rsp+98h+arg_0]
0x140006fe1  cmp     r15d, r12d
0x140006fe4  jnb     loc_140006C4B
0x140006fea  lea     rbp, [rbx+48h]
0x140006fee  cmp     qword ptr [rbp+20h], 0
0x140006ff3  jz      short loc_140007031
0x140006ff5  cmp     rbp, rdi
0x140006ff8  jz      short loc_140007015
0x140006ffa  lea     rdx, [rbp+18h]; String2
0x140006ffe  mov     r8b, 1; CaseInSensitive
0x140007001  lea     rcx, [rdi+18h]; String1
0x140007005  call    cs:__imp_RtlEqualUnicodeString
0x14000700c  nop     dword ptr [rax+rax+00h]
0x140007011  test    al, al
0x140007013  jz      short loc_140007031
0x140007015  inc     r15d
0x140007018  cmp     dword ptr [rbp+0Ch], 0
0x14000701c  jnz     short loc_140007028
0x14000701e  mov     qword ptr [rbx+3Ch], 0
0x140007026  jmp     short loc_140007031
0x140007028  mov     eax, [rbp+8]
0x14000702b  sub     [rbx+3Ch], eax
0x14000702e  add     [rbx+40h], eax
0x140007031  mov     rbx, [rbx]
0x140007034  cmp     rbx, r14
0x140007037  jnz     short loc_140006FD9
0x140007039  mov     r9, [rsp+98h+arg_0]
0x140007041  jmp     loc_140006C4B
0x140007046  mov     dword ptr [rsp+98h+ReturnSingleEntry], eax
0x14000704a  lea     r8, aVfsquerydirect; "VfsQueryDirectoryRecord() - Failed to q"...
0x140007051  mov     eax, [r9+20h]
0x140007055  xor     edx, edx
0x140007057  mov     r9, [rbx+20h]
0x14000705b  mov     [rsp+98h+FileInformationClass], eax
0x14000705f  lea     ecx, [rdx+1]
0x140007062  call    LogWrite
0x140007067  mov     eax, [rbx+70h]
0x14000706a  jmp     loc_140007103
0x14000706f  xor     ebx, ebx
0x140007071  jmp     short loc_1400070AC
0x140007073  lea     rdx, [rbp+18h]; String2
0x140007077  mov     r8b, 1; CaseInSensitive
0x14000707a  lea     rcx, [rdi+18h]; String1
  ... truncated ...
```
