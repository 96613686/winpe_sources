# CComAuthInfo2::~CComAuthInfo2(void)

- ea: `0x180012cf8`
- end: `0x180012d24`
- name: `??1CComAuthInfo2@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CComAuthInfo2 *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013430`
- `0x18001a578`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180012d05`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d05`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d1d`

## pseudocode

```c
void __fastcall CComAuthInfo2::~CComAuthInfo2(BSTR *this)
{
  SysFreeString(this[2]);
  SysFreeString(this[1]);
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180012cf8  push    rbx
0x180012cfa  sub     rsp, 20h
0x180012cfe  mov     rbx, rcx
0x180012d01  mov     rcx, [rcx+10h]; bstrString
0x180012d05  call    cs:__imp_SysFreeString
0x180012d0b  mov     rcx, [rbx+8]; bstrString
0x180012d0f  call    cs:__imp_SysFreeString
0x180012d15  mov     rcx, [rbx]
0x180012d18  add     rsp, 20h
0x180012d1c  pop     rbx
0x180012d1d  jmp     cs:__imp_SysFreeString
```
