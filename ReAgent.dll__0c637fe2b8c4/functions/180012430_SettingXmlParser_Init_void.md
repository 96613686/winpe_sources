# SettingXmlParser::Init(void *)

- ea: `0x180012430`
- end: `0x1800124d8`
- name: `?Init@SettingXmlParser@@UEAAKPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(SettingXmlParser *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180021e90`

## callees

- `0x1800059fc`
- `0x180012120`
- `0x180012430`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001246e`
- `KERNEL32!HeapAlloc` at `0x18001246e`
- `KERNEL32!GetProcessHeap` at `0x180012458`
- `KERNEL32!GetProcessHeap` at `0x180012458`
- `ole32!CoTaskMemFree` at `0x18001244a`
- `ole32!CoTaskMemFree` at `0x18001244a`

## string_xrefs

- `0x1800124ab`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x1800124a4`: `failed to init reagent xml parser`
- `0x1800124b5`: `SettingXmlParser::Init %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall SettingXmlParser::Init(SettingXmlParser *this, void *a2)
{
  void *v3; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v5; // ebx
  LPVOID v6; // rax
  const wchar_t *v7; // r8
  int v9; // [rsp+28h] [rbp-10h]

  *((_QWORD *)this + 9) = a2;
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 8) = 0;
  }
  ProcessHeap = GetProcessHeap();
  v5 = 8;
  v6 = HeapAlloc(ProcessHeap, 8u, 0x4D0u);
  *((_QWORD *)this + 8) = v6;
  if ( !v6 )
  {
    v9 = 3136;
    v7 = L"failed to allocate memory";
LABEL_7:
    UnattendLogW(
      2,
      L"SettingXmlParser::Init %s (0x%x) in file %S line %d",
      v7,
      v5,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      v9);
    return v5;
  }
  v5 = BasicXmlParser::Init(this);
  if ( v5 )
  {
    v9 = 3138;
    v7 = L"failed to init reagent xml parser";
    goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x180012430  mov     [rsp+arg_0], rbx
0x180012435  push    rdi
0x180012436  sub     rsp, 30h
0x18001243a  mov     rdi, rcx
0x18001243d  mov     [rcx+48h], rdx
0x180012441  mov     rcx, [rcx+40h]; pv
0x180012445  test    rcx, rcx
0x180012448  jz      short loc_180012458
0x18001244a  call    cs:__imp_CoTaskMemFree
0x180012450  mov     qword ptr [rdi+40h], 0
0x180012458  call    cs:__imp_GetProcessHeap
0x18001245e  mov     ebx, 8
0x180012463  mov     r8d, 4D0h; dwBytes
0x180012469  mov     rcx, rax; hHeap
0x18001246c  mov     edx, ebx; dwFlags
0x18001246e  call    cs:__imp_HeapAlloc
0x180012474  mov     [rdi+40h], rax
0x180012478  test    rax, rax
0x18001247b  jnz     short loc_18001248E
0x18001247d  mov     [rsp+38h+var_10], 0C40h
0x180012485  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18001248c  jmp     short loc_1800124AB
0x18001248e  mov     rcx, rdi; this
0x180012491  call    ?Init@BasicXmlParser@@UEAAKXZ; BasicXmlParser::Init(void)
0x180012496  mov     ebx, eax
0x180012498  test    eax, eax
0x18001249a  jz      short loc_1800124CB
0x18001249c  mov     [rsp+38h+var_10], 0C42h
0x1800124a4  lea     r8, aFailedToInitRe; "failed to init reagent xml parser"
0x1800124ab  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800124b2  mov     r9d, ebx
0x1800124b5  lea     rdx, aSettingxmlpars_1; "SettingXmlParser::Init %s (0x%x) in fil"...
0x1800124bc  mov     [rsp+38h+var_18], rax
0x1800124c1  mov     ecx, 2
0x1800124c6  call    UnattendLogW
0x1800124cb  mov     eax, ebx
0x1800124cd  mov     rbx, [rsp+38h+arg_0]
0x1800124d2  add     rsp, 30h
0x1800124d6  pop     rdi
0x1800124d7  retn
```
