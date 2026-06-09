# RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(void *,CPathString *)

- ea: `0x180056e70`
- end: `0x180057109`
- name: `?GetUserProfileDirectoryW@CProfileHelper@Uvhd@RdVhd@@UEBAJPEAXPEAVCPathString@@@Z`
- size: `665`
- prototype: `int(RdVhd::Uvhd::CProfileHelper *__hidden this, void *, struct CPathString *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x180032808`
- `0x1800488e4`
- `0x180048b28`
- `0x180056e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ffb`
- `USERENV!GetUserProfileDirectoryW` at `0x180056f69`
- `USERENV!GetUserProfileDirectoryW` at `0x180056fed`
- `USERENV!GetUserProfileDirectoryW` at `0x180056f69`
- `USERENV!GetUserProfileDirectoryW` at `0x180056fed`

## string_xrefs

- `0x180056eb4`: `hToken`
- `0x180056efc`: `pstrUserProfileDirectory`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(
        RdVhd::Uvhd::CProfileHelper *this,
        void *a2,
        struct CPathString *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  signed int v8; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  __int64 v14; // rcx
  WCHAR *v15; // rax
  signed int v16; // eax
  DWORD cchSize; // [rsp+38h] [rbp+10h] BYREF

  cchSize = 0;
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    v6 = 29;
    v7 = L"hToken";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v7);
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    v6 = 30;
    v7 = L"pstrUserProfileDirectory";
    goto LABEL_6;
  }
  v8 = CBaseStringT<unsigned short>::EnsureSpace(a3, 260);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 31;
LABEL_51:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, (unsigned int)v8);
      return (unsigned int)v8;
    }
    return (unsigned int)v8;
  }
  cchSize = CBaseStringT<unsigned short>::GetBufferLength(a3);
  Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(v11);
  if ( GetUserProfileDirectoryW(a2, Buffer, &cchSize) )
  {
LABEL_46:
    v8 = CBaseStringT<unsigned short>::SetLength(a3);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 35;
        goto LABEL_51;
      }
    }
    return (unsigned int)v8;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 234 )
  {
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v8 = v8 & 0x8000FFFF | 0x502A0000;
    }
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 34;
        goto LABEL_51;
      }
      return (unsigned int)v8;
    }
    goto LABEL_46;
  }
  v8 = CBaseStringT<unsigned short>::EnsureSpace(a3, cchSize);
  if ( v8 >= 0 )
  {
    cchSize = CBaseStringT<unsigned short>::GetBufferLength(a3);
    v15 = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(v14);
    if ( !GetUserProfileDirectoryW(a2, v15, &cchSize) )
    {
      v16 = GetLastError();
      v8 = v16;
      if ( v16 && (v16 & 0xFFFF0000) == 0 )
      {
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
        v8 = v8 & 0x8000FFFF | 0x50290000;
      }
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 33;
          goto LABEL_51;
        }
        return (unsigned int)v8;
      }
    }
    goto LABEL_46;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 32;
    goto LABEL_51;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180056e70  mov     [rsp+arg_0], rbx
