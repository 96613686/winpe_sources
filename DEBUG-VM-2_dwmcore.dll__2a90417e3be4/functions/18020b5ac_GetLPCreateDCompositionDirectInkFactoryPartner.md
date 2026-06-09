# GetLPCreateDCompositionDirectInkFactoryPartner

- ea: `0x18020b5ac`
- end: `0x18020b688`
- name: `GetLPCreateDCompositionDirectInkFactoryPartner`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18020b51c`

## callees

- `0x180042de0`
- `0x18020b5ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18020b629`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18020b629`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b5ed`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18020b5e2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18020b5e2`

## string_xrefs

- `0x18020b5db`: `Windows.UI.Input.Inking.dll`
- `0x18020b61f`: `CreateDCompositionDirectInkFactoryPartner`

## pseudocode

```c
__int64 __fastcall GetLPCreateDCompositionDirectInkFactoryPartner(FARPROC *a1)
{
  signed int v1; // ebx
  FARPROC ProcAddress; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-18h]

  v1 = dword_1803BF080;
  if ( dword_1803BF080 < 0 )
  {
    v7 = 24;
LABEL_13:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, v7, 0);
    goto LABEL_14;
  }
  ProcAddress = (FARPROC)qword_1803BF078;
  if ( qword_1803BF078 )
    goto LABEL_11;
  SetLastError(0);
  LibraryW = LoadLibraryW(L"Windows.UI.Input.Inking.dll");
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v7 = 29;
    if ( v1 >= 0 )
      v1 = -2003304445;
    goto LABEL_13;
  }
  ProcAddress = GetProcAddress(LibraryW, "CreateDCompositionDirectInkFactoryPartner");
  qword_1803BF078 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_11:
    *a1 = ProcAddress;
  }
  else
  {
    v1 = -2147467261;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147467261, 0x23u, 0);
  }
LABEL_14:
  dword_1803BF080 = v1;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18020b5ac  mov     [rsp+arg_0], rbx
0x18020b5b1  push    rdi
0x18020b5b2  sub     rsp, 30h
0x18020b5b6  mov     ebx, cs:dword_1803BF080
0x18020b5bc  mov     rdi, rcx
0x18020b5bf  test    ebx, ebx
0x18020b5c1  js      loc_18020B654
0x18020b5c7  mov     rax, cs:qword_1803BF078
0x18020b5ce  test    rax, rax
0x18020b5d1  jnz     short loc_18020B64F
0x18020b5d3  xor     ecx, ecx; dwErrCode
0x18020b5d5  call    cs:__imp_SetLastError
0x18020b5db  lea     rcx, aWindowsUiInput; "Windows.UI.Input.Inking.dll"
0x18020b5e2  call    cs:__imp_LoadLibraryW
0x18020b5e8  test    rax, rax
0x18020b5eb  jnz     short loc_18020B61F
0x18020b5ed  call    cs:__imp_GetLastError
0x18020b5f3  mov     ebx, eax
0x18020b5f5  test    eax, eax
0x18020b5f7  jle     short loc_18020B602
0x18020b5f9  movzx   ebx, ax
0x18020b5fc  or      ebx, 80070000h
0x18020b602  test    ebx, ebx
0x18020b604  mov     [rsp+38h+var_10], 0
0x18020b60d  mov     eax, 88980003h
0x18020b612  mov     [rsp+38h+var_18], 1Dh
0x18020b61a  cmovns  ebx, eax
0x18020b61d  jmp     short loc_18020B665
0x18020b61f  lea     rdx, aCreatedcomposi; "CreateDCompositionDirectInkFactoryPartn"...
0x18020b626  mov     rcx, rax; hModule
0x18020b629  call    cs:__imp_GetProcAddress
0x18020b62f  mov     cs:qword_1803BF078, rax
0x18020b636  test    rax, rax
0x18020b639  jnz     short loc_18020B64F
0x18020b63b  mov     [rsp+38h+var_10], rax
0x18020b640  mov     ebx, 80004003h
0x18020b645  mov     [rsp+38h+var_18], 23h ; '#'
0x18020b64d  jmp     short loc_18020B665
0x18020b64f  mov     [rdi], rax
0x18020b652  jmp     short loc_18020B675
0x18020b654  mov     [rsp+38h+var_10], 0; void *
0x18020b65d  mov     [rsp+38h+var_18], 18h; unsigned int
0x18020b665  xor     edx, edx; int *
0x18020b667  mov     r9d, ebx; int
0x18020b66a  xor     r8d, r8d; unsigned int
0x18020b66d  lea     ecx, [rdx+14h]; unsigned int
0x18020b670  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18020b675  mov     cs:dword_1803BF080, ebx
0x18020b67b  mov     eax, ebx
0x18020b67d  mov     rbx, [rsp+38h+arg_0]
0x18020b682  add     rsp, 30h
0x18020b686  pop     rdi
0x18020b687  retn
```
