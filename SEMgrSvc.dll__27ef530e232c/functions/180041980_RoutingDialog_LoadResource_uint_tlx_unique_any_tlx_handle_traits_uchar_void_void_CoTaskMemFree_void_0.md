# RoutingDialog::LoadResource(uint,tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>> *)

- ea: `0x180041980`
- end: `0x180041aba`
- name: `?LoadResource@RoutingDialog@@MEAAJIPEAV?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000d4ec`
- `0x180041980`
- `0x18008b8b4`
- `0x18008c140`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800419fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800419fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a80`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800419e0`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800419e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RoutingDialog::LoadResource(__int64 a1, unsigned int a2, unsigned __int16 *a3, int a4)
{
  HRESULT v7; // ebx
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // r8
  struct PriHelper *v10; // rax
  PriHelper *v11; // rsi
  void *v12; // rcx
  signed int LastError; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v16[264]; // [rsp+30h] [rbp-238h] BYREF

  v7 = 0;
  if ( !*(_QWORD *)(a1 + 304) )
  {
    memset_0(v16, 0, 0x208u);
    ppszPath = 0;
    v7 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
    if ( v7 < 0
      || (v7 = StringCchPrintfW(v16, 0x104u, L"%s\\SystemResources\\Windows-NFC-SEManagement", ppszPath), v7 < 0) )
    {
LABEL_3:
      if ( ppszPath )
        CoTaskMemFree(ppszPath);
      return (unsigned int)v7;
    }
    v10 = PriHelper::Create(v8, v16, v9);
    *(_QWORD *)(a1 + 304) = v10;
    if ( !v10 )
    {
      v7 = -2147467259;
      goto LABEL_3;
    }
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
  }
  v11 = *(PriHelper **)(a1 + 304);
  v12 = *(void **)a3;
  *(_QWORD *)a3 = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  if ( !(unsigned int)PriHelper::LoadStringW(v11, a2, a3, a4) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180041980  mov     [rsp+arg_18], rbx
0x180041985  push    rbp
0x180041986  push    rsi
0x180041987  push    rdi
0x180041988  sub     rsp, 250h
0x18004198f  mov     rax, cs:__security_cookie
0x180041996  xor     rax, rsp
0x180041999  mov     [rsp+268h+var_28], rax
0x1800419a1  mov     rdi, r8
0x1800419a4  mov     ebp, edx
0x1800419a6  mov     rsi, rcx
0x1800419a9  xor     ebx, ebx
0x1800419ab  cmp     [rcx+130h], rbx
0x1800419b2  jnz     loc_180041A53
0x1800419b8  xor     edx, edx; Val
0x1800419ba  mov     r8d, 208h; Size
0x1800419c0  lea     rcx, [rsp+268h+var_238]; void *
0x1800419c5  call    memset_0
0x1800419ca  mov     [rsp+268h+ppszPath], rbx
0x1800419cf  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x1800419d4  xor     r8d, r8d; hToken
0x1800419d7  xor     edx, edx; dwFlags
0x1800419d9  lea     rcx, FOLDERID_Windows; rfid
0x1800419e0  call    cs:__imp_SHGetKnownFolderPath
0x1800419e6  mov     ebx, eax
0x1800419e8  test    eax, eax
0x1800419ea  jns     short loc_180041A05
0x1800419ec  mov     rcx, [rsp+268h+ppszPath]; pv
0x1800419f1  test    rcx, rcx
0x1800419f4  jz      loc_180041A95
0x1800419fa  call    cs:__imp_CoTaskMemFree
0x180041a00  jmp     loc_180041A95
0x180041a05  mov     r9, [rsp+268h+ppszPath]
0x180041a0a  lea     r8, aSSystemresourc; "%s\\SystemResources\\Windows-NFC-SEMana"...
0x180041a11  mov     edx, 104h; unsigned __int64
0x180041a16  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180041a1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041a20  mov     ebx, eax
0x180041a22  test    eax, eax
0x180041a24  js      short loc_1800419EC
0x180041a26  lea     rdx, [rsp+268h+var_238]; unsigned __int16 *
0x180041a2b  call    ?Create@PriHelper@@SAPEAV1@PEBG00@Z; PriHelper::Create(ushort const *,ushort const *,ushort const *)
0x180041a30  mov     [rsi+130h], rax
0x180041a37  test    rax, rax
0x180041a3a  jnz     short loc_180041A43
0x180041a3c  mov     ebx, 80004005h
0x180041a41  jmp     short loc_1800419EC
0x180041a43  mov     rcx, [rsp+268h+ppszPath]; pv
0x180041a48  test    rcx, rcx
0x180041a4b  jz      short loc_180041A53
0x180041a4d  call    cs:__imp_CoTaskMemFree
0x180041a53  mov     rsi, [rsi+130h]
0x180041a5a  mov     rcx, [rdi]; pv
0x180041a5d  mov     qword ptr [rdi], 0
0x180041a64  test    rcx, rcx
0x180041a67  jz      short loc_180041A6F
0x180041a69  call    cs:__imp_CoTaskMemFree
0x180041a6f  mov     r8, rdi; unsigned __int16 *
0x180041a72  mov     edx, ebp; unsigned int
0x180041a74  mov     rcx, rsi; this
0x180041a77  call    ?LoadStringW@PriHelper@@QEAAHIPEAGH@Z; PriHelper::LoadStringW(uint,ushort *,int)
0x180041a7c  test    eax, eax
0x180041a7e  jnz     short loc_180041A95
0x180041a80  call    cs:__imp_GetLastError
0x180041a86  mov     ebx, eax
0x180041a88  test    eax, eax
0x180041a8a  jle     short loc_180041A95
0x180041a8c  movzx   ebx, ax
0x180041a8f  or      ebx, 80070000h
0x180041a95  mov     eax, ebx
0x180041a97  mov     rcx, [rsp+268h+var_28]
0x180041a9f  xor     rcx, rsp; StackCookie
0x180041aa2  call    __security_check_cookie
0x180041aa7  mov     rbx, [rsp+268h+arg_18]
0x180041aaf  add     rsp, 250h
0x180041ab6  pop     rdi
0x180041ab7  pop     rsi
0x180041ab8  pop     rbp
0x180041ab9  retn
```
