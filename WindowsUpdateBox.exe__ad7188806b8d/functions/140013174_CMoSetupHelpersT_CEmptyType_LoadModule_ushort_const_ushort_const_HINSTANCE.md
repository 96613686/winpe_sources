# CMoSetupHelpersT<CEmptyType>::LoadModule(ushort const *,ushort const *,HINSTANCE__ * *)

- ea: `0x140013174`
- end: `0x140013282`
- name: `?LoadModule@?$CMoSetupHelpersT@VCEmptyType@@@@SAJPEBG0PEAPEAUHINSTANCE__@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, HMODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011268`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140013174`
- `0x1400135b8`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140013230`
- `KERNEL32!FreeLibrary` at `0x140013230`
- `KERNEL32!LoadLibraryExW` at `0x1400131e5`
- `KERNEL32!LoadLibraryExW` at `0x1400131e5`
- `KERNEL32!HeapFree` at `0x140013256`
- `KERNEL32!HeapFree` at `0x140013256`
- `KERNEL32!GetProcessHeap` at `0x140013241`
- `KERNEL32!GetProcessHeap` at `0x140013241`
- `KERNEL32!GetLastError` at `0x1400131f6`
- `KERNEL32!GetLastError` at `0x1400131f6`

## string_xrefs

- `0x1400131b8`: `ReserveManager.dll`

## pseudocode

```c
__int64 __fastcall CMoSetupHelpersT<CEmptyType>::LoadModule(__int64 a1, __int64 a2, HMODULE *a3)
{
  LPCWSTR v3; // rsi
  __int64 v5; // rcx
  unsigned int v6; // edi
  int v7; // eax
  HMODULE Library; // rax
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  lpLibFileName = 0;
  if ( !a1 || !a3 )
  {
    v5 = 2147942487LL;
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_14;
  }
  v7 = CMiscHelpersT<CEmptyType>::CombinePath(a1, L"ReserveManager.dll", 0, &lpLibFileName);
  v6 = v7;
  if ( v7 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v7);
    v3 = lpLibFileName;
    goto LABEL_14;
  }
  v3 = lpLibFileName;
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v5 = v6;
    goto LABEL_3;
  }
  *a3 = Library;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x140013174  mov     rax, rsp
0x140013177  mov     [rax+8], rbx
0x14001317b  mov     [rax+18h], rsi
0x14001317f  mov     [rax+20h], rdi
0x140013183  mov     [rax+10h], rdx
0x140013187  push    r14
0x140013189  sub     rsp, 20h
0x14001318d  xor     esi, esi
0x14001318f  xor     ebx, ebx
0x140013191  mov     [rax+10h], rsi
0x140013195  mov     r14, r8
0x140013198  test    rcx, rcx
0x14001319b  jnz     short loc_1400131AB
0x14001319d  mov     ecx, 80070057h
0x1400131a2  mov     edi, ecx
0x1400131a4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400131a9  jmp     short loc_140013221
0x1400131ab  test    r14, r14
0x1400131ae  jz      short loc_14001319D
0x1400131b0  lea     r9, [rsp+28h+lpLibFileName]
0x1400131b5  xor     r8d, r8d
0x1400131b8  lea     rdx, aReservemanager; "ReserveManager.dll"
0x1400131bf  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1400131c4  mov     edi, eax
0x1400131c6  test    eax, eax
0x1400131c8  jns     short loc_1400131D8
0x1400131ca  mov     ecx, eax
0x1400131cc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400131d1  mov     rsi, [rsp+28h+lpLibFileName]
0x1400131d6  jmp     short loc_140013221
0x1400131d8  mov     rsi, [rsp+28h+lpLibFileName]
0x1400131dd  xor     r8d, r8d; dwFlags
0x1400131e0  mov     rcx, rsi; lpLibFileName
0x1400131e3  xor     edx, edx; hFile
0x1400131e5  call    cs:__imp_LoadLibraryExW
0x1400131ec  nop     dword ptr [rax+rax+00h]
0x1400131f1  test    rax, rax
0x1400131f4  jnz     short loc_14001321E
0x1400131f6  call    cs:__imp_GetLastError
0x1400131fd  nop     dword ptr [rax+rax+00h]
0x140013202  mov     edi, eax
0x140013204  test    eax, eax
0x140013206  jnz     short loc_14001320F
0x140013208  mov     edi, 80004005h
0x14001320d  jmp     short loc_14001321A
0x14001320f  jle     short loc_14001321A
0x140013211  movzx   edi, ax
0x140013214  or      edi, 80070000h
0x14001321a  mov     ecx, edi
0x14001321c  jmp     short loc_1400131A4
0x14001321e  mov     [r14], rax
0x140013221  mov     ecx, edi
0x140013223  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140013228  test    rbx, rbx
0x14001322b  jz      short loc_14001323C
0x14001322d  mov     rcx, rbx; hLibModule
0x140013230  call    cs:__imp_FreeLibrary
0x140013237  nop     dword ptr [rax+rax+00h]
0x14001323c  test    rsi, rsi
0x14001323f  jz      short loc_140013269
0x140013241  call    cs:__imp_GetProcessHeap
0x140013248  nop     dword ptr [rax+rax+00h]
0x14001324d  lea     r8, [rsi-4]; lpMem
0x140013251  xor     edx, edx; dwFlags
0x140013253  mov     rcx, rax; hHeap
0x140013256  call    cs:__imp_HeapFree
0x14001325d  nop     dword ptr [rax+rax+00h]
0x140013262  xor     ecx, ecx
0x140013264  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140013269  mov     rbx, [rsp+28h+arg_0]
0x14001326e  mov     eax, edi
0x140013270  mov     rdi, [rsp+28h+arg_18]
0x140013275  mov     rsi, [rsp+28h+arg_10]
0x14001327a  add     rsp, 20h
0x14001327e  pop     r14
0x140013280  retn
```
