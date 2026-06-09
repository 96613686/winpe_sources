# IsPortableDeviceAPIPresent(void)

- ea: `0x1800036f0`
- end: `0x1800038bf`
- name: `?IsPortableDeviceAPIPresent@@YAHXZ`
- size: `463`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800018c0`
- `0x1800031b0`

## callees

- `0x1800036f0`
- `0x180007f28`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000371a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000371a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000382f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000382f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003861`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800037d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800037d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003821`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003821`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000377e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000377e`

## string_xrefs

- `0x180003713`: `PortableDeviceApi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 IsPortableDeviceAPIPresent(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rbx
  int v2; // esi
  int LastError; // eax
  CPnPNotification *v4; // rcx
  __int64 v5; // rdx
  LPVOID v6; // rcx
  signed int v7; // eax
  bool v8; // sf
  signed int v9; // eax
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  ppv = 0;
  Library = LoadLibraryExW(L"PortableDeviceApi.dll", 0, 0x800u);
  if ( !Library )
  {
    v2 = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 10;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, (unsigned int)LastError);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  LastError = CoInitializeEx(0, 0);
  if ( LastError < 0 )
  {
    v2 = 0;
    if ( LastError == -2147417850 )
      goto LABEL_15;
  }
  else
  {
    v2 = 1;
  }
  if ( LastError > -1 )
  {
LABEL_15:
    LastError = CoCreateInstance(&CLSID_PortableDevice, 0, 1u, &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c, &ppv);
    if ( LastError >= 0 )
    {
      v0 = 1;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 12;
        goto LABEL_7;
      }
    }
    goto LABEL_20;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 11;
    goto LABEL_7;
  }