0x180056e75  mov     [rsp+arg_10], rsi
0x180056e7a  push    rdi
0x180056e7b  sub     rsp, 20h
0x180056e7f  mov     rdi, r8
0x180056e82  mov     [rsp+28h+cchSize], 0
0x180056e8a  mov     rsi, rdx
0x180056e8d  test    rdx, rdx
0x180056e90  jnz     short loc_180056ED5
0x180056e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e99  lea     rax, WPP_GLOBAL_Control
0x180056ea0  cmp     rcx, rax
0x180056ea3  jz      short loc_180056ECB
0x180056ea5  test    byte ptr [rcx+1Ch], 4
0x180056ea9  jz      short loc_180056ECB
0x180056eab  cmp     byte ptr [rcx+19h], 2
0x180056eaf  jb      short loc_180056ECB
0x180056eb1  lea     edx, [rsi+1Dh]
0x180056eb4  lea     r9, aHtoken; "hToken"
0x180056ebb  mov     rcx, [rcx+10h]
0x180056ebf  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180056ec6  call    WPP_SF_S
0x180056ecb  mov     ebx, 80070057h
0x180056ed0  jmp     loc_1800570F7
0x180056ed5  test    rdi, rdi
0x180056ed8  jnz     short loc_180056F05
0x180056eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ee1  lea     rax, WPP_GLOBAL_Control
0x180056ee8  cmp     rcx, rax
0x180056eeb  jz      short loc_180056ECB
0x180056eed  test    byte ptr [rcx+1Ch], 4
0x180056ef1  jz      short loc_180056ECB
0x180056ef3  cmp     byte ptr [rcx+19h], 2
0x180056ef7  jb      short loc_180056ECB
0x180056ef9  lea     edx, [rdi+1Eh]
0x180056efc  lea     r9, aPstruserprofil_1; "pstrUserProfileDirectory"
0x180056f03  jmp     short loc_180056EBB
0x180056f05  mov     edx, 104h
0x180056f0a  mov     rcx, rdi
0x180056f0d  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180056f12  mov     ebx, eax
0x180056f14  test    eax, eax
0x180056f16  jns     short loc_180056F4D
0x180056f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f1f  lea     rax, WPP_GLOBAL_Control
0x180056f26  cmp     rcx, rax
0x180056f29  jz      loc_1800570F7
0x180056f2f  test    byte ptr [rcx+1Ch], 4
0x180056f33  jz      loc_1800570F7
0x180056f39  cmp     byte ptr [rcx+19h], 2
0x180056f3d  jb      loc_1800570F7
0x180056f43  mov     edx, 1Fh
0x180056f48  jmp     loc_1800570E4
0x180056f4d  mov     rcx, rdi
0x180056f50  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180056f55  mov     [rsp+28h+cchSize], eax
0x180056f59  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180056f5e  mov     rdx, rax; lpProfileDir
0x180056f61  lea     r8, [rsp+28h+cchSize]; lpcchSize
0x180056f66  mov     rcx, rsi; hToken
0x180056f69  call    cs:__imp_GetUserProfileDirectoryW
0x180056f6f  test    eax, eax
0x180056f71  jnz     loc_1800570B2
0x180056f77  call    cs:__imp_GetLastError
0x180056f7d  mov     ebx, eax
0x180056f7f  cmp     eax, 0EAh
0x180056f84  jnz     loc_180057064
0x180056f8a  mov     edx, [rsp+28h+cchSize]
0x180056f8e  mov     rcx, rdi
0x180056f91  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180056f96  mov     ebx, eax
0x180056f98  test    eax, eax
0x180056f9a  jns     short loc_180056FD1
0x180056f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fa3  lea     rax, WPP_GLOBAL_Control
0x180056faa  cmp     rcx, rax
0x180056fad  jz      loc_1800570F7
0x180056fb3  test    byte ptr [rcx+1Ch], 4
0x180056fb7  jz      loc_1800570F7
0x180056fbd  cmp     byte ptr [rcx+19h], 2
0x180056fc1  jb      loc_1800570F7
0x180056fc7  mov     edx, 20h ; ' '
0x180056fcc  jmp     loc_1800570E4
0x180056fd1  mov     rcx, rdi
0x180056fd4  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180056fd9  mov     [rsp+28h+cchSize], eax
0x180056fdd  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180056fe2  mov     rdx, rax; lpProfileDir
0x180056fe5  lea     r8, [rsp+28h+cchSize]; lpcchSize
0x180056fea  mov     rcx, rsi; hToken
0x180056fed  call    cs:__imp_GetUserProfileDirectoryW
0x180056ff3  test    eax, eax
0x180056ff5  jnz     loc_1800570B2
0x180056ffb  call    cs:__imp_GetLastError
0x180057001  mov     ebx, eax
0x180057003  test    eax, eax
0x180057005  jz      short loc_180057027
0x180057007  test    eax, 0FFFF0000h
0x18005700c  jnz     short loc_180057027
0x18005700e  test    eax, eax
0x180057010  jle     short loc_18005701B
0x180057012  movzx   ebx, ax
0x180057015  or      ebx, 80070000h
0x18005701b  and     ebx, 0D029FFFFh
0x180057021  or      ebx, 50290000h
0x180057027  test    ebx, ebx
0x180057029  jns     loc_1800570B2
0x18005702f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057036  lea     rax, WPP_GLOBAL_Control
0x18005703d  cmp     rcx, rax
0x180057040  jz      loc_1800570F7
0x180057046  test    byte ptr [rcx+1Ch], 4
0x18005704a  jz      loc_1800570F7
0x180057050  cmp     byte ptr [rcx+19h], 2
0x180057054  jb      loc_1800570F7
0x18005705a  mov     edx, 21h ; '!'
0x18005705f  jmp     loc_1800570E4
0x180057064  test    eax, eax
0x180057066  jz      short loc_180057088
0x180057068  test    eax, 0FFFF0000h
0x18005706d  jnz     short loc_180057088
0x18005706f  test    eax, eax
0x180057071  jle     short loc_18005707C
0x180057073  movzx   ebx, ax
0x180057076  or      ebx, 80070000h
0x18005707c  and     ebx, 0D02AFFFFh
0x180057082  or      ebx, 502A0000h
0x180057088  test    ebx, ebx
0x18005708a  jns     short loc_1800570B2
0x18005708c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057093  lea     rax, WPP_GLOBAL_Control
0x18005709a  cmp     rcx, rax
0x18005709d  jz      short loc_1800570F7
0x18005709f  test    byte ptr [rcx+1Ch], 4
0x1800570a3  jz      short loc_1800570F7
0x1800570a5  cmp     byte ptr [rcx+19h], 2
0x1800570a9  jb      short loc_1800570F7
0x1800570ab  mov     edx, 22h ; '"'
0x1800570b0  jmp     short loc_1800570E4
0x1800570b2  mov     rcx, rdi
0x1800570b5  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x1800570ba  mov     ebx, eax
0x1800570bc  test    eax, eax
0x1800570be  jns     short loc_1800570F7
0x1800570c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570c7  lea     rax, WPP_GLOBAL_Control
0x1800570ce  cmp     rcx, rax
0x1800570d1  jz      short loc_1800570F7
0x1800570d3  test    byte ptr [rcx+1Ch], 4
0x1800570d7  jz      short loc_1800570F7
0x1800570d9  cmp     byte ptr [rcx+19h], 2
0x1800570dd  jb      short loc_1800570F7
0x1800570df  mov     edx, 23h ; '#'
0x1800570e4  mov     rcx, [rcx+10h]
0x1800570e8  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800570ef  mov     r9d, ebx
0x1800570f2  call    WPP_SF_d
0x1800570f7  mov     rsi, [rsp+28h+arg_10]
0x1800570fc  mov     eax, ebx
0x1800570fe  mov     rbx, [rsp+28h+arg_0]
0x180057103  add     rsp, 20h
0x180057107  pop     rdi
0x180057108  retn
```
