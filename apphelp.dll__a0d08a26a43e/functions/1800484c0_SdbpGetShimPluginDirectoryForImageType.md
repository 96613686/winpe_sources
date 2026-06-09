# SdbpGetShimPluginDirectoryForImageType

- ea: `0x1800484c0`
- end: `0x180048660`
- name: `SdbpGetShimPluginDirectoryForImageType`
- size: `416`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x18004842c`

## callees

- `0x1800159e0`
- `0x180018f20`
- `0x180034420`
- `0x1800484c0`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x180048617`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180048617`
- `ntdll!RtlAllocateHeap` at `0x180048589`
- `ntdll!RtlAllocateHeap` at `0x180048589`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048502`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800484e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800484e3`

## string_xrefs

- `0x1800484dc`: `kernel32.dll`
- `0x1800485ef`: `%windir%\apppatch\AcPluginDlls\Plugin\`
- `0x1800485e6`: `%windir%\apppatch\AcPluginDlls\PluginWowX86\`
- `0x1800485d4`: `%windir%\apppatch\AcPluginDlls\PluginWowAMD64\`
- `0x1800485dd`: `%windir%\apppatch\AcPluginDlls\PluginWowARM\`
- `0x1800485cb`: `%windir%\apppatch\AcPluginDlls\PluginWowARM64\`
- `0x1800485a1`: `%windir%\apppatch\AcPluginDlls\PluginWow`

## pseudocode

```c
__int64 __fastcall SdbpGetShimPluginDirectoryForImageType(PCWSTR SourceString, __int64 a2, unsigned __int16 a3)
{
  unsigned __int16 v3; // bx
  HMODULE ModuleHandleA; // rax
  int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax
  unsigned int v9; // eax
  void *v10; // rdi
  PVOID Heap; // rax
  const wchar_t *v12; // rdx
  __int64 v13; // r8
  int v15; // [rsp+70h] [rbp+18h] BYREF

  v3 = a3;
  v15 = 0;
  if ( a3 )
  {
    ModuleHandleA = GetModuleHandleA("kernel32.dll");
    if ( !ModuleHandleA )
      return (unsigned int)-1073741275;
    ProcAddress = GetProcAddress(ModuleHandleA, "GetMachineTypeAttributes");
    if ( !ProcAddress )
      return (unsigned int)-1073741275;
    v8 = ((__int64 (__fastcall *)(_QWORD, int *))ProcAddress)(v3, &v15);
    if ( v8 < 0 )
    {
      v6 = (unsigned __int16)v8;
      v9 = (unsigned __int16)v8 | 0xC0070000;
      if ( v6 )
        return v9;
      return (unsigned int)v6;
    }
    if ( (v15 & 1) == 0 )
      return (unsigned int)-1073741275;
    if ( (v15 & 4) == 0 )
      v3 = 0;
  }
  v10 = 0;
  if ( v3 )
  {
    switch ( v3 )
    {
      case 0x14Cu:
        v12 = L"%windir%\\apppatch\\AcPluginDlls\\PluginWowX86\\";
        break;
      case 0x1C4u:
        v12 = L"%windir%\\apppatch\\AcPluginDlls\\PluginWowARM\\";
        break;
      case 0x8664u:
        v12 = L"%windir%\\apppatch\\AcPluginDlls\\PluginWowAMD64\\";
        break;
      case 0xAA64u:
        v12 = L"%windir%\\apppatch\\AcPluginDlls\\PluginWowARM64\\";
        break;
      default:
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x5Eu);
        v10 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        v6 = RtlStringCchPrintfW(Heap, 47, L"%ls0x%hX\\", L"%windir%\\apppatch\\AcPluginDlls\\PluginWow", v3);
        if ( v6 < 0 )
        {
LABEL_33:
          AslFree(NtCurrentPeb()->ProcessHeap, v10);
          return (unsigned int)v6;
        }
        v12 = (const wchar_t *)v10;
        break;
    }
  }
  else
  {
    v12 = L"%windir%\\apppatch\\AcPluginDlls\\Plugin\\";
  }
  v13 = -1;
  do
    ++v13;
  while ( v12[v13] );
  v6 = RtlExpandEnvironmentStrings(0, v12, v13, SourceString, 260, 0);
  if ( v6 >= 0 )
  {
    if ( (unsigned int)AslDoesDirectoryExistNtPath(SourceString) )
    {
      v6 = 0;
    }
    else
    {
      v6 = -1073741766;
      *SourceString = 0;
    }
  }
  if ( v10 )
    goto LABEL_33;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800484c0  push    rbx
