# CWUEtwConsumer::GetLogFolderSize(void)

- ea: `0x140016404`
- end: `0x140016564`
- name: `?GetLogFolderSize@CWUEtwConsumer@@IEAA_KXZ`
- size: `352`
- prototype: `unsigned __int64 __fastcall(CWUEtwConsumer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400167cc`

## callees

- `0x140011994`
- `0x140016324`
- `0x140016404`
- `0x1400171c0`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1400164a2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1400164a2`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x1400164c3`
- `api-ms-win-core-file-l1-2-1!GetCompressedFileSizeW` at `0x1400164c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall CWUEtwConsumer::GetLogFolderSize(CWUEtwConsumer *this)
{
  unsigned __int64 v2; // rsi
  unsigned int v3; // r15d
  __int64 i; // rdi
  const WCHAR *v5; // r14
  unsigned __int64 v6; // rbx
  DWORD CompressedFileSizeW; // eax
  unsigned int v9; // [rsp+28h] [rbp-58h] BYREF
  DWORD FileSizeHigh; // [rsp+2Ch] [rbp-54h] BYREF
  void **v11; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+38h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-40h]
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h]
  unsigned int v16; // [rsp+68h] [rbp-18h]

  v2 = 0;
  v11 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v12 = 0;
  v13 = 0;
  if ( (int)CWUEtwConsumer::WULogFilesToList(this, &v11) >= 0 )
  {
    v3 = HIDWORD(v13);
    for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i < HIDWORD(v13) )
      {
        v5 = *(const WCHAR **)(v12 + 8 * i);
        v6 = 0;
        FileInformation = 0;
        v15 = 0;
        v16 = 0;
        if ( v5 )
        {
          GetFileAttributesExW(v5, GetFileExInfoStandard, &FileInformation);
          if ( (_DWORD)FileInformation != -1 )
          {
            if ( (FileInformation & 0x800) != 0 )
            {
              FileSizeHigh = 0;
              v9 = 0;
              CompressedFileSizeW = GetCompressedFileSizeW(v5, &FileSizeHigh);
              if ( CompressedFileSizeW != -1 )
                v6 = __PAIR64__(FileSizeHigh, CompressedFileSizeW);
              if ( (int)CWUEtwConsumer::GetLogDriveSectorSize(this, &v9) >= 0 )
                v6 = v9 + v6 - 1 - (v9 + v6 - 1) % v9;
            }
            else if ( (FileInformation & 0x10) == 0 )
            {
              v6 = __PAIR64__(HIDWORD(v15), v16);
            }
          }
        }
        if ( v6 + v2 < v2 )
        {
          v2 = 0;
          break;
        }
        v2 += v6;
      }
    }
  }
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v11);
  return v2;
}

```

## disassembly

