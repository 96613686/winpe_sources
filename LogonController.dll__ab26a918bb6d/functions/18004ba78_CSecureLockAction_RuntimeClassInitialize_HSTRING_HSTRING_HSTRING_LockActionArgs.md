# CSecureLockAction::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *,LockActionArgs *)

- ea: `0x18004ba78`
- end: `0x18004bd8d`
- name: `?RuntimeClassInitialize@CSecureLockAction@@QEAAJPEAUHSTRING__@@00PEAVLockActionArgs@@@Z`
- size: `789`
- prototype: `int(CSecureLockAction *__hidden this, HSTRING, HSTRING, HSTRING, struct LockActionArgs *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c628`

## callees

- `0x18002bc20`
- `0x18003a100`
- `0x18004ba78`
- `0x18005d488`
- `0x18007e6c0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004badb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bbe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004badb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bb67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bbe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bbd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bbd6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004bc41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004bc41`

## pseudocode

```c
__int64 __fastcall CSecureLockAction::RuntimeClassInitialize(
        CSecureLockAction *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        struct LockActionArgs *pvData)
{
  struct LockActionArgs *v5; // r15
  HSTRING *v7; // rdi
  HRESULT v11; // edi
  __int64 v12; // rdx
  HSTRING *v14; // rdi
  HSTRING *v15; // rdi
  HSTRING v16; // rsi
  HSTRING *v17; // rdi
  HSTRING v18; // rsi
  HSTRING *v19; // rdi
  bool v20; // di
  LSTATUS ValueW; // eax
  __int64 v22; // rdx
  signed int v23; // ecx
  int v24; // eax
  int v25; // eax
  unsigned int v26; // ebx
  int pdwType; // [rsp+20h] [rbp-40h]
  int pdwTypea; // [rsp+20h] [rbp-40h]
  _QWORD v29[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD v31; // [rsp+90h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+38h] BYREF

  v5 = pvData;
  v7 = (HSTRING *)((char *)this + 200);
  *((_BYTE *)this + 249) = *(_BYTE *)pvData;
  *((_BYTE *)this + 250) = *((_BYTE *)v5 + 1);
  if ( !a2 || a2 != *v7 )
  {
    WindowsDeleteString(*v7);
    *v7 = 0;
    v11 = WindowsDuplicateString(a2, v7);
    if ( v11 < 0 )
    {
      v12 = 29;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\securelockaction.cpp",
        (const char *)(unsigned int)v11,
        pdwType);
      return (unsigned int)v11;
    }
  }
  v14 = (HSTRING *)((char *)this + 208);
  if ( !a3 || a3 != *v14 )
  {
    WindowsDeleteString(*v14);
    *v14 = 0;
    v11 = WindowsDuplicateString(a3, (HSTRING *)this + 26);
    if ( v11 < 0 )
    {
      v12 = 30;
      goto LABEL_5;
    }
  }
  v15 = (HSTRING *)((char *)this + 216);
  if ( !a4 || a4 != *v15 )
  {
    WindowsDeleteString(*v15);
    *v15 = 0;
    v11 = WindowsDuplicateString(a4, (HSTRING *)this + 27);
    if ( v11 < 0 )
    {
      v12 = 31;
      goto LABEL_5;
    }
  }
  v16 = (HSTRING)*((_QWORD *)v5 + 1);
  v17 = (HSTRING *)((char *)this + 224);
  if ( !v16 || v16 != *v17 )
  {
    WindowsDeleteString(*v17);
    *v17 = 0;
    v11 = WindowsDuplicateString(v16, (HSTRING *)this + 28);
    if ( v11 < 0 )
    {
      v12 = 32;
      goto LABEL_5;
    }
  }
  v18 = (HSTRING)*((_QWORD *)v5 + 2);
  v19 = (HSTRING *)((char *)this + 232);
  if ( !v18 || v18 != *v19 )
  {
    WindowsDeleteString(*v19);
    *v19 = 0;
    v11 = WindowsDuplicateString(v18, (HSTRING *)this + 29);
    if ( v11 < 0 )
    {
      v12 = 33;
      goto LABEL_5;
    }
  }
  pcbData = 4;
  v20 = 0;
  v31 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
             L"EnableLostMode",
             0x10000012u,
             &v31,
             &pvData,
             &pcbData);
  v23 = ValueW;
  if ( ValueW )
  {
    if ( ValueW == 234 )
    {
      LOWORD(v23) = 13;
    }
    else if ( ValueW <= 0 )
    {
      goto LABEL_34;
    }
    goto LABEL_33;
  }
  LOWORD(v23) = 13;
  if ( v31 != 4 )
  {
    if ( pcbData == 4 )
    {
      v22 = 1;
      if ( (unsigned __int16)((_WORD)pvData - 48) <= 1u )
      {
        v20 = (_WORD)pvData == 49;
        v23 = 0;
        goto LABEL_34;
      }
    }
LABEL_33:
    v23 = (unsigned __int16)v23 | 0x80070000;
    goto LABEL_34;
  }
  v22 = 1;
  if ( (unsigned int)pvData > 1 )
    goto LABEL_33;
  v23 = 0;
  v20 = (_DWORD)pvData == 1;
LABEL_34:
  if ( v23 >= 0 )
  {
    *((_BYTE *)this + 248) = v20;
    if ( v20 )
    {
      memset(v29, 0, 24);
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                  v29,
                  v22,
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
                  L"LostModeMessage") >= 0 )
      {
        pvData = (struct LockActionArgs *)v29[0];
        v24 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 240, &pvData);
        v11 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\securelockaction.cpp",
            (const char *)(unsigned int)v24,
            pdwTypea);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v29);
          return (unsigned int)v11;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v29);
    }
  }
  v25 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 104LL))((char *)this + 40);
  v26 = v25;
  if ( v25 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\securelockaction.cpp",
    (const char *)(unsigned int)v25,
    pdwTypea);
  return v26;
}

```

