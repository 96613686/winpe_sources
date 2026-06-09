# SdbpMergeAreTagValuesEqual

- ea: `0x1800504a4`
- end: `0x180050658`
- name: `SdbpMergeAreTagValuesEqual`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b7f8`

## callees

- `0x18000beb0`
- `0x18000efe0`
- `0x18000f114`
- `0x18000f150`
- `0x180010db0`
- `0x1800504a4`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800505bc`
- `ntdll!RtlCompareMemory` at `0x1800505bc`
- `ntdll!toupper` at `0x180050612`
- `ntdll!toupper` at `0x18005061c`
- `ntdll!toupper` at `0x180050612`
- `ntdll!toupper` at `0x18005061c`

## pseudocode

```c
_BOOL8 __fastcall SdbpMergeAreTagValuesEqual(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
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
0x1800504a4  push    rbx
0x1800504a6  push    rbp
0x1800504a7  push    rsi
0x1800504a8  push    rdi
0x1800504a9  push    r14
0x1800504ab  push    r15
0x1800504ad  sub     rsp, 38h
0x1800504b1  xor     r15d, r15d
0x1800504b4  mov     ebx, r9d
0x1800504b7  mov     r14, r8
0x1800504ba  mov     edi, edx
0x1800504bc  mov     rbp, rcx
0x1800504bf  test    edx, edx
0x1800504c1  jz      loc_180050643
0x1800504c7  test    ebx, ebx
0x1800504c9  jz      loc_180050643
0x1800504cf  call    SdbGetTagFromTagID
0x1800504d4  mov     edx, ebx
0x1800504d6  movzx   esi, ax
0x1800504d9  mov     rcx, r14
0x1800504dc  call    SdbGetTagFromTagID
0x1800504e1  movzx   ecx, ax
0x1800504e4  cmp     si, ax
0x1800504e7  jnz     loc_1800505AF
0x1800504ed  mov     eax, esi
0x1800504ef  mov     edx, 0F000h
0x1800504f4  and     eax, edx
0x1800504f6  mov     r8d, 1000h
0x1800504fc  cmp     eax, r8d
0x1800504ff  jz      loc_18005063A
0x180050505  mov     r8d, 6000h
0x18005050b  cmp     eax, r8d
0x18005050e  jz      loc_1800505CF
0x180050514  cmp     eax, 8000h
0x180050519  jz      loc_1800505CF
0x18005051f  mov     edx, edi
0x180050521  mov     rcx, rbp
0x180050524  call    SdbGetTagDataSize
0x180050529  mov     edx, ebx
0x18005052b  mov     esi, eax
0x18005052d  mov     rcx, r14
0x180050530  call    SdbGetTagDataSize
0x180050535  mov     eax, eax
0x180050537  cmp     rsi, rax
0x18005053a  jnz     short loc_1800505AF
0x18005053c  cmp     rsi, 20000000h
0x180050543  jz      short loc_1800505AF
0x180050545  mov     edx, edi
0x180050547  mov     rcx, rbp
0x18005054a  call    SdbpGetMappedTagData
0x18005054f  mov     edx, ebx
0x180050551  mov     rcx, r14
0x180050554  mov     rdi, rax
0x180050557  call    SdbpGetMappedTagData
0x18005055c  mov     rdx, rax; Source2
0x18005055f  test    rsi, rsi
0x180050562  jz      short loc_1800505B6
0x180050564  test    rdi, rdi
0x180050567  jz      short loc_180050577
0x180050569  test    rax, rax
0x18005056c  jnz     short loc_1800505B6
0x18005056e  lea     rax, aSecondTag; "second tag"
0x180050575  jmp     short loc_18005058C
0x180050577  test    rdx, rdx
0x18005057a  lea     rcx, aFirstTag; "first tag"
0x180050581  lea     rax, aBothTags; "both tags"
0x180050588  cmovnz  rax, rcx
0x18005058c  lea     r9, aSdbpgetmappedt; "SdbpGetMappedTagData returned null data"...
0x180050593  mov     [rsp+68h+var_48], rax
0x180050598  mov     r8d, 381h
0x18005059e  lea     rdx, aSdbpmergeareta; "SdbpMergeAreTagValuesEqual"
0x1800505a5  mov     ecx, 1
0x1800505aa  call    AslLogCallPrintf
0x1800505af  xor     eax, eax
0x1800505b1  jmp     loc_18005064B
0x1800505b6  mov     r8, rsi; Length
0x1800505b9  mov     rcx, rdi; Source1
0x1800505bc  call    cs:__imp_RtlCompareMemory
0x1800505c2  cmp     rsi, rax
0x1800505c5  mov     ecx, r15d
0x1800505c8  setz    cl
0x1800505cb  mov     eax, ecx
0x1800505cd  jmp     short loc_18005064B
0x1800505cf  and     cx, dx
0x1800505d2  mov     eax, 0DFFFh
0x1800505d7  sub     cx, r8w
0x1800505db  test    ax, cx
0x1800505de  jnz     short loc_1800505AF
0x1800505e0  mov     edx, edi
0x1800505e2  mov     rcx, rbp
0x1800505e5  call    SdbGetStringTagPtr
0x1800505ea  mov     edx, ebx
0x1800505ec  mov     rcx, r14
0x1800505ef  mov     rbp, rax
0x1800505f2  call    SdbGetStringTagPtr
0x1800505f7  mov     rsi, rax
0x1800505fa  test    rbp, rbp
0x1800505fd  jz      short loc_180050635
0x1800505ff  test    rax, rax
0x180050602  jz      short loc_180050635
0x180050604  movzx   ecx, word ptr [rsi]; C
0x180050607  cmp     [rbp+0], r15w
0x18005060c  jz      short loc_180050630
0x18005060e  movzx   ebx, word ptr [rbp+0]
0x180050612  call    cs:__imp_toupper
0x180050618  mov     ecx, ebx; C
0x18005061a  mov     edi, eax
0x18005061c  call    cs:__imp_toupper
0x180050622  cmp     eax, edi
0x180050624  jnz     short loc_1800505AF
0x180050626  add     rbp, 2
0x18005062a  add     rsi, 2
0x18005062e  jmp     short loc_180050604
0x180050630  test    cx, cx
0x180050633  jmp     short loc_180050645
0x180050635  cmp     rbp, rsi
0x180050638  jmp     short loc_180050645
0x18005063a  and     cx, dx
0x18005063d  cmp     cx, r8w
0x180050641  jmp     short loc_180050645
0x180050643  cmp     edi, ebx
0x180050645  mov     eax, r15d
0x180050648  setz    al
0x18005064b  add     rsp, 38h
0x18005064f  pop     r15
0x180050651  pop     r14
0x180050653  pop     rdi
0x180050654  pop     rsi
0x180050655  pop     rbp
0x180050656  pop     rbx
0x180050657  retn
```
