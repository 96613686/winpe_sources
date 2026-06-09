# CallerContext::Serialize(void)

- ea: `0x180032fe0`
- end: `0x180033181`
- name: `?Serialize@CallerContext@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800652d8`

## callees

- `0x180024fe0`
- `0x18002ec2c`
- `0x180032fe0`
- `0x1801f7960`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003304a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003310d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003304a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003310d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003305d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180033024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003305d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003308a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003309a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003308a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003309a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003312f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18003312f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800330c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800330c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180033121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180033121`

## string_xrefs

- `0x180033145`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x18003315a`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x18003316f`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall CallerContext::Serialize(HSTRING *a1, HSTRING *a2, HSTRING a3)
{
  Microsoft::WRL::Wrappers::Details *v5; // rcx
  HRESULT v6; // eax
  HRESULT v7; // eax
  const wchar_t *StringRawBuffer; // rsi
  const wchar_t *v9; // rdi
  HRESULT v10; // eax
  WCHAR *charBuffer; // [rsp+20h] [rbp-18h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  UINT32 v15; // [rsp+60h] [rbp+28h] BYREF
  HSTRING *v16; // [rsp+68h] [rbp+30h]
  UINT32 length; // [rsp+70h] [rbp+38h] BYREF
  int v18; // [rsp+78h] [rbp+40h]

  v16 = a2;
  *a2 = 0;
  v18 = 1;
  v5 = (Microsoft::WRL::Wrappers::Details *)a1[9];
  if ( v5 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(v5, *a1, a3) )
    {
      length = 0;
      v15 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(a1[9], &length);
      v9 = WindowsGetStringRawBuffer(*a1, &v15);
      charBuffer = 0;
      bufferHandle = 0;
      v10 = WindowsPreallocateStringBuffer(length + 2 + v15, &charBuffer, &bufferHandle);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
          (const char *)(unsigned int)v10,
          (int)charBuffer);
      wcsncpy_0(charBuffer, v9, v15);
      charBuffer[v15] = 44;
      wcsncpy_0(&charBuffer[v15 + 1], StringRawBuffer, length);
      WindowsDeleteString(*a2);
      *a2 = 0;
      if ( WindowsPromoteStringBuffer(bufferHandle, a2) < 0 )
        WindowsDeleteStringBuffer(bufferHandle);
    }
    else
    {
      WindowsDeleteString(*a2);
      *a2 = 0;
      v7 = WindowsDuplicateString(*a1, a2);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
          (const char *)(unsigned int)v7,
          (int)charBuffer);
    }
  }
  else
  {
    WindowsDeleteString(0);
    *a2 = 0;
    v6 = WindowsDuplicateString(*a1, a2);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
        (const char *)(unsigned int)v6,
        (int)charBuffer);
  }
  return a2;
}

```

## disassembly

