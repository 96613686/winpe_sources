# CLogger::RollOver(void)

- ea: `0x180038c10`
- end: `0x180038d4a`
- name: `?RollOver@CLogger@@AEAAHXZ`
- size: `314`
- prototype: `__int64 __fastcall(CLogger *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180038dd0`

## callees

- `0x18000e6e0`
- `0x18000ee70`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x180038018`
- `0x1800380cc`
- `0x180038730`
- `0x18003886c`
- `0x180038c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038d2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038d08`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180038d19`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180038d19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLogger::RollOver(CLogger *this)
{
  __int64 v2; // rdx
  int *v3; // rdi
  __int64 v4; // rbx
  _QWORD *v5; // rax
  void *v6; // rcx
  LPCWSTR v7; // rbx
  unsigned int v8; // edi
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp+30h] BYREF
  char v11; // [rsp+58h] [rbp+38h] BYREF
  __int64 v12; // [rsp+60h] [rbp+40h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ATL::CTime::GetTickCount(&v11);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&lpNewFileName);
  v2 = *((_QWORD *)this + 3);
  v3 = (int *)(lpNewFileName - 12);
  if ( (LPCWSTR)(v2 - 24) != lpNewFileName - 12 )
  {
    if ( v3[4] >= 0 && *(_QWORD *)(v2 - 24) == *(_QWORD *)v3 )
    {
      v4 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v3);
      lpNewFileName = (LPCWSTR)(v4 + 24);
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(&lpNewFileName, v2, *(unsigned int *)(v2 - 16));
    }
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, "\\");
  ATL::CSimpleStringT<wchar_t,0>::Append(
    &lpNewFileName,
    *((_QWORD *)this + 1),
    *(unsigned int *)(*((_QWORD *)this + 1) - 16LL));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, ".to-");
  v5 = (_QWORD *)ATL::CTime::Format(&v11, &v12, L"%Y-%m-%d-%H.%M.%S");
  ATL::CSimpleStringT<wchar_t,0>::Append(&lpNewFileName, *v5, *(unsigned int *)(*v5 - 16LL));
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(&lpNewFileName, ".txt");
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = -1;
  CloseHandle(v6);
  v7 = lpNewFileName;
  MoveFileW(*((LPCWSTR *)this + 4), lpNewFileName);
  v8 = CLogger::Open(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
  return v8;
}

```

## disassembly

```asm
0x180038c10  push    rbp
0x180038c12  push    rbx
0x180038c13  push    rsi
0x180038c14  push    rdi
0x180038c15  push    r14
0x180038c17  mov     rbp, rsp
0x180038c1a  sub     rsp, 20h
0x180038c1e  mov     rsi, rcx
0x180038c21  add     rcx, 48h ; 'H'; lpCriticalSection
0x180038c25  call    cs:__imp_EnterCriticalSection
0x180038c2b  lea     rcx, [rbp+arg_8]
0x180038c2f  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180038c34  lea     rcx, [rbp+lpNewFileName]
0x180038c38  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180038c3d  nop
0x180038c3e  mov     rdx, [rsi+18h]
0x180038c42  lea     rcx, [rdx-18h]
0x180038c46  mov     rdi, [rbp+lpNewFileName]
0x180038c4a  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180038c4e  cmp     rcx, rdi
0x180038c51  jz      short loc_180038C88
0x180038c53  cmp     dword ptr [rdi+10h], 0
0x180038c57  jl      short loc_180038C7B
0x180038c59  mov     rax, [rdi]
0x180038c5c  cmp     [rcx], rax
0x180038c5f  jnz     short loc_180038C7B
0x180038c61  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180038c66  mov     rbx, rax
0x180038c69  mov     rcx, rdi; this
0x180038c6c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038c71  lea     rax, [rbx+18h]
0x180038c75  mov     [rbp+lpNewFileName], rax
0x180038c79  jmp     short loc_180038C88
0x180038c7b  mov     r8d, [rdx-10h]
0x180038c7f  lea     rcx, [rbp+lpNewFileName]
0x180038c83  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180038c88  lea     rdx, asc_18004C1CC; "\\"
0x180038c8f  lea     rcx, [rbp+lpNewFileName]
0x180038c93  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038c98  mov     rdx, [rsi+8]
0x180038c9c  mov     r8d, [rdx-10h]
0x180038ca0  lea     rcx, [rbp+lpNewFileName]
0x180038ca4  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180038ca9  lea     rdx, aTo; ".to-"
0x180038cb0  lea     rcx, [rbp+lpNewFileName]
0x180038cb4  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038cb9  lea     r8, aYMDHMS; "%Y-%m-%d-%H.%M.%S"
0x180038cc0  lea     rdx, [rbp+arg_10]
0x180038cc4  lea     rcx, [rbp+arg_8]
0x180038cc8  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@PEB_W@Z; ATL::CTime::Format(wchar_t const *)
0x180038ccd  nop
0x180038cce  mov     rdx, [rax]
0x180038cd1  mov     r8d, [rdx-10h]
0x180038cd5  lea     rcx, [rbp+lpNewFileName]
0x180038cd9  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180038cde  nop
0x180038cdf  mov     rcx, [rbp+arg_10]
0x180038ce3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038ce7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038cec  lea     rdx, aTxt_1; ".txt"
0x180038cf3  lea     rcx, [rbp+lpNewFileName]
0x180038cf7  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038cfc  mov     rcx, [rsi+30h]; hObject
0x180038d00  mov     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x180038d08  call    cs:__imp_CloseHandle
0x180038d0e  mov     rbx, [rbp+lpNewFileName]
0x180038d12  mov     rdx, rbx; lpNewFileName
0x180038d15  mov     rcx, [rsi+20h]; lpExistingFileName
0x180038d19  call    cs:__imp_MoveFileW
0x180038d1f  mov     rcx, rsi; this
0x180038d22  call    ?Open@CLogger@@QEAAHXZ; CLogger::Open(void)
0x180038d27  mov     edi, eax
0x180038d29  lea     rcx, [rsi+48h]; lpCriticalSection
0x180038d2d  call    cs:__imp_LeaveCriticalSection
0x180038d33  nop
0x180038d34  lea     rcx, [rbx-18h]; this
0x180038d38  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038d3d  mov     eax, edi
0x180038d3f  add     rsp, 20h
0x180038d43  pop     r14
0x180038d45  pop     rdi
0x180038d46  pop     rsi
0x180038d47  pop     rbx
0x180038d48  pop     rbp
0x180038d49  retn
```
