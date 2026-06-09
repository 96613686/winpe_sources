# OuOpenKey(void *,wchar_t const *,void * *)

- ea: `0x1800856c4`
- end: `0x1800857ae`
- name: `?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(void *, const wchar_t *, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800829a0`
- `0x180082f64`
- `0x180083d74`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18007e720`
- `0x1800856c4`
- `0x180085dfc`

## string_xrefs

- `0x1800856f6`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085754`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085709`: `OuOpenKey`
- `0x180085767`: `OuOpenKey`
- `0x180085772`: `OROpenKey(ParentHandle, KeyName, Handle)`

## pseudocode

```c
__int64 __fastcall OuOpenKey(void *a1, const wchar_t *a2, void **a3)
{
  const char *v3; // rax
  signed int v5; // eax
  const char *v6; // [rsp+20h] [rbp-30h] BYREF
  const char *v7; // [rsp+28h] [rbp-28h]
  __int64 v8; // [rsp+30h] [rbp-20h]
  const char *v9; // [rsp+38h] [rbp-18h]
  int v10; // [rsp+40h] [rbp-10h] BYREF

  v10 = 0;
  if ( !a1 )
  {
    v8 = 69;
    v3 = "Not-null check failed: ParentHandle";
LABEL_3:
    v9 = v3;
    v6 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v7 = "OuOpenKey";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v10,
             &v6);
  }
  if ( !a2 )
  {
    v8 = 70;
    v3 = "Not-null check failed: KeyName";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v8 = 71;
    v3 = "Not-null check failed: Handle";
    goto LABEL_3;
  }
  v5 = OROpenKey();
  if ( !v5 )
    return 0;
  v8 = 73;
  v6 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
  v7 = "OuOpenKey";
  v9 = "OROpenKey(ParentHandle, KeyName, Handle)";
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
           &v10,
           &v6,
           (unsigned int)v5);
}

```

## disassembly

```asm
0x1800856c4  push    rbp
0x1800856c6  mov     rbp, rsp
0x1800856c9  sub     rsp, 50h
0x1800856cd  mov     rax, cs:__security_cookie
0x1800856d4  xor     rax, rsp
0x1800856d7  mov     [rbp+var_8], rax
0x1800856db  mov     [rbp+var_10], 0
0x1800856e2  test    rcx, rcx
0x1800856e5  jnz     short loc_18008571F
0x1800856e7  mov     [rbp+var_20], 45h ; 'E'
0x1800856ef  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ParentHandle"
0x1800856f6  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800856fd  mov     [rbp+var_18], rax
0x180085701  mov     [rbp+var_30], rcx
0x180085705  lea     rdx, [rbp+var_30]
0x180085709  lea     rcx, aOuopenkey; "OuOpenKey"
0x180085710  mov     [rbp+var_28], rcx
0x180085714  lea     rcx, [rbp+var_10]
0x180085718  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18008571d  jmp     short loc_18008579B
0x18008571f  test    rdx, rdx
0x180085722  jnz     short loc_180085735
0x180085724  mov     [rbp+var_20], 46h ; 'F'
0x18008572c  lea     rax, aNotNullCheckFa_55; "Not-null check failed: KeyName"
0x180085733  jmp     short loc_1800856F6
0x180085735  test    r8, r8
0x180085738  jnz     short loc_18008574B
0x18008573a  mov     [rbp+var_20], 47h ; 'G'
0x180085742  lea     rax, aNotNullCheckFa_96; "Not-null check failed: Handle"
0x180085749  jmp     short loc_1800856F6
0x18008574b  call    OROpenKey
0x180085750  test    eax, eax
0x180085752  jz      short loc_180085799
0x180085754  lea     rcx, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008575b  mov     [rbp+var_20], 49h ; 'I'
0x180085763  mov     [rbp+var_30], rcx
0x180085767  lea     rcx, aOuopenkey; "OuOpenKey"
0x18008576e  mov     [rbp+var_28], rcx
0x180085772  lea     rcx, aOropenkeyParen; "OROpenKey(ParentHandle, KeyName, Handle"...
0x180085779  mov     [rbp+var_18], rcx
0x18008577d  jle     short loc_180085787
0x18008577f  movzx   eax, ax
0x180085782  or      eax, 80070000h
0x180085787  mov     r8d, eax
0x18008578a  lea     rdx, [rbp+var_30]
0x18008578e  lea     rcx, [rbp+var_10]
0x180085792  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180085797  jmp     short loc_18008579B
0x180085799  xor     eax, eax
0x18008579b  mov     rcx, [rbp+var_8]
0x18008579f  xor     rcx, rsp; StackCookie
0x1800857a2  call    __security_check_cookie
0x1800857a7  add     rsp, 50h
0x1800857ab  pop     rbp
0x1800857ac  retn
```
