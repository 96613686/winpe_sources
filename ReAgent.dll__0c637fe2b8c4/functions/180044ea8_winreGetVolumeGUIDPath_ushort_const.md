# winreGetVolumeGUIDPath(ushort const *)

- ea: `0x180044ea8`
- end: `0x180045013`
- name: `?winreGetVolumeGUIDPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `363`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1800449cc`
- `0x180045870`
- `0x180045ce0`

## callees

- `0x1800059fc`
- `0x18001c324`
- `0x18001c354`
- `0x18001c448`
- `0x18001ee18`
- `0x1800413d8`
- `0x18004156c`
- `0x1800438fc`
- `0x180044ea8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044f10`
- `KERNEL32!GetLastError` at `0x180044f68`
- `KERNEL32!GetLastError` at `0x180044f10`
- `KERNEL32!GetLastError` at `0x180044f68`
- `KERNEL32!GetVolumePathNameW` at `0x180044f06`
- `KERNEL32!GetVolumePathNameW` at `0x180044f06`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180044f5e`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180044f5e`

## string_xrefs

- `0x180044f1c`: `winreGetVolumeGUIDPath GetVolumePathName returned 0 for %S, last error is %lu`
- `0x180044f76`: `winreGetVolumeGUIDPath GetVolumeNameForVolumeMountPoint returned 0 for %S, last error is %lu`
- `0x180044ff0`: `winreGetVolumeGUIDPath returning %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winreGetVolumeGUIDPath(_QWORD *a1, const WCHAR *a2)
{
  _QWORD *v3; // rbx
  DWORD v4; // eax
  DWORD LastError; // eax
  __int64 v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // r8
  int v10; // [rsp+20h] [rbp-68h]
  LPWSTR lpszVolumePathName[3]; // [rsp+30h] [rbp-58h] BYREF
  LPWSTR lpszVolumeName[3]; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v13[40]; // [rsp+60h] [rbp-28h] BYREF

  v3 = a1;
  std::wstring::wstring(a1, a2);
  try
  {
    v10 = 1;
    std::vector<unsigned short>::vector<unsigned short>(lpszVolumePathName);
    std::vector<unsigned short>::vector<unsigned short>(lpszVolumeName);
    if ( GetVolumePathNameW(a2, lpszVolumePathName[0], lpszVolumePathName[1] - lpszVolumePathName[0]) )
    {
      if ( GetVolumeNameForVolumeMountPointW(
             lpszVolumePathName[0],
             lpszVolumeName[0],
             lpszVolumeName[1] - lpszVolumeName[0]) )
      {
        v6 = std::wstring::wstring(v13, lpszVolumeName[0]);
        std::wstring::operator=(v3, v6);
        std::wstring::~wstring((__int64)v13, v7);
      }
      else
      {
        LastError = GetLastError();
        UnattendLogW(
          2,
          L"winreGetVolumeGUIDPath GetVolumeNameForVolumeMountPoint returned 0 for %S, last error is %lu",
          lpszVolumePathName[0],
          LastError,
          v10,
          -2);
      }
      std::vector<unsigned short>::~vector<unsigned short>(lpszVolumeName);
      std::vector<unsigned short>::~vector<unsigned short>(lpszVolumePathName);
    }
    else
    {
      v4 = GetLastError();
      UnattendLogW(2, L"winreGetVolumeGUIDPath GetVolumePathName returned 0 for %S, last error is %lu", a2, v4, v10, -2);
      std::vector<unsigned short>::~vector<unsigned short>(lpszVolumeName);
      std::vector<unsigned short>::~vector<unsigned short>(lpszVolumePathName);
    }
  }
  catch ( exception )
  {
    UnattendLogW(2, L"winreGetVolumeGUIDPath Out of Memory error");
    v3 = a1;
  }
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
  UnattendLogW(0, L"winreGetVolumeGUIDPath returning %ls", v8);
  return v3;
}

```

## disassembly