0x1800484c2  push    rbp
0x1800484c3  push    rsi
0x1800484c4  push    rdi
0x1800484c5  sub     rsp, 38h
0x1800484c9  xor     ebp, ebp
0x1800484cb  movzx   ebx, r8w
0x1800484cf  mov     [rsp+58h+arg_10], ebp
0x1800484d3  mov     rsi, rcx
0x1800484d6  test    r8w, r8w
0x1800484da  jz      short loc_180048542
0x1800484dc  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x1800484e3  call    cs:__imp_GetModuleHandleA
0x1800484e9  test    rax, rax
0x1800484ec  jnz     short loc_1800484F8
0x1800484ee  mov     ebx, 0C0000225h
0x1800484f3  jmp     loc_180048655
0x1800484f8  lea     rdx, aGetmachinetype; "GetMachineTypeAttributes"
0x1800484ff  mov     rcx, rax; hModule
0x180048502  call    cs:__imp_GetProcAddress
0x180048508  test    rax, rax
0x18004850b  jz      short loc_1800484EE
0x18004850d  lea     rdx, [rsp+58h+arg_10]
0x180048512  movzx   ecx, bx
0x180048515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004851a  test    eax, eax
0x18004851c  jns     short loc_180048532
0x18004851e  movzx   ebx, ax
0x180048521  mov     eax, ebx
0x180048523  or      eax, 0C0070000h
0x180048528  test    ebx, ebx
0x18004852a  cmovnz  ebx, eax
0x18004852d  jmp     loc_180048655
0x180048532  mov     ecx, [rsp+58h+arg_10]
0x180048536  test    cl, 1
0x180048539  jz      short loc_1800484EE
0x18004853b  test    cl, 4
0x18004853e  jnz     short loc_180048542
0x180048540  mov     ebx, ebp
0x180048542  movzx   ebx, bx
0x180048545  mov     rdi, rbp
0x180048548  mov     ecx, ebx
0x18004854a  test    ebx, ebx
0x18004854c  jz      loc_1800485EF
0x180048552  sub     ecx, 14Ch
0x180048558  jz      loc_1800485E6
0x18004855e  sub     ecx, 78h ; 'x'
0x180048561  jz      short loc_1800485DD
0x180048563  sub     ecx, 84A0h
0x180048569  jz      short loc_1800485D4
0x18004856b  cmp     ecx, 2400h
0x180048571  jz      short loc_1800485CB
0x180048573  mov     rcx, gs:60h
0x18004857c  mov     edx, 8; Flags
0x180048581  mov     rcx, [rcx+30h]; HeapHandle
0x180048585  lea     r8d, [rdx+56h]; Size
0x180048589  call    cs:__imp_RtlAllocateHeap
0x18004858f  mov     rdi, rax
0x180048592  test    rax, rax
0x180048595  jnz     short loc_1800485A1
0x180048597  mov     ebx, 0C0000017h
0x18004859c  jmp     loc_180048655
0x1800485a1  lea     r9, aWindirApppatch_3; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485a8  mov     dword ptr [rsp+58h+var_38], ebx
0x1800485ac  lea     r8, aLs0xHx; "%ls0x%hX\\"
0x1800485b3  mov     edx, 2Fh ; '/'
0x1800485b8  mov     rcx, rdi
0x1800485bb  call    RtlStringCchPrintfW
0x1800485c0  mov     ebx, eax
0x1800485c2  test    eax, eax
0x1800485c4  js      short loc_180048640
0x1800485c6  mov     rdx, rdi
0x1800485c9  jmp     short loc_1800485F6
0x1800485cb  lea     rdx, aWindirApppatch_1; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485d2  jmp     short loc_1800485F6
0x1800485d4  lea     rdx, aWindirApppatch_4; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485db  jmp     short loc_1800485F6
0x1800485dd  lea     rdx, aWindirApppatch_0; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485e4  jmp     short loc_1800485F6
0x1800485e6  lea     rdx, aWindirApppatch; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485ed  jmp     short loc_1800485F6
0x1800485ef  lea     rdx, aWindirApppatch_2; "%windir%\\apppatch\\AcPluginDlls\\Plugi"...
0x1800485f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800485fa  inc     r8
0x1800485fd  cmp     [rdx+r8*2], bp
0x180048602  jnz     short loc_1800485FA
0x180048604  mov     [rsp+58h+var_30], rbp
0x180048609  mov     r9, rsi
0x18004860c  xor     ecx, ecx
0x18004860e  mov     [rsp+58h+var_38], 104h
0x180048617  call    cs:__imp_RtlExpandEnvironmentStrings
0x18004861d  mov     ebx, eax
0x18004861f  test    eax, eax
0x180048621  js      short loc_18004863B
0x180048623  mov     rcx, rsi; SourceString
0x180048626  call    AslDoesDirectoryExistNtPath
0x18004862b  test    eax, eax
0x18004862d  jnz     short loc_180048639
0x18004862f  mov     ebx, 0C000003Ah
0x180048634  mov     [rsi], bp
0x180048637  jmp     short loc_18004863B
0x180048639  mov     ebx, ebp
0x18004863b  test    rdi, rdi
0x18004863e  jz      short loc_180048655
0x180048640  mov     rcx, gs:60h
0x180048649  mov     rdx, rdi
0x18004864c  mov     rcx, [rcx+30h]
0x180048650  call    AslFree
0x180048655  mov     eax, ebx
0x180048657  add     rsp, 38h
0x18004865b  pop     rdi
0x18004865c  pop     rsi
0x18004865d  pop     rbp
0x18004865e  pop     rbx
0x18004865f  retn
```
