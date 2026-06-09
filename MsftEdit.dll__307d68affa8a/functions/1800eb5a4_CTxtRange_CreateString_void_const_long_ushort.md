# CTxtRange::CreateString(void const *,long,ushort * *)

- ea: `0x1800eb5a4`
- end: `0x1800eb600`
- name: `?CreateString@CTxtRange@@QEAAJPEBXJPEAPEAG@Z`
- size: `92`
- prototype: `int(CTxtRange *__hidden this, const void *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800311c0`

## callees

- `0x1800eb5a4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800eb5c4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800eb5c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800eb5e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800eb5e9`

## pseudocode

```c
HRESULT __fastcall CTxtRange::CreateString(CTxtRange *this, const WCHAR *a2, signed int a3, unsigned __int16 **a4)
{
  HRESULT result; // eax
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return -2147024809;
  if ( (*((_DWORD *)this + 29) & 0x100000) != 0 )
  {
    string = 0;
    result = WindowsCreateString(a2, (unsigned __int64)a3 >> 1, &string);
    *a4 = (unsigned __int16 *)string;
  }
  else
  {
    *a4 = SysAllocStringByteLen((LPCSTR)a2, a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800eb5a4  push    rbx
0x1800eb5a6  sub     rsp, 20h
0x1800eb5aa  mov     rbx, r9
0x1800eb5ad  mov     rax, rdx
0x1800eb5b0  test    r9, r9
0x1800eb5b3  jz      short loc_1800EB5F9
0x1800eb5b5  test    dword ptr [rcx+74h], 100000h
0x1800eb5bc  mov     rcx, rdx; sourceString
0x1800eb5bf  jnz     short loc_1800EB5D5
0x1800eb5c1  mov     edx, r8d; len
0x1800eb5c4  call    cs:__imp_SysAllocStringByteLen
0x1800eb5ca  mov     [rbx], rax
0x1800eb5cd  xor     eax, eax
0x1800eb5cf  add     rsp, 20h
0x1800eb5d3  pop     rbx
0x1800eb5d4  retn
0x1800eb5d5  movsxd  rdx, r8d
0x1800eb5d8  lea     r8, [rsp+28h+string]; string
0x1800eb5dd  shr     rdx, 1; length
0x1800eb5e0  mov     [rsp+28h+string], 0
0x1800eb5e9  call    cs:__imp_WindowsCreateString
0x1800eb5ef  mov     rcx, [rsp+28h+string]
0x1800eb5f4  mov     [rbx], rcx
0x1800eb5f7  jmp     short loc_1800EB5CF
0x1800eb5f9  mov     eax, 80070057h
0x1800eb5fe  jmp     short loc_1800EB5CF
```