```asm
0x140016404  mov     [rsp-28h+arg_8], rbx
0x140016409  mov     [rsp-28h+arg_10], rsi
0x14001640e  push    rbp
0x14001640f  push    rdi
0x140016410  push    r12
0x140016412  push    r14
0x140016414  push    r15
0x140016416  mov     rbp, rsp
0x140016419  sub     rsp, 80h
0x140016420  mov     rax, cs:__security_cookie
0x140016427  xor     rax, rsp
0x14001642a  mov     [rbp+var_10], rax
0x14001642e  mov     r12, rcx
0x140016431  xor     esi, esi
0x140016433  xorps   xmm0, xmm0
0x140016436  movups  [rbp+var_50], xmm0
0x14001643a  lea     rax, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable'
0x140016441  mov     qword ptr [rbp+var_50], rax
0x140016445  mov     qword ptr [rbp+var_50+8], rsi
0x140016449  mov     [rbp+var_40], rsi
0x14001644d  lea     rdx, [rbp+var_50]
0x140016451  call    ?WULogFilesToList@CWUEtwConsumer@@IEAAJPEAV?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@@Z; CWUEtwConsumer::WULogFilesToList(CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>> *)
0x140016456  test    eax, eax
0x140016458  js      loc_140016530
0x14001645e  mov     r15d, dword ptr [rbp+var_40+4]
0x140016462  xor     edi, edi
0x140016464  test    r15d, r15d
0x140016467  jz      loc_140016530
0x14001646d  cmp     edi, dword ptr [rbp+var_40+4]
0x140016470  jnb     loc_140016521
0x140016476  mov     rax, qword ptr [rbp+var_50+8]
0x14001647a  mov     r14, [rax+rdi*8]
0x14001647e  xor     ebx, ebx
0x140016480  mov     [rbp+var_60], rbx
0x140016484  xorps   xmm0, xmm0
0x140016487  xor     eax, eax
0x140016489  movups  [rbp+FileInformation], xmm0
0x14001648d  movups  [rbp+var_28], xmm0
0x140016491  mov     [rbp+var_18], eax
0x140016494  test    r14, r14
0x140016497  jz      short loc_140016515
0x140016499  lea     r8, [rbp+FileInformation]; lpFileInformation
0x14001649d  xor     edx, edx; fInfoLevelId
0x14001649f  mov     rcx, r14; lpFileName
0x1400164a2  call    cs:__imp_GetFileAttributesExW
0x1400164a8  mov     eax, dword ptr [rbp+FileInformation]
0x1400164ab  cmp     eax, 0FFFFFFFFh
0x1400164ae  jz      short loc_140016515
0x1400164b0  bt      eax, 0Bh
0x1400164b4  jnb     short loc_140016501
0x1400164b6  mov     [rbp+FileSizeHigh], ebx
0x1400164b9  mov     [rbp+var_58], ebx
0x1400164bc  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x1400164c0  mov     rcx, r14; lpFileName
0x1400164c3  call    cs:__imp_GetCompressedFileSizeW
0x1400164c9  cmp     eax, 0FFFFFFFFh
0x1400164cc  jz      short loc_1400164DB
0x1400164ce  mov     dword ptr [rbp+var_60], eax
0x1400164d1  mov     eax, [rbp+FileSizeHigh]
0x1400164d4  mov     dword ptr [rbp+var_60+4], eax
0x1400164d7  mov     rbx, [rbp+var_60]
0x1400164db  lea     rdx, [rbp+var_58]; unsigned int *
0x1400164df  mov     rcx, r12; this
0x1400164e2  call    ?GetLogDriveSectorSize@CWUEtwConsumer@@IEAAJPEAK@Z; CWUEtwConsumer::GetLogDriveSectorSize(ulong *)
0x1400164e7  test    eax, eax
0x1400164e9  js      short loc_140016515
0x1400164eb  mov     ecx, [rbp+var_58]
0x1400164ee  dec     rbx
0x1400164f1  add     rbx, rcx
0x1400164f4  xor     edx, edx
0x1400164f6  mov     rax, rbx
0x1400164f9  div     rcx
0x1400164fc  sub     rbx, rdx
0x1400164ff  jmp     short loc_140016515
0x140016501  test    al, 10h
0x140016503  jnz     short loc_140016515
0x140016505  mov     eax, [rbp+var_18]
0x140016508  mov     dword ptr [rbp+var_60], eax
0x14001650b  mov     eax, dword ptr [rbp+var_28+0Ch]
0x14001650e  mov     dword ptr [rbp+var_60+4], eax
0x140016511  mov     rbx, [rbp+var_60]
0x140016515  lea     rax, [rbx+rsi]
0x140016519  cmp     rax, rsi
0x14001651c  jb      short loc_14001652E
0x14001651e  mov     rsi, rax
0x140016521  inc     edi
0x140016523  cmp     edi, r15d
0x140016526  jb      loc_14001646D
0x14001652c  jmp     short loc_140016530
0x14001652e  xor     esi, esi
0x140016530  lea     rcx, [rbp+var_50]
0x140016534  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(void)
0x140016539  mov     rax, rsi
0x14001653c  mov     rcx, [rbp+var_10]
0x140016540  xor     rcx, rsp; StackCookie
0x140016543  call    __security_check_cookie
0x140016548  lea     r11, [rsp+80h+var_s0]
0x140016550  mov     rbx, [r11+38h]
0x140016554  mov     rsi, [r11+40h]
0x140016558  mov     rsp, r11
0x14001655b  pop     r15
0x14001655d  pop     r14
0x14001655f  pop     r12
0x140016561  pop     rdi
0x140016562  pop     rbp
0x140016563  retn
```
