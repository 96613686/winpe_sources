# DavFsSetFileInformation

- ea: `0x18001ead0`
- end: `0x18001ee27`
- name: `DavFsSetFileInformation`
- size: `855`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000bfe0`
- `0x180010478`
- `0x180010770`
- `0x180010ffc`
- `0x180011360`
- `0x18001ead0`
- `0x18002097c`
- `0x1800297e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001edce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001edce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec0c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ed89`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ed89`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001ebfc`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001ebfc`

## pseudocode

```c
__int64 __fastcall DavFsSetFileInformation(__int64 a1)
{
  __int64 v1; // r15
  __int64 v2; // rbx
  WCHAR *v4; // rbx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // esi
  __int64 v9; // rdi
  bool v10; // zf
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 *v13; // r12
  unsigned int v14; // eax
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  __int64 v20; // [rsp+A0h] [rbp+8h] BYREF
  __int64 *v21; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+18h]

  v1 = a1 + 632;
  v21 = 0;
  v2 = *(_QWORD *)(a1 + 648);
  v20 = 0;
  v4 = (WCHAR *)(v2 + 2);
  if ( !v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 51;
LABEL_5:
    WPP_SF_(v5[2], v6, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids);
LABEL_6:
    v7 = 87;
    goto LABEL_42;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v4);
    v5 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(v1 + 8);
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
  {
    WPP_SF_d(v5[2], 53, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v8);
    v5 = WPP_GLOBAL_Control;
  }
  v9 = *(_QWORD *)(v1 + 24);
  v10 = v9 == -2;
  v11 = v9 + 2;
  v22 = v11;
  if ( v10 )
  {
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 1) == 0 )
      goto LABEL_6;
    v6 = 54;
    goto LABEL_5;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    WPP_SF_S(v5[2], 55, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v11);
  DavRemoveDummyShareFromFileName(v11);
  EnterCriticalSection(&HashServerEntryTableLock);
  if ( !(unsigned int)DavDoesUserEntryExist(v4, v8, (_DWORD *)v1, &v21, (__int64 **)&v20)
    || (v12 = v20) == 0
    || (v13 = v21) == 0 )
  {
    v7 = 1223;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids);
    LeaveCriticalSection(&HashServerEntryTableLock);
    goto LABEL_42;
  }
  *(_QWORD *)(a1 + 496) = v21;
  *(_QWORD *)(a1 + 504) = v12;
  ++*((_DWORD *)v13 + 16);
  LeaveCriticalSection(&HashServerEntryTableLock);
  v14 = UMReflectorImpersonate(a1, *(_QWORD *)(a1 + 72));
  v7 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v14);
  }
  else
  {
    v15 = v22;
    *(_DWORD *)(a1 + 56) = 6;
    v16 = DavSetBasicInformation(
            a1,
            v13[4],
            v13[5],
            v15,
            *(unsigned __int8 *)(v1 + 40),
            *(unsigned __int8 *)(v1 + 41),
            *(unsigned __int8 *)(v1 + 42),
            *(unsigned __int8 *)(v1 + 43),
            (FILETIME *)(v1 + 48),
            (FILETIME *)(v1 + 56),
            (FILETIME *)(v1 + 64),
            *(_DWORD *)(v1 + 80));
    v7 = v16;
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v16);
      v17 = DavFormatAndLogError(a1, v7);
      if ( v17
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v17);
      }
    }
    RevertToSelf();
  }
  DavFinalizePerUserEntry(a1 + 496);
  if ( v7 )
  {
LABEL_42:
    v18 = DavMapErrorToNtStatus(v7);
    goto LABEL_43;
  }
  v18 = 0;
LABEL_43:
  *(_DWORD *)(a1 + 32) = v18;
  DavFsFinalizeTheDavCallBackContext(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001ead0  mov     rax, rsp
0x18001ead3  mov     [rax+20h], rbx
0x18001ead7  push    rbp
0x18001ead8  push    rsi
0x18001ead9  push    rdi
0x18001eada  push    r12
0x18001eadc  push    r13
0x18001eade  push    r14
0x18001eae0  push    r15
0x18001eae2  sub     rsp, 60h
0x18001eae6  lea     r15, [rcx+278h]
0x18001eaed  mov     qword ptr [rax+10h], 0
0x18001eaf5  mov     rbx, [r15+10h]
0x18001eaf9  mov     r13, rcx
0x18001eafc  mov     qword ptr [rax+8], 0
0x18001eb04  mov     r12b, 2
0x18001eb07  add     rbx, 2
0x18001eb0b  jnz     short loc_18001EB46
0x18001eb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb14  lea     rbp, WPP_GLOBAL_Control
0x18001eb1b  lea     r14, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001eb22  cmp     rcx, rbp
0x18001eb25  jz      short loc_18001EB3C
0x18001eb27  test    byte ptr [rcx+1Ch], 1
0x18001eb2b  jz      short loc_18001EB3C
0x18001eb2d  lea     edx, [rbx+33h]
0x18001eb30  mov     rcx, [rcx+10h]
0x18001eb34  mov     r8, r14
0x18001eb37  call    WPP_SF_
0x18001eb3c  mov     ebx, 57h ; 'W'
0x18001eb41  jmp     loc_18001EDD4
0x18001eb46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb4d  lea     rbp, WPP_GLOBAL_Control
0x18001eb54  lea     r14, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001eb5b  cmp     rcx, rbp
0x18001eb5e  jz      short loc_18001EB81
0x18001eb60  test    [rcx+1Ch], r12b
0x18001eb64  jz      short loc_18001EB81
0x18001eb66  mov     rcx, [rcx+10h]
0x18001eb6a  mov     edx, 34h ; '4'
0x18001eb6f  mov     r9, rbx
0x18001eb72  mov     r8, r14
0x18001eb75  call    WPP_SF_S
0x18001eb7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb81  mov     esi, [r15+8]
0x18001eb85  cmp     rcx, rbp
0x18001eb88  jz      short loc_18001EBAB
0x18001eb8a  test    [rcx+1Ch], r12b
0x18001eb8e  jz      short loc_18001EBAB
0x18001eb90  mov     rcx, [rcx+10h]
0x18001eb94  mov     edx, 35h ; '5'
0x18001eb99  mov     r9d, esi
0x18001eb9c  mov     r8, r14
0x18001eb9f  call    WPP_SF_d
0x18001eba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebab  mov     rdi, [r15+18h]
0x18001ebaf  add     rdi, 2
0x18001ebb3  mov     [rsp+98h+arg_10], rdi
0x18001ebbb  jnz     short loc_18001EBDA
0x18001ebbd  cmp     rcx, rbp
0x18001ebc0  jz      loc_18001EB3C
0x18001ebc6  test    byte ptr [rcx+1Ch], 1
0x18001ebca  jz      loc_18001EB3C
0x18001ebd0  mov     edx, 36h ; '6'
0x18001ebd5  jmp     loc_18001EB30
0x18001ebda  cmp     rcx, rbp
0x18001ebdd  jz      short loc_18001EBF9
0x18001ebdf  test    [rcx+1Ch], r12b
0x18001ebe3  jz      short loc_18001EBF9
0x18001ebe5  mov     rcx, [rcx+10h]
0x18001ebe9  mov     edx, 37h ; '7'
0x18001ebee  mov     r9, rdi
0x18001ebf1  mov     r8, r14
0x18001ebf4  call    WPP_SF_S
0x18001ebf9  mov     rcx, rdi
0x18001ebfc  call    cs:__imp_DavRemoveDummyShareFromFileName
0x18001ec02  lea     rdi, HashServerEntryTableLock
0x18001ec09  mov     rcx, rdi; lpCriticalSection
0x18001ec0c  call    cs:__imp_EnterCriticalSection
0x18001ec12  lea     rax, [rsp+98h+arg_0]
0x18001ec1a  mov     r8, r15
0x18001ec1d  lea     r9, [rsp+98h+arg_8]
0x18001ec25  mov     [rsp+98h+var_78], rax; __int64
0x18001ec2a  mov     edx, esi
0x18001ec2c  mov     rcx, rbx; hMem
0x18001ec2f  call    DavDoesUserEntryExist
0x18001ec34  test    eax, eax
0x18001ec36  jz      loc_18001EDA3
0x18001ec3c  mov     rax, [rsp+98h+arg_0]
0x18001ec44  test    rax, rax
0x18001ec47  jz      loc_18001EDA3
0x18001ec4d  mov     r12, [rsp+98h+arg_8]
0x18001ec55  test    r12, r12
0x18001ec58  jz      loc_18001EDA3
0x18001ec5e  mov     [r13+1F0h], r12
0x18001ec65  mov     rcx, rdi; lpCriticalSection
0x18001ec68  mov     [r13+1F8h], rax
0x18001ec6f  inc     dword ptr [r12+40h]
0x18001ec74  call    cs:__imp_LeaveCriticalSection
0x18001ec7a  mov     rdx, [r13+48h]
0x18001ec7e  mov     rcx, r13
0x18001ec81  call    UMReflectorImpersonate
0x18001ec86  mov     ebx, eax
0x18001ec88  test    eax, eax
0x18001ec8a  jz      short loc_18001ECBF
0x18001ec8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec93  cmp     rcx, rbp
0x18001ec96  jz      loc_18001ED8F
0x18001ec9c  test    byte ptr [rcx+1Ch], 1
0x18001eca0  jz      loc_18001ED8F
0x18001eca6  mov     rcx, [rcx+10h]
0x18001ecaa  mov     edx, 39h ; '9'
0x18001ecaf  mov     r9d, eax
0x18001ecb2  mov     r8, r14
0x18001ecb5  call    WPP_SF_d
0x18001ecba  jmp     loc_18001ED8F
0x18001ecbf  mov     r9, [rsp+98h+arg_10]; int
0x18001ecc7  lea     rcx, [r15+40h]
0x18001eccb  mov     dword ptr [r13+38h], 6
0x18001ecd3  lea     r8, [r15+38h]
0x18001ecd7  mov     eax, [r15+50h]
0x18001ecdb  lea     r10, [r15+30h]
0x18001ecdf  movzx   r11d, byte ptr [r15+2Bh]
0x18001ece4  movzx   ebx, byte ptr [r15+2Ah]
0x18001ece9  movzx   edi, byte ptr [r15+29h]
0x18001ecee  movzx   esi, byte ptr [r15+28h]
0x18001ecf3  mov     rdx, [r12+20h]; int
0x18001ecf8  mov     [rsp+98h+var_40], eax; int
0x18001ecfc  mov     [rsp+98h+var_48], rcx; FILETIME *
0x18001ed01  mov     rcx, r13; int
0x18001ed04  mov     [rsp+98h+var_50], r8; FILETIME *
0x18001ed09  mov     r8, [r12+28h]; int
0x18001ed0e  mov     [rsp+98h+var_58], r10; FILETIME *
0x18001ed13  mov     [rsp+98h+var_60], r11d; int
0x18001ed18  mov     [rsp+98h+var_68], ebx; int
0x18001ed1c  mov     [rsp+98h+var_70], edi; int
0x18001ed20  mov     dword ptr [rsp+98h+var_78], esi; int
0x18001ed24  call    DavSetBasicInformation
0x18001ed29  mov     ebx, eax
0x18001ed2b  test    eax, eax
0x18001ed2d  jz      short loc_18001ED89
0x18001ed2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed36  cmp     rcx, rbp
0x18001ed39  jz      short loc_18001ED55
0x18001ed3b  test    byte ptr [rcx+1Ch], 1
0x18001ed3f  jz      short loc_18001ED55
0x18001ed41  mov     rcx, [rcx+10h]
0x18001ed45  mov     edx, 3Ah ; ':'
0x18001ed4a  mov     r9d, eax
0x18001ed4d  mov     r8, r14
0x18001ed50  call    WPP_SF_d
0x18001ed55  mov     edx, ebx
0x18001ed57  mov     rcx, r13
0x18001ed5a  call    DavFormatAndLogError
0x18001ed5f  test    eax, eax
0x18001ed61  jz      short loc_18001ED89
0x18001ed63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed6a  cmp     rcx, rbp
0x18001ed6d  jz      short loc_18001ED89
0x18001ed6f  test    byte ptr [rcx+1Ch], 1
0x18001ed73  jz      short loc_18001ED89
0x18001ed75  mov     rcx, [rcx+10h]
0x18001ed79  mov     edx, 3Bh ; ';'
0x18001ed7e  mov     r9d, eax
0x18001ed81  mov     r8, r14
0x18001ed84  call    WPP_SF_d
0x18001ed89  call    cs:__imp_RevertToSelf
0x18001ed8f  lea     rcx, [r13+1F0h]
0x18001ed96  call    DavFinalizePerUserEntry
0x18001ed9b  test    ebx, ebx
0x18001ed9d  jnz     short loc_18001EDD4
0x18001ed9f  xor     eax, eax
0x18001eda1  jmp     short loc_18001EDDB
0x18001eda3  mov     ebx, 4C7h
0x18001eda8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edaf  cmp     rcx, rbp
0x18001edb2  jz      short loc_18001EDCB
0x18001edb4  test    byte ptr [rcx+1Ch], 1
0x18001edb8  jz      short loc_18001EDCB
0x18001edba  mov     rcx, [rcx+10h]
0x18001edbe  mov     edx, 38h ; '8'
0x18001edc3  mov     r8, r14
0x18001edc6  call    WPP_SF_
0x18001edcb  mov     rcx, rdi; lpCriticalSection
0x18001edce  call    cs:__imp_LeaveCriticalSection
0x18001edd4  mov     ecx, ebx
0x18001edd6  call    DavMapErrorToNtStatus
0x18001eddb  mov     rcx, r13
0x18001edde  mov     [r13+20h], eax
0x18001ede2  call    DavFsFinalizeTheDavCallBackContext
0x18001ede7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edee  cmp     rcx, rbp
0x18001edf1  jz      short loc_18001EE0D
0x18001edf3  test    byte ptr [rcx+1Ch], 2
0x18001edf7  jz      short loc_18001EE0D
0x18001edf9  mov     rcx, [rcx+10h]
0x18001edfd  mov     edx, 3Ch ; '<'
0x18001ee02  mov     r9d, ebx
0x18001ee05  mov     r8, r14
0x18001ee08  call    WPP_SF_d
0x18001ee0d  mov     eax, ebx
0x18001ee0f  mov     rbx, [rsp+98h+arg_18]
0x18001ee17  add     rsp, 60h
0x18001ee1b  pop     r15
0x18001ee1d  pop     r14
0x18001ee1f  pop     r13
0x18001ee21  pop     r12
0x18001ee23  pop     rdi
0x18001ee24  pop     rsi
0x18001ee25  pop     rbp
0x18001ee26  retn
```
