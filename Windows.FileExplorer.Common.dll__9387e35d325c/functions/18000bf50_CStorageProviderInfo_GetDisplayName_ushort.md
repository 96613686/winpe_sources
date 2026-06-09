# CStorageProviderInfo::GetDisplayName(ushort * *)

- ea: `0x18000bf50`
- end: `0x18000c17f`
- name: `?GetDisplayName@CStorageProviderInfo@@UEAAJPEAPEAG@Z`
- size: `559`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000b9b0`
- `0x18000bc30`
- `0x18000bf50`
- `0x18000c188`
- `0x18000c694`
- `0x180037780`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c10e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c0da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c10e`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000c0fa`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18000c0fa`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHExpandEnvironmentStringsAlloc` at `0x18000c0c4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHExpandEnvironmentStringsAlloc` at `0x18000c0c4`

## string_xrefs

- `0x18000c064`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18000c15e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderInfo::GetDisplayName(CStorageProviderInfo *this, LPVOID *a2, unsigned int a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  int v10; // eax
  void *v11; // rcx
  __int64 v12; // rdx
  LPVOID v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17[2]; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h]
  WCHAR pszOutBuf[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  pv = 0;
  v19 = 0;
  v20 = 0;
  v5 = (_QWORD *)((char *)this + 360);
  if ( !*((_QWORD *)this + 39) || !*v5 || (v6 = *((_QWORD *)this + 48)) == 0 )
  {
    if ( *v5 )
    {
      if ( *((_QWORD *)this + 48) )
      {
LABEL_14:
        v19 = -1;
        v20 = -1;
        v8 = SHExpandEnvironmentStringsAlloc(*((_QWORD *)this + 15), &pv);
        if ( v8 < 0 )
          goto LABEL_15;
        if ( SHLoadIndirectString((PCWSTR)pv, pszOutBuf, 0x104u, 0) < 0 )
          goto LABEL_23;
        v13 = pv;
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v19 = -1;
        v20 = -1;
        v8 = _AllocString<CTCoAllocPolicy>(v13, v12, pszOutBuf, &pv);
        if ( v8 < 0 )
        {
LABEL_15:
          v11 = pv;
        }
        else
        {
LABEL_23:
          v14 = (unsigned __int16 *)pv;
          v11 = 0;
          pv = 0;
          v20 = 0;
          v19 = 0;
          *a2 = v14;
        }
LABEL_16:
        if ( v11 )
          CoTaskMemFree(v11);
        return (unsigned int)v8;
      }
    }
    else if ( !*((_QWORD *)this + 48) )
    {
      goto LABEL_14;
    }
    wil::details::in1diag3::Log_Hr(retaddr, a2, a3, (const char *)0x8000FFFFLL, v15);
    goto LABEL_14;
  }
  if ( *((_QWORD *)this + 42) )
  {
    *(_QWORD *)v17 = *((_QWORD *)this + 42);
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &pv,
            g_hInst,
            51568);
    v8 = v10;
    if ( v10 >= 0 )
      goto LABEL_9;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v10,
      v17[0]);
    v11 = pv;
    goto LABEL_16;
  }
  v16 = v6;
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
         &pv,
         g_hInst,
         51584);
  v8 = v7;
  if ( v7 >= 0 )
  {
LABEL_9:
    *a2 = pv;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E4,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v7,
    v16);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bf50  mov     [rsp-8+arg_10], rbx
0x18000bf55  mov     [rsp-8+arg_18], rsi
0x18000bf5a  push    rbp
0x18000bf5b  push    rdi
0x18000bf5c  push    r14
0x18000bf5e  lea     rbp, [rsp-170h]
0x18000bf66  sub     rsp, 270h
0x18000bf6d  mov     rax, cs:__security_cookie
0x18000bf74  xor     rax, rsp
0x18000bf77  mov     [rbp+180h+var_20], rax
0x18000bf7e  mov     rdi, rdx
0x18000bf81  mov     rbx, rcx
0x18000bf84  xor     esi, esi
0x18000bf86  mov     [rdx], rsi
0x18000bf89  mov     [rsp+280h+pv], rsi
0x18000bf8e  mov     [rsp+280h+var_248], rsi
0x18000bf93  mov     [rsp+280h+var_240], rsi
0x18000bf98  lea     rax, [rcx+168h]
0x18000bf9f  cmp     [rcx+138h], rsi
0x18000bfa6  jz      short loc_18000BFB0
0x18000bfa8  mov     r9, [rax]
0x18000bfab  test    r9, r9
0x18000bfae  jnz     short loc_18000BFCB
0x18000bfb0  cmp     [rax], rsi
0x18000bfb3  jnz     loc_18000C07D
0x18000bfb9  cmp     [rbx+180h], rsi
0x18000bfc0  jnz     loc_18000C086
0x18000bfc6  jmp     loc_18000C0AD
0x18000bfcb  mov     rcx, [rcx+180h]
0x18000bfd2  test    rcx, rcx
0x18000bfd5  jz      short loc_18000BFB0
0x18000bfd7  mov     rax, [rbx+150h]
0x18000bfde  mov     rdx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18000bfe5  test    rax, rax
0x18000bfe8  jnz     short loc_18000C03A
0x18000bfea  mov     qword ptr [rsp+280h+var_260], rcx; int
0x18000bfef  mov     r8d, 0C980h
0x18000bff5  lea     rcx, [rsp+280h+pv]
0x18000bffa  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18000bfff  mov     ebx, eax
0x18000c001  test    eax, eax
0x18000c003  js      loc_18000C154
0x18000c009  mov     rax, [rsp+280h+pv]
0x18000c00e  mov     [rdi], rax
0x18000c011  xor     eax, eax
0x18000c013  mov     rcx, [rbp+180h+var_20]
0x18000c01a  xor     rcx, rsp; StackCookie
0x18000c01d  call    __security_check_cookie
0x18000c022  lea     r11, [rsp+280h+var_10]
0x18000c02a  mov     rbx, [r11+30h]
0x18000c02e  mov     rsi, [r11+38h]
0x18000c032  mov     rsp, r11
0x18000c035  pop     r14
0x18000c037  pop     rdi
0x18000c038  pop     rbp
0x18000c039  retn
0x18000c03a  mov     [rsp+280h+var_258], rcx
0x18000c03f  mov     qword ptr [rsp+280h+var_260], rax; int
0x18000c044  mov     r8d, 0C970h
0x18000c04a  lea     rcx, [rsp+280h+pv]
0x18000c04f  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18000c054  mov     ebx, eax
0x18000c056  test    eax, eax
0x18000c058  jns     short loc_18000C009
0x18000c05a  mov     rcx, [rbp+188h]; this
0x18000c061  mov     r9d, eax; char *
0x18000c064  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000c06b  mov     edx, 1DEh; void *
0x18000c070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c075  nop
0x18000c076  mov     rcx, [rsp+280h+pv]
0x18000c07b  jmp     short loc_18000C0D5
0x18000c07d  cmp     [rbx+180h], rsi
0x18000c084  jnz     short loc_18000C0AD
0x18000c086  mov     rcx, [rbp+188h]; this
0x18000c08d  mov     r9d, 8000FFFFh; char *
0x18000c093  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c098  mov     rcx, [rsp+280h+pv]; pv
0x18000c09d  test    rcx, rcx
0x18000c0a0  jz      short loc_18000C0AD
0x18000c0a2  call    cs:__imp_CoTaskMemFree
0x18000c0a8  mov     [rsp+280h+pv], rsi
0x18000c0ad  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c0b1  mov     [rsp+280h+var_248], r14
0x18000c0b6  mov     [rsp+280h+var_240], r14
0x18000c0bb  lea     rdx, [rsp+280h+pv]
0x18000c0c0  mov     rcx, [rbx+78h]
0x18000c0c4  call    cs:__imp_SHExpandEnvironmentStringsAlloc
0x18000c0ca  mov     ebx, eax
0x18000c0cc  test    eax, eax
0x18000c0ce  jns     short loc_18000C0E7
0x18000c0d0  mov     rcx, [rsp+280h+pv]; pv
0x18000c0d5  test    rcx, rcx
0x18000c0d8  jz      short loc_18000C0E0
0x18000c0da  call    cs:__imp_CoTaskMemFree
0x18000c0e0  mov     eax, ebx
0x18000c0e2  jmp     loc_18000C013
0x18000c0e7  xor     r9d, r9d; ppvReserved
0x18000c0ea  mov     r8d, 104h; cchOutBuf
0x18000c0f0  lea     rdx, [rsp+280h+pszOutBuf]; pszOutBuf
0x18000c0f5  mov     rcx, [rsp+280h+pv]; pszSource
0x18000c0fa  call    cs:__imp_SHLoadIndirectString
0x18000c100  test    eax, eax
0x18000c102  js      short loc_18000C138
0x18000c104  mov     rcx, [rsp+280h+pv]; pv
0x18000c109  test    rcx, rcx
0x18000c10c  jz      short loc_18000C119
0x18000c10e  call    cs:__imp_CoTaskMemFree
0x18000c114  mov     [rsp+280h+pv], rsi
0x18000c119  mov     [rsp+280h+var_248], r14
0x18000c11e  mov     [rsp+280h+var_240], r14
0x18000c123  lea     r9, [rsp+280h+pv]
0x18000c128  lea     r8, [rsp+280h+pszOutBuf]
0x18000c12d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000c132  mov     ebx, eax
0x18000c134  test    eax, eax
0x18000c136  js      short loc_18000C0D0
0x18000c138  mov     rax, [rsp+280h+pv]
0x18000c13d  mov     rcx, rsi
0x18000c140  mov     [rsp+280h+pv], rcx
0x18000c145  mov     [rsp+280h+var_240], rsi
0x18000c14a  mov     [rsp+280h+var_248], rsi
0x18000c14f  mov     [rdi], rax
0x18000c152  jmp     short loc_18000C0D5
0x18000c154  mov     rcx, [rbp+188h]; this
0x18000c15b  mov     r9d, ebx; char *
0x18000c15e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000c165  mov     edx, 1E4h; void *
0x18000c16a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c16f  nop
0x18000c170  lea     rcx, [rsp+280h+pv]
0x18000c175  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000c17a  jmp     loc_18000C0E0
```
