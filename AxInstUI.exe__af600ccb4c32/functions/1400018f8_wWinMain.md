# wWinMain

- ea: `0x1400018f8`
- end: `0x140001a01`
- name: `wWinMain`
- size: `265`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001140`

## callees

- `0x1400018f8`
- `0x140001af0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400019d5`
- `KERNEL32!LocalFree` at `0x1400019d5`
- `KERNEL32!GetCommandLineW` at `0x140001925`
- `KERNEL32!GetCommandLineW` at `0x140001925`
- `USER32!IsWindow` at `0x1400019a3`
- `USER32!IsWindow` at `0x1400019a3`
- `msvcrt!swscanf_s` at `0x140001998`
- `msvcrt!swscanf_s` at `0x140001998`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001973`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001973`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400019df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400019df`
- `SHELL32!CommandLineToArgvW` at `0x14000193c`
- `SHELL32!CommandLineToArgvW` at `0x14000193c`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v5; // rax
  LPWSTR *v6; // rdi
  int v7; // ebx
  int v8; // esi
  const wchar_t *v9; // rbx
  const unsigned __int16 *v10; // rbp
  const unsigned __int16 *v11; // r14
  unsigned int v12; // r9d
  HWND v13; // rcx
  unsigned int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+30h] [rbp-28h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-20h] BYREF
  int pNumArgs; // [rsp+70h] [rbp+18h] BYREF
  int v19; // [rsp+74h] [rbp+1Ch]

  v19 = HIDWORD(lpCmdLine);
  pNumArgs = 0;
  hWnd = 0;
  v16 = 0;
  CommandLineW = GetCommandLineW();
  if ( !CommandLineW )
    return 87;
  v5 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  v6 = v5;
  if ( !v5 )
    return 14;
  v8 = 0;
  if ( pNumArgs == 4 )
  {
    v9 = v5[1];
    v10 = v5[2];
    v11 = v5[3];
    if ( CoInitializeEx(0, 2u) )
    {
      v7 = 5;
    }
    else
    {
      v8 = 1;
      swscanf_s(v9, L"%Iu", &hWnd);
      if ( IsWindow(hWnd) )
      {
        v13 = hWnd;
      }
      else
      {
        v13 = 0;
        hWnd = 0;
      }
      v7 = VerifyTrust(v13, v10, v11, v12, v15, &v16);
    }
  }
  else
  {
    v7 = 87;
  }
  LocalFree(v6);
  if ( v8 )
    CoUninitialize();
  return v7;
}

```

## disassembly

```asm
0x1400018f8  mov     rax, rsp
0x1400018fb  mov     [rax+8], rbx
0x1400018ff  mov     [rax+10h], rbp
0x140001903  mov     [rax+18h], r8
0x140001907  push    rsi
0x140001908  push    rdi
0x140001909  push    r14
0x14000190b  sub     rsp, 40h
0x14000190f  mov     dword ptr [rax+18h], 0
0x140001916  mov     qword ptr [rax-20h], 0
0x14000191e  mov     dword ptr [rax-28h], 0
0x140001925  call    cs:__imp_GetCommandLineW
0x14000192b  test    rax, rax
0x14000192e  jz      loc_1400019E7
0x140001934  lea     rdx, [rsp+58h+pNumArgs]; pNumArgs
0x140001939  mov     rcx, rax; lpCmdLine
0x14000193c  call    cs:__imp_CommandLineToArgvW
0x140001942  mov     rdi, rax
0x140001945  test    rax, rax
0x140001948  jnz     short loc_140001952
0x14000194a  lea     ebx, [rax+0Eh]
0x14000194d  jmp     loc_1400019EC
0x140001952  xor     esi, esi
0x140001954  cmp     [rsp+58h+pNumArgs], 4
0x140001959  jz      short loc_140001960
0x14000195b  lea     ebx, [rsi+57h]
0x14000195e  jmp     short loc_1400019D2
0x140001960  mov     rbx, [rax+8]
0x140001964  mov     edx, 2; dwCoInit
0x140001969  mov     rbp, [rax+10h]
0x14000196d  xor     ecx, ecx; pvReserved
0x14000196f  mov     r14, [rax+18h]
0x140001973  call    cs:__imp_CoInitializeEx
0x140001979  test    eax, eax
0x14000197b  jz      short loc_140001984
0x14000197d  mov     ebx, 5
0x140001982  jmp     short loc_1400019D2
0x140001984  lea     r8, [rsp+58h+hWnd]
0x140001989  mov     rcx, rbx; Buffer
0x14000198c  lea     rdx, aIu; "%Iu"
0x140001993  mov     esi, 1
0x140001998  call    cs:__imp_swscanf_s
0x14000199e  mov     rcx, [rsp+58h+hWnd]; hWnd
0x1400019a3  call    cs:__imp_IsWindow
0x1400019a9  test    eax, eax
0x1400019ab  jnz     short loc_1400019B6
0x1400019ad  xor     ecx, ecx
0x1400019af  mov     [rsp+58h+hWnd], rcx
0x1400019b4  jmp     short loc_1400019BB
0x1400019b6  mov     rcx, [rsp+58h+hWnd]; hwnd
0x1400019bb  lea     rax, [rsp+58h+var_28]
0x1400019c0  mov     r8, r14; unsigned __int16 *
0x1400019c3  mov     rdx, rbp; unsigned __int16 *
0x1400019c6  mov     [rsp+58h+var_30], rax; int *
0x1400019cb  call    ?VerifyTrust@@YAJPEAUHWND__@@PEBG1KKPEAH@Z; VerifyTrust(HWND__ *,ushort const *,ushort const *,ulong,ulong,int *)
0x1400019d0  mov     ebx, eax
0x1400019d2  mov     rcx, rdi; hMem
0x1400019d5  call    cs:__imp_LocalFree
0x1400019db  test    esi, esi
0x1400019dd  jz      short loc_1400019EC
0x1400019df  call    cs:__imp_CoUninitialize
0x1400019e5  jmp     short loc_1400019EC
0x1400019e7  mov     ebx, 57h ; 'W'
0x1400019ec  mov     rbp, [rsp+58h+arg_8]
0x1400019f1  mov     eax, ebx
0x1400019f3  mov     rbx, [rsp+58h+arg_0]
0x1400019f8  add     rsp, 40h
0x1400019fc  pop     r14
0x1400019fe  pop     rdi
0x1400019ff  pop     rsi
0x140001a00  retn
```
