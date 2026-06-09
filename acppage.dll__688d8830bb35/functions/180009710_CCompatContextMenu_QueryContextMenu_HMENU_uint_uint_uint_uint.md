# CCompatContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180009710`
- end: `0x180009912`
- name: `?QueryContextMenu@CCompatContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `514`
- prototype: `__int64 __fastcall(CCompatContextMenu *this, HMENU, UINT, unsigned int, unsigned int, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009710`
- `0x18000a0e4`
- `0x18000e324`
- `0x18001623a`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `ntdll!RtlIsPartialPlaceholder` at `0x180009841`
- `ntdll!RtlIsPartialPlaceholder` at `0x180009841`
- `KERNEL32!GetLastError` at `0x180009816`
- `KERNEL32!GetLastError` at `0x180009875`
- `KERNEL32!GetLastError` at `0x180009816`
- `KERNEL32!GetLastError` at `0x180009875`
- `KERNEL32!FindFirstFileW` at `0x180009807`
- `KERNEL32!FindFirstFileW` at `0x180009807`
- `KERNEL32!FindClose` at `0x1800098d3`
- `KERNEL32!FindClose` at `0x1800098d3`
- `USER32!LoadStringW` at `0x18000986b`
- `USER32!LoadStringW` at `0x18000986b`
- `USER32!InsertMenuW` at `0x1800098b4`
- `USER32!InsertMenuW` at `0x1800098b4`
- `SHELL32!SHGetItemFromDataObject` at `0x18000977c`
- `SHELL32!SHGetItemFromDataObject` at `0x18000977c`
- `ole32!CoTaskMemFree` at `0x1800098c4`
- `ole32!CoTaskMemFree` at `0x1800098c4`
- `sfc!SfcIsFileProtected` at `0x1800097d1`
- `sfc!SfcIsFileProtected` at `0x1800097d1`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::QueryContextMenu(
        CCompatContextMenu *this,
        HMENU a2,
        UINT a3,
        unsigned int a4,
        unsigned int a5,
        char a6)
{
  UINT_PTR v7; // r12
  __int64 FirstFileW; // rdi
  int v11; // ebx
  struct IUnknown *v12; // rdx
  struct IUnknown *v13; // rdx
  unsigned int v14; // r8d
  signed int LastError; // eax
  signed int v16; // eax
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[400]; // [rsp+290h] [rbp+190h] BYREF

  v7 = a4;
  ppv = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v11 = SHGetItemFromDataObject(
          *((IDataObject **)this + 74),
          DOGIF_ONLY_IF_ONE,
          &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
          &ppv);
  if ( v11 < 0 )
    goto LABEL_24;
  v12 = (struct IUnknown *)*((_QWORD *)this + 75);
  v18 = 260;
  if ( !(unsigned int)RetrieveAndValidateFile((struct IShellItem *)ppv, v12, (unsigned __int16 *)this + 36, &v18)
    || (*((_WORD *)this + 36) != 92 || *((_WORD *)this + 37) != 92) && SfcIsFileProtected(0, (LPCWSTR)this + 36) )
  {
    v11 = -2147467259;
    goto LABEL_24;
  }
  v18 = -1;
  if ( (int)SHMapUrlToZoneEx((const unsigned __int16 *)this + 36, v13, v14, &v18) >= 0 && v18 > 2 )
    goto LABEL_23;
  FirstFileW = (__int64)FindFirstFileW((LPCWSTR)this + 36, &FindFileData);
  if ( FirstFileW == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v11 = LastError;
    goto LABEL_24;
  }
  if ( (unsigned __int8)RtlIsPartialPlaceholder(FindFileData.dwFileAttributes, FindFileData.dwReserved0) )
  {
    v11 = -2147024891;
    goto LABEL_24;
  }
  if ( LoadStringW(g_hInstance, 0x7E6u, Buffer, 400) )
  {
    v11 = 1;
    if ( (a6 & 1) == 0 )
    {
      if ( InsertMenuW(a2, a3, 0x400u, v7, Buffer) )
        goto LABEL_24;
      goto LABEL_18;
    }
LABEL_23:
    v11 = 0;
    goto LABEL_24;
  }
LABEL_18:
  v16 = GetLastError();
  v11 = v16;
  if ( v16 > 0 )
    v11 = (unsigned __int16)v16 | 0x80070000;
LABEL_24:
  CoTaskMemFree(0);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009710  push    rbp
0x180009712  push    rbx
0x180009713  push    rsi
0x180009714  push    rdi
0x180009715  push    r12
0x180009717  push    r14
0x180009719  push    r15
0x18000971b  lea     rbp, [rsp-4C0h]
0x180009723  sub     rsp, 5C0h
0x18000972a  mov     rax, cs:__security_cookie
0x180009731  xor     rax, rsp
0x180009734  mov     [rbp+4F0h+var_40], rax
0x18000973b  mov     r15d, r8d
0x18000973e  mov     r12d, r9d
0x180009741  mov     r14, rdx
0x180009744  mov     [rsp+5F0h+ppv], 0
0x18000974d  mov     rsi, rcx
0x180009750  xor     edx, edx; Val
0x180009752  mov     r8d, 250h; Size
0x180009758  lea     rcx, [rsp+5F0h+FindFileData]; void *
0x18000975d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009761  call    memset_0
0x180009766  mov     rcx, [rsi+250h]; pdtobj
0x18000976d  lea     r9, [rsp+5F0h+ppv]; ppv
0x180009772  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180009779  lea     edx, [rdi+9]; dwFlags
0x18000977c  call    cs:__imp_SHGetItemFromDataObject
0x180009782  mov     ebx, eax
0x180009784  test    eax, eax
0x180009786  js      loc_1800098C2
0x18000978c  mov     rdx, [rsi+258h]; struct IUnknown *
0x180009793  lea     rbx, [rsi+48h]
0x180009797  mov     rcx, [rsp+5F0h+ppv]; struct IShellItem *
0x18000979c  lea     r9, [rsp+5F0h+var_5C0]; unsigned int *
0x1800097a1  mov     r8, rbx; unsigned __int16 *
0x1800097a4  mov     [rsp+5F0h+var_5C0], 104h
0x1800097ac  call    ?RetrieveAndValidateFile@@YAHPEAUIShellItem@@PEAUIUnknown@@PEAGPEAK@Z; RetrieveAndValidateFile(IShellItem *,IUnknown *,ushort *,ulong *)
0x1800097b1  test    eax, eax
0x1800097b3  jnz     short loc_1800097BF
0x1800097b5  mov     ebx, 80004005h
0x1800097ba  jmp     loc_1800098C2
0x1800097bf  cmp     word ptr [rbx], 5Ch ; '\'
0x1800097c3  jnz     short loc_1800097CC
0x1800097c5  cmp     word ptr [rsi+4Ah], 5Ch ; '\'
0x1800097ca  jz      short loc_1800097DB
0x1800097cc  mov     rdx, rbx; ProtFileName
0x1800097cf  xor     ecx, ecx; RpcHandle
0x1800097d1  call    cs:__imp_SfcIsFileProtected
0x1800097d7  test    eax, eax
0x1800097d9  jnz     short loc_1800097B5
0x1800097db  lea     r9, [rsp+5F0h+var_5C0]; unsigned int *
0x1800097e0  mov     [rsp+5F0h+var_5C0], 0FFFFFFFFh
0x1800097e8  mov     rcx, rbx; unsigned __int16 *
0x1800097eb  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x1800097f0  test    eax, eax
0x1800097f2  js      short loc_1800097FF
0x1800097f4  cmp     [rsp+5F0h+var_5C0], 2
0x1800097f9  ja      loc_1800098C0
0x1800097ff  lea     rdx, [rsp+5F0h+FindFileData]; lpFindFileData
0x180009804  mov     rcx, rbx; lpFileName
0x180009807  call    cs:__imp_FindFirstFileW
0x18000980d  mov     rdi, rax
0x180009810  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009814  jnz     short loc_180009839
0x180009816  call    cs:__imp_GetLastError
0x18000981c  test    eax, eax
0x18000981e  jle     short loc_180009828
0x180009820  movzx   eax, ax
0x180009823  or      eax, 80070000h
0x180009828  mov     ebx, 80004005h
0x18000982d  test    eax, eax
0x18000982f  cmovns  eax, ebx
0x180009832  mov     ebx, eax
0x180009834  jmp     loc_1800098C2
0x180009839  mov     edx, [rsp+5F0h+FindFileData.dwReserved0]
0x18000983d  mov     ecx, [rsp+5F0h+FindFileData.dwFileAttributes]
0x180009841  call    cs:__imp_RtlIsPartialPlaceholder
0x180009847  test    al, al
0x180009849  jz      short loc_180009852
0x18000984b  mov     ebx, 80070005h
0x180009850  jmp     short loc_1800098C2
0x180009852  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180009859  lea     r8, [rbp+4F0h+Buffer]; lpBuffer
0x180009860  mov     r9d, 190h; cchBufferMax
0x180009866  mov     edx, 7E6h; uID
0x18000986b  call    cs:__imp_LoadStringW
0x180009871  test    eax, eax
0x180009873  jnz     short loc_18000988C
0x180009875  call    cs:__imp_GetLastError
0x18000987b  mov     ebx, eax
0x18000987d  test    eax, eax
0x18000987f  jle     short loc_1800098C2
0x180009881  movzx   ebx, ax
0x180009884  or      ebx, 80070000h
0x18000988a  jmp     short loc_1800098C2
0x18000988c  mov     ebx, 1
0x180009891  test    byte ptr [rbp+4F0h+arg_28], bl
0x180009897  jnz     short loc_1800098C0
0x180009899  lea     rax, [rbp+4F0h+Buffer]
0x1800098a0  mov     r9, r12; uIDNewItem
0x1800098a3  mov     r8d, 400h; uFlags
0x1800098a9  mov     [rsp+5F0h+lpNewItem], rax; lpNewItem
0x1800098ae  mov     edx, r15d; uPosition
0x1800098b1  mov     rcx, r14; hMenu
0x1800098b4  call    cs:__imp_InsertMenuW
0x1800098ba  test    eax, eax
0x1800098bc  jnz     short loc_1800098C2
0x1800098be  jmp     short loc_180009875
0x1800098c0  xor     ebx, ebx
0x1800098c2  xor     ecx, ecx; pv
0x1800098c4  call    cs:__imp_CoTaskMemFree
0x1800098ca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800098ce  jz      short loc_1800098D9
0x1800098d0  mov     rcx, rdi; hFindFile
0x1800098d3  call    cs:__imp_FindClose
0x1800098d9  mov     rcx, [rsp+5F0h+ppv]
0x1800098de  test    rcx, rcx
0x1800098e1  jz      short loc_1800098EF
0x1800098e3  mov     rax, [rcx]
0x1800098e6  mov     rax, [rax+10h]
0x1800098ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ef  mov     eax, ebx
0x1800098f1  mov     rcx, [rbp+4F0h+var_40]
0x1800098f8  xor     rcx, rsp; StackCookie
0x1800098fb  call    __security_check_cookie
0x180009900  add     rsp, 5C0h
0x180009907  pop     r15
0x180009909  pop     r14
0x18000990b  pop     r12
0x18000990d  pop     rdi
0x18000990e  pop     rsi
0x18000990f  pop     rbx
0x180009910  pop     rbp
0x180009911  retn
```
