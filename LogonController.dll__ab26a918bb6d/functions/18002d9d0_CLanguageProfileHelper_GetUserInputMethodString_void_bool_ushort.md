# CLanguageProfileHelper::GetUserInputMethodString(void *,bool,ushort * *)

- ea: `0x18002d9d0`
- end: `0x18002debc`
- name: `?GetUserInputMethodString@CLanguageProfileHelper@@CAJPEAX_NPEAPEAG@Z`
- size: `1260`
- prototype: `__int64 __fastcall(void *, char, WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e18c`

## callees

- `0x18002d9d0`
- `0x18002dec4`
- `0x18002e564`
- `0x1800358e0`
- `0x18006c000`
- `0x18006e910`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18002dc44`
- `KERNEL32!RaiseException` at `0x18002de08`
- `KERNEL32!RaiseException` at `0x18002dc44`
- `KERNEL32!RaiseException` at `0x18002de08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002db35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002db35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002daed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dafd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dbbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002daed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dafd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dbbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dc01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002dc67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002dc67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002da48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002dcc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002da48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002dcc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002de12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002de12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002de42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002de42`
- `ext-ms-win-globalization-input-l1-1-0!WGITransformInputMethodsForLanguage` at `0x18002dc95`
- `ext-ms-win-globalization-input-l1-1-0!WGITransformInputMethodsForLanguage` at `0x18002dc95`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18002da32`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18002da32`
- `Bcp47Langs!GetUserLanguages` at `0x18002da8d`
- `Bcp47Langs!GetUserLanguages` at `0x18002da8d`
- `Bcp47Langs!GetUserLanguageInputMethods` at `0x18002dde7`
- `Bcp47Langs!GetUserLanguageInputMethods` at `0x18002dde7`
- `Bcp47Langs!GetUserLanguageInputMethodsForUser` at `0x18002dbe4`
- `Bcp47Langs!GetUserLanguageInputMethodsForUser` at `0x18002dbe4`

## pseudocode

```c
__int64 __fastcall CLanguageProfileHelper::GetUserInputMethodString(void *a1, char a2, WCHAR *a3)
{
  WCHAR *v3; // rdi
  char v4; // si
  __int64 v6; // r14
  int UserLanguagesForUser; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // r15
  unsigned __int64 v10; // r12
  SIZE_T v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // r8
  WCHAR v16; // ax
  PCWSTR v17; // rbx
  WCHAR *v18; // rcx
  unsigned __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rcx
  const WCHAR *v22; // rax
  __int64 j; // rdx
  const WCHAR *v24; // rdx
  void *v25; // rbx
  int UserLanguageInputMethodsForUser; // eax
  HSTRING v27; // rcx
  unsigned __int64 v28; // rbx
  unsigned int v29; // eax
  HRESULT v30; // eax
  HSTRING v31; // rdi
  HSTRING v32; // rsi
  int v33; // ebx
  LPVOID *v34; // rdi
  __int64 v35; // rcx
  _WORD *v36; // rax
  int v37; // edx
  __int64 v38; // rax
  __int64 v39; // rcx
  const wchar_t *v40; // rdx
  __int64 v41; // r8
  wchar_t *v42; // r9
  wchar_t v43; // ax
  wchar_t *v44; // rcx
  __int64 v45; // rcx
  _WORD *v46; // rax
  unsigned __int16 *v47; // rax
  LPVOID v48; // rax
  unsigned __int16 **v50; // [rsp+20h] [rbp-69h]
  unsigned __int64 *v51; // [rsp+28h] [rbp-61h]
  unsigned int v52; // [rsp+30h] [rbp-59h]
  UINT32 length; // [rsp+44h] [rbp-45h] BYREF
  HSTRING v55; // [rsp+48h] [rbp-41h] BYREF
  HSTRING string; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v57; // [rsp+58h] [rbp-31h] BYREF
  LPVOID *v58; // [rsp+60h] [rbp-29h]
  __int64 i; // [rsp+68h] [rbp-21h]
  void *v60; // [rsp+70h] [rbp-19h]
  const WCHAR *v61; // [rsp+78h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v63; // [rsp+98h] [rbp+Fh] BYREF

  v3 = a3;
  v58 = (LPVOID *)a3;
  v4 = a2;
  v60 = a1;
  v6 = 0;
  *(_QWORD *)a3 = 0;
  string = 0;
  if ( a1 )
  {
    WindowsDeleteString(0);
    string = 0;
    UserLanguagesForUser = GetUserLanguagesForUser(a1, 0, &string);
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    UserLanguagesForUser = GetUserLanguages(0, &string);
  }
  v8 = UserLanguagesForUser;
  if ( UserLanguagesForUser < 0 )
    goto LABEL_77;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v61 = StringRawBuffer;
  *(_QWORD *)v3 = 0;
  i = 0;
  v10 = 513;
  v11 = 1026;
  if ( !is_mul_ok(0x201u, 2u) )
  {
    v8 = -2147024362;
    goto LABEL_77;
  }
LABEL_70:
  v47 = (unsigned __int16 *)CoTaskMemAlloc(v11);
  *(_QWORD *)v3 = v47;
  if ( !v47 )
  {
    v8 = -2147024882;
    goto LABEL_77;
  }
  v6 = 512;
  StringCchCopyNExW(v47, v10, 0, 0x200u, v50, v51, v52);
  v19 = 512;
  v10 = 0;
  v20 = WindowsGetStringLen(string) + 1;
  for ( i = v20; ; v20 = i )
  {
    v3 = (WCHAR *)&StringRawBuffer[v10];
    if ( !v3 )
      break;
    v21 = v20 - v10;
    if ( v20 - v10 > 0x7FFFFFFF )
      break;
    v22 = &StringRawBuffer[v10];
    for ( j = v21; v21; --v21 )
    {
      if ( !*v22 )
        break;
      ++v22;
    }
    v8 = -2147024809;
    if ( v21 )
      v8 = 0;
    v24 = (const WCHAR *)(j - v21);
    if ( !v21 )
      goto LABEL_76;
    StringRawBuffer = v24;
    if ( !v24 )
      goto LABEL_79;
    v55 = 0;
    v25 = v60;
    WindowsDeleteString(0);
    v55 = 0;
    if ( v25 )
      UserLanguageInputMethodsForUser = GetUserLanguageInputMethodsForUser(v25, v3, 59, &v55);
    else
      UserLanguageInputMethodsForUser = GetUserLanguageInputMethods(v3, 59, &v55);
    if ( UserLanguageInputMethodsForUser >= 0 )
    {
      v27 = 0;
      v57 = 0;
      if ( !v4 )
        goto LABEL_44;
      WindowsDeleteString(0);
      v57 = 0;
      v63 = 0;
      v28 = -1;
      do
        ++v28;
      while ( v3[v28] );
      if ( v28 > 0xFFFFFFFF )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        __debugbreak();
      }
      v29 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v28);
      if ( (unsigned int)v28 >= v29 )
        LODWORD(v28) = v29 - 1;
      v30 = WindowsCreateStringReference(v3, v28, &hstringHeader, &v63);
      if ( v30 < 0 )
      {
        RaiseException(v30, 1u, 0, 0);
        goto LABEL_70;
      }
      v31 = v63;
      v32 = v55;
      v33 = -2147024769;
      if ( (unsigned __int8)IsWGITransformInputMethodsForLanguagePresent() )
        v33 = WGITransformInputMethodsForLanguage(v32, v31, &v57);
      v4 = a2;
      if ( v33 >= 0 )
      {
        v27 = v57;
LABEL_44:
        length = 0;
        if ( !v4 )
          v27 = v55;
        v17 = WindowsGetStringRawBuffer(v27, &length);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetImpl'::`2'::impl);
        if ( *v17 )
        {
          v34 = v58;
          if ( length + 1 <= v19 )
            goto LABEL_48;
          v6 *= 2;
          v48 = CoTaskMemRealloc(*v58, 2 * v6);
          *v34 = v48;
          if ( v48 )
          {
            v19 = v6 - v19;
LABEL_48:
            if ( !v10 )
              goto LABEL_63;
            if ( (unsigned __int64)(v6 - 1) > 0x7FFFFFFE )
            {
              v37 = -2147024809;
            }
            else
            {
              v35 = v6;
              v36 = *v34;
              do
              {
                if ( !*v36 )
                  break;
                ++v36;
                --v35;
              }
              while ( v35 );
              v37 = -2147024809;
              if ( v35 )
              {
                v38 = v6 - v35;
                v39 = 2147483646;
                v40 = L";";
                v41 = v6 - v38;
                v42 = (wchar_t *)((char *)*v34 + 2 * v38);
                if ( v6 != v38 )
                {
                  do
                  {
                    if ( !v39 )
                      break;
                    v43 = *v40;
                    if ( !*v40 )
                      break;
                    ++v40;
                    *v42++ = v43;
                    --v39;
                    --v41;
                  }
                  while ( v41 );
                }
                v44 = v42 - 1;
                if ( v41 )
                  v44 = v42;
                *v44 = 0;
                v37 = -2147024774;
                if ( v41 )
                  v37 = 0;
              }
            }
            --v19;
            if ( v37 >= 0 )
            {
LABEL_63:
              if ( (unsigned __int64)(v6 - 1) <= 0x7FFFFFFE )
              {
                v45 = v6;
                v46 = *v34;
                do
                {
                  if ( !*v46 )
                  {
                    v12 = v6 - v45;
                    goto LABEL_8;
                  }
                  ++v46;
                  --v45;
                }
                while ( v45 );
                v12 = 0;
LABEL_8:
                if ( v45 )
                {
                  v13 = 2147483646;
                  v14 = v6 - v12;
                  v15 = (WCHAR *)((char *)*v34 + 2 * v12);
                  if ( v6 != v12 )
                  {
                    do
                    {
                      if ( !v13 )
                        break;
                      v16 = *v17;
                      if ( !*v17 )
                        break;
                      ++v17;
                      *v15++ = v16;
                      --v13;
                      --v14;
                    }
                    while ( v14 );
                  }
                  v18 = v15 - 1;
                  if ( v14 )
                    v18 = v15;
                  *v18 = 0;
                }
              }
              v19 -= length;
            }
          }
        }
      }
      WindowsDeleteString(v57);
    }
    v10 += (unsigned __int64)StringRawBuffer + 1;
    WindowsDeleteString(v55);
    v55 = 0;
    StringRawBuffer = v61;
  }
  v8 = -2147024809;
