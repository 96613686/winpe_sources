# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x18002aa4c`
- end: `0x18002ac9b`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `591`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x180002300`
- `0x18001db68`
- `0x180022670`
- `0x18002aa4c`
- `0x18002af8c`
- `0x18002b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aaca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aba9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aaca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aba9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ab36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ab36`

## string_xrefs

- `0x18002ab0b`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18002ab61`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18002abc8`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, struct CLMString *a3)
{
  HKEY v5; // rcx
  DWORD v6; // ecx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  WCHAR *Buffer; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  BYTE *v12; // rax
  unsigned __int64 v13; // rdi
  wchar_t *v14; // rax
  BYTE *v15; // rdx
  __int64 v16; // r8
  unsigned __int64 v17; // rdi
  __int64 v18; // rcx
  wchar_t *v19; // rcx
  __int64 v20; // r9
  unsigned int lpData; // [rsp+20h] [rbp-258h]
  DWORD cbData; // [rsp+30h] [rbp-248h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-244h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  SetLastError(0);
  Type[0] = 0;
  v5 = (HKEY)*((_QWORD *)this + 22);
  if ( !v5 )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  cbData = 520;
  v7 = RegQueryValueExW(v5, L"Content Type", 0, Type, (LPBYTE)Data, &cbData);
  v8 = v7;
  if ( v7 && v7 != 234 || Type[0] - 1 > 1 && Type[0] != 7 )
  {
    v6 = v7;
    goto LABEL_3;
  }
  try
  {
    if ( Type[0] == 2 )
    {
      if ( v7 == 234 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      Buffer = CLMString::GetBuffer(a3, 260);
      v10 = ExpandEnvironmentStringsW(Data, Buffer, 0x104u);
      cbData = v10;
      if ( v10 - 1 > 0x102 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      v11 = 2 * v10;
      cbData = v11;
    }
    else
    {
      if ( v7 == 234 )
      {
        v12 = (BYTE *)CLMString::GetBuffer(a3, cbData >> 1);
        v8 = RegQueryValueExW(*((HKEY *)this + 22), L"Content Type", 0, Type, v12, &cbData);
      }
      else
      {
        v13 = cbData;
        v14 = CLMString::GetBuffer(a3, cbData >> 1);
        v17 = v13 >> 1;
        if ( v17 )
        {
          v18 = 2147483646;
          v15 = (BYTE *)Data;
          do
          {
            if ( !v18 )
              break;
            v16 = *(unsigned __int16 *)v15;
            if ( !(_WORD)v16 )
              break;
            v15 += 2;
            *v14++ = v16;
            --v18;
            --v17;
          }
          while ( v17 );
          v19 = v14 - 1;
          if ( v17 )
            v19 = v14;
          *v19 = 0;
          v20 = v17 == 0 ? 0x8007007A : 0;
        }
        else
        {
          v20 = 2147942487LL;
        }
        if ( (int)v20 < 0 )
          wil::details::in1diag3::_Throw_Hr(retaddr, v15, v16, (const char *)v20, lpData);
      }
      v11 = cbData;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
        (const char *)v8,
        lpData);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      770,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  cbData = v11 >> 1;
  CLMString::Truncate(a3, v11 >> 1 != 0 ? (v11 >> 1) - 1 : 0);
  return 1;
}

```

## disassembly

