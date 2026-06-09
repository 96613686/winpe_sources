# WaaS2::Device::GetStringPropertyWithDefault

- ea: `0x180053c50`
- end: `0x180053db5`
- name: `WaaS2::Device::GetStringPropertyWithDefault`
- size: `357`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003c5a0`
- `0x18004be64`
- `0x18004c518`
- `0x18004caa8`
- `0x18004d13c`
- `0x18004d6f8`

## callees

- `0x1800050a0`
- `0x180008d99`
- `0x18000bbd4`
- `0x18000ea1c`
- `0x180010e54`
- `0x180024360`
- `0x18002cbc4`
- `0x180053c50`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053cc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053cc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d95`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaaS2::Device::GetStringPropertyWithDefault(__int64 a1, _QWORD *a2, __int64 a3, char **a4)
{
  __int64 v7; // rdx
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbp
  __int64 v10; // rax
  int v11; // eax
  char v12; // al
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v14; // rdx
  char *v15; // rdi
  __int64 v16; // rbx
  HSTRING string; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v18; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v19[32]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  std::wstring::operator=(a4, a3);
  if ( !a1 )
  {
    v7 = 244;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)0x80070057LL,
      (int)string);
    return 2147942487LL;
  }
  if ( !a2[2] )
  {
    v7 = 245;
    goto LABEL_3;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a1 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v18 = a2;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v19, &v18);
  v11 = v9(a1, *(_QWORD *)(v10 + 24), &string);
  if ( v11 >= 0 )
  {
    v12 = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)(unsigned int)v11,
      (int)string);
    v12 = 0;
  }
  if ( v12 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( StringRawBuffer )
    {
      v14 = -1;
      do
        ++v14;
      while ( StringRawBuffer[v14] );
      if ( v14 > (unsigned __int64)a4[3] )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a4);
      }
      else
      {
        if ( (unsigned __int64)a4[3] <= 7 )
          v15 = (char *)a4;
        else
          v15 = *a4;
        a4[2] = (char *)v14;
        v16 = 2 * v14;
        memmove_0(v15, StringRawBuffer, 2 * v14);
        *(_WORD *)&v15[v16] = 0;
      }
    }
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180053c50  push    rbx
0x180053c52  push    rbp
0x180053c53  push    rsi
0x180053c54  push    rdi
0x180053c55  push    r14
0x180053c57  sub     rsp, 60h
0x180053c5b  mov     rax, cs:__security_cookie
0x180053c62  xor     rax, rsp
0x180053c65  mov     [rsp+88h+var_38], rax
0x180053c6a  mov     rbx, r9
0x180053c6d  mov     rdi, rdx
0x180053c70  mov     rsi, rcx
0x180053c73  mov     rdx, r8
0x180053c76  mov     rcx, r9
0x180053c79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180053c7e  xor     r14d, r14d
0x180053c81  test    rsi, rsi
0x180053c84  jnz     short loc_180053CAE
0x180053c86  mov     edx, 0F4h; void *
0x180053c8b  mov     ebx, 80070057h
0x180053c90  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180053c97  mov     r9d, ebx; char *
0x180053c9a  mov     rcx, [rsp+88h]; this
0x180053ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053ca7  mov     eax, ebx
0x180053ca9  jmp     loc_180053D9D
0x180053cae  cmp     [rdi+10h], r14
0x180053cb2  jnz     short loc_180053CBB
0x180053cb4  mov     edx, 0F5h
0x180053cb9  jmp     short loc_180053C8B
0x180053cbb  mov     [rsp+88h+string], r14
0x180053cc0  mov     rax, [rsi]
0x180053cc3  mov     rbp, [rax+50h]
0x180053cc7  xor     ecx, ecx; string
0x180053cc9  call    cs:__imp_WindowsDeleteString
0x180053ccf  mov     [rsp+88h+string], r14; int
0x180053cd4  cmp     qword ptr [rdi+18h], 7
0x180053cd9  jbe     short loc_180053CDE
0x180053cdb  mov     rdi, [rdi]
0x180053cde  mov     [rsp+88h+var_60], rdi
0x180053ce3  lea     rdx, [rsp+88h+var_60]
0x180053ce8  lea     rcx, [rsp+88h+var_58]
0x180053ced  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180053cf2  nop
0x180053cf3  lea     r8, [rsp+88h+string]
0x180053cf8  mov     rdx, [rax+18h]
0x180053cfc  mov     rcx, rsi
0x180053cff  mov     rax, rbp
0x180053d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d07  mov     rcx, [rsp+88h]; this
0x180053d0f  test    eax, eax
0x180053d11  jns     short loc_180053D2C
0x180053d13  mov     r9d, eax; char *
0x180053d16  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180053d1d  mov     edx, 0F8h; void *
0x180053d22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053d27  mov     al, r14b
0x180053d2a  jmp     short loc_180053D2E
0x180053d2c  mov     al, 1
0x180053d2e  test    al, al
0x180053d30  jz      short loc_180053D90
0x180053d32  xor     edx, edx; length
0x180053d34  mov     rcx, [rsp+88h+string]; string
0x180053d39  call    cs:__imp_WindowsGetStringRawBuffer
0x180053d3f  test    rax, rax
0x180053d42  jz      short loc_180053D90
0x180053d44  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180053d48  inc     rdx
0x180053d4b  cmp     [rax+rdx*2], r14w
0x180053d50  jnz     short loc_180053D48
0x180053d52  cmp     rdx, [rbx+18h]
0x180053d56  ja      short loc_180053D84
0x180053d58  cmp     qword ptr [rbx+18h], 7
0x180053d5d  jbe     short loc_180053D64
0x180053d5f  mov     rdi, [rbx]
0x180053d62  jmp     short loc_180053D67
0x180053d64  mov     rdi, rbx
0x180053d67  mov     [rbx+10h], rdx
0x180053d6b  lea     rbx, [rdx+rdx]
0x180053d6f  mov     r8, rbx; Size
0x180053d72  mov     rdx, rax; Src
0x180053d75  mov     rcx, rdi; void *
0x180053d78  call    memmove_0
0x180053d7d  mov     [rbx+rdi], r14w
0x180053d82  jmp     short loc_180053D90
0x180053d84  mov     r9, rax
0x180053d87  mov     rcx, rbx
0x180053d8a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180053d8f  nop
0x180053d90  mov     rcx, [rsp+88h+string]; string
0x180053d95  call    cs:__imp_WindowsDeleteString
0x180053d9b  xor     eax, eax
0x180053d9d  mov     rcx, [rsp+88h+var_38]
0x180053da2  xor     rcx, rsp; StackCookie
0x180053da5  call    __security_check_cookie
0x180053daa  add     rsp, 60h
0x180053dae  pop     r14
0x180053db0  pop     rdi
0x180053db1  pop     rsi
0x180053db2  pop     rbp
0x180053db3  pop     rbx
0x180053db4  retn
```
