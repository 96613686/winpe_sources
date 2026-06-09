# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180011648`
- end: `0x180011a0c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `964`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180012da4`

## callees

- `0x180006b18`
- `0x18001133c`
- `0x180011648`
- `0x180011df8`
- `0x180012280`
- `0x180012b20`
- `0x18001393c`
- `0x180014f64`
- `0x180015dcc`
- `0x180016644`
- `0x18001899e`
- `0x1800189d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001187d`
- `KERNEL32!HeapFree` at `0x18001187d`
- `KERNEL32!GetProcessHeap` at `0x180011869`
- `KERNEL32!GetProcessHeap` at `0x180011869`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800116f4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800116f4`
- `KERNEL32!GetCurrentProcessId` at `0x180011681`
- `KERNEL32!GetCurrentProcessId` at `0x180011681`
- `KERNEL32!ReleaseMutex` at `0x180011785`
- `KERNEL32!ReleaseMutex` at `0x1800118a6`
- `KERNEL32!ReleaseMutex` at `0x18001195a`
- `KERNEL32!ReleaseMutex` at `0x180011785`
- `KERNEL32!ReleaseMutex` at `0x1800118a6`
- `KERNEL32!ReleaseMutex` at `0x18001195a`
- `KERNEL32!CreateMutexExW` at `0x1800116c7`
- `KERNEL32!CreateMutexExW` at `0x1800116c7`
- `KERNEL32!CloseHandle` at `0x1800117a3`
- `KERNEL32!CloseHandle` at `0x1800118c9`
- `KERNEL32!CloseHandle` at `0x18001197d`
- `KERNEL32!CloseHandle` at `0x1800117a3`
- `KERNEL32!CloseHandle` at `0x1800118c9`
- `KERNEL32!CloseHandle` at `0x18001197d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rsi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned int v24; // r8d
  _QWORD *v25; // rbx
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v43; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v44; // [rsp+48h] [rbp-B8h]
  void *v45; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v44 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v45 = v12;
  v42 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42);
  if ( 4 * v42 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_24;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  v42 = (unsigned __int64)v23;
  if ( v23 )
  {
    v43 = 0;
    v28 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v43, Name, v23);
    v26 = v28;
    if ( v28 >= 0 )
    {
      *(_DWORD *)v25 = 1;
      v25[1] = v6;
      v6 = 0;
      v44 = 0;
      v25[2] = v43;
      *(_QWORD *)&v43 = 0;
      v25[3] = *((_QWORD *)&v43 + 1);
      *((_QWORD *)&v43 + 1) = 0;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      *a2 = v25;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v43);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v43);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v41);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v26;
}

