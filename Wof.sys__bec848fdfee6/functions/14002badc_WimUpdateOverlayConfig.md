# WimUpdateOverlayConfig

- ea: `0x14002badc`
- end: `0x14002be34`
- name: `WimUpdateOverlayConfig`
- size: `856`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, _QWORD *, const void **, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x140027870`

## callees

- `0x14000fce4`
- `0x14001024c`
- `0x1400102bc`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b454`
- `0x14002b48c`
- `0x14002b78c`
- `0x14002badc`
- `0x14002be3c`
- `0x14003c5c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bdcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002bc73`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002bc73`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bdf8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bdf8`
- `FLTMGR!FltClose` at `0x14002be0d`
- `FLTMGR!FltClose` at `0x14002be0d`

## pseudocode

```c
__int64 __fastcall WimUpdateOverlayConfig(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        _QWORD *a3,
        const void **a4,
        _QWORD *a5)
{
  int v5; // r15d
  int v6; // edi
  __int64 v8; // r13
  int v9; // eax
  unsigned int v10; // ebx
  _DWORD *v11; // rdi
  int v12; // eax
  _DWORD *v13; // rsi
  PDEVICE_OBJECT v14; // rcx
  int v15; // edx
  __int64 OverlayInfo; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // r12d
  SIZE_T v21; // rbx
  _DWORD *PoolWithTag; // rax
  unsigned int v23; // ebx
  bool v24; // zf
  unsigned int v25; // r13d
  __int64 v26; // rcx
  _DWORD *v27; // rdx
  unsigned int v28; // r15d
  ULONG v30; // [rsp+30h] [rbp-30h] BYREF
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  PVOID Object; // [rsp+40h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF
  struct _UNICODE_STRING *v35; // [rsp+58h] [rbp-8h]
  unsigned int v37; // [rsp+A8h] [rbp+48h] BYREF

  v5 = (_DWORD)a1 + 64;
  v6 = (int)a4;
  v30 = 0;
  v37 = 0;
  v8 = (__int64)a1;
  P = 0;
  Object = 0;
  FileHandle = 0;
  Src = 0;
  v35 = a1 + 4;
  v9 = WimPathToBootEnvironmentDevice(a1 + 4, a2 + 4, a4, &P, &v37);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
        v6,
        v9);
    goto LABEL_42;
  }
  v11 = 0;
  v12 = WimReadOverlayConfig(v8, 1, &FileHandle, (PFILE_OBJECT *)&Object, &Src, &v30);
  v13 = Src;
  v10 = v12;
  if ( v12 >= 0 )
  {
    OverlayInfo = WimFindOverlayInfo(Src, a3);
    if ( !OverlayInfo )
    {
      v10 = -1073741275;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_id(WPP_GLOBAL_Control->AttachedDevice, v17, v18, *a3);
      goto LABEL_38;
    }
    v19 = *(_QWORD *)(OverlayInfo + 24) - *a5;
    if ( !v19 )
      v19 = *(_QWORD *)(OverlayInfo + 32) - a5[1];
    if ( v19 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_i_guid__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          OverlayInfo + 24,
          (_DWORD)a5,
          *a3,
          OverlayInfo + 24,
          (__int64)a5);
      v10 = -1073741811;
      goto LABEL_38;
    }
    v20 = v37;
    v21 = v37 + v30;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v21, 0x66637077u);
    v11 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v10 = -1073741801;
      goto LABEL_38;
    }
    memset(PoolWithTag, 0, v21);
    v23 = v13[2] * v13[3] + 24;
    memmove(v11, v13, v23);
    v24 = v11[3] == 0;
    v37 = 0;
    if ( !v24 )
    {
      v25 = v37;
      do
      {
        v26 = v11[2] * v25;
        if ( *(_QWORD *)((char *)v11 + v26 + 24) == *a3 )
        {
          v27 = P;
          v28 = v20;
        }
        else
        {
          v27 = (_DWORD *)((char *)v13 + *(unsigned int *)((char *)v11 + v26 + 32));
          v28 = v27[2];
        }
        *(_DWORD *)((char *)v11 + v26 + 32) = v23;
        *(_DWORD *)((char *)v11 + v26 + 36) = v28;
        memmove((char *)v11 + v23, v27, v28);
        v23 += v28;
        ++v25;
      }
      while ( v25 < v11[3] );
      v8 = (__int64)a1;
      v5 = (int)v35;
    }
    if ( v23 > 0x200000 )
    {
      v10 = -1073740761;
      goto LABEL_38;
    }
    v12 = WimWriteOverlayConfig(v8, FileHandle, Object, v11, v23);
    v10 = v12;
    FileHandle = 0;
    Object = 0;
    if ( v12 >= 0 )
    {
      WimPublishConfigChangeNotification();
      goto LABEL_38;
    }
    v14 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_38;
    v15 = 54;
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_38;
    v15 = 51;
  }
  WPP_SF_Zd(v14->AttachedDevice, v15, (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v5, v12);
LABEL_38:
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
LABEL_42:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return v10;
}

```

