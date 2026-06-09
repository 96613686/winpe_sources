# _anonymous_namespace_::CreateUniqueSubKey

- ea: `0x140044100`
- end: `0x14004434d`
- name: `_anonymous_namespace_::CreateUniqueSubKey`
- size: `589`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140043f50`

## callees

- `0x1400042f0`
- `0x140004610`
- `0x14001ed14`
- `0x1400419a4`
- `0x1400419c4`
- `0x140044100`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004425f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004425f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140044272`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140044272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004426a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004426a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400442ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400442ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PHKEY __fastcall anonymous_namespace_::CreateUniqueSubKey(PHKEY phkResult, HKEY hKey)
{
  char *v4; // rdi
  unsigned int *v5; // r15
  int v6; // r12d
  bool v7; // sf
  unsigned int v8; // r8d
  _WORD *v9; // r9
  unsigned int v10; // r8d
  HKEY v11; // r14
  DWORD LastError; // ebx
  const WCHAR *v13; // rdx
  unsigned int v14; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-89h]
  DWORD dwDisposition; // [rsp+54h] [rbp-55h] BYREF
  char *v18; // [rsp+58h] [rbp-51h]
  char *v19; // [rsp+60h] [rbp-49h]
  PHKEY v20; // [rsp+68h] [rbp-41h]
  LPCWSTR lpSubKey[9]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v22[6]; // [rsp+BAh] [rbp+11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v20 = phkResult;
  *phkResult = 0;
  dwDisposition = 0;
  v4 = (char *)operator new(0x18u);
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count_obj2<int>::`vftable';
  v5 = (unsigned int *)(v4 + 16);
  *((_DWORD *)v4 + 4) = 0;
  _InterlockedAdd((volatile signed __int32 *)v4 + 2, 1u);
  v18 = v4 + 16;
  v19 = v4;
  v6 = 7;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v4)(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  do
  {
    v7 = (++*v5 & 0x80000000) != 0;
    v8 = *v5;
    v9 = v22;
    if ( v7 )
    {
      v10 = -v8;
      do
      {
        *--v9 = v10 % 0xA + 48;
        v10 /= 0xAu;
      }
      while ( v10 );
      *--v9 = 45;
    }
    else
    {
      do
      {
        *--v9 = v8 % 0xA + 48;
        v8 /= 0xAu;
      }
      while ( v8 );
    }
    std::wstring::wstring(lpSubKey, v9, v22);
    v6 |= 0x38u;
    v11 = *phkResult;
    if ( *phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v11);
      SetLastError(LastError);
    }
    *phkResult = 0;
    v13 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v13 = lpSubKey[0];
    v14 = RegCreateKeyExW(hKey, v13, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2D,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)v14,
        dwOptions);
    std::wstring::~wstring((char **)lpSubKey);
  }
  while ( dwDisposition == 2 );
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v4)(v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  return phkResult;
}

```

## disassembly

