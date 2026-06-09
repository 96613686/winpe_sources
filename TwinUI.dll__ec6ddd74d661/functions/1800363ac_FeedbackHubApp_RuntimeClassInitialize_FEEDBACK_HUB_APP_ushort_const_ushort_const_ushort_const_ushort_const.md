# FeedbackHubApp::RuntimeClassInitialize(FEEDBACK_HUB_APP,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800363ac`
- end: `0x180036531`
- name: `?RuntimeClassInitialize@FeedbackHubApp@@QEAAJW4FEEDBACK_HUB_APP@@PEBG111@Z`
- size: `389`
- prototype: `int __high(enum FEEDBACK_HUB_APP, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180102b1c`
- `0x180102c44`

## callees

- `0x1800363ac`
- `0x1800378dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800363e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003646d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800364d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800363e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003646d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800364d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800363f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003643a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036484`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800364f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800363f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003643a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036484`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800364f0`

## pseudocode

```c
__int64 __fastcall FeedbackHubApp::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *sourceString,
        const WCHAR *a6)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  HSTRING *v8; // r14
  HRESULT String; // edi
  HSTRING *v13; // r14
  __int64 v14; // rdi
  HSTRING *v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rdx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = -1;
  *(_DWORD *)(a1 + 16) = a2;
  v7 = -1;
  v8 = (HSTRING *)(a1 + 24);
  do
    ++v7;
  while ( a3[v7] );
  WindowsDeleteString(*v8);
  *v8 = 0;
  String = WindowsCreateString(a3, v7, v8);
  if ( String < 0 )
  {
    v17 = 34;
    goto LABEL_11;
  }
  v13 = (HSTRING *)(a1 + 32);
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  WindowsDeleteString(*v13);
  *v13 = 0;
  String = WindowsCreateString(a4, v14, (HSTRING *)(a1 + 32));
  if ( String < 0 )
  {
    v17 = 35;
    goto LABEL_11;
  }
  v15 = (HSTRING *)(a1 + 40);
  v16 = -1;
  do
    ++v16;
  while ( sourceString[v16] );
  WindowsDeleteString(*v15);
  *v15 = 0;
  String = WindowsCreateString(sourceString, v16, (HSTRING *)(a1 + 40));
  if ( String < 0 )
  {
    v17 = 36;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shell\\twinui\\feedback\\lib\\FeedbackHubApp.h",
      (const char *)(unsigned int)String,
      v21);
    return (unsigned int)String;
  }
  do
    ++v6;
  while ( a6[v6] );
  WindowsDeleteString(*(HSTRING *)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  v19 = WindowsCreateString(a6, v6, (HSTRING *)(a1 + 48));
  v20 = v19;
  if ( v19 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"shell\\twinui\\feedback\\lib\\FeedbackHubApp.h",
    (const char *)(unsigned int)v19,
    v21);
  return v20;
}

```

## disassembly

