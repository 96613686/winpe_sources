# PerfObjectDefinition::Init(PerfLibrary *)

- ea: `0x180147b7c`
- end: `0x180147eb1`
- name: `?Init@PerfObjectDefinition@@AEAAHPEAVPerfLibrary@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(PerfObjectDefinition *__hidden this, struct PerfLibrary *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180065834`

## callees

- `0x18003b678`
- `0x18008facc`
- `0x1800f3e64`
- `0x18010bb54`
- `0x180147b7c`
- `0x180147eb8`
- `0x1801480fc`
- `0x180161f18`
- `0x18016a068`
- `0x180188d90`
- `0x180189cce`
- `0x1801ba09c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180147cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180147d39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180147cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180147d39`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180147d20`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180147d20`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180147c4c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180147c4c`

## string_xrefs

- `0x180147c85`: `[PerfCounter] MSFTESQL: cannot create share "%ls" it already exists. 0x%08x`
- `0x180147cd4`: `[PerfCounter] MSFTESQL: cannot create share "%ls" it already exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PerfObjectDefinition::Init(HANDLE *this, struct PerfLibrary *a2)
{
  int v4; // eax
  int v5; // eax
  DWORD v6; // edi
  __int64 MemShareName; // rax
  HANDLE v8; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  const wchar_t *Buffer; // rax
  const wchar_t *v13; // rax
  void *v14; // rax
  unsigned int v15; // edi
  _DWORD *v16; // rdx
  __int64 v17; // rcx
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v19[72]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+78h] [rbp-88h] BYREF
  void **v21; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpName; // [rsp+A8h] [rbp-58h]
  __int64 v23; // [rsp+B0h] [rbp-50h]
  __int16 v24; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v25[160]; // [rsp+140h] [rbp+40h] BYREF

  PerfObjectDefinition::DoInitCalculations((PerfObjectDefinition *)this);
  v4 = *((_DWORD *)this + 9);
  if ( v4 == -1 )
    v5 = *((_DWORD *)this + 524);
  else
    v5 = *((_DWORD *)this + 525) * v4;
  v6 = *((_DWORD *)this + 523) + v5;
  CPerfMonSecurityAttributes::CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v19);
  lpName = (LPCWSTR)&v24;
  v23 = 65;
  v24 = 0;
  v21 = &CCICommonPathString::`vftable';
  MemShareName = CreateMemShareName((CLMString *)v25, (wchar_t *)this);
  CLMString::operator=(&v21, *(_QWORD *)(MemShareName + 8));
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v25);
  FileMappingAttributes.lpSecurityDescriptor = v19;
  v8 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, v6, lpName);
  this[263] = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    Buffer = CLMString::GetBuffer((CLMString *)&v21, 0);
    dwMaximumSizeLow[0] = v10;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x197,
      (unsigned int)L"[PerfCounter] MSFTESQL: cannot create share \"%ls\" it already exists. 0x%08x",
      Buffer,
      *(_QWORD *)dwMaximumSizeLow);
    goto LABEL_8;
  }
  if ( GetLastError() == 183 )
  {
    v13 = CLMString::GetBuffer((CLMString *)&v21, 0);
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x19E,
      (unsigned int)L"[PerfCounter] MSFTESQL: cannot create share \"%ls\" it already exists.",
      v13);
    CloseHandle(this[263]);
    this[263] = 0;
LABEL_8:
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v21);
    CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v19);
    return 0;
  }
  v14 = MapViewOfFile(this[263], 2u, 0, 0, 0);
  this[264] = v14;
  if ( v14 )
  {
    memset_0(v14, 0, v6);
    v16 = this[264];
    this[265] = v16;
    this[266] = v16 + 16;
    v17 = *((unsigned int *)this + 523);
    this[267] = (char *)v16 + v17;
    *v16 = v17 - 8;
    *((_DWORD *)this[265] + 1) = *((_DWORD *)this + 523) - 8;
    *((_DWORD *)this[265] + 2) = 64;
    *((_DWORD *)this[265] + 3) = *((_DWORD *)this + 8) + *((_DWORD *)a2 + 67);
    *((_DWORD *)this[265] + 4) = 0;
    *((_DWORD *)this[265] + 5) = *((_DWORD *)this + 8) + *((_DWORD *)a2 + 66);
    *((_DWORD *)this[265] + 6) = 0;
    *((_DWORD *)this[265] + 7) = 100;
    *((_DWORD *)this[265] + 8) = *((_DWORD *)this + 522);
    *((_DWORD *)this[265] + 11) = -1;
    *((_DWORD *)this[265] + 9) = 0;
    v15 = 1;
    *((_DWORD *)this[265] + 10) = (*((_DWORD *)this + 9) != -1) - 1;
    *(_DWORD *)((char *)this[264] + *((unsigned int *)this + 523) - 8) = *((_DWORD *)this + 524);
    *(_DWORD *)((char *)this[264] + *((unsigned int *)this + 523) - 4) = *((_DWORD *)this + 9);
    PerfObjectDefinition::InitCounters((PerfObjectDefinition *)this, a2);
  }
  else
  {
    CloseHandle(this[263]);
    v15 = 0;
  }
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v21);
  CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v19);
  return v15;
}

```

