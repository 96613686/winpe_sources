# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180004660`
- end: `0x180004690`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(void **)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f007`
- `0x18000f019`
- `0x18000f02b`
- `0x18000f03d`
- `0x18000f04f`
- `0x18000f061`
- `0x18000f073`
- `0x18000f0cf`
- `0x18000f36d`
- `0x18000f37f`
- `0x18000f391`
- `0x18000f3a3`
- `0x18000f3b5`
- `0x18000f3c7`
- `0x18000f3d9`

## callees

- `0x180004660`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004673`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004673`

## pseudocode

```c
void __fastcall std::wstring::~wstring(void **a1)
{
  if ( (unsigned __int64)a1[3] >= 8 )
    operator delete(*a1);
  a1[3] = (void *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x180004660  push    rbx
0x180004662  sub     rsp, 20h
0x180004666  cmp     qword ptr [rcx+18h], 8
0x18000466b  mov     rbx, rcx
0x18000466e  jb      short loc_180004679
0x180004670  mov     rcx, [rcx]
0x180004673  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004679  xor     eax, eax
0x18000467b  mov     qword ptr [rbx+18h], 7
0x180004683  mov     [rbx+10h], rax
0x180004687  mov     [rbx], ax
0x18000468a  add     rsp, 20h
0x18000468e  pop     rbx
0x18000468f  retn
```