```asm
0x180032fe0  mov     [rsp-20h+arg_8], rdx
0x180032fe5  push    rbp
0x180032fe6  push    rbx
0x180032fe7  push    rsi
0x180032fe8  push    rdi
0x180032fe9  mov     rbp, rsp
0x180032fec  sub     rsp, 38h
0x180032ff0  mov     rbx, rdx
0x180032ff3  mov     rdi, rcx
0x180032ff6  mov     eax, 1
0x180032ffb  mov     [rbp+arg_18], eax
0x180032ffe  mov     qword ptr [rdx], 0
0x180033005  mov     [rbp+arg_18], eax
0x180033008  mov     rcx, [rcx+48h]; this
0x18003300c  test    rcx, rcx
0x18003300f  jnz     short loc_18003303B
0x180033011  call    cs:__imp_WindowsDeleteString
0x180033017  mov     qword ptr [rbx], 0
0x18003301e  mov     rdx, rbx; newString
0x180033021  mov     rcx, [rdi]; string
0x180033024  call    cs:__imp_WindowsDuplicateString
0x18003302a  mov     rcx, [rbp+20h]; this
0x18003302e  test    eax, eax
0x180033030  js      loc_180033157
0x180033036  jmp     loc_180033136
0x18003303b  mov     rdx, [rdi]; HSTRING
0x18003303e  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180033043  test    eax, eax
0x180033045  jnz     short loc_180033074
0x180033047  mov     rcx, [rbx]; string
0x18003304a  call    cs:__imp_WindowsDeleteString
0x180033050  mov     qword ptr [rbx], 0
0x180033057  mov     rdx, rbx; newString
0x18003305a  mov     rcx, [rdi]; string
0x18003305d  call    cs:__imp_WindowsDuplicateString
0x180033063  mov     rcx, [rbp+20h]; this
0x180033067  test    eax, eax
0x180033069  js      loc_18003316C
0x18003306f  jmp     loc_180033136
0x180033074  mov     [rbp+length], 0
0x18003307b  mov     [rbp+arg_0], 0
0x180033082  lea     rdx, [rbp+length]; length
0x180033086  mov     rcx, [rdi+48h]; string
0x18003308a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033090  mov     rsi, rax
0x180033093  lea     rdx, [rbp+arg_0]; length
0x180033097  mov     rcx, [rdi]; string
0x18003309a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800330a0  mov     rdi, rax
0x1800330a3  mov     [rbp+charBuffer], 0
0x1800330ab  mov     [rbp+bufferHandle], 0
0x1800330b3  mov     edx, [rbp+length]
0x1800330b6  mov     ecx, [rbp+arg_0]
0x1800330b9  add     edx, 2
0x1800330bc  add     ecx, edx; length
0x1800330be  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800330c2  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800330c6  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800330cc  mov     rcx, [rbp+20h]; this
0x1800330d0  test    eax, eax
0x1800330d2  js      short loc_180033142
0x1800330d4  mov     r8d, [rbp+arg_0]; Count
0x1800330d8  mov     rdx, rdi; Source
0x1800330db  mov     rcx, [rbp+charBuffer]; Destination
0x1800330df  call    wcsncpy_0
0x1800330e4  mov     ecx, [rbp+arg_0]
0x1800330e7  mov     rax, [rbp+charBuffer]
0x1800330eb  mov     word ptr [rax+rcx*2], 2Ch ; ','
0x1800330f1  mov     ecx, [rbp+arg_0]
0x1800330f4  inc     ecx
0x1800330f6  mov     rax, [rbp+charBuffer]
0x1800330fa  lea     rcx, [rax+rcx*2]; Destination
0x1800330fe  mov     r8d, [rbp+length]; Count
0x180033102  mov     rdx, rsi; Source
0x180033105  call    wcsncpy_0
0x18003310a  mov     rcx, [rbx]; string
0x18003310d  call    cs:__imp_WindowsDeleteString
0x180033113  mov     qword ptr [rbx], 0
0x18003311a  mov     rdx, rbx; string
0x18003311d  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180033121  call    cs:__imp_WindowsPromoteStringBuffer
0x180033127  test    eax, eax
0x180033129  jns     short loc_180033136
0x18003312b  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18003312f  call    cs:__imp_WindowsDeleteStringBuffer
0x180033135  nop
0x180033136  mov     rax, rbx
0x180033139  add     rsp, 38h
0x18003313d  pop     rdi
0x18003313e  pop     rsi
0x18003313f  pop     rbx
0x180033140  pop     rbp
0x180033141  retn
0x180033142  mov     r9d, eax; char *
0x180033145  lea     r8, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x18003314c  mov     edx, 91h; void *
0x180033151  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033157  mov     r9d, eax; char *
0x18003315a  lea     r8, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x180033161  mov     edx, 7Eh ; '~'; void *
0x180033166  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003316c  mov     r9d, eax; char *
0x18003316f  lea     r8, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x180033176  mov     edx, 87h; void *
0x18003317b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
