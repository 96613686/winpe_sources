# ProcessOneRegSec(HWND__ *,ushort const *,ushort const *,ushort const *,HKEY__ *,HKEY__ *,ulong,int *)

- ea: `0x18000da30`
- end: `0x18000dbe5`
- name: `?ProcessOneRegSec@@YAJPEAUHWND__@@PEBG11PEAUHKEY__@@2KPEAH@Z`
- size: `437`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HKEY, HKEY hkBckupKey, DWORD dwFlags, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d7ac`
- `0x180010ac0`

## callees

- `0x180006e54`
- `0x18000931c`
- `0x18000c574`
- `0x18000da30`
- `0x180014440`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000db98`
- `KERNEL32!LocalFree` at `0x18000db98`
- `KERNEL32!CompareStringW` at `0x18000db2d`
- `KERNEL32!CompareStringW` at `0x18000db57`
- `KERNEL32!CompareStringW` at `0x18000db2d`
- `KERNEL32!CompareStringW` at `0x18000db57`

## pseudocode

```c
__int64 __fastcall ProcessOneRegSec(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HKEY a5,
        HKEY hkBckupKey,
        DWORD dwFlags,
        int *a8)
{
  int TranslatedLine; // ebx
  unsigned int v12; // r15d
  const WCHAR *v13; // rbx
  int v14; // eax
  HKEY v15; // r8
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  PCNZWCH lpString1; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR pcszValueName; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR pcszSubKey; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v21; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int16 *v22; // [rsp+68h] [rbp-8h] BYREF

  TranslatedLine = 0;
  hMem = 0;
  lpString1 = 0;
  pcszSubKey = 0;
  pcszValueName = 0;
  v22 = 0;
  v21 = 0;
  AdvWriteToLog(L"ProcessOneRegSec: Section=%1\r\n", a4);
  v12 = 0;
  while ( !TranslatedLine )
  {
    TranslatedLine = GetTranslatedLine(a3, a4, v12, (unsigned __int16 **)&hMem, 0);
    if ( TranslatedLine < 0 )
    {
      if ( TranslatedLine == -2147024637 )
        TranslatedLine = 0;
      break;
    }
    if ( !hMem )
      break;
    if ( a8 && !*a8 )
      *a8 = 1;
    ParseCustomLine(
      (unsigned __int16 *)hMem,
      (unsigned __int16 **)&lpString1,
      (unsigned __int16 **)&pcszSubKey,
      (unsigned __int16 **)&pcszValueName,
      &v22,
      &v21,
      0,
      1);
    v13 = lpString1;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"HKCU", -1) == 2
      || (v14 = CompareStringW(0x7Fu, 1u, v13, -1, L"HKEY_CURRENT_USER", -1), v15 = a5, v14 == 2) )
    {
      v15 = hkBckupKey;
    }
    TranslatedLine = RegSaveRestoreW(a1, a2, v15, v13, pcszSubKey, pcszValueName, dwFlags);
    LocalFree(hMem);
    ++v12;
    hMem = 0;
  }
  AdvWriteToLog(L"ProcessOneRegSec: End hr=0x%1!x! %2\r\n", (unsigned int)TranslatedLine, a4);
  return (unsigned int)TranslatedLine;
}

```

## disassembly

