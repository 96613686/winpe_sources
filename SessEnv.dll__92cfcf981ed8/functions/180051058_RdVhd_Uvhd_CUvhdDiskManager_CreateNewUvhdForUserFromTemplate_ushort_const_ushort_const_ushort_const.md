# RdVhd::Uvhd::CUvhdDiskManager::CreateNewUvhdForUserFromTemplate(ushort const *,ushort const *,ushort const *)

- ea: `0x180051058`
- end: `0x18005154d`
- name: `?CreateNewUvhdForUserFromTemplate@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG00@Z`
- size: `1269`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpNewFileName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180052cf0`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18003114c`
- `0x180035db4`
- `0x1800488e4`
- `0x180048944`
- `0x180048b28`
- `0x180050c6c`
- `0x180051058`
- `0x180054158`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180051191`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180051191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005145d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005145d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800514b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800514b9`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180051308`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180051453`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180051308`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180051453`
- `api-ms-win-core-file-l2-1-0!MoveFileWithProgressW` at `0x180051426`
- `api-ms-win-core-file-l2-1-0!MoveFileWithProgressW` at `0x180051426`

## string_xrefs

- `0x180051105`: `szUserSID`
- `0x180051237`: `UVHD-template.vhdx`
- `0x180051197`: `TEMP-`
- `0x180051180`: `szUvhdFilePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::CreateNewUvhdForUserFromTemplate(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        LPCWSTR lpNewFileName)
{
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  signed int v11; // ebx
  wchar_t *v12; // rax
  __int64 v13; // rsi
  int v14; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // r10
  const WCHAR *v20; // rax
  LPCWSTR v21; // r10
  signed int LastError; // eax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // rax
  const WCHAR *v25; // rax
  const WCHAR *v26; // rax
  signed int v27; // eax
  const WCHAR *v28; // rax
  signed int v29; // eax
  void **v31; // [rsp+30h] [rbp-69h] BYREF
  int v32; // [rsp+38h] [rbp-61h]
  __int64 v33; // [rsp+3Ch] [rbp-5Dh]
  int v34; // [rsp+44h] [rbp-55h]
  __int64 v35; // [rsp+48h] [rbp-51h]
  int v36; // [rsp+50h] [rbp-49h]
  void **v37; // [rsp+58h] [rbp-41h] BYREF
  int v38; // [rsp+60h] [rbp-39h]
  __int64 v39; // [rsp+64h] [rbp-35h]
  int v40; // [rsp+6Ch] [rbp-2Dh]
  __int64 v41; // [rsp+70h] [rbp-29h]
  int v42; // [rsp+78h] [rbp-21h]
  void **v43; // [rsp+80h] [rbp-19h] BYREF
  int v44; // [rsp+88h] [rbp-11h]
  __int64 v45; // [rsp+8Ch] [rbp-Dh]
  int v46; // [rsp+94h] [rbp-5h]
  __int64 v47; // [rsp+98h] [rbp-1h]
  int v48; // [rsp+A0h] [rbp+7h]

  v33 = 128;
  v35 = 0;
  v34 = 0;
  v32 = 0;
  v36 = 0x8000000;
  v42 = 0x8000000;
  v48 = 0x8000000;
  v31 = &CPathString::`vftable';
  v39 = 128;
  v41 = 0;
  v40 = 0;
  v38 = 0;
  v37 = &CPathString::`vftable';
  v45 = 128;
  v47 = 0;
  v46 = 0;
  v44 = 0;
  v43 = &CPathString::`vftable';
  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 118;
    v10 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v10);
