# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dee0`
- end: `0x18000e1cf`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `751`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000dc10`
- `0x18000dc94`

## callees

- `0x18000dea4`
- `0x18000dee0`
- `0x18001d858`
- `0x18001d9b0`
- `0x18001e798`
- `0x18002c570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000df8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e0a2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000df8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df9f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // rbp
  WCHAR *v5; // r9
  __int64 v6; // rax
  __int64 v7; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rdx
  wil::details *v14; // rax
  wil::details *v15; // rbx
  const char *v16; // r9
  const unsigned __int16 *v18; // r8
  __int64 v19; // rcx
  WCHAR *v20; // r10
  __int64 v21; // r9
  WCHAR *v22; // rcx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v25; // rcx
  WCHAR *v26; // rax
  __int64 v27; // rdx
  wil::details *v28; // rax
  const char *v29; // r9
  wil::details *v30; // rdi
  void *v31; // rdx
  WCHAR *v32; // rax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rsi
  WCHAR *v35; // rdx
  int v36; // eax
  void *v37; // rdx
  unsigned int v38; // esi
  void *v39; // rdx
  void *v40; // rdx
  void *v41; // rdx
  int v42; // [rsp+20h] [rbp-248h] BYREF
  int v43[3]; // [rsp+24h] [rbp-244h] BYREF
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
    v18 = L"_p0";
    v19 = 2147483646;
    v20 = &Name[v13];
    v21 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v19 )
          break;
        if ( !*v18 )
          break;
        *v20++ = *v18++;
        --v19;
        --v21;
      }
      while ( v21 );
    }
    v22 = v20 - 1;
    if ( v21 )
      v22 = v20;
    *v22 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v15 = v14;
  if ( !v14 )
  {
    if ( GetLastError() == 2 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v16);
  }
  v43[0] = 0;
  v42 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, v43);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v42);
    goto LABEL_28;
  }
  v25 = 260;
  v26 = Name;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = 260 - v25;
  if ( v25 )
  {
    v32 = &Name[v27];
    v33 = L"h";
    v34 = 260 - v27;
    if ( 260 != v27 )
    {
      do
      {
        if ( !v4 )
          break;
        if ( !*v33 )
          break;
        *v32++ = *v33++;
        --v4;
        --v34;
      }
      while ( v34 );
    }
    v35 = v32 - 1;
    if ( v34 )
      v35 = v32;
    *v35 = 0;
  }
  v28 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v30 = v28;
  if ( !v28 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v29);
LABEL_28:
    wil::details::CloseHandle(v15, v31);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v28, &v42);
  v38 = v36;
  if ( v36 >= 0 )
  {
    wil::details::CloseHandle(v30, v37);
    *a3 = v43[0] | (unsigned __int64)((__int64)v42 << 31);
    wil::details::CloseHandle(v15, v41);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v42);
    wil::details::CloseHandle(v30, v39);
    wil::details::CloseHandle(v15, v40);
    return v38;
  }
}