```asm
0x18000da30  mov     [rsp-28h+arg_8], rbx
0x18000da35  mov     [rsp-28h+arg_10], rsi
0x18000da3a  mov     [rsp-28h+hWnd], rcx
0x18000da3f  push    rbp
0x18000da40  push    rdi
0x18000da41  push    r12
0x18000da43  push    r13
0x18000da45  push    r15
0x18000da47  mov     rbp, rsp
0x18000da4a  sub     rsp, 70h
0x18000da4e  xor     ebx, ebx
0x18000da50  mov     [rbp+hMem], 0
0x18000da58  mov     r13, rdx
0x18000da5b  mov     [rbp+lpString1], rbx
0x18000da5f  mov     rdx, r9
0x18000da62  mov     [rbp+pcszSubKey], rbx
0x18000da66  lea     rcx, aProcessoneregs; "ProcessOneRegSec: Section=%1\r\n"
0x18000da6d  mov     [rbp+pcszValueName], rbx
0x18000da71  mov     [rbp+var_8], rbx
0x18000da75  mov     rsi, r9
0x18000da78  mov     [rbp+var_10], rbx
0x18000da7c  mov     r12, r8
0x18000da7f  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000da84  mov     rdi, [rbp+arg_38]
0x18000da88  xor     r15d, r15d
0x18000da8b  test    ebx, ebx
0x18000da8d  jnz     loc_18000DBB9
0x18000da93  lea     r9, [rbp+hMem]; unsigned __int16 **
0x18000da97  mov     [rsp+70h+lpString2], 0; unsigned int *
0x18000daa0  mov     r8d, r15d; unsigned int
0x18000daa3  mov     rdx, rsi; lpAppName
0x18000daa6  mov     rcx, r12; lpFileName
0x18000daa9  call    ?GetTranslatedLine@@YAJPEBG0KPEAPEAGPEAK@Z; GetTranslatedLine(ushort const *,ushort const *,ulong,ushort * *,ulong *)
0x18000daae  mov     ebx, eax
0x18000dab0  test    eax, eax
0x18000dab2  js      loc_18000DBAE
0x18000dab8  cmp     [rbp+hMem], 0
0x18000dabd  jz      loc_18000DBB9
0x18000dac3  test    rdi, rdi
0x18000dac6  jz      short loc_18000DAD3
0x18000dac8  cmp     dword ptr [rdi], 0
0x18000dacb  jnz     short loc_18000DAD3
0x18000dacd  mov     dword ptr [rdi], 1
0x18000dad3  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18000dad7  lea     rax, [rbp+var_10]
0x18000dadb  mov     [rsp+70h+var_38], 1; int
0x18000dae3  lea     r9, [rbp+pcszValueName]; unsigned __int16 **
0x18000dae7  mov     [rsp+70h+dwFlags], 0; int
0x18000daef  lea     r8, [rbp+pcszSubKey]; unsigned __int16 **
0x18000daf3  mov     qword ptr [rsp+70h+cchCount2], rax; unsigned __int16 **
0x18000daf8  lea     rdx, [rbp+lpString1]; unsigned __int16 **
0x18000dafc  lea     rax, [rbp+var_8]
0x18000db00  mov     [rsp+70h+lpString2], rax; unsigned __int16 **
0x18000db05  call    ?ParseCustomLine@@YAHPEAGPEAPEAG1111HH@Z; ParseCustomLine(ushort *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,int,int)
0x18000db0a  mov     rbx, [rbp+lpString1]
0x18000db0e  lea     rax, aHkcu; "HKCU"
0x18000db15  or      ecx, 0FFFFFFFFh
0x18000db18  mov     r8, rbx; lpString1
0x18000db1b  mov     [rsp+70h+cchCount2], ecx; cchCount2
0x18000db1f  mov     r9d, ecx; cchCount1
0x18000db22  mov     [rsp+70h+lpString2], rax; lpString2
0x18000db27  lea     edx, [rcx+2]; dwCmpFlags
0x18000db2a  lea     ecx, [rdx+7Eh]; Locale
0x18000db2d  call    cs:__imp_CompareStringW
0x18000db33  cmp     eax, 2
0x18000db36  jz      short loc_18000DB66
0x18000db38  or      ecx, 0FFFFFFFFh
0x18000db3b  lea     rax, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18000db42  mov     [rsp+70h+cchCount2], ecx; cchCount2
0x18000db46  mov     r9d, ecx; cchCount1
0x18000db49  mov     r8, rbx; lpString1
0x18000db4c  mov     [rsp+70h+lpString2], rax; lpString2
0x18000db51  lea     edx, [rcx+2]; dwCmpFlags
0x18000db54  lea     ecx, [rdx+7Eh]; Locale
0x18000db57  call    cs:__imp_CompareStringW
0x18000db5d  mov     r8, [rbp+arg_20]
0x18000db61  cmp     eax, 2
0x18000db64  jnz     short loc_18000DB6A
0x18000db66  mov     r8, [rbp+hkBckupKey]; hkBckupKey
0x18000db6a  mov     eax, [rbp+arg_30]
0x18000db6d  mov     r9, rbx; pcszRootKey
0x18000db70  mov     rcx, [rbp+hWnd]; hWnd
0x18000db74  mov     rdx, r13; pszTitleString
0x18000db77  mov     [rsp+70h+dwFlags], eax; dwFlags
0x18000db7b  mov     rax, [rbp+pcszValueName]
0x18000db7f  mov     qword ptr [rsp+70h+cchCount2], rax; pcszValueName
0x18000db84  mov     rax, [rbp+pcszSubKey]
0x18000db88  mov     [rsp+70h+lpString2], rax; pcszSubKey
0x18000db8d  call    RegSaveRestoreW
0x18000db92  mov     rcx, [rbp+hMem]; hMem
0x18000db96  mov     ebx, eax
0x18000db98  call    cs:__imp_LocalFree
0x18000db9e  inc     r15d
0x18000dba1  mov     [rbp+hMem], 0
0x18000dba9  jmp     loc_18000DA8B
0x18000dbae  xor     eax, eax
0x18000dbb0  cmp     ebx, 80070103h
0x18000dbb6  cmovz   ebx, eax
0x18000dbb9  mov     r8, rsi
0x18000dbbc  lea     rcx, aProcessoneregs_0; "ProcessOneRegSec: End hr=0x%1!x! %2\r\n"
0x18000dbc3  mov     edx, ebx
0x18000dbc5  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000dbca  lea     r11, [rsp+70h+var_s0]
0x18000dbcf  mov     eax, ebx
0x18000dbd1  mov     rbx, [r11+38h]
0x18000dbd5  mov     rsi, [r11+40h]
0x18000dbd9  mov     rsp, r11
0x18000dbdc  pop     r15
0x18000dbde  pop     r13
0x18000dbe0  pop     r12
0x18000dbe2  pop     rdi
0x18000dbe3  pop     rbp
0x18000dbe4  retn
```