```

## disassembly

```asm
0x180011648  mov     [rsp-8+arg_10], rbx
0x18001164d  push    rbp
0x18001164e  push    rsi
0x18001164f  push    rdi
0x180011650  push    r14
0x180011652  push    r15
0x180011654  lea     rbp, [rsp-180h]
0x18001165c  sub     rsp, 280h
0x180011663  mov     rax, cs:__security_cookie
0x18001166a  xor     rax, rsp
0x18001166d  mov     [rbp+1A0h+var_30], rax
0x180011674  mov     r15, rdx
0x180011677  mov     rbx, rcx
0x18001167a  mov     qword ptr [rdx], 0
0x180011681  call    cs:__imp_GetCurrentProcessId
0x180011688  nop     dword ptr [rax+rax+00h]
0x18001168d  mov     r9d, eax
0x180011690  mov     [rsp+2A0h+var_278], rbx
0x180011695  mov     r14d, 78h ; 'x'
0x18001169b  mov     [rsp+2A0h+var_280], r14d; int
0x1800116a0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800116a7  mov     edx, 104h; unsigned __int64
0x1800116ac  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800116b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800116b6  nop
0x1800116b7  mov     r9d, 1F0001h; dwDesiredAccess
0x1800116bd  xor     r8d, r8d; dwFlags
0x1800116c0  lea     rdx, [rsp+2A0h+Name]; lpName
0x1800116c5  xor     ecx, ecx; lpMutexAttributes
0x1800116c7  call    cs:__imp_CreateMutexExW
0x1800116ce  nop     dword ptr [rax+rax+00h]
0x1800116d3  mov     rsi, rax
0x1800116d6  mov     [rsp+2A0h+var_258], rax
0x1800116db  test    rax, rax
0x1800116de  jnz     short loc_1800116EB
0x1800116e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800116e5  nop
0x1800116e6  jmp     loc_180011996
0x1800116eb  xor     r8d, r8d; bAlertable
0x1800116ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800116f1  mov     rcx, rsi; hHandle
0x1800116f4  call    cs:__imp_WaitForSingleObjectEx
0x1800116fb  nop     dword ptr [rax+rax+00h]
0x180011700  cmp     eax, 102h
0x180011705  jz      short loc_180011717
0x180011707  test    eax, 0FFFFFF7Fh
0x18001170c  jnz     loc_1800119C8
0x180011712  mov     rdi, rsi
0x180011715  jmp     short loc_180011719
0x180011717  xor     edi, edi
0x180011719  mov     [rsp+2A0h+var_250], rdi
0x18001171e  mov     [rsp+2A0h+var_270], 0
0x180011727  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x18001172c  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011731  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011736  mov     ebx, eax
0x180011738  test    eax, eax
0x18001173a  jns     loc_1800117C5
0x180011740  mov     rcx, [rbp+1A8h]; this
0x180011747  mov     r9d, eax; char *
0x18001174a  mov     edx, 66h ; 'f'; void *
0x18001174f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011754  mov     rcx, [rbp+1A8h]; this
0x18001175b  mov     r9d, ebx; char *
0x18001175e  mov     edx, 6Fh ; 'o'; void *
0x180011763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011768  mov     rcx, [rbp+1A8h]; this
0x18001176f  mov     r9d, ebx; char *
0x180011772  mov     edx, 12Eh; void *
0x180011777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001177c  nop
0x18001177d  test    rdi, rdi
0x180011780  jz      short loc_1800117A0
0x180011782  mov     rcx, rdi; hMutex
0x180011785  call    cs:__imp_ReleaseMutex
0x18001178c  nop     dword ptr [rax+rax+00h]
0x180011791  mov     rcx, [rbp+1A8h]; this
0x180011798  test    eax, eax
0x18001179a  jz      loc_1800119D5
0x1800117a0  mov     rcx, rsi; hObject
0x1800117a3  call    cs:__imp_CloseHandle
0x1800117aa  nop     dword ptr [rax+rax+00h]
0x1800117af  mov     rcx, [rbp+1A8h]; this
0x1800117b6  test    eax, eax
0x1800117b8  jz      loc_1800119E0
0x1800117be  mov     eax, ebx
0x1800117c0  jmp     loc_180011996
0x1800117c5  mov     rax, [rsp+2A0h+var_270]
0x1800117ca  lea     rcx, ds:0[rax*4]
0x1800117d2  test    rcx, rcx
0x1800117d5  jz      short loc_1800117E5
0x1800117d7  mov     [r15], rcx
0x1800117da  mov     eax, [rcx]
0x1800117dc  inc     eax
0x1800117de  mov     [rcx], eax
0x1800117e0  jmp     loc_180011952
0x1800117e5  mov     qword ptr [r15], 0
0x1800117ec  mov     rdx, r14; dwBytes
0x1800117ef  mov     ecx, 8; dwFlags
0x1800117f4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800117f9  mov     rbx, rax
0x1800117fc  mov     [rsp+2A0h+var_270], rax
0x180011801  test    rax, rax
0x180011804  jnz     short loc_180011823
0x180011806  mov     rcx, [rbp+1A8h]; this
0x18001180d  mov     r14d, 8007000Eh
0x180011813  mov     r9d, r14d; char *
0x180011816  mov     edx, 14Bh; void *
0x18001181b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011820  nop
0x180011821  jmp     short loc_180011889
0x180011823  xorps   xmm0, xmm0
0x180011826  movdqu  [rsp+2A0h+var_268], xmm0
0x18001182c  mov     r8, rbx; void *
0x18001182f  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011834  lea     rcx, [rsp+2A0h+var_268]; this
0x180011839  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18001183e  mov     r14d, eax
0x180011841  test    eax, eax
0x180011843  jns     loc_1800118EC
0x180011849  mov     rcx, [rbp+1A8h]; this
0x180011850  mov     r9d, eax; char *
0x180011853  mov     edx, 14Eh; void *
0x180011858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001185d  nop
0x18001185e  lea     rcx, [rsp+2A0h+var_268]; this
0x180011863  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011868  nop
0x180011869  call    cs:__imp_GetProcessHeap
0x180011870  nop     dword ptr [rax+rax+00h]
0x180011875  mov     rcx, rax; hHeap
0x180011878  mov     r8, rbx; lpMem
0x18001187b  xor     edx, edx; dwFlags
0x18001187d  call    cs:__imp_HeapFree
0x180011884  nop     dword ptr [rax+rax+00h]
0x180011889  mov     rcx, [rbp+1A8h]; this
0x180011890  mov     r9d, r14d; char *
0x180011893  mov     edx, 137h; void *
0x180011898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001189d  nop
0x18001189e  test    rdi, rdi
0x1800118a1  jz      short loc_1800118C1
0x1800118a3  mov     rcx, rdi; hMutex
0x1800118a6  call    cs:__imp_ReleaseMutex
0x1800118ad  nop     dword ptr [rax+rax+00h]
0x1800118b2  mov     rcx, [rbp+1A8h]; this
0x1800118b9  test    eax, eax
0x1800118bb  jz      loc_1800119EB
0x1800118c1  test    rsi, rsi
0x1800118c4  jz      short loc_1800118E4
0x1800118c6  mov     rcx, rsi; hObject
0x1800118c9  call    cs:__imp_CloseHandle
0x1800118d0  nop     dword ptr [rax+rax+00h]
0x1800118d5  mov     rcx, [rbp+1A8h]; this
0x1800118dc  test    eax, eax
0x1800118de  jz      loc_1800119F6
0x1800118e4  mov     eax, r14d
0x1800118e7  jmp     loc_180011996
0x1800118ec  mov     dword ptr [rbx], 1
0x1800118f2  mov     [rbx+8], rsi
0x1800118f6  xor     esi, esi
0x1800118f8  mov     [rsp+2A0h+var_258], rsi
0x1800118fd  mov     rax, qword ptr [rsp+2A0h+var_268]
0x180011902  mov     [rbx+10h], rax
0x180011906  mov     qword ptr [rsp+2A0h+var_268], rsi
0x18001190b  mov     rax, qword ptr [rsp+2A0h+var_268+8]
0x180011910  mov     [rbx+18h], rax
0x180011914  mov     qword ptr [rsp+2A0h+var_268+8], rsi
0x180011919  lea     rcx, [rbx+22h]; void *
0x18001191d  xor     edx, edx; Val
0x18001191f  lea     r8d, [rsi+56h]; Size
0x180011923  call    memset_0
0x180011928  mov     word ptr [rbx+20h], 58h ; 'X'
0x18001192e  mov     dword ptr [rbx+24h], 1
0x180011935  lea     rcx, [rbx+28h]; void *
0x180011939  xor     edx, edx; Val
0x18001193b  lea     r8d, [rsi+50h]; Size
0x18001193f  call    memset_0
0x180011944  mov     [r15], rbx
0x180011947  lea     rcx, [rsp+2A0h+var_268]; this
0x18001194c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011951  nop
0x180011952  test    rdi, rdi
0x180011955  jz      short loc_180011975
0x180011957  mov     rcx, rdi; hMutex
0x18001195a  call    cs:__imp_ReleaseMutex
0x180011961  nop     dword ptr [rax+rax+00h]
0x180011966  mov     rcx, [rbp+1A8h]; this
0x18001196d  test    eax, eax
0x18001196f  jz      loc_180011A01
0x180011975  test    rsi, rsi
0x180011978  jz      short loc_180011994
0x18001197a  mov     rcx, rsi; hObject
0x18001197d  call    cs:__imp_CloseHandle
0x180011984  nop     dword ptr [rax+rax+00h]
0x180011989  mov     rcx, [rbp+1A8h]; this
0x180011990  test    eax, eax
0x180011992  jz      short loc_1800119BD
0x180011994  xor     eax, eax
0x180011996  mov     rcx, [rbp+1A0h+var_30]
0x18001199d  xor     rcx, rsp; StackCookie
0x1800119a0  call    __security_check_cookie
0x1800119a5  mov     rbx, [rsp+2A0h+arg_10]
0x1800119ad  add     rsp, 280h
0x1800119b4  pop     r15
0x1800119b6  pop     r14
0x1800119b8  pop     rdi
0x1800119b9  pop     rsi
0x1800119ba  pop     rbp
0x1800119bb  retn
0x1800119bd  mov     edx, 0A0Bh; void *
0x1800119c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800119c8  mov     rcx, [rbp+1A8h]; this
0x1800119cf  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800119d5  mov     edx, 0A15h; void *
0x1800119da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800119e0  mov     edx, 0A0Bh; void *
0x1800119e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800119eb  mov     edx, 0A15h; void *
0x1800119f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800119f6  mov     edx, 0A0Bh; void *
0x1800119fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a01  mov     edx, 0A15h; void *
0x180011a06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