```asm
0x1800363ac  push    rbx
0x1800363ae  push    rbp
0x1800363af  push    rsi
0x1800363b0  push    rdi
0x1800363b1  push    r12
0x1800363b3  push    r14
0x1800363b5  push    r15; int
0x1800363b7  sub     rsp, 20h
0x1800363bb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800363bf  mov     [rcx+10h], edx
0x1800363c2  mov     rdi, rbx
0x1800363c5  lea     r14, [rcx+18h]
0x1800363c9  xor     r12d, r12d
0x1800363cc  mov     r15, r9
0x1800363cf  mov     rbp, r8
0x1800363d2  mov     rsi, rcx
0x1800363d5  inc     rdi
0x1800363d8  cmp     [r8+rdi*2], r12w
0x1800363dd  jnz     short loc_1800363D5
0x1800363df  mov     rcx, [r14]; string
0x1800363e2  call    cs:__imp_WindowsDeleteString
0x1800363e9  nop     dword ptr [rax+rax+00h]
0x1800363ee  mov     r8, r14; string
0x1800363f1  mov     [r14], r12
0x1800363f4  mov     edx, edi; length
0x1800363f6  mov     rcx, rbp; sourceString
0x1800363f9  call    cs:__imp_WindowsCreateString
0x180036400  nop     dword ptr [rax+rax+00h]
0x180036405  mov     edi, eax
0x180036407  test    eax, eax
0x180036409  js      loc_180036506
0x18003640f  lea     r14, [rsi+20h]
0x180036413  mov     rdi, rbx
0x180036416  inc     rdi
0x180036419  cmp     [r15+rdi*2], r12w
0x18003641e  jnz     short loc_180036416
0x180036420  mov     rcx, [r14]; string
0x180036423  call    cs:__imp_WindowsDeleteString
0x18003642a  nop     dword ptr [rax+rax+00h]
0x18003642f  mov     r8, r14; string
0x180036432  mov     [r14], r12
0x180036435  mov     edx, edi; length
0x180036437  mov     rcx, r15; sourceString
0x18003643a  call    cs:__imp_WindowsCreateString
0x180036441  nop     dword ptr [rax+rax+00h]
0x180036446  mov     edi, eax
0x180036448  test    eax, eax
0x18003644a  js      loc_18003650D
0x180036450  mov     rbp, [rsp+58h+sourceString]
0x180036458  lea     r14, [rsi+28h]
0x18003645c  mov     rdi, rbx
0x18003645f  inc     rdi
0x180036462  cmp     [rbp+rdi*2+0], r12w
0x180036468  jnz     short loc_18003645F
0x18003646a  mov     rcx, [r14]; string
0x18003646d  call    cs:__imp_WindowsDeleteString
0x180036474  nop     dword ptr [rax+rax+00h]
0x180036479  mov     r8, r14; string
0x18003647c  mov     [r14], r12
0x18003647f  mov     edx, edi; length
0x180036481  mov     rcx, rbp; sourceString
0x180036484  call    cs:__imp_WindowsCreateString
0x18003648b  nop     dword ptr [rax+rax+00h]
0x180036490  mov     edi, eax
0x180036492  test    eax, eax
0x180036494  jns     short loc_1800364C1
0x180036496  mov     edx, 24h ; '$'; void *
0x18003649b  mov     rcx, [rsp+58h]; this
0x1800364a0  lea     r8, aShellTwinuiFee_3; "shell\\twinui\\feedback\\lib\\FeedbackH"...
0x1800364a7  mov     r9d, edi; char *
0x1800364aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364af  mov     eax, edi
0x1800364b1  add     rsp, 20h
0x1800364b5  pop     r15
0x1800364b7  pop     r14
0x1800364b9  pop     r12
0x1800364bb  pop     rdi
0x1800364bc  pop     rsi
0x1800364bd  pop     rbp
0x1800364be  pop     rbx
0x1800364bf  retn
0x1800364c1  mov     rdi, [rsp+58h+arg_28]
0x1800364c9  inc     rbx
0x1800364cc  cmp     [rdi+rbx*2], r12w
0x1800364d1  jnz     short loc_1800364C9
0x1800364d3  mov     rcx, [rsi+30h]; string
0x1800364d7  call    cs:__imp_WindowsDeleteString
0x1800364de  nop     dword ptr [rax+rax+00h]
0x1800364e3  lea     r8, [rsi+30h]; string
0x1800364e7  mov     [rsi+30h], r12
0x1800364eb  mov     edx, ebx; length
0x1800364ed  mov     rcx, rdi; sourceString
0x1800364f0  call    cs:__imp_WindowsCreateString
0x1800364f7  nop     dword ptr [rax+rax+00h]
0x1800364fc  mov     ebx, eax
0x1800364fe  test    eax, eax
0x180036500  js      short loc_180036514
0x180036502  xor     eax, eax
0x180036504  jmp     short loc_1800364B1
0x180036506  mov     edx, 22h ; '"'
0x18003650b  jmp     short loc_18003649B
0x18003650d  mov     edx, 23h ; '#'
0x180036512  jmp     short loc_18003649B
0x180036514  mov     rcx, [rsp+58h]; this
0x180036519  lea     r8, aShellTwinuiFee_3; "shell\\twinui\\feedback\\lib\\FeedbackH"...
0x180036520  mov     r9d, ebx; char *
0x180036523  mov     edx, 25h ; '%'; void *
0x180036528  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003652d  mov     eax, ebx
0x18003652f  jmp     short loc_1800364B1
```
