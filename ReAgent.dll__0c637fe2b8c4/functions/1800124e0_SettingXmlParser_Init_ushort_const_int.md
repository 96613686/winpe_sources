# SettingXmlParser::Init(ushort const *,int)

- ea: `0x1800124e0`
- end: `0x180012595`
- name: `?Init@SettingXmlParser@@UEAAKPEBGH@Z`
- size: `181`
- prototype: `__int64 __fastcall(SettingXmlParser *this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180021e90`
- `0x180027cc0`

## callees

- `0x1800059fc`
- `0x180011f90`
- `0x1800124e0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012527`
- `KERNEL32!HeapAlloc` at `0x180012527`
- `KERNEL32!GetProcessHeap` at `0x180012511`
- `KERNEL32!GetProcessHeap` at `0x180012511`
- `ole32!CoTaskMemFree` at `0x180012503`
- `ole32!CoTaskMemFree` at `0x180012503`

## string_xrefs

- `0x18001256a`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180012563`: `failed to init reagent xml parser`
- `0x180012574`: `SettingXmlParser::Init %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall SettingXmlParser::Init(SettingXmlParser *this, const unsigned __int16 *a2, int a3)
{
  void *v4; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v8; // ebx
  LPVOID v9; // rax
  const wchar_t *v10; // r8
  int v12; // [rsp+28h] [rbp-30h]

  *((_QWORD *)this + 9) = 0;
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 8) = 0;
  }
  ProcessHeap = GetProcessHeap();
  v8 = 8;
  v9 = HeapAlloc(ProcessHeap, 8u, 0x4D0u);
  *((_QWORD *)this + 8) = v9;
  if ( !v9 )
  {
    v12 = 3116;
    v10 = L"failed to allocate memory";
LABEL_7:
    UnattendLogW(
      2,
      L"SettingXmlParser::Init %s (0x%x) in file %S line %d",
      v10,
      v8,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      v12);
    return v8;
  }
  v8 = BasicXmlParser::Init(this, a2, a3);
  if ( v8 )
  {
    v12 = 3118;
    v10 = L"failed to init reagent xml parser";
    goto LABEL_7;
  }
  return v8;
}

```

## disassembly

```asm
0x1800124e0  push    rbx
0x1800124e2  push    rbp
0x1800124e3  push    rsi
0x1800124e4  push    rdi
0x1800124e5  sub     rsp, 38h
0x1800124e9  mov     rdi, rcx
0x1800124ec  mov     qword ptr [rcx+48h], 0
0x1800124f4  mov     rcx, [rcx+40h]; pv
0x1800124f8  mov     esi, r8d
0x1800124fb  mov     rbp, rdx
0x1800124fe  test    rcx, rcx
0x180012501  jz      short loc_180012511
0x180012503  call    cs:__imp_CoTaskMemFree
0x180012509  mov     qword ptr [rdi+40h], 0
0x180012511  call    cs:__imp_GetProcessHeap
0x180012517  mov     ebx, 8
0x18001251c  mov     r8d, 4D0h; dwBytes
0x180012522  mov     rcx, rax; hHeap
0x180012525  mov     edx, ebx; dwFlags
0x180012527  call    cs:__imp_HeapAlloc
0x18001252d  mov     [rdi+40h], rax
0x180012531  test    rax, rax
0x180012534  jnz     short loc_180012547
0x180012536  mov     [rsp+58h+var_30], 0C2Ch
0x18001253e  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180012545  jmp     short loc_18001256A
0x180012547  mov     r8d, esi; int
0x18001254a  mov     rdx, rbp; unsigned __int16 *
0x18001254d  mov     rcx, rdi; this
0x180012550  call    ?Init@BasicXmlParser@@UEAAKPEBGH@Z; BasicXmlParser::Init(ushort const *,int)
0x180012555  mov     ebx, eax
0x180012557  test    eax, eax
0x180012559  jz      short loc_18001258A
0x18001255b  mov     [rsp+58h+var_30], 0C2Eh
0x180012563  lea     r8, aFailedToInitRe; "failed to init reagent xml parser"
0x18001256a  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180012571  mov     r9d, ebx
0x180012574  lea     rdx, aSettingxmlpars_1; "SettingXmlParser::Init %s (0x%x) in fil"...
0x18001257b  mov     [rsp+58h+var_38], rax
0x180012580  mov     ecx, 2
0x180012585  call    UnattendLogW
0x18001258a  mov     eax, ebx
0x18001258c  add     rsp, 38h
0x180012590  pop     rdi
0x180012591  pop     rsi
0x180012592  pop     rbp
0x180012593  pop     rbx
0x180012594  retn
```