```asm
0x140044100  mov     [rsp-8+arg_10], rbx
0x140044105  push    rbp
0x140044106  push    rsi
0x140044107  push    rdi
0x140044108  push    r12
0x14004410a  push    r13
0x14004410c  push    r14
0x14004410e  push    r15
0x140044110  lea     rbp, [rsp-27h]
0x140044115  sub     rsp, 0D0h
0x14004411c  mov     rax, cs:__security_cookie
0x140044123  xor     rax, rsp
0x140044126  mov     [rbp+57h+var_40], rax
0x14004412a  mov     r13, rdx
0x14004412d  mov     rsi, rcx
0x140044130  mov     [rbp+57h+var_98], rcx
0x140044134  xor     r14d, r14d
0x140044137  mov     [rbp+57h+var_B0], r14d
0x14004413b  mov     [rcx], r14
0x14004413e  lea     ebx, [r14+1]
0x140044142  mov     [rbp+57h+var_B0], ebx
0x140044145  mov     [rbp+57h+dwDisposition], r14d
0x140044149  lea     ecx, [rbx+17h]; Size
0x14004414c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140044151  mov     rdi, rax
0x140044154  mov     [rbp+57h+var_A8], rax
0x140044158  xorps   xmm0, xmm0
0x14004415b  movups  xmmword ptr [rax], xmm0
0x14004415e  mov     [rax+8], ebx
0x140044161  mov     [rax+0Ch], ebx
0x140044164  lea     rax, ??_7?$_Ref_count_obj2@H@std@@6B@; const std::_Ref_count_obj2<int>::`vftable'
0x14004416b  mov     [rdi], rax
0x14004416e  lea     r15, [rdi+10h]
0x140044172  mov     [r15], r14d
0x140044175  lock add [rdi+8], ebx
0x140044179  mov     [rbp+57h+var_A8], r15
0x14004417d  mov     [rbp+57h+var_A0], rdi
0x140044181  lea     r12d, [r14+7]
0x140044185  mov     [rbp+57h+var_B0], r12d
0x140044189  or      ebx, 0FFFFFFFFh
0x14004418c  mov     eax, ebx
0x14004418e  lock xadd [rdi+8], eax
0x140044193  add     eax, ebx
0x140044195  jnz     short loc_1400441C0
0x140044197  mov     rax, [rdi]
0x14004419a  mov     rcx, rdi
0x14004419d  mov     rax, [rax]
0x1400441a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400441a5  mov     eax, ebx
0x1400441a7  lock xadd [rdi+0Ch], eax
0x1400441ac  add     eax, ebx
0x1400441ae  jnz     short loc_1400441C0
0x1400441b0  mov     rax, [rdi]
0x1400441b3  mov     rcx, rdi
0x1400441b6  mov     rax, [rax+8]
0x1400441ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400441bf  nop
0x1400441c0  mov     ebx, 2Dh ; '-'
0x1400441c5  add     dword ptr [r15], 1
0x1400441c9  mov     r8d, [r15]
0x1400441cc  lea     r9, [rbp+57h+var_46]
0x1400441d0  jns     short loc_14004420F
0x1400441d2  neg     r8d
0x1400441d5  sub     r9, 2
0x1400441d9  mov     eax, 0CCCCCCCDh
0x1400441de  mul     r8d
0x1400441e1  shr     edx, 3
0x1400441e4  movzx   eax, dx
0x1400441e7  shl     ax, 2
0x1400441eb  lea     ecx, [rax+rdx]
0x1400441ee  add     cx, cx
0x1400441f1  sub     r8w, cx
0x1400441f5  add     r8w, 30h ; '0'
0x1400441fa  mov     [r9], r8w
0x1400441fe  mov     r8d, edx
0x140044201  test    edx, edx
0x140044203  jnz     short loc_1400441D5
0x140044205  add     r9, 0FFFFFFFFFFFFFFFEh
0x140044209  mov     [r9], bx
0x14004420d  jmp     short loc_14004423F
0x14004420f  sub     r9, 2
0x140044213  mov     eax, 0CCCCCCCDh
0x140044218  mul     r8d
0x14004421b  shr     edx, 3
0x14004421e  movzx   eax, dx
0x140044221  shl     ax, 2
0x140044225  lea     ecx, [rax+rdx]
0x140044228  add     cx, cx
0x14004422b  sub     r8w, cx
0x14004422f  add     r8w, 30h ; '0'
0x140044234  mov     [r9], r8w
0x140044238  mov     r8d, edx
0x14004423b  test    edx, edx
0x14004423d  jnz     short loc_14004420F
0x14004423f  lea     r8, [rbp+57h+var_46]
0x140044243  mov     rdx, r9
0x140044246  lea     rcx, [rbp+57h+lpSubKey]
0x14004424a  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x14004424f  or      r12d, 38h
0x140044253  mov     [rbp+57h+var_B0], r12d
0x140044257  mov     r14, [rsi]
0x14004425a  test    r14, r14
0x14004425d  jz      short loc_14004427D
0x14004425f  call    cs:__imp_GetLastError
0x140044265  mov     ebx, eax
0x140044267  mov     rcx, r14; hKey
0x14004426a  call    cs:__imp_RegCloseKey
0x140044270  mov     ecx, ebx; dwErrCode
0x140044272  call    cs:__imp_SetLastError
0x140044278  mov     ebx, 2Dh ; '-'
0x14004427d  xor     r14d, r14d
0x140044280  mov     [rsi], r14
0x140044283  lea     rdx, [rbp+57h+lpSubKey]
0x140044287  cmp     [rbp+57h+var_78], 7
0x14004428c  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140044291  lea     rax, [rbp+57h+dwDisposition]
0x140044295  mov     [rsp+100h+lpdwDisposition], rax; lpdwDisposition
0x14004429a  mov     [rsp+100h+phkResult], rsi; phkResult
0x14004429f  mov     [rsp+100h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400442a4  mov     [rsp+100h+samDesired], 2001Fh; samDesired
0x1400442ac  mov     [rsp+100h+dwOptions], r14d; unsigned int
0x1400442b1  xor     r9d, r9d; lpClass
0x1400442b4  xor     r8d, r8d; Reserved
0x1400442b7  mov     rcx, r13; hKey
0x1400442ba  call    cs:__imp_RegCreateKeyExW
0x1400442c0  mov     rcx, [rbp+5Fh]; this
0x1400442c4  test    eax, eax
0x1400442c6  jnz     short loc_14004433B
0x1400442c8  lea     rcx, [rbp+57h+lpSubKey]
0x1400442cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400442d1  cmp     [rbp+57h+dwDisposition], 2
0x1400442d5  jz      loc_1400441C5
0x1400442db  or      ebx, 0FFFFFFFFh
0x1400442de  mov     eax, ebx
0x1400442e0  lock xadd [rdi+8], eax
0x1400442e5  add     eax, ebx
0x1400442e7  jnz     short loc_140044311
0x1400442e9  mov     rax, [rdi]
0x1400442ec  mov     rcx, rdi
0x1400442ef  mov     rax, [rax]
0x1400442f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400442f7  mov     ecx, ebx
0x1400442f9  lock xadd [rdi+0Ch], ecx
0x1400442fe  add     ecx, ebx
0x140044300  jnz     short loc_140044311
0x140044302  mov     rcx, [rdi]
0x140044305  mov     rax, [rcx+8]
0x140044309  mov     rcx, rdi
0x14004430c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044311  mov     rax, rsi
0x140044314  mov     rcx, [rbp+57h+var_40]
0x140044318  xor     rcx, rsp; StackCookie
0x14004431b  call    __security_check_cookie
0x140044320  mov     rbx, [rsp+100h+arg_10]
0x140044328  add     rsp, 0D0h
0x14004432f  pop     r15
0x140044331  pop     r14
0x140044333  pop     r13
0x140044335  pop     r12
0x140044337  pop     rdi
0x140044338  pop     rsi
0x140044339  pop     rbp
0x14004433a  retn
0x14004433b  mov     r9d, eax; char *
0x14004433e  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140044345  mov     edx, ebx; void *
0x140044347  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
