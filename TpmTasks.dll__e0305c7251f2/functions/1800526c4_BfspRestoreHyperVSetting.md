# BfspRestoreHyperVSetting

- ea: `0x1800526c4`
- end: `0x1800528a0`
- name: `BfspRestoreHyperVSetting`
- size: `476`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004d7e4`

## callees

- `0x1800078b0`
- `0x180008598`
- `0x1800525b0`
- `0x1800526c4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180052791`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180052791`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052862`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052862`
- `bcd!BcdSetElementData` at `0x180052825`
- `bcd!BcdSetElementData` at `0x180052825`
- `bcd!BcdCloseObject` at `0x180052872`
- `bcd!BcdCloseObject` at `0x180052872`
- `bcd!BcdOpenObject` at `0x1800527fb`
- `bcd!BcdOpenObject` at `0x1800527fb`

## pseudocode

```c
__int64 __fastcall BfspRestoreHyperVSetting(__int64 a1, const wchar_t *a2, __int64 a3, __int16 a4)
{
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  wchar_t *v11; // rcx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE hLibModule[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+70h] [rbp-90h]
  void (*v20)(void); // [rsp+80h] [rbp-80h]
  wchar_t Destination[264]; // [rsp+90h] [rbp-70h] BYREF

  v20 = 0;
  v16 = 0;
  *(_OWORD *)hLibModule = 0;
  v13 = 0;
  v18 = 0;
  v14 = 0;
  v19 = 0;
  v15 = 0;
  v8 = BfspOpenDismApi((__int64)hLibModule);
  if ( v8 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))hLibModule[1])(0, 0, 0);
    if ( v9 < 0
      || ((a4 & 0x8000) == 0
        ? (wcscpy_s(Destination, 0x104u, a2), *wcsrchr(Destination, 0x5Cu) = 0, v11 = Destination)
        : (v11 = L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}"),
          (v9 = ((__int64 (__fastcall *)(wchar_t *, _QWORD, _QWORD, unsigned int *))v18)(v11, 0, 0, &v13), v9 < 0)
       || (v9 = (*((__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD, __int64 *))&v18 + 1))(
                  v13,
                  L"Microsoft-Hyper-V-Hypervisor",
                  0,
                  0,
                  &v14),
           v9 < 0)) )
    {
      v10 = (unsigned __int16)v9;
      if ( !(_WORD)v9 )
        v10 = 31;
      v8 = v10 | 0xC0070000;
    }
    else if ( *(_DWORD *)(v14 + 8) == 4 )
    {
      v8 = BcdOpenObject(a1, a3, &v15);
      if ( v8 >= 0 )
      {
        v16 = 1;
        v8 = BcdSetElementData(v15, 620757232, &v16, 8);
      }
    }
    if ( v14 )
      ((void (*)(void))v19)();
    (*((void (__fastcall **)(_QWORD))&v19 + 1))(v13);
    v20();
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
  }
  if ( v15 )
    BcdCloseObject(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800526c4  mov     [rsp-8+arg_18], rbx
0x1800526c9  push    rbp
0x1800526ca  push    rsi
0x1800526cb  push    rdi
0x1800526cc  push    r14
0x1800526ce  push    r15
0x1800526d0  lea     rbp, [rsp-1B0h]
0x1800526d8  sub     rsp, 2B0h
0x1800526df  mov     rax, cs:__security_cookie
0x1800526e6  xor     rax, rsp
0x1800526e9  mov     [rbp+1D0h+var_30], rax
0x1800526f0  xor     eax, eax
0x1800526f2  xorps   xmm0, xmm0
0x1800526f5  mov     rsi, rcx
0x1800526f8  mov     [rbp+1D0h+var_250], rax
0x1800526fc  lea     rcx, [rsp+2D0h+hLibModule]
0x180052701  mov     [rsp+2D0h+var_288], rax
0x180052706  movups  xmmword ptr [rsp+2D0h+hLibModule], xmm0
0x18005270b  mov     [rsp+2D0h+var_2A0], eax
0x18005270f  mov     edi, r9d
0x180052712  movups  [rsp+2D0h+var_270], xmm0
0x180052717  mov     [rsp+2D0h+var_298], rax
0x18005271c  mov     r14, r8
0x18005271f  movups  [rsp+2D0h+var_260], xmm0
0x180052724  mov     [rsp+2D0h+var_290], rax
0x180052729  mov     r15, rdx
0x18005272c  call    BfspOpenDismApi
0x180052731  mov     ebx, eax
0x180052733  test    eax, eax
0x180052735  js      loc_180052868
0x18005273b  mov     rax, [rsp+2D0h+hLibModule+8]
0x180052740  xor     r8d, r8d
0x180052743  xor     edx, edx
0x180052745  xor     ecx, ecx
0x180052747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005274c  test    eax, eax
0x18005274e  jns     short loc_180052768
0x180052750  movzx   ebx, ax
0x180052753  mov     eax, 1Fh
0x180052758  test    ebx, ebx
0x18005275a  cmovz   ebx, eax
0x18005275d  or      ebx, 0C0070000h
0x180052763  jmp     loc_18005282D
0x180052768  bt      edi, 0Fh
0x18005276c  jnb     short loc_180052777
0x18005276e  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180052775  jmp     short loc_1800527A0
0x180052777  mov     r8, r15; Source
0x18005277a  lea     rcx, [rbp+1D0h+Destination]; Destination
0x18005277e  mov     edx, 104h; SizeInWords
0x180052783  call    wcscpy_s
0x180052788  mov     edx, 5Ch ; '\'; Ch
0x18005278d  lea     rcx, [rbp+1D0h+Destination]; Str
0x180052791  call    cs:__imp_wcsrchr
0x180052797  xor     ecx, ecx
0x180052799  mov     [rax], cx
0x18005279c  lea     rcx, [rbp+1D0h+Destination]
0x1800527a0  mov     rax, qword ptr [rsp+2D0h+var_270]
0x1800527a5  lea     r9, [rsp+2D0h+var_2A0]
0x1800527aa  xor     r8d, r8d
0x1800527ad  xor     edx, edx
0x1800527af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527b4  test    eax, eax
0x1800527b6  js      short loc_180052750
0x1800527b8  mov     ecx, [rsp+2D0h+var_2A0]
0x1800527bc  lea     rax, [rsp+2D0h+var_298]
0x1800527c1  mov     [rsp+2D0h+var_2B0], rax
0x1800527c6  lea     rdx, aMicrosoftHyper; "Microsoft-Hyper-V-Hypervisor"
0x1800527cd  mov     rax, qword ptr [rsp+2D0h+var_270+8]
0x1800527d2  xor     r9d, r9d
0x1800527d5  xor     r8d, r8d
0x1800527d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527dd  test    eax, eax
0x1800527df  js      loc_180052750
0x1800527e5  mov     rax, [rsp+2D0h+var_298]
0x1800527ea  cmp     dword ptr [rax+8], 4
0x1800527ee  jnz     short loc_18005282D
0x1800527f0  lea     r8, [rsp+2D0h+var_290]
0x1800527f5  mov     rdx, r14
0x1800527f8  mov     rcx, rsi
0x1800527fb  call    cs:__imp_BcdOpenObject
0x180052801  mov     ebx, eax
0x180052803  test    eax, eax
0x180052805  js      short loc_18005282D
0x180052807  mov     rcx, [rsp+2D0h+var_290]
0x18005280c  lea     r8, [rsp+2D0h+var_288]
0x180052811  mov     r9d, 8
0x180052817  mov     [rsp+2D0h+var_288], 1
0x180052820  mov     edx, 250000F0h
0x180052825  call    cs:__imp_BcdSetElementData
0x18005282b  mov     ebx, eax
0x18005282d  mov     rcx, [rsp+2D0h+var_298]
0x180052832  test    rcx, rcx
0x180052835  jz      short loc_180052841
0x180052837  mov     rax, qword ptr [rsp+2D0h+var_260]
0x18005283c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052841  mov     ecx, [rsp+2D0h+var_2A0]
0x180052845  mov     rax, qword ptr [rsp+2D0h+var_260+8]
0x18005284a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005284f  mov     rax, [rbp+1D0h+var_250]
0x180052853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052858  mov     rcx, [rsp+2D0h+hLibModule]; hLibModule
0x18005285d  test    rcx, rcx
0x180052860  jz      short loc_180052868
0x180052862  call    cs:__imp_FreeLibrary
0x180052868  mov     rcx, [rsp+2D0h+var_290]
0x18005286d  test    rcx, rcx
0x180052870  jz      short loc_180052878
0x180052872  call    cs:__imp_BcdCloseObject
0x180052878  mov     eax, ebx
0x18005287a  mov     rcx, [rbp+1D0h+var_30]
0x180052881  xor     rcx, rsp; StackCookie
0x180052884  call    __security_check_cookie
0x180052889  mov     rbx, [rsp+2D0h+arg_18]
0x180052891  add     rsp, 2B0h
0x180052898  pop     r15
0x18005289a  pop     r14
0x18005289c  pop     rdi
0x18005289d  pop     rsi
0x18005289e  pop     rbp
0x18005289f  retn
```
