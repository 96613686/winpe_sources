# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180002a84`
- end: `0x180002d4b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `711`
- prototype: `HRESULT __fastcall(const wchar_t *name, bool value, unsigned __int64 *name, bool *is64Bit)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001f20`
- `0x180001fa4`

## callees

- `0x180002a84`
- `0x180002d54`
- `0x18000308c`
- `0x180021efc`
- `0x180022528`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ca0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002b90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002c43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002b90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002c43`

## pseudocode

```c
HRESULT __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *name,
        bool value,
        unsigned __int64 *a3,
        bool *is64Bit)
{
  wchar_t *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // rax
  __int64 v13; // r8
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  wchar_t *v16; // rdx
  __int64 v17; // rax
  wchar_t *v18; // rcx
  HANDLE v19; // rax
  void *v20; // rdi
  HRESULT ValueFromSemaphore; // eax
  HRESULT LastError; // esi
  __int64 v23; // rdx
  wchar_t *v24; // rax
  __int64 v25; // r8
  wchar_t *v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // rbx
  wchar_t *v29; // rdx
  HANDLE v30; // rax
  void *v31; // rbx
  HRESULT v33; // eax
  int countHigh; // [rsp+20h] [rbp-E0h] BYREF
  int countLow[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t localName[264]; // [rsp+30h] [rbp-D0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  v4 = localName;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*name )
      break;
    *v4++ = *name++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = localName;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &localName[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = OpenSemaphoreW(0x1F0003u, 0, localName);
  v20 = v19;
  if ( v19 )
  {
    countLow[0] = 0;
    countHigh = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, countLow);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xD6u, "wil", ValueFromSemaphore);
      goto LABEL_33;
    }
    v23 = 260;
    v24 = localName;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v23;
    }
    while ( v23 );
    v25 = (260 - v23) & -(__int64)(v23 != 0);
    if ( v23 )
    {
      v26 = &localName[v25];
      v27 = L"h";
      v28 = 260 - v25;
      if ( 260 != v25 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v27 )
            break;
          *v26++ = *v27++;
          --v5;
          --v28;
        }
        while ( v28 );
      }
      v29 = v26 - 1;
      if ( v28 )
        v29 = v26;
      *v29 = 0;
    }
    v30 = OpenSemaphoreW(0x1F0003u, 0, localName);
    v31 = v30;
    if ( !v30 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xDCu, "wil");
LABEL_33:
      wil::details::CloseHandle(v20);
      return LastError;
    }
    v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &countHigh);
    LastError = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xDEu, "wil", v33);
      wil::details::CloseHandle(v31);
      goto LABEL_33;
    }
    wil::details::CloseHandle(v31);
    *a3 = countLow[0] | (unsigned __int64)((__int64)countHigh << 31);
    wil::details::CloseHandle(v20);
  }
  else if ( GetLastError() != 2 )
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, 0xD0u, "wil");
  }
  return 0;
}

```

## disassembly

