# CAutoLogonManager::GetAutoLogonCredential(ushort * *,ushort * *,ushort * *)

- ea: `0x18003dbe0`
- end: `0x18003dee1`
- name: `?GetAutoLogonCredential@CAutoLogonManager@@UEAAJPEAPEAG00@Z`
- size: `769`
- prototype: `__int64 __fastcall(CAutoLogonManager *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180039418`
- `0x18003dbe0`
- `0x18003dee8`
- `0x18003e8dc`
- `0x18003ebbc`
- `0x18005d488`
- `0x18006c000`
- `0x18006ca26`
- `0x18006cad0`
- `0x180092340`
- `0x1800925c0`
- `0x18009b79c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003dd3d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003dd3d`
- `KERNEL32!LocalFree` at `0x18003de9b`
- `KERNEL32!LocalFree` at `0x18003de9b`
- `KERNEL32!FormatMessageW` at `0x18003de5f`
- `KERNEL32!FormatMessageW` at `0x18003de5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dd09`

## string_xrefs

- `0x18003dd91`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003ddd9`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003dea9`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoLogonManager::GetAutoLogonCredential(
        CAutoLogonManager *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  char v8; // di
  CAutoLogonManager *v9; // rsi
  __int64 v10; // rdx
  unsigned int v11; // r8d
  int v12; // r9d
  DWORD RegistryAutoLogonCredential; // ebx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  size_t v16; // rbx
  size_t v17; // rsi
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  __int64 v20; // rdx
  unsigned __int16 *v21; // rsi
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  const wchar_t *v27; // rax
  const wchar_t *v28; // r8
  unsigned int lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned int Arguments; // [rsp+30h] [rbp-D0h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Src[256]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v33[256]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v34[256]; // [rsp+450h] [rbp+350h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+5A8h]

  v8 = 0;
  *(_DWORD *)Buffer = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  memset_0(v33, 0, sizeof(v33));
  memset_0(Src, 0, sizeof(Src));
  memset_0(v34, 0, sizeof(v34));
  v9 = (CAutoLogonManager *)((char *)this - 8);
  (*(void (__fastcall **)(CAutoLogonManager *))(*(_QWORD *)this + 64LL))(this);
  if ( (*((_BYTE *)this + 80) & 0x10) == 0 )
  {
    if ( (*((_BYTE *)v9 + 88) & 0x20) != 0 )
    {
      RegistryAutoLogonCredential = CAutoLogonManager::_GetRegistryAutoLogonCredential(
                                      (CAutoLogonManager *)((char *)this - 8),
                                      Src,
                                      v11,
                                      v33,
                                      lpBuffer,
                                      v34,
                                      Arguments);
      if ( (RegistryAutoLogonCredential & 0x80000000) == 0 )
        goto LABEL_7;
    }
    else
    {
      RegistryAutoLogonCredential = -2147418113;
    }
LABEL_26:
    CAutoLogonManager::_UpdateAutoLogonMode(v9, 4, v11, v12);
    Src[0] = 0;
    v33[0] = 0;
    v34[0] = 0;
    if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 1) != 0 )
    {
      if ( FormatMessageW(0x1100u, 0, RegistryAutoLogonCredential, 0, Buffer, 1u, 0) )
      {
        v27 = *(const wchar_t **)Buffer;
      }
      else
      {
        v27 = 0;
        *(_QWORD *)Buffer = 0;
      }
      v28 = L"???";
      if ( v27 )
        v28 = v27;
      McTemplateU0z_EventWriteTransfer(v26, v25, v28);
      v8 = 1;
    }
    if ( (v8 & 1) != 0 )
      LocalFree(*(HLOCAL *)Buffer);
    v20 = 321;
    goto LABEL_36;
  }
  if ( !(unsigned __int8)IsSingleUserNoPassword(Src, v10, v33) )
  {
    RegistryAutoLogonCredential = -2147467259;
    goto LABEL_26;
  }
  v34[0] = 0;
