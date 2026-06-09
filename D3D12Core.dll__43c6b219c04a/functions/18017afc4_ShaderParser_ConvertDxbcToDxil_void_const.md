# ShaderParser::ConvertDxbcToDxil(void const *)

- ea: `0x18017afc4`
- end: `0x18017b0b4`
- name: `?ConvertDxbcToDxil@ShaderParser@@IEAAIPEBX@Z`
- size: `240`
- prototype: `unsigned int __fastcall(ShaderParser *__hidden this, const void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009ac44`

## callees

- `0x180003c84`
- `0x18000b010`
- `0x18001a900`
- `0x1800aa378`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017b08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017b08c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShaderParser::ConvertDxbcToDxil(LPVOID *this, char *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  _QWORD *v6; // rdi
  __int64 v7; // rbx
  int HashType; // eax
  const wchar_t *v9; // r9
  int v10; // eax
  void *v11; // rbx
  int v13; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+10h] BYREF
  void *v15; // [rsp+80h] [rbp+18h] BYREF

  v14 = 0;
  v4 = ((__int64 (__fastcall *)(GUID *, GUID *, _QWORD **))pfnDxcCreateInstance)(
         &CLSID_DxbcConverter,
         &GUID_5f956ed5_78d1_4b15_8247_f7187614a041,
         &v14);
  ThrowFailure(v4);
  v5 = sqlite3_str_length((__int64)a2);
  v15 = 0;
  v13 = 0;
  v6 = v14;
  v7 = *v14;
  HashType = CDXBCParser::GetHashType(a2 + 4);
  v9 = 0;
  if ( HashType == 3 )
    v9 = L"-disableHashCheck";
  v10 = (*(__int64 (__fastcall **)(_QWORD *, char *, _QWORD, const wchar_t *, void **, int *, _QWORD))(v7 + 24))(
          v6,
          a2,
          v5,
          v9,
          &v15,
          &v13,
          0);
  ThrowFailure(v10);
  v11 = v15;
  CoTaskMemFree(this[39]);
  this[39] = v11;
  LODWORD(v11) = v13;
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18017afc4  push    rbx
0x18017afc6  push    rbp
0x18017afc7  push    rsi
0x18017afc8  push    rdi
0x18017afc9  push    r14
0x18017afcb  sub     rsp, 40h
0x18017afcf  mov     rbp, rdx
0x18017afd2  mov     r14, rcx
0x18017afd5  mov     [rsp+68h+arg_8], 0
0x18017afde  lea     r8, [rsp+68h+arg_8]
0x18017afe3  lea     rdx, _GUID_5f956ed5_78d1_4b15_8247_f7187614a041
0x18017afea  lea     rcx, ?CLSID_DxbcConverter@@3U_GUID@@B; _GUID const CLSID_DxbcConverter
0x18017aff1  mov     rax, cs:?pfnDxcCreateInstance@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*pfnDxcCreateInstance)(_GUID const &,_GUID const &,void * *)
0x18017aff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017affd  mov     ecx, eax; int
0x18017afff  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18017b004  mov     rcx, rbp
0x18017b007  call    sqlite3_str_length
0x18017b00c  mov     esi, eax
0x18017b00e  mov     [rsp+68h+arg_10], 0
0x18017b01a  mov     [rsp+68h+arg_0], 0
0x18017b022  mov     rdi, [rsp+68h+arg_8]
0x18017b027  mov     rbx, [rdi]
0x18017b02a  lea     rcx, [rbp+4]
0x18017b02e  call    ?GetHashType@CDXBCParser@@SA?AW4DXBCParserHashType@@AEBUDXBCHash@@@Z; CDXBCParser::GetHashType(DXBCHash const &)
0x18017b033  lea     rcx, aDisablehashche; "-disableHashCheck"
0x18017b03a  xor     r9d, r9d
0x18017b03d  cmp     eax, 3
0x18017b040  cmovz   r9, rcx
0x18017b044  mov     [rsp+68h+var_38], 0
0x18017b04d  lea     rax, [rsp+68h+arg_0]
0x18017b052  mov     [rsp+68h+var_40], rax
0x18017b057  lea     rax, [rsp+68h+arg_10]
0x18017b05f  mov     [rsp+68h+var_48], rax
0x18017b064  mov     r8d, esi
0x18017b067  mov     rdx, rbp
0x18017b06a  mov     rcx, rdi
0x18017b06d  mov     rax, [rbx+18h]
0x18017b071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b076  mov     ecx, eax; int
0x18017b078  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18017b07d  mov     rbx, [rsp+68h+arg_10]
0x18017b085  mov     rcx, [r14+138h]; pv
0x18017b08c  call    cs:__imp_CoTaskMemFree
0x18017b092  mov     [r14+138h], rbx
0x18017b099  mov     ebx, [rsp+68h+arg_0]
0x18017b09d  lea     rcx, [rsp+68h+arg_8]
0x18017b0a2  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18017b0a7  mov     eax, ebx
0x18017b0a9  add     rsp, 40h
0x18017b0ad  pop     r14
0x18017b0af  pop     rdi
0x18017b0b0  pop     rsi
0x18017b0b1  pop     rbp
0x18017b0b2  pop     rbx
0x18017b0b3  retn
```
