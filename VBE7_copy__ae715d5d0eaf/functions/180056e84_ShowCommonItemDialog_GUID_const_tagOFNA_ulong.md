# ShowCommonItemDialog(_GUID const &,tagOFNA *,ulong)

- ea: `0x180056e84`
- end: `0x1800572d9`
- name: `?ShowCommonItemDialog@@YAHAEBU_GUID@@PEAUtagOFNA@@K@Z`
- size: `1109`
- prototype: `__int64 __fastcall(const struct _GUID *, struct tagOFNA *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180055ca0`
- `0x180055cf4`

## callees

- `0x180056c3c`
- `0x180056e84`
- `0x18005742c`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x180057226`
- `MSVCR100!free` at `0x180057234`
- `MSVCR100!free` at `0x180057242`
- `MSVCR100!free` at `0x180057250`
- `MSVCR100!free` at `0x18005727f`
- `MSVCR100!free` at `0x18005728e`
- `MSVCR100!free` at `0x1800572a1`
- `MSVCR100!free` at `0x180057226`
- `MSVCR100!free` at `0x180057234`
- `MSVCR100!free` at `0x180057242`
- `MSVCR100!free` at `0x180057250`
- `MSVCR100!free` at `0x18005727f`
- `MSVCR100!free` at `0x18005728e`
- `MSVCR100!free` at `0x1800572a1`
- `MSVCR100!malloc` at `0x180056f82`
- `MSVCR100!malloc` at `0x180056ff5`
- `MSVCR100!malloc` at `0x180057071`
- `MSVCR100!malloc` at `0x1800570ec`
- `MSVCR100!malloc` at `0x180056f82`
- `MSVCR100!malloc` at `0x180056ff5`
- `MSVCR100!malloc` at `0x180057071`
- `MSVCR100!malloc` at `0x1800570ec`
- `KERNEL32!GetLastError` at `0x18005713a`
- `KERNEL32!GetLastError` at `0x18005713a`
- `KERNEL32!GetModuleHandleA` at `0x18005711f`
- `KERNEL32!GetModuleHandleA` at `0x18005711f`
- `KERNEL32!WideCharToMultiByte` at `0x1800571ea`
- `KERNEL32!WideCharToMultiByte` at `0x1800571ea`
- `KERNEL32!GetProcAddress` at `0x18005712f`
- `KERNEL32!GetProcAddress` at `0x18005712f`
- `KERNEL32!MultiByteToWideChar` at `0x180056fab`
- `KERNEL32!MultiByteToWideChar` at `0x180057028`
- `KERNEL32!MultiByteToWideChar` at `0x18005709d`
- `KERNEL32!MultiByteToWideChar` at `0x18005710e`
- `KERNEL32!MultiByteToWideChar` at `0x180056fab`
- `KERNEL32!MultiByteToWideChar` at `0x180057028`
- `KERNEL32!MultiByteToWideChar` at `0x18005709d`
- `KERNEL32!MultiByteToWideChar` at `0x18005710e`
- `ole32!CoTaskMemFree` at `0x180057218`
- `ole32!CoTaskMemFree` at `0x180057218`

## string_xrefs

- `0x180057125`: `SHCreateItemFromParsingName`
- `0x180057118`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall ShowCommonItemDialog(const struct _GUID *a1, struct tagOFNA *a2, int a3)
{
  unsigned int v3; // edi
  WCHAR *v5; // rbx
  WCHAR *v6; // r15
  WCHAR *v7; // r12
  WCHAR *v8; // r13
  int Instance; // esi
  const CHAR *lpstrDefExt; // rsi
  __int64 v11; // rbx
  unsigned int v12; // ebx
  WCHAR *lpWideCharStr; // rax
  const CHAR *lpstrFile; // rsi
  __int64 v15; // rbx
  unsigned int v16; // ebx
  WCHAR *v17; // rax
  const CHAR *lpstrTitle; // rsi
  __int64 v19; // rbx
  unsigned int v20; // ebx
  WCHAR *v21; // rax
  const CHAR *lpstrInitialDir; // rsi
  __int64 v23; // rbx
  unsigned int v24; // ebx
  WCHAR *v25; // rax
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v29; // ebx
  void **v30; // rbx
  __int64 v31; // r14
  void *v32; // rcx
  int cchWideChar; // [rsp+28h] [rbp-58h]
  int v35; // [rsp+40h] [rbp-40h] BYREF
  WCHAR *v36; // [rsp+48h] [rbp-38h]
  struct IFileDialog *v37; // [rsp+50h] [rbp-30h] BYREF
  __int64 v38; // [rsp+58h] [rbp-28h] BYREF
  LPCWCH v39; // [rsp+60h] [rbp-20h] BYREF
  __int64 v40; // [rsp+68h] [rbp-18h] BYREF
  void *Block; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v43; // [rsp+D8h] [rbp+58h] BYREF

  v3 = 0;
  v5 = 0;
  v37 = 0;
  v43 = 0;
  Block = 0;
  v38 = 0;
  v39 = 0;
  v6 = 0;
  v36 = 0;
  v7 = 0;
  v8 = 0;
  v40 = 0;
  Instance = VBCoCreateInstance(a1, 0, 1u, &GUID_42f85136_db7e_439c_85f1_e4075d135fc8, (LPVOID *)&v37);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IFileDialog *, int *))v37->lpVtbl->GetOptions)(v37, &v35);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct IFileDialog *, _QWORD))v37->lpVtbl->SetOptions)(v37, a3 | v35 | 0x40u);
      if ( Instance >= 0 )
      {
        Instance = SetFilterStrings(v37, a2->lpstrFilter, (struct _COMDLG_FILTERSPEC **)&Block, &v43);
        if ( Instance >= 0 )
        {
          Instance = ((__int64 (__fastcall *)(struct IFileDialog *, _QWORD))v37->lpVtbl->SetFileTypeIndex)(
                       v37,
                       a2->nFilterIndex);
          if ( Instance >= 0 )
          {
            lpstrDefExt = a2->lpstrDefExt;
            if ( lpstrDefExt )
            {
              v11 = -1;
              do
                ++v11;
              while ( lpstrDefExt[v11] );
              v12 = v11 + 1;
              lpWideCharStr = (WCHAR *)malloc(2LL * v12);
              v6 = lpWideCharStr;
              if ( !lpWideCharStr )
              {
                Instance = -2147024882;
LABEL_13:
                v5 = 0;
                goto LABEL_48;
              }
              if ( !MultiByteToWideChar(0, 0, lpstrDefExt, -1, lpWideCharStr, v12) )
              {
                Instance = -2147467259;
                goto LABEL_13;
              }
              Instance = ((__int64 (__fastcall *)(struct IFileDialog *, WCHAR *))v37->lpVtbl->SetDefaultExtension)(
                           v37,
                           v6);
              if ( Instance < 0 )
                goto LABEL_13;
            }
            lpstrFile = a2->lpstrFile;
            if ( !lpstrFile )
              goto LABEL_76;
            v15 = -1;
            do
              ++v15;
            while ( lpstrFile[v15] );
            v16 = v15 + 1;
            v17 = (WCHAR *)malloc(2LL * v16);
            v36 = v17;
            if ( !v17 )
            {
              Instance = -2147024882;
              v5 = 0;
              goto LABEL_48;
            }
            cchWideChar = v16;
            v5 = v17;
            if ( !MultiByteToWideChar(0, 0, lpstrFile, -1, v17, cchWideChar) )
            {
              Instance = -2147467259;
              goto LABEL_48;
            }
            Instance = ((__int64 (__fastcall *)(struct IFileDialog *, WCHAR *))v37->lpVtbl->SetFileName)(v37, v5);
            if ( Instance >= 0 )
            {
LABEL_76:
              if ( a2->lpstrFile )
              {
                lpstrTitle = a2->lpstrTitle;
                v19 = -1;
                do
                  ++v19;
                while ( lpstrTitle[v19] );
                v20 = v19 + 1;
                v21 = (WCHAR *)malloc(2LL * v20);
                v7 = v21;
                if ( !v21 )
                  goto LABEL_27;
                if ( !MultiByteToWideChar(0, 0, lpstrTitle, -1, v21, v20) )
                  goto LABEL_29;
                Instance = ((__int64 (__fastcall *)(struct IFileDialog *, WCHAR *))v37->lpVtbl->SetTitle)(v37, v7);
                if ( Instance < 0 )
                  goto LABEL_47;
              }
              lpstrInitialDir = a2->lpstrInitialDir;
              if ( lpstrInitialDir )
              {
                v23 = -1;
                do
                  ++v23;
                while ( lpstrInitialDir[v23] );
                v24 = v23 + 1;
                v25 = (WCHAR *)malloc(2LL * v24);
                v8 = v25;
                if ( !v25 )
                {
LABEL_27:
                  Instance = -2147024882;
                  goto LABEL_47;
                }
                if ( !MultiByteToWideChar(0, 0, lpstrInitialDir, -1, v25, v24) )
                {
LABEL_29:
                  Instance = -2147467259;
                  goto LABEL_47;
                }
                ModuleHandleA = GetModuleHandleA("shell32.dll");
                ProcAddress = GetProcAddress(ModuleHandleA, "SHCreateItemFromParsingName");
                if ( !ProcAddress )
                {
                  LastError = GetLastError();
                  Instance = (unsigned __int16)LastError | 0x80070000;
                  if ( LastError <= 0 )
                    Instance = LastError;
                  goto LABEL_47;
                }
                Instance = ((__int64 (__fastcall *)(WCHAR *, _QWORD, GUID *, __int64 *))ProcAddress)(
                             v8,
                             0,
                             &IID_IShellItem,
                             &v40);
                if ( Instance < 0
                  || (Instance = ((__int64 (__fastcall *)(struct IFileDialog *, __int64))v37->lpVtbl->SetDefaultFolder)(
                                   v37,
                                   v40),
                      Instance < 0) )
                {
LABEL_47:
                  v5 = v36;
                  goto LABEL_48;
                }
              }
              Instance = ((__int64 (__fastcall *)(struct IFileDialog *, HWND))v37->lpVtbl->Show)(v37, a2->hwndOwner);
              if ( Instance >= 0 )
              {
                Instance = ((__int64 (__fastcall *)(struct IFileDialog *, __int64 *))v37->lpVtbl->GetResult)(v37, &v38);
                if ( Instance >= 0 )
                {
                  v29 = (*(__int64 (__fastcall **)(__int64, __int64, LPCWCH *))(*(_QWORD *)v38 + 40LL))(
                          v38,
                          2147844096LL,
                          &v39);
                  if ( !WideCharToMultiByte(0, 0, v39, -1, a2->lpstrFile, a2->nMaxFile, 0, 0) )
                    v29 = -2147467259;
                  Instance = v29;
                }
              }
              goto LABEL_47;
            }
          }
        }
      }
    }
  }
LABEL_48:
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    CoTaskMemFree((LPVOID)v39);
  if ( v6 )
    free(v6);
  if ( v5 )
    free(v5);
  if ( v7 )
    free(v7);
  if ( v8 )
    free(v8);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  v30 = (void **)Block;
  if ( Block )
  {
    if ( v43 )
    {
      v31 = v43;
      do
      {
        if ( *v30 )
          free(*v30);
        v32 = v30[1];
        if ( v32 )
          free(v32);
        v30 += 2;
        --v31;
      }
      while ( v31 );
    }
    free(Block);
  }
  if ( v37 )
    ((void (__fastcall *)(struct IFileDialog *))v37->lpVtbl->Release)(v37);
  LOBYTE(v3) = Instance >= 0;
  return v3;
}

```

