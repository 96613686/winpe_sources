# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180014884`
- end: `0x1800148f2`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `110`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HStringReference *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x180014884`
- `0x180014cdc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800148cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800148cd`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        Microsoft::WRL::Wrappers::HStringReference *this,
        const unsigned __int16 *a2,
        UINT32 a3,
        UINT32 a4)
{
  unsigned int v4; // r8d
  HRESULT StringReference; // [rsp+20h] [rbp-18h]
  UINT32 length; // [rsp+58h] [rbp+20h]

  length = a4;
  if ( a4 >= a3 )
    length = a3 - 1;
  StringReference = WindowsCreateStringReference(a2, length, (HSTRING_HEADER *)this, (HSTRING *)this + 3);
  if ( StringReference < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, 1, v4);
}

```

## disassembly

```asm
0x180014884  mov     [rsp+length], r9d
0x180014889  mov     [rsp+arg_10], r8d
0x18001488e  mov     [rsp+sourceString], rdx
0x180014893  mov     [rsp+hstringHeader], rcx
0x180014898  sub     rsp, 38h
0x18001489c  mov     eax, [rsp+38h+arg_10]
0x1800148a0  cmp     [rsp+38h+length], eax
0x1800148a4  jb      short loc_1800148B0
0x1800148a6  mov     eax, [rsp+38h+arg_10]
0x1800148aa  dec     eax
0x1800148ac  mov     [rsp+38h+length], eax
0x1800148b0  mov     rax, [rsp+38h+hstringHeader]
0x1800148b5  add     rax, 18h
0x1800148b9  mov     rcx, [rsp+38h+hstringHeader]
0x1800148be  mov     r9, rax; string
0x1800148c1  mov     r8, rcx; hstringHeader
0x1800148c4  mov     edx, [rsp+38h+length]; length
0x1800148c8  mov     rcx, [rsp+38h+sourceString]; sourceString
0x1800148cd  call    cs:__imp_WindowsCreateStringReference
0x1800148d3  mov     [rsp+38h+var_18], eax
0x1800148d7  cmp     [rsp+38h+var_18], 0
0x1800148dc  jge     short loc_1800148ED
0x1800148de  mov     edx, 1; int
0x1800148e3  mov     ecx, [rsp+38h+var_18]; this
0x1800148e7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800148ec  nop
0x1800148ed  add     rsp, 38h
0x1800148f1  retn
```
