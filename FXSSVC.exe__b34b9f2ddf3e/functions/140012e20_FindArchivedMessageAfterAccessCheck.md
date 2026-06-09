# FindArchivedMessageAfterAccessCheck

- ea: `0x140012e20`
- end: `0x1400130f9`
- name: `FindArchivedMessageAfterAccessCheck`
- size: `729`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64, unsigned int, int, wchar_t *Str)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010bc8`
- `0x140010f50`
- `0x14001a6a0`
- `0x14001cb80`
- `0x140020f80`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140006b0c`
- `0x14000bf38`
- `0x14000fca0`
- `0x140012e20`
- `0x1400229f4`
- `0x140045798`
- `0x14004eb7c`
- `0x140065dbc`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x14001308d`
- `ADVAPI32!EqualSid` at `0x14001308d`
- `KERNEL32!GetLastError` at `0x140012f13`
- `KERNEL32!GetLastError` at `0x140012f13`
- `KERNEL32!LocalFree` at `0x1400130e0`
- `KERNEL32!LocalFree` at `0x1400130e0`
- `msvcrt!wcsrchr` at `0x140012fd5`
- `msvcrt!wcsrchr` at `0x140012fd5`

## pseudocode

```c
__int64 __fastcall FindArchivedMessageAfterAccessCheck(
        unsigned int a1,
        unsigned __int64 a2,
        unsigned int a3,
        int a4,
        wchar_t *Str)
{
  PSID v5; // rdi
  BOOL v8; // r13d
  int v10; // ebp
  CMapDeviceId *v11; // rcx
  void *ClientUserSID; // rax
  CFaxArchiving *v14; // rcx
  void *v15; // rsi
  DWORD LastError; // ebx
  void *v17; // r9
  wchar_t *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // r8
  wchar_t *v21; // rax
  CFaxArchiving *v22; // rcx
  const unsigned __int16 *v23; // rdx
  CMapDeviceId *v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // [rsp+28h] [rbp-50h]
  PSID pSid2; // [rsp+88h] [rbp+10h] BYREF

  v5 = 0;
  pSid2 = 0;
  v8 = a1 == 1;
  v10 = a4 != 0 ? 128 : 256;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 457, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_i(*((_QWORD *)v11 + 2), 458, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, 0);
    return 87;
  }
  if ( a1 > 1 )
  {
    if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v11 + 2), 459, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a1);
    return 87;
  }
  ClientUserSID = GetClientUserSID();
  v15 = ClientUserSID;
  if ( !ClientUserSID )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 460, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    goto LABEL_53;
  }
  v17 = 0;
  if ( a1 == 1 && (v10 & a3) == 0 )
    v17 = ClientUserSID;
  v18 = Str;
  LastError = CFaxArchiving::SearchMessage(v14, a2, v8, v17, Str, v26);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_il(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, a2, LastError);
    }
    if ( LastError != 2 )
      goto LABEL_53;
    goto LABEL_52;
  }
  v21 = wcsrchr(v18, 0x5Cu);
  v23 = v21 + 1;
  if ( !v21 )
    v23 = 0;
  LastError = CFaxArchiving::ExtractComponentsFromArchiveFileName(v22, v23, 0, &pSid2);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 462, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    v5 = pSid2;
    goto LABEL_53;
  }
  v5 = pSid2;
  if ( pSid2 )
  {
    if ( (v10 & a3) != 0 || EqualSid(v15, pSid2) )
      goto LABEL_53;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v25 = 464;
    goto LABEL_51;
  }
  if ( !(unsigned int)CanAccessUnAssignedFaxes(a3, 1) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v25 = 463;
LABEL_51:
    WPP_SF_(*((_QWORD *)v24 + 2), v25, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
LABEL_52:
    LastError = 7009;
  }
LABEL_53:
  pMemFree(v15);
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x140012e20  mov     rax, rsp
0x140012e23  push    rbx
0x140012e24  push    rbp
0x140012e25  push    rsi
0x140012e26  push    rdi
0x140012e27  push    r12
0x140012e29  push    r13
0x140012e2b  push    r14
0x140012e2d  push    r15
0x140012e2f  sub     rsp, 38h
0x140012e33  xor     edi, edi
0x140012e35  xor     r13d, r13d
0x140012e38  cmp     ecx, 1
0x140012e3b  mov     [rax+10h], rdi
0x140012e3f  mov     r15d, r8d
0x140012e42  mov     r14, rdx
0x140012e45  setz    r13b
0x140012e49  mov     ebx, ecx
0x140012e4b  neg     r9d
0x140012e4e  sbb     ebp, ebp
0x140012e50  and     ebp, 0FFFFFF80h
0x140012e53  add     ebp, 100h
0x140012e59  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e60  lea     rax, WPP_GLOBAL_Control
0x140012e67  mov     r12b, 4
0x140012e6a  cmp     rcx, rax
0x140012e6d  jz      short loc_140012E9E
0x140012e6f  test    [rcx+1Ch], r12b
0x140012e73  jz      short loc_140012E9E
0x140012e75  cmp     byte ptr [rcx+19h], 5
0x140012e79  jb      short loc_140012E9E
0x140012e7b  mov     rcx, [rcx+10h]
0x140012e7f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140012e86  mov     edx, 1C9h
0x140012e8b  call    WPP_SF_
0x140012e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e97  lea     rax, WPP_GLOBAL_Control
0x140012e9e  test    r14, r14
0x140012ea1  jnz     short loc_140012ECE
0x140012ea3  cmp     rcx, rax
0x140012ea6  jz      short loc_140012EFC
0x140012ea8  test    [rcx+1Ch], r12b
0x140012eac  jz      short loc_140012EFC
0x140012eae  cmp     byte ptr [rcx+19h], 2
0x140012eb2  jb      short loc_140012EFC
0x140012eb4  mov     rcx, [rcx+10h]
0x140012eb8  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140012ebf  mov     edx, 1CAh
0x140012ec4  xor     r9d, r9d
0x140012ec7  call    WPP_SF_i
0x140012ecc  jmp     short loc_140012EFC
0x140012ece  cmp     ebx, 1
0x140012ed1  jbe     short loc_140012F06
0x140012ed3  cmp     rcx, rax
0x140012ed6  jz      short loc_140012EFC
0x140012ed8  test    [rcx+1Ch], r12b
0x140012edc  jz      short loc_140012EFC
0x140012ede  cmp     byte ptr [rcx+19h], 2
0x140012ee2  jb      short loc_140012EFC
0x140012ee4  mov     rcx, [rcx+10h]
0x140012ee8  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140012eef  mov     edx, 1CBh
0x140012ef4  mov     r9d, ebx
0x140012ef7  call    WPP_SF_d
0x140012efc  mov     eax, 57h ; 'W'
0x140012f01  jmp     loc_1400130E8
0x140012f06  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x140012f0b  mov     rsi, rax
0x140012f0e  test    rax, rax
0x140012f11  jnz     short loc_140012F63
0x140012f13  call    cs:__imp_GetLastError
0x140012f19  mov     ebx, eax
0x140012f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f22  lea     rax, WPP_GLOBAL_Control
0x140012f29  cmp     rcx, rax
0x140012f2c  jz      loc_1400130D0
0x140012f32  test    [rcx+1Ch], r12b
0x140012f36  jz      loc_1400130D0
0x140012f3c  cmp     byte ptr [rcx+19h], 2
0x140012f40  jb      loc_1400130D0
0x140012f46  mov     rcx, [rcx+10h]
0x140012f4a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140012f51  mov     edx, 1CCh
0x140012f56  mov     r9d, ebx
0x140012f59  call    WPP_SF_d
0x140012f5e  jmp     loc_1400130D0
0x140012f63  xor     r9d, r9d
0x140012f66  cmp     ebx, 1
0x140012f69  jnz     short loc_140012F72
0x140012f6b  test    r15d, ebp
0x140012f6e  cmovz   r9, rsi; void *
0x140012f72  mov     r12, [rsp+78h+Str]
0x140012f7a  mov     r8d, r13d; int
0x140012f7d  mov     rdx, r14; unsigned __int64
0x140012f80  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x140012f85  call    ?SearchMessage@CFaxArchiving@@QEAAK_KHPEAXPEAGK@Z; CFaxArchiving::SearchMessage(unsigned __int64,int,void *,ushort *,ulong)
0x140012f8a  mov     ebx, eax
0x140012f8c  test    eax, eax
0x140012f8e  jz      short loc_140012FCD
0x140012f90  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f97  lea     rax, WPP_GLOBAL_Control
0x140012f9e  cmp     rcx, rax
0x140012fa1  jz      short loc_140012FBF
0x140012fa3  test    byte ptr [rcx+1Ch], 4
0x140012fa7  jz      short loc_140012FBF
0x140012fa9  cmp     byte ptr [rcx+19h], 2
0x140012fad  jb      short loc_140012FBF
0x140012faf  mov     rcx, [rcx+10h]
0x140012fb3  mov     r9, r14
0x140012fb6  mov     dword ptr [rsp+78h+var_58], ebx
0x140012fba  call    WPP_SF_il
0x140012fbf  cmp     ebx, 2
0x140012fc2  jnz     loc_1400130D0
0x140012fc8  jmp     loc_1400130CB
0x140012fcd  mov     edx, 5Ch ; '\'; Ch
0x140012fd2  mov     rcx, r12; Str
0x140012fd5  call    cs:__imp_wcsrchr
0x140012fdb  test    rax, rax
0x140012fde  lea     r9, [rsp+78h+pSid2]; void **
0x140012fe6  lea     rdx, [rax+2]
0x140012fea  cmovz   rdx, rax; unsigned __int16 *
0x140012fee  xor     r8d, r8d; unsigned __int64 *
0x140012ff1  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x140012ff6  mov     ebx, eax
0x140012ff8  test    eax, eax
0x140012ffa  jz      short loc_140013040
0x140012ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x140013003  lea     rax, WPP_GLOBAL_Control
0x14001300a  cmp     rcx, rax
0x14001300d  jz      short loc_140013033
0x14001300f  test    byte ptr [rcx+1Ch], 4
0x140013013  jz      short loc_140013033
0x140013015  cmp     byte ptr [rcx+19h], 2
0x140013019  jb      short loc_140013033
0x14001301b  mov     rcx, [rcx+10h]
0x14001301f  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140013026  mov     edx, 1CEh
0x14001302b  mov     r9d, ebx
0x14001302e  call    WPP_SF_d
0x140013033  mov     rdi, [rsp+78h+pSid2]
0x14001303b  jmp     loc_1400130D0
0x140013040  mov     rdi, [rsp+78h+pSid2]
0x140013048  test    rdi, rdi
0x14001304b  jnz     short loc_140013082
0x14001304d  lea     edx, [rdi+1]; int
0x140013050  mov     ecx, r15d; unsigned int
0x140013053  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x140013058  test    eax, eax
0x14001305a  jnz     short loc_1400130D0
0x14001305c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013063  lea     rax, WPP_GLOBAL_Control
0x14001306a  cmp     rcx, rax
0x14001306d  jz      short loc_1400130CB
0x14001306f  test    byte ptr [rcx+1Ch], 4
0x140013073  jz      short loc_1400130CB
0x140013075  cmp     byte ptr [rcx+19h], 2
0x140013079  jb      short loc_1400130CB
0x14001307b  mov     edx, 1CFh
0x140013080  jmp     short loc_1400130BB
0x140013082  test    r15d, ebp
0x140013085  jnz     short loc_1400130D0
0x140013087  mov     rdx, rdi; pSid2
0x14001308a  mov     rcx, rsi; pSid1
0x14001308d  call    cs:__imp_EqualSid
0x140013093  test    eax, eax
0x140013095  jnz     short loc_1400130D0
0x140013097  mov     rcx, cs:WPP_GLOBAL_Control
0x14001309e  lea     rax, WPP_GLOBAL_Control
0x1400130a5  cmp     rcx, rax
0x1400130a8  jz      short loc_1400130CB
0x1400130aa  test    byte ptr [rcx+1Ch], 4
0x1400130ae  jz      short loc_1400130CB
0x1400130b0  cmp     byte ptr [rcx+19h], 2
0x1400130b4  jb      short loc_1400130CB
0x1400130b6  mov     edx, 1D0h
0x1400130bb  mov     rcx, [rcx+10h]
0x1400130bf  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400130c6  call    WPP_SF_
0x1400130cb  mov     ebx, 1B61h
0x1400130d0  mov     rcx, rsi; lpMem
0x1400130d3  call    pMemFree
0x1400130d8  test    rdi, rdi
0x1400130db  jz      short loc_1400130E6
0x1400130dd  mov     rcx, rdi; hMem
0x1400130e0  call    cs:__imp_LocalFree
0x1400130e6  mov     eax, ebx
0x1400130e8  add     rsp, 38h
0x1400130ec  pop     r15
0x1400130ee  pop     r14
0x1400130f0  pop     r13
0x1400130f2  pop     r12
0x1400130f4  pop     rdi
0x1400130f5  pop     rsi
0x1400130f6  pop     rbp
0x1400130f7  pop     rbx
0x1400130f8  retn
```
