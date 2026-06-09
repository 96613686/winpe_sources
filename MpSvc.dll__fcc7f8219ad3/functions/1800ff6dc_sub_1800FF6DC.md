# sub_1800FF6DC

- ea: `0x1800ff6dc`
- end: `0x1800ff9e9`
- name: `sub_1800FF6DC`
- size: `781`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db3c0`
- `0x1800e0cec`

## callees

- `0x18003c6f0`
- `0x180067aa0`
- `0x180067aec`
- `0x1800a9720`
- `0x1800a9750`
- `0x1800b25dc`
- `0x1800bcf74`
- `0x1800ff6dc`

## import_xrefs

- `MpClient!MpConfigOpen` at `0x1800ff722`
- `MpClient!MpConfigOpen` at `0x1800ff842`
- `MpClient!MpConfigOpen` at `0x1800ff722`
- `MpClient!MpConfigOpen` at `0x1800ff842`
- `MpClient!MpConfigClose` at `0x1800ff829`
- `MpClient!MpConfigClose` at `0x1800ff91d`
- `MpClient!MpConfigClose` at `0x1800ff970`
- `MpClient!MpConfigClose` at `0x1800ff9c3`
- `MpClient!MpConfigClose` at `0x1800ff829`
- `MpClient!MpConfigClose` at `0x1800ff91d`
- `MpClient!MpConfigClose` at `0x1800ff970`
- `MpClient!MpConfigClose` at `0x1800ff9c3`
- `MpClient!MpConfigGetValueAlloc` at `0x1800ff79b`
- `MpClient!MpConfigGetValueAlloc` at `0x1800ff79b`
- `MpClient!MpFreeMemory` at `0x1800ff762`
- `MpClient!MpFreeMemory` at `0x1800ff90e`
- `MpClient!MpFreeMemory` at `0x1800ff961`
- `MpClient!MpFreeMemory` at `0x1800ff9b4`
- `MpClient!MpFreeMemory` at `0x1800ff762`
- `MpClient!MpFreeMemory` at `0x1800ff90e`
- `MpClient!MpFreeMemory` at `0x1800ff961`
- `MpClient!MpFreeMemory` at `0x1800ff9b4`

## string_xrefs

- `0x1800ff786`: `ProductAppDataPath`
- `0x1800ff7b6`: `DLPCache`

## pseudocode

```c
__int64 __fastcall sub_1800FF6DC(__int64 a1)
{
  int ValueAlloc; // ebx
  __int64 v3; // rcx
  COMPUTER_NAME_FORMAT *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  COMPUTER_NAME_FORMAT *v10; // rdx
  void *v12; // rbx
  __int64 v13; // rdx
  unsigned int v14; // edi
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  int v17; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  int v19; // [rsp+50h] [rbp-10h] BYREF

  v15 = 0;
  v16 = 0;
  lpMem = 0;
  ValueAlloc = MpConfigOpen(L".", &v15);
  if ( ValueAlloc < 0 )
  {
    v3 = *(_QWORD *)&NameType;
    v4 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType == &NameType || (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 60;
LABEL_46:
    sub_1800A9750(*(_QWORD *)(v3 + 16), v5, &stru_1804C4148, (unsigned int)ValueAlloc);
LABEL_47:
    if ( v16 )
      MpFreeMemory(v16);
    if ( v15 )
      MpConfigClose(v15, v4);
    return (unsigned int)ValueAlloc;
  }
  if ( v16 )
    MpFreeMemory(v16);
  v19 = 2;
  v17 = 0;
  ValueAlloc = MpConfigGetValueAlloc(v15, L"ProductAppDataPath", &v19, &v17, &v16, 0);
  if ( ValueAlloc < 0 )
  {
    v3 = *(_QWORD *)&NameType;
    v4 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType == &NameType || (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 61;
    goto LABEL_46;
  }
  ValueAlloc = sub_18003C6F0(&lpMem, L"%ls\\%ls\\%ls", v16, L"DLPCache", L"FileEvidence");
  if ( ValueAlloc < 0 )
  {
    v7 = *(_QWORD *)&NameType;
    v4 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      v8 = 62;
LABEL_12:
      sub_1800A9750(*(_QWORD *)(v7 + 16), v8, &stru_1804C4148, (unsigned int)ValueAlloc);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  if ( v15 )
  {
    MpConfigClose(v15, v6);
    v15 = 0;
  }
  ValueAlloc = MpConfigOpen(L"Features", &v15);
  if ( ValueAlloc < 0 )
  {
    v7 = *(_QWORD *)&NameType;
    v4 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      v8 = 63;
      goto LABEL_12;
    }
LABEL_13:
    if ( lpMem )
      sub_180067AEC(lpMem);
    goto LABEL_47;
  }
  v17 = 0;
  ValueAlloc = sub_1800B25DC(v15, L"DlpFileEvidenceRetentionPeriod", &v17, 0);
  if ( ValueAlloc < 0 )
  {
    v7 = *(_QWORD *)&NameType;
    v4 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      v8 = 64;
      goto LABEL_12;
    }
    goto LABEL_13;
  }
  v9 = (unsigned int)(86400 * v17);
  if ( (_DWORD)v9 )
  {
    v12 = lpMem;
    v14 = sub_1800BCF74(lpMem, &pszFile, v9, a1, 0);
    if ( v12 )
      sub_180067AEC(v12);
    if ( v16 )
      MpFreeMemory(v16);
    if ( v15 )
      MpConfigClose(v15, v13);
    return v14;
  }
  else
  {
    v10 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
      sub_1800A9720(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 65, &stru_1804C4148);
    if ( lpMem )
      sub_180067AEC(lpMem);
    if ( v16 )
      MpFreeMemory(v16);
    if ( v15 )
      MpConfigClose(v15, v10);
    return 0;
  }
}

```

## disassembly

```asm
0x1800ff6dc  mov     [rsp-8+arg_8], rbx
0x1800ff6e1  mov     [rsp-8+arg_10], rdi
0x1800ff6e6  push    rbp
0x1800ff6e7  mov     rbp, rsp
0x1800ff6ea  sub     rsp, 60h
0x1800ff6ee  mov     rax, cs:__security_cookie
0x1800ff6f5  xor     rax, rsp
0x1800ff6f8  mov     [rbp+var_8], rax
0x1800ff6fc  mov     rdi, rcx
0x1800ff6ff  mov     [rbp+var_30], 0
0x1800ff707  lea     rcx, asc_1804AB18C; "."
0x1800ff70e  mov     [rbp+var_28], 0
0x1800ff716  lea     rdx, [rbp+var_30]
0x1800ff71a  mov     [rbp+lpMem], 0
0x1800ff722  call    cs:MpConfigOpen
0x1800ff728  mov     ebx, eax
0x1800ff72a  test    eax, eax
0x1800ff72c  jns     short loc_1800FF759
0x1800ff72e  mov     rcx, cs:NameType
0x1800ff735  lea     rdx, NameType
0x1800ff73c  cmp     rcx, rdx
0x1800ff73f  jz      loc_1800FF9AB
0x1800ff745  test    byte ptr [rcx+1Ch], 1
0x1800ff749  jz      loc_1800FF9AB
0x1800ff74f  mov     edx, 3Ch ; '<'
0x1800ff754  jmp     loc_1800FF998
0x1800ff759  mov     rcx, [rbp+var_28]
0x1800ff75d  test    rcx, rcx
0x1800ff760  jz      short loc_1800FF768
0x1800ff762  call    cs:__imp_MpFreeMemory
0x1800ff768  mov     rcx, [rbp+var_30]
0x1800ff76c  lea     rax, [rbp+var_28]
0x1800ff770  mov     [rsp+60h+var_38], 0
0x1800ff779  lea     r9, [rbp+var_20]
0x1800ff77d  lea     r8, [rbp+var_10]
0x1800ff781  mov     [rsp+60h+var_40], rax
0x1800ff786  lea     rdx, aProductappdata; "ProductAppDataPath"
0x1800ff78d  mov     [rbp+var_10], 2
0x1800ff794  mov     [rbp+var_20], 0
0x1800ff79b  call    cs:MpConfigGetValueAlloc
0x1800ff7a1  mov     ebx, eax
0x1800ff7a3  test    eax, eax
0x1800ff7a5  js      loc_1800FF97A
0x1800ff7ab  mov     r8, [rbp+var_28]
0x1800ff7af  lea     rax, aFileevidence; "FileEvidence"
0x1800ff7b6  lea     r9, aDlpcache; "DLPCache"
0x1800ff7bd  mov     [rsp+60h+var_40], rax
0x1800ff7c2  lea     rdx, aLsLsLs_0; "%ls\\%ls\\%ls"
0x1800ff7c9  lea     rcx, [rbp+lpMem]
0x1800ff7cd  call    sub_18003C6F0
0x1800ff7d2  mov     ebx, eax
0x1800ff7d4  test    eax, eax
0x1800ff7d6  jns     short loc_1800FF820
0x1800ff7d8  mov     rcx, cs:NameType
0x1800ff7df  lea     rdx, NameType
0x1800ff7e6  cmp     rcx, rdx
0x1800ff7e9  jz      short loc_1800FF809
0x1800ff7eb  test    byte ptr [rcx+1Ch], 1
0x1800ff7ef  jz      short loc_1800FF809
0x1800ff7f1  mov     edx, 3Eh ; '>'
0x1800ff7f6  mov     rcx, [rcx+10h]
0x1800ff7fa  lea     r8, stru_1804C4148
0x1800ff801  mov     r9d, ebx
0x1800ff804  call    sub_1800A9750
0x1800ff809  mov     rcx, [rbp+lpMem]; lpMem
0x1800ff80d  test    rcx, rcx
0x1800ff810  jz      loc_1800FF9AB
0x1800ff816  call    sub_180067AEC
0x1800ff81b  jmp     loc_1800FF9AB
0x1800ff820  mov     rcx, [rbp+var_30]
0x1800ff824  test    rcx, rcx
0x1800ff827  jz      short loc_1800FF837
0x1800ff829  call    cs:MpConfigClose
0x1800ff82f  mov     [rbp+var_30], 0
0x1800ff837  lea     rdx, [rbp+var_30]
0x1800ff83b  lea     rcx, aFeatures; "Features"
0x1800ff842  call    cs:MpConfigOpen
0x1800ff848  mov     ebx, eax
0x1800ff84a  test    eax, eax
0x1800ff84c  jns     short loc_1800FF86E
0x1800ff84e  mov     rcx, cs:NameType
0x1800ff855  lea     rdx, NameType
0x1800ff85c  cmp     rcx, rdx
0x1800ff85f  jz      short loc_1800FF809
0x1800ff861  test    byte ptr [rcx+1Ch], 1
0x1800ff865  jz      short loc_1800FF809
0x1800ff867  mov     edx, 3Fh ; '?'
0x1800ff86c  jmp     short loc_1800FF7F6
0x1800ff86e  mov     rcx, [rbp+var_30]
0x1800ff872  lea     r8, [rbp+var_20]
0x1800ff876  xor     r9d, r9d
0x1800ff879  mov     [rbp+var_20], 0
0x1800ff880  lea     rdx, aDlpfileevidenc; "DlpFileEvidenceRetentionPeriod"
0x1800ff887  call    sub_1800B25DC
0x1800ff88c  mov     ebx, eax
0x1800ff88e  test    eax, eax
0x1800ff890  jns     short loc_1800FF8BD
0x1800ff892  mov     rcx, cs:NameType
0x1800ff899  lea     rdx, NameType
0x1800ff8a0  cmp     rcx, rdx
0x1800ff8a3  jz      loc_1800FF809
0x1800ff8a9  test    byte ptr [rcx+1Ch], 1
0x1800ff8ad  jz      loc_1800FF809
0x1800ff8b3  mov     edx, 40h ; '@'
0x1800ff8b8  jmp     loc_1800FF7F6
0x1800ff8bd  imul    r8d, [rbp+var_20], 15180h
0x1800ff8c5  test    r8d, r8d
0x1800ff8c8  jnz     short loc_1800FF92A
0x1800ff8ca  mov     rcx, cs:NameType
0x1800ff8d1  lea     rdx, NameType
0x1800ff8d8  cmp     rcx, rdx
0x1800ff8db  jz      short loc_1800FF8F7
0x1800ff8dd  test    byte ptr [rcx+1Ch], 4
0x1800ff8e1  jz      short loc_1800FF8F7
0x1800ff8e3  mov     rcx, [rcx+10h]
0x1800ff8e7  lea     edx, [r8+41h]
0x1800ff8eb  lea     r8, stru_1804C4148
0x1800ff8f2  call    sub_1800A9720
0x1800ff8f7  mov     rcx, [rbp+lpMem]; lpMem
0x1800ff8fb  test    rcx, rcx
0x1800ff8fe  jz      short loc_1800FF905
0x1800ff900  call    sub_180067AEC
0x1800ff905  mov     rcx, [rbp+var_28]
0x1800ff909  test    rcx, rcx
0x1800ff90c  jz      short loc_1800FF914
0x1800ff90e  call    cs:__imp_MpFreeMemory
0x1800ff914  mov     rcx, [rbp+var_30]
0x1800ff918  test    rcx, rcx
0x1800ff91b  jz      short loc_1800FF923
0x1800ff91d  call    cs:MpConfigClose
0x1800ff923  xor     eax, eax
0x1800ff925  jmp     loc_1800FF9CB
0x1800ff92a  mov     rbx, [rbp+lpMem]
0x1800ff92e  lea     rdx, pszFile
0x1800ff935  mov     rcx, rbx
0x1800ff938  mov     [rsp+60h+var_40], 0
0x1800ff941  mov     r9, rdi
0x1800ff944  call    sub_1800BCF74
0x1800ff949  mov     edi, eax
0x1800ff94b  test    rbx, rbx
0x1800ff94e  jz      short loc_1800FF958
0x1800ff950  mov     rcx, rbx; lpMem
0x1800ff953  call    sub_180067AEC
0x1800ff958  mov     rcx, [rbp+var_28]
0x1800ff95c  test    rcx, rcx
0x1800ff95f  jz      short loc_1800FF967
0x1800ff961  call    cs:__imp_MpFreeMemory
0x1800ff967  mov     rcx, [rbp+var_30]
0x1800ff96b  test    rcx, rcx
0x1800ff96e  jz      short loc_1800FF976
0x1800ff970  call    cs:MpConfigClose
0x1800ff976  mov     eax, edi
0x1800ff978  jmp     short loc_1800FF9CB
0x1800ff97a  mov     rcx, cs:NameType
0x1800ff981  lea     rdx, NameType
0x1800ff988  cmp     rcx, rdx
0x1800ff98b  jz      short loc_1800FF9AB
0x1800ff98d  test    byte ptr [rcx+1Ch], 1
0x1800ff991  jz      short loc_1800FF9AB
0x1800ff993  mov     edx, 3Dh ; '='
0x1800ff998  mov     rcx, [rcx+10h]
0x1800ff99c  lea     r8, stru_1804C4148
0x1800ff9a3  mov     r9d, ebx
0x1800ff9a6  call    sub_1800A9750
0x1800ff9ab  mov     rcx, [rbp+var_28]
0x1800ff9af  test    rcx, rcx
0x1800ff9b2  jz      short loc_1800FF9BA
0x1800ff9b4  call    cs:__imp_MpFreeMemory
0x1800ff9ba  mov     rcx, [rbp+var_30]
0x1800ff9be  test    rcx, rcx
0x1800ff9c1  jz      short loc_1800FF9C9
0x1800ff9c3  call    cs:MpConfigClose
0x1800ff9c9  mov     eax, ebx
0x1800ff9cb  mov     rcx, [rbp+var_8]
0x1800ff9cf  xor     rcx, rsp; StackCookie
0x1800ff9d2  call    __security_check_cookie
0x1800ff9d7  lea     r11, [rsp+60h+var_s0]
0x1800ff9dc  mov     rbx, [r11+18h]
0x1800ff9e0  mov     rdi, [r11+20h]
0x1800ff9e4  mov     rsp, r11
0x1800ff9e7  pop     rbp
0x1800ff9e8  retn
```
