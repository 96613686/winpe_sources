# CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)

- ea: `0x140030254`
- end: `0x1400306da`
- name: `?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z`
- size: `1158`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1400306e0`
- `0x1400308b0`

## callees

- `0x140002c73`
- `0x140004b70`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x14002f968`
- `0x140030254`
- `0x140032b98`
- `0x1400370a0`
- `0x140037184`
- `0x1400720c8`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003033a`
- `KERNEL32!GetLastError` at `0x140030425`
- `KERNEL32!GetLastError` at `0x140030499`
- `KERNEL32!GetLastError` at `0x140030580`
- `KERNEL32!GetLastError` at `0x1400305e3`
- `KERNEL32!GetLastError` at `0x14003068b`
- `KERNEL32!GetLastError` at `0x14003033a`
- `KERNEL32!GetLastError` at `0x140030425`
- `KERNEL32!GetLastError` at `0x140030499`
- `KERNEL32!GetLastError` at `0x140030580`
- `KERNEL32!GetLastError` at `0x1400305e3`
- `KERNEL32!GetLastError` at `0x14003068b`
- `KERNEL32!SetLastError` at `0x14003067d`
- `KERNEL32!SetLastError` at `0x14003069e`
- `KERNEL32!SetLastError` at `0x14003067d`
- `KERNEL32!SetLastError` at `0x14003069e`
- `KERNEL32!DeleteFileW` at `0x140030461`
- `KERNEL32!DeleteFileW` at `0x140030613`
- `KERNEL32!DeleteFileW` at `0x14003066e`
- `KERNEL32!DeleteFileW` at `0x140030461`
- `KERNEL32!DeleteFileW` at `0x140030613`
- `KERNEL32!DeleteFileW` at `0x14003066e`
- `KERNEL32!CopyFileW` at `0x1400305bb`
- `KERNEL32!CopyFileW` at `0x1400305bb`
- `FXSTIFF!MergeTiffFiles` at `0x1400303f9`
- `FXSTIFF!MergeTiffFiles` at `0x1400303f9`

## pseudocode

```c
__int64 __fastcall CreateTiffFile(struct _JOB_QUEUE *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // rcx
  __int16 v7; // r10
  bool v8; // zf
  struct _JOB_QUEUE *v9; // rbx
  const unsigned __int16 *v10; // rcx
  DWORD LastError; // eax
  __int64 v12; // rdx
  char v13; // al
  char v14; // al
  int v15; // ebx
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  const WCHAR *v18; // rbx
  DWORD v19; // eax
  unsigned int v20; // ebx
  unsigned int v22; // [rsp+40h] [rbp-C0h]
  __int16 v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  v7 = 0;
  v8 = *((_DWORD *)a1 + 9) == 2;
  v23[0] = 0;
  if ( v8 && (v9 = (struct _JOB_QUEUE *)*((_QWORD *)a1 + 73)) != 0 )
  {
    if ( *((_QWORD *)v9 + 23) )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)v9 + 9);
      if ( v10 )
      {
        if ( !(unsigned int)GetBodyTiffResolution(v10, v23) )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v12 = 51;
LABEL_44:
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              LastError);
            goto LABEL_58;
          }
          goto LABEL_58;
        }
        v7 = v23[0];
      }
      if ( !(unsigned int)CreateCoverpageTiffFileEx2(
                            v7,
                            *((_DWORD *)a1 + 16),
                            (struct _JOB_QUEUE *)((char *)v9 + 176),
                            (struct _JOB_QUEUE *)((char *)a1 + 448),
                            (struct _JOB_QUEUE *)((char *)v9 + 240),
                            a2,
                            *((const unsigned __int16 **)v9 + 55),
                            FileName,
                            v22) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *((_DWORD *)a1 + 8),
            *((_QWORD *)v9 + 23));
        }
        goto LABEL_58;
      }
      if ( *((_QWORD *)v9 + 9) && !(unsigned int)MergeTiffFiles(FileName) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = GetLastError();
          WPP_SF_lSSl(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)FileName, *((_QWORD *)v9 + 9), v13);
        }
        if ( !DeleteFileW(FileName)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = GetLastError();
          WPP_SF_lSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            *((_DWORD *)a1 + 8),
            (__int64)FileName,
            v14);
        }
        goto LABEL_58;
      }
      v15 = StringCchCopyW(a3, 0x104u, FileName);
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v17 = 55;
LABEL_56:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, (unsigned int)v15);
LABEL_57:
        DeleteFileW(FileName);
        SetLastError((unsigned __int16)v15);
        goto LABEL_58;
      }
      return 1;
    }
  }
  else
  {
    v9 = a1;
  }
  v18 = (const WCHAR *)*((_QWORD *)v9 + 9);
  if ( !a2 )
    a2 = L"tif";
  if ( GenerateUniqueFileNameWithPrefix(v6, *((_QWORD *)g_pFaxConfig + 12), 0, a2, FileName) )
  {
    if ( !CopyFileW(v18, FileName, 0) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v19);
      }
      DeleteFileW(FileName);
      goto LABEL_58;
    }
    v15 = StringCchCopyW(a3, 0x104u, FileName);
    if ( v15 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v17 = 50;
      goto LABEL_56;
    }
    return 1;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v12 = 48;
    goto LABEL_44;
  }
