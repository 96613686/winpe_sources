# ParseCommandLine(int &)

- ea: `0x1400183c4`
- end: `0x1400184c4`
- name: `?ParseCommandLine@@YAHAEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002e680`

## callees

- `0x1400183c4`
- `0x1400184cc`
- `0x14001855c`
- `0x14002b2e8`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400183d6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400183d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140018433`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001845c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140018485`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140018433`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14001845c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140018485`

## pseudocode

```c
__int64 __fastcall ParseCommandLine(int *a1)
{
  unsigned int v1; // ebx
  wchar_t *CommandLineW; // rax
  wchar_t **v4; // r8
  wchar_t **v5; // r8
  wchar_t *i; // rax
  const WCHAR *v7; // rdi
  wchar_t **v8; // r8

  v1 = 0;
  *a1 = 0;
  CommandLineW = GetCommandLineW();
  if ( CommandLineW )
  {
    wcstok_mvcrt_legacy_two_parameter_form(CommandLineW, L" \t", v4);
    for ( i = wcstok_mvcrt_legacy_two_parameter_form(0, L" \t", v5);
          ;
          i = wcstok_mvcrt_legacy_two_parameter_form(0, L" \t", v8) )
    {
      v7 = i;
      if ( !i )
        break;
      if ( CompareStringW(0x7Fu, 1u, i, -1, L"/RegServer", -1) == 2 )
      {
        v1 = 1;
        DllRegisterServer();
        return v1;
      }
      if ( CompareStringW(0x7Fu, 1u, v7, -1, L"/UnRegServer", -1) == 2 )
      {
        v1 = 1;
        DllUnregisterServer();
        return v1;
      }
      if ( CompareStringW(0x7Fu, 1u, v7, -1, L"-secured", -1) == 2 )
        *a1 = 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400183c4  push    rbx
0x1400183c6  push    rbp
0x1400183c7  push    rsi
0x1400183c8  push    rdi
0x1400183c9  push    r14
0x1400183cb  sub     rsp, 30h
0x1400183cf  xor     ebx, ebx
0x1400183d1  mov     rsi, rcx
0x1400183d4  mov     [rcx], ebx
0x1400183d6  call    cs:__imp_GetCommandLineW
0x1400183dc  test    rax, rax
0x1400183df  jz      loc_1400184AE
0x1400183e5  lea     rdx, Delimiter; " \t"
0x1400183ec  mov     rcx, rax; String
0x1400183ef  call    wcstok_mvcrt_legacy_two_parameter_form
0x1400183f4  lea     rdx, Delimiter; " \t"
0x1400183fb  xor     ecx, ecx; String
0x1400183fd  call    wcstok_mvcrt_legacy_two_parameter_form
0x140018402  or      r14d, 0FFFFFFFFh
0x140018406  lea     ebp, [rbx+1]
0x140018409  mov     rdi, rax
0x14001840c  test    rax, rax
0x14001840f  jz      loc_1400184AE
0x140018415  lea     rax, String2; "/RegServer"
0x14001841c  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x140018421  mov     r9d, r14d; cchCount1
0x140018424  mov     [rsp+58h+lpString2], rax; lpString2
0x140018429  mov     r8, rdi; lpString1
0x14001842c  mov     edx, ebp; dwCmpFlags
0x14001842e  mov     ecx, 7Fh; Locale
0x140018433  call    cs:__imp_CompareStringW
0x140018439  cmp     eax, 2
0x14001843c  jz      short loc_1400184BB
0x14001843e  lea     rax, aUnregserver; "/UnRegServer"
0x140018445  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x14001844a  mov     r9d, r14d; cchCount1
0x14001844d  mov     [rsp+58h+lpString2], rax; lpString2
0x140018452  mov     r8, rdi; lpString1
0x140018455  mov     edx, ebp; dwCmpFlags
0x140018457  mov     ecx, 7Fh; Locale
0x14001845c  call    cs:__imp_CompareStringW
0x140018462  cmp     eax, 2
0x140018465  jz      short loc_1400184A7
0x140018467  lea     rax, aSecured; "-secured"
0x14001846e  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x140018473  mov     r9d, r14d; cchCount1
0x140018476  mov     [rsp+58h+lpString2], rax; lpString2
0x14001847b  mov     r8, rdi; lpString1
0x14001847e  mov     edx, ebp; dwCmpFlags
0x140018480  mov     ecx, 7Fh; Locale
0x140018485  call    cs:__imp_CompareStringW
0x14001848b  cmp     eax, 2
0x14001848e  jz      short loc_1400184A3
0x140018490  lea     rdx, Delimiter; " \t"
0x140018497  xor     ecx, ecx; String
0x140018499  call    wcstok_mvcrt_legacy_two_parameter_form
0x14001849e  jmp     loc_140018409
0x1400184a3  mov     [rsi], ebp
0x1400184a5  jmp     short loc_140018490
0x1400184a7  mov     ebx, ebp
0x1400184a9  call    DllUnregisterServer
0x1400184ae  mov     eax, ebx
0x1400184b0  add     rsp, 30h
0x1400184b4  pop     r14
0x1400184b6  pop     rdi
0x1400184b7  pop     rsi
0x1400184b8  pop     rbp
0x1400184b9  pop     rbx
0x1400184ba  retn
0x1400184bb  mov     ebx, ebp
0x1400184bd  call    DllRegisterServer
0x1400184c2  jmp     short loc_1400184AE
```
