# QueryNewLinkHandler(_GUID const *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,HWND__ *,INewShortcutHookW * *,INewShortcutHookA * *)

- ea: `0x18001c984`
- end: `0x18001cd56`
- name: `?QueryNewLinkHandler@@YAJPEBU_GUID@@KPEAGK1K1K1K1PEAUHWND__@@PEAPEAUINewShortcutHookW@@PEAPEAUINewShortcutHookA@@@Z`
- size: `978`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, unsigned __int16 *, unsigned int, LPCWCH, unsigned int, LPWSTR, unsigned int, unsigned __int16 *, unsigned int, LPCWCH lpWideCharStr, HWND, struct INewShortcutHookW **, struct INewShortcutHookA **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d4f0`

## callees

- `0x18001c984`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cb74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cb74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ca21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ca21`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cb64`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cbb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cbe0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cb64`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cbb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001cbe0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cc6b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ccae`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cce6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cc6b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ccae`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cce6`

## pseudocode

```c
__int64 __fastcall QueryNewLinkHandler(
        const struct _GUID *a1,
        int a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        LPWSTR a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned int a10,
        LPCWCH lpWideCharStr,
        HWND a12,
        struct INewShortcutHookW **a13,
        struct INewShortcutHookA **a14)
{
  unsigned int v15; // ebx
  SIZE_T cbMultiByte; // rbx
  CHAR *v17; // r14
  struct INewShortcutHookW *v19; // [rsp+40h] [rbp-C0h] BYREF
  struct INewShortcutHookA *v20; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR v22; // [rsp+58h] [rbp-A8h]
  struct INewShortcutHookA **v23; // [rsp+60h] [rbp-A0h]
  CHAR MultiByteStr[272]; // [rsp+70h] [rbp-90h] BYREF
  CHAR v25[272]; // [rsp+180h] [rbp+80h] BYREF
  CHAR v26[272]; // [rsp+290h] [rbp+190h] BYREF

  if ( (a2 & 0x10000000) == 0 )
    a3 = a5;
  *a7 = 0;
  *a9 = 0;
  v22 = a9;
  v23 = a14;
  ppv = 0;
  v15 = CoCreateInstance(a1, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
  if ( !v15 )
  {
    v19 = 0;
    if ( (**(unsigned int (__fastcall ***)(LPVOID, GUID *, struct INewShortcutHookW **))ppv)(
           ppv,
           &GUID_000214f7_0000_0000_c000_000000000046,
           &v19) )
    {
      v20 = 0;
      v15 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct INewShortcutHookA **))ppv)(
              ppv,
              &GUID_000214e1_0000_0000_c000_000000000046,
              &v20);
      if ( !v15 )
      {
        cbMultiByte = (unsigned int)(WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0) + 1);
        v17 = (CHAR *)LocalAlloc(0x40u, cbMultiByte);
        if ( v17 )
        {
          WideCharToMultiByte(0, 0, a3, -1, MultiByteStr, 260, 0, 0);
          WideCharToMultiByte(0, 0, lpWideCharStr, -1, v17, cbMultiByte, 0, 0);
          v15 = ((__int64 (__fastcall *)(struct INewShortcutHookA *, CHAR *, HWND))v20->lpVtbl->SetReferent)(
                  v20,
                  MultiByteStr,
                  a12);
          if ( v15
            || lpWideCharStr
            && (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookA *, CHAR *))v20->lpVtbl->SetFolder)(v20, v17)) != 0
            || (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookA *, CHAR *, __int64))v20->lpVtbl->GetName)(
                        v20,
                        v26,
                        260)) != 0
            || (MultiByteToWideChar(0, 0, v26, -1, a7, 260),
                (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookA *, CHAR *, __int64))v20->lpVtbl->GetExtension)(
                         v20,
                         v25,
                         260)) != 0)
            || (MultiByteToWideChar(0, 0, v25, -1, v22, 260),
                v15 = ((__int64 (__fastcall *)(struct INewShortcutHookA *, CHAR *, __int64))v20->lpVtbl->GetReferent)(
                        v20,
                        MultiByteStr,
                        260),
                MultiByteToWideChar(0, 0, v25, -1, a3, 260),
                v15) )
          {
            ((void (__fastcall *)(struct INewShortcutHookA *))v20->lpVtbl->Release)(v20);
          }
          else
          {
            *v23 = v20;
          }
          LocalFree(v17);
        }
        else
        {
          v15 = -2147024882;
        }
      }
    }
    else
    {
      v15 = ((__int64 (__fastcall *)(struct INewShortcutHookW *, unsigned __int16 *, HWND))v19->lpVtbl->SetReferent)(
              v19,
              a3,
              a12);
      if ( v15
        || lpWideCharStr
        && (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookW *, LPCWCH))v19->lpVtbl->SetFolder)(
                    v19,
                    lpWideCharStr)) != 0
        || (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookW *, LPWSTR, __int64))v19->lpVtbl->GetName)(
                    v19,
                    a7,
                    260)) != 0
        || (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookW *, LPWSTR, __int64))v19->lpVtbl->GetExtension)(
                    v19,
                    v22,
                    260)) != 0
        || (v15 = ((__int64 (__fastcall *)(struct INewShortcutHookW *, unsigned __int16 *, __int64))v19->lpVtbl->GetReferent)(
                    v19,
                    a3,
                    260)) != 0 )
      {
        ((void (__fastcall *)(struct INewShortcutHookW *))v19->lpVtbl->Release)(v19);
      }
      else
      {
        *a13 = v19;
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v15;
}

