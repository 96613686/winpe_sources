# DllCanUnloadNow

- ea: `0x180028190`
- end: `0x1800281dd`
- name: `DllCanUnloadNow`
- size: `77`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180025150`
- `0x180028190`
- `0x1804c5304`

## import_xrefs

- `mfc140u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x1800281a3`
- `mfc140u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x1800281a3`
- `mfc140u!__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ` at `0x1800281cf`
- `mfc140u!__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ` at `0x1800281cf`
- `mfc140u!?AfxDllCanUnloadNow@@YAJXZ` at `0x1800281a9`
- `mfc140u!?AfxDllCanUnloadNow@@YAJXZ` at `0x1800281a9`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct AFX_MODULE_STATE *v0; // rax
  HRESULT v1; // ebx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v0 = (struct AFX_MODULE_STATE *)sub_1804C5304();
  AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v3, v0);
  v1 = 0;
  if ( AfxDllCanUnloadNow() || (unsigned int)sub_180025150(&qword_1806FFB30) )
    v1 = 1;
  AFX_MAINTAIN_STATE2::~AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v3);
  return v1;
}

```

## disassembly

```asm
0x180028190  push    rbx
0x180028192  sub     rsp, 30h
0x180028196  call    sub_1804C5304
0x18002819b  mov     rdx, rax
0x18002819e  lea     rcx, [rsp+38h+var_18]
0x1800281a3  call    cs:__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z; AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(AFX_MODULE_STATE *)
0x1800281a9  call    cs:?AfxDllCanUnloadNow@@YAJXZ; AfxDllCanUnloadNow(void)
0x1800281af  xor     ebx, ebx
0x1800281b1  test    eax, eax
0x1800281b3  jnz     short loc_1800281C5
0x1800281b5  lea     rcx, qword_1806FFB30
0x1800281bc  call    sub_180025150
0x1800281c1  test    eax, eax
0x1800281c3  jz      short loc_1800281CA
0x1800281c5  mov     ebx, 1
0x1800281ca  lea     rcx, [rsp+38h+var_18]
0x1800281cf  call    cs:__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ; AFX_MAINTAIN_STATE2::~AFX_MAINTAIN_STATE2(void)
0x1800281d5  mov     eax, ebx
0x1800281d7  add     rsp, 30h
0x1800281db  pop     rbx
0x1800281dc  retn
```
