# CRemoteTextKeyTransitionedEventArgs::get_KeyText(HSTRING__ * *)

- ea: `0x180030620`
- end: `0x180030692`
- name: `?get_KeyText@CRemoteTextKeyTransitionedEventArgs@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CRemoteTextKeyTransitionedEventArgs *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180030620`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003067f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003067f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003065d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003065d`

## pseudocode

```c
__int64 __fastcall CRemoteTextKeyTransitionedEventArgs::get_KeyText(
        CRemoteTextKeyTransitionedEventArgs *this,
        HSTRING *a2)
{
  HSTRING v3; // rbx
  HRESULT v4; // ebx
  HSTRING v5; // rdx
  HSTRING v6; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HSTRING)*((_QWORD *)this + 54);
  newString = 0;
  WindowsDeleteString(0);
  newString = 0;
  v4 = WindowsDuplicateString(v3, &newString);
  if ( v4 < 0 )
  {
    v6 = newString;
  }
  else
  {
    v5 = newString;
    v6 = 0;
    newString = 0;
    *a2 = v5;
  }
  WindowsDeleteString(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030620  mov     [rsp+arg_8], rbx
0x180030625  push    rdi
0x180030626  sub     rsp, 20h
0x18003062a  mov     qword ptr [rdx], 0
0x180030631  mov     rdi, rdx
0x180030634  mov     rbx, [rcx+1B0h]
0x18003063b  xor     ecx, ecx; string
0x18003063d  mov     [rsp+28h+newString], 0
0x180030646  call    cs:__imp_WindowsDeleteString
0x18003064c  lea     rdx, [rsp+28h+newString]; newString
0x180030651  mov     [rsp+28h+newString], 0
0x18003065a  mov     rcx, rbx; string
0x18003065d  call    cs:__imp_WindowsDuplicateString
0x180030663  mov     ebx, eax
0x180030665  test    eax, eax
0x180030667  js      short loc_18003067A
0x180030669  mov     rdx, [rsp+28h+newString]
0x18003066e  xor     ecx, ecx
0x180030670  mov     [rsp+28h+newString], rcx
0x180030675  mov     [rdi], rdx
0x180030678  jmp     short loc_18003067F
0x18003067a  mov     rcx, [rsp+28h+newString]; string
0x18003067f  call    cs:__imp_WindowsDeleteString
0x180030685  mov     eax, ebx
0x180030687  mov     rbx, [rsp+28h+arg_8]
0x18003068c  add     rsp, 20h
0x180030690  pop     rdi
0x180030691  retn
```