```

## disassembly

```asm
0x18001c984  mov     [rsp-8+arg_8], rbx
0x18001c989  push    rbp
0x18001c98a  push    rsi
0x18001c98b  push    rdi
0x18001c98c  push    r12
0x18001c98e  push    r13
0x18001c990  push    r14
0x18001c992  push    r15
0x18001c994  lea     rbp, [rsp-2B0h]
0x18001c99c  sub     rsp, 3B0h
0x18001c9a3  mov     rax, cs:__security_cookie
0x18001c9aa  xor     rax, rsp
0x18001c9ad  mov     [rbp+2E0h+var_40], rax
0x18001c9b4  mov     r9, [rbp+2E0h+arg_40]
0x18001c9bb  xor     edi, edi
0x18001c9bd  mov     rax, [rbp+2E0h+arg_20]
0x18001c9c4  mov     r15, r8
0x18001c9c7  mov     r8, [rbp+2E0h+arg_68]
0x18001c9ce  bt      edx, 1Ch
0x18001c9d2  mov     r13, [rbp+2E0h+arg_30]
0x18001c9d9  mov     rsi, [rbp+2E0h+lpWideCharStr]
0x18001c9e0  cmovnb  r15, rax
0x18001c9e4  mov     r12, [rbp+2E0h+arg_58]
0x18001c9eb  lea     rax, [rsp+3E0h+var_390]
0x18001c9f0  mov     r14, [rbp+2E0h+arg_60]
0x18001c9f7  xor     edx, edx; pUnkOuter
0x18001c9f9  mov     [r13+0], di
0x18001c9fe  mov     [r9], di
0x18001ca02  mov     [rsp+3E0h+var_388], r9
0x18001ca07  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001ca0e  mov     [rsp+3E0h+var_380], r8
0x18001ca13  lea     r8d, [rdi+1]; dwClsContext
0x18001ca17  mov     [rsp+3E0h+ppv], rax; ppv
0x18001ca1c  mov     [rsp+3E0h+var_390], rdi
0x18001ca21  call    cs:__imp_CoCreateInstance
0x18001ca27  mov     ebx, eax
0x18001ca29  test    eax, eax
0x18001ca2b  jnz     loc_18001CD2A
0x18001ca31  mov     rcx, [rsp+3E0h+var_390]
0x18001ca36  lea     r8, [rsp+3E0h+var_3A0]
0x18001ca3b  mov     [rsp+3E0h+var_3A0], rdi
0x18001ca40  lea     rdx, _GUID_000214f7_0000_0000_c000_000000000046
0x18001ca47  mov     rax, [rcx]
0x18001ca4a  mov     rax, [rax]
0x18001ca4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca52  test    eax, eax
0x18001ca54  jnz     loc_18001CB1B
0x18001ca5a  mov     rcx, [rsp+3E0h+var_3A0]
0x18001ca5f  mov     r8, r12
0x18001ca62  mov     rdx, r15
0x18001ca65  mov     rax, [rcx]
0x18001ca68  mov     rax, [rax+18h]
0x18001ca6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca71  mov     ebx, eax
0x18001ca73  test    eax, eax
0x18001ca75  jnz     loc_18001CB05
0x18001ca7b  test    rsi, rsi
0x18001ca7e  jz      short loc_18001CA9A
0x18001ca80  mov     rcx, [rsp+3E0h+var_3A0]
0x18001ca85  mov     rdx, rsi
0x18001ca88  mov     rax, [rcx]
0x18001ca8b  mov     rax, [rax+28h]
0x18001ca8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca94  mov     ebx, eax
0x18001ca96  test    eax, eax
0x18001ca98  jnz     short loc_18001CB05
0x18001ca9a  mov     rcx, [rsp+3E0h+var_3A0]
0x18001ca9f  mov     edi, 104h
0x18001caa4  mov     r8d, edi
0x18001caa7  mov     rdx, r13
0x18001caaa  mov     rax, [rcx]
0x18001caad  mov     rax, [rax+38h]
0x18001cab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cab6  mov     ebx, eax
0x18001cab8  test    eax, eax
0x18001caba  jnz     short loc_18001CB05
0x18001cabc  mov     rcx, [rsp+3E0h+var_3A0]
0x18001cac1  mov     r8d, edi
0x18001cac4  mov     rdx, [rsp+3E0h+var_388]
0x18001cac9  mov     rax, [rcx]
0x18001cacc  mov     rax, [rax+40h]
0x18001cad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad5  mov     ebx, eax
0x18001cad7  test    eax, eax
0x18001cad9  jnz     short loc_18001CB05
0x18001cadb  mov     rcx, [rsp+3E0h+var_3A0]
0x18001cae0  mov     r8d, edi
0x18001cae3  mov     rdx, r15
0x18001cae6  mov     rax, [rcx]
0x18001cae9  mov     rax, [rax+20h]
0x18001caed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caf2  mov     ebx, eax
0x18001caf4  test    eax, eax
0x18001caf6  jnz     short loc_18001CB05
0x18001caf8  mov     rax, [rsp+3E0h+var_3A0]
0x18001cafd  mov     [r14], rax
0x18001cb00  jmp     loc_18001CD19
0x18001cb05  mov     rcx, [rsp+3E0h+var_3A0]
0x18001cb0a  mov     rax, [rcx]
0x18001cb0d  mov     rax, [rax+10h]
0x18001cb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb16  jmp     loc_18001CD19
0x18001cb1b  mov     rcx, [rsp+3E0h+var_390]
0x18001cb20  lea     r8, [rsp+3E0h+var_398]
0x18001cb25  mov     [rsp+3E0h+var_398], rdi
0x18001cb2a  lea     rdx, _GUID_000214e1_0000_0000_c000_000000000046
0x18001cb31  mov     rax, [rcx]
0x18001cb34  mov     rax, [rax]
0x18001cb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb3c  mov     ebx, eax
0x18001cb3e  test    eax, eax
0x18001cb40  jnz     loc_18001CD19
0x18001cb46  mov     [rsp+3E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18001cb4b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001cb4f  mov     [rsp+3E0h+lpDefaultChar], rdi; lpDefaultChar
0x18001cb54  mov     r8, rsi; lpWideCharStr
0x18001cb57  mov     [rsp+3E0h+cbMultiByte], edi; cbMultiByte
0x18001cb5b  xor     edx, edx; dwFlags
0x18001cb5d  xor     ecx, ecx; CodePage
0x18001cb5f  mov     [rsp+3E0h+ppv], rdi; lpMultiByteStr
0x18001cb64  call    cs:__imp_WideCharToMultiByte
0x18001cb6a  mov     ecx, 40h ; '@'; uFlags
0x18001cb6f  lea     ebx, [rax+1]
0x18001cb72  mov     edx, ebx; uBytes
0x18001cb74  call    cs:__imp_LocalAlloc
0x18001cb7a  mov     r14, rax
0x18001cb7d  test    rax, rax
0x18001cb80  jnz     short loc_18001CB8C
0x18001cb82  mov     ebx, 8007000Eh
0x18001cb87  jmp     loc_18001CD19
0x18001cb8c  mov     [rsp+3E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18001cb91  lea     rax, [rsp+3E0h+MultiByteStr]
0x18001cb96  mov     [rsp+3E0h+lpDefaultChar], rdi; lpDefaultChar
0x18001cb9b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001cb9f  mov     edi, 104h
0x18001cba4  mov     r8, r15; lpWideCharStr
0x18001cba7  mov     [rsp+3E0h+cbMultiByte], edi; cbMultiByte
0x18001cbab  xor     edx, edx; dwFlags
0x18001cbad  xor     ecx, ecx; CodePage
0x18001cbaf  mov     [rsp+3E0h+ppv], rax; lpMultiByteStr
0x18001cbb4  call    cs:__imp_WideCharToMultiByte
0x18001cbba  mov     [rsp+3E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001cbc3  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001cbc7  mov     [rsp+3E0h+lpDefaultChar], 0; lpDefaultChar
0x18001cbd0  mov     r8, rsi; lpWideCharStr
0x18001cbd3  mov     [rsp+3E0h+cbMultiByte], ebx; cbMultiByte
0x18001cbd7  xor     edx, edx; dwFlags
0x18001cbd9  xor     ecx, ecx; CodePage
0x18001cbdb  mov     [rsp+3E0h+ppv], r14; lpMultiByteStr
0x18001cbe0  call    cs:__imp_WideCharToMultiByte
0x18001cbe6  mov     rcx, [rsp+3E0h+var_398]
0x18001cbeb  lea     rdx, [rsp+3E0h+MultiByteStr]
0x18001cbf0  mov     r8, r12
0x18001cbf3  mov     rax, [rcx]
0x18001cbf6  mov     rax, [rax+18h]
0x18001cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbff  mov     ebx, eax
0x18001cc01  test    eax, eax
0x18001cc03  jnz     loc_18001CCFF
0x18001cc09  test    rsi, rsi
0x18001cc0c  jz      short loc_18001CC2C
0x18001cc0e  mov     rcx, [rsp+3E0h+var_398]
0x18001cc13  mov     rdx, r14
0x18001cc16  mov     rax, [rcx]
0x18001cc19  mov     rax, [rax+28h]
0x18001cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc22  mov     ebx, eax
0x18001cc24  test    eax, eax
0x18001cc26  jnz     loc_18001CCFF
0x18001cc2c  mov     rcx, [rsp+3E0h+var_398]
0x18001cc31  lea     rdx, [rbp+2E0h+var_150]
0x18001cc38  mov     r8d, edi
0x18001cc3b  mov     rax, [rcx]
0x18001cc3e  mov     rax, [rax+38h]
0x18001cc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc47  mov     ebx, eax
0x18001cc49  test    eax, eax
0x18001cc4b  jnz     loc_18001CCFF
0x18001cc51  or      esi, 0FFFFFFFFh
0x18001cc54  mov     [rsp+3E0h+cbMultiByte], edi; cchWideChar
0x18001cc58  mov     r9d, esi; cbMultiByte
0x18001cc5b  mov     [rsp+3E0h+ppv], r13; lpWideCharStr
0x18001cc60  lea     r8, [rbp+2E0h+var_150]; lpMultiByteStr
0x18001cc67  xor     edx, edx; dwFlags
0x18001cc69  xor     ecx, ecx; CodePage
0x18001cc6b  call    cs:__imp_MultiByteToWideChar
0x18001cc71  mov     rcx, [rsp+3E0h+var_398]
0x18001cc76  lea     rdx, [rbp+2E0h+var_260]
0x18001cc7d  mov     r8d, edi
0x18001cc80  mov     rax, [rcx]
0x18001cc83  mov     rax, [rax+40h]
0x18001cc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc8c  mov     ebx, eax
0x18001cc8e  test    eax, eax
0x18001cc90  jnz     short loc_18001CCFF
0x18001cc92  mov     rdx, [rsp+3E0h+var_388]
0x18001cc97  lea     r8, [rbp+2E0h+var_260]; lpMultiByteStr
0x18001cc9e  mov     [rsp+3E0h+cbMultiByte], edi; cchWideChar
0x18001cca2  mov     r9d, esi; cbMultiByte
0x18001cca5  mov     [rsp+3E0h+ppv], rdx; lpWideCharStr
0x18001ccaa  xor     ecx, ecx; CodePage
0x18001ccac  xor     edx, edx; dwFlags
0x18001ccae  call    cs:__imp_MultiByteToWideChar
0x18001ccb4  mov     rcx, [rsp+3E0h+var_398]
0x18001ccb9  lea     rdx, [rsp+3E0h+MultiByteStr]
0x18001ccbe  mov     r8d, edi
0x18001ccc1  mov     rax, [rcx]
0x18001ccc4  mov     rax, [rax+20h]
0x18001ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cccd  mov     r9d, esi; cbMultiByte
0x18001ccd0  mov     [rsp+3E0h+cbMultiByte], edi; cchWideChar
0x18001ccd4  lea     r8, [rbp+2E0h+var_260]; lpMultiByteStr
0x18001ccdb  mov     [rsp+3E0h+ppv], r15; lpWideCharStr
0x18001cce0  xor     edx, edx; dwFlags
0x18001cce2  xor     ecx, ecx; CodePage
0x18001cce4  mov     ebx, eax
0x18001cce6  call    cs:__imp_MultiByteToWideChar
0x18001ccec  test    ebx, ebx
0x18001ccee  jnz     short loc_18001CCFF
0x18001ccf0  mov     rcx, [rsp+3E0h+var_380]
0x18001ccf5  mov     rax, [rsp+3E0h+var_398]
0x18001ccfa  mov     [rcx], rax
0x18001ccfd  jmp     short loc_18001CD10
0x18001ccff  mov     rcx, [rsp+3E0h+var_398]
0x18001cd04  mov     rax, [rcx]
0x18001cd07  mov     rax, [rax+10h]
0x18001cd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd10  mov     rcx, r14; hMem
0x18001cd13  call    cs:__imp_LocalFree
0x18001cd19  mov     rcx, [rsp+3E0h+var_390]
0x18001cd1e  mov     rax, [rcx]
0x18001cd21  mov     rax, [rax+10h]
0x18001cd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2a  mov     eax, ebx
0x18001cd2c  mov     rcx, [rbp+2E0h+var_40]
0x18001cd33  xor     rcx, rsp; StackCookie
0x18001cd36  call    __security_check_cookie
0x18001cd3b  mov     rbx, [rsp+3E0h+arg_8]
0x18001cd43  add     rsp, 3B0h
0x18001cd4a  pop     r15
0x18001cd4c  pop     r14
0x18001cd4e  pop     r13
0x18001cd50  pop     r12
0x18001cd52  pop     rdi
0x18001cd53  pop     rsi
0x18001cd54  pop     rbp
0x18001cd55  retn
```
