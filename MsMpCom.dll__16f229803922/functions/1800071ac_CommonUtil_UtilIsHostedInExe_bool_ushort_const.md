# CommonUtil::UtilIsHostedInExe(bool *,ushort const *)

- ea: `0x1800071ac`
- end: `0x180007266`
- name: `?UtilIsHostedInExe@CommonUtil@@YAJPEA_NPEBG@Z`
- size: `186`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, bool *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x180006f68`
- `0x1800071ac`
- `0x180009110`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007239`
- `msvcrt!_wcsicmp` at `0x180007239`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800071e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007223`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000724e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800071e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007223`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000724e`

## string_xrefs

- `0x180007232`: `dllhost.exe`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilIsHostedInExe(CommonUtil *this, unsigned __int16 **a2, unsigned __int16 *a3)
{
  int ModuleFileName; // ebx
  void *v6; // rbx
  int FilenameFrom; // eax
  unsigned int v8; // edi
  void *v9; // [rsp+38h] [rbp+10h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  ModuleFileName = CommonUtil::UtilGetModuleFileName((CommonUtil *)&v9, a2, (HINSTANCE)a3);
  if ( ModuleFileName < 0 )
  {
    if ( v9 )
      operator delete[](v9);
    return (unsigned int)ModuleFileName;
  }
  v6 = v9;
  String2 = 0;
  FilenameFrom = CommonUtil::UtilGetFilenameFromPath<unsigned short>(v9, &String2);
  v8 = FilenameFrom;
  if ( FilenameFrom == 1 )
  {
    v8 = -2147467259;
LABEL_8:
    if ( v6 )
      operator delete[](v6);
    return v8;
  }
  if ( FilenameFrom < 0 )
    goto LABEL_8;
  *(_BYTE *)this = _wcsicmp(L"dllhost.exe", String2) == 0;
  if ( v6 )
    operator delete[](v6);
  return 0;
}

```

## disassembly

```asm
0x1800071ac  mov     rax, rsp
0x1800071af  mov     [rax+8], rbx
0x1800071b3  mov     [rax+20h], rsi
0x1800071b7  mov     [rax+10h], rdx
0x1800071bb  push    rdi
0x1800071bc  sub     rsp, 20h
0x1800071c0  mov     rsi, rcx
0x1800071c3  mov     qword ptr [rax+10h], 0
0x1800071cb  lea     rcx, [rax+10h]; this
0x1800071cf  call    ?UtilGetModuleFileName@CommonUtil@@YAJPEAPEAGPEAUHINSTANCE__@@@Z; CommonUtil::UtilGetModuleFileName(ushort * *,HINSTANCE__ *)
0x1800071d4  mov     ebx, eax
0x1800071d6  test    eax, eax
0x1800071d8  jns     short loc_1800071EE
0x1800071da  mov     rcx, [rsp+28h+arg_8]
0x1800071df  test    rcx, rcx
0x1800071e2  jz      short loc_1800071EA
0x1800071e4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800071ea  mov     eax, ebx
0x1800071ec  jmp     short loc_180007256
0x1800071ee  mov     rbx, [rsp+28h+arg_8]
0x1800071f3  lea     rdx, [rsp+28h+String2]
0x1800071f8  mov     rcx, rbx
0x1800071fb  mov     [rsp+28h+String2], 0
0x180007204  call    ??$UtilGetFilenameFromPath@G@CommonUtil@@YAJPEBGPEAPEBGPEA_K@Z; CommonUtil::UtilGetFilenameFromPath<ushort>(ushort const *,ushort const * *,unsigned __int64 *)
0x180007209  mov     edi, eax
0x18000720b  cmp     eax, 1
0x18000720e  jnz     short loc_180007217
0x180007210  mov     edi, 80004005h
0x180007215  jmp     short loc_18000721B
0x180007217  test    eax, eax
0x180007219  jns     short loc_18000722D
0x18000721b  test    rbx, rbx
0x18000721e  jz      short loc_180007229
0x180007220  mov     rcx, rbx
0x180007223  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007229  mov     eax, edi
0x18000722b  jmp     short loc_180007256
0x18000722d  mov     rdx, [rsp+28h+String2]; String2
0x180007232  lea     rcx, aDllhostExe; "dllhost.exe"
0x180007239  call    cs:__imp__wcsicmp
0x18000723f  test    eax, eax
0x180007241  setz    al
0x180007244  mov     [rsi], al
0x180007246  test    rbx, rbx
0x180007249  jz      short loc_180007254
0x18000724b  mov     rcx, rbx
0x18000724e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007254  xor     eax, eax
0x180007256  mov     rbx, [rsp+28h+arg_0]
0x18000725b  mov     rsi, [rsp+28h+arg_18]
0x180007260  add     rsp, 20h
0x180007264  pop     rdi
0x180007265  retn
```
