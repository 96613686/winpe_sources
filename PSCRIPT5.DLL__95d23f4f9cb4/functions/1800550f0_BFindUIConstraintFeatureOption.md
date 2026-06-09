# BFindUIConstraintFeatureOption

- ea: `0x1800550f0`
- end: `0x1800552b7`
- name: `BFindUIConstraintFeatureOption`
- size: `455`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180056f4c`
- `0x180057f44`

## callees

- `0x1800550f0`
- `0x180056744`

## string_xrefs

- `0x18005523a`: `InstalledMemory`

## pseudocode

```c
_BOOL8 __fastcall BFindUIConstraintFeatureOption(
        __int64 a1,
        const char *a2,
        __int64 *a3,
        __int64 a4,
        const char *a5,
        __int64 *a6,
        _DWORD *a7)
{
  char v10; // al
  const char *v11; // r9
  const char *v12; // rax
  int v13; // edx
  int v14; // r8d
  const char *v15; // rbx
  const char *v16; // rax
  int v17; // r8d
  int v18; // ecx
  const char *v19; // rax
  int v20; // r8d
  int v21; // ecx
  const char *v22; // rdx
  const char *v23; // rax
  int v24; // r8d
  int v25; // ecx
  const char *v26; // rax
  int v27; // ecx
  int v28; // r8d
  __int64 ListItem; // rax
  __int64 v30; // rax
  _BOOL8 result; // rax

  if ( *a2 == 42 )
    v10 = a2[1];
  else
    v10 = *a2;
  v11 = a2 + 1;
  if ( *a2 != 42 )
    v11 = a2;
  if ( !v10 || !v11 )
    return 0;
  v12 = v11;
  do
  {
    v13 = (unsigned __int8)v12["ManualFeed" - v11];
    v14 = *(unsigned __int8 *)v12 - v13;
    if ( v14 )
      break;
    ++v12;
  }
  while ( v13 );
  v15 = a5;
  if ( v14 )
    goto LABEL_22;
  if ( !*a5 )
    goto LABEL_21;
  v16 = a5;
  do
  {
    v17 = (unsigned __int8)v16["True" - a5];
    v18 = *(unsigned __int8 *)v16 - v17;
    if ( v18 )
      break;
    ++v16;
  }
  while ( v17 );
  if ( !v18 )
    goto LABEL_21;
  v19 = a5;
  do
  {
    v20 = (unsigned __int8)v19[gstrOnKwd - a5];
    v21 = *(unsigned __int8 *)v19 - v20;
    if ( v21 )
      break;
    ++v19;
  }
  while ( v20 );
  if ( v21 )
  {
LABEL_22:
    v23 = v11;
    do
    {
      v24 = (unsigned __int8)v23["CustomPageSize" - v11];
      v25 = *(unsigned __int8 *)v23 - v24;
      if ( v25 )
        break;
      ++v23;
    }
    while ( v24 );
    if ( v25 || *a5 && strcmp(a5, "True") )
    {
      v26 = v11;
      do
      {
        v27 = (unsigned __int8)v26["VMOption" - v11];
        v28 = *(unsigned __int8 *)v26 - v27;
        if ( v28 )
          break;
        ++v26;
      }
      while ( v27 );
      v22 = "InstalledMemory";
      if ( v28 )
        v22 = v11;
    }
    else
    {
      v22 = "PageSize";
      v15 = "CustomPageSize";
    }
  }
  else
  {
LABEL_21:
    v22 = "InputSlot";
    v15 = "ManualFeed";
  }
  ListItem = PvFindListItem(*(_QWORD *)(a1 + 152), v22, a4);
  *a3 = ListItem;
  if ( !ListItem )
    return 0;
  if ( *v15 )
  {
    v30 = PvFindListItem(*(_QWORD *)(ListItem + 88), v15, a7);
    *a6 = v30;
    return v30 != 0;
  }
  else
  {
    result = 1;
    *a6 = 0;
    *a7 = 255;
  }
  return result;
}

