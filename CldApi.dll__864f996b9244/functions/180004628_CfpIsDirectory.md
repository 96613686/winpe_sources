# CfpIsDirectory

- ea: `0x180004628`
- end: `0x180004691`
- name: `CfpIsDirectory`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d560`
- `0x18000e610`

## callees

- `0x180004628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004669`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000465b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000465b`

## pseudocode

```c
signed int __fastcall CfpIsDirectory(unsigned __int64 a1, bool *a2)
{
  signed int result; // eax
  bool v4; // sf
  __int64 FileInformation; // [rsp+30h] [rbp+8h] BYREF

  FileInformation = 0;
  if ( a1 != -1 && (a1 & 1) != 0 )
    a1 = *(_QWORD *)(a1 & 0xFFFFFFFFFFFFFFFEuLL);
  if ( GetFileInformationByHandleEx((HANDLE)a1, FileAttributeTagInfo, &FileInformation, 8u) )
  {
    result = 0;
  }
  else
  {
    result = GetLastError();
    v4 = result < 0;
    if ( result <= 0 )
      goto LABEL_9;
    result = (unsigned __int16)result | 0x80070000;
  }
  v4 = result < 0;
LABEL_9:
  if ( !v4 )
    *a2 = (FileInformation & 0x10) != 0;
  return result;
}

```

## disassembly

```asm
0x180004628  push    rbx
0x18000462a  sub     rsp, 20h
0x18000462e  mov     [rsp+28h+FileInformation], 0
0x180004637  mov     rbx, rdx
0x18000463a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000463e  jz      short loc_18000464C
0x180004640  test    cl, 1
0x180004643  jz      short loc_18000464C
0x180004645  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004649  mov     rcx, [rcx]; hFile
0x18000464c  mov     r9d, 8; dwBufferSize
0x180004652  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180004657  lea     edx, [r9+1]; FileInformationClass
0x18000465b  call    cs:__imp_GetFileInformationByHandleEx
0x180004661  test    eax, eax
0x180004663  jz      short loc_180004669
0x180004665  xor     eax, eax
0x180004667  jmp     short loc_18000467B
0x180004669  call    cs:__imp_GetLastError
0x18000466f  test    eax, eax
0x180004671  jle     short loc_18000467D
0x180004673  movzx   eax, ax
0x180004676  or      eax, 80070000h
0x18000467b  test    eax, eax
0x18000467d  js      short loc_18000468B
0x18000467f  mov     ecx, dword ptr [rsp+28h+FileInformation]
0x180004683  shr     ecx, 4
0x180004686  and     cl, 1
0x180004689  mov     [rbx], cl
0x18000468b  add     rsp, 20h
0x18000468f  pop     rbx
0x180004690  retn
```
