# SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)

- ea: `0x180011e98`
- end: `0x180011f0b`
- name: `?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct ISupportErrorInfo **)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003860`
- `0x1800054c0`
- `0x1800063d0`
- `0x180007030`
- `0x180008430`
- `0x1800084e0`
- `0x1800085b0`
- `0x180009520`
- `0x18000e8e0`
- `0x18000e990`
- `0x18000fb00`
- `0x180011f50`
- `0x180012000`

## callees

- `0x180001194`
- `0x180002310`
- `0x180011cd0`
- `0x180011e98`

## pseudocode

```c
__int64 __fastcall SupportErrorInfoImpl::CreateInstance(struct ISupportErrorInfo **a1)
{
  struct ISupportErrorInfo *v2; // rax
  struct ISupportErrorInfo *v3; // rbx
  unsigned int v4; // ebx
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (struct ISupportErrorInfo *)operator new(0x10u);
  v3 = v2;
  if ( v2 )
  {
    v2[1].lpVtbl = 0;
    v2->lpVtbl = (struct ISupportErrorInfoVtbl *)&SimpleIUnknownImpl<ISupportErrorInfo>::`vftable';
    LODWORD(v2[1].lpVtbl) = 1;
    ModuleRefCounter::AddRef();
    v3->lpVtbl = (struct ISupportErrorInfoVtbl *)&SupportErrorInfoImpl::`vftable';
    *a1 = v3;
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
  v6 = 0;
  ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180011e98  mov     [rsp+arg_0], rbx
0x180011e9d  push    rdi
0x180011e9e  sub     rsp, 20h
0x180011ea2  mov     rdi, rcx
0x180011ea5  mov     ecx, 10h; Size
0x180011eaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011eaf  mov     rbx, rax
0x180011eb2  test    rax, rax
0x180011eb5  jz      short loc_180011EE6
0x180011eb7  mov     qword ptr [rax+8], 0
0x180011ebf  lea     rax, ??_7?$SimpleIUnknownImpl@UISupportErrorInfo@@@@6B@; const SimpleIUnknownImpl<ISupportErrorInfo>::`vftable'
0x180011ec6  mov     [rbx], rax
0x180011ec9  mov     dword ptr [rbx+8], 1
0x180011ed0  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180011ed5  lea     rax, ??_7SupportErrorInfoImpl@@6B@; const SupportErrorInfoImpl::`vftable'
0x180011edc  mov     [rbx], rax
0x180011edf  mov     [rdi], rbx
0x180011ee2  xor     ebx, ebx
0x180011ee4  jmp     short loc_180011EEB
0x180011ee6  mov     ebx, 8007000Eh
0x180011eeb  lea     rcx, [rsp+28h+arg_8]
0x180011ef0  mov     [rsp+28h+arg_8], 0
0x180011ef9  call    ??1?$CComPtrBase@UISupportErrorInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(void)
0x180011efe  mov     eax, ebx
0x180011f00  mov     rbx, [rsp+28h+arg_0]
0x180011f05  add     rsp, 20h
0x180011f09  pop     rdi
0x180011f0a  retn
```