```asm
0x180002a84  mov     [rsp-8+arg_0], rbx
0x180002a89  mov     [rsp-8+arg_8], rsi
0x180002a8e  push    rbp
0x180002a8f  push    rdi
0x180002a90  push    r12
0x180002a92  push    r14
0x180002a94  push    r15
0x180002a96  lea     rbp, [rsp-150h]
0x180002a9e  sub     rsp, 250h
0x180002aa5  mov     rax, cs:__security_cookie
0x180002aac  xor     rax, rsp
0x180002aaf  mov     [rbp+170h+var_30], rax
0x180002ab6  xor     r12d, r12d
0x180002ab9  lea     rax, [rsp+270h+localName]
0x180002abe  mov     r14d, 7FFFFFFEh
0x180002ac4  mov     [value], r12
0x180002ac7  mov     ebx, 104h
0x180002acc  mov     r9d, r14d
0x180002acf  mov     edx, ebx
0x180002ad1  mov     r15, value
0x180002ad4  test    r9, r9
0x180002ad7  jz      short loc_180002AF8
0x180002ad9  movzx   r8d, word ptr [name]
0x180002add  test    r8w, r8w
0x180002ae1  jz      short loc_180002AF8
0x180002ae3  mov     [rax], r8w
0x180002ae7  add     name, 2
0x180002aeb  add     rax, 2
0x180002aef  dec     r9
0x180002af2  sub     rdx, 1
0x180002af6  jnz     short loc_180002AD4
0x180002af8  test    rdx, rdx
0x180002afb  lea     name, [rax-2]
0x180002aff  mov     rdx, rbx
0x180002b02  cmovnz  name, rax
0x180002b06  lea     rax, [rsp+270h+localName]
0x180002b0b  mov     [name], r12w
0x180002b0f  cmp     [rax], r12w
0x180002b13  jz      short loc_180002B1F
0x180002b15  add     rax, 2
0x180002b19  sub     rdx, 1
0x180002b1d  jnz     short loc_180002B0F
0x180002b1f  mov     name, rbx
0x180002b22  mov     rax, rdx
0x180002b25  sub     name, rdx
0x180002b28  neg     rax
0x180002b2b  sbb     value, value
0x180002b2e  and     value, name
0x180002b31  test    rdx, rdx
0x180002b34  jz      short loc_180002B84
0x180002b36  mov     rax, rbx
0x180002b39  lea     rdx, [rsp+270h+localName]
0x180002b3e  lea     r9, aP0; "_p0"
0x180002b45  mov     name, r14
0x180002b48  lea     rdx, [rdx+value*2]
0x180002b4c  sub     rax, value
0x180002b4f  jz      short loc_180002B75
0x180002b51  test    name, name
0x180002b54  jz      short loc_180002B75
0x180002b56  movzx   r8d, word ptr [r9]
0x180002b5a  test    r8w, r8w
0x180002b5e  jz      short loc_180002B75
0x180002b60  mov     [rdx], r8w
0x180002b64  add     r9, 2
0x180002b68  add     rdx, 2
0x180002b6c  dec     name
0x180002b6f  sub     rax, 1
0x180002b73  jnz     short loc_180002B51
0x180002b75  test    rax, rax
0x180002b78  lea     name, [rdx-2]
0x180002b7c  cmovnz  name, rdx
0x180002b80  mov     [name], r12w
0x180002b84  lea     value, [rsp+270h+localName]; lpName
0x180002b89  xor     edx, edx; bInheritHandle
0x180002b8b  mov     ecx, 1F0003h; dwDesiredAccess
0x180002b90  call    cs:__imp_OpenSemaphoreW
0x180002b96  mov     rdi, rax
0x180002b99  test    rax, rax
0x180002b9c  jz      loc_180002CA0
0x180002ba2  lea     rdx, [rsp+270h+countLow]; count
0x180002ba7  mov     [rsp+270h+countLow], r12d
0x180002bac  mov     name, rax; semaphore
0x180002baf  mov     [rsp+270h+countHigh], r12d
0x180002bb4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180002bb9  mov     esi, eax
0x180002bbb  test    eax, eax
0x180002bbd  js      loc_180002D2B
0x180002bc3  mov     rdx, rbx
0x180002bc6  lea     rax, [rsp+270h+localName]
0x180002bcb  cmp     [rax], r12w
0x180002bcf  jz      short loc_180002BDB
0x180002bd1  add     rax, 2
0x180002bd5  sub     rdx, 1
0x180002bd9  jnz     short loc_180002BCB
0x180002bdb  mov     name, rbx
0x180002bde  mov     rax, rdx
0x180002be1  sub     name, rdx
0x180002be4  neg     rax
0x180002be7  sbb     value, value
0x180002bea  and     value, name
0x180002bed  test    rdx, rdx
0x180002bf0  jz      short loc_180002C37
0x180002bf2  lea     rax, [rsp+270h+localName]
0x180002bf7  lea     rax, [rax+value*2]
0x180002bfb  lea     name, asc_18004B964; "h"
0x180002c02  sub     rbx, value
0x180002c05  jz      short loc_180002C28
0x180002c07  test    r14, r14
0x180002c0a  jz      short loc_180002C28
0x180002c0c  movzx   edx, word ptr [name]
0x180002c0f  test    dx, dx
0x180002c12  jz      short loc_180002C28
0x180002c14  mov     [rax], dx
0x180002c17  add     name, 2
0x180002c1b  add     rax, 2
0x180002c1f  dec     r14
0x180002c22  sub     rbx, 1
0x180002c26  jnz     short loc_180002C07
0x180002c28  test    rbx, rbx
0x180002c2b  lea     rdx, [rax-2]
0x180002c2f  cmovnz  rdx, rax
0x180002c33  mov     [rdx], r12w
0x180002c37  lea     value, [rsp+270h+localName]; lpName
0x180002c3c  xor     edx, edx; bInheritHandle
0x180002c3e  mov     ecx, 1F0003h; dwDesiredAccess
0x180002c43  call    cs:__imp_OpenSemaphoreW
0x180002c49  mov     rbx, rax
0x180002c4c  test    rax, rax
0x180002c4f  jnz     short loc_180002CC5
0x180002c51  mov     name, [rbp+178h]; callerReturnAddress
0x180002c58  lea     value, fileName; "wil"
0x180002c5f  mov     edx, 0DCh; lineNumber
0x180002c64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002c69  mov     esi, eax
0x180002c6b  mov     name, rdi; handle
0x180002c6e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002c73  mov     eax, esi
0x180002c75  mov     name, [rbp+170h+var_30]
0x180002c7c  xor     name, rsp; StackCookie
0x180002c7f  call    __security_check_cookie
0x180002c84  lea     r11, [rsp+270h+var_20]
0x180002c8c  mov     rbx, [r11+30h]
0x180002c90  mov     rsi, [r11+38h]
0x180002c94  mov     rsp, r11
0x180002c97  pop     r15
0x180002c99  pop     r14
0x180002c9b  pop     r12
0x180002c9d  pop     rdi
0x180002c9e  pop     rbp
0x180002c9f  retn
0x180002ca0  call    cs:__imp_GetLastError
0x180002ca6  cmp     eax, 2
0x180002ca9  jz      short loc_180002CFC
0x180002cab  mov     name, [rbp+178h]; callerReturnAddress
0x180002cb2  lea     value, fileName; "wil"
0x180002cb9  mov     edx, 0D0h; lineNumber
0x180002cbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002cc3  jmp     short loc_180002C75
0x180002cc5  lea     rdx, [rsp+270h+countHigh]; count
0x180002cca  mov     name, rbx; semaphore
0x180002ccd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180002cd2  mov     esi, eax
0x180002cd4  test    eax, eax
0x180002cd6  js      short loc_180002D03
0x180002cd8  mov     name, rbx; handle
0x180002cdb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002ce0  movsxd  rax, [rsp+270h+countLow]
0x180002ce5  movsxd  name, [rsp+270h+countHigh]
0x180002cea  shl     name, 1Fh
0x180002cee  or      name, rax
0x180002cf1  mov     [r15], name
0x180002cf4  mov     name, rdi; handle
0x180002cf7  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002cfc  xor     eax, eax
0x180002cfe  jmp     loc_180002C75
0x180002d03  mov     name, [rbp+178h]; callerReturnAddress
0x180002d0a  lea     value, fileName; "wil"
0x180002d11  mov     r9d, eax; hr
0x180002d14  mov     edx, 0DEh; lineNumber
0x180002d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d1e  mov     name, rbx; handle
0x180002d21  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002d26  jmp     loc_180002C6B
0x180002d2b  mov     name, [rbp+178h]; callerReturnAddress
0x180002d32  lea     value, fileName; "wil"
0x180002d39  mov     r9d, eax; hr
0x180002d3c  mov     edx, 0D6h; lineNumber
0x180002d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d46  jmp     loc_180002C6B
```
