# DeleteBootLogFiles

- ea: `0x180010170`
- end: `0x180010423`
- name: `DeleteBootLogFiles`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001cd38`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x1800087e8`
- `0x18000d410`
- `0x18000d524`
- `0x18000e3cc`
- `0x18000efa4`
- `0x180010170`
- `0x18001042c`
- `0x1800158d4`
- `0x18001a40c`
- `0x18001a42c`
- `0x18001be20`
- `0x1800233ac`
- `0x180023634`
- `0x18002377c`
- `0x18002386c`
- `0x18002485c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180010312`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180010312`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010248`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103f8`

## string_xrefs

- `0x1800103e3`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x180010408`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteBootLogFiles(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v8; // rax
  int v9; // edx
  int v10; // eax
  unsigned int LastError; // ebx
  __int64 v12; // rdx
  HANDLE FirstFileW; // rax
  HANDLE v14; // rdi
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // rax
  __int64 v19; // rdx
  WCHAR *cFileName; // [rsp+20h] [rbp-E0h]
  _WORD v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[112]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp-48h]
  _BYTE v27[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v28; // [rsp+140h] [rbp+40h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+150h] [rbp+50h] BYREF
  WCHAR FileName; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v31[526]; // [rsp+3A2h] [rbp+2A2h] BYREF
  unsigned __int16 v32; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v33[526]; // [rsp+5B2h] [rbp+4B2h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+808h] [rbp+708h]

  FileName = 0;
  memset_0(v31, 0, 0x206u);
  hFindFile = (HANDLE)-1LL;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v21[0] = 0;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v24);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  LODWORD(cFileName) = v9;
  v10 = StringCchPrintfW(&FileName, 0x104u, L"%s\\??????????-??????????.%s", v8);
  LastError = v10;
  if ( v10 >= 0 )
  {
    FirstFileW = FindFirstFileW(&FileName, &FindFileData);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::reset(
      &hFindFile,
      FirstFileW);
    v14 = hFindFile;
    if ( (char *)hFindFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( GetLastError() == 2 )
      {
LABEL_12:
        LastError = 0;
        goto LABEL_13;
      }
      v19 = 794;
    }
    else
    {
      do
      {
        v22 = 0;
        v32 = 0;
        memset_0(v33, 0, 0x206u);
        if ( snwscanf_s(FindFileData.cFileName, 0x104u, L"%010u", &v22) == 1 && a3 < a4 - v22 )
        {
          v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          cFileName = FindFileData.cFileName;
          v10 = StringCchPrintfW(&v32, 0x104u, L"%s\\%s", v15);
          LastError = v10;
          if ( v10 < 0 )
          {
            v12 = 833;
            goto LABEL_16;
          }
          v10 = DeleteFileWithLogging(&v32, v21, &v24);
          LastError = v10;
          if ( v10 < 0 )
          {
            v12 = 836;
            goto LABEL_16;
          }
        }
      }
      while ( FindNextFileW(v14, &FindFileData) );
      if ( GetLastError() == 18 )
      {
        if ( v21[0] )
        {
          LogDeleteFileSuccess(v21, &v24);
          std::wstring::wstring((__int64)v27, (__int64)&sourceString);
          std::basic_stringbuf<unsigned short>::_Tidy(v25);
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
          std::basic_stringbuf<unsigned short>::_Init(v25, v17, v28, v26);
          std::wstring::_Tidy_deallocate(v27);
        }
        goto LABEL_12;
      }
      v19 = 844;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v19,
                  (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
                  v16);
    goto LABEL_13;
  }
  v12 = 782;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
    (const char *)(unsigned int)v10,
    (int)cFileName);
LABEL_13:
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
  return LastError;
}

