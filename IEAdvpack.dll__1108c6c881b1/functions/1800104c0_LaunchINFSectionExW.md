# LaunchINFSectionExW

- ea: `0x1800104c0`
- end: `0x18001065d`
- name: `LaunchINFSectionExW`
- size: `413`
- prototype: `HRESULT __stdcall(HWND hwnd, HINSTANCE hInstance, LPWSTR pszParms, INT nShow)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000d370`

## callees

- `0x1800022bc`
- `0x180006af8`
- `0x1800082f0`
- `0x180008a6c`
- `0x18000c574`
- `0x18000f7b0`
- `0x1800104c0`

## import_xrefs

- `msvcrt!_wtol` at `0x1800105c6`
- `msvcrt!_wtol` at `0x1800105c6`
- `KERNEL32!LocalFree` at `0x180010617`
- `KERNEL32!LocalFree` at `0x180010617`
- `KERNEL32!LocalAlloc` at `0x1800104f6`
- `KERNEL32!LocalAlloc` at `0x1800104f6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800105fe`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800105fe`

## pseudocode

```c
HRESULT __stdcall LaunchINFSectionExW(HWND hwnd, HINSTANCE hInstance, LPWSTR pszParms, INT nShow)
{
  unsigned int v5; // edi
  CABINFOW *v6; // rbx
  unsigned __int16 *StringField; // rbp
  const unsigned __int16 *pszCab; // rcx
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v11; // [rsp+90h] [rbp+18h] BYREF

  v11 = pszParms;
  v5 = 0;
  AdvWriteToLog(L"LaunchINFSectionEx: Param= %1\r\n", pszParms);
  v6 = (CABINFOW *)LocalAlloc(0x40u, 0x228u);
  if ( v6 )
  {
    v6->pszInf = GetStringField(&v11, L",", 34, 1);
    v6->pszSection = GetStringField(&v11, L",", 34, 1);
    v6->pszCab = GetStringField(&v11, L",", 34, 1);
    StringField = GetStringField(&v11, L",", 34, 1);
    qword_180032318 = GetStringField(&v11, L",", 34, 1);
    if ( StringField )
      v6->dwFlags = _wtol(StringField);
    pszCab = v6->pszCab;
    if ( v6->pszCab && *pszCab )
    {
      if ( !IsFullPath(pszCab) )
      {
        MsgBox2Param(hwnd, 0x47Du, v9, 0, 0x10u, 0);
        goto LABEL_10;
      }
      StringCchCopyW(v6->szSrcPath, 0x104u, (size_t *)v9);
      PathRemoveFileSpecW(v6->szSrcPath);
    }
    v5 = ExecuteCabW(hwnd, v6, 0);
LABEL_10:
    LocalFree(v6);
    goto LABEL_11;
  }
  MsgBox2Param(hwnd, 0x44Eu, 0, 0, 0x10u, 0);
LABEL_11:
  AdvWriteToLog(L"LaunchINFSectionEx: End hr=0x%1!x!\r\n", v5);
  return v5;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_10], r8
