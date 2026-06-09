# shared::get_full_path_name(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1400637e4`
- end: `0x140063935`
- name: `?get_full_path_name@shared@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z`
- size: `337`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140045a4c`

## callees

- `0x140006061`
- `0x140007404`
- `0x140018bec`
- `0x140019da0`
- `0x14001a08c`
- `0x140039dfc`
- `0x1400637e4`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x140063825`
- `KERNEL32!GetFullPathNameW` at `0x14006386c`
- `KERNEL32!GetFullPathNameW` at `0x140063825`
- `KERNEL32!GetFullPathNameW` at `0x14006386c`
- `KERNEL32!GetLastError` at `0x1400638b0`
- `KERNEL32!GetLastError` at `0x1400638b0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063887`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063887`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall shared::get_full_path_name(const WCHAR *lpFileName, __int64 a2)
{
  const WCHAR *v4; // rcx
  DWORD FullPathNameW; // eax
  __int64 v6; // r8
  LPWSTR v7; // r9
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rbx
  __int64 v11; // rdi
  unsigned __int64 v12; // rdx
  char *v13; // rsi
  __int64 v14; // rbx
  LPWSTR lpBuffer; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h]

  std::vector<wchar_t>::vector<wchar_t>(&lpBuffer, 260);
  if ( *((_QWORD *)lpFileName + 3) <= 7u )
    v4 = lpFileName;
  else
    v4 = *(const WCHAR **)lpFileName;
  FullPathNameW = GetFullPathNameW(v4, (v17 - (__int64)lpBuffer) >> 1, lpBuffer, 0);
  v7 = lpBuffer;
  if ( FullPathNameW >= (unsigned __int64)((v17 - (__int64)lpBuffer) >> 1) )
  {
    std::vector<wchar_t>::resize(&lpBuffer);
    if ( *((_QWORD *)lpFileName + 3) > 7u )
      lpFileName = *(const WCHAR **)lpFileName;
    FullPathNameW = GetFullPathNameW(lpFileName, (v17 - (__int64)lpBuffer) >> 1, lpBuffer, 0);
    v7 = lpBuffer;
  }
  if ( FullPathNameW )
  {
    v12 = -1;
    do
      ++v12;
    while ( v7[v12] );
    if ( v12 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>((char **)a2, v12, v6, v7);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v13 = (char *)a2;
      else
        v13 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v12;
      v14 = 2 * v12;
      memmove_0(v13, v7, 2 * v12);
      *(_WORD *)&v13[v14] = 0;
    }
    v11 = 0x8000000000LL;
  }
  else
  {
    v8 = strrchr("admin\\appman\\appv\\shared\\system\\file_utils.cpp", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\shared\\system\\file_utils.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = (FileId << 52) | GetLastError() | 0x252500000000LL;
  }
  std::vector<wchar_t>::~vector<wchar_t>((char **)&lpBuffer);
  return v11;
}

```

## disassembly

```asm
0x1400637e4  push    rbx
0x1400637e6  push    rbp
0x1400637e7  push    rsi
0x1400637e8  push    rdi
0x1400637e9  sub     rsp, 48h
0x1400637ed  mov     rdi, rdx
0x1400637f0  mov     rbx, rcx
0x1400637f3  mov     edx, 104h
0x1400637f8  lea     rcx, [rsp+68h+lpBuffer]
0x1400637fd  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140063802  nop
0x140063803  mov     r8, [rsp+68h+lpBuffer]; lpBuffer
0x140063808  mov     rdx, [rsp+68h+var_40]
0x14006380d  sub     rdx, r8
0x140063810  sar     rdx, 1; nBufferLength
0x140063813  cmp     qword ptr [rbx+18h], 7
0x140063818  jbe     short loc_14006381F
0x14006381a  mov     rcx, [rbx]
0x14006381d  jmp     short loc_140063822
0x14006381f  mov     rcx, rbx; lpFileName
0x140063822  xor     r9d, r9d; lpFilePart
0x140063825  call    cs:__imp_GetFullPathNameW
0x14006382b  mov     edx, eax
0x14006382d  mov     rcx, [rsp+68h+var_40]
0x140063832  mov     r9, [rsp+68h+lpBuffer]
0x140063837  sub     rcx, r9
0x14006383a  sar     rcx, 1
0x14006383d  cmp     rdx, rcx
0x140063840  jb      short loc_140063877
0x140063842  lea     rcx, [rsp+68h+lpBuffer]
0x140063847  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x14006384c  mov     r8, [rsp+68h+lpBuffer]; lpBuffer
0x140063851  mov     rdx, [rsp+68h+var_40]
0x140063856  sub     rdx, r8
0x140063859  sar     rdx, 1; nBufferLength
0x14006385c  cmp     qword ptr [rbx+18h], 7
0x140063861  jbe     short loc_140063866
0x140063863  mov     rbx, [rbx]
0x140063866  xor     r9d, r9d; lpFilePart
0x140063869  mov     rcx, rbx; lpFileName
0x14006386c  call    cs:__imp_GetFullPathNameW
0x140063872  mov     r9, [rsp+68h+lpBuffer]
0x140063877  xor     ebp, ebp
0x140063879  test    eax, eax
0x14006387b  jnz     short loc_1400638CE
0x14006387d  lea     edx, [rbp+5Ch]; Ch
0x140063880  lea     rcx, aAdminAppmanApp_5; "admin\\appman\\appv\\shared\\system\\fi"...
0x140063887  call    cs:__imp_strrchr
0x14006388d  test    rax, rax
0x140063890  jz      short loc_140063897
0x140063892  inc     rax
0x140063895  jmp     short loc_14006389E
0x140063897  lea     rax, aAdminAppmanApp_5; "admin\\appman\\appv\\shared\\system\\fi"...
0x14006389e  mov     rdx, rax; char *
0x1400638a1  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400638a8  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400638ad  mov     rbx, rax
0x1400638b0  call    cs:__imp_GetLastError
0x1400638b6  mov     edi, eax
0x1400638b8  shl     rbx, 34h
0x1400638bc  or      rdi, rbx
0x1400638bf  mov     rax, 252500000000h
0x1400638c9  or      rdi, rax
0x1400638cc  jmp     short loc_14006391F
0x1400638ce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400638d2  inc     rdx
0x1400638d5  cmp     [r9+rdx*2], bp
0x1400638da  jnz     short loc_1400638D2
0x1400638dc  cmp     rdx, [rdi+18h]
0x1400638e0  ja      short loc_14006390D
0x1400638e2  cmp     qword ptr [rdi+18h], 7
0x1400638e7  jbe     short loc_1400638EE
0x1400638e9  mov     rsi, [rdi]
0x1400638ec  jmp     short loc_1400638F1
0x1400638ee  mov     rsi, rdi
0x1400638f1  mov     [rdi+10h], rdx
0x1400638f5  lea     rbx, [rdx+rdx]
0x1400638f9  mov     r8, rbx; Size
0x1400638fc  mov     rdx, r9; Src
0x1400638ff  mov     rcx, rsi; void *
0x140063902  call    memmove_0
0x140063907  mov     [rbx+rsi], bp
0x14006390b  jmp     short loc_140063915
0x14006390d  mov     rcx, rdi
0x140063910  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140063915  mov     rdi, 8000000000h
0x14006391f  lea     rcx, [rsp+68h+lpBuffer]
0x140063924  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063929  mov     rax, rdi
0x14006392c  add     rsp, 48h
0x140063930  pop     rdi
0x140063931  pop     rsi
0x140063932  pop     rbp
0x140063933  pop     rbx
0x140063934  retn
```