```

## disassembly

```asm
0x18000dee0  mov     [rsp+arg_8], rbx
0x18000dee5  push    rbp
0x18000dee6  push    rsi
0x18000dee7  push    r14
0x18000dee9  sub     rsp, 250h
0x18000def0  mov     rax, cs:__security_cookie
0x18000def7  xor     rax, rsp
0x18000defa  mov     [rsp+268h+var_28], rax
0x18000df02  mov     ebp, 7FFFFFFEh
0x18000df07  mov     qword ptr [r8], 0
0x18000df0e  mov     esi, 104h
0x18000df13  lea     r9, [rsp+268h+Name]
0x18000df18  mov     eax, ebp
0x18000df1a  mov     r10d, esi
0x18000df1d  mov     r14, r8
0x18000df20  mov     rdx, rcx
0x18000df23  test    rax, rax
0x18000df26  jz      short loc_18000DF45
0x18000df28  movzx   ecx, word ptr [rdx]
0x18000df2b  test    cx, cx
0x18000df2e  jz      short loc_18000DF45
0x18000df30  mov     [r9], cx
0x18000df34  add     rdx, 2
0x18000df38  add     r9, 2
0x18000df3c  dec     rax
0x18000df3f  sub     r10, 1
0x18000df43  jnz     short loc_18000DF23
0x18000df45  test    r10, r10
0x18000df48  lea     rcx, [r9-2]
0x18000df4c  cmovnz  rcx, r9
0x18000df50  xor     eax, eax
0x18000df52  mov     [rcx], ax
0x18000df55  mov     rcx, rsi
0x18000df58  lea     rax, [rsp+268h+Name]
0x18000df5d  nop     dword ptr [rax]
0x18000df60  cmp     word ptr [rax], 0
0x18000df64  jz      short loc_18000DF70
0x18000df66  add     rax, 2
0x18000df6a  sub     rcx, 1
0x18000df6e  jnz     short loc_18000DF60
0x18000df70  xor     eax, eax
0x18000df72  mov     rdx, rsi
0x18000df75  sub     rdx, rcx
0x18000df78  test    rcx, rcx
0x18000df7b  cmovz   rdx, rax
0x18000df7f  jnz     short loc_18000DFEB
0x18000df81  lea     r8, [rsp+268h+Name]; lpName
0x18000df86  xor     edx, edx; bInheritHandle
0x18000df88  mov     ecx, 1F0003h; dwDesiredAccess
0x18000df8d  call    cs:__imp_OpenSemaphoreW
0x18000df93  mov     rbx, rax
0x18000df96  test    rax, rax
0x18000df99  jnz     loc_18000E03E
0x18000df9f  call    cs:__imp_GetLastError
0x18000dfa5  cmp     eax, 2
0x18000dfa8  jz      loc_18000E1C8
0x18000dfae  mov     rcx, [rsp+268h]; this
0x18000dfb6  lea     r8, aWil; "wil"
0x18000dfbd  mov     edx, 0D0h; void *
0x18000dfc2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dfc7  mov     rcx, [rsp+268h+var_28]
0x18000dfcf  xor     rcx, rsp; StackCookie
0x18000dfd2  call    __security_check_cookie
0x18000dfd7  mov     rbx, [rsp+268h+arg_8]
0x18000dfdf  add     rsp, 250h
0x18000dfe6  pop     r14
0x18000dfe8  pop     rsi
0x18000dfe9  pop     rbp
0x18000dfea  retn
0x18000dfeb  mov     r9, rsi
0x18000dfee  lea     r10, [rsp+268h+Name]
0x18000dff3  lea     r8, aP0; "_p0"
0x18000dffa  mov     rcx, rbp
0x18000dffd  lea     r10, [r10+rdx*2]
0x18000e001  sub     r9, rdx
0x18000e004  jz      short loc_18000E029
0x18000e006  test    rcx, rcx
0x18000e009  jz      short loc_18000E029
0x18000e00b  movzx   eax, word ptr [r8]
0x18000e00f  test    ax, ax
0x18000e012  jz      short loc_18000E029
0x18000e014  mov     [r10], ax
0x18000e018  add     r8, 2
0x18000e01c  add     r10, 2
0x18000e020  dec     rcx
0x18000e023  sub     r9, 1
0x18000e027  jnz     short loc_18000E006
0x18000e029  test    r9, r9
0x18000e02c  lea     rcx, [r10-2]
0x18000e030  cmovnz  rcx, r10
0x18000e034  xor     eax, eax
0x18000e036  mov     [rcx], ax
0x18000e039  jmp     loc_18000DF81
0x18000e03e  lea     rdx, [rsp+268h+var_244]; int *
0x18000e043  mov     [rsp+268h+arg_0], rdi
0x18000e04b  mov     rcx, rbx; hHandle
0x18000e04e  mov     [rsp+268h+var_244], 0
0x18000e056  mov     [rsp+268h+var_248], 0; int
0x18000e05e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e063  mov     edi, eax
0x18000e065  test    eax, eax
0x18000e067  js      loc_18000E136
0x18000e06d  mov     rcx, rsi
0x18000e070  lea     rax, [rsp+268h+Name]
0x18000e075  cmp     word ptr [rax], 0
0x18000e079  jz      short loc_18000E085
0x18000e07b  add     rax, 2
0x18000e07f  sub     rcx, 1
0x18000e083  jnz     short loc_18000E075
0x18000e085  xor     eax, eax
0x18000e087  mov     rdx, rsi
0x18000e08a  sub     rdx, rcx
0x18000e08d  test    rcx, rcx
0x18000e090  cmovz   rdx, rax
0x18000e094  jnz     short loc_18000E0E6
0x18000e096  lea     r8, [rsp+268h+Name]; lpName
0x18000e09b  xor     edx, edx; bInheritHandle
0x18000e09d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e0a2  call    cs:__imp_OpenSemaphoreW
0x18000e0a8  mov     rdi, rax
0x18000e0ab  test    rax, rax
0x18000e0ae  jnz     loc_18000E157
0x18000e0b4  mov     rcx, [rsp+268h]; this
0x18000e0bc  lea     r8, aWil; "wil"
0x18000e0c3  mov     edx, 0DCh; void *
0x18000e0c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e0cd  mov     edi, eax
0x18000e0cf  mov     rcx, rbx; this
0x18000e0d2  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e0d7  mov     eax, edi
0x18000e0d9  mov     rdi, [rsp+268h+arg_0]
0x18000e0e1  jmp     loc_18000DFC7
0x18000e0e6  lea     rax, [rsp+268h+Name]
0x18000e0eb  lea     rax, [rax+rdx*2]
0x18000e0ef  lea     rcx, asc_18006C3D0; "h"
0x18000e0f6  sub     rsi, rdx
0x18000e0f9  jz      short loc_18000E121
0x18000e0fb  nop     dword ptr [rax+rax+00h]
0x18000e100  test    rbp, rbp
0x18000e103  jz      short loc_18000E121
0x18000e105  movzx   edx, word ptr [rcx]
0x18000e108  test    dx, dx
0x18000e10b  jz      short loc_18000E121
0x18000e10d  mov     [rax], dx
0x18000e110  add     rcx, 2
0x18000e114  add     rax, 2
0x18000e118  dec     rbp
0x18000e11b  sub     rsi, 1
0x18000e11f  jnz     short loc_18000E100
0x18000e121  test    rsi, rsi
0x18000e124  lea     rdx, [rax-2]
0x18000e128  cmovnz  rdx, rax
0x18000e12c  xor     eax, eax
0x18000e12e  mov     [rdx], ax
0x18000e131  jmp     loc_18000E096
0x18000e136  mov     rcx, [rsp+268h]; this
0x18000e13e  lea     r8, aWil; "wil"
0x18000e145  mov     r9d, edi; char *
0x18000e148  mov     edx, 0D6h; void *
0x18000e14d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e152  jmp     loc_18000E0CF
0x18000e157  lea     rdx, [rsp+268h+var_248]; int *
0x18000e15c  mov     rcx, rdi; hHandle
0x18000e15f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e164  mov     esi, eax
0x18000e166  test    eax, eax
0x18000e168  jns     short loc_18000E19D
0x18000e16a  mov     rcx, [rsp+268h]; this
0x18000e172  lea     r8, aWil; "wil"
0x18000e179  mov     r9d, eax; char *
0x18000e17c  mov     edx, 0DEh; void *
0x18000e181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e186  mov     rcx, rdi; this
0x18000e189  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e18e  mov     rcx, rbx; this
0x18000e191  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e196  mov     eax, esi
0x18000e198  jmp     loc_18000E0D9
0x18000e19d  mov     rcx, rdi; this
0x18000e1a0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e1a5  movsxd  rax, [rsp+268h+var_244]
0x18000e1aa  movsxd  rcx, [rsp+268h+var_248]
0x18000e1af  shl     rcx, 1Fh
0x18000e1b3  or      rcx, rax
0x18000e1b6  mov     [r14], rcx
0x18000e1b9  mov     rcx, rbx; this
0x18000e1bc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000e1c1  xor     eax, eax
0x18000e1c3  jmp     loc_18000E0D9
0x18000e1c8  xor     eax, eax
0x18000e1ca  jmp     loc_18000DFC7
```
