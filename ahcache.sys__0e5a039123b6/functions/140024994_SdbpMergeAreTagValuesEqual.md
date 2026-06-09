# SdbpMergeAreTagValuesEqual

- ea: `0x140024994`
- end: `0x140024b62`
- name: `SdbpMergeAreTagValuesEqual`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003af10`

## callees

- `0x140024994`
- `0x14003e1f0`
- `0x14003e364`
- `0x14003ef10`
- `0x14003fcf8`
- `0x14004007c`

## import_xrefs

- `ntoskrnl!toupper` at `0x140024b0b`
- `ntoskrnl!toupper` at `0x140024b1b`
- `ntoskrnl!toupper` at `0x140024b0b`
- `ntoskrnl!toupper` at `0x140024b1b`
- `ntoskrnl!RtlCompareMemory` at `0x140024aac`
- `ntoskrnl!RtlCompareMemory` at `0x140024aac`

## pseudocode

```c
_BOOL8 __fastcall SdbpMergeAreTagValuesEqual(void *a1, __int64 a2, void *a3, unsigned int a4)
{
  unsigned int v6; // edi
  __int16 TagFromTagID; // si
  __int16 v9; // cx
  int v10; // eax
  SIZE_T TagDataSize; // rsi
  const void *MappedTagData; // rdi
  const void *v13; // rax
  const void *v14; // rdx
  const char *v15; // rax
  _WORD *StringTagPtr; // rbp
  __int64 v18; // rax
  unsigned __int16 *v19; // rsi
  int v20; // ecx
  int v21; // ebx
  int v22; // edi

  v6 = a2;
  if ( !(_DWORD)a2 || !a4 )
    return (_DWORD)a2 == a4;
  TagFromTagID = SdbGetTagFromTagID(a1, a2);
  v9 = SdbGetTagFromTagID(a3, a4);
  if ( TagFromTagID != v9 )
    return 0;
  v10 = TagFromTagID & 0xF000;
  if ( v10 == 4096 )
    return (v9 & 0xF000) == 4096;
  if ( v10 == 24576 || v10 == 0x8000 )
  {
    if ( (((v9 & 0xF000) - 24576) & 0xDFFF) != 0 )
      return 0;
    StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, v6);
    v18 = SdbGetStringTagPtr(a3, a4);
    v19 = (unsigned __int16 *)v18;
    if ( StringTagPtr && v18 )
    {
      while ( 1 )
      {
        v20 = *v19;
        if ( !*StringTagPtr )
          break;
        v21 = (unsigned __int16)*StringTagPtr;
        v22 = toupper(v20);
        if ( toupper(v21) != v22 )
          return 0;
        ++StringTagPtr;
        ++v19;
      }
      return (_WORD)v20 == 0;
    }
    else
    {
      return StringTagPtr == (_WORD *)v18;
    }
  }
  TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v6);
  if ( TagDataSize != (unsigned int)SdbGetTagDataSize(a3, a4) || TagDataSize == 0x20000000 )
    return 0;
  MappedTagData = (const void *)SdbpGetMappedTagData(a1, v6);
  v13 = (const void *)SdbpGetMappedTagData(a3, a4);
  v14 = v13;
  if ( TagDataSize )
  {
    if ( !MappedTagData )
    {
      v15 = "both tags";
      if ( v14 )
        v15 = "first tag";
      goto LABEL_15;
    }
    if ( !v13 )
    {
      v15 = "second tag";
LABEL_15:
      AslLogCallPrintf(
        1,
        "SdbpMergeAreTagValuesEqual",
        897,
        "SdbpGetMappedTagData returned null data pointer for data with size > 0. Null returned for %s",
        v15);
      return 0;
    }
  }
  return TagDataSize == RtlCompareMemory(MappedTagData, v13, TagDataSize);
}

