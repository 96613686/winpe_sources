# HrCreatePhonebookEntry

- ea: `0x18000d040`
- end: `0x18000d127`
- name: `HrCreatePhonebookEntry`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d040`
- `0x180012f8e`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d0d5`
- `KERNEL32!GetLastError` at `0x18000d0e8`
- `KERNEL32!GetLastError` at `0x18000d0d5`
- `KERNEL32!GetLastError` at `0x18000d0e8`
- `KERNEL32!LoadLibraryA` at `0x18000d06e`
- `KERNEL32!LoadLibraryA` at `0x18000d06e`
- `KERNEL32!GetProcAddress` at `0x18000d086`
- `KERNEL32!GetProcAddress` at `0x18000d086`
- `KERNEL32!FreeLibrary` at `0x18000d0e0`
- `KERNEL32!FreeLibrary` at `0x18000d0e0`

## string_xrefs

- `0x18000d067`: `rasdlg.dll`

## pseudocode

```c
__int64 __fastcall HrCreatePhonebookEntry(__int64 a1, DWORD *a2)
{
  HMODULE LibraryA; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rbx
  DWORD LastError; // ebx
  int v9; // [rsp+20h] [rbp-258h] BYREF
  __int64 v10; // [rsp+24h] [rbp-254h]
  int v11; // [rsp+2Ch] [rbp-24Ch]
  _BYTE v12[524]; // [rsp+30h] [rbp-248h] BYREF
  DWORD v13; // [rsp+23Ch] [rbp-3Ch]

  LibraryA = LoadLibraryA("rasdlg.dll");
  v5 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "RasEntryDlgW");
    if ( ProcAddress )
    {
      memset_0(v12, 0, 0x220u);
      v9 = 560;
      v10 = a1;
      v11 = 2;
      ((void (__fastcall *)(_QWORD, _QWORD, int *))ProcAddress)(0, 0, &v9);
      LastError = v13;
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
    return 0;
  if ( a2 )
    *a2 = LastError;
  return 2148322500LL;
}

```

## disassembly

```asm
0x18000d040  mov     [rsp+arg_10], rbx
0x18000d045  push    rbp
0x18000d046  push    rsi
0x18000d047  push    rdi
0x18000d048  sub     rsp, 260h
0x18000d04f  mov     rax, cs:__security_cookie
0x18000d056  xor     rax, rsp
0x18000d059  mov     [rsp+278h+var_28], rax
0x18000d061  mov     rbp, rcx
0x18000d064  mov     rsi, rdx
0x18000d067  lea     rcx, aRasdlgDll; "rasdlg.dll"
0x18000d06e  call    cs:__imp_LoadLibraryA
0x18000d074  mov     rdi, rax
0x18000d077  test    rax, rax
0x18000d07a  jz      short loc_18000D0E8
0x18000d07c  lea     rdx, ProcName; "RasEntryDlgW"
0x18000d083  mov     rcx, rax; hModule
0x18000d086  call    cs:__imp_GetProcAddress
0x18000d08c  mov     rbx, rax
0x18000d08f  test    rax, rax
0x18000d092  jz      short loc_18000D0D5
0x18000d094  xor     edx, edx; Val
0x18000d096  lea     rcx, [rsp+278h+var_248]; void *
0x18000d09b  mov     r8d, 220h; Size
0x18000d0a1  call    memset_0
0x18000d0a6  lea     r8, [rsp+278h+var_258]
0x18000d0ab  mov     [rsp+278h+var_258], 230h
0x18000d0b3  xor     edx, edx
0x18000d0b5  mov     [rsp+278h+var_254], rbp
0x18000d0ba  xor     ecx, ecx
0x18000d0bc  mov     [rsp+278h+var_24C], 2
0x18000d0c4  mov     rax, rbx
0x18000d0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0cc  mov     ebx, [rsp+278h+var_3C]
0x18000d0d3  jmp     short loc_18000D0DD
0x18000d0d5  call    cs:__imp_GetLastError
0x18000d0db  mov     ebx, eax
0x18000d0dd  mov     rcx, rdi; hLibModule
0x18000d0e0  call    cs:__imp_FreeLibrary
0x18000d0e6  jmp     short loc_18000D0F0
0x18000d0e8  call    cs:__imp_GetLastError
0x18000d0ee  mov     ebx, eax
0x18000d0f0  test    ebx, ebx
0x18000d0f2  jz      short loc_18000D102
0x18000d0f4  test    rsi, rsi
0x18000d0f7  jz      short loc_18000D0FB
0x18000d0f9  mov     [rsi], ebx
0x18000d0fb  mov     eax, 800CCCC4h
0x18000d100  jmp     short loc_18000D104
0x18000d102  xor     eax, eax
0x18000d104  mov     rcx, [rsp+278h+var_28]
0x18000d10c  xor     rcx, rsp; StackCookie
0x18000d10f  call    __security_check_cookie
0x18000d114  mov     rbx, [rsp+278h+arg_10]
0x18000d11c  add     rsp, 260h
0x18000d123  pop     rdi
0x18000d124  pop     rsi
0x18000d125  pop     rbp
0x18000d126  retn
```
