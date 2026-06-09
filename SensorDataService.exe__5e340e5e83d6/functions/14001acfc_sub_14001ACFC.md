# sub_14001ACFC

- ea: `0x14001acfc`
- end: `0x14001ae15`
- name: `sub_14001ACFC`
- size: `281`
- prototype: `int __fastcall(__int64 **, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14001abe0`

## callees

- `0x140001008`
- `0x14000127c`
- `0x140006f60`
- `0x140014c44`
- `0x14001acfc`
- `0x14004ef34`
- `0x1400ca010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001ad65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001ad65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001ad45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001ad45`

## string_xrefs

- `0x14001ad4e`: `Failed to remove FrameProvider %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall sub_14001ACFC(__int64 **a1, __int64 a2)
{
  __int64 v3; // rcx
  HSTRING *v4; // rax
  PCWSTR StringRawBuffer; // rax
  HSTRING v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-38h] BYREF

  v3 = **a1;
  v12 = v3;
  if ( v3 )
    sub_1400CA010(v3);
  v4 = (HSTRING *)sub_140014C44(&string, (int *)&v12);
  StringRawBuffer = WindowsGetStringRawBuffer(*v4, 0);
  v6 = (HSTRING)sub_14004EF34(a2, L"Failed to remove FrameProvider %s.", StringRawBuffer);
  WindowsDeleteString(string);
  if ( (unsigned int)dword_140111000 > 3 && (qword_140111010 & 0x10) != 0 && (qword_140111018 & 0x10) == qword_140111018 )
  {
    string = v6;
    sub_140001008(qword_140111010, (__int64)word_1400FF56A, v7, v8, (int **)&string);
  }
  LODWORD(v9) = dword_140111038;
  if ( (unsigned int)dword_140111038 > 3 )
  {
    LODWORD(v9) = qword_140111048;
    if ( (qword_140111048 & 0x10) != 0 )
    {
      v9 = qword_140111050 & 0x10;
      if ( v9 == qword_140111050 )
        LODWORD(v9) = sub_14000127C((__int64)&dword_140111038, (unsigned __int8 *)word_1400FF53A, 0, 0, 2u, &v13);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14001acfc  push    rbx
0x14001acfe  sub     rsp, 70h
0x14001ad02  mov     rax, cs:__security_cookie
0x14001ad09  xor     rax, rsp
0x14001ad0c  mov     [rsp+78h+var_18], rax
0x14001ad11  mov     rbx, rdx
0x14001ad14  mov     rax, [rcx]
0x14001ad17  mov     rcx, [rax]
0x14001ad1a  mov     [rsp+78h+var_40], rcx
0x14001ad1f  test    rcx, rcx
0x14001ad22  jz      short loc_14001AD31
0x14001ad24  mov     rax, [rcx]
0x14001ad27  mov     rax, [rax+8]
0x14001ad2b  call    sub_1400CA010
0x14001ad30  nop
0x14001ad31  lea     rdx, [rsp+78h+var_40]
0x14001ad36  lea     rcx, [rsp+78h+string]
0x14001ad3b  call    sub_140014C44
0x14001ad40  xor     edx, edx; length
0x14001ad42  mov     rcx, [rax]; string
0x14001ad45  call    cs:WindowsGetStringRawBuffer
0x14001ad4b  mov     r8, rax
0x14001ad4e  lea     rdx, aFailedToRemove_1; "Failed to remove FrameProvider %s."
0x14001ad55  mov     rcx, rbx
0x14001ad58  call    sub_14004EF34
0x14001ad5d  mov     rbx, rax
0x14001ad60  mov     rcx, [rsp+78h+string]; string
0x14001ad65  call    cs:WindowsDeleteString
0x14001ad6b  mov     ecx, cs:dword_140111000
0x14001ad71  cmp     ecx, 3
0x14001ad74  jbe     short loc_14001ADAF
0x14001ad76  mov     rdx, cs:qword_140111018
0x14001ad7d  mov     rcx, cs:qword_140111010
0x14001ad84  test    cl, 10h
0x14001ad87  jz      short loc_14001ADAF
0x14001ad89  mov     rax, rdx
0x14001ad8c  and     eax, 10h
0x14001ad8f  cmp     rax, rdx
0x14001ad92  jnz     short loc_14001ADAF
0x14001ad94  mov     [rsp+78h+string], rbx
0x14001ad99  lea     rax, [rsp+78h+string]
0x14001ad9e  mov     [rsp+78h+var_58], rax
0x14001ada3  lea     rdx, word_1400FF56A
0x14001adaa  call    sub_140001008
0x14001adaf  mov     eax, cs:dword_140111038
0x14001adb5  cmp     eax, 3
0x14001adb8  jbe     short loc_14001AE02
0x14001adba  mov     rcx, cs:qword_140111050
0x14001adc1  mov     rax, cs:qword_140111048
0x14001adc8  test    al, 10h
0x14001adca  jz      short loc_14001AE02
0x14001adcc  mov     rax, rcx
0x14001adcf  and     eax, 10h
0x14001add2  cmp     rax, rcx
0x14001add5  jnz     short loc_14001AE02
0x14001add7  lea     rax, [rsp+78h+var_38]
0x14001addc  mov     [rsp+78h+var_50], rax
0x14001ade1  mov     dword ptr [rsp+78h+var_58], 2
0x14001ade9  xor     r9d, r9d
0x14001adec  xor     r8d, r8d
0x14001adef  lea     rdx, word_1400FF53A
0x14001adf6  lea     rcx, dword_140111038
0x14001adfd  call    sub_14000127C
0x14001ae02  mov     rcx, [rsp+78h+var_18]
0x14001ae07  xor     rcx, rsp; StackCookie
0x14001ae0a  call    __security_check_cookie
0x14001ae0f  add     rsp, 70h
0x14001ae13  pop     rbx
0x14001ae14  retn
```
