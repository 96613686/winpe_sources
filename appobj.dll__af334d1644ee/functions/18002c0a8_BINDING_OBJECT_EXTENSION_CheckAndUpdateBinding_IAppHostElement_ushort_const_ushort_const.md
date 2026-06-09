# BINDING_OBJECT_EXTENSION::CheckAndUpdateBinding(IAppHostElement *,ushort const *,ushort const *)

- ea: `0x18002c0a8`
- end: `0x18002c20d`
- name: `?CheckAndUpdateBinding@BINDING_OBJECT_EXTENSION@@AEAAJPEAUIAppHostElement@@PEBG1@Z`
- size: `357`
- prototype: `__int64 __fastcall(BINDING_OBJECT_EXTENSION *this, struct IAppHostElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c540`

## callees

- `0x18002c0a8`
- `0x18002c35c`
- `0x18002c460`
- `0x18002c98c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002c10b`
- `msvcrt!_wcsicmp` at `0x18002c13d`
- `msvcrt!_wcsicmp` at `0x18002c10b`
- `msvcrt!_wcsicmp` at `0x18002c13d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c189`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c19b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1db`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c189`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c19b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1db`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c1f2`

## string_xrefs

- `0x18002c0ea`: `protocol`
- `0x18002c14e`: `certificateStoreName`

## pseudocode

```c
__int64 __fastcall BINDING_OBJECT_EXTENSION::CheckAndUpdateBinding(
        BINDING_OBJECT_EXTENSION *this,
        struct IAppHostElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int ElementStringProperty; // ebx
  BINDING_OBJECT_EXTENSION *v8; // rcx
  BSTR v10; // [rsp+20h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+28h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+20h] BYREF

  String1 = 0;
  v10 = 0;
  bstrString = 0;
  ElementStringProperty = GetElementStringProperty(a2, L"protocol", &String1);
  if ( ElementStringProperty >= 0 )
  {
    if ( _wcsicmp(String1, L"https") )
    {
LABEL_10:
      SysFreeString(String1);
      String1 = 0;
      goto LABEL_11;
    }
    ElementStringProperty = GetElementStringProperty(a2, L"certificateHash", &v10);
    if ( ElementStringProperty < 0 )
      goto LABEL_11;
    if ( _wcsicmp(v10, a3) )
    {
LABEL_9:
      SysFreeString(v10);
      v10 = 0;
      goto LABEL_10;
    }
    ElementStringProperty = GetElementStringProperty(a2, L"certificateStoreName", &bstrString);
    if ( ElementStringProperty >= 0 )
    {
      if ( BINDING_OBJECT_EXTENSION::DoesCertExists(a4, bstrString) )
      {
        ElementStringProperty = BINDING_OBJECT_EXTENSION::ExecuteRebindSslCertificate(v8, a2, a4, bstrString);
        if ( ElementStringProperty >= 0 )
        {
          SysFreeString(bstrString);
          bstrString = 0;
          goto LABEL_9;
        }
      }
    }
  }
LABEL_11:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v10 )
  {
    SysFreeString(v10);
    v10 = 0;
  }
  if ( String1 )
    SysFreeString(String1);
  return (unsigned int)ElementStringProperty;
}

```

## disassembly