0x1800104c5  push    rbx
0x1800104c6  push    rbp
0x1800104c7  push    rsi
0x1800104c8  push    rdi
0x1800104c9  push    r12
0x1800104cb  push    r13
0x1800104cd  push    r14
0x1800104cf  push    r15
0x1800104d1  sub     rsp, 38h
0x1800104d5  mov     rsi, rcx
0x1800104d8  xor     r13d, r13d
0x1800104db  lea     rcx, aLaunchinfsecti_6; "LaunchINFSectionEx: Param= %1\r\n"
0x1800104e2  mov     rdx, r8
0x1800104e5  mov     edi, r13d
0x1800104e8  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800104ed  mov     edx, 228h; uBytes
0x1800104f2  lea     ecx, [r13+40h]; uFlags
0x1800104f6  call    cs:__imp_LocalAlloc
0x1800104fc  mov     rbx, rax
0x1800104ff  test    rax, rax
0x180010502  jnz     short loc_180010529
0x180010504  mov     [rsp+78h+var_50], r13d; unsigned int
0x180010509  xor     r9d, r9d; unsigned __int16 *
0x18001050c  xor     r8d, r8d; unsigned __int16 *
0x18001050f  mov     [rsp+78h+var_58], 10h; unsigned int
0x180010517  mov     edx, 44Eh; uID
0x18001051c  mov     rcx, rsi; hWnd
0x18001051f  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180010524  jmp     loc_18001061D
0x180010529  mov     r12d, 22h ; '"'
0x18001052f  lea     r14, asc_18001E134; ","
0x180010536  mov     r8d, r12d; unsigned __int16
0x180010539  lea     rcx, [rsp+78h+arg_10]; unsigned __int16 **
0x180010541  mov     rdx, r14; unsigned __int16 *
0x180010544  lea     r15d, [r12-21h]
0x180010549  mov     r9d, r15d; int
0x18001054c  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x180010551  mov     r8d, r12d; unsigned __int16
0x180010554  mov     [rbx+8], rax
0x180010558  mov     r9d, r15d; int
0x18001055b  lea     rcx, [rsp+78h+arg_10]; unsigned __int16 **
0x180010563  mov     rdx, r14; unsigned __int16 *
0x180010566  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18001056b  mov     r8d, r12d; unsigned __int16
0x18001056e  mov     [rbx+10h], rax
0x180010572  mov     r9d, r15d; int
0x180010575  lea     rcx, [rsp+78h+arg_10]; unsigned __int16 **
0x18001057d  mov     rdx, r14; unsigned __int16 *
0x180010580  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x180010585  mov     r8d, r12d; unsigned __int16
0x180010588  mov     [rbx], rax
0x18001058b  mov     r9d, r15d; int
0x18001058e  lea     rcx, [rsp+78h+arg_10]; unsigned __int16 **
0x180010596  mov     rdx, r14; unsigned __int16 *
0x180010599  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18001059e  mov     r8d, r12d; unsigned __int16
0x1800105a1  lea     rcx, [rsp+78h+arg_10]; unsigned __int16 **
0x1800105a9  mov     r9d, r15d; int
0x1800105ac  mov     rdx, r14; unsigned __int16 *
0x1800105af  mov     rbp, rax
0x1800105b2  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x1800105b7  mov     cs:qword_180032318, rax
0x1800105be  test    rbp, rbp
0x1800105c1  jz      short loc_1800105D2
0x1800105c3  mov     rcx, rbp; String
0x1800105c6  call    cs:__imp__wtol
0x1800105cc  mov     [rbx+220h], eax
0x1800105d2  mov     rcx, [rbx]; unsigned __int16 *
0x1800105d5  test    rcx, rcx
0x1800105d8  jz      short loc_180010604
0x1800105da  cmp     [rcx], r13w
0x1800105de  jz      short loc_180010604
0x1800105e0  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x1800105e5  mov     r8, rcx; unsigned __int16 *
0x1800105e8  test    eax, eax
0x1800105ea  jz      short loc_18001063E
0x1800105ec  mov     edx, 104h; unsigned __int64
0x1800105f1  lea     rcx, [rbx+18h]; unsigned __int16 *
0x1800105f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800105fa  lea     rcx, [rbx+18h]; pszPath
0x1800105fe  call    cs:__imp_PathRemoveFileSpecW
0x180010604  xor     r8d, r8d; pReserved
0x180010607  mov     rdx, rbx; pCab
0x18001060a  mov     rcx, rsi; hwnd
0x18001060d  call    ExecuteCabW
0x180010612  mov     edi, eax
0x180010614  mov     rcx, rbx; hMem
0x180010617  call    cs:__imp_LocalFree
0x18001061d  mov     edx, edi
0x18001061f  lea     rcx, aLaunchinfsecti_7; "LaunchINFSectionEx: End hr=0x%1!x!\r\n"
0x180010626  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18001062b  mov     eax, edi
0x18001062d  add     rsp, 38h
0x180010631  pop     r15
0x180010633  pop     r14
0x180010635  pop     r13
0x180010637  pop     r12
0x180010639  pop     rdi
0x18001063a  pop     rsi
0x18001063b  pop     rbp
0x18001063c  pop     rbx
0x18001063d  retn
0x18001063e  mov     [rsp+78h+var_50], r13d; unsigned int
0x180010643  xor     r9d, r9d; unsigned __int16 *
0x180010646  mov     edx, 47Dh; uID
0x18001064b  mov     [rsp+78h+var_58], 10h; unsigned int
0x180010653  mov     rcx, rsi; hWnd
0x180010656  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18001065b  jmp     short loc_180010614
```