LABEL_7:
  v14 = 0x7FFFFFFF;
  v15 = Src;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = 2 * (v15 - Src);
  v17 = v16 + 2;
  v18 = (unsigned __int16 *)CoTaskMemAlloc(v16 + 2);
  v19 = v18;
  if ( v18 )
  {
    if ( v16 )
    {
      if ( v17 < v16 )
      {
        memset_0(v18, 0, v17);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v18, Src, v16);
      }
    }
    v19[v16 / 2] = 0;
  }
  if ( !v19 )
  {
    RegistryAutoLogonCredential = -2147024882;
    v20 = 324;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)RegistryAutoLogonCredential,
      lpBuffer);
    return RegistryAutoLogonCredential;
  }
  wil::make_cotaskmem_string_secure_nothrow(Buffer, v33);
  v21 = *(unsigned __int16 **)Buffer;
  if ( *(_QWORD *)Buffer )
  {
    wil::make_cotaskmem_string_secure_nothrow(Buffer, v34);
    v23 = *(unsigned __int16 **)Buffer;
    if ( *(_QWORD *)Buffer )
    {
      *a2 = v19;
      *a3 = v21;
      *a4 = v23;
      return 0;
    }
    RegistryAutoLogonCredential = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)0x8007000ELL,
      lpBuffer);
    if ( v21 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v22, v21);
  }
  else
  {
    RegistryAutoLogonCredential = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)0x8007000ELL,
      lpBuffer);
  }
  wil::cotaskmem_secure_deleter::operator()<unsigned short>(v22, v19);
  return RegistryAutoLogonCredential;
}