```asm
0x18002c0a8  mov     [rsp-18h+arg_8], rbx
0x18002c0ad  mov     [rsp-18h+arg_10], rsi
0x18002c0b2  mov     [rsp-18h+bstrString], rcx
0x18002c0b7  push    rbp
0x18002c0b8  push    rdi
0x18002c0b9  push    r14
0x18002c0bb  mov     rbp, rsp
0x18002c0be  sub     rsp, 30h
0x18002c0c2  mov     rdi, rdx
0x18002c0c5  mov     [rbp+String1], 0
0x18002c0cd  mov     r14, r8
0x18002c0d0  mov     [rbp+var_10], 0
0x18002c0d8  mov     rcx, rdi; struct IAppHostElement *
0x18002c0db  mov     [rbp+bstrString], 0
0x18002c0e3  lea     r8, [rbp+String1]; unsigned __int16 **
0x18002c0e7  mov     rsi, r9
0x18002c0ea  lea     rdx, aProtocol; "protocol"
0x18002c0f1  call    ?GetElementStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; GetElementStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18002c0f6  mov     ebx, eax
0x18002c0f8  test    eax, eax
0x18002c0fa  js      loc_18002C1BB
0x18002c100  mov     rcx, [rbp+String1]; String1
0x18002c104  lea     rdx, aHttps; "https"
0x18002c10b  call    cs:__imp__wcsicmp
0x18002c111  test    eax, eax
0x18002c113  jnz     loc_18002C1A9
0x18002c119  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18002c11d  mov     rcx, rdi; struct IAppHostElement *
0x18002c120  lea     rdx, aCertificatehas; "certificateHash"
0x18002c127  call    ?GetElementStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; GetElementStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18002c12c  mov     ebx, eax
0x18002c12e  test    eax, eax
0x18002c130  js      loc_18002C1BB
0x18002c136  mov     rcx, [rbp+var_10]; String1
0x18002c13a  mov     rdx, r14; String2
0x18002c13d  call    cs:__imp__wcsicmp
0x18002c143  test    eax, eax
0x18002c145  jnz     short loc_18002C197
0x18002c147  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18002c14b  mov     rcx, rdi; struct IAppHostElement *
0x18002c14e  lea     rdx, aCertificatesto; "certificateStoreName"
0x18002c155  call    ?GetElementStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; GetElementStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18002c15a  mov     ebx, eax
0x18002c15c  test    eax, eax
0x18002c15e  js      short loc_18002C1BB
0x18002c160  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18002c164  mov     rcx, rsi; unsigned __int16 *
0x18002c167  call    ?DoesCertExists@BINDING_OBJECT_EXTENSION@@CAHPEBG0@Z; BINDING_OBJECT_EXTENSION::DoesCertExists(ushort const *,ushort const *)
0x18002c16c  test    eax, eax
0x18002c16e  jz      short loc_18002C1BB
0x18002c170  mov     r9, [rbp+bstrString]; unsigned __int16 *
0x18002c174  mov     r8, rsi; unsigned __int16 *
0x18002c177  mov     rdx, rdi; struct IAppHostElement *
0x18002c17a  call    ?ExecuteRebindSslCertificate@BINDING_OBJECT_EXTENSION@@AEAAJPEAUIAppHostElement@@PEBG1@Z; BINDING_OBJECT_EXTENSION::ExecuteRebindSslCertificate(IAppHostElement *,ushort const *,ushort const *)
0x18002c17f  mov     ebx, eax
0x18002c181  test    eax, eax
0x18002c183  js      short loc_18002C1BB
0x18002c185  mov     rcx, [rbp+bstrString]; bstrString
0x18002c189  call    cs:__imp_SysFreeString
0x18002c18f  mov     [rbp+bstrString], 0
0x18002c197  mov     rcx, [rbp+var_10]; bstrString
0x18002c19b  call    cs:__imp_SysFreeString
0x18002c1a1  mov     [rbp+var_10], 0
0x18002c1a9  mov     rcx, [rbp+String1]; bstrString
0x18002c1ad  call    cs:__imp_SysFreeString
0x18002c1b3  mov     [rbp+String1], 0
0x18002c1bb  mov     rcx, [rbp+bstrString]; bstrString
0x18002c1bf  test    rcx, rcx
0x18002c1c2  jz      short loc_18002C1D2
0x18002c1c4  call    cs:__imp_SysFreeString
0x18002c1ca  mov     [rbp+bstrString], 0
0x18002c1d2  mov     rcx, [rbp+var_10]; bstrString
0x18002c1d6  test    rcx, rcx
0x18002c1d9  jz      short loc_18002C1E9
0x18002c1db  call    cs:__imp_SysFreeString
0x18002c1e1  mov     [rbp+var_10], 0
0x18002c1e9  mov     rcx, [rbp+String1]; bstrString
0x18002c1ed  test    rcx, rcx
0x18002c1f0  jz      short loc_18002C1F8
0x18002c1f2  call    cs:__imp_SysFreeString
0x18002c1f8  mov     rsi, [rsp+30h+arg_10]
0x18002c1fd  mov     eax, ebx
0x18002c1ff  mov     rbx, [rsp+30h+arg_8]
0x18002c204  add     rsp, 30h
0x18002c208  pop     r14
0x18002c20a  pop     rdi
0x18002c20b  pop     rbp
0x18002c20c  retn
```