```

## disassembly

```asm
0x140024994  push    rbx
0x140024996  push    rbp
0x140024997  push    rsi
0x140024998  push    rdi
0x140024999  push    r14
0x14002499b  push    r15
0x14002499d  sub     rsp, 38h
0x1400249a1  xor     r15d, r15d
0x1400249a4  mov     ebx, r9d
0x1400249a7  mov     r14, r8
0x1400249aa  mov     edi, edx
0x1400249ac  mov     rbp, rcx
0x1400249af  test    edx, edx
0x1400249b1  jz      loc_140024B4C
0x1400249b7  test    ebx, ebx
0x1400249b9  jz      loc_140024B4C
0x1400249bf  call    SdbGetTagFromTagID
0x1400249c4  mov     edx, ebx
0x1400249c6  movzx   esi, ax
0x1400249c9  mov     rcx, r14
0x1400249cc  call    SdbGetTagFromTagID
0x1400249d1  movzx   ecx, ax
0x1400249d4  cmp     si, ax
0x1400249d7  jnz     loc_140024A9F
0x1400249dd  mov     eax, esi
0x1400249df  mov     edx, 0F000h
0x1400249e4  and     eax, edx
0x1400249e6  mov     r8d, 1000h
0x1400249ec  cmp     eax, r8d
0x1400249ef  jz      loc_140024B43
0x1400249f5  mov     r8d, 6000h
0x1400249fb  cmp     eax, r8d
0x1400249fe  jz      loc_140024AC8
0x140024a04  cmp     eax, 8000h
0x140024a09  jz      loc_140024AC8
0x140024a0f  mov     edx, edi
0x140024a11  mov     rcx, rbp
0x140024a14  call    SdbGetTagDataSize
0x140024a19  mov     edx, ebx
0x140024a1b  mov     esi, eax
0x140024a1d  mov     rcx, r14
0x140024a20  call    SdbGetTagDataSize
0x140024a25  mov     eax, eax
0x140024a27  cmp     rsi, rax
0x140024a2a  jnz     short loc_140024A9F
0x140024a2c  cmp     rsi, 20000000h
0x140024a33  jz      short loc_140024A9F
0x140024a35  mov     edx, edi
0x140024a37  mov     rcx, rbp
0x140024a3a  call    SdbpGetMappedTagData
0x140024a3f  mov     edx, ebx
0x140024a41  mov     rcx, r14
0x140024a44  mov     rdi, rax
0x140024a47  call    SdbpGetMappedTagData
0x140024a4c  mov     rdx, rax; Source2
0x140024a4f  test    rsi, rsi
0x140024a52  jz      short loc_140024AA6
0x140024a54  test    rdi, rdi
0x140024a57  jz      short loc_140024A67
0x140024a59  test    rax, rax
0x140024a5c  jnz     short loc_140024AA6
0x140024a5e  lea     rax, aSecondTag; "second tag"
0x140024a65  jmp     short loc_140024A7C
0x140024a67  test    rdx, rdx
0x140024a6a  lea     rcx, aFirstTag; "first tag"
0x140024a71  lea     rax, aBothTags; "both tags"
0x140024a78  cmovnz  rax, rcx
0x140024a7c  lea     r9, aSdbpgetmappedt; "SdbpGetMappedTagData returned null data"...
0x140024a83  mov     [rsp+68h+var_48], rax
0x140024a88  mov     r8d, 381h
0x140024a8e  lea     rdx, aSdbpmergeareta; "SdbpMergeAreTagValuesEqual"
0x140024a95  mov     ecx, 1
0x140024a9a  call    AslLogCallPrintf
0x140024a9f  xor     eax, eax
0x140024aa1  jmp     loc_140024B54
0x140024aa6  mov     r8, rsi; Length
0x140024aa9  mov     rcx, rdi; Source1
0x140024aac  call    cs:__imp_RtlCompareMemory
0x140024ab3  nop     dword ptr [rax+rax+00h]
0x140024ab8  cmp     rsi, rax
0x140024abb  mov     ecx, r15d
0x140024abe  setz    cl
0x140024ac1  mov     eax, ecx
0x140024ac3  jmp     loc_140024B54
0x140024ac8  and     cx, dx
0x140024acb  mov     eax, 0DFFFh
0x140024ad0  sub     cx, r8w
0x140024ad4  test    ax, cx
0x140024ad7  jnz     short loc_140024A9F
0x140024ad9  mov     edx, edi
0x140024adb  mov     rcx, rbp
0x140024ade  call    SdbGetStringTagPtr
0x140024ae3  mov     edx, ebx
0x140024ae5  mov     rcx, r14
0x140024ae8  mov     rbp, rax
0x140024aeb  call    SdbGetStringTagPtr
0x140024af0  mov     rsi, rax
0x140024af3  test    rbp, rbp
0x140024af6  jz      short loc_140024B3E
0x140024af8  test    rax, rax
0x140024afb  jz      short loc_140024B3E
0x140024afd  movzx   ecx, word ptr [rsi]; C
0x140024b00  cmp     [rbp+0], r15w
0x140024b05  jz      short loc_140024B39
0x140024b07  movzx   ebx, word ptr [rbp+0]
0x140024b0b  call    cs:__imp_toupper
0x140024b12  nop     dword ptr [rax+rax+00h]
0x140024b17  mov     ecx, ebx; C
0x140024b19  mov     edi, eax
0x140024b1b  call    cs:__imp_toupper
0x140024b22  nop     dword ptr [rax+rax+00h]
0x140024b27  cmp     eax, edi
0x140024b29  jnz     loc_140024A9F
0x140024b2f  add     rbp, 2
0x140024b33  add     rsi, 2
0x140024b37  jmp     short loc_140024AFD
0x140024b39  test    cx, cx
0x140024b3c  jmp     short loc_140024B4E
0x140024b3e  cmp     rbp, rsi
0x140024b41  jmp     short loc_140024B4E
0x140024b43  and     cx, dx
0x140024b46  cmp     cx, r8w
0x140024b4a  jmp     short loc_140024B4E
0x140024b4c  cmp     edi, ebx
0x140024b4e  mov     eax, r15d
0x140024b51  setz    al
0x140024b54  add     rsp, 38h
0x140024b58  pop     r15
0x140024b5a  pop     r14
0x140024b5c  pop     rdi
0x140024b5d  pop     rsi
0x140024b5e  pop     rbp
0x140024b5f  pop     rbx
0x140024b60  retn
```