```asm
0x18002aa4c  mov     [rsp+arg_8], rbx
0x18002aa51  push    rsi
0x18002aa52  push    rdi
0x18002aa53  push    r14
0x18002aa55  sub     rsp, 260h
0x18002aa5c  mov     rax, cs:__security_cookie
0x18002aa63  xor     rax, rsp
0x18002aa66  mov     [rsp+278h+var_28], rax
0x18002aa6e  mov     rsi, r8
0x18002aa71  mov     rdi, rcx
0x18002aa74  xor     ecx, ecx; dwErrCode
0x18002aa76  call    cs:__imp_SetLastError
0x18002aa7c  xor     r14d, r14d
0x18002aa7f  mov     [rsp+278h+Type], r14d
0x18002aa84  mov     rcx, [rdi+0B0h]; hKey
0x18002aa8b  test    rcx, rcx
0x18002aa8e  jnz     short loc_18002AA9F
0x18002aa90  lea     ecx, [r14+6]; dwErrCode
0x18002aa94  call    cs:__imp_SetLastError
0x18002aa9a  jmp     loc_18002AC75
0x18002aa9f  mov     [rsp+278h+cbData], 208h
0x18002aaa7  lea     rax, [rsp+278h+cbData]
0x18002aaac  mov     [rsp+278h+lpcbData], rax; lpcbData
0x18002aab1  lea     rax, [rsp+278h+Data]
0x18002aab6  mov     [rsp+278h+lpData], rax; int
0x18002aabb  lea     r9, [rsp+278h+Type]; lpType
0x18002aac0  xor     r8d, r8d; lpReserved
0x18002aac3  lea     rdx, ValueName; "Content Type"
0x18002aaca  call    cs:__imp_RegQueryValueExW
0x18002aad0  mov     ebx, eax
0x18002aad2  mov     ecx, 0EAh
0x18002aad7  test    eax, eax
0x18002aad9  jz      short loc_18002AADF
0x18002aadb  cmp     eax, ecx
0x18002aadd  jnz     short loc_18002AAF0
0x18002aadf  mov     edx, [rsp+278h+Type]
0x18002aae3  lea     eax, [rdx-1]
0x18002aae6  cmp     eax, 1
0x18002aae9  jbe     short loc_18002AAF4
0x18002aaeb  cmp     edx, 7
0x18002aaee  jz      short loc_18002AAF4
0x18002aaf0  mov     ecx, ebx
0x18002aaf2  jmp     short loc_18002AA94
0x18002aaf4  cmp     edx, 2
0x18002aaf7  jnz     short loc_18002AB72
0x18002aaf9  cmp     ebx, ecx
0x18002aafb  jnz     short loc_18002AB1C
0x18002aafd  mov     rcx, [rsp+278h]; this
0x18002ab05  mov     r9d, 0CEh; char *
0x18002ab0b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002ab12  mov     edx, 2E3h; void *
0x18002ab17  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ab1c  mov     edi, 104h
0x18002ab21  mov     edx, edi; int
0x18002ab23  mov     rcx, rsi; this
0x18002ab26  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18002ab2b  mov     r8d, edi; nSize
0x18002ab2e  mov     rdx, rax; lpDst
0x18002ab31  lea     rcx, [rsp+278h+Data]; lpSrc
0x18002ab36  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ab3c  mov     [rsp+278h+cbData], eax
0x18002ab40  lea     ecx, [rax-1]
0x18002ab43  cmp     ecx, 102h
0x18002ab49  ja      short loc_18002AB53
0x18002ab4b  add     eax, eax
0x18002ab4d  mov     [rsp+278h+cbData], eax
0x18002ab51  jmp     short loc_18002ABB5
0x18002ab53  mov     rcx, [rsp+278h]; this
0x18002ab5b  mov     r9d, 0CEh; char *
0x18002ab61  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002ab68  mov     edx, 2E9h; void *
0x18002ab6d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ab72  cmp     ebx, ecx
0x18002ab74  mov     rcx, rsi; this
0x18002ab77  jnz     short loc_18002ABD9
0x18002ab79  mov     edx, [rsp+278h+cbData]
0x18002ab7d  shr     edx, 1; int
0x18002ab7f  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18002ab84  lea     rcx, [rsp+278h+cbData]
0x18002ab89  mov     [rsp+278h+lpcbData], rcx; lpcbData
0x18002ab8e  mov     [rsp+278h+lpData], rax; unsigned int
0x18002ab93  lea     r9, [rsp+278h+Type]; lpType
0x18002ab98  xor     r8d, r8d; lpReserved
0x18002ab9b  lea     rdx, ValueName; "Content Type"
0x18002aba2  mov     rcx, [rdi+0B0h]; hKey
0x18002aba9  call    cs:__imp_RegQueryValueExW
0x18002abaf  mov     ebx, eax
0x18002abb1  mov     eax, [rsp+278h+cbData]
0x18002abb5  test    ebx, ebx
0x18002abb7  jz      loc_18002AC57
0x18002abbd  mov     rcx, [rsp+278h]; this
0x18002abc5  mov     r9d, ebx; char *
0x18002abc8  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002abcf  mov     edx, 2FDh; void *
0x18002abd4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002abd9  mov     edx, [rsp+278h+cbData]
0x18002abdd  mov     edi, edx
0x18002abdf  shr     edx, 1; int
0x18002abe1  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18002abe6  shr     rdi, 1
0x18002abe9  jz      short loc_18002AC3A
0x18002abeb  mov     ecx, 7FFFFFFEh
0x18002abf0  lea     rdx, [rsp+278h+Data]
0x18002abf5  test    rcx, rcx
0x18002abf8  jz      short loc_18002AC19
0x18002abfa  movzx   r8d, word ptr [rdx]
0x18002abfe  test    r8w, r8w
0x18002ac02  jz      short loc_18002AC19
0x18002ac04  add     rdx, 2
0x18002ac08  mov     [rax], r8w
0x18002ac0c  add     rax, 2
0x18002ac10  dec     rcx
0x18002ac13  sub     rdi, 1
0x18002ac17  jnz     short loc_18002ABF5
0x18002ac19  lea     rcx, [rax-2]
0x18002ac1d  test    rdi, rdi
0x18002ac20  cmovnz  rcx, rax
0x18002ac24  mov     [rcx], r14w
0x18002ac28  neg     rdi
0x18002ac2b  sbb     r9d, r9d
0x18002ac2e  not     r9d
0x18002ac31  and     r9d, 8007007Ah
0x18002ac38  jmp     short loc_18002AC40
0x18002ac3a  mov     r9d, 80070057h; char *
0x18002ac40  mov     rcx, [rsp+278h]; this
0x18002ac48  test    r9d, r9d
0x18002ac4b  jns     loc_18002ABB1
0x18002ac51  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002ac57  shr     eax, 1
0x18002ac59  mov     [rsp+278h+cbData], eax
0x18002ac5d  lea     ecx, [rax-1]
0x18002ac60  neg     eax
0x18002ac62  sbb     edx, edx
0x18002ac64  and     edx, ecx; unsigned int
0x18002ac66  mov     rcx, rsi; this
0x18002ac69  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18002ac6e  mov     eax, 1
0x18002ac73  jmp     short loc_18002AC77
0x18002ac75  xor     eax, eax
0x18002ac77  mov     rcx, [rsp+278h+var_28]
0x18002ac7f  xor     rcx, rsp; StackCookie
0x18002ac82  call    __security_check_cookie
0x18002ac87  mov     rbx, [rsp+278h+arg_8]
0x18002ac8f  add     rsp, 260h
0x18002ac96  pop     r14
0x18002ac98  pop     rdi
0x18002ac99  pop     rsi
0x18002ac9a  retn
```
