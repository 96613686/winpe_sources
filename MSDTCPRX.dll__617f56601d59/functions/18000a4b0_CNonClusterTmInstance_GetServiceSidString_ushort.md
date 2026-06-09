# CNonClusterTmInstance::GetServiceSidString(ushort * *)

- ea: `0x18000a4b0`
- end: `0x18000a5ae`
- name: `?GetServiceSidString@CNonClusterTmInstance@@UEAAJPEAPEAG@Z`
- size: `254`
- prototype: `__int64 __fastcall(CNonClusterTmInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a4b0`
- `0x18000d5f4`
- `0x18001156c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a4d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a561`

## string_xrefs

- `0x18000a4f1`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18000a57c`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18000a583`: `DuplicateString, StringCchCopyW failed`
- `0x18000a4c3`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@100): DuplicateString, ppwszDest != NULL`
- `0x18000a4f8`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::GetServiceSidString(CNonClusterTmInstance *this, unsigned __int16 **a2)
{
  void *v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r8
  _WORD *v9; // rcx
  signed int LastError; // eax

  if ( !a2 )
    DtcInternalErrorW(L"DuplicateString (com\\complus\\dtc\\shared\\util\\stringutil.cpp@100): DuplicateString, ppwszDest != NULL");
  *a2 = 0;
  v3 = CoTaskMemAlloc(0x80u);
  if ( !v3 )
  {
    v4 = -2147024882;
    TraceFileW(
      -2147024882,
      L"DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed",
      L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
      0x70u);
LABEL_15:
    CoTaskMemFree(v3);
    return v4;
  }
  v5 = 2147483646;
  v6 = L"S-1-5-80-3960419045-2460139048-4046793004-1809597027-2250574426";
  v7 = 64;
  v8 = v3;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  v4 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  if ( v7 )
  {
    *a2 = (unsigned __int16 *)v3;
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  TraceFileW(v4, L"DuplicateString, StringCchCopyW failed", L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", 0x77u);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_15;
  return v4;
}

```

## disassembly

```asm
0x18000a4b0  push    rbx
0x18000a4b2  push    rbp
0x18000a4b3  push    rsi
0x18000a4b4  push    rdi
0x18000a4b5  sub     rsp, 28h
0x18000a4b9  xor     ebp, ebp
0x18000a4bb  mov     rsi, rdx
0x18000a4be  test    rdx, rdx
0x18000a4c1  jnz     short loc_18000A4D0
0x18000a4c3  lea     rcx, aDuplicatestrin_6; "DuplicateString (com\\complus\\dtc\\sha"...
0x18000a4ca  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000a4d0  mov     ecx, 80h; cb
0x18000a4d5  mov     [rdx], rbp
0x18000a4d8  call    cs:__imp_CoTaskMemAlloc
0x18000a4de  mov     rdi, rax
0x18000a4e1  test    rax, rax
0x18000a4e4  jnz     short loc_18000A509
0x18000a4e6  mov     ebx, 8007000Eh
0x18000a4eb  lea     r9d, [rax+70h]; unsigned int
0x18000a4ef  mov     ecx, ebx; int
0x18000a4f1  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18000a4f8  lea     rdx, aDuplicatestrin_3; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x18000a4ff  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18000a504  jmp     loc_18000A595
0x18000a509  mov     eax, 7FFFFFFEh
0x18000a50e  lea     rcx, aS1580396041904; "S-1-5-80-3960419045-2460139048-40467930"...
0x18000a515  mov     edx, 40h ; '@'
0x18000a51a  mov     r8, rdi
0x18000a51d  test    rax, rax
0x18000a520  jz      short loc_18000A541
0x18000a522  movzx   r9d, word ptr [rcx]
0x18000a526  test    r9w, r9w
0x18000a52a  jz      short loc_18000A541
0x18000a52c  mov     [r8], r9w
0x18000a530  add     rcx, 2
0x18000a534  add     r8, 2
0x18000a538  dec     rax
0x18000a53b  sub     rdx, 1
0x18000a53f  jnz     short loc_18000A51D
0x18000a541  mov     rax, rdx
0x18000a544  lea     rcx, [r8-2]
0x18000a548  neg     rax
0x18000a54b  sbb     ebx, ebx
0x18000a54d  not     ebx
0x18000a54f  and     ebx, 8007007Ah
0x18000a555  test    rdx, rdx
0x18000a558  cmovnz  rcx, r8
0x18000a55c  mov     [rcx], bp
0x18000a55f  jnz     short loc_18000A5A0
0x18000a561  call    cs:__imp_GetLastError
0x18000a567  mov     ebx, eax
0x18000a569  test    eax, eax
0x18000a56b  jle     short loc_18000A576
0x18000a56d  movzx   ebx, ax
0x18000a570  or      ebx, 80070000h
0x18000a576  mov     r9d, 77h ; 'w'; unsigned int
0x18000a57c  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18000a583  lea     rdx, aDuplicatestrin_4; "DuplicateString, StringCchCopyW failed"
0x18000a58a  mov     ecx, ebx; int
0x18000a58c  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18000a591  test    ebx, ebx
0x18000a593  jns     short loc_18000A5A3
0x18000a595  mov     rcx, rdi; pv
0x18000a598  call    cs:__imp_CoTaskMemFree
0x18000a59e  jmp     short loc_18000A5A3
0x18000a5a0  mov     [rsi], rdi
0x18000a5a3  mov     eax, ebx
0x18000a5a5  add     rsp, 28h
0x18000a5a9  pop     rdi
0x18000a5aa  pop     rsi
0x18000a5ab  pop     rbp
0x18000a5ac  pop     rbx
0x18000a5ad  retn
```
