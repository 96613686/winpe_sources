# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180072360`
- end: `0x1800726af`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `847`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800737f0`

## callees

- `0x180046940`
- `0x1800719d0`
- `0x180071a00`
- `0x1800721b0`
- `0x180072360`
- `0x1801f7110`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180072489`
- `KERNEL32!GetLastError` at `0x180072489`
- `KERNEL32!CloseHandle` at `0x180072610`
- `KERNEL32!CloseHandle` at `0x18007261f`
- `KERNEL32!CloseHandle` at `0x180072652`
- `KERNEL32!CloseHandle` at `0x180072610`
- `KERNEL32!CloseHandle` at `0x18007261f`
- `KERNEL32!CloseHandle` at `0x180072652`
- `KERNEL32!OpenSemaphoreW` at `0x18007247b`
- `KERNEL32!OpenSemaphoreW` at `0x1800725ae`
- `KERNEL32!OpenSemaphoreW` at `0x18007247b`
- `KERNEL32!OpenSemaphoreW` at `0x1800725ae`

## string_xrefs

- `0x180072669`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x180072683`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x18007269d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        char a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebp
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  signed __int64 v10; // r10
  WCHAR v11; // ax
  WCHAR *v12; // rax
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  char *v20; // r9
  WCHAR v21; // r8
  WCHAR *v22; // rax
  HANDLE v23; // rax
  void *v24; // rbx
  const char *v25; // r9
  int v26; // r14d
  int ValueFromSemaphore; // eax
  int v28; // r15d
  __int64 v30; // rcx
  WCHAR *v31; // rax
  WCHAR *v32; // rdx
  __int64 v33; // rdi
  char *v34; // rcx
  WCHAR v35; // ax
  WCHAR *v36; // rax
  HANDLE v37; // rax
  const char *v38; // r9
  void *v39; // rsi
  int v40; // edi
  int v41; // eax
  const char *v42; // r9
  const char *v43; // r9
  __int64 v44; // rax
  const char *v45; // r9
  int v46; // [rsp+20h] [rbp-268h] BYREF
  int v47; // [rsp+24h] [rbp-264h] BYREF
  unsigned __int64 *v48; // [rsp+28h] [rbp-260h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v48 = a3;
  if ( a4 )
    *a4 = 0;
  LastError = 0;
  *a3 = 0;
  v8 = 260;
  v9 = Name;
  v10 = (char *)a1 - (char *)Name;
  do
  {
    if ( v8 == -2147483386 )
      break;
    v11 = *(WCHAR *)((char *)v9 + v10);
    if ( !v11 )
      break;
    *v9++ = v11;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  v13 = 260;
  *v12 = 0;
  v14 = Name;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = 2147483646;
  v16 = 260 - v13;
  if ( v13 )
  {
    v17 = &Name[v16];
    v18 = 260 - v16;
    if ( v16 != 260 )
    {
      v19 = 2147483646;
      v20 = (char *)((char *)L"_p0" - (char *)v17);
      do
      {
        if ( !v19 )
          break;
        v21 = *(_WORD *)&v20[(_QWORD)v17];
        if ( !v21 )
          break;
        *v17 = v21;
        --v19;
        ++v17;
        --v18;
      }
      while ( v18 );
    }
    v22 = v17 - 1;
    if ( v18 )
      v22 = v17;
    *v22 = 0;
  }
  v23 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v23;
  if ( !v23 )
  {
    if ( GetLastError() != 2 )
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v25);
LABEL_26:
    if ( !v24 )
      return LastError;
    goto LABEL_51;
  }
  v46 = 0;
  v47 = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v23, &v46);
  v28 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v46);
    LastError = v28;
    goto LABEL_26;
  }
  if ( !a2 )
    goto LABEL_48;
  v30 = 260;
  v31 = Name;
  do
  {
    if ( !*v31 )
      break;
    ++v31;
    --v30;
  }
  while ( v30 );
  if ( v30 )
  {
    v32 = &Name[260 - v30];
    v33 = v30;
    v34 = (char *)((char *)L"h" - (char *)v32);
    do
    {
      if ( !v15 )
        break;
      v35 = *(WCHAR *)((char *)v32 + (_QWORD)v34);
      if ( !v35 )
        break;
      *v32 = v35;
      --v15;
      ++v32;
      --v33;
    }
    while ( v33 );
    v36 = v32 - 1;
    if ( v33 )
      v36 = v32;
    *v36 = 0;
  }
  v37 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v39 = v37;
  if ( v37 )
  {
    v41 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v37, &v47);
    v40 = v41;
    _mm_lfence();
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v41,
        v46);
      if ( !CloseHandle(v39) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
          v42);
      goto LABEL_42;
    }
    if ( !CloseHandle(v39) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
        v43);
    v26 = v47;
LABEL_48:
    v44 = v46;
    if ( a4 )
      *a4 = 1;
    *v48 = ((__int64)v26 << 31) | v44;
    goto LABEL_51;
  }
  v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v38);
LABEL_42:
  LastError = v40;
LABEL_51:
  if ( !CloseHandle(v24) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
      v45);
  return LastError;
}

```