LABEL_76:
  v3 = (WCHAR *)v58;
  v6 = 0;
LABEL_77:
  if ( *(_QWORD *)v3 )
  {
    CoTaskMemFree(*(LPVOID *)v3);
    *(_QWORD *)v3 = v6;
  }
LABEL_79:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x18002d9d0  mov     [rsp-8+arg_8], rbx
0x18002d9d5  push    rbp
0x18002d9d6  push    rsi
0x18002d9d7  push    rdi
0x18002d9d8  push    r12
0x18002d9da  push    r13
0x18002d9dc  push    r14
0x18002d9de  push    r15
0x18002d9e0  lea     rbp, [rsp-27h]
0x18002d9e5  sub     rsp, 0B0h
0x18002d9ec  mov     rax, cs:__security_cookie
0x18002d9f3  xor     rax, rsp
0x18002d9f6  mov     [rbp+57h+var_40], rax
0x18002d9fa  mov     rdi, r8
0x18002d9fd  mov     [rbp+57h+var_80], r8
0x18002da01  movzx   esi, dl
0x18002da04  mov     [rbp+57h+var_A0], dl
0x18002da07  mov     rbx, rcx
0x18002da0a  mov     [rbp+57h+var_70], rcx
0x18002da0e  xor     r14d, r14d
0x18002da11  mov     [r8], r14
0x18002da14  mov     [rbp+57h+string], r14
0x18002da18  test    rcx, rcx
0x18002da1b  jz      short loc_18002DA7D
0x18002da1d  xor     ecx, ecx; string
0x18002da1f  call    cs:__imp_WindowsDeleteString
0x18002da25  mov     [rbp+57h+string], r14
0x18002da29  xor     edx, edx
0x18002da2b  lea     r8, [rbp+57h+string]
0x18002da2f  mov     rcx, rbx
0x18002da32  call    cs:__imp_GetUserLanguagesForUser
0x18002da38  mov     ebx, eax
0x18002da3a  test    eax, eax
0x18002da3c  js      loc_18002DE78
0x18002da42  xor     edx, edx; length
0x18002da44  mov     rcx, [rbp+57h+string]; string
0x18002da48  call    cs:__imp_WindowsGetStringRawBuffer
0x18002da4e  mov     r15, rax
0x18002da51  mov     [rbp+57h+var_68], rax
0x18002da55  mov     [rdi], r14
0x18002da58  mov     [rbp+57h+var_78], r14
0x18002da5c  mov     eax, 2
0x18002da61  mov     r12d, 201h
0x18002da67  mul     r12
0x18002da6a  test    rdx, rdx
0x18002da6d  jz      loc_18002DE0F
0x18002da73  mov     ebx, 80070216h
0x18002da78  jmp     loc_18002DE78
0x18002da7d  call    cs:__imp_WindowsDeleteString
0x18002da83  mov     [rbp+57h+string], r14
0x18002da87  xor     ecx, ecx
0x18002da89  lea     rdx, [rbp+57h+string]
0x18002da8d  call    cs:__imp_GetUserLanguages
0x18002da93  jmp     short loc_18002DA38
0x18002da95  mov     rax, r14
0x18002da98  sub     rax, rcx
0x18002da9b  test    rcx, rcx
0x18002da9e  jz      short loc_18002DAE3
0x18002daa0  mov     ecx, 7FFFFFFEh
0x18002daa5  mov     rdx, r14
0x18002daa8  sub     rdx, rax
0x18002daab  lea     r8, [r8+rax*2]
0x18002daaf  jz      short loc_18002DAD3
0x18002dab1  test    rcx, rcx
0x18002dab4  jz      short loc_18002DAD3
0x18002dab6  movzx   eax, word ptr [rbx]
0x18002dab9  test    ax, ax
0x18002dabc  jz      short loc_18002DAD3
0x18002dabe  add     rbx, 2
0x18002dac2  mov     [r8], ax
0x18002dac6  add     r8, 2
0x18002daca  dec     rcx
0x18002dacd  sub     rdx, 1
0x18002dad1  jnz     short loc_18002DAB1
0x18002dad3  lea     rcx, [r8-2]
0x18002dad7  test    rdx, rdx
0x18002dada  cmovnz  rcx, r8
0x18002dade  xor     eax, eax
0x18002dae0  mov     [rcx], ax
0x18002dae3  mov     eax, [rbp+57h+length]
0x18002dae6  sub     r13, rax
0x18002dae9  mov     rcx, [rbp+57h+var_88]; string
0x18002daed  call    cs:__imp_WindowsDeleteString
0x18002daf3  inc     r15
0x18002daf6  add     r12, r15
0x18002daf9  mov     rcx, [rbp+57h+var_98]; string
0x18002dafd  call    cs:__imp_WindowsDeleteString
0x18002db03  xor     r8d, r8d
0x18002db06  mov     [rbp+57h+var_98], r8
0x18002db0a  mov     r15, [rbp+57h+var_68]
0x18002db0e  mov     rax, [rbp+57h+var_78]
0x18002db12  jmp     short loc_18002DB50
0x18002db14  mov     r14d, 200h
0x18002db1a  mov     r9d, r14d; unsigned __int64
0x18002db1d  xor     r8d, r8d; unsigned __int16 *
0x18002db20  mov     rdx, r12; unsigned __int64
0x18002db23  mov     rcx, rax; unsigned __int16 *
0x18002db26  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18002db2b  mov     r13d, r14d
0x18002db2e  xor     r12d, r12d
0x18002db31  mov     rcx, [rbp+57h+string]; string
0x18002db35  call    cs:__imp_WindowsGetStringLen
0x18002db3b  inc     eax
0x18002db3d  mov     [rbp+57h+var_78], rax
0x18002db41  xor     r8d, r8d
0x18002db44  nop     dword ptr [rax+00h]
0x18002db48  nop     dword ptr [rax+rax+00000000h]
0x18002db50  lea     rdi, [r15+r12*2]
0x18002db54  test    rdi, rdi
0x18002db57  jz      loc_18002DE6C
0x18002db5d  mov     rcx, rax
0x18002db60  sub     rcx, r12
0x18002db63  cmp     rcx, 7FFFFFFFh
0x18002db6a  ja      loc_18002DE6C
0x18002db70  mov     rax, rdi
0x18002db73  mov     rdx, rcx
0x18002db76  test    rcx, rcx
0x18002db79  jz      short loc_18002DB8B
0x18002db7b  cmp     word ptr [rax], 0
0x18002db7f  jz      short loc_18002DB8B
0x18002db81  add     rax, 2
0x18002db85  sub     rcx, 1
0x18002db89  jnz     short loc_18002DB7B
0x18002db8b  mov     ebx, 80070057h
0x18002db90  test    rcx, rcx
0x18002db93  cmovnz  ebx, r8d
0x18002db97  sub     rdx, rcx
0x18002db9a  mov     r15, r8
0x18002db9d  test    rcx, rcx
0x18002dba0  cmovnz  r15, rdx
0x18002dba4  jz      loc_18002DE71
0x18002dbaa  test    r15, r15
0x18002dbad  jz      loc_18002DE89
0x18002dbb3  mov     [rbp+57h+var_98], r8
0x18002dbb7  mov     rbx, [rbp+57h+var_70]
0x18002dbbb  xor     ecx, ecx; string
0x18002dbbd  call    cs:__imp_WindowsDeleteString
0x18002dbc3  mov     [rbp+57h+var_98], 0
0x18002dbcb  test    rbx, rbx
0x18002dbce  jz      loc_18002DDDB
0x18002dbd4  mov     r8d, 3Bh ; ';'
0x18002dbda  lea     r9, [rbp+57h+var_98]
0x18002dbde  mov     rdx, rdi
0x18002dbe1  mov     rcx, rbx
0x18002dbe4  call    cs:__imp_GetUserLanguageInputMethodsForUser
0x18002dbea  test    eax, eax
0x18002dbec  js      loc_18002DAF3
0x18002dbf2  xor     ecx, ecx; string
0x18002dbf4  mov     [rbp+57h+var_88], rcx
0x18002dbf8  test    sil, sil
0x18002dbfb  jz      loc_18002DCAD
0x18002dc01  call    cs:__imp_WindowsDeleteString
0x18002dc07  mov     [rbp+57h+var_88], 0
0x18002dc0f  mov     [rbp+57h+var_48], 0
0x18002dc17  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002dc1e  xchg    ax, ax
0x18002dc20  inc     rbx
0x18002dc23  cmp     word ptr [rdi+rbx*2], 0
0x18002dc28  jnz     short loc_18002DC20
0x18002dc2a  mov     eax, 0FFFFFFFFh
0x18002dc2f  cmp     rbx, rax
0x18002dc32  jbe     short loc_18002DC4B
0x18002dc34  xor     r9d, r9d; lpArguments
0x18002dc37  xor     r8d, r8d; nNumberOfArguments
0x18002dc3a  mov     edx, 1; dwExceptionFlags
0x18002dc3f  mov     ecx, 80070216h; dwExceptionCode
0x18002dc44  call    cs:__imp_RaiseException
0x18002dc4a  int     3; Trap to Debugger
0x18002dc4b  mov     ecx, ebx; unsigned int
0x18002dc4d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002dc52  cmp     ebx, eax
0x18002dc54  jnb     loc_18002DE30
0x18002dc5a  lea     r9, [rbp+57h+var_48]; string
0x18002dc5e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002dc62  mov     edx, ebx; length
0x18002dc64  mov     rcx, rdi; sourceString
0x18002dc67  call    cs:__imp_WindowsCreateStringReference
0x18002dc6d  test    eax, eax
0x18002dc6f  js      loc_18002DDFB
0x18002dc75  mov     rdi, [rbp+57h+var_48]
0x18002dc79  mov     rsi, [rbp+57h+var_98]
0x18002dc7d  mov     ebx, 8007007Fh
0x18002dc82  call    IsWGITransformInputMethodsForLanguagePresent
0x18002dc87  test    al, al
0x18002dc89  jz      short loc_18002DC9D
0x18002dc8b  lea     r8, [rbp+57h+var_88]
0x18002dc8f  mov     rdx, rdi
0x18002dc92  mov     rcx, rsi
0x18002dc95  call    cs:__imp_WGITransformInputMethodsForLanguage
0x18002dc9b  mov     ebx, eax
0x18002dc9d  movzx   esi, [rbp+57h+var_A0]
0x18002dca1  test    ebx, ebx
0x18002dca3  js      loc_18002DAE9
0x18002dca9  mov     rcx, [rbp+57h+var_88]; string
0x18002dcad  mov     [rbp+57h+length], 0
0x18002dcb4  lea     rdx, [rbp+57h+length]; length
0x18002dcb8  test    sil, sil
0x18002dcbb  jz      loc_18002DDF2
0x18002dcc1  call    cs:__imp_WindowsGetStringRawBuffer
0x18002dcc7  mov     rbx, rax
0x18002dcca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput> `wil::Feature<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::GetImpl(void)'::`2'::impl
0x18002dcd1  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonUINoUpdateUserInput@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonUINoUpdateUserInput>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18002dcd6  cmp     word ptr [rbx], 0
0x18002dcda  jz      loc_18002DAE9
0x18002dce0  mov     ecx, [rbp+57h+length]
0x18002dce3  inc     ecx
0x18002dce5  mov     rdi, [rbp+57h+var_80]
0x18002dce9  cmp     rcx, r13
0x18002dcec  ja      loc_18002DE38
0x18002dcf2  test    r12, r12
0x18002dcf5  jz      loc_18002DD9E
0x18002dcfb  lea     rax, [r14-1]
0x18002dcff  cmp     rax, 7FFFFFFEh
0x18002dd05  ja      loc_18002DE62
0x18002dd0b  mov     r9, [rdi]
0x18002dd0e  mov     rcx, r14
0x18002dd11  mov     rax, r9
0x18002dd14  cmp     word ptr [rax], 0
0x18002dd18  jz      short loc_18002DD24
0x18002dd1a  add     rax, 2
0x18002dd1e  sub     rcx, 1
0x18002dd22  jnz     short loc_18002DD14
0x18002dd24  mov     edx, 80070057h
0x18002dd29  xor     eax, eax
0x18002dd2b  test    rcx, rcx
0x18002dd2e  cmovnz  edx, eax
0x18002dd31  jz      short loc_18002DD93
0x18002dd33  mov     rax, r14
0x18002dd36  sub     rax, rcx
0x18002dd39  test    rcx, rcx
0x18002dd3c  jz      short loc_18002DD93
0x18002dd3e  mov     ecx, 7FFFFFFEh
0x18002dd43  lea     rdx, asc_1800A9754; ";"
0x18002dd4a  mov     r8, r14
0x18002dd4d  sub     r8, rax
0x18002dd50  lea     r9, [r9+rax*2]
0x18002dd54  jz      short loc_18002DD78
0x18002dd56  test    rcx, rcx
0x18002dd59  jz      short loc_18002DD78
0x18002dd5b  movzx   eax, word ptr [rdx]
0x18002dd5e  test    ax, ax
0x18002dd61  jz      short loc_18002DD78
0x18002dd63  add     rdx, 2
0x18002dd67  mov     [r9], ax
0x18002dd6b  add     r9, 2
0x18002dd6f  dec     rcx
0x18002dd72  sub     r8, 1
0x18002dd76  jnz     short loc_18002DD56
0x18002dd78  lea     rcx, [r9-2]
0x18002dd7c  test    r8, r8
0x18002dd7f  cmovnz  rcx, r9
0x18002dd83  xor     eax, eax
0x18002dd85  mov     [rcx], ax
0x18002dd88  mov     edx, 8007007Ah
0x18002dd8d  test    r8, r8
0x18002dd90  cmovnz  edx, eax
0x18002dd93  dec     r13
0x18002dd96  test    edx, edx
0x18002dd98  js      loc_18002DAE9
0x18002dd9e  lea     rax, [r14-1]
0x18002dda2  cmp     rax, 7FFFFFFEh
0x18002dda8  ja      loc_18002DAE3
0x18002ddae  mov     r8, [rdi]
0x18002ddb1  mov     rcx, r14
0x18002ddb4  mov     rax, r8
0x18002ddb7  nop     word ptr [rax+rax+00000000h]
0x18002ddc0  cmp     word ptr [rax], 0
0x18002ddc4  jz      loc_18002DA95
0x18002ddca  add     rax, 2
0x18002ddce  sub     rcx, 1
0x18002ddd2  jnz     short loc_18002DDC0
0x18002ddd4  xor     eax, eax
0x18002ddd6  jmp     loc_18002DA9B
0x18002dddb  mov     edx, 3Bh ; ';'
0x18002dde0  lea     r8, [rbp+57h+var_98]
0x18002dde4  mov     rcx, rdi
0x18002dde7  call    cs:__imp_GetUserLanguageInputMethods
0x18002dded  jmp     loc_18002DBEA
0x18002ddf2  mov     rcx, [rbp+57h+var_98]
0x18002ddf6  jmp     loc_18002DCC1
0x18002ddfb  xor     r9d, r9d; lpArguments
0x18002ddfe  xor     r8d, r8d; nNumberOfArguments
0x18002de01  mov     edx, 1; dwExceptionFlags
0x18002de06  mov     ecx, eax; dwExceptionCode
0x18002de08  call    cs:__imp_RaiseException
0x18002de0e  nop
0x18002de0f  mov     rcx, rax; cb
0x18002de12  call    cs:__imp_CoTaskMemAlloc
0x18002de18  mov     [rdi], rax
0x18002de1b  mov     ebx, r14d
0x18002de1e  mov     ecx, 8007000Eh
0x18002de23  test    rax, rax
0x18002de26  cmovz   ebx, ecx
0x18002de29  jz      short loc_18002DE78
0x18002de2b  jmp     loc_18002DB14
0x18002de30  lea     ebx, [rax-1]
0x18002de33  jmp     loc_18002DC5A
0x18002de38  add     r14, r14
0x18002de3b  lea     rdx, [r14+r14]; cb
0x18002de3f  mov     rcx, [rdi]; pv
  ... truncated ...
```
