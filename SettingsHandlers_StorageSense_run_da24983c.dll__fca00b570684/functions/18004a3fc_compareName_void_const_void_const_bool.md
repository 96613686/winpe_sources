# compareName(void const *,void const *,bool)

- ea: `0x18004a3fc`
- end: `0x18004a521`
- name: `?compareName@@YAHPEBX0_N@Z`
- size: `293`
- prototype: `__int64 __fastcall(const void *, const void *, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004a310`
- `0x18004a530`
- `0x18004a540`
- `0x18004a550`

## callees

- `0x18004a3fc`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a45f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a45f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004a489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004a489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a4dc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004a4e8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004a4e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall compareName(__int64 *a1, __int64 *a2, char a3)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  int (__fastcall *v6)(__int64, HSTRING *); // rbx
  int (__fastcall *v7)(__int64, HSTRING *); // rbx
  unsigned int v8; // ebx
  BOOL IsStringEmpty; // ebx
  BOOL v10; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING v12; // rcx
  const WCHAR *v13; // rbx
  const WCHAR *v14; // rax
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  HSTRING v17; // [rsp+48h] [rbp+28h] BYREF

  v4 = *a1;
  v5 = *a2;
  v17 = 0;
  string = 0;
  v6 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v4 + 88LL);
  WindowsDeleteString(0);
  v17 = 0;
  if ( v6(v4, &v17) < 0 )
    goto LABEL_7;
  v7 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v5 + 88LL);
  WindowsDeleteString(string);
  string = 0;
  if ( v7(v5, &string) < 0 )
  {
LABEL_3:
    v8 = -1;
    goto LABEL_13;
  }
  IsStringEmpty = WindowsIsStringEmpty(v17);
  v10 = WindowsIsStringEmpty(string);
  if ( IsStringEmpty )
  {
    if ( v10 )
    {
      v8 = 0;
      goto LABEL_13;
    }
LABEL_7:
    v8 = 1;
    goto LABEL_13;
  }
  if ( v10 )
    goto LABEL_3;
  if ( a3 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = v17;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
    v12 = string;
  }
  v13 = StringRawBuffer;
  v14 = WindowsGetStringRawBuffer(v12, 0);
  v8 = StrCmpIW(v14, v13);
LABEL_13:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v17);
  return v8;
}

```

## disassembly

```asm
0x18004a3fc  mov     [rsp-18h+arg_10], rbx
0x18004a401  mov     [rsp-18h+arg_18], rsi
0x18004a406  push    rbp
0x18004a407  push    rdi
0x18004a408  push    r14
0x18004a40a  mov     rbp, rsp
0x18004a40d  sub     rsp, 20h
0x18004a411  mov     r14b, r8b
0x18004a414  mov     rdi, [rcx]
0x18004a417  mov     rsi, [rdx]
0x18004a41a  mov     [rbp+arg_8], 0
0x18004a422  mov     [rbp+string], 0
0x18004a42a  mov     rax, [rdi]
0x18004a42d  mov     rbx, [rax+58h]
0x18004a431  xor     ecx, ecx; string
0x18004a433  call    cs:__imp_WindowsDeleteString
0x18004a439  mov     [rbp+arg_8], 0
0x18004a441  lea     rdx, [rbp+arg_8]
0x18004a445  mov     rcx, rdi
0x18004a448  mov     rax, rbx
0x18004a44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a450  test    eax, eax
0x18004a452  js      short loc_18004A4A7
0x18004a454  mov     rax, [rsi]
0x18004a457  mov     rbx, [rax+58h]
0x18004a45b  mov     rcx, [rbp+string]; string
0x18004a45f  call    cs:__imp_WindowsDeleteString
0x18004a465  mov     [rbp+string], 0
0x18004a46d  lea     rdx, [rbp+string]
0x18004a471  mov     rcx, rsi
0x18004a474  mov     rax, rbx
0x18004a477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a47c  test    eax, eax
0x18004a47e  jns     short loc_18004A485
0x18004a480  or      ebx, 0FFFFFFFFh
0x18004a483  jmp     short loc_18004A4F0
0x18004a485  mov     rcx, [rbp+arg_8]; string
0x18004a489  call    cs:__imp_WindowsIsStringEmpty
0x18004a48f  mov     ebx, eax
0x18004a491  mov     rcx, [rbp+string]; string
0x18004a495  call    cs:__imp_WindowsIsStringEmpty
0x18004a49b  test    ebx, ebx
0x18004a49d  jz      short loc_18004A4AE
0x18004a49f  test    eax, eax
0x18004a4a1  jz      short loc_18004A4A7
0x18004a4a3  xor     ebx, ebx
0x18004a4a5  jmp     short loc_18004A4F0
0x18004a4a7  mov     ebx, 1
0x18004a4ac  jmp     short loc_18004A4F0
0x18004a4ae  test    eax, eax
0x18004a4b0  jnz     short loc_18004A480
0x18004a4b2  xor     edx, edx; length
0x18004a4b4  test    r14b, r14b
0x18004a4b7  jz      short loc_18004A4C9
0x18004a4b9  mov     rcx, [rbp+string]; string
0x18004a4bd  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a4c3  mov     rcx, [rbp+arg_8]
0x18004a4c7  jmp     short loc_18004A4D7
0x18004a4c9  mov     rcx, [rbp+arg_8]; string
0x18004a4cd  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a4d3  mov     rcx, [rbp+string]; string
0x18004a4d7  mov     rbx, rax
0x18004a4da  xor     edx, edx; length
0x18004a4dc  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a4e2  mov     rdx, rbx; psz2
0x18004a4e5  mov     rcx, rax; psz1
0x18004a4e8  call    cs:__imp_StrCmpIW
0x18004a4ee  mov     ebx, eax
0x18004a4f0  mov     rcx, [rbp+string]; string
0x18004a4f4  call    cs:__imp_WindowsDeleteString
0x18004a4fa  mov     [rbp+string], 0
0x18004a502  mov     rcx, [rbp+arg_8]; string
0x18004a506  call    cs:__imp_WindowsDeleteString
0x18004a50c  mov     eax, ebx
0x18004a50e  mov     rbx, [rsp+20h+arg_10]
0x18004a513  mov     rsi, [rsp+20h+arg_18]
0x18004a518  add     rsp, 20h
0x18004a51c  pop     r14
0x18004a51e  pop     rdi
0x18004a51f  pop     rbp
0x18004a520  retn
```