```

## disassembly

```asm
0x180010170  mov     [rsp-8+arg_10], rbx
0x180010175  push    rbp
0x180010176  push    rsi
0x180010177  push    rdi
0x180010178  push    r12
0x18001017a  push    r13
0x18001017c  push    r14
0x18001017e  push    r15
0x180010180  lea     rbp, [rsp-6D0h]
0x180010188  sub     rsp, 7D0h
0x18001018f  mov     rax, cs:__security_cookie
0x180010196  xor     rax, rsp
0x180010199  mov     [rbp+700h+var_40], rax
0x1800101a0  mov     esi, r9d
0x1800101a3  mov     r14d, r8d
0x1800101a6  mov     r15, rdx
0x1800101a9  mov     rbx, rcx
0x1800101ac  xor     r12d, r12d
0x1800101af  mov     [rbp+700h+FileName], r12w
0x1800101b7  xor     edx, edx; Val
0x1800101b9  mov     r8d, 206h; Size
0x1800101bf  lea     rcx, [rbp+700h+var_45E]; void *
0x1800101c6  call    memset_0
0x1800101cb  mov     [rsp+800h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1800101d4  xor     edx, edx; Val
0x1800101d6  mov     r8d, 250h; Size
0x1800101dc  lea     rcx, [rbp+700h+FindFileData]; void *
0x1800101e0  call    memset_0
0x1800101e5  mov     [rsp+800h+var_7D0], r12w
0x1800101eb  lea     rcx, [rsp+800h+var_7C0]
0x1800101f0  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800101f5  nop
0x1800101f6  mov     rcx, rbx
0x1800101f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800101fe  mov     rdx, rax
0x180010201  mov     rcx, r15
0x180010204  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010209  mov     qword ptr [rsp+800h+var_7E0], rdx
0x18001020e  mov     r9, rax
0x180010211  lea     r8, aSS_1; "%s\\??????????-??????????.%s"
0x180010218  mov     r13d, 104h
0x18001021e  mov     edx, r13d; unsigned __int64
0x180010221  lea     rcx, [rbp+700h+FileName]; unsigned __int16 *
0x180010228  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001022d  mov     ebx, eax
0x18001022f  test    eax, eax
0x180010231  jns     short loc_18001023D
0x180010233  mov     edx, 30Eh
0x180010238  jmp     loc_1800103D9
0x18001023d  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x180010241  lea     rcx, [rbp+700h+FileName]; lpFileName
0x180010248  call    cs:__imp_FindFirstFileW
0x18001024e  mov     rdx, rax
0x180010251  lea     rcx, [rsp+800h+hFindFile]
0x180010256  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::reset(void *)
0x18001025b  mov     rdi, [rsp+800h+hFindFile]
0x180010260  lea     rax, [rdi-1]
0x180010264  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010268  ja      loc_1800103F8
0x18001026e  mov     [rsp+800h+var_7CC], r12d
0x180010273  mov     [rbp+700h+var_250], r12w
0x18001027b  xor     edx, edx; Val
0x18001027d  mov     r8d, 206h; Size
0x180010283  lea     rcx, [rbp+700h+var_24E]; void *
0x18001028a  call    memset_0
0x18001028f  lea     r9, [rsp+800h+var_7CC]
0x180010294  lea     r8, a010u; "%010u"
0x18001029b  mov     rdx, r13; BufferCount
0x18001029e  lea     rcx, [rbp+700h+FindFileData.cFileName]; Buffer
0x1800102a2  call    _snwscanf_s
0x1800102a7  cmp     eax, 1
0x1800102aa  jnz     short loc_18001030B
0x1800102ac  mov     eax, esi
0x1800102ae  sub     eax, [rsp+800h+var_7CC]
0x1800102b2  cmp     r14d, eax
0x1800102b5  jnb     short loc_18001030B
0x1800102b7  mov     rcx, r15
0x1800102ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800102bf  lea     rcx, [rbp+700h+FindFileData.cFileName]
0x1800102c3  mov     qword ptr [rsp+800h+var_7E0], rcx; int
0x1800102c8  mov     r9, rax
0x1800102cb  lea     r8, aSS; "%s\\%s"
0x1800102d2  mov     rdx, r13; unsigned __int64
0x1800102d5  lea     rcx, [rbp+700h+var_250]; unsigned __int16 *
0x1800102dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800102e1  mov     ebx, eax
0x1800102e3  test    eax, eax
0x1800102e5  js      loc_1800103D4
0x1800102eb  lea     r8, [rsp+800h+var_7C0]
0x1800102f0  lea     rdx, [rsp+800h+var_7D0]
0x1800102f5  lea     rcx, [rbp+700h+var_250]
0x1800102fc  call    DeleteFileWithLogging
0x180010301  mov     ebx, eax
0x180010303  test    eax, eax
0x180010305  js      loc_1800103CD
0x18001030b  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x18001030f  mov     rcx, rdi; hFindFile
0x180010312  call    cs:__imp_FindNextFileW
0x180010318  test    eax, eax
0x18001031a  jnz     loc_18001026E
0x180010320  call    cs:__imp_GetLastError
0x180010326  cmp     eax, 12h
0x180010329  jnz     loc_1800103F1
0x18001032f  cmp     [rsp+800h+var_7D0], r12w
0x180010335  jbe     short loc_180010389
0x180010337  lea     rdx, [rsp+800h+var_7C0]
0x18001033c  lea     rcx, [rsp+800h+var_7D0]
0x180010341  call    LogDeleteFileSuccess
0x180010346  lea     rdx, sourceString
0x18001034d  lea     rcx, [rbp+700h+var_6D0]
0x180010351  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010356  nop
0x180010357  lea     rcx, [rsp+800h+var_7B8]
0x18001035c  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x180010361  lea     rcx, [rbp+700h+var_6D0]
0x180010365  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001036a  mov     rdx, rax
0x18001036d  mov     r9d, [rbp+700h+var_748]
0x180010371  mov     r8, [rbp+700h+var_6C0]
0x180010375  lea     rcx, [rsp+800h+var_7B8]
0x18001037a  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18001037f  nop
0x180010380  lea     rcx, [rbp+700h+var_6D0]
0x180010384  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010389  mov     ebx, r12d
0x18001038c  lea     rcx, [rsp+800h+var_7C0]
0x180010391  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180010396  nop
0x180010397  lea     rcx, [rsp+800h+hFindFile]
0x18001039c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800103a1  mov     eax, ebx
0x1800103a3  mov     rcx, [rbp+700h+var_40]
0x1800103aa  xor     rcx, rsp; StackCookie
0x1800103ad  call    __security_check_cookie
0x1800103b2  mov     rbx, [rsp+800h+arg_10]
0x1800103ba  add     rsp, 7D0h
0x1800103c1  pop     r15
0x1800103c3  pop     r14
0x1800103c5  pop     r13
0x1800103c7  pop     r12
0x1800103c9  pop     rdi
0x1800103ca  pop     rsi
0x1800103cb  pop     rbp
0x1800103cc  retn
0x1800103cd  mov     edx, 344h
0x1800103d2  jmp     short loc_1800103D9
0x1800103d4  mov     edx, 341h; void *
0x1800103d9  mov     rcx, [rbp+708h]; this
0x1800103e0  mov     r9d, eax; char *
0x1800103e3  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x1800103ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103ef  jmp     short loc_18001038C
0x1800103f1  mov     edx, 34Ch
0x1800103f6  jmp     short loc_180010408
0x1800103f8  call    cs:__imp_GetLastError
0x1800103fe  cmp     eax, 2
0x180010401  jz      short loc_180010389
0x180010403  mov     edx, 31Ah; void *
0x180010408  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001040f  mov     rcx, [rbp+708h]; this
0x180010416  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001041b  mov     ebx, eax
0x18001041d  jmp     loc_18001038C
```
