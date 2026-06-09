# sub_1800AFBE4

- ea: `0x1800afbe4`
- end: `0x1800afddb`
- name: `sub_1800AFBE4`
- size: `503`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800afa98`
- `0x1800b131c`
- `0x180150d80`
- `0x1801512a8`
- `0x1801c16b0`
- `0x1804194d0`
- `0x18045028c`

## callees

- `0x18003539c`
- `0x180067aa0`
- `0x180067aec`
- `0x1800a9720`
- `0x1800afbe4`
- `0x1800b2574`

## import_xrefs

- `MpClient!MpConfigOpen` at `0x1800afc22`
- `MpClient!MpConfigOpen` at `0x1800afc22`
- `MpClient!MpConfigClose` at `0x1800afc37`
- `MpClient!MpConfigClose` at `0x1800afcf2`
- `MpClient!MpConfigClose` at `0x1800afdb2`
- `MpClient!MpConfigClose` at `0x1800afc37`
- `MpClient!MpConfigClose` at `0x1800afcf2`
- `MpClient!MpConfigClose` at `0x1800afdb2`
- `MpClient!MpConfigGetValueAlloc` at `0x1800afc70`
- `MpClient!MpConfigGetValueAlloc` at `0x1800afc70`
- `MpClient!MpFreeMemory` at `0x1800afc85`
- `MpClient!MpFreeMemory` at `0x1800afce3`
- `MpClient!MpFreeMemory` at `0x1800afd6d`
- `MpClient!MpFreeMemory` at `0x1800afda3`
- `MpClient!MpFreeMemory` at `0x1800afc85`
- `MpClient!MpFreeMemory` at `0x1800afce3`
- `MpClient!MpFreeMemory` at `0x1800afd6d`
- `MpClient!MpFreeMemory` at `0x1800afda3`

## string_xrefs

- `0x1800afc5e`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall sub_1800AFBE4(_QWORD *a1, char a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int ValueAlloc; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  COMPUTER_NAME_FORMAT *v11; // rdx
  __int64 v12; // rax
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF

  *a1 = 0;
  v16 = 0;
  v4 = MpConfigOpen(L".", &v16);
  v6 = v16;
  ValueAlloc = v4;
  if ( v4 < 0 )
  {
LABEL_2:
    if ( v6 )
      MpConfigClose(v6, v5);
    return (unsigned int)ValueAlloc;
  }
  v15 = 0;
  LODWORD(lpMem) = 2;
  LODWORD(v18) = 0;
  ValueAlloc = MpConfigGetValueAlloc(v16, L"InstallLocation", &lpMem, &v18, &v15, 0);
  if ( ValueAlloc < 0 )
  {
LABEL_6:
    if ( v15 )
      MpFreeMemory(v15);
    v6 = v16;
    goto LABEL_2;
  }
  v9 = v15;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v15 + 2 * v10) );
  if ( !v10 )
  {
    v11 = &NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      sub_1800A9720(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 20, &stru_1804BDFA8);
      v9 = v15;
    }
    if ( v9 )
      MpFreeMemory(v9);
    if ( v16 )
      MpConfigClose(v16, v11);
    return 2147942411LL;
  }
  if ( *(_WORD *)(v15 + 2 * v10 - 2) == 92 )
  {
    *(_WORD *)(v15 + 2 * v10 - 2) = 0;
    v9 = v15;
  }
  if ( a2 )
  {
    lpMem = 0;
    ValueAlloc = sub_18003539C(&lpMem, v9);
    if ( ValueAlloc < 0 )
    {
LABEL_24:
      if ( lpMem )
        sub_180067AEC(lpMem);
      goto LABEL_6;
    }
    v18 = 0;
    ValueAlloc = sub_1800B2574(&v18, L"%s", lpMem);
    if ( ValueAlloc < 0 )
    {
      if ( v18 )
        MpFreeMemory(v18);
      goto LABEL_24;
    }
    v12 = v18;
    v13 = lpMem;
    v18 = 0;
    *a1 = v12;
    if ( v13 )
      sub_180067AEC(v13);
    v14 = v15;
  }
  else
  {
    v14 = 0;
    *a1 = v9;
    v15 = 0;
  }
  if ( v14 )
    MpFreeMemory(v14);
  if ( v16 )
    MpConfigClose(v16, v5);
  return 0;
}

```

