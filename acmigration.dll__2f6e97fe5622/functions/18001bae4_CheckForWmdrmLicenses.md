# _CheckForWmdrmLicenses

- ea: `0x18001bae4`
- end: `0x18001bb5a`
- name: `_CheckForWmdrmLicenses`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ba90`
- `0x18001bab0`
- `0x18001bad0`

## callees

- `0x18001bae4`
- `0x18006a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001bb30`
- `KERNEL32!FreeLibrary` at `0x18001bb30`
- `KERNEL32!LoadLibraryExW` at `0x18001bafe`
- `KERNEL32!LoadLibraryExW` at `0x18001bafe`
- `KERNEL32!GetProcAddress` at `0x18001bb1b`
- `KERNEL32!GetProcAddress` at `0x18001bb1b`

## string_xrefs

- `0x18001baf4`: `Microsoft.Media.PlayReady.Appraiser.dll`

## pseudocode

```c
__int64 __fastcall CheckForWmdrmLicenses(int a1, _DWORD *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rsi
  int v6; // ebx
  __int64 (*ProcAddress)(void); // rax
  __int64 result; // rax

  Library = LoadLibraryExW(L"Microsoft.Media.PlayReady.Appraiser.dll", 0, 0);
  v5 = Library;
  if ( !Library )
    goto LABEL_7;
  v6 = -2147467259;
  ProcAddress = GetProcAddress(Library, "CheckForWmdrmLicenses");
  if ( ProcAddress )
    v6 = ProcAddress();
  FreeLibrary(v5);
  if ( v6 >= 0 )
  {
    result = 1;
    if ( (a1 & v6) == a1 )
    {
      *a2 = 1;
      return result;
    }
  }
  else
  {
LABEL_7:
    result = 0;
  }
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18001bae4  push    rbx
0x18001bae6  push    rbp
0x18001bae7  push    rsi
0x18001bae8  push    rdi
0x18001bae9  sub     rsp, 28h
0x18001baed  mov     rdi, rdx
0x18001baf0  mov     ebp, ecx
0x18001baf2  xor     edx, edx; hFile
0x18001baf4  lea     rcx, aMicrosoftMedia; "Microsoft.Media.PlayReady.Appraiser.dll"
0x18001bafb  xor     r8d, r8d; dwFlags
0x18001bafe  call    cs:__imp_LoadLibraryExW
0x18001bb04  mov     rsi, rax
0x18001bb07  test    rax, rax
0x18001bb0a  jz      short loc_18001BB49
0x18001bb0c  lea     rdx, aCheckforwmdrml; "CheckForWmdrmLicenses"
0x18001bb13  mov     rcx, rax; hModule
0x18001bb16  mov     ebx, 80004005h
0x18001bb1b  call    cs:__imp_GetProcAddress
0x18001bb21  test    rax, rax
0x18001bb24  jz      short loc_18001BB2D
0x18001bb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb2b  mov     ebx, eax
0x18001bb2d  mov     rcx, rsi; hLibModule
0x18001bb30  call    cs:__imp_FreeLibrary
0x18001bb36  test    ebx, ebx
0x18001bb38  js      short loc_18001BB49
0x18001bb3a  and     ebx, ebp
0x18001bb3c  mov     eax, 1
0x18001bb41  cmp     ebx, ebp
0x18001bb43  jnz     short loc_18001BB4B
0x18001bb45  mov     [rdi], eax
0x18001bb47  jmp     short loc_18001BB51
0x18001bb49  xor     eax, eax
0x18001bb4b  mov     dword ptr [rdi], 0
0x18001bb51  add     rsp, 28h
0x18001bb55  pop     rdi
0x18001bb56  pop     rsi
0x18001bb57  pop     rbp
0x18001bb58  pop     rbx
0x18001bb59  retn
```
