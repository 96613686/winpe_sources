# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x1400498d4`
- end: `0x140049b2d`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `601`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140043310`
- `0x14004d05c`

## callees

- `0x140005240`
- `0x140016098`
- `0x1400317a8`
- `0x1400317c8`
- `0x1400317e8`
- `0x1400498d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049959`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049a34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049959`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049a34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049927`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049927`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400499c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400499c5`

## string_xrefs

- `0x14004999a`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x1400499f0`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x140049a53`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x140049adc`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, struct CLMString *a3)
{
  HKEY v6; // rcx
  DWORD v7; // ecx
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  WCHAR *Buffer; // rax
  DWORD v11; // eax
  unsigned int v12; // eax
  BYTE *v13; // rax
  unsigned __int64 v14; // rdi
  wchar_t *v15; // rax
  unsigned __int64 v16; // rdi
  __int64 v17; // rcx
  BYTE *v18; // rdx
  wchar_t v19; // r8
  wchar_t *v20; // rcx
  __int64 v21; // r9
  unsigned int lpData; // [rsp+20h] [rbp-268h]
  DWORD cbData; // [rsp+30h] [rbp-258h] BYREF
  DWORD Type; // [rsp+34h] [rbp-254h] BYREF
  __int64 v26; // [rsp+38h] [rbp-250h]
  WCHAR Data[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v26 = -2;
  SetLastError(0);
  Type = 0;
  v6 = (HKEY)*((_QWORD *)this + 22);
  if ( !v6 )
  {
    v7 = 6;
LABEL_3:
    SetLastError(v7);
    return 0;
  }
  cbData = 520;
  v8 = RegQueryValueExW(v6, a2, 0, &Type, (LPBYTE)Data, &cbData);
  v9 = v8;
  if ( v8 && v8 != 234 || Type - 1 > 1 && Type != 7 )
  {
    v7 = v8;
    goto LABEL_3;
  }
  try
  {
    if ( Type == 2 )
    {
      if ( v8 == 234 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      Buffer = CLMString::GetBuffer(a3, 260);
      v11 = ExpandEnvironmentStringsW(Data, Buffer, 0x104u);
      cbData = v11;
      if ( v11 - 1 > 0x102 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      v12 = 2 * v11;
      cbData = v12;
    }
    else
    {
      if ( v8 == 234 )
      {
        v13 = (BYTE *)CLMString::GetBuffer(a3, cbData >> 1);
        v9 = RegQueryValueExW(*((HKEY *)this + 22), a2, 0, &Type, v13, &cbData);
      }
      else
      {
        v14 = cbData;
        v15 = CLMString::GetBuffer(a3, cbData >> 1);
        v16 = v14 >> 1;
        if ( v16 )
        {
          v17 = 2147483646;
          v18 = (BYTE *)Data;
          do
          {
            if ( !v17 )
              break;
            v19 = *(_WORD *)v18;
            if ( !*(_WORD *)v18 )
              break;
            v18 += 2;
            *v15++ = v19;
            --v17;
            --v16;
          }
          while ( v16 );
          v20 = v15 - 1;
          if ( v16 )
            v20 = v15;
          *v20 = 0;
          v21 = v16 == 0 ? 0x8007007A : 0;
        }
        else
        {
          v21 = 2147942487LL;
        }
        if ( (int)v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F8,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
            (const char *)v21,
            lpData);
      }
      v12 = cbData;
    }
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
        (const char *)v9,
        lpData);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      770,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  cbData = v12 >> 1;
  CLMString::Truncate(a3, v12 >> 1 != 0 ? (v12 >> 1) - 1 : 0);
  return 1;
}

```

## disassembly

```asm
0x1400498d4  push    rbx
0x1400498d6  push    rsi
0x1400498d7  push    rdi
0x1400498d8  push    r14
0x1400498da  push    r15
0x1400498dc  sub     rsp, 260h
0x1400498e3  mov     [rsp+288h+var_250], 0FFFFFFFFFFFFFFFEh
0x1400498ec  mov     rax, cs:__security_cookie
0x1400498f3  xor     rax, rsp
0x1400498f6  mov     [rsp+288h+var_38], rax
0x1400498fe  mov     rsi, r8
0x140049901  mov     rdi, rdx
0x140049904  mov     r14, rcx
0x140049907  xor     ecx, ecx; dwErrCode
0x140049909  call    cs:__imp_SetLastError
0x14004990f  xor     r15d, r15d
0x140049912  mov     [rsp+288h+Type], r15d
0x140049917  mov     rcx, [r14+0B0h]; hKey
0x14004991e  test    rcx, rcx
0x140049921  jnz     short loc_140049932
0x140049923  lea     ecx, [r15+6]; dwErrCode
0x140049927  call    cs:__imp_SetLastError
0x14004992d  jmp     loc_140049B0C
0x140049932  mov     [rsp+288h+cbData], 208h
0x14004993a  lea     rax, [rsp+288h+cbData]
0x14004993f  mov     [rsp+288h+lpcbData], rax; lpcbData
0x140049944  lea     rax, [rsp+288h+Data]
0x140049949  mov     [rsp+288h+lpData], rax; int
0x14004994e  lea     r9, [rsp+288h+Type]; lpType
0x140049953  xor     r8d, r8d; lpReserved
0x140049956  mov     rdx, rdi; lpValueName
0x140049959  call    cs:__imp_RegQueryValueExW
0x14004995f  mov     ebx, eax
0x140049961  mov     ecx, 0EAh
0x140049966  test    eax, eax
0x140049968  jz      short loc_14004996E
0x14004996a  cmp     eax, ecx
0x14004996c  jnz     short loc_14004997F
0x14004996e  mov     edx, [rsp+288h+Type]
0x140049972  lea     eax, [rdx-1]
0x140049975  cmp     eax, 1
0x140049978  jbe     short loc_140049983
0x14004997a  cmp     edx, 7
0x14004997d  jz      short loc_140049983
0x14004997f  mov     ecx, ebx
0x140049981  jmp     short loc_140049927
0x140049983  cmp     edx, 2
0x140049986  jnz     short loc_140049A01
0x140049988  cmp     ebx, ecx
0x14004998a  jnz     short loc_1400499AB
0x14004998c  mov     rcx, [rsp+288h]; this
0x140049994  mov     r9d, 0CEh; char *
0x14004999a  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400499a1  mov     edx, 2E3h; void *
0x1400499a6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400499ab  mov     edi, 104h
0x1400499b0  mov     edx, edi; int
0x1400499b2  mov     rcx, rsi; this
0x1400499b5  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1400499ba  mov     r8d, edi; nSize
0x1400499bd  mov     rdx, rax; lpDst
0x1400499c0  lea     rcx, [rsp+288h+Data]; lpSrc
0x1400499c5  call    cs:__imp_ExpandEnvironmentStringsW
0x1400499cb  mov     [rsp+288h+cbData], eax
0x1400499cf  lea     ecx, [rax-1]
0x1400499d2  cmp     ecx, 102h
0x1400499d8  ja      short loc_1400499E2
0x1400499da  add     eax, eax
0x1400499dc  mov     [rsp+288h+cbData], eax
0x1400499e0  jmp     short loc_140049A40
0x1400499e2  mov     rcx, [rsp+288h]; this
0x1400499ea  mov     r9d, 0CEh; char *
0x1400499f0  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400499f7  mov     edx, 2E9h; void *
0x1400499fc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140049a01  cmp     ebx, ecx
0x140049a03  mov     rcx, rsi; this
0x140049a06  jnz     short loc_140049A64
0x140049a08  mov     edx, [rsp+288h+cbData]
0x140049a0c  shr     edx, 1; int
0x140049a0e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x140049a13  lea     rcx, [rsp+288h+cbData]
0x140049a18  mov     [rsp+288h+lpcbData], rcx; lpcbData
0x140049a1d  mov     [rsp+288h+lpData], rax; unsigned int
0x140049a22  lea     r9, [rsp+288h+Type]; lpType
0x140049a27  xor     r8d, r8d; lpReserved
0x140049a2a  mov     rdx, rdi; lpValueName
0x140049a2d  mov     rcx, [r14+0B0h]; hKey
0x140049a34  call    cs:__imp_RegQueryValueExW
0x140049a3a  mov     ebx, eax
0x140049a3c  mov     eax, [rsp+288h+cbData]
0x140049a40  test    ebx, ebx
0x140049a42  jz      loc_140049AEE
0x140049a48  mov     rcx, [rsp+288h]; this
0x140049a50  mov     r9d, ebx; char *
0x140049a53  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x140049a5a  mov     edx, 2FDh; void *
0x140049a5f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140049a64  mov     edx, [rsp+288h+cbData]
0x140049a68  mov     edi, edx
0x140049a6a  shr     edx, 1; int
0x140049a6c  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x140049a71  shr     rdi, 1
0x140049a74  jz      short loc_140049AC5
0x140049a76  mov     ecx, 7FFFFFFEh
0x140049a7b  lea     rdx, [rsp+288h+Data]
0x140049a80  test    rcx, rcx
0x140049a83  jz      short loc_140049AA4
0x140049a85  movzx   r8d, word ptr [rdx]
0x140049a89  test    r8w, r8w
0x140049a8d  jz      short loc_140049AA4
0x140049a8f  add     rdx, 2
0x140049a93  mov     [rax], r8w
0x140049a97  add     rax, 2
0x140049a9b  dec     rcx
0x140049a9e  sub     rdi, 1
0x140049aa2  jnz     short loc_140049A80
0x140049aa4  lea     rcx, [rax-2]
0x140049aa8  test    rdi, rdi
0x140049aab  cmovnz  rcx, rax
0x140049aaf  mov     [rcx], r15w
0x140049ab3  neg     rdi
0x140049ab6  sbb     r9d, r9d
0x140049ab9  not     r9d
0x140049abc  and     r9d, 8007007Ah
0x140049ac3  jmp     short loc_140049ACB
0x140049ac5  mov     r9d, 80070057h; char *
0x140049acb  mov     rcx, [rsp+288h]; this
0x140049ad3  test    r9d, r9d
0x140049ad6  jns     loc_140049A3C
0x140049adc  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x140049ae3  mov     edx, 2F8h; void *
0x140049ae8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140049aee  shr     eax, 1
0x140049af0  mov     [rsp+288h+cbData], eax
0x140049af4  lea     ecx, [rax-1]
0x140049af7  neg     eax
0x140049af9  sbb     edx, edx
0x140049afb  and     edx, ecx; unsigned int
0x140049afd  mov     rcx, rsi; this
0x140049b00  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x140049b05  mov     eax, 1
0x140049b0a  jmp     short loc_140049B0E
0x140049b0c  xor     eax, eax
0x140049b0e  mov     rcx, [rsp+288h+var_38]
0x140049b16  xor     rcx, rsp; StackCookie
0x140049b19  call    __security_check_cookie
0x140049b1e  add     rsp, 260h
0x140049b25  pop     r15
0x140049b27  pop     r14
0x140049b29  pop     rdi
0x140049b2a  pop     rsi
0x140049b2b  pop     rbx
0x140049b2c  retn
```
