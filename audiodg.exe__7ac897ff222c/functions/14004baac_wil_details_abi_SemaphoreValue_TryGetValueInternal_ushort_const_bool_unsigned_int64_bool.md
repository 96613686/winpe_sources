# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14004baac`
- end: `0x14004bcbc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `528`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140061ec8`

## callees

- `0x14000c33c`
- `0x140016f30`
- `0x140021930`
- `0x140034cbc`
- `0x140037ed4`
- `0x14004baac`
- `0x14004c130`
- `0x14005d0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004bb79`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004bbe2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004bb79`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004bbe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bc76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bc76`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r9
  __int64 v7; // r10
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  wil::details *v12; // rax
  wil::details *v13; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  unsigned int LastError; // edi
  void *v17; // rdx
  wil::details *v18; // rax
  const char *v19; // r9
  wil::details *v20; // rdi
  int v21; // eax
  void *v22; // rdx
  int v23; // esi
  void *v24; // rdx
  void *v25; // rdx
  const char *v27; // r9
  size_t v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  v9 = 260;
  if ( v5 )
    v8 = v4;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    v11 = (260 - v9) & -(__int64)(v9 != 0);
    StringCopyWorkerW(&Name[v11], 260 - v11, (size_t *)v9, L"_p0", v28);
  }
  v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v13 = v12;
  if ( v12 )
  {
    v30[0] = 0;
    v29 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, v30);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v28);
LABEL_20:
      wil::details::CloseHandle(v13, v17);
      return LastError;
    }
    StringCchCatW(Name, v15, L"h");
    v18 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v18;
    if ( !v18 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v19);
      goto LABEL_20;
    }
    v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v29);
    v23 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v21,
        v28);
      wil::details::CloseHandle(v20, v24);
      LastError = v23;
      goto LABEL_20;
    }
    wil::details::CloseHandle(v20, v22);
    *a3 = v30[0] | (unsigned __int64)((__int64)v29 << 31);
    wil::details::CloseHandle(v13, v25);
    return 0;
  }
  if ( GetLastError() == 2 )
    return 0;
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v27);
}