## disassembly

```asm
0x18004ba78  mov     [rsp-28h+arg_10], rbx
0x18004ba7d  mov     [rsp-28h+arg_18], rsi
0x18004ba82  push    rbp
0x18004ba83  push    rdi
0x18004ba84  push    r12
0x18004ba86  push    r14
0x18004ba88  push    r15
0x18004ba8a  mov     rbp, rsp
0x18004ba8d  sub     rsp, 60h
0x18004ba91  mov     r15, [rbp+arg_20]
0x18004ba95  mov     rsi, r9
0x18004ba98  lea     rdi, [rcx+0C8h]
0x18004ba9f  mov     r14, r8
0x18004baa2  mov     r12, rdx
0x18004baa5  mov     rbx, rcx
0x18004baa8  mov     al, [r15]
0x18004baab  mov     [rcx+0F9h], al
0x18004bab1  mov     al, [r15+1]
0x18004bab5  mov     [rcx+0FAh], al
0x18004babb  test    rdx, rdx
0x18004babe  jz      short loc_18004BAC5
0x18004bac0  cmp     rdx, [rdi]
0x18004bac3  jz      short loc_18004BB06
0x18004bac5  mov     rcx, [rdi]; string
0x18004bac8  call    cs:__imp_WindowsDeleteString
0x18004bace  mov     rdx, rdi; newString
0x18004bad1  mov     qword ptr [rdi], 0
0x18004bad8  mov     rcx, r12; string
0x18004badb  call    cs:__imp_WindowsDuplicateString
0x18004bae1  mov     edi, eax
0x18004bae3  test    eax, eax
0x18004bae5  jns     short loc_18004BB06
0x18004bae7  mov     edx, 1Dh; void *
0x18004baec  mov     rcx, [rbp+28h]; this
0x18004baf0  lea     r8, aPcshellShellAu_13; "pcshell\\shell\\auth\\authux\\controlle"...
0x18004baf7  mov     r9d, edi; char *
0x18004bafa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004baff  mov     eax, edi
0x18004bb01  jmp     loc_18004BD74
0x18004bb06  lea     rdi, [rbx+0D0h]
0x18004bb0d  test    r14, r14
0x18004bb10  jz      short loc_18004BB17
0x18004bb12  cmp     r14, [rdi]
0x18004bb15  jz      short loc_18004BB40
0x18004bb17  mov     rcx, [rdi]; string
0x18004bb1a  call    cs:__imp_WindowsDeleteString
0x18004bb20  mov     rdx, rdi; newString
0x18004bb23  mov     qword ptr [rdi], 0
0x18004bb2a  mov     rcx, r14; string
0x18004bb2d  call    cs:__imp_WindowsDuplicateString
0x18004bb33  mov     edi, eax
0x18004bb35  test    eax, eax
0x18004bb37  jns     short loc_18004BB40
0x18004bb39  mov     edx, 1Eh
0x18004bb3e  jmp     short loc_18004BAEC
0x18004bb40  lea     rdi, [rbx+0D8h]
0x18004bb47  test    rsi, rsi
0x18004bb4a  jz      short loc_18004BB51
0x18004bb4c  cmp     rsi, [rdi]
0x18004bb4f  jz      short loc_18004BB7D
0x18004bb51  mov     rcx, [rdi]; string
0x18004bb54  call    cs:__imp_WindowsDeleteString
0x18004bb5a  mov     rdx, rdi; newString
0x18004bb5d  mov     qword ptr [rdi], 0
0x18004bb64  mov     rcx, rsi; string
0x18004bb67  call    cs:__imp_WindowsDuplicateString
0x18004bb6d  mov     edi, eax
0x18004bb6f  test    eax, eax
0x18004bb71  jns     short loc_18004BB7D
0x18004bb73  mov     edx, 1Fh
0x18004bb78  jmp     loc_18004BAEC
0x18004bb7d  mov     rsi, [r15+8]
0x18004bb81  lea     rdi, [rbx+0E0h]
0x18004bb88  test    rsi, rsi
0x18004bb8b  jz      short loc_18004BB92
0x18004bb8d  cmp     rsi, [rdi]
0x18004bb90  jz      short loc_18004BBBE
0x18004bb92  mov     rcx, [rdi]; string
0x18004bb95  call    cs:__imp_WindowsDeleteString
0x18004bb9b  mov     rdx, rdi; newString
0x18004bb9e  mov     qword ptr [rdi], 0
0x18004bba5  mov     rcx, rsi; string
0x18004bba8  call    cs:__imp_WindowsDuplicateString
0x18004bbae  mov     edi, eax
0x18004bbb0  test    eax, eax
0x18004bbb2  jns     short loc_18004BBBE
0x18004bbb4  mov     edx, 20h ; ' '
0x18004bbb9  jmp     loc_18004BAEC
0x18004bbbe  mov     rsi, [r15+10h]
0x18004bbc2  lea     rdi, [rbx+0E8h]
0x18004bbc9  test    rsi, rsi
0x18004bbcc  jz      short loc_18004BBD3
0x18004bbce  cmp     rsi, [rdi]
0x18004bbd1  jz      short loc_18004BBFF
0x18004bbd3  mov     rcx, [rdi]; string
0x18004bbd6  call    cs:__imp_WindowsDeleteString
0x18004bbdc  mov     rdx, rdi; newString
0x18004bbdf  mov     qword ptr [rdi], 0
0x18004bbe6  mov     rcx, rsi; string
0x18004bbe9  call    cs:__imp_WindowsDuplicateString
0x18004bbef  mov     edi, eax
0x18004bbf1  test    eax, eax
0x18004bbf3  jns     short loc_18004BBFF
0x18004bbf5  mov     edx, 21h ; '!'
0x18004bbfa  jmp     loc_18004BAEC
0x18004bbff  lea     rax, [rbp+arg_8]
0x18004bc03  mov     [rbp+arg_8], 4
0x18004bc0a  mov     [rsp+60h+pcbData], rax; pcbData
0x18004bc0f  lea     r8, aEnablelostmode; "EnableLostMode"
0x18004bc16  lea     rax, [rbp+arg_20]
0x18004bc1a  xor     edi, edi
0x18004bc1c  mov     [rsp+60h+pvData], rax; pvData
0x18004bc21  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004bc28  lea     rax, [rbp+arg_0]
0x18004bc2c  mov     [rbp+arg_0], edi
0x18004bc2f  mov     r9d, 10000012h; dwFlags
0x18004bc35  mov     [rsp+60h+pdwType], rax; int
0x18004bc3a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004bc41  call    cs:__imp_RegGetValueW
0x18004bc47  lea     esi, [rdi+31h]
0x18004bc4a  mov     ecx, eax
0x18004bc4c  test    eax, eax
0x18004bc4e  jnz     short loc_18004BC90
0x18004bc50  cmp     [rbp+arg_0], 4
0x18004bc54  lea     ecx, [rdi+0Dh]
0x18004bc57  jnz     short loc_18004BC6C
0x18004bc59  lea     edx, [rdi+1]
0x18004bc5c  cmp     dword ptr [rbp+arg_20], edx
0x18004bc5f  ja      short loc_18004BCA2
0x18004bc61  xor     ecx, ecx
0x18004bc63  cmp     dword ptr [rbp+arg_20], edx
0x18004bc66  setz    dil
0x18004bc6a  jmp     short loc_18004BCAB
0x18004bc6c  cmp     [rbp+arg_8], 4
0x18004bc70  jnz     short loc_18004BCA2
0x18004bc72  movzx   eax, word ptr [rbp+arg_20]
0x18004bc76  mov     edx, 1
0x18004bc7b  sub     ax, 30h ; '0'
0x18004bc7f  cmp     ax, dx
0x18004bc82  ja      short loc_18004BCA2
0x18004bc84  cmp     si, word ptr [rbp+arg_20]
0x18004bc88  setz    dil
0x18004bc8c  xor     ecx, ecx
0x18004bc8e  jmp     short loc_18004BCAB
0x18004bc90  cmp     eax, 0EAh
0x18004bc95  jnz     short loc_18004BC9E
0x18004bc97  mov     ecx, 0Dh
0x18004bc9c  jmp     short loc_18004BCA2
0x18004bc9e  test    eax, eax
0x18004bca0  jle     short loc_18004BCAB
0x18004bca2  movzx   ecx, cx
0x18004bca5  or      ecx, 80070000h
0x18004bcab  test    ecx, ecx
0x18004bcad  js      loc_18004BD43
0x18004bcb3  mov     [rbx+0F8h], dil
0x18004bcba  test    dil, dil
0x18004bcbd  jz      loc_18004BD43
0x18004bcc3  lea     r9, aLostmodemessag; "LostModeMessage"
0x18004bcca  mov     [rbp+var_20], 0
0x18004bcd2  lea     r8, aSoftwareMicros_31; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004bcd9  mov     [rbp+var_18], 0
0x18004bce1  lea     rcx, [rbp+var_20]
0x18004bce5  mov     [rbp+var_10], 0
0x18004bced  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18004bcf2  test    eax, eax
0x18004bcf4  js      short loc_18004BD3A
0x18004bcf6  mov     rax, [rbp+var_20]
0x18004bcfa  lea     rcx, [rbx+0F0h]
0x18004bd01  lea     rdx, [rbp+arg_20]
0x18004bd05  mov     [rbp+arg_20], rax
0x18004bd09  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004bd0e  mov     edi, eax
0x18004bd10  test    eax, eax
0x18004bd12  jns     short loc_18004BD3A
0x18004bd14  mov     rcx, [rbp+28h]; this
0x18004bd18  lea     r8, aPcshellShellAu_13; "pcshell\\shell\\auth\\authux\\controlle"...
0x18004bd1f  mov     r9d, eax; char *
0x18004bd22  mov     edx, 2Ch ; ','; void *
0x18004bd27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd2c  lea     rcx, [rbp+var_20]
0x18004bd30  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004bd35  jmp     loc_18004BAFF
0x18004bd3a  lea     rcx, [rbp+var_20]
0x18004bd3e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004bd43  lea     rcx, [rbx+28h]
0x18004bd47  mov     rax, [rcx]
0x18004bd4a  mov     rax, [rax+68h]
0x18004bd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd53  mov     ebx, eax
0x18004bd55  test    eax, eax
0x18004bd57  jns     short loc_18004BD72
0x18004bd59  mov     rcx, [rbp+28h]; this
0x18004bd5d  lea     r8, aPcshellShellAu_13; "pcshell\\shell\\auth\\authux\\controlle"...
0x18004bd64  mov     r9d, eax; char *
0x18004bd67  mov     edx, esi; void *
0x18004bd69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd6e  mov     eax, ebx
0x18004bd70  jmp     short loc_18004BD74
0x18004bd72  xor     eax, eax
0x18004bd74  lea     r11, [rsp+60h+var_s0]
0x18004bd79  mov     rbx, [r11+40h]
0x18004bd7d  mov     rsi, [r11+48h]
0x18004bd81  mov     rsp, r11
0x18004bd84  pop     r15
0x18004bd86  pop     r14
0x18004bd88  pop     r12
0x18004bd8a  pop     rdi
0x18004bd8b  pop     rbp
0x18004bd8c  retn
```