## disassembly

```asm
0x14002badc  mov     [rsp-38h+arg_10], rbx
0x14002bae1  mov     [rsp-38h+arg_0], rcx
0x14002bae6  push    rbp
0x14002bae7  push    rsi
0x14002bae8  push    rdi
0x14002bae9  push    r12
0x14002baeb  push    r13
0x14002baed  push    r14
0x14002baef  push    r15
0x14002baf1  mov     rbp, rsp
0x14002baf4  sub     rsp, 60h
0x14002baf8  xor     r12d, r12d
0x14002bafb  lea     r15, [rcx+40h]
0x14002baff  mov     rdi, r9
0x14002bb02  mov     [rbp+var_30], r12d
0x14002bb06  mov     r14, r8
0x14002bb09  mov     [rbp+arg_8], r12d
0x14002bb0d  mov     r13, rcx
0x14002bb10  mov     [rbp+P], r12
0x14002bb14  lea     rax, [rbp+arg_8]
0x14002bb18  mov     [rbp+Object], r12
0x14002bb1c  mov     r8, rdi
0x14002bb1f  mov     [rbp+FileHandle], r12
0x14002bb23  mov     rcx, r15
0x14002bb26  mov     [rbp+Src], r12
0x14002bb2a  add     rdx, 40h ; '@'
0x14002bb2e  mov     [rbp+var_8], r15
0x14002bb32  lea     r9, [rbp+P]
0x14002bb36  mov     [rsp+60h+var_40], rax
0x14002bb3b  call    WimPathToBootEnvironmentDevice
0x14002bb40  mov     ebx, eax
0x14002bb42  test    eax, eax
0x14002bb44  jns     short loc_14002BB85
0x14002bb46  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bb4d  test    dword ptr [rcx+2Ch], 400h
0x14002bb54  jz      loc_14002BDD7
0x14002bb5a  cmp     byte ptr [rcx+29h], 2
0x14002bb5e  jb      loc_14002BDD7
0x14002bb64  mov     rcx, [rcx+18h]
0x14002bb68  lea     edx, [r12+32h]
0x14002bb6d  mov     r9, rdi
0x14002bb70  mov     dword ptr [rsp+60h+var_40], eax
0x14002bb74  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002bb7b  call    WPP_SF_Zd
0x14002bb80  jmp     loc_14002BDD7
0x14002bb85  lea     rax, [rbp+var_30]
0x14002bb89  mov     dl, 1
0x14002bb8b  mov     [rsp+60h+var_38], rax
0x14002bb90  lea     r9, [rbp+Object]
0x14002bb94  lea     rax, [rbp+Src]
0x14002bb98  mov     rcx, r13
0x14002bb9b  lea     r8, [rbp+FileHandle]
0x14002bb9f  mov     [rsp+60h+var_40], rax
0x14002bba4  mov     rdi, r12
0x14002bba7  call    WimReadOverlayConfig
0x14002bbac  mov     rsi, [rbp+Src]
0x14002bbb0  mov     ebx, eax
0x14002bbb2  test    eax, eax
0x14002bbb4  jns     short loc_14002BBF5
0x14002bbb6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbbd  test    dword ptr [rcx+2Ch], 400h
0x14002bbc4  jz      loc_14002BDAB
0x14002bbca  cmp     byte ptr [rcx+29h], 2
0x14002bbce  jb      loc_14002BDAB
0x14002bbd4  mov     edx, 33h ; '3'
0x14002bbd9  mov     rcx, [rcx+18h]
0x14002bbdd  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002bbe4  mov     r9, r15
0x14002bbe7  mov     dword ptr [rsp+60h+var_40], eax
0x14002bbeb  call    WPP_SF_Zd
0x14002bbf0  jmp     loc_14002BDAB
0x14002bbf5  mov     rdx, r14
0x14002bbf8  mov     rcx, rsi
0x14002bbfb  call    WimFindOverlayInfo
0x14002bc00  test    rax, rax
0x14002bc03  jnz     short loc_14002BC39
0x14002bc05  mov     ebx, 0C0000225h
0x14002bc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc11  test    dword ptr [rcx+2Ch], 400h
0x14002bc18  jz      loc_14002BDAB
0x14002bc1e  cmp     byte ptr [rcx+29h], 2
0x14002bc22  jb      loc_14002BDAB
0x14002bc28  mov     r9, [r14]
0x14002bc2b  mov     rcx, [rcx+18h]
0x14002bc2f  call    WPP_SF_id
0x14002bc34  jmp     loc_14002BDAB
0x14002bc39  mov     r8, [rbp+arg_20]
0x14002bc3d  lea     rdx, [rax+18h]
0x14002bc41  mov     rcx, [rdx]
0x14002bc44  sub     rcx, [r8]
0x14002bc47  jnz     short loc_14002BC51
0x14002bc49  mov     rcx, [rdx+8]
0x14002bc4d  sub     rcx, [r8+8]
0x14002bc51  test    rcx, rcx
0x14002bc54  jnz     loc_14002BD7A
0x14002bc5a  mov     ecx, [rbp+var_30]
0x14002bc5d  mov     r8d, 66637077h; Tag
0x14002bc63  mov     r12d, [rbp+arg_8]
0x14002bc67  add     ecx, r12d
0x14002bc6a  mov     ebx, ecx
0x14002bc6c  mov     edx, ecx; NumberOfBytes
0x14002bc6e  mov     ecx, 1; PoolType
0x14002bc73  call    cs:__imp_ExAllocatePoolWithTag
0x14002bc7a  nop     dword ptr [rax+rax+00h]
0x14002bc7f  mov     rdi, rax
0x14002bc82  test    rax, rax
0x14002bc85  jnz     short loc_14002BC94
0x14002bc87  mov     ebx, 0C0000017h
0x14002bc8c  xor     r12d, r12d
0x14002bc8f  jmp     loc_14002BDAB
0x14002bc94  mov     r8, rbx; Size
0x14002bc97  xor     edx, edx; Val
0x14002bc99  mov     rcx, rdi; void *
0x14002bc9c  call    memset
0x14002bca1  mov     ebx, [rsi+0Ch]
0x14002bca4  mov     rdx, rsi; Src
0x14002bca7  imul    ebx, [rsi+8]
0x14002bcab  mov     rcx, rdi; void *
0x14002bcae  add     ebx, 18h
0x14002bcb1  mov     r8d, ebx; Size
0x14002bcb4  call    memmove
0x14002bcb9  cmp     dword ptr [rdi+0Ch], 0
0x14002bcbd  mov     [rbp+arg_8], 0
0x14002bcc4  jbe     short loc_14002BD19
0x14002bcc6  mov     r13d, [rbp+arg_8]
0x14002bcca  mov     rax, [r14]
0x14002bccd  mov     ecx, r13d
0x14002bcd0  imul    ecx, [rdi+8]
0x14002bcd4  cmp     [rcx+rdi+18h], rax
0x14002bcd9  jz      short loc_14002BCE8
0x14002bcdb  mov     edx, [rcx+rdi+20h]
0x14002bcdf  add     rdx, rsi
0x14002bce2  mov     r15d, [rdx+8]
0x14002bce6  jmp     short loc_14002BCEF
0x14002bce8  mov     rdx, [rbp+P]; Src
0x14002bcec  mov     r15d, r12d
0x14002bcef  mov     [rcx+rdi+20h], ebx
0x14002bcf3  mov     [rcx+rdi+24h], r15d
0x14002bcf8  mov     ecx, ebx
0x14002bcfa  add     rcx, rdi; void *
0x14002bcfd  mov     r8d, r15d; Size
0x14002bd00  call    memmove
0x14002bd05  add     ebx, r15d
0x14002bd08  inc     r13d
0x14002bd0b  cmp     r13d, [rdi+0Ch]
0x14002bd0f  jb      short loc_14002BCCA
0x14002bd11  mov     r13, [rbp+arg_0]
0x14002bd15  mov     r15, [rbp+var_8]
0x14002bd19  cmp     ebx, 200000h
0x14002bd1f  jbe     short loc_14002BD2B
0x14002bd21  mov     ebx, 0C0000427h
0x14002bd26  jmp     loc_14002BC8C
0x14002bd2b  mov     r8, [rbp+Object]
0x14002bd2f  mov     r9, rdi
0x14002bd32  mov     rdx, [rbp+FileHandle]
0x14002bd36  mov     rcx, r13
0x14002bd39  mov     dword ptr [rsp+60h+var_40], ebx
0x14002bd3d  call    WimWriteOverlayConfig
0x14002bd42  xor     r12d, r12d
0x14002bd45  mov     ebx, eax
0x14002bd47  mov     [rbp+FileHandle], r12
0x14002bd4b  mov     [rbp+Object], r12
0x14002bd4f  test    eax, eax
0x14002bd51  jns     short loc_14002BD73
0x14002bd53  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd5a  test    dword ptr [rcx+2Ch], 400h
0x14002bd61  jz      short loc_14002BDAB
0x14002bd63  cmp     byte ptr [rcx+29h], 2
0x14002bd67  jb      short loc_14002BDAB
0x14002bd69  lea     edx, [r12+36h]
0x14002bd6e  jmp     loc_14002BBD9
0x14002bd73  call    WimPublishConfigChangeNotification
0x14002bd78  jmp     short loc_14002BDAB
0x14002bd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd81  test    dword ptr [rcx+2Ch], 400h
0x14002bd88  jz      short loc_14002BDA6
0x14002bd8a  cmp     byte ptr [rcx+29h], 2
0x14002bd8e  jb      short loc_14002BDA6
0x14002bd90  mov     r9, [r14]
0x14002bd93  mov     rcx, [rcx+18h]
0x14002bd97  mov     [rsp+60h+var_38], r8
0x14002bd9c  mov     [rsp+60h+var_40], rdx
0x14002bda1  call    WPP_SF_i_guid__guid_
0x14002bda6  mov     ebx, 0C000000Dh
0x14002bdab  test    rsi, rsi
0x14002bdae  jz      short loc_14002BDC1
0x14002bdb0  xor     edx, edx; Tag
0x14002bdb2  mov     rcx, rsi; P
0x14002bdb5  call    cs:__imp_ExFreePoolWithTag
0x14002bdbc  nop     dword ptr [rax+rax+00h]
0x14002bdc1  test    rdi, rdi
0x14002bdc4  jz      short loc_14002BDD7
0x14002bdc6  xor     edx, edx; Tag
0x14002bdc8  mov     rcx, rdi; P
0x14002bdcb  call    cs:__imp_ExFreePoolWithTag
0x14002bdd2  nop     dword ptr [rax+rax+00h]
0x14002bdd7  cmp     [rbp+P], r12
0x14002bddb  jz      short loc_14002BDEF
0x14002bddd  mov     rcx, [rbp+P]; P
0x14002bde1  xor     edx, edx; Tag
0x14002bde3  call    cs:__imp_ExFreePoolWithTag
0x14002bdea  nop     dword ptr [rax+rax+00h]
0x14002bdef  mov     rcx, [rbp+Object]; Object
0x14002bdf3  test    rcx, rcx
0x14002bdf6  jz      short loc_14002BE04
0x14002bdf8  call    cs:__imp_ObfDereferenceObject
0x14002bdff  nop     dword ptr [rax+rax+00h]
0x14002be04  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002be08  test    rcx, rcx
0x14002be0b  jz      short loc_14002BE19
0x14002be0d  call    cs:__imp_FltClose
0x14002be14  nop     dword ptr [rax+rax+00h]
0x14002be19  mov     eax, ebx
0x14002be1b  mov     rbx, [rsp+60h+arg_10]
0x14002be23  add     rsp, 60h
0x14002be27  pop     r15
0x14002be29  pop     r14
0x14002be2b  pop     r13
0x14002be2d  pop     r12
0x14002be2f  pop     rdi
0x14002be30  pop     rsi
0x14002be31  pop     rbp
0x14002be32  retn
```
