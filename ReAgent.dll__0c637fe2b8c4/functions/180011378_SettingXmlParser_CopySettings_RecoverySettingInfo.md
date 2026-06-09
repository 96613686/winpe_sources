# SettingXmlParser::CopySettings(RecoverySettingInfo *)

- ea: `0x180011378`
- end: `0x18001148f`
- name: `?CopySettings@SettingXmlParser@@QEAAKPEAURecoverySettingInfo@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(SettingXmlParser *this, struct RecoverySettingInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180021e90`

## callees

- `0x1800059fc`
- `0x180011378`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800113c7`
- `KERNEL32!HeapAlloc` at `0x1800113c7`
- `KERNEL32!GetProcessHeap` at `0x1800113b1`
- `KERNEL32!GetProcessHeap` at `0x1800113b1`
- `ole32!CoTaskMemFree` at `0x1800113a3`
- `ole32!CoTaskMemFree` at `0x1800113a3`

## string_xrefs

- `0x1800113d6`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x1800113f4`: `SettingXmlParser::CopySettings %s (0x%x) in file %S line %d`

## pseudocode

```c
__int64 __fastcall SettingXmlParser::CopySettings(SettingXmlParser *this, struct RecoverySettingInfo *a2)
{
  struct RecoverySettingInfo *v2; // rbx
  void *v5; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v7; // edi
  _OWORD *v8; // rax
  __int64 v9; // rcx
  __int128 v10; // xmm1

  v2 = a2;
  if ( !a2 )
    return 87;
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 8) = 0;
  }
  ProcessHeap = GetProcessHeap();
  v7 = 8;
  v8 = HeapAlloc(ProcessHeap, 8u, 0x4D0u);
  *((_QWORD *)this + 8) = v8;
  if ( v8 )
  {
    v7 = 0;
    v9 = 9;
    do
    {
      *v8 = *(_OWORD *)v2;
      v8[1] = *((_OWORD *)v2 + 1);
      v8[2] = *((_OWORD *)v2 + 2);
      v8[3] = *((_OWORD *)v2 + 3);
      v8[4] = *((_OWORD *)v2 + 4);
      v8[5] = *((_OWORD *)v2 + 5);
      v8[6] = *((_OWORD *)v2 + 6);
      v10 = *((_OWORD *)v2 + 7);
      v2 = (struct RecoverySettingInfo *)((char *)v2 + 128);
      v8[7] = v10;
      v8 += 8;
      --v9;
    }
    while ( v9 );
    *v8 = *(_OWORD *)v2;
    v8[1] = *((_OWORD *)v2 + 1);
    v8[2] = *((_OWORD *)v2 + 2);
    v8[3] = *((_OWORD *)v2 + 3);
    v8[4] = *((_OWORD *)v2 + 4);
  }
  else
  {
    UnattendLogW(
      2,
      L"SettingXmlParser::CopySettings %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      3306);
  }
  return v7;
}

```

## disassembly

```asm
0x180011378  mov     [rsp+arg_0], rbx
0x18001137d  mov     [rsp+arg_8], rsi
0x180011382  push    rdi
0x180011383  sub     rsp, 30h
0x180011387  mov     rbx, rdx
0x18001138a  mov     rsi, rcx
0x18001138d  test    rdx, rdx
0x180011390  jnz     short loc_18001139A
0x180011392  lea     eax, [rdx+57h]
0x180011395  jmp     loc_18001147F
0x18001139a  mov     rcx, [rcx+40h]; pv
0x18001139e  test    rcx, rcx
0x1800113a1  jz      short loc_1800113B1
0x1800113a3  call    cs:__imp_CoTaskMemFree
0x1800113a9  mov     qword ptr [rsi+40h], 0
0x1800113b1  call    cs:__imp_GetProcessHeap
0x1800113b7  mov     edi, 8
0x1800113bc  mov     r8d, 4D0h; dwBytes
0x1800113c2  mov     rcx, rax; hHeap
0x1800113c5  mov     edx, edi; dwFlags
0x1800113c7  call    cs:__imp_HeapAlloc
0x1800113cd  mov     [rsi+40h], rax
0x1800113d1  test    rax, rax
0x1800113d4  jnz     short loc_180011405
0x1800113d6  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800113dd  mov     [rsp+38h+var_10], 0CEAh
0x1800113e5  mov     r9d, edi
0x1800113e8  mov     [rsp+38h+var_18], rax
0x1800113ed  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800113f4  lea     rdx, aSettingxmlpars; "SettingXmlParser::CopySettings %s (0x%x"...
0x1800113fb  lea     ecx, [rdi-6]
0x1800113fe  call    UnattendLogW
0x180011403  jmp     short loc_18001147D
0x180011405  xor     edi, edi
0x180011407  lea     ecx, [rdi+9]
0x18001140a  lea     edx, [rcx+77h]
0x18001140d  movups  xmm0, xmmword ptr [rbx]
0x180011410  movups  xmmword ptr [rax], xmm0
0x180011413  movups  xmm1, xmmword ptr [rbx+10h]
0x180011417  movups  xmmword ptr [rax+10h], xmm1
0x18001141b  movups  xmm0, xmmword ptr [rbx+20h]
0x18001141f  movups  xmmword ptr [rax+20h], xmm0
0x180011423  movups  xmm1, xmmword ptr [rbx+30h]
0x180011427  movups  xmmword ptr [rax+30h], xmm1
0x18001142b  movups  xmm0, xmmword ptr [rbx+40h]
0x18001142f  movups  xmmword ptr [rax+40h], xmm0
0x180011433  movups  xmm1, xmmword ptr [rbx+50h]
0x180011437  movups  xmmword ptr [rax+50h], xmm1
0x18001143b  movups  xmm0, xmmword ptr [rbx+60h]
0x18001143f  movups  xmmword ptr [rax+60h], xmm0
0x180011443  movups  xmm1, xmmword ptr [rbx+70h]
0x180011447  add     rbx, rdx
0x18001144a  movups  xmmword ptr [rax+70h], xmm1
0x18001144e  add     rax, rdx
0x180011451  sub     rcx, 1
0x180011455  jnz     short loc_18001140D
0x180011457  movups  xmm0, xmmword ptr [rbx]
0x18001145a  movups  xmmword ptr [rax], xmm0
0x18001145d  movups  xmm1, xmmword ptr [rbx+10h]
0x180011461  movups  xmmword ptr [rax+10h], xmm1
0x180011465  movups  xmm0, xmmword ptr [rbx+20h]
0x180011469  movups  xmmword ptr [rax+20h], xmm0
0x18001146d  movups  xmm1, xmmword ptr [rbx+30h]
0x180011471  movups  xmmword ptr [rax+30h], xmm1
0x180011475  movups  xmm0, xmmword ptr [rbx+40h]
0x180011479  movups  xmmword ptr [rax+40h], xmm0
0x18001147d  mov     eax, edi
0x18001147f  mov     rbx, [rsp+38h+arg_0]
0x180011484  mov     rsi, [rsp+38h+arg_8]
0x180011489  add     rsp, 30h
0x18001148d  pop     rdi
0x18001148e  retn
```