```

## disassembly

```asm
0x1800550f0  mov     [rsp+arg_0], rbx
0x1800550f5  mov     [rsp+arg_8], rsi
0x1800550fa  push    rdi
0x1800550fb  sub     rsp, 20h
0x1800550ff  cmp     byte ptr [rdx], 2Ah ; '*'
0x180055102  mov     r11, r9
0x180055105  mov     rdi, r8
0x180055108  mov     rsi, rcx
0x18005510b  jnz     short loc_180055112
0x18005510d  mov     al, [rdx+1]
0x180055110  jmp     short loc_180055114
0x180055112  mov     al, [rdx]
0x180055114  lea     r9, [rdx+1]
0x180055118  cmovnz  r9, rdx
0x18005511c  test    al, al
0x18005511e  jz      loc_1800552A5
0x180055124  test    r9, r9
0x180055127  jz      loc_1800552A5
0x18005512d  lea     rcx, gstrManualFeedKwd; "ManualFeed"
0x180055134  mov     rax, r9
0x180055137  sub     rcx, r9
0x18005513a  movzx   r8d, byte ptr [rax]
0x18005513e  movzx   edx, byte ptr [rax+rcx]
0x180055142  sub     r8d, edx
0x180055145  jnz     short loc_18005514E
0x180055147  inc     rax
0x18005514a  test    edx, edx
0x18005514c  jnz     short loc_18005513A
0x18005514e  mov     rbx, [rsp+28h+arg_20]
0x180055153  lea     r10, gstrTrueKwd; "True"
0x18005515a  test    r8d, r8d
0x18005515d  jnz     short loc_1800551BF
0x18005515f  cmp     [rbx], r8b
0x180055162  jz      short loc_1800551AC
0x180055164  mov     rdx, r10
0x180055167  mov     rax, rbx
0x18005516a  sub     rdx, rbx
0x18005516d  movzx   ecx, byte ptr [rax]
0x180055170  movzx   r8d, byte ptr [rax+rdx]
0x180055175  sub     ecx, r8d
0x180055178  jnz     short loc_180055182
0x18005517a  inc     rax
0x18005517d  test    r8d, r8d
0x180055180  jnz     short loc_18005516D
0x180055182  test    ecx, ecx
0x180055184  jz      short loc_1800551AC
0x180055186  lea     rdx, gstrOnKwd
0x18005518d  mov     rax, rbx
0x180055190  sub     rdx, rbx
0x180055193  movzx   ecx, byte ptr [rax]
0x180055196  movzx   r8d, byte ptr [rax+rdx]
0x18005519b  sub     ecx, r8d
0x18005519e  jnz     short loc_1800551A8
0x1800551a0  inc     rax
0x1800551a3  test    r8d, r8d
0x1800551a6  jnz     short loc_180055193
0x1800551a8  test    ecx, ecx
0x1800551aa  jnz     short loc_1800551BF
0x1800551ac  lea     rdx, gstrInputSlotKwd; "InputSlot"
0x1800551b3  lea     rbx, gstrManualFeedKwd; "ManualFeed"
0x1800551ba  jmp     loc_180055245
0x1800551bf  lea     rdx, gstrCustomSizeKwd; "CustomPageSize"
0x1800551c6  mov     rax, r9
0x1800551c9  sub     rdx, r9
0x1800551cc  movzx   ecx, byte ptr [rax]
0x1800551cf  movzx   r8d, byte ptr [rax+rdx]
0x1800551d4  sub     ecx, r8d
0x1800551d7  jnz     short loc_1800551E1
0x1800551d9  inc     rax
0x1800551dc  test    r8d, r8d
0x1800551df  jnz     short loc_1800551CC
0x1800551e1  test    ecx, ecx
0x1800551e3  jnz     short loc_180055216
0x1800551e5  cmp     [rbx], cl
0x1800551e7  jz      short loc_180055206
0x1800551e9  mov     rax, rbx
0x1800551ec  sub     r10, rbx
0x1800551ef  movzx   ecx, byte ptr [rax]
0x1800551f2  movzx   edx, byte ptr [rax+r10]
0x1800551f7  sub     ecx, edx
0x1800551f9  jnz     short loc_180055202
0x1800551fb  inc     rax
0x1800551fe  test    edx, edx
0x180055200  jnz     short loc_1800551EF
0x180055202  test    ecx, ecx
0x180055204  jnz     short loc_180055216
0x180055206  lea     rdx, gstrPageSizeKwd; "PageSize"
0x18005520d  lea     rbx, gstrCustomSizeKwd; "CustomPageSize"
0x180055214  jmp     short loc_180055245
0x180055216  lea     rdx, gstrVMOptionKwd; "VMOption"
0x18005521d  mov     rax, r9
0x180055220  sub     rdx, r9
0x180055223  movzx   r8d, byte ptr [rax]
0x180055227  movzx   ecx, byte ptr [rax+rdx]
0x18005522b  sub     r8d, ecx
0x18005522e  jnz     short loc_180055237
0x180055230  inc     rax
0x180055233  test    ecx, ecx
0x180055235  jnz     short loc_180055223
0x180055237  test    r8d, r8d
0x18005523a  lea     rdx, gstrInstallMemKwd; "InstalledMemory"
0x180055241  cmovnz  rdx, r9
0x180055245  mov     rcx, [rsi+98h]
0x18005524c  mov     r8, r11
0x18005524f  call    PvFindListItem
0x180055254  mov     [rdi], rax
0x180055257  test    rax, rax
0x18005525a  jz      short loc_1800552A5
0x18005525c  cmp     byte ptr [rbx], 0
0x18005525f  jz      short loc_180055287
0x180055261  mov     r8, [rsp+28h+arg_30]
0x180055266  mov     rdx, rbx
0x180055269  mov     rcx, [rax+58h]
0x18005526d  call    PvFindListItem
0x180055272  mov     r8, rax
0x180055275  mov     rax, [rsp+28h+arg_28]
0x18005527a  mov     [rax], r8
0x18005527d  xor     eax, eax
0x18005527f  test    r8, r8
0x180055282  setnz   al
0x180055285  jmp     short loc_1800552A7
0x180055287  mov     rcx, [rsp+28h+arg_28]
0x18005528c  mov     eax, 1
0x180055291  mov     qword ptr [rcx], 0
0x180055298  mov     rcx, [rsp+28h+arg_30]
0x18005529d  mov     dword ptr [rcx], 0FFh
0x1800552a3  jmp     short loc_1800552A7
0x1800552a5  xor     eax, eax
0x1800552a7  mov     rbx, [rsp+28h+arg_0]
0x1800552ac  mov     rsi, [rsp+28h+arg_8]
0x1800552b1  add     rsp, 20h
0x1800552b5  pop     rdi
0x1800552b6  retn
```
