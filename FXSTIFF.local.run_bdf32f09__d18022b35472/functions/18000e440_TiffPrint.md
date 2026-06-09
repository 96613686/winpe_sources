# TiffPrint

- ea: `0x18000e440`
- end: `0x18000e51b`
- name: `TiffPrint`
- size: `219`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, wchar_t *String, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001718`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000e440`
- `0x18000e530`

## import_xrefs

- `GDI32!DeleteDC` at `0x18000e503`
- `GDI32!DeleteDC` at `0x18000e503`
- `GDI32!CreateDCW` at `0x18000e4a8`
- `GDI32!CreateDCW` at `0x18000e4a8`
- `KERNEL32!GetLastError` at `0x18000e4d2`
- `KERNEL32!GetLastError` at `0x18000e4d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffPrint(LPCWSTR lpFileName, wchar_t *String, wchar_t **a3)
{
  wchar_t *v5; // rax
  HDC DCW; // rax
  HDC v7; // rdi
  __int64 v8; // rbx
  DWORD LastError; // eax
  unsigned int v11; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids);
  }
  v5 = wcstok_mvcrt_legacy_two_parameter_form(String, L",", a3);
  DCW = CreateDCW(L"WINSPOOL", v5, 0, 0);
  v7 = DCW;
  if ( DCW )
  {
    v11 = TiffPrintDC(lpFileName, 0, DCW);
    DeleteDC(v7);
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v8, 25, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids, LastError);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000e440  mov     [rsp+arg_0], rbx
0x18000e445  mov     [rsp+arg_8], rbp
0x18000e44a  push    rdi
0x18000e44b  sub     rsp, 20h
0x18000e44f  mov     rdi, rdx
0x18000e452  mov     rbx, rcx
0x18000e455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e45c  lea     rbp, WPP_GLOBAL_Control
0x18000e463  cmp     rcx, rbp
0x18000e466  jz      short loc_18000E489
0x18000e468  test    byte ptr [rcx+1Ch], 2
0x18000e46c  jz      short loc_18000E489
0x18000e46e  cmp     byte ptr [rcx+19h], 5
0x18000e472  jb      short loc_18000E489
0x18000e474  mov     rcx, [rcx+10h]
0x18000e478  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e47f  mov     edx, 18h
0x18000e484  call    WPP_SF_
0x18000e489  lea     rdx, Delimiter; ","
0x18000e490  mov     rcx, rdi; String
0x18000e493  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000e498  xor     r9d, r9d; pdm
0x18000e49b  lea     rcx, pwszDriver; "WINSPOOL"
0x18000e4a2  xor     r8d, r8d; pszPort
0x18000e4a5  mov     rdx, rax; pwszDevice
0x18000e4a8  call    cs:__imp_CreateDCW
0x18000e4ae  mov     rdi, rax
0x18000e4b1  test    rax, rax
0x18000e4b4  jnz     short loc_18000E4F1
0x18000e4b6  mov     rbx, cs:WPP_GLOBAL_Control
0x18000e4bd  cmp     rbx, rbp
0x18000e4c0  jz      short loc_18000E4ED
0x18000e4c2  test    byte ptr [rbx+1Ch], 2
0x18000e4c6  jz      short loc_18000E4ED
0x18000e4c8  cmp     byte ptr [rbx+19h], 2
0x18000e4cc  jb      short loc_18000E4ED
0x18000e4ce  mov     rbx, [rbx+10h]
0x18000e4d2  call    cs:__imp_GetLastError
0x18000e4d8  lea     edx, [rdi+19h]
0x18000e4db  mov     rcx, rbx
0x18000e4de  mov     r9d, eax
0x18000e4e1  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e4e8  call    WPP_SF_d
0x18000e4ed  xor     eax, eax
0x18000e4ef  jmp     short loc_18000E50B
0x18000e4f1  mov     r8, rdi; hdc
0x18000e4f4  xor     edx, edx; pPrinterName
0x18000e4f6  mov     rcx, rbx; lpFileName
0x18000e4f9  call    TiffPrintDC
0x18000e4fe  mov     rcx, rdi; hdc
0x18000e501  mov     ebx, eax
0x18000e503  call    cs:__imp_DeleteDC
0x18000e509  mov     eax, ebx
0x18000e50b  mov     rbx, [rsp+28h+arg_0]
0x18000e510  mov     rbp, [rsp+28h+arg_8]
0x18000e515  add     rsp, 20h
0x18000e519  pop     rdi
0x18000e51a  retn
```
