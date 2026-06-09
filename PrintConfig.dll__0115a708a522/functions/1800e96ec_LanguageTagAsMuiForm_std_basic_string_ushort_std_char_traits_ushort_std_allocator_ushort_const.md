# LanguageTagAsMuiForm(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800e96ec`
- end: `0x1800e9824`
- name: `?LanguageTagAsMuiForm@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z`
- size: `312`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e9194`

## callees

- `0x180003400`
- `0x18000de1c`
- `0x1800e96ec`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800e9770`
- `KERNEL32!RaiseException` at `0x1800e9770`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x1800e9786`
- `Bcp47Langs!Bcp47GetMuiForm` at `0x1800e9786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e97f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e97f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e9751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e9751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e979d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e979d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall LanguageTagAsMuiForm(_QWORD *a1, __int64 *a2)
{
  UINT32 v4; // edx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v6; // r8
  const OLECHAR *v7; // rdx
  HSTRING v9[3]; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-28h] BYREF

  v9[2] = (HSTRING)-2LL;
  WindowsDeleteString(0);
  v9[0] = 0;
  v4 = *((_DWORD *)a2 + 4);
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  if ( WindowsCreateStringReference((PCWSTR)a2, v4, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)Bcp47GetMuiForm(string, v9) < 0 )
  {
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v6 = 0;
    v7 = &Filename;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v9[0], 0);
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    v7 = StringRawBuffer;
  }
  std::wstring::_Construct<1,unsigned short const *>(a1, v7, v6);
  if ( v9[0] )
    WindowsDeleteString(v9[0]);
  return a1;
}

```

## disassembly

```asm
0x1800e96ec  mov     r11, rsp
0x1800e96ef  push    rdi
0x1800e96f0  sub     rsp, 60h
0x1800e96f4  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1800e96fc  mov     [r11+18h], rbx
0x1800e9700  mov     [r11+20h], rsi
0x1800e9704  mov     rax, cs:__security_cookie
0x1800e970b  xor     rax, rsp
0x1800e970e  mov     [rsp+68h+var_10], rax
0x1800e9713  mov     rdi, rdx
0x1800e9716  mov     rbx, rcx
0x1800e9719  mov     [rsp+68h+var_48], rcx
0x1800e971e  xor     esi, esi
0x1800e9720  mov     [r11-48h], rsi
0x1800e9724  xor     ecx, ecx; string
0x1800e9726  call    cs:__imp_WindowsDeleteString
0x1800e972d  nop     dword ptr [rax+rax+00h]
0x1800e9732  mov     [rsp+68h+var_48], rsi
0x1800e9737  mov     edx, [rdi+10h]; length
0x1800e973a  cmp     qword ptr [rdi+18h], 7
0x1800e973f  jbe     short loc_1800E9744
0x1800e9741  mov     rdi, [rdi]
0x1800e9744  lea     r9, [rsp+68h+string]; string
0x1800e9749  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x1800e974e  mov     rcx, rdi; sourceString
0x1800e9751  call    cs:__imp_WindowsCreateStringReference
0x1800e9758  nop     dword ptr [rax+rax+00h]
0x1800e975d  test    eax, eax
0x1800e975f  jns     short loc_1800E977C
0x1800e9761  xor     r9d, r9d; lpArguments
0x1800e9764  xor     r8d, r8d; nNumberOfArguments
0x1800e9767  lea     edx, [r9+1]; dwExceptionFlags
0x1800e976b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800e9770  call    cs:__imp_RaiseException
0x1800e9777  nop     dword ptr [rax+rax+00h]
0x1800e977c  lea     rdx, [rsp+68h+var_48]
0x1800e9781  mov     rcx, [rsp+68h+string]
0x1800e9786  call    cs:__imp_Bcp47GetMuiForm
0x1800e978d  nop     dword ptr [rax+rax+00h]
0x1800e9792  test    eax, eax
0x1800e9794  js      short loc_1800E97CA
0x1800e9796  xor     edx, edx; length
0x1800e9798  mov     rcx, [rsp+68h+var_48]; string
0x1800e979d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e97a4  nop     dword ptr [rax+rax+00h]
0x1800e97a9  xorps   xmm0, xmm0
0x1800e97ac  movups  xmmword ptr [rbx], xmm0
0x1800e97af  mov     [rbx+10h], rsi
0x1800e97b3  mov     [rbx+18h], rsi
0x1800e97b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800e97bb  inc     r8
0x1800e97be  cmp     [rax+r8*2], si
0x1800e97c3  jnz     short loc_1800E97BB
0x1800e97c5  mov     rdx, rax
0x1800e97c8  jmp     short loc_1800E97E2
0x1800e97ca  xorps   xmm0, xmm0
0x1800e97cd  movups  xmmword ptr [rbx], xmm0
0x1800e97d0  mov     [rbx+10h], rsi
0x1800e97d4  mov     [rbx+18h], rsi
0x1800e97d8  xor     r8d, r8d
0x1800e97db  lea     rdx, Filename
0x1800e97e2  mov     rcx, rbx
0x1800e97e5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800e97ea  nop
0x1800e97eb  mov     rcx, [rsp+68h+var_48]; string
0x1800e97f0  test    rcx, rcx
0x1800e97f3  jz      short loc_1800E9801
0x1800e97f5  call    cs:__imp_WindowsDeleteString
0x1800e97fc  nop     dword ptr [rax+rax+00h]
0x1800e9801  mov     rax, rbx
0x1800e9804  mov     rcx, [rsp+68h+var_10]
0x1800e9809  xor     rcx, rsp; StackCookie
0x1800e980c  call    __security_check_cookie
0x1800e9811  lea     r11, [rsp+68h+var_8]
0x1800e9816  mov     rbx, [r11+20h]
0x1800e981a  mov     rsi, [r11+28h]
0x1800e981e  mov     rsp, r11
0x1800e9821  pop     rdi
0x1800e9822  retn
```
