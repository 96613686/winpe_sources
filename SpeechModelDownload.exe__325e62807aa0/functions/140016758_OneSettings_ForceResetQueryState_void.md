# OneSettings::ForceResetQueryState(void)

- ea: `0x140016758`
- end: `0x1400168ac`
- name: `?ForceResetQueryState@OneSettings@@QEAAJXZ`
- size: `340`
- prototype: `__int64 __fastcall(OneSettings *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140013ac0`

## callees

- `0x140007dc8`
- `0x140015794`
- `0x140016758`
- `0x140018bcc`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400167c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400167c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400167ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001688f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400167ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001688f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001680d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001680d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016868`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016848`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016859`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016848`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016859`

## pseudocode

```c
__int64 __fastcall OneSettings::ForceResetQueryState(OneSettings *this)
{
  unsigned int v2; // edi
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  void *v10; // rbx
  HANDLE v11; // rax
  int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  _BYTE v14[16]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-40h]
  char v16; // [rsp+48h] [rbp-38h]
  _BYTE v17[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  HKEY hKey; // [rsp+90h] [rbp+10h] BYREF

  (*(void (__fastcall **)(char *, _BYTE *))(*((_QWORD *)this + 27) + 112LL))((char *)this + 216, v14);
  if ( !*((_DWORD *)this + 176) )
  {
    v2 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)0x8007139FLL,
      phkResult);
LABEL_3:
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v17);
    if ( v16 )
    {
      v3 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    return v2;
  }
  v6 = (const WCHAR *)((char *)this + 128);
  hKey = 0;
  if ( *((_QWORD *)this + 19) > 7u )
    v6 = *(const WCHAR **)v6;
  v7 = RegOpenKeyExW(*((HKEY *)this + 20), v6, 0, 0xF003Fu, &hKey);
  if ( v7 )
  {
    v2 = wil::details::in1diag3::Return_Win32(retaddr, v8, v9, (const char *)v7, phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_3;
  }
  RegDeleteValueW(hKey, L"ETag");
  RegDeleteValueW(hKey, L"RefreshAfter");
  if ( hKey )
    RegCloseKey(hKey);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v17);
  if ( v16 )
  {
    v10 = lpMem;
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140016758  mov     [rsp-8+arg_8], rbx
0x14001675d  mov     [rsp-8+arg_10], rdi
0x140016762  push    rbp
0x140016763  mov     rbp, rsp
0x140016766  sub     rsp, 80h
0x14001676d  mov     rbx, rcx
0x140016770  lea     rdx, [rbp+var_50]
0x140016774  add     rcx, 0D8h
0x14001677b  mov     rax, [rcx]
0x14001677e  mov     rax, [rax+70h]
0x140016782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016787  cmp     dword ptr [rbx+2C0h], 0
0x14001678e  jnz     short loc_1400167DB
0x140016790  mov     rcx, [rbp+8]; this
0x140016794  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x14001679b  mov     edi, 8007139Fh
0x1400167a0  mov     edx, 166h; void *
0x1400167a5  mov     r9d, edi; char *
0x1400167a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400167ad  lea     rcx, [rbp+var_30]; this
0x1400167b1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1400167b6  cmp     [rbp+var_38], 0
0x1400167ba  jz      short loc_1400167D4
0x1400167bc  mov     rbx, [rbp+lpMem]
0x1400167c0  call    cs:__imp_GetProcessHeap
0x1400167c6  mov     r8, rbx; lpMem
0x1400167c9  xor     edx, edx; dwFlags
0x1400167cb  mov     rcx, rax; hHeap
0x1400167ce  call    cs:__imp_HeapFree
0x1400167d4  mov     eax, edi
0x1400167d6  jmp     loc_140016897
0x1400167db  lea     rdx, [rbx+80h]
0x1400167e2  mov     [rbp+hKey], 0
0x1400167ea  cmp     qword ptr [rdx+18h], 7
0x1400167ef  jbe     short loc_1400167F4
0x1400167f1  mov     rdx, [rdx]; lpSubKey
0x1400167f4  mov     rcx, [rbx+0A0h]; hKey
0x1400167fb  lea     rax, [rbp+hKey]
0x1400167ff  mov     r9d, 0F003Fh; samDesired
0x140016805  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x14001680a  xor     r8d, r8d; ulOptions
0x14001680d  call    cs:__imp_RegOpenKeyExW
0x140016813  test    eax, eax
0x140016815  jz      short loc_14001683D
0x140016817  mov     rcx, [rbp+8]; this
0x14001681b  mov     r9d, eax; char *
0x14001681e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016823  mov     rcx, [rbp+hKey]; hKey
0x140016827  mov     edi, eax
0x140016829  test    rcx, rcx
0x14001682c  jz      loc_1400167AD
0x140016832  call    cs:__imp_RegCloseKey
0x140016838  jmp     loc_1400167AD
0x14001683d  mov     rcx, [rbp+hKey]; hKey
0x140016841  lea     rdx, aEtag; "ETag"
0x140016848  call    cs:__imp_RegDeleteValueW
0x14001684e  mov     rcx, [rbp+hKey]; hKey
0x140016852  lea     rdx, aRefreshafter; "RefreshAfter"
0x140016859  call    cs:__imp_RegDeleteValueW
0x14001685f  mov     rcx, [rbp+hKey]; hKey
0x140016863  test    rcx, rcx
0x140016866  jz      short loc_14001686E
0x140016868  call    cs:__imp_RegCloseKey
0x14001686e  lea     rcx, [rbp+var_30]; this
0x140016872  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140016877  cmp     [rbp+var_38], 0
0x14001687b  jz      short loc_140016895
0x14001687d  mov     rbx, [rbp+lpMem]
0x140016881  call    cs:__imp_GetProcessHeap
0x140016887  mov     r8, rbx; lpMem
0x14001688a  xor     edx, edx; dwFlags
0x14001688c  mov     rcx, rax; hHeap
0x14001688f  call    cs:__imp_HeapFree
0x140016895  xor     eax, eax
0x140016897  lea     r11, [rsp+80h+var_s0]
0x14001689f  mov     rbx, [r11+18h]
0x1400168a3  mov     rdi, [r11+20h]
0x1400168a7  mov     rsp, r11
0x1400168aa  pop     rbp
0x1400168ab  retn
```
