# GetMccMncFromProviderId(HSTRING__ * *,ulong &,ulong &)

- ea: `0x180101550`
- end: `0x180101632`
- name: `?GetMccMncFromProviderId@@YAXPEAPEAUHSTRING__@@AEAK1@Z`
- size: `226`
- prototype: `void __fastcall(HSTRING *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18010251c`
- `0x180102780`
- `0x180102a80`
- `0x180102d94`
- `0x180103044`

## callees

- `0x1800a98c0`
- `0x180101550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801015dd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801015f5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801015dd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801015f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801015d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801015ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801015d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801015ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18010157d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18010157d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801015ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801015ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstring` at `0x1801015c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstring` at `0x1801015c3`

## pseudocode

```c
void __fastcall GetMccMncFromProviderId(HSTRING *a1, unsigned int *a2, unsigned int *a3)
{
  HSTRING v6; // rcx
  PCWSTR StringRawBuffer; // rax
  unsigned int v8; // eax
  HSTRING v9; // rcx
  PCWSTR v10; // rax
  HSTRING newString; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0x7FFFFFFF;
  *a3 = 0x7FFFFFFF;
  if ( WindowsGetStringLen(*a1) > 4 )
  {
    v6 = *a1;
    newString = 0;
    string = 0;
    if ( WindowsSubstringWithSpecifiedLength(v6, 0, 3u, &newString) >= 0 && WindowsSubstring(*a1, 3u, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
      v8 = _o__wtoi(StringRawBuffer);
      v9 = string;
      *a2 = v8;
      v10 = WindowsGetStringRawBuffer(v9, 0);
      *a3 = _o__wtoi(v10);
    }
    if ( newString )
      WindowsDeleteString(newString);
    if ( string )
      WindowsDeleteString(string);
  }
}

```

## disassembly

```asm
0x180101550  push    rbx
0x180101552  push    rsi
0x180101553  push    rdi
0x180101554  sub     rsp, 40h
0x180101558  mov     rax, cs:__security_cookie
0x18010155f  xor     rax, rsp
0x180101562  mov     [rsp+58h+var_28], rax
0x180101567  mov     eax, 7FFFFFFFh
0x18010156c  mov     rbx, rcx
0x18010156f  mov     [rdx], eax
0x180101571  mov     rsi, r8
0x180101574  mov     [r8], eax
0x180101577  mov     rdi, rdx
0x18010157a  mov     rcx, [rcx]; string
0x18010157d  call    cs:__imp_WindowsGetStringLen
0x180101583  cmp     eax, 4
0x180101586  jbe     loc_18010161D
0x18010158c  mov     rcx, [rbx]; string
0x18010158f  lea     r9, [rsp+58h+newString]; newString
0x180101594  xor     edx, edx; startIndex
0x180101596  mov     [rsp+58h+newString], 0
0x18010159f  mov     [rsp+58h+string], 0
0x1801015a8  lea     r8d, [rdx+3]; length
0x1801015ac  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1801015b2  test    eax, eax
0x1801015b4  js      short loc_1801015FD
0x1801015b6  mov     rcx, [rbx]; string
0x1801015b9  lea     r8, [rsp+58h+string]; newString
0x1801015be  mov     edx, 3; startIndex
0x1801015c3  call    cs:__imp_WindowsSubstring
0x1801015c9  test    eax, eax
0x1801015cb  js      short loc_1801015FD
0x1801015cd  mov     rcx, [rsp+58h+newString]; string
0x1801015d2  xor     edx, edx; length
0x1801015d4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801015da  mov     rcx, rax
0x1801015dd  call    cs:__imp__o__wtoi
0x1801015e3  mov     rcx, [rsp+58h+string]; string
0x1801015e8  xor     edx, edx; length
0x1801015ea  mov     [rdi], eax
0x1801015ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1801015f2  mov     rcx, rax
0x1801015f5  call    cs:__imp__o__wtoi
0x1801015fb  mov     [rsi], eax
0x1801015fd  mov     rcx, [rsp+58h+newString]; string
0x180101602  test    rcx, rcx
0x180101605  jz      short loc_18010160D
0x180101607  call    cs:__imp_WindowsDeleteString
0x18010160d  mov     rcx, [rsp+58h+string]; string
0x180101612  test    rcx, rcx
0x180101615  jz      short loc_18010161D
0x180101617  call    cs:__imp_WindowsDeleteString
0x18010161d  mov     rcx, [rsp+58h+var_28]
0x180101622  xor     rcx, rsp; StackCookie
0x180101625  call    __security_check_cookie
0x18010162a  add     rsp, 40h
0x18010162e  pop     rdi
0x18010162f  pop     rsi
0x180101630  pop     rbx
0x180101631  retn
```
