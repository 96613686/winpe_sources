# CDfsShellExtProp::~CDfsShellExtProp(void)

- ea: `0x1800082c8`
- end: `0x180008380`
- name: `??1CDfsShellExtProp@@UEAA@XZ`
- size: `184`
- prototype: `void __fastcall(CDfsShellExtProp *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b10`
- `0x1800083f0`

## callees

- `0x1800082c8`
- `0x18000a7b4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800082e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008309`
- `OLEAUT32!__imp_SysFreeString` at `0x180008316`
- `OLEAUT32!__imp_SysFreeString` at `0x180008323`
- `OLEAUT32!__imp_SysFreeString` at `0x180008330`
- `OLEAUT32!__imp_SysFreeString` at `0x18000833d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000834a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008357`
- `OLEAUT32!__imp_SysFreeString` at `0x180008364`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008309`
- `OLEAUT32!__imp_SysFreeString` at `0x180008316`
- `OLEAUT32!__imp_SysFreeString` at `0x180008323`
- `OLEAUT32!__imp_SysFreeString` at `0x180008330`
- `OLEAUT32!__imp_SysFreeString` at `0x18000833d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000834a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008357`
- `OLEAUT32!__imp_SysFreeString` at `0x180008364`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDfsShellExtProp::~CDfsShellExtProp(BSTR *this)
{
  AtlThunkData_t *v2; // rcx

  *this = (BSTR)&CDfsShellExtProp::`vftable';
  SysFreeString(this[33]);
  SysFreeString(this[32]);
  SysFreeString(this[31]);
  SysFreeString(this[30]);
  SysFreeString(this[29]);
  SysFreeString(this[28]);
  SysFreeString(this[27]);
  SysFreeString(this[25]);
  SysFreeString(this[24]);
  SysFreeString(this[23]);
  SysFreeString(this[22]);
  v2 = (AtlThunkData_t *)this[5];
  if ( v2 )
    AtlThunk_FreeData(v2);
}

```

## disassembly

```asm
0x1800082c8  push    rbx
0x1800082ca  sub     rsp, 20h
0x1800082ce  mov     rbx, rcx
0x1800082d1  lea     rax, ??_7CDfsShellExtProp@@6B@; const CDfsShellExtProp::`vftable'
0x1800082d8  mov     [rcx], rax
0x1800082db  mov     rcx, [rcx+108h]; bstrString
0x1800082e2  call    cs:__imp_SysFreeString
0x1800082e8  mov     rcx, [rbx+100h]; bstrString
0x1800082ef  call    cs:__imp_SysFreeString
0x1800082f5  mov     rcx, [rbx+0F8h]; bstrString
0x1800082fc  call    cs:__imp_SysFreeString
0x180008302  mov     rcx, [rbx+0F0h]; bstrString
0x180008309  call    cs:__imp_SysFreeString
0x18000830f  mov     rcx, [rbx+0E8h]; bstrString
0x180008316  call    cs:__imp_SysFreeString
0x18000831c  mov     rcx, [rbx+0E0h]; bstrString
0x180008323  call    cs:__imp_SysFreeString
0x180008329  mov     rcx, [rbx+0D8h]; bstrString
0x180008330  call    cs:__imp_SysFreeString
0x180008336  mov     rcx, [rbx+0C8h]; bstrString
0x18000833d  call    cs:__imp_SysFreeString
0x180008343  mov     rcx, [rbx+0C0h]; bstrString
0x18000834a  call    cs:__imp_SysFreeString
0x180008350  mov     rcx, [rbx+0B8h]; bstrString
0x180008357  call    cs:__imp_SysFreeString
0x18000835d  mov     rcx, [rbx+0B0h]; bstrString
0x180008364  call    cs:__imp_SysFreeString
0x18000836a  nop
0x18000836b  mov     rcx, [rbx+28h]; Thunk
0x18000836f  test    rcx, rcx
0x180008372  jz      short loc_18000837A
0x180008374  call    AtlThunk_FreeData
0x180008379  nop
0x18000837a  add     rsp, 20h
0x18000837e  pop     rbx
0x18000837f  retn
```
