# GetStorageFromSubject(SIP_SUBJECTINFO_ *,ulong,HINSTANCE__ *,bool)

- ea: `0x180006690`
- end: `0x180006721`
- name: `?GetStorageFromSubject@@YAPEAUIStorage@@PEAUSIP_SUBJECTINFO_@@KPEAUHINSTANCE__@@_N@Z`
- size: `145`
- prototype: `struct IStorage *__fastcall(struct SIP_SUBJECTINFO_ *, unsigned int, HINSTANCE, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba20`

## callees

- `0x180006690`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800066b2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800066b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006715`

## string_xrefs

- `0x1800066a8`: `StgOpenStorage`

## pseudocode

```c
struct IStorage *__fastcall GetStorageFromSubject(struct SIP_SUBJECTINFO_ *a1, unsigned int a2, HINSTANCE a3, char a4)
{
  FARPROC ProcAddress; // rax
  struct IStorage *result; // rax
  char *hFile; // rcx
  struct IStorage *v10; // [rsp+40h] [rbp-38h] BYREF

  if ( a4 )
  {
    hFile = (char *)a1->hFile;
    if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(hFile);
      a1->hFile = 0;
    }
  }
  ProcAddress = GetProcAddress(a3, "StgOpenStorage");
  if ( !ProcAddress )
    return 0;
  v10 = 0;
  if ( ((int (__fastcall *)(LPCWSTR, _QWORD, _QWORD, _QWORD, _DWORD, struct IStorage **))ProcAddress)(
         a1->pwsFileName,
         0,
         a2,
         0,
         0,
         &v10) < 0
    || (result = v10) == 0 )
  {
    SetLastError(0xBu);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006690  push    rbx
0x180006692  push    rbp
0x180006693  push    rsi
0x180006694  push    rdi
0x180006695  sub     rsp, 58h
0x180006699  xor     ebp, ebp
0x18000669b  mov     rbx, r8
0x18000669e  mov     esi, edx
0x1800066a0  mov     rdi, rcx
0x1800066a3  test    r9b, r9b
0x1800066a6  jnz     short loc_180006707
0x1800066a8  lea     rdx, aStgopenstorage; "StgOpenStorage"
0x1800066af  mov     rcx, rbx; hModule
0x1800066b2  call    cs:__imp_GetProcAddress
0x1800066b8  test    rax, rax
0x1800066bb  jz      short loc_180006703
0x1800066bd  lea     rcx, [rsp+78h+var_38]
0x1800066c2  mov     [rsp+78h+var_38], rbp
0x1800066c7  mov     [rsp+78h+var_50], rcx
0x1800066cc  xor     r9d, r9d
0x1800066cf  mov     rcx, [rdi+18h]
0x1800066d3  mov     r8d, esi
0x1800066d6  xor     edx, edx
0x1800066d8  mov     [rsp+78h+var_58], ebp
0x1800066dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e1  test    eax, eax
0x1800066e3  js      short loc_1800066F8
0x1800066e5  mov     rax, [rsp+78h+var_38]
0x1800066ea  test    rax, rax
0x1800066ed  jz      short loc_1800066F8
0x1800066ef  add     rsp, 58h
0x1800066f3  pop     rdi
0x1800066f4  pop     rsi
0x1800066f5  pop     rbp
0x1800066f6  pop     rbx
0x1800066f7  retn
0x1800066f8  mov     ecx, 0Bh; dwErrCode
0x1800066fd  call    cs:__imp_SetLastError
0x180006703  xor     eax, eax
0x180006705  jmp     short loc_1800066EF
0x180006707  mov     rcx, [rcx+10h]; hObject
0x18000670b  lea     rax, [rcx-1]
0x18000670f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006713  ja      short loc_1800066A8
0x180006715  call    cs:__imp_CloseHandle
0x18000671b  mov     [rdi+10h], rbp
0x18000671f  jmp     short loc_1800066A8
```
