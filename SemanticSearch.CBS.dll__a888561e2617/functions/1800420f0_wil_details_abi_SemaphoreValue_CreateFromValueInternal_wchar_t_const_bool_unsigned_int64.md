# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800420f0`
- end: `0x1800423b4`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `708`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800439f0`

## callees

- `0x1800161b0`
- `0x18003c690`
- `0x180041660`
- `0x180041c60`
- `0x1800420f0`
- `0x18004c070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004227b`
- `KERNEL32!GetLastError` at `0x180042350`
- `KERNEL32!GetLastError` at `0x18004227b`
- `KERNEL32!GetLastError` at `0x180042350`
- `KERNEL32!CreateSemaphoreExW` at `0x180042243`
- `KERNEL32!CreateSemaphoreExW` at `0x18004231b`
- `KERNEL32!CreateSemaphoreExW` at `0x180042243`
- `KERNEL32!CreateSemaphoreExW` at `0x18004231b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  signed __int64 v9; // r8
  WCHAR v10; // ax
  WCHAR *v11; // rax
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  char *v19; // r9
  WCHAR v20; // r8
  WCHAR *v21; // rax
  unsigned __int64 v22; // rbp
  LONG v23; // r10d
  LONG v24; // r14d
  LONG v25; // r8d
  wil::details *v26; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v29; // r8d
  unsigned int v30; // esi
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rax
  WCHAR *v35; // rcx
  __int64 v36; // rbx
  char *v37; // rdx
  WCHAR v38; // ax
  WCHAR *v39; // rax
  wil::details *v40; // rcx
  HANDLE v41; // rbx
  int v42; // eax
  unsigned int v43; // r8d
  unsigned int v44; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 260;
  v9 = (char *)a2 - (char *)Name;
  do
  {
    if ( v8 == -2147483386 )
      break;
    v10 = *(WCHAR *)((char *)v7 + v9);
    if ( !v10 )
      break;
    *v7++ = v10;
    --v8;
  }
  while ( v8 );
  v11 = v7 - 1;
  if ( v8 )
    v11 = v7;
  v12 = 260;
  *v11 = 0;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 2147483646;
  v15 = 260 - v12;
  if ( v12 )
  {
    v16 = &Name[v15];
    v17 = 260 - v15;
    if ( v15 != 260 )
    {
      v18 = 2147483646;
      v19 = (char *)((char *)L"_p0" - (char *)v16);
      do
      {
        if ( !v18 )
          break;
        v20 = *(WCHAR *)((char *)v16 + (_QWORD)v19);
        if ( !v20 )
          break;
        *v16 = v20;
        --v18;
        ++v16;
        --v17;
      }
      while ( v17 );
    }
    v21 = v16 - 1;
    if ( v17 )
      v21 = v16;
    *v21 = 0;
  }
  v22 = a4 >> 31;
  v23 = a4 & 0x7FFFFFFF;
  v24 = 1;
  v25 = 1;
  if ( v23 )
    v25 = v23;
  Semaphore = CreateSemaphoreExW(0, v23, v25, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    v30 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        v29,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v30;
    }
  }
  v32 = 260;
  v33 = Name;
  do
  {
    if ( !*v33 )
      break;
    ++v33;
    --v32;
  }
  while ( v32 );
  v34 = 260 - v32;
  if ( v32 )
  {
    v35 = &Name[v34];
    v36 = 260 - v34;
    if ( 260 != v34 )
    {
      v37 = (char *)((char *)L"h" - (char *)v35);
      do
      {
        if ( !v14 )
          break;
        v38 = *(WCHAR *)((char *)v35 + (_QWORD)v37);
        if ( !v38 )
          break;
        *v35 = v38;
        --v14;
        ++v35;
        --v36;
      }
      while ( v36 );
    }
    v39 = v35 - 1;
    if ( v36 )
      v39 = v35;
    *v39 = 0;
  }
  if ( (_DWORD)v22 )
    v24 = v22;
  v41 = CreateSemaphoreExW(0, v22, v24, Name, 0, 0x1F0003u);
  if ( v41 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v41);
  }
  else
  {
    v42 = wil::details::GetLastErrorFailHr(v40);
    v44 = v42;
    if ( v42 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x8D, v43, (const char *)(unsigned int)v42, dwFlagsa);
      return v44;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800420f0  mov     r11, rsp
0x1800420f3  push    r15
0x1800420f5  sub     rsp, 270h
0x1800420fc  mov     rax, cs:__security_cookie
0x180042103  xor     rax, rsp
0x180042106  mov     [rsp+278h+var_38], rax
0x18004210e  mov     rax, 0C000000000000000h
0x180042118  mov     r10, r9
0x18004211b  mov     r8, rdx
0x18004211e  mov     r15, rcx
0x180042121  test    rax, r9
0x180042124  jnz     loc_1800423AE
0x18004212a  mov     [r11+10h], rbx
0x18004212e  lea     rax, [rsp+278h+Name]
0x180042133  mov     [r11+18h], rbp
0x180042137  lea     rcx, [rsp+278h+Name]
0x18004213c  mov     [r11-10h], rsi
0x180042140  mov     ebx, 104h
0x180042145  mov     [r11-18h], rdi
0x180042149  mov     edx, ebx
0x18004214b  mov     [r11-20h], r12
0x18004214f  sub     r8, rax
0x180042152  mov     [r11-28h], r14
0x180042156  nop     word ptr [rax+rax+00000000h]
0x180042160  lea     rax, [rdx+7FFFFEFAh]
0x180042167  test    rax, rax
0x18004216a  jz      short loc_180042183
0x18004216c  movzx   eax, word ptr [r8+rcx]
0x180042171  test    ax, ax
0x180042174  jz      short loc_180042183
0x180042176  mov     [rcx], ax
0x180042179  add     rcx, 2
0x18004217d  sub     rdx, 1
0x180042181  jnz     short loc_180042160
0x180042183  test    rdx, rdx
0x180042186  lea     rax, [rcx-2]
0x18004218a  cmovnz  rax, rcx
0x18004218e  xor     r12d, r12d
0x180042191  mov     rcx, rbx
0x180042194  mov     [rax], r12w
0x180042198  lea     rax, [rsp+278h+Name]
0x18004219d  nop     dword ptr [rax]
0x1800421a0  cmp     [rax], r12w
0x1800421a4  jz      short loc_1800421B0
0x1800421a6  add     rax, 2
0x1800421aa  sub     rcx, 1
0x1800421ae  jnz     short loc_1800421A0
0x1800421b0  mov     rax, rbx
0x1800421b3  mov     edi, 7FFFFFFEh
0x1800421b8  sub     rax, rcx
0x1800421bb  test    rcx, rcx
0x1800421be  cmovz   rax, r12
0x1800421c2  jz      short loc_180042211
0x1800421c4  mov     rdx, rbx
0x1800421c7  lea     rcx, [rsp+278h+Name]
0x1800421cc  lea     rcx, [rcx+rax*2]
0x1800421d0  sub     rdx, rax
0x1800421d3  jz      short loc_180042202
0x1800421d5  lea     r9, aP0; "_p0"
0x1800421dc  mov     eax, edi
0x1800421de  sub     r9, rcx
0x1800421e1  test    rax, rax
0x1800421e4  jz      short loc_180042202
0x1800421e6  movzx   r8d, word ptr [r9+rcx]
0x1800421eb  test    r8w, r8w
0x1800421ef  jz      short loc_180042202
0x1800421f1  mov     [rcx], r8w
0x1800421f5  dec     rax
0x1800421f8  add     rcx, 2
0x1800421fc  sub     rdx, 1
0x180042200  jnz     short loc_1800421E1
0x180042202  test    rdx, rdx
0x180042205  lea     rax, [rcx-2]
0x180042209  cmovnz  rax, rcx
0x18004220d  mov     [rax], r12w
0x180042211  mov     rbp, r10
0x180042214  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18004221c  shr     rbp, 1Fh
0x180042220  lea     r9, [rsp+278h+Name]; lpName
0x180042225  and     r10d, 7FFFFFFFh
0x18004222c  mov     [rsp+278h+dwFlags], r12d; int
0x180042231  mov     r14d, 1
0x180042237  mov     edx, r10d; lInitialCount
0x18004223a  mov     r8d, r14d
0x18004223d  cmova   r8d, r10d; lMaximumCount
0x180042241  xor     ecx, ecx; lpSemaphoreAttributes
0x180042243  call    cs:__imp_CreateSemaphoreExW
0x180042249  mov     rsi, rax
0x18004224c  test    rax, rax
0x18004224f  jnz     short loc_18004227B
0x180042251  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180042256  mov     esi, eax
0x180042258  test    eax, eax
0x18004225a  jns     short loc_18004228C
0x18004225c  lfence
0x18004225f  mov     rcx, [rsp+278h]; this
0x180042267  mov     r9d, eax; char *
0x18004226a  mov     edx, 88h; void *
0x18004226f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042274  mov     eax, esi
0x180042276  jmp     loc_180042364
0x18004227b  call    cs:__imp_GetLastError
0x180042281  mov     rdx, rsi
0x180042284  mov     rcx, r15
0x180042287  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004228c  mov     rcx, rbx
0x18004228f  lea     rax, [rsp+278h+Name]
0x180042294  cmp     [rax], r12w
0x180042298  jz      short loc_1800422A3
0x18004229a  add     rax, 2
0x18004229e  sub     rcx, r14
0x1800422a1  jnz     short loc_180042294
0x1800422a3  mov     rax, rbx
0x1800422a6  sub     rax, rcx
0x1800422a9  test    rcx, rcx
0x1800422ac  cmovz   rax, r12
0x1800422b0  jz      short loc_1800422FC
0x1800422b2  lea     rcx, [rsp+278h+Name]
0x1800422b7  lea     rcx, [rcx+rax*2]
0x1800422bb  sub     rbx, rax
0x1800422be  jz      short loc_1800422ED
0x1800422c0  lea     rdx, asc_180076850; "h"
0x1800422c7  sub     rdx, rcx
0x1800422ca  nop     word ptr [rax+rax+00h]
0x1800422d0  test    rdi, rdi
0x1800422d3  jz      short loc_1800422ED
0x1800422d5  movzx   eax, word ptr [rdx+rcx]
0x1800422d9  test    ax, ax
0x1800422dc  jz      short loc_1800422ED
0x1800422de  mov     [rcx], ax
0x1800422e1  dec     rdi
0x1800422e4  add     rcx, 2
0x1800422e8  sub     rbx, r14
0x1800422eb  jnz     short loc_1800422D0
0x1800422ed  test    rbx, rbx
0x1800422f0  lea     rax, [rcx-2]
0x1800422f4  cmovnz  rax, rcx
0x1800422f8  mov     [rax], r12w
0x1800422fc  test    ebp, ebp
0x1800422fe  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180042306  lea     r9, [rsp+278h+Name]; lpName
0x18004230b  mov     [rsp+278h+dwFlags], r12d; int
0x180042310  cmovnz  r14d, ebp
0x180042314  mov     edx, ebp; lInitialCount
0x180042316  mov     r8d, r14d; lMaximumCount
0x180042319  xor     ecx, ecx; lpSemaphoreAttributes
0x18004231b  call    cs:__imp_CreateSemaphoreExW
0x180042321  mov     rbx, rax
0x180042324  test    rax, rax
0x180042327  jnz     short loc_180042350
0x180042329  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004232e  mov     ebx, eax
0x180042330  test    eax, eax
0x180042332  jns     short loc_180042362
0x180042334  lfence
0x180042337  mov     rcx, [rsp+278h]; this
0x18004233f  mov     r9d, eax; char *
0x180042342  mov     edx, 8Dh; void *
0x180042347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004234c  mov     eax, ebx
0x18004234e  jmp     short loc_180042364
0x180042350  call    cs:__imp_GetLastError
0x180042356  lea     rcx, [r15+8]
0x18004235a  mov     rdx, rbx
0x18004235d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180042362  xor     eax, eax
0x180042364  mov     r12, [rsp+278h+var_20]
0x18004236c  mov     rdi, [rsp+278h+var_18]
0x180042374  mov     rsi, [rsp+278h+var_10]
0x18004237c  mov     rbp, [rsp+278h+arg_10]
0x180042384  mov     rbx, [rsp+278h+arg_8]
0x18004238c  mov     r14, [rsp+278h+var_28]
0x180042394  mov     rcx, [rsp+278h+var_38]
0x18004239c  xor     rcx, rsp; StackCookie
0x18004239f  call    __security_check_cookie
0x1800423a4  add     rsp, 270h
0x1800423ab  pop     r15
0x1800423ad  retn
0x1800423ae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
