# BFindUIConstraintFeatureOption

- ea: `0x180056b4c`
- end: `0x180056d14`
- name: `BFindUIConstraintFeatureOption`
- size: `456`
- prototype: `_BOOL8 __fastcall(__int64, const char *, __int64 *, __int64, const char *, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180058b50`
- `0x180059b58`

## callees

- `0x180056b4c`
- `0x1800582c4`

## string_xrefs

- `0x180056c96`: `InstalledMemory`

## pseudocode

```c
_BOOL8 __fastcall BFindUIConstraintFeatureOption(
        __int64 a1,
        const char *a2,
        __int64 *a3,
        _DWORD *a4,
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
  _QWORD *ListItem; // rax
  _QWORD *v30; // rax
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
  ListItem = PvFindListItem(*(_QWORD **)(a1 + 152), (__int64)v22, a4);
  *a3 = (__int64)ListItem;
  if ( !ListItem )
    return 0;
  if ( *v15 )
  {
    v30 = PvFindListItem((_QWORD *)ListItem[11], (__int64)v15, a7);
    *a6 = (__int64)v30;
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
0x180056b4c  mov     [rsp+arg_0], rbx
0x180056b51  mov     [rsp+arg_8], rsi
0x180056b56  push    rdi
0x180056b57  sub     rsp, 20h
0x180056b5b  cmp     byte ptr [rdx], 2Ah ; '*'
0x180056b5e  mov     r11, r9
0x180056b61  mov     rdi, r8
0x180056b64  mov     rsi, rcx
0x180056b67  jnz     short loc_180056B6E
0x180056b69  mov     al, [rdx+1]
0x180056b6c  jmp     short loc_180056B70
0x180056b6e  mov     al, [rdx]
0x180056b70  lea     r9, [rdx+1]
0x180056b74  cmovnz  r9, rdx
0x180056b78  test    al, al
0x180056b7a  jz      loc_180056D01
0x180056b80  test    r9, r9
0x180056b83  jz      loc_180056D01
0x180056b89  lea     rcx, gstrManualFeedKwd; "ManualFeed"
0x180056b90  mov     rax, r9
0x180056b93  sub     rcx, r9
0x180056b96  movzx   r8d, byte ptr [rax]
0x180056b9a  movzx   edx, byte ptr [rax+rcx]
0x180056b9e  sub     r8d, edx
0x180056ba1  jnz     short loc_180056BAA
0x180056ba3  inc     rax
0x180056ba6  test    edx, edx
0x180056ba8  jnz     short loc_180056B96
0x180056baa  mov     rbx, [rsp+28h+arg_20]
0x180056baf  lea     r10, gstrTrueKwd; "True"
0x180056bb6  test    r8d, r8d
0x180056bb9  jnz     short loc_180056C1B
0x180056bbb  cmp     [rbx], r8b
0x180056bbe  jz      short loc_180056C08
0x180056bc0  mov     rdx, r10
0x180056bc3  mov     rax, rbx
0x180056bc6  sub     rdx, rbx
0x180056bc9  movzx   ecx, byte ptr [rax]
0x180056bcc  movzx   r8d, byte ptr [rax+rdx]
0x180056bd1  sub     ecx, r8d
0x180056bd4  jnz     short loc_180056BDE
0x180056bd6  inc     rax
0x180056bd9  test    r8d, r8d
0x180056bdc  jnz     short loc_180056BC9
0x180056bde  test    ecx, ecx
0x180056be0  jz      short loc_180056C08
0x180056be2  lea     rdx, gstrOnKwd
0x180056be9  mov     rax, rbx
0x180056bec  sub     rdx, rbx
0x180056bef  movzx   ecx, byte ptr [rax]
0x180056bf2  movzx   r8d, byte ptr [rax+rdx]
0x180056bf7  sub     ecx, r8d
0x180056bfa  jnz     short loc_180056C04
0x180056bfc  inc     rax
0x180056bff  test    r8d, r8d
0x180056c02  jnz     short loc_180056BEF
0x180056c04  test    ecx, ecx
0x180056c06  jnz     short loc_180056C1B
0x180056c08  lea     rdx, gstrInputSlotKwd; "InputSlot"
0x180056c0f  lea     rbx, gstrManualFeedKwd; "ManualFeed"
0x180056c16  jmp     loc_180056CA1
0x180056c1b  lea     rdx, gstrCustomSizeKwd; "CustomPageSize"
0x180056c22  mov     rax, r9
0x180056c25  sub     rdx, r9
0x180056c28  movzx   ecx, byte ptr [rax]
0x180056c2b  movzx   r8d, byte ptr [rax+rdx]
0x180056c30  sub     ecx, r8d
0x180056c33  jnz     short loc_180056C3D
0x180056c35  inc     rax
0x180056c38  test    r8d, r8d
0x180056c3b  jnz     short loc_180056C28
0x180056c3d  test    ecx, ecx
0x180056c3f  jnz     short loc_180056C72
0x180056c41  cmp     [rbx], cl
0x180056c43  jz      short loc_180056C62
0x180056c45  mov     rax, rbx
0x180056c48  sub     r10, rbx
0x180056c4b  movzx   ecx, byte ptr [rax]
0x180056c4e  movzx   edx, byte ptr [rax+r10]
0x180056c53  sub     ecx, edx
0x180056c55  jnz     short loc_180056C5E
0x180056c57  inc     rax
0x180056c5a  test    edx, edx
0x180056c5c  jnz     short loc_180056C4B
0x180056c5e  test    ecx, ecx
0x180056c60  jnz     short loc_180056C72
0x180056c62  lea     rdx, gstrPageSizeKwd; "PageSize"
0x180056c69  lea     rbx, gstrCustomSizeKwd; "CustomPageSize"
0x180056c70  jmp     short loc_180056CA1
0x180056c72  lea     rdx, gstrVMOptionKwd; "VMOption"
0x180056c79  mov     rax, r9
0x180056c7c  sub     rdx, r9
0x180056c7f  movzx   r8d, byte ptr [rax]
0x180056c83  movzx   ecx, byte ptr [rax+rdx]
0x180056c87  sub     r8d, ecx
0x180056c8a  jnz     short loc_180056C93
0x180056c8c  inc     rax
0x180056c8f  test    ecx, ecx
0x180056c91  jnz     short loc_180056C7F
0x180056c93  test    r8d, r8d
0x180056c96  lea     rdx, gstrInstallMemKwd; "InstalledMemory"
0x180056c9d  cmovnz  rdx, r9
0x180056ca1  mov     rcx, [rsi+98h]
0x180056ca8  mov     r8, r11
0x180056cab  call    PvFindListItem
0x180056cb0  mov     [rdi], rax
0x180056cb3  test    rax, rax
0x180056cb6  jz      short loc_180056D01
0x180056cb8  cmp     byte ptr [rbx], 0
0x180056cbb  jz      short loc_180056CE3
0x180056cbd  mov     r8, [rsp+28h+arg_30]
0x180056cc2  mov     rdx, rbx
0x180056cc5  mov     rcx, [rax+58h]
0x180056cc9  call    PvFindListItem
0x180056cce  mov     r8, rax
0x180056cd1  mov     rax, [rsp+28h+arg_28]
0x180056cd6  mov     [rax], r8
0x180056cd9  xor     eax, eax
0x180056cdb  test    r8, r8
0x180056cde  setnz   al
0x180056ce1  jmp     short loc_180056D03
0x180056ce3  mov     rcx, [rsp+28h+arg_28]
0x180056ce8  mov     eax, 1
0x180056ced  mov     qword ptr [rcx], 0
0x180056cf4  mov     rcx, [rsp+28h+arg_30]
0x180056cf9  mov     dword ptr [rcx], 0FFh
0x180056cff  jmp     short loc_180056D03
0x180056d01  xor     eax, eax
0x180056d03  mov     rbx, [rsp+28h+arg_0]
0x180056d08  mov     rsi, [rsp+28h+arg_8]
0x180056d0d  add     rsp, 20h
0x180056d11  pop     rdi
0x180056d12  retn
```