```

## disassembly

```asm
0x14004baac  push    rbp
0x14004baae  push    rbx
0x14004baaf  push    rsi
0x14004bab0  push    rdi
0x14004bab1  push    r14
0x14004bab3  push    r15
0x14004bab5  lea     rbp, [rsp-168h]
0x14004babd  sub     rsp, 268h
0x14004bac4  mov     rax, cs:__security_cookie
0x14004bacb  xor     rax, rsp
0x14004bace  mov     [rbp+190h+var_40], rax
0x14004bad5  xor     r15d, r15d
0x14004bad8  lea     rax, [rsp+290h+Name]
0x14004badd  mov     edx, 104h
0x14004bae2  mov     [r8], r15
0x14004bae5  mov     r9d, edx
0x14004bae8  mov     r14, r8
0x14004baeb  mov     r10d, 7FFFFFFEh
0x14004baf1  test    r10, r10
0x14004baf4  jz      short loc_14004BB15
0x14004baf6  movzx   r8d, word ptr [rcx]
0x14004bafa  test    r8w, r8w
0x14004bafe  jz      short loc_14004BB15
0x14004bb00  mov     [rax], r8w
0x14004bb04  add     rcx, 2
0x14004bb08  add     rax, 2
0x14004bb0c  dec     r10
0x14004bb0f  sub     r9, 1
0x14004bb13  jnz     short loc_14004BAF1
0x14004bb15  lea     rcx, [rax-2]
0x14004bb19  test    r9, r9
0x14004bb1c  mov     r8, rdx
0x14004bb1f  cmovnz  rcx, rax
0x14004bb23  lea     rax, [rsp+290h+Name]
0x14004bb28  mov     [rcx], r15w
0x14004bb2c  cmp     [rax], r15w
0x14004bb30  jz      short loc_14004BB3C
0x14004bb32  add     rax, 2
0x14004bb36  sub     r8, 1; pcchNewDestLength
0x14004bb3a  jnz     short loc_14004BB2C
0x14004bb3c  mov     rcx, rdx
0x14004bb3f  mov     rax, r8
0x14004bb42  sub     rcx, r8
0x14004bb45  neg     rax
0x14004bb48  sbb     r9, r9
0x14004bb4b  and     r9, rcx
0x14004bb4e  test    r8, r8
0x14004bb51  jz      short loc_14004BB6B
0x14004bb53  sub     rdx, r9; cchDest
0x14004bb56  lea     rcx, [rsp+290h+Name]
0x14004bb5b  lea     rcx, [rcx+r9*2]; pszDest
0x14004bb5f  lea     r9, aP0; "_p0"
0x14004bb66  call    StringCopyWorkerW
0x14004bb6b  mov     esi, 1F0003h
0x14004bb70  lea     r8, [rsp+290h+Name]; lpName
0x14004bb75  mov     ecx, esi; dwDesiredAccess
0x14004bb77  xor     edx, edx; bInheritHandle
0x14004bb79  call    cs:__imp_OpenSemaphoreW
0x14004bb7f  mov     rbx, rax
0x14004bb82  test    rax, rax
0x14004bb85  jz      loc_14004BC76
0x14004bb8b  lea     rdx, [rsp+290h+var_25C]; int *
0x14004bb90  mov     [rsp+290h+var_25C], r15d
0x14004bb95  mov     rcx, rax; hHandle
0x14004bb98  mov     [rsp+290h+var_260], r15d
0x14004bb9d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14004bba2  mov     edi, eax
0x14004bba4  test    eax, eax
0x14004bba6  jns     short loc_14004BBC8
0x14004bba8  mov     rcx, [rbp+198h]; this
0x14004bbaf  lea     r8, aWil; "wil"
0x14004bbb6  mov     r9d, eax; char *
0x14004bbb9  mov     edx, 0D6h; void *
0x14004bbbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004bbc3  jmp     loc_14004BC6A
0x14004bbc8  lea     r8, asc_1400C716C; "h"
0x14004bbcf  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x14004bbd4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14004bbd9  lea     r8, [rsp+290h+Name]; lpName
0x14004bbde  xor     edx, edx; bInheritHandle
0x14004bbe0  mov     ecx, esi; dwDesiredAccess
0x14004bbe2  call    cs:__imp_OpenSemaphoreW
0x14004bbe8  mov     rdi, rax
0x14004bbeb  test    rax, rax
0x14004bbee  jz      short loc_14004BC50
0x14004bbf0  lea     rdx, [rsp+290h+var_260]; int *
0x14004bbf5  mov     rcx, rax; hHandle
0x14004bbf8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14004bbfd  mov     esi, eax
0x14004bbff  test    eax, eax
0x14004bc01  jns     short loc_14004BC2A
0x14004bc03  mov     rcx, [rbp+198h]; this
0x14004bc0a  lea     r8, aWil; "wil"
0x14004bc11  mov     r9d, eax; char *
0x14004bc14  mov     edx, 0DEh; void *
0x14004bc19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004bc1e  mov     rcx, rdi; this
0x14004bc21  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14004bc26  mov     edi, esi
0x14004bc28  jmp     short loc_14004BC6A
0x14004bc2a  mov     rcx, rdi; this
0x14004bc2d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14004bc32  movsxd  rax, [rsp+290h+var_25C]
0x14004bc37  movsxd  rcx, [rsp+290h+var_260]
0x14004bc3c  shl     rcx, 1Fh
0x14004bc40  or      rcx, rax
0x14004bc43  mov     [r14], rcx
0x14004bc46  mov     rcx, rbx; this
0x14004bc49  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14004bc4e  jmp     short loc_14004BC81
0x14004bc50  mov     rcx, [rbp+198h]; this
0x14004bc57  lea     r8, aWil; "wil"
0x14004bc5e  mov     edx, 0DCh; void *
0x14004bc63  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004bc68  mov     edi, eax
0x14004bc6a  mov     rcx, rbx; this
0x14004bc6d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14004bc72  mov     eax, edi
0x14004bc74  jmp     short loc_14004BC9D
0x14004bc76  call    cs:__imp_GetLastError
0x14004bc7c  cmp     eax, 2
0x14004bc7f  jnz     short loc_14004BC85
0x14004bc81  xor     eax, eax
0x14004bc83  jmp     short loc_14004BC9D
0x14004bc85  mov     rcx, [rbp+198h]; this
0x14004bc8c  lea     r8, aWil; "wil"
0x14004bc93  mov     edx, 0D0h; void *
0x14004bc98  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004bc9d  mov     rcx, [rbp+190h+var_40]
0x14004bca4  xor     rcx, rsp; StackCookie
0x14004bca7  call    __security_check_cookie
0x14004bcac  add     rsp, 268h
0x14004bcb3  pop     r15
0x14004bcb5  pop     r14
0x14004bcb7  pop     rdi
0x14004bcb8  pop     rsi
0x14004bcb9  pop     rbx
0x14004bcba  pop     rbp
0x14004bcbb  retn
```
