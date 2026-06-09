# sub_18015CCFC

- ea: `0x18015ccfc`
- end: `0x18015cdb6`
- name: `sub_18015CCFC`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18013f8ac`

## callees

- `0x180057e60`
- `0x180095ae0`
- `0x18015ccfc`

## import_xrefs

- `MpClient!MpConfigClose` at `0x18015cd3c`
- `MpClient!MpConfigClose` at `0x18015cd9b`
- `MpClient!MpConfigClose` at `0x18015cd3c`
- `MpClient!MpConfigClose` at `0x18015cd9b`
- `MpClient!MpConfigDelValue` at `0x18015cd4d`
- `MpClient!MpConfigDelValue` at `0x18015cd4d`
- `MpClient!MpConfigOpen` at `0x18015cd26`
- `MpClient!MpConfigOpen` at `0x18015cd26`

## pseudocode

```c
__int64 sub_18015CCFC()
{
  int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v0 = MpConfigOpen(L"Features", &v7);
  v4 = v7;
  v5 = v0;
  if ( v0 < 0 )
  {
LABEL_2:
    if ( v4 )
      MpConfigClose(v4, v1, v2, v3);
    return (unsigned int)v5;
  }
  v5 = MpConfigDelValue(v7, L"DlpAnyAppEnabled", v2, v3);
  if ( v5 < 0 )
  {
    if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
      sub_180095AE0(*((_QWORD *)off_18033CF60 + 2), 149, &stru_1802CE128, (unsigned int)v5);
    v4 = v7;
    goto LABEL_2;
  }
  if ( v7 )
    MpConfigClose(v7, v1, v2, v3);
  return 0;
}

```

## disassembly

```asm
0x18015ccfc  push    rbx
0x18015ccfe  sub     rsp, 30h
0x18015cd02  mov     rax, cs:__security_cookie
0x18015cd09  xor     rax, rsp
0x18015cd0c  mov     [rsp+38h+var_10], rax
0x18015cd11  lea     rdx, [rsp+38h+var_18]
0x18015cd16  mov     [rsp+38h+var_18], 0
0x18015cd1f  lea     rcx, aFeatures_0; "Features"
0x18015cd26  call    cs:MpConfigOpen
0x18015cd2c  mov     rcx, [rsp+38h+var_18]
0x18015cd31  mov     ebx, eax
0x18015cd33  test    eax, eax
0x18015cd35  jns     short loc_18015CD46
0x18015cd37  test    rcx, rcx
0x18015cd3a  jz      short loc_18015CD42
0x18015cd3c  call    cs:MpConfigClose
0x18015cd42  mov     eax, ebx
0x18015cd44  jmp     short loc_18015CDA3
0x18015cd46  lea     rdx, aDlpanyappenabl; "DlpAnyAppEnabled"
0x18015cd4d  call    cs:MpConfigDelValue
0x18015cd53  mov     ebx, eax
0x18015cd55  test    eax, eax
0x18015cd57  jns     short loc_18015CD91
0x18015cd59  mov     rcx, cs:off_18033CF60
0x18015cd60  lea     rax, off_18033CF60
0x18015cd67  cmp     rcx, rax
0x18015cd6a  jz      short loc_18015CD8A
0x18015cd6c  test    byte ptr [rcx+1Ch], 1
0x18015cd70  jz      short loc_18015CD8A
0x18015cd72  mov     rcx, [rcx+10h]
0x18015cd76  lea     r8, stru_1802CE128
0x18015cd7d  mov     edx, 95h
0x18015cd82  mov     r9d, ebx
0x18015cd85  call    sub_180095AE0
0x18015cd8a  mov     rcx, [rsp+38h+var_18]
0x18015cd8f  jmp     short loc_18015CD37
0x18015cd91  mov     rcx, [rsp+38h+var_18]
0x18015cd96  test    rcx, rcx
0x18015cd99  jz      short loc_18015CDA1
0x18015cd9b  call    cs:MpConfigClose
0x18015cda1  xor     eax, eax
0x18015cda3  mov     rcx, [rsp+38h+var_10]
0x18015cda8  xor     rcx, rsp; StackCookie
0x18015cdab  call    __security_check_cookie
0x18015cdb0  add     rsp, 30h
0x18015cdb4  pop     rbx
0x18015cdb5  retn
```