## disassembly

```asm
0x180072360  push    rbx
0x180072362  push    rbp
0x180072363  push    rsi
0x180072364  push    rdi
0x180072365  push    r12
0x180072367  push    r13
0x180072369  sub     rsp, 258h
0x180072370  mov     rax, cs:__security_cookie
0x180072377  xor     rax, rsp
0x18007237a  mov     [rsp+288h+var_48], rax
0x180072382  mov     [rsp+288h+var_260], r8
0x180072387  mov     r13, r9
0x18007238a  movzx   r12d, dl
0x18007238e  mov     r10, rcx
0x180072391  test    r9, r9
0x180072394  jz      short loc_18007239A
0x180072396  mov     byte ptr [r9], 0
0x18007239a  xor     ebp, ebp
0x18007239c  lea     rax, [rsp+288h+Name]
0x1800723a1  mov     edi, 104h
0x1800723a6  mov     [r8], rbp
0x1800723a9  mov     edx, edi
0x1800723ab  lea     rcx, [rsp+288h+Name]
0x1800723b0  sub     r10, rax
0x1800723b3  lea     rax, [rdx+7FFFFEFAh]
0x1800723ba  test    rax, rax
0x1800723bd  jz      short loc_1800723D6
0x1800723bf  movzx   eax, word ptr [rcx+r10]
0x1800723c4  test    ax, ax
0x1800723c7  jz      short loc_1800723D6
0x1800723c9  mov     [rcx], ax
0x1800723cc  add     rcx, 2
0x1800723d0  sub     rdx, 1
0x1800723d4  jnz     short loc_1800723B3
0x1800723d6  lea     rax, [rcx-2]
0x1800723da  test    rdx, rdx
0x1800723dd  cmovnz  rax, rcx
0x1800723e1  mov     rcx, rdi
0x1800723e4  mov     [rax], bp
0x1800723e7  lea     rax, [rsp+288h+Name]
0x1800723ec  nop     dword ptr [rax+00h]
0x1800723f0  cmp     [rax], bp
0x1800723f3  jz      short loc_1800723FF
0x1800723f5  add     rax, 2
0x1800723f9  sub     rcx, 1
0x1800723fd  jnz     short loc_1800723F0
0x1800723ff  mov     rax, rdi
0x180072402  mov     esi, 7FFFFFFEh
0x180072407  sub     rax, rcx
0x18007240a  test    rcx, rcx
0x18007240d  cmovz   rax, rbp
0x180072411  jz      short loc_18007245F
0x180072413  mov     rdx, rdi
0x180072416  lea     rcx, [rsp+288h+Name]
0x18007241b  lea     rcx, [rcx+rax*2]
0x18007241f  sub     rdx, rax
0x180072422  jz      short loc_180072451
0x180072424  lea     r9, aP0; "_p0"
0x18007242b  mov     eax, esi
0x18007242d  sub     r9, rcx
0x180072430  test    rax, rax
0x180072433  jz      short loc_180072451
0x180072435  movzx   r8d, word ptr [rcx+r9]
0x18007243a  test    r8w, r8w
0x18007243e  jz      short loc_180072451
0x180072440  mov     [rcx], r8w
0x180072444  dec     rax
0x180072447  add     rcx, 2
0x18007244b  sub     rdx, 1
0x18007244f  jnz     short loc_180072430
0x180072451  test    rdx, rdx
0x180072454  lea     rax, [rcx-2]
0x180072458  cmovnz  rax, rcx
0x18007245c  mov     [rax], bp
0x18007245f  mov     [rsp+288h+arg_0], r14
0x180072467  lea     r8, [rsp+288h+Name]; lpName
0x18007246c  xor     edx, edx; bInheritHandle
0x18007246e  mov     [rsp+288h+var_38], r15
0x180072476  mov     ecx, 1F0003h; dwDesiredAccess
0x18007247b  call    cs:__imp_OpenSemaphoreW
0x180072481  mov     rbx, rax
0x180072484  test    rax, rax
0x180072487  jnz     short loc_1800724B1
0x180072489  call    cs:__imp_GetLastError
0x18007248f  cmp     eax, 2
0x180072492  jz      short loc_1800724F2
0x180072494  mov     rcx, [rsp+288h]; this
0x18007249c  lea     r8, aWil; "wil"
0x1800724a3  mov     edx, 0CDh; void *
0x1800724a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800724ad  mov     ebp, eax
0x1800724af  jmp     short loc_1800724F2
0x1800724b1  lea     rdx, [rsp+288h+var_268]; int *
0x1800724b6  mov     [rsp+288h+var_268], ebp; int
0x1800724ba  mov     rcx, rbx; hHandle
0x1800724bd  mov     [rsp+288h+var_264], ebp
0x1800724c1  mov     r14d, ebp
0x1800724c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800724c9  mov     r15d, eax
0x1800724cc  test    eax, eax
0x1800724ce  jns     short loc_18007252D
0x1800724d0  lfence
0x1800724d3  mov     rcx, [rsp+288h]; this
0x1800724db  lea     r8, aWil; "wil"
0x1800724e2  mov     r9d, eax; char *
0x1800724e5  mov     edx, 0D3h; void *
0x1800724ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800724ef  mov     ebp, r15d
0x1800724f2  test    rbx, rbx
0x1800724f5  jnz     loc_18007264F
0x1800724fb  mov     r15, [rsp+288h+var_38]
0x180072503  mov     eax, ebp
0x180072505  mov     r14, [rsp+288h+arg_0]
0x18007250d  mov     rcx, [rsp+288h+var_48]
0x180072515  xor     rcx, rsp; StackCookie
0x180072518  call    __security_check_cookie
0x18007251d  add     rsp, 258h
0x180072524  pop     r13
0x180072526  pop     r12
0x180072528  pop     rdi
0x180072529  pop     rsi
0x18007252a  pop     rbp
0x18007252b  pop     rbx
0x18007252c  retn
0x18007252d  test    r12b, r12b
0x180072530  jz      loc_18007262E
0x180072536  mov     rcx, rdi
0x180072539  lea     rax, [rsp+288h+Name]
0x18007253e  xchg    ax, ax
0x180072540  cmp     [rax], bp
0x180072543  jz      short loc_18007254F
0x180072545  add     rax, 2
0x180072549  sub     rcx, 1
0x18007254d  jnz     short loc_180072540
0x18007254f  mov     rax, rdi
0x180072552  sub     rax, rcx
0x180072555  test    rcx, rcx
0x180072558  cmovz   rax, rbp
0x18007255c  jz      short loc_1800725A2
0x18007255e  lea     rdx, [rsp+288h+Name]
0x180072563  lea     rdx, [rdx+rax*2]
0x180072567  sub     rdi, rax
0x18007256a  jz      short loc_180072594
0x18007256c  lea     rcx, asc_1802B9360; "h"
0x180072573  sub     rcx, rdx
0x180072576  test    rsi, rsi
0x180072579  jz      short loc_180072594
0x18007257b  movzx   eax, word ptr [rcx+rdx]
0x18007257f  test    ax, ax
0x180072582  jz      short loc_180072594
0x180072584  mov     [rdx], ax
0x180072587  dec     rsi
0x18007258a  add     rdx, 2
0x18007258e  sub     rdi, 1
0x180072592  jnz     short loc_180072576
0x180072594  test    rdi, rdi
0x180072597  lea     rax, [rdx-2]
0x18007259b  cmovnz  rax, rdx
0x18007259f  mov     [rax], bp
0x1800725a2  lea     r8, [rsp+288h+Name]; lpName
0x1800725a7  xor     edx, edx; bInheritHandle
0x1800725a9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800725ae  call    cs:__imp_OpenSemaphoreW
0x1800725b4  mov     rsi, rax
0x1800725b7  test    rax, rax
0x1800725ba  jnz     short loc_1800725DB
0x1800725bc  mov     rcx, [rsp+288h]; this
0x1800725c4  lea     r8, aWil; "wil"
0x1800725cb  mov     edx, 0D9h; void *
0x1800725d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800725d5  mov     edi, eax
0x1800725d7  mov     ebp, edi
0x1800725d9  jmp     short loc_18007264F
0x1800725db  lea     rdx, [rsp+288h+var_264]; int *
0x1800725e0  mov     rcx, rsi; hHandle
0x1800725e3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800725e8  mov     edi, eax
0x1800725ea  lfence
0x1800725ed  test    eax, eax
0x1800725ef  jns     short loc_18007261C
0x1800725f1  mov     rcx, [rsp+288h]; this
0x1800725f9  lea     r8, aWil; "wil"
0x180072600  mov     r9d, eax; char *
0x180072603  mov     edx, 0DBh; void *
0x180072608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007260d  mov     rcx, rsi; hObject
0x180072610  call    cs:__imp_CloseHandle
0x180072616  test    eax, eax
0x180072618  jz      short loc_18007267B
0x18007261a  jmp     short loc_1800725D7
0x18007261c  mov     rcx, rsi; hObject
0x18007261f  call    cs:__imp_CloseHandle
0x180072625  test    eax, eax
0x180072627  jz      short loc_180072661
0x180072629  mov     r14d, [rsp+288h+var_264]
0x18007262e  movsxd  rax, [rsp+288h+var_268]
0x180072633  movsxd  rcx, r14d
0x180072636  shl     rcx, 1Fh
0x18007263a  test    r13, r13
0x18007263d  jz      short loc_180072644
0x18007263f  mov     byte ptr [r13+0], 1
0x180072644  or      rax, rcx
0x180072647  mov     rcx, [rsp+288h+var_260]
0x18007264c  mov     [rcx], rax
0x18007264f  mov     rcx, rbx; hObject
0x180072652  call    cs:__imp_CloseHandle
0x180072658  test    eax, eax
0x18007265a  jz      short loc_180072695
0x18007265c  jmp     loc_1800724FB
0x180072661  mov     rcx, [rsp+288h]; this
0x180072669  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180072670  mov     edx, 9D1h; void *
0x180072675  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18007267b  mov     rcx, [rsp+288h]; this
0x180072683  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18007268a  mov     edx, 9D1h; void *
0x18007268f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180072695  mov     rcx, [rsp+288h]; this
0x18007269d  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800726a4  mov     edx, 9D1h; void *
0x1800726a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