LABEL_20:
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v2 )
    CoUninitialize();
  if ( Library && !FreeLibrary(Library) )
  {
    v7 = GetLastError();
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( v8
      && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
        (unsigned int)v9);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x1800036f0  mov     [rsp+arg_8], rbx
0x1800036f5  mov     [rsp+arg_10], rbp
0x1800036fa  push    rsi
0x1800036fb  push    rdi
0x1800036fc  push    r14
0x1800036fe  sub     rsp, 30h
0x180003702  xor     ebp, ebp
0x180003704  mov     edi, ebp
0x180003706  mov     [rsp+48h+arg_0], rbp
0x18000370b  xor     edx, edx; hFile
0x18000370d  mov     r8d, 800h; dwFlags
0x180003713  lea     rcx, LibFileName; "PortableDeviceApi.dll"
0x18000371a  call    cs:__imp_LoadLibraryExW
0x180003720  mov     rbx, rax
0x180003723  lea     r14, WPP_GLOBAL_Control
0x18000372a  test    rax, rax
0x18000372d  jnz     short loc_18000377A
0x18000372f  mov     esi, ebp
0x180003731  call    cs:__imp_GetLastError
0x180003737  test    eax, eax
0x180003739  jle     short loc_180003743
0x18000373b  movzx   eax, ax
0x18000373e  or      eax, 80070000h
0x180003743  mov     rcx, cs:WPP_GLOBAL_Control
0x18000374a  cmp     rcx, r14
0x18000374d  jz      loc_180003801
0x180003753  test    byte ptr [rcx+1Ch], 2
0x180003757  jz      loc_180003801
0x18000375d  mov     edx, 0Ah
0x180003762  mov     r9d, eax
0x180003765  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x18000376c  mov     rcx, [rcx+10h]
0x180003770  call    WPP_SF_d
0x180003775  jmp     loc_180003801
0x18000377a  xor     edx, edx; dwCoInit
0x18000377c  xor     ecx, ecx; pvReserved
0x18000377e  call    cs:__imp_CoInitializeEx
0x180003784  test    eax, eax
0x180003786  js      short loc_18000378F
0x180003788  mov     esi, 1
0x18000378d  jmp     short loc_180003798
0x18000378f  mov     esi, ebp
0x180003791  cmp     eax, 80010106h
0x180003796  jz      short loc_1800037B6
0x180003798  cmp     eax, 0FFFFFFFFh
0x18000379b  jg      short loc_1800037B6
0x18000379d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037a4  cmp     rcx, r14
0x1800037a7  jz      short loc_180003801
0x1800037a9  test    byte ptr [rcx+1Ch], 2
0x1800037ad  jz      short loc_180003801
0x1800037af  mov     edx, 0Bh
0x1800037b4  jmp     short loc_180003762
0x1800037b6  lea     rax, [rsp+48h+arg_0]
0x1800037bb  mov     [rsp+48h+ppv], rax; ppv
0x1800037c0  lea     r9, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c; riid
0x1800037c7  xor     edx, edx; pUnkOuter
0x1800037c9  mov     r8d, 1; dwClsContext
0x1800037cf  lea     rcx, CLSID_PortableDevice; rclsid
0x1800037d6  call    cs:__imp_CoCreateInstance
0x1800037dc  test    eax, eax
0x1800037de  jns     short loc_1800037FC
0x1800037e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037e7  cmp     rcx, r14
0x1800037ea  jz      short loc_180003801
0x1800037ec  test    byte ptr [rcx+1Ch], 2
0x1800037f0  jz      short loc_180003801
0x1800037f2  mov     edx, 0Ch
0x1800037f7  jmp     loc_180003762
0x1800037fc  mov     edi, 1
0x180003801  mov     rcx, [rsp+48h+arg_0]
0x180003806  test    rcx, rcx
0x180003809  jz      short loc_18000381D
0x18000380b  mov     [rsp+48h+arg_0], rbp
0x180003810  mov     rax, [rcx]
0x180003813  mov     rax, [rax+10h]
0x180003817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381c  nop
0x18000381d  test    esi, esi
0x18000381f  jz      short loc_180003827
0x180003821  call    cs:__imp_CoUninitialize
0x180003827  test    rbx, rbx
0x18000382a  jz      short loc_180003893
0x18000382c  mov     rcx, rbx; hLibModule
0x18000382f  call    cs:__imp_FreeLibrary
0x180003835  test    eax, eax
0x180003837  jnz     short loc_180003893
0x180003839  call    cs:__imp_GetLastError
0x18000383f  test    eax, eax
0x180003841  jle     short loc_18000384D
0x180003843  movzx   eax, ax
0x180003846  or      eax, 80070000h
0x18000384b  test    eax, eax
0x18000384d  jns     short loc_180003893
0x18000384f  mov     rax, cs:WPP_GLOBAL_Control
0x180003856  cmp     rax, r14
0x180003859  jz      short loc_180003893
0x18000385b  test    byte ptr [rax+1Ch], 2
0x18000385f  jz      short loc_180003893
0x180003861  call    cs:__imp_GetLastError
0x180003867  test    eax, eax
0x180003869  jle     short loc_180003873
0x18000386b  movzx   eax, ax
0x18000386e  or      eax, 80070000h
0x180003873  mov     edx, 0Dh
0x180003878  mov     r9d, eax
0x18000387b  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003882  mov     rcx, cs:WPP_GLOBAL_Control
0x180003889  mov     rcx, [rcx+10h]
0x18000388d  call    WPP_SF_d
0x180003892  nop
0x180003893  mov     rcx, [rsp+48h+arg_0]
0x180003898  test    rcx, rcx
0x18000389b  jz      short loc_1800038AA
0x18000389d  mov     rdx, [rcx]
0x1800038a0  mov     rax, [rdx+10h]
0x1800038a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a9  nop
0x1800038aa  mov     eax, edi
0x1800038ac  mov     rbx, [rsp+48h+arg_8]
0x1800038b1  mov     rbp, [rsp+48h+arg_10]
0x1800038b6  add     rsp, 30h
0x1800038ba  pop     r14
0x1800038bc  pop     rdi
0x1800038bd  pop     rsi
0x1800038be  retn
```