LABEL_7:
    v11 = -2147024809;
    goto LABEL_85;
  }
  if ( !a3 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 119;
    v10 = L"szUvhdShareUrl";
    goto LABEL_6;
  }
  if ( !lpNewFileName )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 120;
    v10 = L"szUvhdFilePath";
    goto LABEL_6;
  }
  v12 = wcsrchr(lpNewFileName, 0x5Cu);
  v13 = (__int64)(v12 + 1);
  if ( !v12 )
    v13 = 0;
  v14 = CPathString::BuildPath((CPathString *)&v31, a3, L"TEMP-");
  v11 = v14;
  if ( v14 >= 0 )
  {
    v14 = CBaseStringT<unsigned short>::Append((__int64)&v31, v13);
    v11 = v14;
    if ( v14 >= 0 )
    {
      v14 = CPathString::BuildPath((CPathString *)&v37, a3, L"UVHD-template.vhdx");
      v11 = v14;
      if ( v14 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          CBaseStringT<unsigned short>::PContents(&v31);
          v18 = CBaseStringT<unsigned short>::PContents(&v37);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            124,
            (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
            v18,
            v19);
        }
        CBaseStringT<unsigned short>::PContents(&v31);
        v20 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v37);
        if ( CopyFileExW(v20, v21, 0, 0, 0, 0) )
          goto LABEL_51;
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError && (LastError & 0xFFFF0000) == 0 )
        {
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          v11 = v11 & 0x8000FFFF | 0x50520000;
        }
        if ( v11 >= 0 )
        {
LABEL_51:
          v23 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v31);
          v14 = RdVhd::Uvhd::CUvhdDiskManager::RandomizeVDiskSignature(this, v23, (struct CPathString *)&v43);
          v11 = v14;
          if ( v14 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 126;
              goto LABEL_25;
            }
            goto LABEL_85;
          }
          v24 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v43);
          v14 = RdVhd::Uvhd::CUvhdDiskManager::BindUvhdToUser(this, v24, a2);
          v11 = v14;
          if ( v14 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 127;
              goto LABEL_25;
            }
            goto LABEL_85;
          }
          v25 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v31);
          if ( MoveFileWithProgressW(v25, lpNewFileName, 0, 0, 2u) )
            goto LABEL_85;
          v26 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v31);
          if ( CopyFileExW(v26, lpNewFileName, 0, 0, 0, 0) )
            goto LABEL_73;
          v27 = GetLastError();
          v11 = v27;
          if ( v27 && (v27 & 0xFFFF0000) == 0 )
          {
            if ( v27 > 0 )
              v11 = (unsigned __int16)v27 | 0x80070000;
            v11 = v11 & 0x8000FFFF | 0x50530000;
          }
          if ( v11 >= 0 )
          {
LABEL_73:
            v28 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v31);
            if ( DeleteFileW(v28) )
              goto LABEL_85;
            v29 = GetLastError();
            v11 = v29;
            if ( v29 && (v29 & 0xFFFF0000) == 0 )
            {
              if ( v29 > 0 )
                v11 = (unsigned __int16)v29 | 0x80070000;
              v11 = v11 & 0x8000FFFF | 0x50540000;
            }
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
            {
              goto LABEL_85;
            }
            v16 = 129;
          }
          else
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_85;
            }
            v16 = 128;
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_85;
          }
          v16 = 125;
        }
        v17 = (unsigned int)v11;
        goto LABEL_84;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 123;
        goto LABEL_25;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 122;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 121;
LABEL_25:
      v17 = (unsigned int)v14;
LABEL_84:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v17);
    }
  }
LABEL_85:
  CPathString::~CPathString((CPathString *)&v43);
  CPathString::~CPathString((CPathString *)&v37);
  CPathString::~CPathString((CPathString *)&v31);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180051058  push    rbp