## disassembly

```asm
0x180147b7c  mov     [rsp-8+arg_10], rbx
0x180147b81  push    rbp
0x180147b82  push    rsi
0x180147b83  push    rdi
0x180147b84  lea     rbp, [rsp-0F0h]
0x180147b8c  sub     rsp, 1F0h
0x180147b93  mov     rax, cs:__security_cookie
0x180147b9a  xor     rax, rsp
0x180147b9d  mov     [rbp+100h+var_20], rax
0x180147ba4  mov     rsi, rdx
0x180147ba7  mov     rbx, rcx
0x180147baa  call    ?DoInitCalculations@PerfObjectDefinition@@AEAAXXZ; PerfObjectDefinition::DoInitCalculations(void)
0x180147baf  mov     eax, [rbx+24h]
0x180147bb2  mov     ecx, [rbx+82Ch]
0x180147bb8  cmp     eax, 0FFFFFFFFh
0x180147bbb  jnz     short loc_180147BC5
0x180147bbd  mov     eax, [rbx+830h]
0x180147bc3  jmp     short loc_180147BCC
0x180147bc5  imul    eax, [rbx+834h]
0x180147bcc  lea     edi, [rcx+rax]
0x180147bcf  lea     rcx, [rsp+200h+var_1D0]; this
0x180147bd4  call    ??0CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::CPerfMonSecurityAttributes(void)
0x180147bd9  nop
0x180147bda  lea     rax, [rbp+100h+var_148]
0x180147bde  mov     [rbp+100h+var_158], rax
0x180147be2  mov     [rbp+100h+var_150], 41h ; 'A'
0x180147bea  xor     eax, eax
0x180147bec  mov     [rbp+100h+var_148], ax
0x180147bf0  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x180147bf7  mov     [rbp+100h+var_160], rax
0x180147bfb  lea     r9, psz
0x180147c02  mov     rdx, rbx; wchar_t *
0x180147c05  lea     rcx, [rbp+100h+var_C0]; this
0x180147c09  call    ?CreateMemShareName@@YA?AV?$TLMString@$0EA@$0EA@$0HPPP@@@PEB_W00@Z; CreateMemShareName(wchar_t const *,wchar_t const *,wchar_t const *)
0x180147c0e  nop
0x180147c0f  mov     rdx, [rax+8]
0x180147c13  lea     rcx, [rbp+100h+var_160]
0x180147c17  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180147c1c  nop
0x180147c1d  lea     rcx, [rbp+100h+var_C0]
0x180147c21  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180147c26  lea     rax, [rsp+200h+var_1D0]
0x180147c2b  mov     [rbp+100h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180147c2f  mov     rax, [rbp+100h+var_158]
0x180147c33  mov     [rsp+200h+lpName], rax; lpName
0x180147c38  mov     [rsp+200h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180147c3c  xor     r9d, r9d; dwMaximumSizeHigh
0x180147c3f  lea     r8d, [r9+4]; flProtect
0x180147c43  lea     rdx, [rsp+200h+FileMappingAttributes]; lpFileMappingAttributes
0x180147c48  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180147c4c  call    cs:__imp_CreateFileMappingW
0x180147c52  mov     [rbx+838h], rax
0x180147c59  test    rax, rax
0x180147c5c  jnz     short loc_180147CB9
0x180147c5e  call    cs:__imp_GetLastError
0x180147c64  mov     ebx, eax
0x180147c66  test    eax, eax
0x180147c68  jle     short loc_180147C73
0x180147c6a  movzx   ebx, ax
0x180147c6d  or      ebx, 80070000h
0x180147c73  xor     edx, edx; int
0x180147c75  lea     rcx, [rbp+100h+var_160]; this
0x180147c79  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180147c7e  mov     [rsp+200h+dwMaximumSizeLow], ebx
0x180147c82  mov     r9, rax; wchar_t *
0x180147c85  lea     r8, aPerfcounterMsf_9; "[PerfCounter] MSFTESQL: cannot create s"...
0x180147c8c  mov     edx, 197h; wchar_t *
0x180147c91  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180147c98  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180147c9d  nop
0x180147c9e  lea     rcx, [rbp+100h+var_160]
0x180147ca2  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180147ca7  nop
0x180147ca8  lea     rcx, [rsp+200h+var_1D0]; this
0x180147cad  call    ??1CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes(void)
0x180147cb2  xor     eax, eax
0x180147cb4  jmp     loc_180147E8F
0x180147cb9  call    cs:__imp_GetLastError
0x180147cbf  cmp     eax, 0B7h
0x180147cc4  jnz     short loc_180147D06
0x180147cc6  xor     edx, edx; int
0x180147cc8  lea     rcx, [rbp+100h+var_160]; this
0x180147ccc  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180147cd1  mov     r9, rax; wchar_t *
0x180147cd4  lea     r8, aPerfcounterMsf_1; "[PerfCounter] MSFTESQL: cannot create s"...
0x180147cdb  mov     edx, 19Eh; wchar_t *
0x180147ce0  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180147ce7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180147cec  mov     rcx, [rbx+838h]; hObject
0x180147cf3  call    cs:__imp_CloseHandle
0x180147cf9  mov     qword ptr [rbx+838h], 0
0x180147d04  jmp     short loc_180147C9E
0x180147d06  mov     qword ptr [rsp+200h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180147d0f  xor     r9d, r9d; dwFileOffsetLow
0x180147d12  xor     r8d, r8d; dwFileOffsetHigh
0x180147d15  lea     edx, [r9+2]; dwDesiredAccess
0x180147d19  mov     rcx, [rbx+838h]; hFileMappingObject
0x180147d20  call    cs:__imp_MapViewOfFile
0x180147d26  mov     [rbx+840h], rax
0x180147d2d  test    rax, rax
0x180147d30  jnz     short loc_180147D46
0x180147d32  mov     rcx, [rbx+838h]; hObject
0x180147d39  call    cs:__imp_CloseHandle
0x180147d3f  xor     edi, edi
0x180147d41  jmp     loc_180147E79
0x180147d46  mov     r8d, edi; Size
0x180147d49  xor     edx, edx; Val
0x180147d4b  mov     rcx, rax; void *
0x180147d4e  call    memset_0
0x180147d53  mov     rdx, [rbx+840h]
0x180147d5a  mov     [rbx+848h], rdx
0x180147d61  lea     rax, [rdx+40h]
0x180147d65  mov     [rbx+850h], rax
0x180147d6c  mov     ecx, [rbx+82Ch]
0x180147d72  lea     rax, [rdx+rcx]
0x180147d76  mov     [rbx+858h], rax
0x180147d7d  lea     eax, [rcx-8]
0x180147d80  mov     [rdx], eax
0x180147d82  mov     ecx, [rbx+82Ch]
0x180147d88  sub     ecx, 8
0x180147d8b  mov     rax, [rbx+848h]
0x180147d92  mov     [rax+4], ecx
0x180147d95  mov     rax, [rbx+848h]
0x180147d9c  mov     dword ptr [rax+8], 40h ; '@'
0x180147da3  mov     ecx, [rsi+10Ch]
0x180147da9  add     ecx, [rbx+20h]
0x180147dac  mov     rax, [rbx+848h]
0x180147db3  mov     [rax+0Ch], ecx
0x180147db6  mov     rax, [rbx+848h]
0x180147dbd  mov     dword ptr [rax+10h], 0
0x180147dc4  mov     ecx, [rsi+108h]
0x180147dca  add     ecx, [rbx+20h]
0x180147dcd  mov     rax, [rbx+848h]
0x180147dd4  mov     [rax+14h], ecx
0x180147dd7  mov     rax, [rbx+848h]
0x180147dde  mov     dword ptr [rax+18h], 0
0x180147de5  mov     rax, [rbx+848h]
0x180147dec  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x180147df3  mov     rcx, [rbx+848h]
0x180147dfa  mov     eax, [rbx+828h]
0x180147e00  mov     [rcx+20h], eax
0x180147e03  mov     rax, [rbx+848h]
0x180147e0a  mov     dword ptr [rax+2Ch], 0FFFFFFFFh
0x180147e11  mov     rax, [rbx+848h]
0x180147e18  mov     dword ptr [rax+24h], 0
0x180147e1f  xor     r8d, r8d
0x180147e22  cmp     dword ptr [rbx+24h], 0FFFFFFFFh
0x180147e26  setnz   r8b
0x180147e2a  mov     edi, 1
0x180147e2f  sub     r8d, edi
0x180147e32  mov     rax, [rbx+848h]
0x180147e39  mov     [rax+28h], r8d
0x180147e3d  mov     r9d, [rbx+82Ch]
0x180147e44  mov     r8, [rbx+840h]
0x180147e4b  mov     eax, [rbx+830h]
0x180147e51  mov     [r9+r8-8], eax
0x180147e56  mov     r10d, [rbx+82Ch]
0x180147e5d  mov     r9, [rbx+840h]
0x180147e64  mov     r8d, [rbx+24h]
0x180147e68  mov     [r10+r9-4], r8d
0x180147e6d  mov     rdx, rsi; struct PerfLibrary *
0x180147e70  mov     rcx, rbx; this
0x180147e73  call    ?InitCounters@PerfObjectDefinition@@AEAAXPEAVPerfLibrary@@@Z; PerfObjectDefinition::InitCounters(PerfLibrary *)
0x180147e78  nop
0x180147e79  lea     rcx, [rbp+100h+var_160]
0x180147e7d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180147e82  nop
0x180147e83  lea     rcx, [rsp+200h+var_1D0]; this
0x180147e88  call    ??1CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes(void)
0x180147e8d  mov     eax, edi
0x180147e8f  mov     rcx, [rbp+100h+var_20]
0x180147e96  xor     rcx, rsp; StackCookie
0x180147e99  call    __security_check_cookie
0x180147e9e  mov     rbx, [rsp+200h+arg_10]
0x180147ea6  add     rsp, 1F0h
0x180147ead  pop     rdi
0x180147eae  pop     rsi
0x180147eaf  pop     rbp
0x180147eb0  retn
```