```asm
0x180044ea8  mov     rax, rsp
0x180044eab  mov     [rax+8], rcx
0x180044eaf  push    rdi
0x180044eb0  sub     rsp, 80h
0x180044eb7  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x180044ebf  mov     [rax+10h], rbx
0x180044ec3  mov     rdi, rdx
0x180044ec6  mov     rbx, rcx
0x180044ec9  mov     dword ptr [rax-68h], 0
0x180044ed0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180044ed5  mov     [rsp+88h+var_68], 1
0x180044edd  lea     rcx, [rsp+88h+lpszVolumePathName]
0x180044ee2  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_K@Z; std::vector<ushort>::vector<ushort>(unsigned __int64)
0x180044ee7  nop
0x180044ee8  lea     rcx, [rsp+88h+lpszVolumeName]
0x180044eed  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_K@Z; std::vector<ushort>::vector<ushort>(unsigned __int64)
0x180044ef2  nop
0x180044ef3  mov     rdx, [rsp+88h+lpszVolumePathName]; lpszVolumePathName
0x180044ef8  mov     r8, [rsp+88h+var_50]
0x180044efd  sub     r8, rdx
0x180044f00  sar     r8, 1; cchBufferLength
0x180044f03  mov     rcx, rdi; lpszFileName
0x180044f06  call    cs:__imp_GetVolumePathNameW
0x180044f0c  test    eax, eax
0x180044f0e  jnz     short loc_180044F49
0x180044f10  call    cs:__imp_GetLastError
0x180044f16  mov     r9d, eax
0x180044f19  mov     r8, rdi
0x180044f1c  lea     rdx, aWinregetvolume_1; "winreGetVolumeGUIDPath GetVolumePathNam"...
0x180044f23  mov     ecx, 2
0x180044f28  call    UnattendLogW
0x180044f2d  nop
0x180044f2e  lea     rcx, [rsp+88h+lpszVolumeName]
0x180044f33  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044f38  nop
0x180044f39  lea     rcx, [rsp+88h+lpszVolumePathName]
0x180044f3e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044f43  nop
0x180044f44  jmp     loc_180044FE5
0x180044f49  mov     rdx, [rsp+88h+lpszVolumeName]; lpszVolumeName
0x180044f4e  mov     r8, [rsp+88h+var_38]
0x180044f53  sub     r8, rdx
0x180044f56  sar     r8, 1; cchBufferLength
0x180044f59  mov     rcx, [rsp+88h+lpszVolumePathName]; lpszVolumeMountPoint
0x180044f5e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180044f64  test    eax, eax
0x180044f66  jnz     short loc_180044FA0
0x180044f68  call    cs:__imp_GetLastError
0x180044f6e  mov     r9d, eax
0x180044f71  mov     r8, [rsp+88h+lpszVolumePathName]
0x180044f76  lea     rdx, aWinregetvolume; "winreGetVolumeGUIDPath GetVolumeNameFor"...
0x180044f7d  mov     ecx, 2
0x180044f82  call    UnattendLogW
0x180044f87  nop
0x180044f88  lea     rcx, [rsp+88h+lpszVolumeName]
0x180044f8d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044f92  nop
0x180044f93  lea     rcx, [rsp+88h+lpszVolumePathName]
0x180044f98  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044f9d  nop
0x180044f9e  jmp     short loc_180044FE5
0x180044fa0  mov     rdx, [rsp+88h+lpszVolumeName]
0x180044fa5  lea     rcx, [rsp+88h+var_28]
0x180044faa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044faf  mov     rdx, rax
0x180044fb2  mov     rcx, rbx
0x180044fb5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044fba  lea     rcx, [rsp+88h+var_28]
0x180044fbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044fc4  nop
0x180044fc5  lea     rcx, [rsp+88h+lpszVolumeName]
0x180044fca  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044fcf  nop
0x180044fd0  lea     rcx, [rsp+88h+lpszVolumePathName]
0x180044fd5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044fda  nop
0x180044fdb  jmp     short loc_180044FE5
0x180044fdd  mov     rbx, [rsp+88h+arg_0]
0x180044fe5  mov     rcx, rbx
0x180044fe8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044fed  mov     r8, rax
0x180044ff0  lea     rdx, aWinregetvolume_2; "winreGetVolumeGUIDPath returning %ls"
0x180044ff7  xor     ecx, ecx
0x180044ff9  call    UnattendLogW
0x180044ffe  mov     rax, rbx
0x180045001  mov     rbx, [rsp+88h+arg_8]
0x180045009  add     rsp, 80h
0x180045010  pop     rdi
0x180045011  retn
```