0x18005105a  push    rbx
0x18005105b  push    rsi
0x18005105c  push    rdi
0x18005105d  push    r12
0x18005105f  push    r13
0x180051061  push    r14
0x180051063  push    r15
0x180051065  lea     rbp, [rsp-1Fh]
0x18005106a  sub     rsp, 0B8h
0x180051071  xor     r13d, r13d
0x180051074  mov     [rbp+57h+var_B4], 80h
0x18005107c  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180051083  mov     [rbp+57h+var_A8], r13
0x180051087  mov     r12, rcx
0x18005108a  mov     [rbp+57h+var_AC], r13d
0x18005108e  mov     ecx, 8000000h
0x180051093  mov     [rbp+57h+var_B8], r13d
0x180051097  mov     [rbp+57h+var_A0], ecx
0x18005109a  mov     r14, r9
0x18005109d  mov     [rbp+57h+var_78], ecx
0x1800510a0  mov     rdi, r8
0x1800510a3  mov     [rbp+57h+var_50], ecx
0x1800510a6  mov     r15, rdx
0x1800510a9  mov     [rbp+57h+var_C0], rax
0x1800510ad  mov     [rbp+57h+var_8C], 80h
0x1800510b5  mov     [rbp+57h+var_80], r13
0x1800510b9  mov     [rbp+57h+var_84], r13d
0x1800510bd  mov     [rbp+57h+var_90], r13d
0x1800510c1  mov     [rbp+57h+var_98], rax
0x1800510c5  mov     [rbp+57h+var_64], 80h
0x1800510cd  mov     [rbp+57h+var_58], r13
0x1800510d1  mov     [rbp+57h+var_5C], r13d
0x1800510d5  mov     [rbp+57h+var_68], r13d
0x1800510d9  mov     [rbp+57h+var_70], rax
0x1800510dd  test    rdx, rdx
0x1800510e0  jnz     short loc_180051126
0x1800510e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800510e9  lea     rdi, WPP_GLOBAL_Control
0x1800510f0  cmp     rcx, rdi
0x1800510f3  jz      short loc_18005111C
0x1800510f5  test    byte ptr [rcx+1Ch], 4
0x1800510f9  jz      short loc_18005111C
0x1800510fb  cmp     byte ptr [rcx+19h], 2
0x1800510ff  jb      short loc_18005111C
0x180051101  lea     edx, [r15+76h]
0x180051105  lea     r9, aSzusersid_0; "szUserSID"
0x18005110c  mov     rcx, [rcx+10h]
0x180051110  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180051117  call    WPP_SF_S
0x18005111c  mov     ebx, 80070057h
0x180051121  jmp     loc_18005151C
0x180051126  test    rdi, rdi
0x180051129  jnz     short loc_180051158
0x18005112b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051132  lea     rdi, WPP_GLOBAL_Control
0x180051139  cmp     rcx, rdi
0x18005113c  jz      short loc_18005111C
0x18005113e  test    byte ptr [rcx+1Ch], 4
0x180051142  jz      short loc_18005111C
0x180051144  cmp     byte ptr [rcx+19h], 2
0x180051148  jb      short loc_18005111C
0x18005114a  mov     edx, 77h ; 'w'
0x18005114f  lea     r9, aSzuvhdshareurl; "szUvhdShareUrl"
0x180051156  jmp     short loc_18005110C
0x180051158  test    r14, r14
0x18005115b  jnz     short loc_180051189
0x18005115d  mov     rcx, cs:WPP_GLOBAL_Control
0x180051164  lea     rdi, WPP_GLOBAL_Control
0x18005116b  cmp     rcx, rdi
0x18005116e  jz      short loc_18005111C
0x180051170  test    byte ptr [rcx+1Ch], 4
0x180051174  jz      short loc_18005111C
0x180051176  cmp     byte ptr [rcx+19h], 2
0x18005117a  jb      short loc_18005111C
0x18005117c  lea     edx, [r14+78h]
0x180051180  lea     r9, aSzuvhdfilepath; "szUvhdFilePath"
0x180051187  jmp     short loc_18005110C
0x180051189  mov     edx, 5Ch ; '\'; Ch
0x18005118e  mov     rcx, r14; Str
0x180051191  call    cs:__imp_wcsrchr
0x180051197  lea     r8, aTemp_0; "TEMP-"
0x18005119e  mov     rdx, rdi; unsigned __int16 *
0x1800511a1  test    rax, rax
0x1800511a4  lea     rcx, [rbp+57h+var_C0]; this
0x1800511a8  lea     rsi, [rax+2]
0x1800511ac  cmovz   rsi, rax
0x1800511b0  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x1800511b5  mov     ebx, eax
0x1800511b7  test    eax, eax
0x1800511b9  jns     short loc_1800511F3
0x1800511bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800511c2  lea     rdi, WPP_GLOBAL_Control
0x1800511c9  cmp     rcx, rdi
0x1800511cc  jz      loc_18005151C
0x1800511d2  test    byte ptr [rcx+1Ch], 4
0x1800511d6  jz      loc_18005151C
0x1800511dc  cmp     byte ptr [rcx+19h], 2
0x1800511e0  jb      loc_18005151C
0x1800511e6  mov     edx, 79h ; 'y'
0x1800511eb  mov     r9d, eax
0x1800511ee  jmp     loc_18005150C
0x1800511f3  mov     rdx, rsi
0x1800511f6  lea     rcx, [rbp+57h+var_C0]
0x1800511fa  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x1800511ff  mov     ebx, eax
0x180051201  test    eax, eax
0x180051203  jns     short loc_180051237
0x180051205  mov     rcx, cs:WPP_GLOBAL_Control
0x18005120c  lea     rdi, WPP_GLOBAL_Control
0x180051213  cmp     rcx, rdi
0x180051216  jz      loc_18005151C
0x18005121c  test    byte ptr [rcx+1Ch], 4
0x180051220  jz      loc_18005151C
0x180051226  cmp     byte ptr [rcx+19h], 2
0x18005122a  jb      loc_18005151C
0x180051230  mov     edx, 7Ah ; 'z'
0x180051235  jmp     short loc_1800511EB
0x180051237  lea     r8, aUvhdTemplateVh; "UVHD-template.vhdx"
0x18005123e  mov     rdx, rdi; unsigned __int16 *
0x180051241  lea     rcx, [rbp+57h+var_98]; this
0x180051245  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x18005124a  mov     ebx, eax
0x18005124c  test    eax, eax
0x18005124e  jns     short loc_180051285
0x180051250  mov     rcx, cs:WPP_GLOBAL_Control
0x180051257  lea     rdi, WPP_GLOBAL_Control
0x18005125e  cmp     rcx, rdi
0x180051261  jz      loc_18005151C
0x180051267  test    byte ptr [rcx+1Ch], 4
0x18005126b  jz      loc_18005151C
0x180051271  cmp     byte ptr [rcx+19h], 2
0x180051275  jb      loc_18005151C
0x18005127b  mov     edx, 7Bh ; '{'
0x180051280  jmp     loc_1800511EB
0x180051285  mov     rax, cs:WPP_GLOBAL_Control
0x18005128c  lea     rdi, WPP_GLOBAL_Control
0x180051293  cmp     rax, rdi
0x180051296  jz      short loc_1800512DD
0x180051298  test    byte ptr [rax+1Ch], 4
0x18005129c  jz      short loc_1800512DD
0x18005129e  cmp     byte ptr [rax+19h], 4
0x1800512a2  jb      short loc_1800512DD
0x1800512a4  lea     rcx, [rbp+57h+var_C0]
0x1800512a8  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800512ad  lea     rcx, [rbp+57h+var_98]
0x1800512b1  mov     r10, rax
0x1800512b4  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800512b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800512c0  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800512c7  mov     edx, 7Ch ; '|'
0x1800512cc  mov     [rsp+0F0h+pbCancel], r10
0x1800512d1  mov     r9, rax
0x1800512d4  mov     rcx, [rcx+10h]
0x1800512d8  call    WPP_SF_SS
0x1800512dd  lea     rcx, [rbp+57h+var_C0]
0x1800512e1  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800512e6  lea     rcx, [rbp+57h+var_98]
0x1800512ea  mov     r10, rax
0x1800512ed  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800512f2  xor     r9d, r9d; lpData
0x1800512f5  mov     [rsp+0F0h+dwCopyFlags], r13d; dwCopyFlags
0x1800512fa  xor     r8d, r8d; lpProgressRoutine
0x1800512fd  mov     [rsp+0F0h+pbCancel], r13; pbCancel
0x180051302  mov     rdx, r10; lpNewFileName
0x180051305  mov     rcx, rax; lpExistingFileName
0x180051308  call    cs:__imp_CopyFileExW
0x18005130e  mov     esi, 0FFFF0000h
0x180051313  test    eax, eax
0x180051315  jnz     short loc_180051372
0x180051317  call    cs:__imp_GetLastError
0x18005131d  mov     ebx, eax
0x18005131f  test    eax, eax
0x180051321  jz      short loc_180051340
0x180051323  test    esi, eax
0x180051325  jnz     short loc_180051340
0x180051327  test    eax, eax
0x180051329  jle     short loc_180051334
0x18005132b  movzx   ebx, ax
0x18005132e  or      ebx, 80070000h
0x180051334  and     ebx, 0D052FFFFh
0x18005133a  or      ebx, 50520000h
0x180051340  test    ebx, ebx
0x180051342  jns     short loc_180051372
0x180051344  mov     rcx, cs:WPP_GLOBAL_Control
0x18005134b  cmp     rcx, rdi
0x18005134e  jz      loc_18005151C
0x180051354  test    byte ptr [rcx+1Ch], 4
0x180051358  jz      loc_18005151C
0x18005135e  cmp     byte ptr [rcx+19h], 2
0x180051362  jb      loc_18005151C
0x180051368  mov     edx, 7Dh ; '}'
0x18005136d  jmp     loc_180051509
0x180051372  lea     rcx, [rbp+57h+var_C0]
0x180051376  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005137b  mov     rdx, rax; unsigned __int16 *
0x18005137e  lea     r8, [rbp+57h+var_70]; struct CPathString *
0x180051382  mov     rcx, r12; this
0x180051385  call    ?RandomizeVDiskSignature@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CUvhdDiskManager::RandomizeVDiskSignature(ushort const *,CPathString &)
0x18005138a  mov     ebx, eax
0x18005138c  test    eax, eax
0x18005138e  jns     short loc_1800513BE
0x180051390  mov     rcx, cs:WPP_GLOBAL_Control
0x180051397  cmp     rcx, rdi
0x18005139a  jz      loc_18005151C
0x1800513a0  test    byte ptr [rcx+1Ch], 4
0x1800513a4  jz      loc_18005151C
0x1800513aa  cmp     byte ptr [rcx+19h], 2
0x1800513ae  jb      loc_18005151C
0x1800513b4  mov     edx, 7Eh ; '~'
0x1800513b9  jmp     loc_1800511EB
0x1800513be  lea     rcx, [rbp+57h+var_70]
0x1800513c2  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800513c7  mov     rdx, rax; unsigned __int16 *
0x1800513ca  mov     r8, r15; unsigned __int16 *
0x1800513cd  mov     rcx, r12; this
0x1800513d0  call    ?BindUvhdToUser@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0@Z; RdVhd::Uvhd::CUvhdDiskManager::BindUvhdToUser(ushort const *,ushort const *)
0x1800513d5  mov     ebx, eax
0x1800513d7  test    eax, eax
0x1800513d9  jns     short loc_180051409
0x1800513db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800513e2  cmp     rcx, rdi
0x1800513e5  jz      loc_18005151C
0x1800513eb  test    byte ptr [rcx+1Ch], 4
0x1800513ef  jz      loc_18005151C
0x1800513f5  cmp     byte ptr [rcx+19h], 2
0x1800513f9  jb      loc_18005151C
0x1800513ff  mov     edx, 7Fh
0x180051404  jmp     loc_1800511EB
0x180051409  lea     rcx, [rbp+57h+var_C0]
0x18005140d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180051412  mov     rcx, rax; lpExistingFileName
0x180051415  mov     dword ptr [rsp+0F0h+pbCancel], 2; dwFlags
0x18005141d  xor     r9d, r9d; lpData
0x180051420  xor     r8d, r8d; lpProgressRoutine
0x180051423  mov     rdx, r14; lpNewFileName
0x180051426  call    cs:__imp_MoveFileWithProgressW
0x18005142c  test    eax, eax
0x18005142e  jnz     loc_18005151C
0x180051434  lea     rcx, [rbp+57h+var_C0]
0x180051438  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005143d  mov     rcx, rax; lpExistingFileName
0x180051440  mov     [rsp+0F0h+dwCopyFlags], r13d; dwCopyFlags
0x180051445  xor     r9d, r9d; lpData
0x180051448  mov     [rsp+0F0h+pbCancel], r13; pbCancel
0x18005144d  xor     r8d, r8d; lpProgressRoutine
0x180051450  mov     rdx, r14; lpNewFileName
0x180051453  call    cs:__imp_CopyFileExW
0x180051459  test    eax, eax
0x18005145b  jnz     short loc_1800514AD
0x18005145d  call    cs:__imp_GetLastError
0x180051463  mov     ebx, eax
0x180051465  test    eax, eax
0x180051467  jz      short loc_180051486
0x180051469  test    esi, eax
0x18005146b  jnz     short loc_180051486
0x18005146d  test    eax, eax
0x18005146f  jle     short loc_18005147A
0x180051471  movzx   ebx, ax
0x180051474  or      ebx, 80070000h
0x18005147a  and     ebx, 0D053FFFFh
0x180051480  or      ebx, 50530000h
0x180051486  test    ebx, ebx
0x180051488  jns     short loc_1800514AD
0x18005148a  mov     rcx, cs:WPP_GLOBAL_Control
0x180051491  cmp     rcx, rdi
0x180051494  jz      loc_18005151C
0x18005149a  test    byte ptr [rcx+1Ch], 4
0x18005149e  jz      short loc_18005151C
0x1800514a0  cmp     byte ptr [rcx+19h], 2
0x1800514a4  jb      short loc_18005151C
0x1800514a6  mov     edx, 80h
0x1800514ab  jmp     short loc_180051509
0x1800514ad  lea     rcx, [rbp+57h+var_C0]
0x1800514b1  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800514b6  mov     rcx, rax; lpFileName
0x1800514b9  call    cs:__imp_DeleteFileW
0x1800514bf  test    eax, eax
0x1800514c1  jnz     short loc_18005151C
0x1800514c3  call    cs:__imp_GetLastError
0x1800514c9  mov     ebx, eax
0x1800514cb  test    eax, eax
0x1800514cd  jz      short loc_1800514EC
0x1800514cf  test    esi, eax
0x1800514d1  jnz     short loc_1800514EC
0x1800514d3  test    eax, eax
0x1800514d5  jle     short loc_1800514E0
0x1800514d7  movzx   ebx, ax
0x1800514da  or      ebx, 80070000h
0x1800514e0  and     ebx, 0D054FFFFh
0x1800514e6  or      ebx, 50540000h
0x1800514ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800514f3  cmp     rcx, rdi
0x1800514f6  jz      short loc_18005151C
0x1800514f8  test    byte ptr [rcx+1Ch], 4
0x1800514fc  jz      short loc_18005151C
0x1800514fe  cmp     byte ptr [rcx+19h], 3
0x180051502  jb      short loc_18005151C
0x180051504  mov     edx, 81h
0x180051509  mov     r9d, ebx
  ... truncated ...
```
