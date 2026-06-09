# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800050b0`
- end: `0x180005381`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `721`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004d90`
- `0x180004e10`

## callees

- `0x180004c94`
- `0x1800050b0`
- `0x180005390`
- `0x180005538`
- `0x180012a48`
- `0x180012a6c`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800051a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800052ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051bb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // rbp
  WCHAR *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v10; // rcx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r8
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  HANDLE v20; // rax
  wil::details *v21; // rdi
  unsigned int v22; // r8d
  const char *v23; // r9
  int ValueFromSemaphore; // eax
  int v26; // r8d
  unsigned int LastError; // ebx
  __int64 v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rdx
  WCHAR *v31; // rax
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rsi
  WCHAR *v34; // rdx
  wil::details *v35; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  wil::details *v38; // rbx
  int v39; // eax
  void *v40; // rdx
  int v41; // r8d
  unsigned int v42; // esi
  void *v43; // rdx
  void *v44; // rdx
  void *v45; // rdx
  void *v46; // rdx
  int v47; // [rsp+20h] [rbp-248h] BYREF
  int v48; // [rsp+24h] [rbp-244h] BYREF
  void *v49; // [rsp+28h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v4 = 2147483646;
  *a3 = 0;
  v5 = Name;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v5++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v5 - 1;
  if ( v7 )
    v10 = v5;
  *v10 = 0;
  v11 = 260;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = 260 - v11;
  if ( v11 )
  {
    v14 = L"_p0";
    v16 = v11;
    v15 = v13 == 260;
    v17 = 2147483646;
    v18 = &Name[v13];
    if ( !v15 )
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*v14 )
          break;
        *v18++ = *v14++;
        --v17;
        --v16;
      }
      while ( v16 );
    }
    v19 = v18 - 1;
    if ( v16 )
      v19 = v18;
    *v19 = 0;
  }
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v49 = v20;
  v21 = (wil::details *)v20;
  if ( !v20 )
  {
    if ( GetLastError() == 2 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v22, v23);
  }
  v48 = 0;
  v47 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v48);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v26, (const char *)(unsigned int)ValueFromSemaphore);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v49);
    return LastError;
  }
  v28 = 260;
  v29 = Name;
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  v30 = 260 - v28;
  if ( v28 )
  {
    v31 = &Name[v30];
    v32 = L"h";
    v33 = 260 - v30;
    if ( 260 != v30 )
    {
      do
      {
        if ( !v4 )
          break;
        if ( !*v32 )
          break;
        *v31++ = *v32++;
        --v4;
        --v33;
      }
      while ( v33 );
    }
    v34 = v31 - 1;
    if ( v33 )
      v34 = v31;
    *v34 = 0;
  }
  v35 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v38 = v35;
  if ( !v35 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v36, v37);
    wil::details::CloseHandle(v21, v44);
    return LastError;
  }
  v39 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v35, &v47);
  v42 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v41, (const char *)(unsigned int)v39);
    wil::details::CloseHandle(v38, v45);
    wil::details::CloseHandle(v21, v46);
    return v42;
  }
  else
  {
    wil::details::CloseHandle(v38, v40);
    *a3 = v48 | (unsigned __int64)((__int64)v47 << 31);
    wil::details::CloseHandle(v21, v43);
    return 0;
  }
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp+arg_8], rbp
0x1800050b5  push    rsi
0x1800050b6  push    rdi
0x1800050b7  push    r14
0x1800050b9  sub     rsp, 250h
0x1800050c0  mov     rax, cs:__security_cookie
0x1800050c7  xor     rax, rsp
0x1800050ca  mov     [rsp+268h+var_28], rax
0x1800050d2  mov     ebp, 7FFFFFFEh
0x1800050d7  mov     qword ptr [r8], 0
0x1800050de  mov     esi, 104h
0x1800050e3  lea     rax, [rsp+268h+Name]
0x1800050e8  mov     edx, ebp
0x1800050ea  mov     r9d, esi
0x1800050ed  mov     r14, r8
0x1800050f0  mov     r10, rcx
0x1800050f3  test    rdx, rdx
0x1800050f6  jz      short loc_180005115
0x1800050f8  movzx   ecx, word ptr [r10]
0x1800050fc  test    cx, cx
0x1800050ff  jz      short loc_180005115
0x180005101  mov     [rax], cx
0x180005104  add     r10, 2
0x180005108  add     rax, 2
0x18000510c  dec     rdx
0x18000510f  sub     r9, 1
0x180005113  jnz     short loc_1800050F3
0x180005115  lea     rcx, [rax-2]
0x180005119  test    r9, r9
0x18000511c  cmovnz  rcx, rax
0x180005120  xor     eax, eax
0x180005122  mov     [rcx], ax
0x180005125  mov     rcx, rsi
0x180005128  lea     rax, [rsp+268h+Name]
0x18000512d  nop     dword ptr [rax]
0x180005130  cmp     word ptr [rax], 0
0x180005134  jz      short loc_180005140
0x180005136  add     rax, 2
0x18000513a  sub     rcx, 1
0x18000513e  jnz     short loc_180005130
0x180005140  xor     eax, eax
0x180005142  mov     rdx, rsi
0x180005145  sub     rdx, rcx
0x180005148  test    rcx, rcx
0x18000514b  cmovz   rdx, rax
0x18000514f  jz      short loc_18000519C
0x180005151  mov     rax, rsi
0x180005154  lea     r8, aP0; "_p0"
0x18000515b  sub     rax, rdx
0x18000515e  mov     rcx, rbp
0x180005161  lea     rdx, [rsp+rdx*2+268h+Name]
0x180005166  jz      short loc_18000518C
0x180005168  test    rcx, rcx
0x18000516b  jz      short loc_18000518C
0x18000516d  movzx   r9d, word ptr [r8]
0x180005171  test    r9w, r9w
0x180005175  jz      short loc_18000518C
0x180005177  mov     [rdx], r9w
0x18000517b  add     r8, 2
0x18000517f  add     rdx, 2
0x180005183  dec     rcx
0x180005186  sub     rax, 1
0x18000518a  jnz     short loc_180005168
0x18000518c  test    rax, rax
0x18000518f  lea     rcx, [rdx-2]
0x180005193  cmovnz  rcx, rdx
0x180005197  xor     eax, eax
0x180005199  mov     [rcx], ax
0x18000519c  lea     r8, [rsp+268h+Name]; lpName
0x1800051a1  xor     edx, edx; bInheritHandle
0x1800051a3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800051a8  call    cs:__imp_OpenSemaphoreW
0x1800051ae  mov     [rsp+268h+var_240], rax
0x1800051b3  mov     rdi, rax
0x1800051b6  test    rax, rax
0x1800051b9  jnz     short loc_180005200
0x1800051bb  call    cs:__imp_GetLastError
0x1800051c1  cmp     eax, 2
0x1800051c4  jnz     short loc_1800051EC
0x1800051c6  xor     eax, eax
0x1800051c8  mov     rcx, [rsp+268h+var_28]
0x1800051d0  xor     rcx, rsp; StackCookie
0x1800051d3  call    __security_check_cookie
0x1800051d8  mov     rbp, [rsp+268h+arg_8]
0x1800051e0  add     rsp, 250h
0x1800051e7  pop     r14
0x1800051e9  pop     rdi
0x1800051ea  pop     rsi
0x1800051eb  retn
0x1800051ec  mov     rcx, [rsp+268h]; this
0x1800051f4  mov     edx, 0D0h; void *
0x1800051f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800051fe  jmp     short loc_1800051C8
0x180005200  lea     rdx, [rsp+268h+var_244]; int *
0x180005205  mov     [rsp+268h+arg_0], rbx
0x18000520d  mov     rcx, rdi; hHandle
0x180005210  mov     [rsp+268h+var_244], 0
0x180005218  mov     [rsp+268h+var_248], 0; int
0x180005220  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005225  mov     ebx, eax
0x180005227  test    eax, eax
0x180005229  js      loc_180005360
0x18000522f  mov     rcx, rsi
0x180005232  lea     rax, [rsp+268h+Name]
0x180005237  cmp     word ptr [rax], 0
0x18000523b  jz      short loc_180005247
0x18000523d  add     rax, 2
0x180005241  sub     rcx, 1
0x180005245  jnz     short loc_180005237
0x180005247  xor     eax, eax
0x180005249  mov     rdx, rsi
0x18000524c  sub     rdx, rcx
0x18000524f  test    rcx, rcx
0x180005252  cmovz   rdx, rax
0x180005256  jz      short loc_1800052A1
0x180005258  lea     rax, [rsp+268h+Name]
0x18000525d  lea     rax, [rax+rdx*2]
0x180005261  lea     rcx, asc_1800230C8; "h"
0x180005268  sub     rsi, rdx
0x18000526b  jz      short loc_180005291
0x18000526d  nop     dword ptr [rax]
0x180005270  test    rbp, rbp
0x180005273  jz      short loc_180005291
0x180005275  movzx   edx, word ptr [rcx]
0x180005278  test    dx, dx
0x18000527b  jz      short loc_180005291
0x18000527d  mov     [rax], dx
0x180005280  add     rcx, 2
0x180005284  add     rax, 2
0x180005288  dec     rbp
0x18000528b  sub     rsi, 1
0x18000528f  jnz     short loc_180005270
0x180005291  test    rsi, rsi
0x180005294  lea     rdx, [rax-2]
0x180005298  cmovnz  rdx, rax
0x18000529c  xor     eax, eax
0x18000529e  mov     [rdx], ax
0x1800052a1  lea     r8, [rsp+268h+Name]; lpName
0x1800052a6  xor     edx, edx; bInheritHandle
0x1800052a8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800052ad  call    cs:__imp_OpenSemaphoreW
0x1800052b3  mov     rbx, rax
0x1800052b6  test    rax, rax
0x1800052b9  jz      short loc_180005301
0x1800052bb  lea     rdx, [rsp+268h+var_248]; int *
0x1800052c0  mov     rcx, rax; hHandle
0x1800052c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800052c8  mov     esi, eax
0x1800052ca  test    eax, eax
0x1800052cc  js      short loc_18000532C
0x1800052ce  mov     rcx, rbx; this
0x1800052d1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800052d6  movsxd  rax, [rsp+268h+var_244]
0x1800052db  movsxd  rcx, [rsp+268h+var_248]
0x1800052e0  shl     rcx, 1Fh
0x1800052e4  or      rcx, rax
0x1800052e7  mov     [r14], rcx
0x1800052ea  mov     rcx, rdi; this
0x1800052ed  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800052f2  mov     rbx, [rsp+268h+arg_0]
0x1800052fa  xor     eax, eax
0x1800052fc  jmp     loc_1800051C8
0x180005301  mov     rcx, [rsp+268h]; this
0x180005309  mov     edx, 0DCh; void *
0x18000530e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005313  mov     rcx, rdi; this
0x180005316  mov     ebx, eax
0x180005318  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000531d  mov     eax, ebx
0x18000531f  mov     rbx, [rsp+268h+arg_0]
0x180005327  jmp     loc_1800051C8
0x18000532c  mov     rcx, [rsp+268h]; this
0x180005334  mov     r9d, esi; char *
0x180005337  mov     edx, 0DEh; void *
0x18000533c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005341  mov     rcx, rbx; this
0x180005344  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005349  mov     rcx, rdi; this
0x18000534c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005351  mov     rbx, [rsp+268h+arg_0]
0x180005359  mov     eax, esi
0x18000535b  jmp     loc_1800051C8
0x180005360  mov     rcx, [rsp+268h]; this
0x180005368  mov     r9d, ebx; char *
0x18000536b  mov     edx, 0D6h; void *
0x180005370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005375  lea     rcx, [rsp+268h+var_240]
0x18000537a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000537f  jmp     short loc_18000531D
```
