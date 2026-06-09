# SaveNewOffsetToBackup(ushort const *,unsigned __int64,ushort const *)

- ea: `0x180037eb4`
- end: `0x1800380a4`
- name: `?SaveNewOffsetToBackup@@YAHPEBG_K0@Z`
- size: `496`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18002f980`
- `0x180036c38`

## callees

- `0x1800059fc`
- `0x18000c6f0`
- `0x18001c324`
- `0x18001c448`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f47c`
- `0x180037eb4`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180037ffd`
- `ntdll!RtlNtStatusToDosError` at `0x18003800c`
- `ntdll!RtlNtStatusToDosError` at `0x180037ffd`
- `ntdll!RtlNtStatusToDosError` at `0x18003800c`
- `KERNEL32!GetLastError` at `0x180038054`
- `KERNEL32!GetLastError` at `0x180038054`
- `KERNEL32!WritePrivateProfileStringW` at `0x18003804a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18003804a`
- `KERNEL32!SetLastError` at `0x180037f15`
- `KERNEL32!SetLastError` at `0x180037f15`
- `KERNEL32!GetFileAttributesW` at `0x180037f23`
- `KERNEL32!GetFileAttributesW` at `0x180037f23`

## string_xrefs

- `0x180037f31`: `Undo Directory [%s] does not exist.`
- `0x18003805d`: `WritePrivateProfileString new partition offset string failed. Error: 0X%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SaveNewOffsetToBackup(LPCWSTR lpFileName, __int64 a2, const unsigned __int16 *a3)
{
  unsigned int v6; // edi
  DWORD v7; // ecx
  __int64 v8; // rdx
  _QWORD *v9; // rax
  const WCHAR *v10; // r9
  unsigned __int64 v11; // rax
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  int v16; // eax
  NTSTATUS v17; // ebx
  const WCHAR *v18; // rax
  DWORD LastError; // eax
  _QWORD v21[5]; // [rsp+28h] [rbp-2B0h] BYREF
  WCHAR String[304]; // [rsp+50h] [rbp-288h] BYREF

  v6 = 0;
  memset_0(String, 0, 0x25Cu);
  std::wstring::wstring(v21, lpFileName);
  if ( !lpFileName )
  {
    v7 = 160;
LABEL_3:
    SetLastError(v7);
    goto LABEL_18;
  }
  if ( GetFileAttributesW(lpFileName) == -1 )
  {
    UnattendLogW(2, L"Undo Directory [%s] does not exist.", lpFileName);
    v7 = 1168;
    goto LABEL_3;
  }
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  v10 = &cchOriginalDestLength;
  if ( *((_WORD *)v9 + v21[2] - 1) != 92 )
    v10 = L"\\";
  v11 = std::char_traits<unsigned short>::length(v10);
  std::wstring::append(v21, v12, v11);
  v13 = std::char_traits<unsigned short>::length(L"location.txt");
  std::wstring::append(v21, v14, v13);
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  UnattendLogW(0, L" Save new offset [%I64u] to %s for restore", a2, v15, -2);
  v16 = StringCchPrintfW(String, 0x12Eu, L"%I64u", a2);
  v17 = v16;
  if ( v16 < 0 )
  {
    UnattendLogW(2, L"StringCchPrintf winre location offset failed. Error: 0X%X", (unsigned int)v16);
    if ( (v17 & 0x10000000) != 0 )
    {
      if ( RtlNtStatusToDosError(v17) != 317 )
        v17 = RtlNtStatusToDosError(v17);
    }
    else if ( (v17 & 0x1FFF0000) == 0x70000 )
    {
      v17 = (unsigned __int16)v17;
    }
    v7 = v17;
    goto LABEL_3;
  }
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  if ( WritePrivateProfileStringW(L"WinRE Location", a3, String, v18) )
  {
    v6 = 1;
  }
  else
  {
    LastError = GetLastError();
    UnattendLogW(2, L"WritePrivateProfileString new partition offset string failed. Error: 0X%X", LastError);
  }
LABEL_18:
  std::wstring::~wstring((__int64)v21, v8);
  return v6;
}

