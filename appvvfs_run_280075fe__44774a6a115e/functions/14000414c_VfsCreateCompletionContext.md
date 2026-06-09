# VfsCreateCompletionContext

- ea: `0x14000414c`
- end: `0x140004374`
- name: `VfsCreateCompletionContext`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003c00`

## callees

- `0x14000414c`
- `0x140005308`
- `0x14000f124`
- `0x140014000`

## import_xrefs

- `ntoskrnl!IoReplaceFileObjectName` at `0x140004338`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140004338`
- `ntoskrnl!RtlCopySid` at `0x1400042db`
- `ntoskrnl!RtlCopySid` at `0x1400042db`
- `ntoskrnl!ExAllocatePool2` at `0x140004269`
- `ntoskrnl!ExAllocatePool2` at `0x140004269`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000429c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000429c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400041ed`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400041ed`

## pseudocode

```c
__int64 __fastcall VfsCreateCompletionContext(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v6; // esi
  struct _FILE_OBJECT *RelatedFileObject; // r15
  __int64 v8; // r10
  char *v10; // rax
  char *v11; // rdi
  NTSTATUS v12; // ebx
  int v13; // edx
  int v14; // edx
  unsigned __int16 v15; // bx
  __int64 Pool2; // rax
  _OWORD *v17; // rax
  __int64 v18; // r8
  unsigned __int16 v19; // dx
  WCHAR *v20; // rax
  USHORT v21; // dx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp+8h]

  v6 = 0;
  FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL);
  RelatedFileObject = FileObject->RelatedFileObject;
  *a4 = 0;
  v8 = *(_QWORD *)(a1 + 16);
  if ( (*(_DWORD *)(v8 + 32) & 0xFF000000) == 0x1000000 && (*(_DWORD *)(a2 + 76) & 0x3C0) == 0x1C0 )
    v6 = 4;
  if ( (*(_BYTE *)(v8 + 6) & 4) != 0 )
    v6 |= 4u;
  if ( RelatedFileObject && (unsigned __int8)VfsDecodeFileObject(RelatedFileObject, 0, 0) )
    v6 |= 2u;
  if ( !v6 )
    return 0;
  v10 = (char *)ExAllocateFromPagedLookasideList(&stru_14001F800);
  v11 = v10;
  if ( !v10 )
    return 3221225626LL;
  v12 = 0;
  memset(v10, 0, 0x88u);
  v13 = 0;
  if ( (v6 & 2) != 0 )
  {
    *(_DWORD *)v11 = 2;
    *((_QWORD *)v11 + 1) = RelatedFileObject;
    v13 = 2;
  }
  if ( (v6 & 4) != 0 )
  {
    v14 = v13 | 4;
    *(_DWORD *)v11 = v14;
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 6LL) & 4) != 0 )
    {
      *(_DWORD *)v11 = v14 | 1;
      v15 = *(_WORD *)(a3 + 88);
      Pool2 = ExAllocatePool2(256, v15, 1951614550);
      *((_QWORD *)v11 + 16) = Pool2;
      if ( Pool2 )
      {
        *((_WORD *)v11 + 60) = 0;
        *((_WORD *)v11 + 61) = v15;
        v12 = 0;
        RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 120), (PCUNICODE_STRING)(a3 + 88));
      }
      else
      {
        v12 = -1073741670;
      }
      if ( v12 < 0 )
        goto LABEL_29;
    }
    v17 = *(_OWORD **)(a2 + 8);
    *(_OWORD *)(v11 + 84) = *v17;
    *(_OWORD *)(v11 + 100) = v17[1];
    RtlCopySid(0x44u, v11 + 16, *(PSID *)a2);
  }
  if ( (*(_DWORD *)v11 & 2) != 0 )
  {
    v18 = *(unsigned __int16 *)(a3 + 24);
    v19 = *(_WORD *)(a3 + 8);
    if ( (unsigned __int16)v18 < v19 )
    {
      v20 = (WCHAR *)(v18 + *(_QWORD *)(a3 + 16));
      v21 = v19 - v18;
    }
    else
    {
      v20 = 0;
      v21 = 0;
    }
    v12 = IoReplaceFileObjectName(FileObject, v20, v21);
    if ( v12 < 0 )
      goto LABEL_29;
    FileObject->RelatedFileObject = 0;
  }
  *a4 = v11;
LABEL_29:
  if ( v12 < 0 )
    VfsDeleteCreateCompletionContext(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000414c  mov     [rsp+arg_18], r9
0x140004151  mov     [rsp+arg_8], rdx
0x140004156  push    rbx
0x140004157  push    rsi
0x140004158  push    rdi
0x140004159  push    r12
0x14000415b  push    r13
0x14000415d  push    r14
0x14000415f  push    r15
0x140004161  sub     rsp, 40h
0x140004165  mov     r13, r8
0x140004168  mov     r12, rcx
0x14000416b  xor     esi, esi
0x14000416d  mov     rax, [rcx+10h]
0x140004171  mov     rax, [rax+8]
0x140004175  mov     [rsp+78h+FileObject], rax
0x14000417d  mov     r15, [rax+40h]
0x140004181  mov     [r9], rsi
0x140004184  mov     r10, [rcx+10h]
0x140004188  mov     eax, [r10+20h]
0x14000418c  and     eax, 0FF000000h
0x140004191  lea     r14d, [rsi+4]
0x140004195  cmp     eax, 1000000h
0x14000419a  jnz     short loc_1400041AD
0x14000419c  mov     eax, [rdx+4Ch]
0x14000419f  and     eax, 3C0h
0x1400041a4  cmp     eax, 1C0h
0x1400041a9  cmovz   esi, r14d
0x1400041ad  test    [r10+6], r14b
0x1400041b1  jz      short loc_1400041B6
0x1400041b3  or      esi, r14d
0x1400041b6  test    r15, r15
0x1400041b9  jz      short loc_1400041CF
0x1400041bb  xor     r8d, r8d
0x1400041be  xor     edx, edx
0x1400041c0  mov     rcx, r15
0x1400041c3  call    VfsDecodeFileObject
0x1400041c8  test    al, al
0x1400041ca  jz      short loc_1400041CF
0x1400041cc  or      esi, 2
0x1400041cf  test    esi, esi
0x1400041d1  jnz     short loc_1400041E6
0x1400041d3  xor     eax, eax
0x1400041d5  add     rsp, 40h
0x1400041d9  pop     r15
0x1400041db  pop     r14
0x1400041dd  pop     r13
0x1400041df  pop     r12
0x1400041e1  pop     rdi
0x1400041e2  pop     rsi
0x1400041e3  pop     rbx
0x1400041e4  retn
0x1400041e6  lea     rcx, stru_14001F800; Lookaside
0x1400041ed  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400041f4  nop     dword ptr [rax+rax+00h]
0x1400041f9  mov     rdi, rax
0x1400041fc  test    rax, rax
0x1400041ff  jnz     short loc_140004208
0x140004201  mov     eax, 0C000009Ah
0x140004206  jmp     short loc_1400041D5
0x140004208  xor     ebx, ebx
0x14000420a  mov     [rsp+78h+var_58], ebx
0x14000420e  mov     [rsp+78h+var_50], rdi
0x140004213  xor     edx, edx; Val
0x140004215  mov     r8d, 88h; Size
0x14000421b  mov     rcx, rdi; void *
0x14000421e  call    memset
0x140004223  nop
0x140004224  xor     edx, edx
0x140004226  test    sil, 2
0x14000422a  jz      short loc_140004239
0x14000422c  mov     dword ptr [rdi], 2
0x140004232  mov     [rdi+8], r15
0x140004236  lea     edx, [rbx+2]
0x140004239  test    r14b, sil
0x14000423c  jz      loc_1400042E7
0x140004242  or      edx, r14d
0x140004245  mov     [rdi], edx
0x140004247  mov     rax, [r12+10h]
0x14000424c  test    [rax+6], r14b
0x140004250  jz      short loc_1400042B4
0x140004252  or      edx, 1
0x140004255  mov     [rdi], edx
0x140004257  movzx   ebx, word ptr [r13+58h]
0x14000425c  mov     edx, ebx
0x14000425e  mov     ecx, 100h
0x140004263  mov     r8d, 74534656h
0x140004269  call    cs:__imp_ExAllocatePool2
0x140004270  nop     dword ptr [rax+rax+00h]
0x140004275  mov     [rdi+80h], rax
0x14000427c  test    rax, rax
0x14000427f  jnz     short loc_140004288
0x140004281  mov     ebx, 0C000009Ah
0x140004286  jmp     short loc_1400042A8
0x140004288  xor     eax, eax
0x14000428a  mov     [rdi+78h], ax
0x14000428e  mov     [rdi+7Ah], bx
0x140004292  xor     ebx, ebx
0x140004294  lea     rdx, [r13+58h]; SourceString
0x140004298  lea     rcx, [rdi+78h]; DestinationString
0x14000429c  call    cs:__imp_RtlCopyUnicodeString
0x1400042a3  nop     dword ptr [rax+rax+00h]
0x1400042a8  mov     [rsp+78h+var_58], ebx
0x1400042ac  test    ebx, ebx
0x1400042ae  js      loc_140004361
0x1400042b4  mov     r8, [rsp+78h+arg_8]
0x1400042bc  mov     rax, [r8+8]
0x1400042c0  movups  xmm0, xmmword ptr [rax]
0x1400042c3  movups  xmmword ptr [rdi+54h], xmm0
0x1400042c7  movups  xmm1, xmmword ptr [rax+10h]
0x1400042cb  movups  xmmword ptr [rdi+64h], xmm1
0x1400042cf  lea     rdx, [rdi+10h]; DestinationSid
0x1400042d3  mov     r8, [r8]; SourceSid
0x1400042d6  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1400042db  call    cs:__imp_RtlCopySid
0x1400042e2  nop     dword ptr [rax+rax+00h]
0x1400042e7  mov     eax, [rdi]
0x1400042e9  test    al, 2
0x1400042eb  jz      short loc_140004356
0x1400042ed  movzx   r8d, word ptr [r13+18h]
0x1400042f2  movzx   edx, word ptr [r13+8]
0x1400042f7  cmp     r8w, dx
0x1400042fb  jb      short loc_14000430C
0x1400042fd  mov     [rsp+78h+var_40], 0
0x140004306  xor     eax, eax
0x140004308  xor     edx, edx
0x14000430a  jmp     short loc_140004326
0x14000430c  mov     rax, [r13+10h]
0x140004310  add     rax, r8
0x140004313  mov     [rsp+78h+var_40], rax
0x140004318  sub     dx, r8w
0x14000431c  mov     [rsp+78h+var_48], dx
0x140004321  mov     [rsp+78h+var_46], dx
0x140004326  movzx   r8d, dx; FileNameLength
0x14000432a  mov     rdx, rax; NewFileName
0x14000432d  mov     rsi, [rsp+78h+FileObject]
0x140004335  mov     rcx, rsi; FileObject
0x140004338  call    cs:__imp_IoReplaceFileObjectName
0x14000433f  nop     dword ptr [rax+rax+00h]
0x140004344  mov     ebx, eax
0x140004346  mov     [rsp+78h+var_58], eax
0x14000434a  test    eax, eax
0x14000434c  js      short loc_140004361
0x14000434e  mov     qword ptr [rsi+40h], 0
0x140004356  mov     rax, [rsp+78h+arg_18]
0x14000435e  mov     [rax], rdi
0x140004361  test    ebx, ebx
0x140004363  jns     short loc_14000436D
0x140004365  mov     rcx, rdi; Entry
0x140004368  call    VfsDeleteCreateCompletionContext
0x14000436d  mov     eax, ebx
0x14000436f  jmp     loc_1400041D5
0x14001495d  push    rbp
0x14001495f  sub     rsp, 20h
0x140014963  mov     rbp, rdx
0x140014966  cmp     dword ptr [rbp+20h], 0
0x14001496a  jge     short loc_140014976
0x14001496c  mov     rcx, [rbp+28h]; Entry
0x140014970  call    VfsDeleteCreateCompletionContext
0x140014975  nop
0x140014976  add     rsp, 20h
0x14001497a  pop     rbp
0x14001497b  retn
```
