# SCRIPT_MAP_CUSTOM_MAPPER::AddScriptMap(INativeConfigurationElement *,ushort const *,MULTISZ *)

- ea: `0x18001bd50`
- end: `0x18001c023`
- name: `?AddScriptMap@SCRIPT_MAP_CUSTOM_MAPPER@@AEAAJPEAVINativeConfigurationElement@@PEBGPEAVMULTISZ@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(SCRIPT_MAP_CUSTOM_MAPPER *__hidden this, struct INativeConfigurationElement *, const unsigned __int16 *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180021570`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18001bd50`
- `0x18002c010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001bf55`
- `msvcrt!_ultow` at `0x18001bf55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfd9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001beea`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001beea`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001bdc6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001bdc6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001bffa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001bffa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001bfc3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001bfc3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf09`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf21`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf39`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf64`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf9c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bfb2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf09`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf21`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf39`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf64`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bf9c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001bfb2`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001bfcf`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001bfcf`

## string_xrefs

- `0x18001bdfb`: `requireAccess`

## pseudocode

```c
__int64 __fastcall SCRIPT_MAP_CUSTOM_MAPPER::AddScriptMap(
        SCRIPT_MAP_CUSTOM_MAPPER *this,
        struct INativeConfigurationElement *a2,
        const unsigned __int16 *a3,
        struct MULTISZ *a4)
{
  signed int v7; // ebx
  unsigned int v8; // esi
  const unsigned __int16 *v9; // rdx
  int v10; // r8d
  const unsigned __int16 *Str; // rax
  signed int LastError; // eax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  const unsigned __int16 *v16; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[56]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v20[256]; // [rsp+100h] [rbp+0h] BYREF

  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, v20, 0x100u);
  if ( a4 && a3 && a2 )
  {
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
           a2,
           L"requireAccess",
           &v14,
           0,
           0);
    if ( v7 >= 0 )
    {
      v8 = v14 == 3;
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
             a2,
             L"resourceType",
             &v15,
             0,
             0);
      if ( v7 >= 0 )
      {
        if ( !v15 )
          v8 |= 4u;
        v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               L"verb",
               &v17,
               0,
               0);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                 a2,
                 L"path",
                 &v16,
                 0,
                 0);
          if ( v7 >= 0 )
          {
            v9 = v16;
            if ( *v16 == 42 && v16[1] == 46 )
              v9 = ++v16;
            v7 = STRU::Copy((STRU *)v18, v9);
            if ( v7 >= 0 )
            {
              v7 = STRU::Append((STRU *)v18, L",");
              if ( v7 >= 0 )
              {
                v7 = STRU::Append((STRU *)v18, a3);
                if ( v7 >= 0 )
                {
                  v7 = STRU::Append((STRU *)v18, L",");
                  if ( v7 >= 0 )
                  {
                    _ultow(v8, Buffer, 10);
                    v7 = STRU::Append((STRU *)v18, Buffer);
                    if ( v7 >= 0 )
                    {
                      v10 = *v17 - 42;
                      if ( *v17 == 42 )
                        v10 = v17[1];
                      if ( !v10
                        || (v7 = STRU::Append((STRU *)v18, L","), v7 >= 0)
                        && (v7 = STRU::Append((STRU *)v18, v17), v7 >= 0) )
                      {
                        Str = STRU::QueryStr((STRU *)v18);
                        if ( !MULTISZ::Append(a4, Str) )
                        {
                          LastError = GetLastError();
                          v7 = LastError;
                          if ( LastError > 0 )
                            v7 = (unsigned __int16)LastError | 0x80070000;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001bd50  push    rbp
0x18001bd52  push    rbx
0x18001bd53  push    rsi
0x18001bd54  push    rdi
0x18001bd55  push    r13
0x18001bd57  push    r14
0x18001bd59  push    r15
0x18001bd5b  lea     rbp, [rsp-210h]
0x18001bd63  sub     rsp, 310h
0x18001bd6a  mov     rax, cs:__security_cookie
0x18001bd71  xor     rax, rsp
0x18001bd74  mov     [rbp+240h+var_40], rax
0x18001bd7b  mov     r14, r8
0x18001bd7e  mov     [rsp+340h+var_310], 0
0x18001bd86  mov     rdi, rdx
0x18001bd89  mov     [rsp+340h+var_30C], 0
0x18001bd91  xor     edx, edx; Val
0x18001bd93  mov     [rsp+340h+var_300], 0
0x18001bd9c  mov     r8d, 200h; Size
0x18001bda2  mov     [rsp+340h+var_308], 0
0x18001bdab  lea     rcx, [rbp+240h+var_240]; void *
0x18001bdaf  mov     r15, r9
0x18001bdb2  call    memset_0
0x18001bdb7  mov     r8d, 100h
0x18001bdbd  lea     rdx, [rbp+240h+var_240]
0x18001bdc1  lea     rcx, [rsp+340h+var_2F8]
0x18001bdc6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001bdcc  test    r15, r15
0x18001bdcf  jz      loc_18001BFF0
0x18001bdd5  test    r14, r14
0x18001bdd8  jz      loc_18001BFF0
0x18001bdde  test    rdi, rdi
0x18001bde1  jz      loc_18001BFF0
0x18001bde7  mov     rax, [rdi]
0x18001bdea  lea     r8, [rsp+340h+var_310]
0x18001bdef  xor     r9d, r9d
0x18001bdf2  mov     [rsp+340h+var_320], 0
0x18001bdfb  lea     rdx, aRequireaccess; "requireAccess"
0x18001be02  mov     rcx, rdi
0x18001be05  mov     rax, [rax+30h]
0x18001be09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be0e  mov     ebx, eax
0x18001be10  test    eax, eax
0x18001be12  js      loc_18001BFF5
0x18001be18  xor     esi, esi
0x18001be1a  mov     [rsp+340h+var_320], 0
0x18001be23  cmp     [rsp+340h+var_310], 3
0x18001be28  lea     r8, [rsp+340h+var_30C]
0x18001be2d  lea     rdx, aResourcetype; "resourceType"
0x18001be34  mov     rcx, rdi
0x18001be37  lea     eax, [rsi+1]
0x18001be3a  cmovz   esi, eax
0x18001be3d  mov     rax, [rdi]
0x18001be40  xor     r9d, r9d
0x18001be43  mov     rax, [rax+30h]
0x18001be47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4c  mov     ebx, eax
0x18001be4e  test    eax, eax
0x18001be50  js      loc_18001BFF5
0x18001be56  cmp     [rsp+340h+var_30C], 0
0x18001be5b  jnz     short loc_18001BE60
0x18001be5d  or      esi, 4
0x18001be60  mov     rax, [rdi]
0x18001be63  lea     r8, [rsp+340h+var_300]
0x18001be68  xor     r9d, r9d
0x18001be6b  mov     [rsp+340h+var_320], 0
0x18001be74  lea     rdx, aVerb; "verb"
0x18001be7b  mov     rcx, rdi
0x18001be7e  mov     rax, [rax+40h]
0x18001be82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be87  mov     ebx, eax
0x18001be89  test    eax, eax
0x18001be8b  js      loc_18001BFF5
0x18001be91  mov     rax, [rdi]
0x18001be94  lea     r8, [rsp+340h+var_308]
0x18001be99  xor     r9d, r9d
0x18001be9c  mov     [rsp+340h+var_320], 0
0x18001bea5  lea     rdx, aPath; "path"
0x18001beac  mov     rcx, rdi
0x18001beaf  mov     rax, [rax+40h]
0x18001beb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beb8  mov     ebx, eax
0x18001beba  test    eax, eax
0x18001bebc  js      loc_18001BFF5
0x18001bec2  mov     rdx, [rsp+340h+var_308]
0x18001bec7  mov     r13d, 2Ah ; '*'
0x18001becd  cmp     [rdx], r13w
0x18001bed1  jnz     short loc_18001BEE5
0x18001bed3  lea     rax, [rdx+2]
0x18001bed7  cmp     word ptr [rax], 2Eh ; '.'
0x18001bedb  jnz     short loc_18001BEE5
0x18001bedd  mov     rdx, rax
0x18001bee0  mov     [rsp+340h+var_308], rax
0x18001bee5  lea     rcx, [rsp+340h+var_2F8]
0x18001beea  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001bef0  mov     ebx, eax
0x18001bef2  test    eax, eax
0x18001bef4  js      loc_18001BFF5
0x18001befa  lea     rdi, asc_180032E60; ","
0x18001bf01  mov     rdx, rdi
0x18001bf04  lea     rcx, [rsp+340h+var_2F8]
0x18001bf09  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bf0f  mov     ebx, eax
0x18001bf11  test    eax, eax
0x18001bf13  js      loc_18001BFF5
0x18001bf19  mov     rdx, r14
0x18001bf1c  lea     rcx, [rsp+340h+var_2F8]
0x18001bf21  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bf27  mov     ebx, eax
0x18001bf29  test    eax, eax
0x18001bf2b  js      loc_18001BFF5
0x18001bf31  mov     rdx, rdi
0x18001bf34  lea     rcx, [rsp+340h+var_2F8]
0x18001bf39  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bf3f  mov     ebx, eax
0x18001bf41  test    eax, eax
0x18001bf43  js      loc_18001BFF5
0x18001bf49  mov     r8d, 0Ah; Radix
0x18001bf4f  lea     rdx, [rbp+240h+Buffer]; Buffer
0x18001bf53  mov     ecx, esi; Value
0x18001bf55  call    cs:__imp__ultow
0x18001bf5b  lea     rdx, [rbp+240h+Buffer]
0x18001bf5f  lea     rcx, [rsp+340h+var_2F8]
0x18001bf64  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bf6a  mov     ebx, eax
0x18001bf6c  test    eax, eax
0x18001bf6e  js      loc_18001BFF5
0x18001bf74  mov     rcx, [rsp+340h+var_300]
0x18001bf79  movzx   r8d, word ptr [rcx]
0x18001bf7d  sub     r8d, r13d
0x18001bf80  jnz     short loc_18001BF8F
0x18001bf82  movzx   r8d, word ptr [rcx+2]
0x18001bf87  xor     eax, eax
0x18001bf89  movzx   ecx, ax
0x18001bf8c  sub     r8d, ecx
0x18001bf8f  test    r8d, r8d
0x18001bf92  jz      short loc_18001BFBE
0x18001bf94  mov     rdx, rdi
0x18001bf97  lea     rcx, [rsp+340h+var_2F8]
0x18001bf9c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bfa2  mov     ebx, eax
0x18001bfa4  test    eax, eax
0x18001bfa6  js      short loc_18001BFF5
0x18001bfa8  mov     rdx, [rsp+340h+var_300]
0x18001bfad  lea     rcx, [rsp+340h+var_2F8]
0x18001bfb2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001bfb8  mov     ebx, eax
0x18001bfba  test    eax, eax
0x18001bfbc  js      short loc_18001BFF5
0x18001bfbe  lea     rcx, [rsp+340h+var_2F8]
0x18001bfc3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001bfc9  mov     rdx, rax
0x18001bfcc  mov     rcx, r15
0x18001bfcf  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001bfd5  test    eax, eax
0x18001bfd7  jnz     short loc_18001BFF5
0x18001bfd9  call    cs:__imp_GetLastError
0x18001bfdf  mov     ebx, eax
0x18001bfe1  test    eax, eax
0x18001bfe3  jle     short loc_18001BFF5
0x18001bfe5  movzx   ebx, ax
0x18001bfe8  or      ebx, 80070000h
0x18001bfee  jmp     short loc_18001BFF5
0x18001bff0  mov     ebx, 80070057h
0x18001bff5  lea     rcx, [rsp+340h+var_2F8]
0x18001bffa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c000  mov     eax, ebx
0x18001c002  mov     rcx, [rbp+240h+var_40]
0x18001c009  xor     rcx, rsp; StackCookie
0x18001c00c  call    __security_check_cookie
0x18001c011  add     rsp, 310h
0x18001c018  pop     r15
0x18001c01a  pop     r14
0x18001c01c  pop     r13
0x18001c01e  pop     rdi
0x18001c01f  pop     rsi
0x18001c020  pop     rbx
0x18001c021  pop     rbp
0x18001c022  retn
```