```

## disassembly

```asm
0x180037eb4  mov     rax, rsp
0x180037eb7  push    rbp
0x180037eb8  push    rsi
0x180037eb9  push    rdi
0x180037eba  sub     rsp, 2C0h
0x180037ec1  mov     [rsp+2D8h+var_2B8], 0FFFFFFFFFFFFFFFEh
0x180037eca  mov     [rax+20h], rbx
0x180037ece  mov     rax, cs:__security_cookie
0x180037ed5  xor     rax, rsp
0x180037ed8  mov     [rsp+2D8h+var_28], rax
0x180037ee0  mov     rsi, r8
0x180037ee3  mov     rbp, rdx
0x180037ee6  mov     rbx, rcx
0x180037ee9  xor     edi, edi
0x180037eeb  xor     edx, edx; Val
0x180037eed  mov     r8d, 25Ch; Size
0x180037ef3  lea     rcx, [rsp+2D8h+String]; void *
0x180037ef8  call    memset_0
0x180037efd  mov     rdx, rbx
0x180037f00  lea     rcx, [rsp+2D8h+var_2B0]
0x180037f05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180037f0a  nop
0x180037f0b  test    rbx, rbx
0x180037f0e  jnz     short loc_180037F20
0x180037f10  mov     ecx, 0A0h; dwErrCode
0x180037f15  call    cs:__imp_SetLastError
0x180037f1b  jmp     loc_180038075
0x180037f20  mov     rcx, rbx; lpFileName
0x180037f23  call    cs:__imp_GetFileAttributesW
0x180037f29  cmp     eax, 0FFFFFFFFh
0x180037f2c  jnz     short loc_180037F49
0x180037f2e  mov     r8, rbx
0x180037f31  lea     rdx, aUndoDirectoryS; "Undo Directory [%s] does not exist."
0x180037f38  mov     ecx, 2
0x180037f3d  call    UnattendLogW
0x180037f42  mov     ecx, 490h
0x180037f47  jmp     short loc_180037F15
0x180037f49  lea     rcx, [rsp+2D8h+var_2B0]
0x180037f4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037f53  mov     rcx, [rsp+2D8h+var_2A0]
0x180037f58  lea     rdx, pszSrc; "\\"
0x180037f5f  lea     r9, cchOriginalDestLength
0x180037f66  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180037f6c  cmovnz  r9, rdx
0x180037f70  mov     rcx, r9
0x180037f73  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180037f78  mov     r8, rax
0x180037f7b  mov     rdx, r9
0x180037f7e  lea     rcx, [rsp+2D8h+var_2B0]
0x180037f83  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180037f88  lea     rcx, aLocationTxt; "location.txt"
0x180037f8f  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180037f94  mov     r8, rax
0x180037f97  mov     rdx, rcx
0x180037f9a  lea     rcx, [rsp+2D8h+var_2B0]
0x180037f9f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180037fa4  lea     rcx, [rsp+2D8h+var_2B0]
0x180037fa9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037fae  mov     r9, rax
0x180037fb1  mov     r8, rbp
0x180037fb4  lea     rdx, aSaveNewOffsetI; " Save new offset [%I64u] to %s for rest"...
0x180037fbb  xor     ecx, ecx
0x180037fbd  call    UnattendLogW
0x180037fc2  mov     r9, rbp
0x180037fc5  lea     r8, aI64u_0; "%I64u"
0x180037fcc  mov     edx, 12Eh; unsigned __int64
0x180037fd1  lea     rcx, [rsp+2D8h+String]; unsigned __int16 *
0x180037fd6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037fdb  mov     ebx, eax
0x180037fdd  test    eax, eax
0x180037fdf  jns     short loc_18003802E
0x180037fe1  mov     r8d, eax
0x180037fe4  lea     rdx, aStringcchprint_3; "StringCchPrintf winre location offset f"...
0x180037feb  mov     ecx, 2
0x180037ff0  call    UnattendLogW
0x180037ff5  bt      ebx, 1Ch
0x180037ff9  jnb     short loc_180038016
0x180037ffb  mov     ecx, ebx; Status
0x180037ffd  call    cs:__imp_RtlNtStatusToDosError
0x180038003  cmp     eax, 13Dh
0x180038008  jz      short loc_180038027
0x18003800a  mov     ecx, ebx; Status
0x18003800c  call    cs:__imp_RtlNtStatusToDosError
0x180038012  mov     ebx, eax
0x180038014  jmp     short loc_180038027
0x180038016  mov     eax, ebx
0x180038018  and     eax, 1FFF0000h
0x18003801d  cmp     eax, 70000h
0x180038022  jnz     short loc_180038027
0x180038024  movzx   ebx, bx
0x180038027  mov     ecx, ebx
0x180038029  jmp     loc_180037F15
0x18003802e  lea     rcx, [rsp+2D8h+var_2B0]
0x180038033  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038038  mov     r9, rax; lpFileName
0x18003803b  lea     r8, [rsp+2D8h+String]; lpString
0x180038040  mov     rdx, rsi; lpKeyName
0x180038043  lea     rcx, aWinreLocation; "WinRE Location"
0x18003804a  call    cs:__imp_WritePrivateProfileStringW
0x180038050  test    eax, eax
0x180038052  jnz     short loc_180038070
0x180038054  call    cs:__imp_GetLastError
0x18003805a  mov     r8d, eax
0x18003805d  lea     rdx, aWriteprivatepr; "WritePrivateProfileString new partition"...
0x180038064  mov     ecx, 2
0x180038069  call    UnattendLogW
0x18003806e  jmp     short loc_180038075
0x180038070  mov     edi, 1
0x180038075  lea     rcx, [rsp+2D8h+var_2B0]
0x18003807a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003807f  mov     eax, edi
0x180038081  mov     rcx, [rsp+2D8h+var_28]
0x180038089  xor     rcx, rsp; StackCookie
0x18003808c  call    __security_check_cookie
0x180038091  mov     rbx, [rsp+2D8h+arg_18]
0x180038099  add     rsp, 2C0h
0x1800380a0  pop     rdi
0x1800380a1  pop     rsi
0x1800380a2  pop     rbp
0x1800380a3  retn
```