## disassembly

```asm
0x1800afbe4  mov     [rsp-18h+arg_8], rbx
0x1800afbe9  mov     [rsp-18h+arg_10], rsi
0x1800afbee  push    rbp
0x1800afbef  push    rdi
0x1800afbf0  push    r14
0x1800afbf2  mov     rbp, rsp
0x1800afbf5  sub     rsp, 60h
0x1800afbf9  mov     rax, cs:__security_cookie
0x1800afc00  xor     rax, rsp
0x1800afc03  mov     [rbp+var_10], rax
0x1800afc07  xor     r14d, r14d
0x1800afc0a  mov     sil, dl
0x1800afc0d  mov     [rcx], r14
0x1800afc10  lea     rdx, [rbp+var_28]
0x1800afc14  mov     rdi, rcx
0x1800afc17  mov     [rbp+var_28], r14
0x1800afc1b  lea     rcx, asc_1804AB18C; "."
0x1800afc22  call    cs:MpConfigOpen
0x1800afc28  mov     rcx, [rbp+var_28]
0x1800afc2c  mov     ebx, eax
0x1800afc2e  test    eax, eax
0x1800afc30  jns     short loc_1800AFC44
0x1800afc32  test    rcx, rcx
0x1800afc35  jz      short loc_1800AFC3D
0x1800afc37  call    cs:MpConfigClose
0x1800afc3d  mov     eax, ebx
0x1800afc3f  jmp     loc_1800AFDBA
0x1800afc44  lea     rax, [rbp+var_30]
0x1800afc48  mov     [rsp+60h+var_38], r14
0x1800afc4d  lea     r9, [rbp+var_18]
0x1800afc51  mov     [rsp+60h+var_40], rax
0x1800afc56  lea     r8, [rbp+lpMem]
0x1800afc5a  mov     [rbp+var_30], r14
0x1800afc5e  lea     rdx, aInstalllocatio; "InstallLocation"
0x1800afc65  mov     dword ptr [rbp+lpMem], 2
0x1800afc6c  mov     dword ptr [rbp+var_18], r14d
0x1800afc70  call    cs:MpConfigGetValueAlloc
0x1800afc76  mov     ebx, eax
0x1800afc78  test    eax, eax
0x1800afc7a  jns     short loc_1800AFC91
0x1800afc7c  mov     rcx, [rbp+var_30]
0x1800afc80  test    rcx, rcx
0x1800afc83  jz      short loc_1800AFC8B
0x1800afc85  call    cs:__imp_MpFreeMemory
0x1800afc8b  mov     rcx, [rbp+var_28]
0x1800afc8f  jmp     short loc_1800AFC32
0x1800afc91  mov     rax, [rbp+var_30]
0x1800afc95  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800afc99  inc     rcx
0x1800afc9c  cmp     [rax+rcx*2], r14w
0x1800afca1  jnz     short loc_1800AFC99
0x1800afca3  cmp     rcx, 1
0x1800afca7  jnb     short loc_1800AFD02
0x1800afca9  mov     rcx, cs:NameType
0x1800afcb0  lea     rdx, NameType
0x1800afcb7  cmp     rcx, rdx
0x1800afcba  jz      short loc_1800AFCDB
0x1800afcbc  test    byte ptr [rcx+1Ch], 1
0x1800afcc0  jz      short loc_1800AFCDB
0x1800afcc2  mov     rcx, [rcx+10h]
0x1800afcc6  lea     r8, stru_1804BDFA8
0x1800afccd  mov     edx, 14h
0x1800afcd2  call    sub_1800A9720
0x1800afcd7  mov     rax, [rbp+var_30]
0x1800afcdb  test    rax, rax
0x1800afcde  jz      short loc_1800AFCE9
0x1800afce0  mov     rcx, rax
0x1800afce3  call    cs:__imp_MpFreeMemory
0x1800afce9  mov     rcx, [rbp+var_28]
0x1800afced  test    rcx, rcx
0x1800afcf0  jz      short loc_1800AFCF8
0x1800afcf2  call    cs:MpConfigClose
0x1800afcf8  mov     eax, 8007000Bh
0x1800afcfd  jmp     loc_1800AFDBA
0x1800afd02  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800afd08  jnz     short loc_1800AFD14
0x1800afd0a  mov     [rax+rcx*2-2], r14w
0x1800afd10  mov     rax, [rbp+var_30]
0x1800afd14  test    sil, sil
0x1800afd17  jz      short loc_1800AFD94
0x1800afd19  mov     rdx, rax
0x1800afd1c  mov     [rbp+lpMem], r14
0x1800afd20  lea     rcx, [rbp+lpMem]
0x1800afd24  call    sub_18003539C
0x1800afd29  mov     ebx, eax
0x1800afd2b  test    eax, eax
0x1800afd2d  jns     short loc_1800AFD46
0x1800afd2f  mov     rcx, [rbp+lpMem]; lpMem
0x1800afd33  test    rcx, rcx
0x1800afd36  jz      loc_1800AFC7C
0x1800afd3c  call    sub_180067AEC
0x1800afd41  jmp     loc_1800AFC7C
0x1800afd46  mov     r8, [rbp+lpMem]
0x1800afd4a  lea     rdx, aS_2; "%s"
0x1800afd51  lea     rcx, [rbp+var_18]
0x1800afd55  mov     [rbp+var_18], r14
0x1800afd59  call    sub_1800B2574
0x1800afd5e  mov     ebx, eax
0x1800afd60  test    eax, eax
0x1800afd62  jns     short loc_1800AFD75
0x1800afd64  mov     rcx, [rbp+var_18]
0x1800afd68  test    rcx, rcx
0x1800afd6b  jz      short loc_1800AFD2F
0x1800afd6d  call    cs:__imp_MpFreeMemory
0x1800afd73  jmp     short loc_1800AFD2F
0x1800afd75  mov     rax, [rbp+var_18]
0x1800afd79  mov     rcx, [rbp+lpMem]; lpMem
0x1800afd7d  mov     [rbp+var_18], r14
0x1800afd81  mov     [rdi], rax
0x1800afd84  test    rcx, rcx
0x1800afd87  jz      short loc_1800AFD8E
0x1800afd89  call    sub_180067AEC
0x1800afd8e  mov     rcx, [rbp+var_30]
0x1800afd92  jmp     short loc_1800AFD9E
0x1800afd94  mov     rcx, r14
0x1800afd97  mov     [rdi], rax
0x1800afd9a  mov     [rbp+var_30], rcx
0x1800afd9e  test    rcx, rcx
0x1800afda1  jz      short loc_1800AFDA9
0x1800afda3  call    cs:__imp_MpFreeMemory
0x1800afda9  mov     rcx, [rbp+var_28]
0x1800afdad  test    rcx, rcx
0x1800afdb0  jz      short loc_1800AFDB8
0x1800afdb2  call    cs:MpConfigClose
0x1800afdb8  xor     eax, eax
0x1800afdba  mov     rcx, [rbp+var_10]
0x1800afdbe  xor     rcx, rsp; StackCookie
0x1800afdc1  call    __security_check_cookie
0x1800afdc6  lea     r11, [rsp+60h+var_s0]
0x1800afdcb  mov     rbx, [r11+28h]
0x1800afdcf  mov     rsi, [r11+30h]
0x1800afdd3  mov     rsp, r11
0x1800afdd6  pop     r14
0x1800afdd8  pop     rdi
0x1800afdd9  pop     rbp
0x1800afdda  retn
```
