# VcreateFile(VstackStrLCP const &,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18004acd0`
- end: `0x18004ad67`
- name: `?VcreateFile@@YAPEAXAEBVVstackStrLCP@@KKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `151`
- prototype: `void *__fastcall(const struct VstackStrLCP *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, DWORD, unsigned int, HANDLE)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006ba20`
- `0x18006d120`
- `0x18006e510`
- `0x180070440`
- `0x180091940`
- `0x1800928f0`
- `0x180094b80`
- `0x1800e12b0`

## callees

- `0x18004acd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18004ad0c`
- `KERNEL32!CreateFileW` at `0x18004ad0c`
- `KERNEL32!GetFileType` at `0x18004ad21`
- `KERNEL32!GetFileType` at `0x18004ad21`
- `KERNEL32!CloseHandle` at `0x18004ad4e`
- `KERNEL32!CloseHandle` at `0x18004ad4e`
- `onetnative!ULSSendTraceTag` at `0x18004ad45`
- `onetnative!ULSSendTraceTag` at `0x18004ad45`

## pseudocode

```c
void *__fastcall VcreateFile(
        LPCWSTR *a1,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD a5,
        unsigned int a6,
        HANDLE hTemplateFile)
{
  HANDLE FileW; // rax
  __int64 v8; // rdi
  void *v9; // rbx
  DWORD FileType; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-28h]

  FileW = CreateFileW(a1[64], a2, a3, a4, a5, a6 & 0xFFE0FFFF | 0x100000, hTemplateFile);
  v8 = -1;
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return v9;
  FileType = GetFileType(FileW);
  if ( FileType == 1 )
    return v9;
  LODWORD(dwCreationDisposition) = FileType;
  ULSSendTraceTag(3974544, 117141571, 20, L"GetFileType returned %d in VensureOnlyFile", dwCreationDisposition);
  CloseHandle(v9);
  return (void *)v8;
}

```

## disassembly

```asm
0x18004acd0  mov     [rsp+arg_0], rbx
0x18004acd5  push    rdi
0x18004acd6  sub     rsp, 40h
0x18004acda  mov     rax, [rsp+48h+arg_30]
0x18004ace2  mov     r10d, [rsp+48h+arg_28]
0x18004ace7  mov     rcx, [rcx+200h]; lpFileName
0x18004acee  and     r10d, 0FFF0FFFFh
0x18004acf5  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18004acfa  bts     r10d, 14h
0x18004acff  mov     eax, [rsp+48h+arg_20]
0x18004ad03  mov     [rsp+48h+dwFlagsAndAttributes], r10d; dwFlagsAndAttributes
0x18004ad08  mov     dword ptr [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18004ad0c  call    cs:CreateFileW
0x18004ad12  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004ad16  mov     rbx, rax
0x18004ad19  cmp     rax, rdi
0x18004ad1c  jz      short loc_18004AD56
0x18004ad1e  mov     rcx, rax; hFile
0x18004ad21  call    cs:GetFileType
0x18004ad27  cmp     eax, 1
0x18004ad2a  jz      short loc_18004AD56
0x18004ad2c  lea     r9, aGetfiletypeRet; "GetFileType returned %d in VensureOnlyF"...
0x18004ad33  mov     dword ptr [rsp+48h+dwCreationDisposition], eax
0x18004ad37  mov     edx, 6FB7043h
0x18004ad3c  lea     r8d, [rdi+15h]
0x18004ad40  mov     ecx, 3CA590h
0x18004ad45  call    cs:ULSSendTraceTag
0x18004ad4b  mov     rcx, rbx; hObject
0x18004ad4e  call    cs:CloseHandle
0x18004ad54  jmp     short loc_18004AD59
0x18004ad56  mov     rdi, rbx
0x18004ad59  mov     rax, rdi
0x18004ad5c  mov     rbx, [rsp+48h+arg_0]
0x18004ad61  add     rsp, 40h
0x18004ad65  pop     rdi
0x18004ad66  retn
```
