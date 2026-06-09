# BasicXmlParser::Init(ushort const *,int)

- ea: `0x180011f90`
- end: `0x18001210d`
- name: `?Init@BasicXmlParser@@UEAAKPEBGH@Z`
- size: `381`
- prototype: `__int64 __fastcall(BasicXmlParser *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800124e0`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x180011f90`
- `0x18001259c`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001202e`
- `KERNEL32!HeapAlloc` at `0x18001202e`
- `KERNEL32!GetProcessHeap` at `0x18001201a`
- `KERNEL32!GetProcessHeap` at `0x18001201a`
- `ole32!CoTaskMemFree` at `0x180011fbd`
- `ole32!CoTaskMemFree` at `0x180011fd4`
- `ole32!CoTaskMemFree` at `0x180011fbd`
- `ole32!CoTaskMemFree` at `0x180011fd4`

## string_xrefs

- `0x18001204c`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180012085`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001209c`: `failed to copy file path`
- `0x180012056`: `BasicXmlParser::Init %s (0x%x) in file %S line %d`
- `0x1800120a8`: `BasicXmlParser::Init %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall BasicXmlParser::Init(BasicXmlParser *this, const unsigned __int16 *a2, int a3)
{
  void *v4; // rcx
  void *v7; // rcx
  unsigned __int64 v9; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int inited; // ebx
  unsigned __int16 *v12; // rax
  const wchar_t *v13; // r8
  int v14; // [rsp+28h] [rbp-20h]
  unsigned __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 1) = 0;
  }
  if ( !a2 )
    return 87;
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, &v15) < 0 || !v15 )
    return 87;
  v9 = v15 + 1;
  ProcessHeap = GetProcessHeap();
  inited = 8;
  v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v9);
  *((_QWORD *)this + 1) = v12;
  if ( v12 )
  {
    inited = StringCchCopyW(v12, v9, a2);
    if ( (inited & 0x80000000) != 0 )
    {
      UnattendLogW(
        2,
        L"BasicXmlParser::Init %s (0x%x) in file %S line %d",
        L"failed to copy file path",
        inited,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        2318);
      return (unsigned __int16)inited;
    }
    inited = BasicXmlParser::InitInternal(this);
    if ( !inited )
    {
      if ( a3 )
        return (*(unsigned int (__fastcall **)(BasicXmlParser *))(*(_QWORD *)this + 32LL))(this);
      return inited;
    }
    v14 = 2320;
    v13 = L"failed to init internal";
  }
  else
  {
    v14 = 2316;
    v13 = L"failed to allocate memory";
  }
  UnattendLogW(
    2,
    L"BasicXmlParser::Init %s (0x%x) in file %S line %d",
    v13,
    inited,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
    v14);
  return inited;
}

```

## disassembly

```asm
0x180011f90  mov     [rsp+arg_8], rbx
0x180011f95  mov     [rsp+arg_10], rbp
0x180011f9a  push    rsi
0x180011f9b  push    rdi
0x180011f9c  push    r14
0x180011f9e  sub     rsp, 30h
0x180011fa2  mov     rdi, rcx
0x180011fa5  mov     [rsp+48h+arg_0], 0
0x180011fae  mov     rcx, [rcx+10h]; pv
0x180011fb2  mov     r14d, r8d
0x180011fb5  mov     rbp, rdx
0x180011fb8  test    rcx, rcx
0x180011fbb  jz      short loc_180011FCB
0x180011fbd  call    cs:__imp_CoTaskMemFree
0x180011fc3  mov     qword ptr [rdi+10h], 0
0x180011fcb  mov     rcx, [rdi+8]; pv
0x180011fcf  test    rcx, rcx
0x180011fd2  jz      short loc_180011FE2
0x180011fd4  call    cs:__imp_CoTaskMemFree
0x180011fda  mov     qword ptr [rdi+8], 0
0x180011fe2  test    rbp, rbp
0x180011fe5  jnz     short loc_180011FEF
0x180011fe7  lea     eax, [rbp+57h]
0x180011fea  jmp     loc_1800120FA
0x180011fef  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x180011ff4  mov     edx, 7FFFFFFFh; unsigned __int64
0x180011ff9  mov     rcx, rbp; unsigned __int16 *
0x180011ffc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012001  test    eax, eax
0x180012003  js      loc_1800120F3
0x180012009  mov     rsi, [rsp+48h+arg_0]
0x18001200e  test    rsi, rsi
0x180012011  jz      loc_1800120F3
0x180012017  inc     rsi
0x18001201a  call    cs:__imp_GetProcessHeap
0x180012020  mov     ebx, 8
0x180012025  lea     r8, [rsi+rsi]; dwBytes
0x180012029  mov     edx, ebx; dwFlags
0x18001202b  mov     rcx, rax; hHeap
0x18001202e  call    cs:__imp_HeapAlloc
0x180012034  mov     [rdi+8], rax
0x180012038  test    rax, rax
0x18001203b  jnz     short loc_180012071
0x18001203d  mov     [rsp+48h+var_20], 90Ch
0x180012045  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18001204c  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180012053  mov     r9d, ebx
0x180012056  lea     rdx, aBasicxmlparser_1; "BasicXmlParser::Init %s (0x%x) in file "...
0x18001205d  mov     [rsp+48h+var_28], rax
0x180012062  mov     ecx, 2
0x180012067  call    UnattendLogW
0x18001206c  jmp     loc_1800120F8
0x180012071  mov     r8, rbp; unsigned __int16 *
0x180012074  mov     rdx, rsi; unsigned __int64
0x180012077  mov     rcx, rax; unsigned __int16 *
0x18001207a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001207f  mov     ebx, eax
0x180012081  test    eax, eax
0x180012083  jns     short loc_1800120B9
0x180012085  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001208c  mov     [rsp+48h+var_20], 90Eh
0x180012094  mov     r9d, ebx
0x180012097  mov     [rsp+48h+var_28], rax
0x18001209c  lea     r8, aFailedToCopyFi_0; "failed to copy file path"
0x1800120a3  mov     ecx, 2
0x1800120a8  lea     rdx, aBasicxmlparser_1; "BasicXmlParser::Init %s (0x%x) in file "...
0x1800120af  call    UnattendLogW
0x1800120b4  movzx   ebx, bx
0x1800120b7  jmp     short loc_1800120F8
0x1800120b9  mov     rcx, rdi; this
0x1800120bc  call    ?InitInternal@BasicXmlParser@@AEAAKXZ; BasicXmlParser::InitInternal(void)
0x1800120c1  mov     ebx, eax
0x1800120c3  test    eax, eax
0x1800120c5  jz      short loc_1800120DB
0x1800120c7  mov     [rsp+48h+var_20], 910h
0x1800120cf  lea     r8, aFailedToInitIn; "failed to init internal"
0x1800120d6  jmp     loc_18001204C
0x1800120db  test    r14d, r14d
0x1800120de  jz      short loc_1800120F8
0x1800120e0  mov     rax, [rdi]
0x1800120e3  mov     rcx, rdi
0x1800120e6  mov     rax, [rax+20h]
0x1800120ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ef  mov     ebx, eax
0x1800120f1  jmp     short loc_1800120F8
0x1800120f3  mov     ebx, 57h ; 'W'
0x1800120f8  mov     eax, ebx
0x1800120fa  mov     rbx, [rsp+48h+arg_8]
0x1800120ff  mov     rbp, [rsp+48h+arg_10]
0x180012104  add     rsp, 30h
0x180012108  pop     r14
0x18001210a  pop     rdi
0x18001210b  pop     rsi
0x18001210c  retn
```
