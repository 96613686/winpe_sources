# CSpellerGlobalState::LogMultilingual(ISpellChecker *,ushort const *,int,bool,ushort const *,bool)

- ea: `0x18010ebd0`
- end: `0x18010ecb2`
- name: `?LogMultilingual@CSpellerGlobalState@@QEAA_NPEAUISpellChecker@@PEBGH_N12@Z`
- size: `226`
- prototype: `bool(CSpellerGlobalState *__hidden this, struct ISpellChecker *, const unsigned __int16 *, int, bool, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180108e3c`
- `0x180270400`

## callees

- `0x18010ebd0`
- `0x180120444`
- `0x180123e7c`
- `0x180127034`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ec54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ec54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ec2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ec9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ec2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010ec9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ec91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010ec91`

## pseudocode

```c
char __fastcall CSpellerGlobalState::LogMultilingual(
        CSpellerGlobalState *this,
        struct ISpellChecker *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        bool a5,
        const unsigned __int16 *a6,
        bool a7)
{
  __int64 v7; // rax
  char v10; // si
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, HSTRING *); // rbx
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // cl
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v16; // rcx
  CSpellCheckerTelemetry *v17; // rcx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  string = (HSTRING)a3;
  v7 = *(_QWORD *)a2;
  pv = 0;
  v10 = 0;
  if ( (*(int (__fastcall **)(struct ISpellChecker *, LPVOID *))(v7 + 24))(a2, &pv) >= 0 )
  {
    v11 = *((_QWORD *)this + 37);
    string = 0;
    v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v12(v11, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( a7 )
      {
        if ( CSpellCheckerTelemetry::IsEnabled(v14, v13) )
        {
          wil::details::static_lazy<CSpellCheckerTelemetry>::get(
            v16,
            _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_);
          CSpellCheckerTelemetry::LogSpellerMultilingual_(v17, (unsigned __int16 *)pv, StringRawBuffer, a4);
        }
        v10 = 1;
      }
    }
    CoTaskMemFree(pv);
    WindowsDeleteString(string);
  }
  return v10;
}

```

## disassembly

```asm
0x18010ebd0  mov     r11, rsp
0x18010ebd3  mov     [r11+8], rbx
0x18010ebd7  mov     [r11+18h], r8
0x18010ebdb  push    rbp
0x18010ebdc  push    rsi
0x18010ebdd  push    rdi
0x18010ebde  sub     rsp, 20h
0x18010ebe2  mov     rax, [rdx]
0x18010ebe5  mov     r8, rdx
0x18010ebe8  mov     rdi, rcx
0x18010ebeb  mov     qword ptr [r11+10h], 0
0x18010ebf3  lea     rdx, [r11+10h]
0x18010ebf7  mov     rcx, r8
0x18010ebfa  mov     ebp, r9d
0x18010ebfd  xor     sil, sil
0x18010ec00  mov     rax, [rax+18h]
0x18010ec04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ec09  test    eax, eax
0x18010ec0b  js      loc_18010ECA2
0x18010ec11  mov     rdi, [rdi+128h]
0x18010ec18  xor     ecx, ecx; string
0x18010ec1a  mov     [rsp+38h+string], 0
0x18010ec23  mov     rax, [rdi]
0x18010ec26  mov     rbx, [rax+38h]
0x18010ec2a  call    cs:__imp_WindowsDeleteString
0x18010ec30  lea     rdx, [rsp+38h+string]
0x18010ec35  mov     [rsp+38h+string], 0
0x18010ec3e  mov     rcx, rdi
0x18010ec41  mov     rax, rbx
0x18010ec44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ec49  test    eax, eax
0x18010ec4b  js      short loc_18010EC8C
0x18010ec4d  mov     rcx, [rsp+38h+string]; string
0x18010ec52  xor     edx, edx; length
0x18010ec54  call    cs:__imp_WindowsGetStringRawBuffer
0x18010ec5a  mov     rbx, rax
0x18010ec5d  cmp     [rsp+38h+arg_30], sil
0x18010ec62  jz      short loc_18010EC8C
0x18010ec64  call    ?IsEnabled@CSpellCheckerTelemetry@@SA_NE_K@Z; CSpellCheckerTelemetry::IsEnabled(uchar,unsigned __int64)
0x18010ec69  test    al, al
0x18010ec6b  jz      short loc_18010EC89
0x18010ec6d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3c853e741dc03bb96b7f8662095382b4_@@CA@XZ; _lambda_3c853e741dc03bb96b7f8662095382b4_::_lambda_invoker_cdecl_(void)
0x18010ec74  call    ?get@?$static_lazy@VCSpellCheckerTelemetry@@@details@wil@@QEAAPEAVCSpellCheckerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CSpellCheckerTelemetry>::get(void (*)(void))
0x18010ec79  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x18010ec7e  mov     r9d, ebp; unsigned int
0x18010ec81  mov     r8, rbx; unsigned __int16 *
0x18010ec84  call    ?LogSpellerMultilingual_@CSpellCheckerTelemetry@@QEBAXPEAGPEBGK@Z; CSpellCheckerTelemetry::LogSpellerMultilingual_(ushort *,ushort const *,ulong)
0x18010ec89  mov     sil, 1
0x18010ec8c  mov     rcx, [rsp+38h+pv]; pv
0x18010ec91  call    cs:__imp_CoTaskMemFree
0x18010ec97  mov     rcx, [rsp+38h+string]; string
0x18010ec9c  call    cs:__imp_WindowsDeleteString
0x18010eca2  mov     rbx, [rsp+38h+arg_0]
0x18010eca7  mov     al, sil
0x18010ecaa  add     rsp, 20h
0x18010ecae  pop     rdi
0x18010ecaf  pop     rsi
0x18010ecb0  pop     rbp
0x18010ecb1  retn
```
