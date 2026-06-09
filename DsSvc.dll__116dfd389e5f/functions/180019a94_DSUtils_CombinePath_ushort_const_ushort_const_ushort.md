# DSUtils::CombinePath(ushort const *,ushort const *,ushort * *)

- ea: `0x180019a94`
- end: `0x180019b1b`
- name: `?CombinePath@DSUtils@@YAJPEBG0PEAPEAG@Z`
- size: `135`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, PCWSTR pszMore, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800109d8`
- `0x180012f20`

## callees

- `0x18000c728`
- `0x18000c93c`
- `0x180019a94`
- `0x18001afe8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180019ae2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180019ae2`

## pseudocode

```c
__int64 __fastcall DSUtils::CombinePath(PCWSTR pszPathIn, PCWSTR pszMore, unsigned __int16 *a3, unsigned __int16 **a4)
{
  PWSTR *v7; // rax
  HRESULT v8; // edi
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  if ( !pszPathIn )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, pszMore);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(pszPathIn, pszMore);
  v10 = 0;
  v7 = (PWSTR *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&v10);
  v8 = PathAllocCombine(pszPathIn, pszMore, 1u, v7);
  if ( v8 >= 0 )
  {
    *(_QWORD *)a3 = v10;
    v10 = 0;
  }
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019a94  mov     [rsp+arg_8], rbx
0x180019a99  mov     [rsp+arg_10], rsi
0x180019a9e  push    rdi
0x180019a9f  sub     rsp, 20h
0x180019aa3  mov     rbx, r8
0x180019aa6  mov     rsi, rdx
0x180019aa9  mov     rdi, rcx
0x180019aac  test    rcx, rcx
0x180019aaf  jnz     short loc_180019AB6
0x180019ab1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019ab6  test    rbx, rbx
0x180019ab9  jnz     short loc_180019AC0
0x180019abb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019ac0  lea     rcx, [rsp+28h+arg_0]
0x180019ac5  mov     [rsp+28h+arg_0], 0
0x180019ace  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180019ad3  mov     r9, rax; ppszPathOut
0x180019ad6  mov     r8d, 1; dwFlags
0x180019adc  mov     rdx, rsi; pszMore
0x180019adf  mov     rcx, rdi; pszPathIn
0x180019ae2  call    cs:__imp_PathAllocCombine
0x180019ae8  mov     edi, eax
0x180019aea  test    eax, eax
0x180019aec  js      short loc_180019AFF
0x180019aee  mov     rcx, [rsp+28h+arg_0]
0x180019af3  mov     [rbx], rcx
0x180019af6  mov     [rsp+28h+arg_0], 0
0x180019aff  lea     rcx, [rsp+28h+arg_0]
0x180019b04  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180019b09  mov     rbx, [rsp+28h+arg_8]
0x180019b0e  mov     eax, edi
0x180019b10  mov     rsi, [rsp+28h+arg_10]
0x180019b15  add     rsp, 20h
0x180019b19  pop     rdi
0x180019b1a  retn
```