```

## disassembly

```asm
0x18003dbe0  push    rbp
0x18003dbe2  push    rbx
0x18003dbe3  push    rsi
0x18003dbe4  push    rdi
0x18003dbe5  push    r12
0x18003dbe7  push    r13
0x18003dbe9  push    r14
0x18003dbeb  push    r15
0x18003dbed  lea     rbp, [rsp-568h]
0x18003dbf5  sub     rsp, 668h
0x18003dbfc  mov     rax, cs:__security_cookie
0x18003dc03  xor     rax, rsp
0x18003dc06  mov     [rbp+5A0h+var_50], rax
0x18003dc0d  mov     r12, r9
0x18003dc10  mov     r15, r8
0x18003dc13  mov     r14, rdx
0x18003dc16  mov     rbx, rcx
0x18003dc19  xor     r13d, r13d
0x18003dc1c  mov     edi, r13d
0x18003dc1f  mov     dword ptr [rsp+6A0h+Buffer], r13d
0x18003dc24  mov     [rdx], r13
0x18003dc27  mov     [r8], r13
0x18003dc2a  mov     [r9], r13
0x18003dc2d  mov     esi, 200h
0x18003dc32  mov     r8d, esi; Size
0x18003dc35  xor     edx, edx; Val
0x18003dc37  lea     rcx, [rbp+5A0h+var_450]; void *
0x18003dc3e  call    memset_0
0x18003dc43  mov     r8d, esi; Size
0x18003dc46  xor     edx, edx; Val
0x18003dc48  lea     rcx, [rsp+6A0h+Src]; void *
0x18003dc4d  call    memset_0
0x18003dc52  mov     r8d, esi; Size
0x18003dc55  xor     edx, edx; Val
0x18003dc57  lea     rcx, [rbp+5A0h+var_250]; void *
0x18003dc5e  call    memset_0
0x18003dc63  lea     rsi, [rbx-8]
0x18003dc67  mov     rax, [rbx]
0x18003dc6a  mov     rcx, rbx
0x18003dc6d  mov     rax, [rax+40h]
0x18003dc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc76  test    byte ptr [rsi+58h], 10h
0x18003dc7a  jz      short loc_18003DCA5
0x18003dc7c  lea     r8, [rbp+5A0h+var_450]
0x18003dc83  lea     rcx, [rsp+6A0h+Src]
0x18003dc88  call    _IsSingleUserNoPassword
0x18003dc8d  test    al, al
0x18003dc8f  jz      short loc_18003DC9B
0x18003dc91  mov     [rbp+5A0h+var_250], r13w
0x18003dc99  jmp     short loc_18003DCD9
0x18003dc9b  mov     ebx, 80004005h
0x18003dca0  jmp     loc_18003DE0F
0x18003dca5  test    byte ptr [rsi+58h], 20h
0x18003dca9  jz      loc_18003DE0A
0x18003dcaf  lea     rax, [rbp+5A0h+var_250]
0x18003dcb6  mov     qword ptr [rsp+6A0h+nSize], rax; unsigned __int16 *
0x18003dcbb  lea     r9, [rbp+5A0h+var_450]; unsigned __int16 *
0x18003dcc2  lea     rdx, [rsp+6A0h+Src]; unsigned __int16 *
0x18003dcc7  mov     rcx, rsi; this
0x18003dcca  call    ?_GetRegistryAutoLogonCredential@CAutoLogonManager@@AEAAJPEAGK0K0K@Z; CAutoLogonManager::_GetRegistryAutoLogonCredential(ushort *,ulong,ushort *,ulong,ushort *,ulong)
0x18003dccf  mov     ebx, eax
0x18003dcd1  test    eax, eax
0x18003dcd3  js      loc_18003DE0F
0x18003dcd9  mov     ecx, 7FFFFFFFh
0x18003dcde  lea     rax, [rsp+6A0h+Src]
0x18003dce3  cmp     [rax], r13w
0x18003dce7  jz      short loc_18003DCF3
0x18003dce9  add     rax, 2
0x18003dced  sub     rcx, 1
0x18003dcf1  jnz     short loc_18003DCE3
0x18003dcf3  lea     rcx, [rsp+6A0h+Src]
0x18003dcf8  sub     rax, rcx
0x18003dcfb  sar     rax, 1
0x18003dcfe  lea     rbx, [rax+rax]
0x18003dd02  lea     rsi, [rbx+2]
0x18003dd06  mov     rcx, rsi; cb
0x18003dd09  call    cs:__imp_CoTaskMemAlloc
0x18003dd0f  mov     rdi, rax
0x18003dd12  test    rax, rax
0x18003dd15  jz      short loc_18003DD53
0x18003dd17  test    rbx, rbx
0x18003dd1a  jz      short loc_18003DD4E
0x18003dd1c  mov     rcx, rax; void *
0x18003dd1f  cmp     rsi, rbx
0x18003dd22  jb      short loc_18003DD33
0x18003dd24  mov     r8, rbx; Size
0x18003dd27  lea     rdx, [rsp+6A0h+Src]; Src
0x18003dd2c  call    memcpy_0
0x18003dd31  jmp     short loc_18003DD4E
0x18003dd33  mov     r8, rsi; Size
0x18003dd36  xor     edx, edx; Val
0x18003dd38  call    memset_0
0x18003dd3d  call    cs:__imp__o__errno
0x18003dd43  mov     dword ptr [rax], 22h ; '"'
0x18003dd49  call    _invalid_parameter_noinfo
0x18003dd4e  mov     [rbx+rdi], r13w
0x18003dd53  test    rdi, rdi
0x18003dd56  jnz     short loc_18003DD67
0x18003dd58  mov     ebx, 8007000Eh
0x18003dd5d  mov     edx, 144h
0x18003dd62  jmp     loc_18003DEA6
0x18003dd67  lea     rdx, [rbp+5A0h+var_450]
0x18003dd6e  lea     rcx, [rsp+6A0h+Buffer]
0x18003dd73  call    ?make_cotaskmem_string_secure_nothrow@wil@@YA?AV?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@PEBG@Z; wil::make_cotaskmem_string_secure_nothrow(ushort const *)
0x18003dd78  mov     rsi, qword ptr [rsp+6A0h+Buffer]
0x18003dd7d  test    rsi, rsi
0x18003dd80  jnz     short loc_18003DDAF
0x18003dd82  mov     rcx, [rbp+5A8h]; this
0x18003dd89  mov     ebx, 8007000Eh
0x18003dd8e  mov     r9d, ebx; char *
0x18003dd91  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003dd98  mov     edx, 147h; void *
0x18003dd9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dda2  mov     rdx, rdi
0x18003dda5  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003ddaa  jmp     loc_18003DEBC
0x18003ddaf  lea     rdx, [rbp+5A0h+var_250]
0x18003ddb6  lea     rcx, [rsp+6A0h+Buffer]
0x18003ddbb  call    ?make_cotaskmem_string_secure_nothrow@wil@@YA?AV?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@PEBG@Z; wil::make_cotaskmem_string_secure_nothrow(ushort const *)
0x18003ddc0  mov     rax, qword ptr [rsp+6A0h+Buffer]
0x18003ddc5  test    rax, rax
0x18003ddc8  jnz     short loc_18003DDF9
0x18003ddca  mov     rcx, [rbp+5A8h]; this
0x18003ddd1  mov     ebx, 8007000Eh
0x18003ddd6  mov     r9d, ebx; char *
0x18003ddd9  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003dde0  mov     edx, 14Ah; void *
0x18003dde5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ddea  test    rsi, rsi
0x18003dded  jz      short loc_18003DDA2
0x18003ddef  mov     rdx, rsi
0x18003ddf2  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18003ddf7  jmp     short loc_18003DDA2
0x18003ddf9  mov     [r14], rdi
0x18003ddfc  mov     [r15], rsi
0x18003ddff  mov     [r12], rax
0x18003de03  xor     eax, eax
0x18003de05  jmp     loc_18003DEBE
0x18003de0a  mov     ebx, 8000FFFFh
0x18003de0f  mov     edx, 4; int
0x18003de14  mov     rcx, rsi; this
0x18003de17  call    ?_UpdateAutoLogonMode@CAutoLogonManager@@AEAAXHHH@Z; CAutoLogonManager::_UpdateAutoLogonMode(int,int,int)
0x18003de1c  mov     [rsp+6A0h+Src], r13w
0x18003de22  mov     [rbp+5A0h+var_450], r13w
0x18003de2a  mov     [rbp+5A0h+var_250], r13w
0x18003de32  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 1
0x18003de39  jz      short loc_18003DE90
0x18003de3b  mov     qword ptr [rsp+6A0h+Arguments], r13; Arguments
0x18003de40  mov     [rsp+6A0h+nSize], 1; nSize
0x18003de48  lea     rax, [rsp+6A0h+Buffer]
0x18003de4d  mov     [rsp+6A0h+lpBuffer], rax; int
0x18003de52  xor     r9d, r9d; dwLanguageId
0x18003de55  mov     r8d, ebx; dwMessageId
0x18003de58  xor     edx, edx; lpSource
0x18003de5a  mov     ecx, 1100h; dwFlags
0x18003de5f  call    cs:__imp_FormatMessageW
0x18003de65  test    eax, eax
0x18003de67  jnz     short loc_18003DE73
0x18003de69  mov     rax, r13
0x18003de6c  mov     qword ptr [rsp+6A0h+Buffer], rax
0x18003de71  jmp     short loc_18003DE78
0x18003de73  mov     rax, qword ptr [rsp+6A0h+Buffer]
0x18003de78  lea     r8, asc_1800B02B0; "???"
0x18003de7f  test    rax, rax
0x18003de82  cmovnz  r8, rax
0x18003de86  call    McTemplateU0z_EventWriteTransfer
0x18003de8b  mov     edi, 1
0x18003de90  test    dil, 1
0x18003de94  jz      short loc_18003DEA1
0x18003de96  mov     rcx, qword ptr [rsp+6A0h+Buffer]; hMem
0x18003de9b  call    cs:__imp_LocalFree
0x18003dea1  mov     edx, 141h; void *
0x18003dea6  mov     r9d, ebx; char *
0x18003dea9  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003deb0  mov     rcx, [rbp+5A8h]; this
0x18003deb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003debc  mov     eax, ebx
0x18003debe  mov     rcx, [rbp+5A0h+var_50]
0x18003dec5  xor     rcx, rsp; StackCookie
0x18003dec8  call    __security_check_cookie
0x18003decd  add     rsp, 668h
0x18003ded4  pop     r15
0x18003ded6  pop     r14
0x18003ded8  pop     r13
0x18003deda  pop     r12
0x18003dedc  pop     rdi
0x18003dedd  pop     rsi
0x18003dede  pop     rbx
0x18003dedf  pop     rbp
0x18003dee0  retn
```
