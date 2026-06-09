# sub_18015CFEC

- ea: `0x18015cfec`
- end: `0x18015d11c`
- name: `sub_18015CFEC`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18013f8ac`

## callees

- `0x180057e60`
- `0x180095ae0`
- `0x18015cfec`

## import_xrefs

- `MpClient!MpConfigClose` at `0x18015d02c`
- `MpClient!MpConfigClose` at `0x18015d101`
- `MpClient!MpConfigClose` at `0x18015d02c`
- `MpClient!MpConfigClose` at `0x18015d101`
- `MpClient!MpConfigDelValue` at `0x18015d040`
- `MpClient!MpConfigDelValue` at `0x18015d090`
- `MpClient!MpConfigDelValue` at `0x18015d0c8`
- `MpClient!MpConfigDelValue` at `0x18015d040`
- `MpClient!MpConfigDelValue` at `0x18015d090`
- `MpClient!MpConfigDelValue` at `0x18015d0c8`
- `MpClient!MpConfigOpen` at `0x18015d016`
- `MpClient!MpConfigOpen` at `0x18015d016`

## pseudocode

```c
__int64 sub_18015CFEC()
{
  int v0; // eax
  _UNKNOWN **v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  int v5; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  v0 = MpConfigOpen(L"Features", &v10);
  v4 = v10;
  v5 = v0;
  if ( v0 < 0 )
  {
LABEL_2:
    if ( v4 )
      MpConfigClose(v4, v1, v2, v3);
    return (unsigned int)v5;
  }
  v5 = MpConfigDelValue(v10, L"MpFC_Dlp_PauseResume_Enable", v2, v3);
  if ( v5 < 0 )
  {
    v7 = off_18033CF60;
    v1 = &off_18033CF60;
    if ( off_18033CF60 == (_UNKNOWN *)&off_18033CF60 || (*((_BYTE *)off_18033CF60 + 28) & 1) == 0 )
      goto LABEL_10;
    v8 = 159;
LABEL_9:
    sub_180095AE0(v7[2], v8, &stru_1802CE128, (unsigned int)v5);
LABEL_10:
    v4 = v10;
    goto LABEL_2;
  }
  v5 = MpConfigDelValue(v10, L"MpFC_Dlp_PauseResume_WaitTime", v2, v3);
  if ( v5 < 0 )
  {
    v7 = off_18033CF60;
    v1 = &off_18033CF60;
    if ( off_18033CF60 == (_UNKNOWN *)&off_18033CF60 || (*((_BYTE *)off_18033CF60 + 28) & 1) == 0 )
      goto LABEL_10;
    v8 = 160;
    goto LABEL_9;
  }
  v5 = MpConfigDelValue(v10, L"MpFC_Dlp_PauseResume_ActionType", v2, v3);
  if ( v5 < 0 )
  {
    v7 = off_18033CF60;
    v1 = &off_18033CF60;
    if ( off_18033CF60 == (_UNKNOWN *)&off_18033CF60 || (*((_BYTE *)off_18033CF60 + 28) & 1) == 0 )
      goto LABEL_10;
    v8 = 161;
    goto LABEL_9;
  }
  if ( v10 )
    MpConfigClose(v10, v9, v2, v3);
  return 0;
}

```

## disassembly

```asm
0x18015cfec  push    rbx
0x18015cfee  sub     rsp, 30h
0x18015cff2  mov     rax, cs:__security_cookie
0x18015cff9  xor     rax, rsp
0x18015cffc  mov     [rsp+38h+var_10], rax
0x18015d001  lea     rdx, [rsp+38h+var_18]
0x18015d006  mov     [rsp+38h+var_18], 0
0x18015d00f  lea     rcx, aFeatures_0; "Features"
0x18015d016  call    cs:MpConfigOpen
0x18015d01c  mov     rcx, [rsp+38h+var_18]
0x18015d021  mov     ebx, eax
0x18015d023  test    eax, eax
0x18015d025  jns     short loc_18015D039
0x18015d027  test    rcx, rcx
0x18015d02a  jz      short loc_18015D032
0x18015d02c  call    cs:MpConfigClose
0x18015d032  mov     eax, ebx
0x18015d034  jmp     loc_18015D109
0x18015d039  lea     rdx, aMpfcDlpPausere; "MpFC_Dlp_PauseResume_Enable"
0x18015d040  call    cs:MpConfigDelValue
0x18015d046  mov     ebx, eax
0x18015d048  test    eax, eax
0x18015d04a  jns     short loc_18015D084
0x18015d04c  mov     rcx, cs:off_18033CF60
0x18015d053  lea     rdx, off_18033CF60
0x18015d05a  cmp     rcx, rdx
0x18015d05d  jz      short loc_18015D07D
0x18015d05f  test    byte ptr [rcx+1Ch], 1
0x18015d063  jz      short loc_18015D07D
0x18015d065  mov     edx, 9Fh
0x18015d06a  mov     rcx, [rcx+10h]
0x18015d06e  lea     r8, stru_1802CE128
0x18015d075  mov     r9d, ebx
0x18015d078  call    sub_180095AE0
0x18015d07d  mov     rcx, [rsp+38h+var_18]
0x18015d082  jmp     short loc_18015D027
0x18015d084  mov     rcx, [rsp+38h+var_18]
0x18015d089  lea     rdx, aMpfcDlpPausere_0; "MpFC_Dlp_PauseResume_WaitTime"
0x18015d090  call    cs:MpConfigDelValue
0x18015d096  mov     ebx, eax
0x18015d098  test    eax, eax
0x18015d09a  jns     short loc_18015D0BC
0x18015d09c  mov     rcx, cs:off_18033CF60
0x18015d0a3  lea     rdx, off_18033CF60
0x18015d0aa  cmp     rcx, rdx
0x18015d0ad  jz      short loc_18015D07D
0x18015d0af  test    byte ptr [rcx+1Ch], 1
0x18015d0b3  jz      short loc_18015D07D
0x18015d0b5  mov     edx, 0A0h
0x18015d0ba  jmp     short loc_18015D06A
0x18015d0bc  mov     rcx, [rsp+38h+var_18]
0x18015d0c1  lea     rdx, aMpfcDlpPausere_1; "MpFC_Dlp_PauseResume_ActionType"
0x18015d0c8  call    cs:MpConfigDelValue
0x18015d0ce  mov     ebx, eax
0x18015d0d0  test    eax, eax
0x18015d0d2  jns     short loc_18015D0F7
0x18015d0d4  mov     rcx, cs:off_18033CF60
0x18015d0db  lea     rdx, off_18033CF60
0x18015d0e2  cmp     rcx, rdx
0x18015d0e5  jz      short loc_18015D07D
0x18015d0e7  test    byte ptr [rcx+1Ch], 1
0x18015d0eb  jz      short loc_18015D07D
0x18015d0ed  mov     edx, 0A1h
0x18015d0f2  jmp     loc_18015D06A
0x18015d0f7  mov     rcx, [rsp+38h+var_18]
0x18015d0fc  test    rcx, rcx
0x18015d0ff  jz      short loc_18015D107
0x18015d101  call    cs:MpConfigClose
0x18015d107  xor     eax, eax
0x18015d109  mov     rcx, [rsp+38h+var_10]
0x18015d10e  xor     rcx, rsp; StackCookie
0x18015d111  call    __security_check_cookie
0x18015d116  add     rsp, 30h
0x18015d11a  pop     rbx
0x18015d11b  retn
```
