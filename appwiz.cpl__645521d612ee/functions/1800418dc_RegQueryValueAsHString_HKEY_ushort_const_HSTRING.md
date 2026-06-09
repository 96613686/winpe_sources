# RegQueryValueAsHString(HKEY__ *,ushort const *,HSTRING__ * *)

- ea: `0x1800418dc`
- end: `0x180041a67`
- name: `?RegQueryValueAsHString@@YAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, HSTRING *string)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180041190`

## callees

- `0x180002fec`
- `0x180007560`
- `0x1800418dc`
- `0x180041d00`
- `0x180044bd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041924`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800419eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041924`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800419eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041a1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041a1d`

## string_xrefs

- `0x1800419a0`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x180041a2e`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`

## pseudocode

```c
int __fastcall RegQueryValueAsHString(HKEY hkey, LPCWSTR lpValue, HSTRING *string)
{
  unsigned int ValueW; // eax
  unsigned int v7; // r8d
  __int64 v9; // rbx
  unsigned __int64 v10; // rax
  void *pvData; // rdi
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // r8d
  HRESULT v15; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-48h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF
  DWORD v20; // [rsp+88h] [rbp+20h] BYREF

  *string = 0;
  v20 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, &v20, 0, &pcbData);
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x21, v7, (const char *)ValueW, pdwType);
  if ( v20 != 1 || pcbData < 2 )
    return 0;
  v9 = -1;
  v10 = 2 * ((unsigned __int64)(pcbData + 1) >> 1);
  if ( !is_mul_ok((unsigned __int64)(pcbData + 1) >> 1, 2u) )
    v10 = -1;
  pvData = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  if ( pvData )
  {
    v13 = RegGetValueW(hkey, 0, lpValue, 0xFFFFu, &v20, pvData, &pcbData);
    if ( v13 )
    {
      v12 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x28, v14, (const char *)v13, pdwTypea);
    }
    else
    {
      do
        ++v9;
      while ( *((_WORD *)pvData + v9) );
      v15 = WindowsCreateString((PCNZWCH)pvData, v9, string);
      v12 = v15;
      if ( v15 >= 0 )
        v12 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29,
          (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
          (const char *)(unsigned int)v15,
          pdwTypea);
    }
    operator delete(pvData);
  }
  else
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
      (const char *)0x8007000ELL,
      pdwType);
  }
  return v12;
}

```

## disassembly

```asm
0x1800418dc  mov     r11, rsp
0x1800418df  mov     [r11+8], rbx
0x1800418e3  push    rbp
0x1800418e4  push    rsi
0x1800418e5  push    rdi
0x1800418e6  push    r14
0x1800418e8  push    r15
0x1800418ea  sub     rsp, 40h
0x1800418ee  xor     r15d, r15d
0x1800418f1  lea     rax, [r11+18h]
0x1800418f5  mov     [r11-38h], rax
0x1800418f9  mov     r14, r8
0x1800418fc  mov     [r8], r15
0x1800418ff  lea     rax, [r11+20h]
0x180041903  mov     r8, rdx; lpValue
0x180041906  mov     [r11-40h], r15
0x18004190a  mov     rsi, rdx
0x18004190d  mov     [r11-48h], rax
0x180041911  xor     edx, edx; lpSubKey
0x180041913  mov     [r11+20h], r15d
0x180041917  mov     r9d, 0FFFFh; dwFlags
0x18004191d  mov     [r11+18h], r15d
0x180041921  mov     rbp, rcx
0x180041924  call    cs:__imp_RegGetValueW
0x18004192a  cmp     eax, 2
0x18004192d  jz      loc_180041A54
0x180041933  test    eax, eax
0x180041935  jz      short loc_18004194D
0x180041937  mov     rcx, [rsp+68h]; this
0x18004193c  lea     edx, [r15+21h]; void *
0x180041940  mov     r9d, eax; char *
0x180041943  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041948  jmp     loc_180041A56
0x18004194d  cmp     [rsp+68h+arg_18], 1
0x180041955  jnz     loc_180041A54
0x18004195b  mov     ecx, [rsp+68h+arg_10]
0x180041962  cmp     ecx, 2
0x180041965  jb      loc_180041A54
0x18004196b  lea     edx, [rcx+1]
0x18004196e  mov     eax, 2
0x180041973  shr     rdx, 1
0x180041976  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004197d  mul     rdx
0x180041980  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041987  cmovb   rax, rbx
0x18004198b  mov     rcx, rax; unsigned __int64
0x18004198e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041993  mov     rdi, rax
0x180041996  test    rax, rax
0x180041999  jnz     short loc_1800419BE
0x18004199b  mov     rcx, [rsp+68h]; this
0x1800419a0  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x1800419a7  mov     ebx, 8007000Eh
0x1800419ac  lea     edx, [rax+26h]; void *
0x1800419af  mov     r9d, ebx; char *
0x1800419b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800419b7  mov     eax, ebx
0x1800419b9  jmp     loc_180041A56
0x1800419be  lea     rax, [rsp+68h+arg_10]
0x1800419c6  mov     r9d, 0FFFFh; dwFlags
0x1800419cc  mov     [rsp+68h+pcbData], rax; pcbData
0x1800419d1  mov     r8, rsi; lpValue
0x1800419d4  lea     rax, [rsp+68h+arg_18]
0x1800419dc  mov     [rsp+68h+pvData], rdi; pvData
0x1800419e1  xor     edx, edx; lpSubKey
0x1800419e3  mov     [rsp+68h+pdwType], rax; int
0x1800419e8  mov     rcx, rbp; hkey
0x1800419eb  call    cs:__imp_RegGetValueW
0x1800419f1  test    eax, eax
0x1800419f3  jz      short loc_180041A0B
0x1800419f5  mov     rcx, [rsp+68h]; this
0x1800419fa  mov     r9d, eax; char *
0x1800419fd  mov     edx, 28h ; '('; void *
0x180041a02  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041a07  mov     ebx, eax
0x180041a09  jmp     short loc_180041A47
0x180041a0b  inc     rbx
0x180041a0e  cmp     [rdi+rbx*2], r15w
0x180041a13  jnz     short loc_180041A0B
0x180041a15  mov     r8, r14; string
0x180041a18  mov     edx, ebx; length
0x180041a1a  mov     rcx, rdi; sourceString
0x180041a1d  call    cs:__imp_WindowsCreateString
0x180041a23  mov     ebx, eax
0x180041a25  test    eax, eax
0x180041a27  jns     short loc_180041A44
0x180041a29  mov     rcx, [rsp+68h]; this
0x180041a2e  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041a35  mov     r9d, eax; char *
0x180041a38  mov     edx, 29h ; ')'; void *
0x180041a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a42  jmp     short loc_180041A47
0x180041a44  mov     ebx, r15d
0x180041a47  mov     rcx, rdi; lpMem
0x180041a4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041a4f  jmp     loc_1800419B7
0x180041a54  xor     eax, eax
0x180041a56  mov     rbx, [rsp+68h+arg_0]
0x180041a5b  add     rsp, 40h
0x180041a5f  pop     r15
0x180041a61  pop     r14
0x180041a63  pop     rdi
0x180041a64  pop     rsi
0x180041a65  pop     rbp
0x180041a66  retn
```
