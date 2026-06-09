# TiffPrint

- ea: `0x18000ea70`
- end: `0x18000eb5e`
- name: `TiffPrint`
- size: `238`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, wchar_t *String, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001718`
- `0x180009f04`
- `0x180009f34`
- `0x18000ea70`
- `0x18000eb70`

## import_xrefs

- `GDI32!DeleteDC` at `0x18000eb3f`
- `GDI32!DeleteDC` at `0x18000eb3f`
- `GDI32!CreateDCW` at `0x18000ead8`
- `GDI32!CreateDCW` at `0x18000ead8`
- `KERNEL32!GetLastError` at `0x18000eb08`
- `KERNEL32!GetLastError` at `0x18000eb08`

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
0x18000ea70  mov     [rsp+arg_0], rbx
0x18000ea75  mov     [rsp+arg_8], rbp
0x18000ea7a  push    rdi
0x18000ea7b  sub     rsp, 20h
0x18000ea7f  mov     rdi, rdx
0x18000ea82  mov     rbx, rcx
0x18000ea85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea8c  lea     rbp, WPP_GLOBAL_Control
0x18000ea93  cmp     rcx, rbp
0x18000ea96  jz      short loc_18000EAB9
0x18000ea98  test    byte ptr [rcx+1Ch], 2
0x18000ea9c  jz      short loc_18000EAB9
0x18000ea9e  cmp     byte ptr [rcx+19h], 5
0x18000eaa2  jb      short loc_18000EAB9
0x18000eaa4  mov     rcx, [rcx+10h]
0x18000eaa8  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000eaaf  mov     edx, 18h
0x18000eab4  call    WPP_SF_
0x18000eab9  lea     rdx, Delimiter; ","
0x18000eac0  mov     rcx, rdi; String
0x18000eac3  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000eac8  xor     r9d, r9d; pdm
0x18000eacb  lea     rcx, pwszDriver; "WINSPOOL"
0x18000ead2  xor     r8d, r8d; pszPort
0x18000ead5  mov     rdx, rax; pwszDevice
0x18000ead8  call    cs:__imp_CreateDCW
0x18000eadf  nop     dword ptr [rax+rax+00h]
0x18000eae4  mov     rdi, rax
0x18000eae7  test    rax, rax
0x18000eaea  jnz     short loc_18000EB2D
0x18000eaec  mov     rbx, cs:WPP_GLOBAL_Control
0x18000eaf3  cmp     rbx, rbp
0x18000eaf6  jz      short loc_18000EB29
0x18000eaf8  test    byte ptr [rbx+1Ch], 2
0x18000eafc  jz      short loc_18000EB29
0x18000eafe  cmp     byte ptr [rbx+19h], 2
0x18000eb02  jb      short loc_18000EB29
0x18000eb04  mov     rbx, [rbx+10h]
0x18000eb08  call    cs:__imp_GetLastError
0x18000eb0f  nop     dword ptr [rax+rax+00h]
0x18000eb14  lea     edx, [rdi+19h]
0x18000eb17  mov     rcx, rbx
0x18000eb1a  mov     r9d, eax
0x18000eb1d  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000eb24  call    WPP_SF_d
0x18000eb29  xor     eax, eax
0x18000eb2b  jmp     short loc_18000EB4D
0x18000eb2d  mov     r8, rdi; hdc
0x18000eb30  xor     edx, edx; pPrinterName
0x18000eb32  mov     rcx, rbx; lpFileName
0x18000eb35  call    TiffPrintDC
0x18000eb3a  mov     rcx, rdi; hdc
0x18000eb3d  mov     ebx, eax
0x18000eb3f  call    cs:__imp_DeleteDC
0x18000eb46  nop     dword ptr [rax+rax+00h]
0x18000eb4b  mov     eax, ebx
0x18000eb4d  mov     rbx, [rsp+28h+arg_0]
0x18000eb52  mov     rbp, [rsp+28h+arg_8]
0x18000eb57  add     rsp, 20h
0x18000eb5b  pop     rdi
0x18000eb5c  retn
```