## disassembly

```asm
0x180056e84  mov     [rsp-38h+arg_0], rbx
0x180056e89  mov     [rsp-38h+arg_10], r8d
0x180056e8e  push    rbp
0x180056e8f  push    rsi
0x180056e90  push    rdi
0x180056e91  push    r12
0x180056e93  push    r13
0x180056e95  push    r14
0x180056e97  push    r15
0x180056e99  mov     rbp, rsp
0x180056e9c  mov     eax, 80h
0x180056ea1  call    _alloca_probe
0x180056ea6  sub     rsp, rax
0x180056ea9  xor     edi, edi
0x180056eab  lea     rax, [rbp+var_30]
0x180056eaf  mov     r14, rdx
0x180056eb2  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; struct _GUID *
0x180056eb9  lea     r8d, [rdi+1]; unsigned int
0x180056ebd  mov     ebx, edi
0x180056ebf  xor     edx, edx; struct IUnknown *
0x180056ec1  mov     [rbp+var_30], rdi
0x180056ec5  mov     [rbp+arg_18], edi
0x180056ec8  mov     [rbp+Block], rdi
0x180056ecc  mov     [rbp+var_28], rdi
0x180056ed0  mov     [rbp+var_20], rdi
0x180056ed4  mov     r15d, edi
0x180056ed7  mov     [rbp+var_38], rbx
0x180056edb  mov     r12d, edi
0x180056ede  mov     r13d, edi
0x180056ee1  mov     [rbp+var_18], rdi
0x180056ee5  mov     [rsp+80h+lpWideCharStr], rax; LPVOID *
0x180056eea  call    ?VBCoCreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; VBCoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180056eef  mov     esi, eax
0x180056ef1  test    eax, eax
0x180056ef3  js      loc_180057200
0x180056ef9  mov     rcx, [rbp+var_30]
0x180056efd  lea     rdx, [rbp+var_40]
0x180056f01  mov     rax, [rcx]
0x180056f04  call    qword ptr [rax+50h]
0x180056f07  mov     esi, eax
0x180056f09  test    eax, eax
0x180056f0b  js      loc_180057200
0x180056f11  mov     edx, [rbp+var_40]
0x180056f14  mov     rcx, [rbp+var_30]
0x180056f18  or      edx, [rbp+arg_10]
0x180056f1b  mov     rax, [rcx]
0x180056f1e  or      edx, 40h
0x180056f21  call    qword ptr [rax+48h]
0x180056f24  mov     esi, eax
0x180056f26  test    eax, eax
0x180056f28  js      loc_180057200
0x180056f2e  mov     rdx, [r14+18h]; char *
0x180056f32  mov     rcx, [rbp+var_30]; struct IFileDialog *
0x180056f36  lea     r9, [rbp+arg_18]; unsigned int *
0x180056f3a  lea     r8, [rbp+Block]; struct _COMDLG_FILTERSPEC **
0x180056f3e  call    ?SetFilterStrings@@YAJPEAUIFileDialog@@PEBDPEAPEAU_COMDLG_FILTERSPEC@@PEAI@Z; SetFilterStrings(IFileDialog *,char const *,_COMDLG_FILTERSPEC * *,uint *)
0x180056f43  mov     esi, eax
0x180056f45  test    eax, eax
0x180056f47  js      loc_180057200
0x180056f4d  mov     rcx, [rbp+var_30]
0x180056f51  mov     edx, [r14+2Ch]
0x180056f55  mov     rax, [rcx]
0x180056f58  call    qword ptr [rax+28h]
0x180056f5b  mov     esi, eax
0x180056f5d  test    eax, eax
0x180056f5f  js      loc_180057200
0x180056f65  mov     rsi, [r14+68h]
0x180056f69  test    rsi, rsi
0x180056f6c  jz      short loc_180056FD8
0x180056f6e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180056f72  inc     rbx
0x180056f75  cmp     [rsi+rbx], dil
0x180056f79  jnz     short loc_180056F72
0x180056f7b  inc     ebx
0x180056f7d  mov     ecx, ebx
0x180056f7f  add     rcx, rcx; Size
0x180056f82  call    cs:__imp_malloc
0x180056f88  mov     r15, rax
0x180056f8b  test    rax, rax
0x180056f8e  jnz     short loc_180056F97
0x180056f90  mov     esi, 8007000Eh
0x180056f95  jmp     short loc_180056FBA
0x180056f97  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180056f9b  mov     r8, rsi; lpMultiByteStr
0x180056f9e  xor     edx, edx; dwFlags
0x180056fa0  xor     ecx, ecx; CodePage
0x180056fa2  mov     [rsp+80h+cchWideChar], ebx; cchWideChar
0x180056fa6  mov     [rsp+80h+lpWideCharStr], rax; lpWideCharStr
0x180056fab  call    cs:__imp_MultiByteToWideChar
0x180056fb1  test    eax, eax
0x180056fb3  jnz     short loc_180056FC2
0x180056fb5  mov     esi, 80004005h
0x180056fba  mov     rbx, rdi
0x180056fbd  jmp     loc_180057200
0x180056fc2  mov     rcx, [rbp+var_30]
0x180056fc6  mov     rdx, r15
0x180056fc9  mov     rax, [rcx]
0x180056fcc  call    qword ptr [rax+0B0h]
0x180056fd2  mov     esi, eax
0x180056fd4  test    eax, eax
0x180056fd6  js      short loc_180056FBA
0x180056fd8  mov     rsi, [r14+30h]
0x180056fdc  test    rsi, rsi
0x180056fdf  jz      short loc_180057053
0x180056fe1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180056fe5  inc     rbx
0x180056fe8  cmp     [rsi+rbx], dil
0x180056fec  jnz     short loc_180056FE5
0x180056fee  inc     ebx
0x180056ff0  mov     ecx, ebx
0x180056ff2  add     rcx, rcx; Size
0x180056ff5  call    cs:__imp_malloc
0x180056ffb  mov     [rbp+var_38], rax
0x180056fff  test    rax, rax
0x180057002  jnz     short loc_180057011
0x180057004  mov     esi, 8007000Eh
0x180057009  mov     rbx, rax
0x18005700c  jmp     loc_180057200
0x180057011  mov     [rsp+80h+cchWideChar], ebx; cchWideChar
0x180057015  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180057019  mov     r8, rsi; lpMultiByteStr
0x18005701c  xor     edx, edx; dwFlags
0x18005701e  xor     ecx, ecx; CodePage
0x180057020  mov     rbx, rax
0x180057023  mov     [rsp+80h+lpWideCharStr], rax; lpWideCharStr
0x180057028  call    cs:__imp_MultiByteToWideChar
0x18005702e  test    eax, eax
0x180057030  jnz     short loc_18005703C
0x180057032  mov     esi, 80004005h
0x180057037  jmp     loc_180057200
0x18005703c  mov     rcx, [rbp+var_30]
0x180057040  mov     rdx, rbx
0x180057043  mov     rax, [rcx]
0x180057046  call    qword ptr [rax+78h]
0x180057049  mov     esi, eax
0x18005704b  test    eax, eax
0x18005704d  js      loc_180057200
0x180057053  cmp     [r14+30h], rdi
0x180057057  jz      short loc_1800570CB
0x180057059  mov     rsi, [r14+58h]
0x18005705d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180057061  inc     rbx
0x180057064  cmp     [rsi+rbx], dil
0x180057068  jnz     short loc_180057061
0x18005706a  inc     ebx
0x18005706c  mov     ecx, ebx
0x18005706e  add     rcx, rcx; Size
0x180057071  call    cs:__imp_malloc
0x180057077  mov     r12, rax
0x18005707a  test    rax, rax
0x18005707d  jnz     short loc_180057089
0x18005707f  mov     esi, 8007000Eh
0x180057084  jmp     loc_1800571FC
0x180057089  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005708d  mov     r8, rsi; lpMultiByteStr
0x180057090  xor     edx, edx; dwFlags
0x180057092  xor     ecx, ecx; CodePage
0x180057094  mov     [rsp+80h+cchWideChar], ebx; cchWideChar
0x180057098  mov     [rsp+80h+lpWideCharStr], rax; lpWideCharStr
0x18005709d  call    cs:__imp_MultiByteToWideChar
0x1800570a3  test    eax, eax
0x1800570a5  jnz     short loc_1800570B1
0x1800570a7  mov     esi, 80004005h
0x1800570ac  jmp     loc_1800571FC
0x1800570b1  mov     rcx, [rbp+var_30]
0x1800570b5  mov     rdx, r12
0x1800570b8  mov     rax, [rcx]
0x1800570bb  call    qword ptr [rax+88h]
0x1800570c1  mov     esi, eax
0x1800570c3  test    eax, eax
0x1800570c5  js      loc_1800571FC
0x1800570cb  mov     rsi, [r14+50h]
0x1800570cf  test    rsi, rsi
0x1800570d2  jz      loc_180057183
0x1800570d8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800570dc  inc     rbx
0x1800570df  cmp     [rsi+rbx], dil
0x1800570e3  jnz     short loc_1800570DC
0x1800570e5  inc     ebx
0x1800570e7  mov     ecx, ebx
0x1800570e9  add     rcx, rcx; Size
0x1800570ec  call    cs:__imp_malloc
0x1800570f2  mov     r13, rax
0x1800570f5  test    rax, rax
0x1800570f8  jz      short loc_18005707F
0x1800570fa  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800570fe  mov     r8, rsi; lpMultiByteStr
0x180057101  xor     edx, edx; dwFlags
0x180057103  xor     ecx, ecx; CodePage
0x180057105  mov     [rsp+80h+cchWideChar], ebx; cchWideChar
0x180057109  mov     [rsp+80h+lpWideCharStr], rax; lpWideCharStr
0x18005710e  call    cs:__imp_MultiByteToWideChar
0x180057114  test    eax, eax
0x180057116  jz      short loc_1800570A7
0x180057118  lea     rcx, aShell32Dll; "shell32.dll"
0x18005711f  call    cs:__imp_GetModuleHandleA
0x180057125  lea     rdx, aShcreateitemfr; "SHCreateItemFromParsingName"
0x18005712c  mov     rcx, rax; hModule
0x18005712f  call    cs:__imp_GetProcAddress
0x180057135  test    rax, rax
0x180057138  jnz     short loc_180057153
0x18005713a  call    cs:__imp_GetLastError
0x180057140  movzx   esi, ax
0x180057143  or      esi, 80070000h
0x180057149  test    eax, eax
0x18005714b  cmovle  esi, eax
0x18005714e  jmp     loc_1800571FC
0x180057153  lea     r9, [rbp+var_18]
0x180057157  lea     r8, IID_IShellItem
0x18005715e  xor     edx, edx
0x180057160  mov     rcx, r13
0x180057163  call    rax
0x180057165  mov     esi, eax
0x180057167  test    eax, eax
0x180057169  js      loc_1800571FC
0x18005716f  mov     rcx, [rbp+var_30]
0x180057173  mov     rdx, [rbp+var_18]
0x180057177  mov     rax, [rcx]
0x18005717a  call    qword ptr [rax+58h]
0x18005717d  mov     esi, eax
0x18005717f  test    eax, eax
0x180057181  js      short loc_1800571FC
0x180057183  mov     rcx, [rbp+var_30]
0x180057187  mov     rdx, [r14+8]
0x18005718b  mov     rax, [rcx]
0x18005718e  call    qword ptr [rax+18h]
0x180057191  mov     esi, eax
0x180057193  test    eax, eax
0x180057195  js      short loc_1800571FC
0x180057197  mov     rcx, [rbp+var_30]
0x18005719b  lea     rdx, [rbp+var_28]
0x18005719f  mov     rax, [rcx]
0x1800571a2  call    qword ptr [rax+0A0h]
0x1800571a8  mov     esi, eax
0x1800571aa  test    eax, eax
0x1800571ac  js      short loc_1800571FC
0x1800571ae  mov     rcx, [rbp+var_28]
0x1800571b2  lea     r8, [rbp+var_20]
0x1800571b6  mov     edx, 80058000h
0x1800571bb  mov     rax, [rcx]
0x1800571be  call    qword ptr [rax+28h]
0x1800571c1  mov     r8, [rbp+var_20]; lpWideCharStr
0x1800571c5  mov     [rsp+80h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800571ca  mov     ebx, eax
0x1800571cc  mov     eax, [r14+38h]
0x1800571d0  mov     [rsp+80h+lpDefaultChar], rdi; lpDefaultChar
0x1800571d5  mov     [rsp+80h+cchWideChar], eax; cbMultiByte
0x1800571d9  mov     rax, [r14+30h]
0x1800571dd  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800571e1  xor     edx, edx; dwFlags
0x1800571e3  xor     ecx, ecx; CodePage
0x1800571e5  mov     [rsp+80h+lpWideCharStr], rax; lpMultiByteStr
0x1800571ea  call    cs:__imp_WideCharToMultiByte
0x1800571f0  mov     esi, 80004005h
0x1800571f5  test    eax, eax
0x1800571f7  cmovz   ebx, esi
0x1800571fa  mov     esi, ebx
0x1800571fc  mov     rbx, [rbp+var_38]
0x180057200  mov     rcx, [rbp+var_28]
0x180057204  test    rcx, rcx
0x180057207  jz      short loc_18005720F
0x180057209  mov     rax, [rcx]
0x18005720c  call    qword ptr [rax+10h]
0x18005720f  mov     rcx, [rbp+var_20]; pv
0x180057213  test    rcx, rcx
0x180057216  jz      short loc_18005721E
0x180057218  call    cs:__imp_CoTaskMemFree
0x18005721e  test    r15, r15
0x180057221  jz      short loc_18005722C
0x180057223  mov     rcx, r15; Block
0x180057226  call    cs:__imp_free
0x18005722c  test    rbx, rbx
0x18005722f  jz      short loc_18005723A
0x180057231  mov     rcx, rbx; Block
0x180057234  call    cs:__imp_free
0x18005723a  test    r12, r12
0x18005723d  jz      short loc_180057248
0x18005723f  mov     rcx, r12; Block
0x180057242  call    cs:__imp_free
0x180057248  test    r13, r13
0x18005724b  jz      short loc_180057256
0x18005724d  mov     rcx, r13; Block
0x180057250  call    cs:__imp_free
0x180057256  mov     rcx, [rbp+var_18]
0x18005725a  test    rcx, rcx
0x18005725d  jz      short loc_180057265
0x18005725f  mov     rax, [rcx]
0x180057262  call    qword ptr [rax+10h]
0x180057265  mov     rbx, [rbp+Block]
0x180057269  test    rbx, rbx
0x18005726c  jz      short loc_1800572A7
0x18005726e  cmp     [rbp+arg_18], edi
0x180057271  jbe     short loc_18005729D
0x180057273  mov     r14d, [rbp+arg_18]
0x180057277  cmp     [rbx], rdi
0x18005727a  jz      short loc_180057285
0x18005727c  mov     rcx, [rbx]; Block
0x18005727f  call    cs:__imp_free
0x180057285  mov     rcx, [rbx+8]; Block
0x180057289  test    rcx, rcx
  ... truncated ...
```
