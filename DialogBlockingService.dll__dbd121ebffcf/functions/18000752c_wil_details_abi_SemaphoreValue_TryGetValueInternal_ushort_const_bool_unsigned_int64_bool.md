# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000752c`
- end: `0x1800077bb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800046d8`

## callees

- `0x180001620`
- `0x1800059a8`
- `0x1800067e4`
- `0x180006804`
- `0x180007200`
- `0x18000752c`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800075c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000763c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800075c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000763c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000767f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000767f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076fa`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000752c  push    rbp
0x18000752e  push    rbx
0x18000752f  push    rsi
0x180007530  push    rdi
0x180007531  push    r14
0x180007533  push    r15
0x180007535  lea     rbp, [rsp-158h]
0x18000753d  sub     rsp, 258h
0x180007544  mov     rax, cs:__security_cookie
0x18000754b  xor     rax, rsp
0x18000754e  mov     [rbp+180h+var_40], rax
0x180007555  xor     r15d, r15d
0x180007558  lea     rax, [rsp+280h+Name]
0x18000755d  mov     [r8], r15
0x180007560  mov     r14, r8
0x180007563  mov     edx, 104h
0x180007568  mov     r9d, 7FFFFFFEh
0x18000756e  test    r9, r9
0x180007571  jz      short loc_180007592
0x180007573  movzx   r8d, word ptr [rcx]
0x180007577  test    r8w, r8w
0x18000757b  jz      short loc_180007592
0x18000757d  mov     [rax], r8w
0x180007581  add     rcx, 2
0x180007585  add     rax, 2
0x180007589  dec     r9
0x18000758c  sub     rdx, 1; unsigned __int64
0x180007590  jnz     short loc_18000756E
0x180007592  test    rdx, rdx
0x180007595  lea     rcx, [rax-2]
0x180007599  lea     r8, aP0; "_p0"
0x1800075a0  cmovnz  rcx, rax
0x1800075a4  mov     [rcx], r15w
0x1800075a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800075ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800075b2  mov     esi, 1F0003h
0x1800075b7  lea     r8, [rsp+280h+Name]; lpName
0x1800075bc  mov     ecx, esi; dwDesiredAccess
0x1800075be  xor     edx, edx; bInheritHandle
0x1800075c0  call    cs:__imp_OpenSemaphoreW
0x1800075c6  mov     rbx, rax
0x1800075c9  test    rax, rax
0x1800075cc  jz      loc_180007709
0x1800075d2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800075d7  mov     [rsp+280h+var_25C], r15d
0x1800075dc  mov     rcx, rax; hHandle
0x1800075df  mov     [rsp+280h+var_260], r15d; int
0x1800075e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800075e9  mov     edi, eax
0x1800075eb  test    eax, eax
0x1800075ed  jns     short loc_180007622
0x1800075ef  mov     rcx, [rbp+188h]; this
0x1800075f6  lea     r8, aWil; "wil"
0x1800075fd  mov     r9d, eax; char *
0x180007600  mov     edx, 0D6h; void *
0x180007605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000760a  mov     rcx, rbx; hObject
0x18000760d  call    cs:__imp_CloseHandle
0x180007613  test    eax, eax
0x180007615  jz      loc_180007785
0x18000761b  mov     eax, edi
0x18000761d  jmp     loc_180007730
0x180007622  lea     r8, asc_180010110; "h"
0x180007629  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000762e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007633  lea     r8, [rsp+280h+Name]; lpName
0x180007638  xor     edx, edx; bInheritHandle
0x18000763a  mov     ecx, esi; dwDesiredAccess
0x18000763c  call    cs:__imp_OpenSemaphoreW
0x180007642  mov     rdi, rax
0x180007645  test    rax, rax
0x180007648  jz      loc_1800076DD
0x18000764e  lea     rdx, [rsp+280h+var_260]; int *
0x180007653  mov     rcx, rax; hHandle
0x180007656  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000765b  mov     esi, eax
0x18000765d  test    eax, eax
0x18000765f  jns     short loc_1800076A5
0x180007661  mov     rcx, [rbp+188h]; this
0x180007668  lea     r8, aWil; "wil"
0x18000766f  mov     r9d, eax; char *
0x180007672  mov     edx, 0DEh; void *
0x180007677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000767c  mov     rcx, rdi; hObject
0x18000767f  call    cs:__imp_CloseHandle
0x180007685  test    eax, eax
0x180007687  jz      loc_180007797
0x18000768d  mov     rcx, rbx; hObject
0x180007690  call    cs:__imp_CloseHandle
0x180007696  test    eax, eax
0x180007698  jz      loc_1800077A9
0x18000769e  mov     eax, esi
0x1800076a0  jmp     loc_180007730
0x1800076a5  mov     rcx, rdi; hObject
0x1800076a8  call    cs:__imp_CloseHandle
0x1800076ae  test    eax, eax
0x1800076b0  jz      loc_18000774F
0x1800076b6  movsxd  rax, [rsp+280h+var_25C]
0x1800076bb  movsxd  rcx, [rsp+280h+var_260]
0x1800076c0  shl     rcx, 1Fh
0x1800076c4  or      rcx, rax
0x1800076c7  mov     [r14], rcx
0x1800076ca  mov     rcx, rbx; hObject
0x1800076cd  call    cs:__imp_CloseHandle
0x1800076d3  test    eax, eax
0x1800076d5  jz      loc_180007761
0x1800076db  jmp     short loc_180007714
0x1800076dd  mov     rcx, [rbp+188h]; this
0x1800076e4  lea     r8, aWil; "wil"
0x1800076eb  mov     edx, 0DCh; void *
0x1800076f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800076f5  mov     rcx, rbx; hObject
0x1800076f8  mov     edi, eax
0x1800076fa  call    cs:__imp_CloseHandle
0x180007700  test    eax, eax
0x180007702  jz      short loc_180007773
0x180007704  jmp     loc_18000761B
0x180007709  call    cs:__imp_GetLastError
0x18000770f  cmp     eax, 2
0x180007712  jnz     short loc_180007718
0x180007714  xor     eax, eax
0x180007716  jmp     short loc_180007730
0x180007718  mov     rcx, [rbp+188h]; this
0x18000771f  lea     r8, aWil; "wil"
0x180007726  mov     edx, 0D0h; void *
0x18000772b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007730  mov     rcx, [rbp+180h+var_40]
0x180007737  xor     rcx, rsp; StackCookie
0x18000773a  call    __security_check_cookie
0x18000773f  add     rsp, 258h
0x180007746  pop     r15
0x180007748  pop     r14
0x18000774a  pop     rdi
0x18000774b  pop     rsi
0x18000774c  pop     rbx
0x18000774d  pop     rbp
0x18000774e  retn
0x18000774f  mov     rcx, [rbp+188h]; this
0x180007756  mov     edx, 0A0Bh; void *
0x18000775b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007761  mov     rcx, [rbp+188h]; this
0x180007768  mov     edx, 0A0Bh; void *
0x18000776d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007773  mov     rcx, [rbp+188h]; this
0x18000777a  mov     edx, 0A0Bh; void *
0x18000777f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007785  mov     rcx, [rbp+188h]; this
0x18000778c  mov     edx, 0A0Bh; void *
0x180007791  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007797  mov     rcx, [rbp+188h]; this
0x18000779e  mov     edx, 0A0Bh; void *
0x1800077a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077a9  mov     rcx, [rbp+188h]; this
0x1800077b0  mov     edx, 0A0Bh; void *
0x1800077b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