LABEL_58:
  v20 = 0;
  if ( !GetLastError() )
    SetLastError(0x1Fu);
  return v20;
}

```

## disassembly

```asm
0x140030254  mov     [rsp-8+arg_18], rbx
0x140030259  push    rbp
0x14003025a  push    rsi
0x14003025b  push    rdi
0x14003025c  push    r13
0x14003025e  push    r14
0x140030260  lea     rbp, [rsp-180h]
0x140030268  sub     rsp, 280h
0x14003026f  mov     rax, cs:__security_cookie
0x140030276  xor     rax, rsp
0x140030279  mov     [rbp+1A0h+var_30], rax
0x140030280  mov     r14, r8
0x140030283  mov     rsi, rdx
0x140030286  mov     rdi, rcx
0x140030289  mov     rcx, cs:WPP_GLOBAL_Control
0x140030290  lea     r13, WPP_GLOBAL_Control
0x140030297  cmp     rcx, r13
0x14003029a  jz      short loc_1400302BD
0x14003029c  test    byte ptr [rcx+1Ch], 4
0x1400302a0  jz      short loc_1400302BD
0x1400302a2  cmp     byte ptr [rcx+19h], 5
0x1400302a6  jb      short loc_1400302BD
0x1400302a8  mov     rcx, [rcx+10h]
0x1400302ac  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400302b3  mov     edx, 2Fh ; '/'
0x1400302b8  call    WPP_SF_
0x1400302bd  xor     edx, edx; Val
0x1400302bf  lea     rcx, [rsp+2A0h+FileName]; void *
0x1400302c4  mov     r8d, 208h; Size
0x1400302ca  call    memset_0
0x1400302cf  xor     r10d, r10d
0x1400302d2  cmp     dword ptr [rdi+24h], 2
0x1400302d6  mov     [rsp+2A0h+var_250], r10w
0x1400302dc  jnz     loc_140030522
0x1400302e2  mov     rbx, [rdi+248h]
0x1400302e9  test    rbx, rbx
0x1400302ec  jz      loc_140030522
0x1400302f2  cmp     [rbx+0B8h], r10
0x1400302f9  jz      loc_140030525
0x1400302ff  mov     rcx, [rbx+48h]; unsigned __int16 *
0x140030303  test    rcx, rcx
0x140030306  jz      short loc_140030356
0x140030308  lea     rdx, [rsp+2A0h+var_250]; __int16 *
0x14003030d  call    ?GetBodyTiffResolution@@YAHPEBGPEAF@Z; GetBodyTiffResolution(ushort const *,short *)
0x140030312  test    eax, eax
0x140030314  jnz     short loc_140030350
0x140030316  mov     rax, cs:WPP_GLOBAL_Control
0x14003031d  cmp     rax, r13
0x140030320  jz      loc_140030689
0x140030326  test    byte ptr [rax+1Ch], 4
0x14003032a  jz      loc_140030689
0x140030330  cmp     byte ptr [rax+19h], 2
0x140030334  jb      loc_140030689
0x14003033a  call    cs:__imp_GetLastError
0x140030341  nop     dword ptr [rax+rax+00h]
0x140030346  mov     edx, 33h ; '3'
0x14003034b  jmp     loc_140030591
0x140030350  movzx   r10d, [rsp+2A0h+var_250]
0x140030356  mov     edx, [rdi+40h]; unsigned int
0x140030359  lea     rcx, [rbx+0F0h]
0x140030360  lea     rax, [rsp+2A0h+FileName]
0x140030365  mov     [rsp+2A0h+var_268], rax; unsigned __int16 *
0x14003036a  lea     r9, [rdi+1C0h]; struct _FAX_PERSONAL_PROFILEW *
0x140030371  mov     rax, [rbx+1B8h]
0x140030378  lea     r8, [rbx+0B0h]; struct _FAX_COVERPAGE_INFO_EXW *
0x14003037f  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x140030384  mov     [rsp+2A0h+var_278], rsi; unsigned __int16 *
0x140030389  mov     [rsp+2A0h+var_280], rcx; struct _FAX_PERSONAL_PROFILEW *
0x14003038e  movzx   ecx, r10w; __int16
0x140030392  call    ?CreateCoverpageTiffFileEx2@@YAHFKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@1PEBG2PEAGK@Z; CreateCoverpageTiffFileEx2(short,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *,ushort const *,ushort const *,ushort *,ulong)
0x140030397  test    eax, eax
0x140030399  jnz     short loc_1400303E7
0x14003039b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400303a2  cmp     rcx, r13
0x1400303a5  jz      loc_140030689
0x1400303ab  test    byte ptr [rcx+1Ch], 4
0x1400303af  jz      loc_140030689
0x1400303b5  cmp     byte ptr [rcx+19h], 2
0x1400303b9  jb      loc_140030689
0x1400303bf  mov     r9d, [rdi+20h]
0x1400303c3  lea     edx, [rax+34h]
0x1400303c6  mov     rax, [rbx+0B8h]
0x1400303cd  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400303d4  mov     rcx, [rcx+10h]
0x1400303d8  mov     [rsp+2A0h+var_280], rax
0x1400303dd  call    WPP_SF_DS
0x1400303e2  jmp     loc_140030689
0x1400303e7  mov     rdx, [rbx+48h]
0x1400303eb  test    rdx, rdx
0x1400303ee  jz      loc_1400304D8
0x1400303f4  lea     rcx, [rsp+2A0h+FileName]
0x1400303f9  call    cs:__imp_MergeTiffFiles
0x140030400  nop     dword ptr [rax+rax+00h]
0x140030405  test    eax, eax
0x140030407  jnz     loc_1400304D8
0x14003040d  mov     rax, cs:WPP_GLOBAL_Control
0x140030414  cmp     rax, r13
0x140030417  jz      short loc_14003045C
0x140030419  test    byte ptr [rax+1Ch], 4
0x14003041d  jz      short loc_14003045C
0x14003041f  cmp     byte ptr [rax+19h], 2
0x140030423  jb      short loc_14003045C
0x140030425  call    cs:__imp_GetLastError
0x14003042c  nop     dword ptr [rax+rax+00h]
0x140030431  mov     rcx, cs:WPP_GLOBAL_Control
0x140030438  mov     r9d, [rdi+20h]
0x14003043c  mov     dword ptr [rsp+2A0h+var_270], eax; char
0x140030440  mov     rax, [rbx+48h]
0x140030444  mov     rcx, [rcx+10h]; LoggerHandle
0x140030448  mov     [rsp+2A0h+var_278], rax; __int64
0x14003044d  lea     rax, [rsp+2A0h+FileName]
0x140030452  mov     [rsp+2A0h+var_280], rax; __int64
0x140030457  call    WPP_SF_lSSl
0x14003045c  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x140030461  call    cs:__imp_DeleteFileW
0x140030468  nop     dword ptr [rax+rax+00h]
0x14003046d  test    eax, eax
0x14003046f  jnz     loc_140030689
0x140030475  mov     rax, cs:WPP_GLOBAL_Control
0x14003047c  cmp     rax, r13
0x14003047f  jz      loc_140030689
0x140030485  test    byte ptr [rax+1Ch], 4
0x140030489  jz      loc_140030689
0x14003048f  cmp     byte ptr [rax+19h], 2
0x140030493  jb      loc_140030689
0x140030499  call    cs:__imp_GetLastError
0x1400304a0  nop     dword ptr [rax+rax+00h]
0x1400304a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400304ac  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400304b3  mov     r9d, [rdi+20h]
0x1400304b7  mov     edx, 36h ; '6'
0x1400304bc  mov     dword ptr [rsp+2A0h+var_278], eax
0x1400304c0  lea     rax, [rsp+2A0h+FileName]
0x1400304c5  mov     [rsp+2A0h+var_280], rax
0x1400304ca  mov     rcx, [rcx+10h]
0x1400304ce  call    WPP_SF_lSl
0x1400304d3  jmp     loc_140030689
0x1400304d8  lea     r8, [rsp+2A0h+FileName]; unsigned __int16 *
0x1400304dd  mov     edx, 104h; unsigned __int64
0x1400304e2  mov     rcx, r14; unsigned __int16 *
0x1400304e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400304ea  mov     ebx, eax
0x1400304ec  test    eax, eax
0x1400304ee  jns     loc_1400306AC
0x1400304f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400304fb  cmp     rcx, r13
0x1400304fe  jz      loc_140030669
0x140030504  test    byte ptr [rcx+1Ch], 4
0x140030508  jz      loc_140030669
0x14003050e  cmp     byte ptr [rcx+19h], 2
0x140030512  jb      loc_140030669
0x140030518  mov     edx, 37h ; '7'
0x14003051d  jmp     loc_140030656
0x140030522  mov     rbx, rdi
0x140030525  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14003052c  lea     rax, aTif; "tif"
0x140030533  mov     rbx, [rbx+48h]
0x140030537  test    rsi, rsi
0x14003053a  cmovz   rsi, rax
0x14003053e  lea     rax, [rsp+2A0h+FileName]
0x140030543  mov     rdx, [rdx+60h]
0x140030547  mov     r9, rsi
0x14003054a  xor     r8d, r8d
0x14003054d  mov     [rsp+2A0h+var_280], rax
0x140030552  call    GenerateUniqueFileNameWithPrefix
0x140030557  test    rax, rax
0x14003055a  jnz     short loc_1400305B0
0x14003055c  mov     rax, cs:WPP_GLOBAL_Control
0x140030563  cmp     rax, r13
0x140030566  jz      loc_140030689
0x14003056c  test    byte ptr [rax+1Ch], 4
0x140030570  jz      loc_140030689
0x140030576  cmp     byte ptr [rax+19h], 2
0x14003057a  jb      loc_140030689
0x140030580  call    cs:__imp_GetLastError
0x140030587  nop     dword ptr [rax+rax+00h]
0x14003058c  mov     edx, 30h ; '0'
0x140030591  mov     rcx, cs:WPP_GLOBAL_Control
0x140030598  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003059f  mov     r9d, eax
0x1400305a2  mov     rcx, [rcx+10h]
0x1400305a6  call    WPP_SF_d
0x1400305ab  jmp     loc_140030689
0x1400305b0  xor     r8d, r8d; bFailIfExists
0x1400305b3  lea     rdx, [rsp+2A0h+FileName]; lpNewFileName
0x1400305b8  mov     rcx, rbx; lpExistingFileName
0x1400305bb  call    cs:__imp_CopyFileW
0x1400305c2  nop     dword ptr [rax+rax+00h]
0x1400305c7  test    eax, eax
0x1400305c9  jnz     short loc_140030621
0x1400305cb  mov     rax, cs:WPP_GLOBAL_Control
0x1400305d2  cmp     rax, r13
0x1400305d5  jz      short loc_14003060E
0x1400305d7  test    byte ptr [rax+1Ch], 4
0x1400305db  jz      short loc_14003060E
0x1400305dd  cmp     byte ptr [rax+19h], 2
0x1400305e1  jb      short loc_14003060E
0x1400305e3  call    cs:__imp_GetLastError
0x1400305ea  nop     dword ptr [rax+rax+00h]
0x1400305ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305f6  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400305fd  mov     edx, 31h ; '1'
0x140030602  mov     r9d, eax
0x140030605  mov     rcx, [rcx+10h]
0x140030609  call    WPP_SF_d
0x14003060e  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x140030613  call    cs:__imp_DeleteFileW
0x14003061a  nop     dword ptr [rax+rax+00h]
0x14003061f  jmp     short loc_140030689
0x140030621  lea     r8, [rsp+2A0h+FileName]; unsigned __int16 *
0x140030626  mov     edx, 104h; unsigned __int64
0x14003062b  mov     rcx, r14; unsigned __int16 *
0x14003062e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140030633  mov     ebx, eax
0x140030635  test    eax, eax
0x140030637  jns     short loc_1400306AC
0x140030639  mov     rcx, cs:WPP_GLOBAL_Control
0x140030640  cmp     rcx, r13
0x140030643  jz      short loc_140030669
0x140030645  test    byte ptr [rcx+1Ch], 4
0x140030649  jz      short loc_140030669
0x14003064b  cmp     byte ptr [rcx+19h], 2
0x14003064f  jb      short loc_140030669
0x140030651  mov     edx, 32h ; '2'
0x140030656  mov     rcx, [rcx+10h]
0x14003065a  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030661  mov     r9d, ebx
0x140030664  call    WPP_SF_d
0x140030669  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14003066e  call    cs:__imp_DeleteFileW
0x140030675  nop     dword ptr [rax+rax+00h]
0x14003067a  movzx   ecx, bx; dwErrCode
0x14003067d  call    cs:__imp_SetLastError
0x140030684  nop     dword ptr [rax+rax+00h]
0x140030689  xor     ebx, ebx
0x14003068b  call    cs:__imp_GetLastError
0x140030692  nop     dword ptr [rax+rax+00h]
0x140030697  test    eax, eax
0x140030699  jnz     short loc_1400306B1
0x14003069b  lea     ecx, [rbx+1Fh]; dwErrCode
0x14003069e  call    cs:__imp_SetLastError
0x1400306a5  nop     dword ptr [rax+rax+00h]
0x1400306aa  jmp     short loc_1400306B1
0x1400306ac  mov     ebx, 1
0x1400306b1  mov     eax, ebx
0x1400306b3  mov     rcx, [rbp+1A0h+var_30]
0x1400306ba  xor     rcx, rsp; StackCookie
0x1400306bd  call    __security_check_cookie
0x1400306c2  mov     rbx, [rsp+2A0h+arg_18]
0x1400306ca  add     rsp, 280h
0x1400306d1  pop     r14
0x1400306d3  pop     r13
0x1400306d5  pop     rdi
0x1400306d6  pop     rsi
0x1400306d7  pop     rbp
0x1400306d8  retn
```
