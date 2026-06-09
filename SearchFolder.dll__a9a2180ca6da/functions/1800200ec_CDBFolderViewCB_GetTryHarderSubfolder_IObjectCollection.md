# CDBFolderViewCB::_GetTryHarderSubfolder(IObjectCollection *)

- ea: `0x1800200ec`
- end: `0x180020382`
- name: `?_GetTryHarderSubfolder@CDBFolderViewCB@@AEAAJPEAUIObjectCollection@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(CDBFolderViewCB *__hidden this, struct IObjectCollection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bad0`

## callees

- `0x180004a50`
- `0x180006900`
- `0x180013e0c`
- `0x18001e564`
- `0x1800200ec`
- `0x180021e64`
- `0x18003ceec`
- `0x18003dd70`
- `0x180051010`

## import_xrefs

- `SHELL32!Shell_GetCachedImageIndexW` at `0x1800202b5`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x1800202b5`
- `SHELL32!SHGetIDListFromObject` at `0x180020224`
- `SHELL32!SHGetIDListFromObject` at `0x180020224`
- `SHELL32!__imp_ILFree` at `0x180020328`
- `SHELL32!__imp_ILFree` at `0x180020328`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002026c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020288`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800202a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002026c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020288`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800202a1`

## string_xrefs

- `0x1800202aa`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CDBFolderViewCB::_GetTryHarderSubfolder(CDBFolderViewCB *this, struct IObjectCollection *a2)
{
  HRESULT TryHarderItem; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  struct IUnknown *v8; // rcx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _ITEMIDLIST_ABSOLUTE *v14; // rcx
  __int64 v15; // rcx
  unsigned int CachedImageIndexW; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  void *v22; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *punk; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v26[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v27[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR Buffer[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  TryHarderItem = 0;
  if ( !(unsigned int)CDBFolderViewCB::_AnyScopeNonRecursive(this) )
    return (unsigned int)TryHarderItem;
  if ( Microsoft_Windows_Shell_CoreEnableBits < 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v5,
      (unsigned int)ShellTraceId_TryHarder_Calculate_Search_Subfolders_Start,
      v6,
      v7,
      (__int64)v25);
  v8 = (struct IUnknown *)*((_QWORD *)this + 13);
  v22 = 0;
  TryHarderItem = IUnknown_QueryObject(
                    v8,
                    &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
                    &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                    &v22);
  if ( TryHarderItem >= 0 )
  {
    v20 = 0;
    ppidl = 0;
    if ( (*(int (__fastcall **)(void *, int *))(*(_QWORD *)v22 + 128LL))(v22, &v20) >= 0 && (v20 & 0x40000000) != 0 )
    {
      *(_OWORD *)v25 = 0;
      TryHarderItem = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v22 + 104LL))(v22, v25);
      if ( TryHarderItem >= 0 )
      {
        v14 = (struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)this + 9);
        v24 = *(struct _GUID *)v25;
        TryHarderItem = CreateSearchOnAnyFolder(v14, &v24, v18, v19, (struct _ITEMIDLIST_ABSOLUTE **)&ppidl);
LABEL_11:
        if ( TryHarderItem >= 0 && ppidl )
        {
          LoadStringW(g_hinst, 0x5D34u, Buffer, 260);
          LoadStringW(g_hinst, 0x5D35u, v27, 260);
          LoadStringW(g_hinst, 0x5D36u, v26, 260);
          CachedImageIndexW = Shell_GetCachedImageIndexW(L"imageres.dll", 3, 0);
          *(_QWORD *)&v24.Data1 = 0;
          TryHarderItem = CreateTryHarderItem(v26, CachedImageIndexW, Buffer, v27, v26, ppidl);
          if ( TryHarderItem >= 0 )
          {
            TryHarderItem = ((__int64 (__fastcall *)(struct IObjectCollection *, _QWORD))a2->lpVtbl->AddObject)(
                              a2,
                              *(_QWORD *)&v24.Data1);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v24.Data1 + 16LL))(*(_QWORD *)&v24.Data1);
          }
          ILFree(ppidl);
        }
      }
    }
    else
    {
      v15 = *((_QWORD *)this + 13);
      punk = 0;
      TryHarderItem = CreateSearchWithNewFlags(v15, v12, v13, &punk);
      if ( TryHarderItem >= 0 )
      {
        TryHarderItem = SHGetIDListFromObject(punk, &ppidl);
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        goto LABEL_11;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( Microsoft_Windows_Shell_CoreEnableBits < 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v9,
      (unsigned int)ShellTraceId_TryHarder_Calculate_Search_Subfolders_Stop,
      v10,
      v11,
      (__int64)v25);
  return (unsigned int)TryHarderItem;
}

```

## disassembly

```asm
0x1800200ec  mov     [rsp-8+arg_10], rbx
0x1800200f1  push    rbp
0x1800200f2  push    rsi
0x1800200f3  push    rdi
0x1800200f4  lea     rbp, [rsp-5C0h]
0x1800200fc  sub     rsp, 6C0h
0x180020103  mov     rax, cs:__security_cookie
0x18002010a  xor     rax, rsp
0x18002010d  mov     [rbp+5D0h+var_20], rax
0x180020114  mov     rsi, rdx
0x180020117  mov     rdi, rcx
0x18002011a  xor     ebx, ebx
0x18002011c  call    ?_AnyScopeNonRecursive@CDBFolderViewCB@@AEAAHXZ; CDBFolderViewCB::_AnyScopeNonRecursive(void)
0x180020121  test    eax, eax
0x180020123  jz      loc_18002035E
0x180020129  cmp     cs:Microsoft_Windows_Shell_CoreEnableBits, bl
0x18002012f  jge     short loc_180020147
0x180020131  lea     rax, [rsp+6D0h+var_660]
0x180020136  lea     rdx, ShellTraceId_TryHarder_Calculate_Search_Subfolders_Start
0x18002013d  mov     qword ptr [rsp+6D0h+var_6B0], rax; int
0x180020142  call    McGenEventWrite_EtwEventWriteTransfer
0x180020147  mov     rcx, [rdi+68h]; struct IUnknown *
0x18002014b  lea     r9, [rsp+6D0h+var_680]; void **
0x180020150  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x180020157  mov     [rsp+6D0h+var_680], rbx
0x18002015c  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x180020163  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x180020168  mov     ebx, eax
0x18002016a  test    eax, eax
0x18002016c  js      loc_18002033F
0x180020172  mov     rcx, [rsp+6D0h+var_680]
0x180020177  lea     rdx, [rsp+6D0h+var_690]
0x18002017c  mov     [rsp+6D0h+var_690], 0
0x180020184  mov     [rsp+6D0h+ppidl], 0
0x18002018d  mov     rax, [rcx]
0x180020190  mov     rax, [rax+80h]
0x180020197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002019c  test    eax, eax
0x18002019e  js      short loc_1800201F9
0x1800201a0  test    [rsp+6D0h+var_690], 40000000h
0x1800201a8  jz      short loc_1800201F9
0x1800201aa  mov     rcx, [rsp+6D0h+var_680]
0x1800201af  lea     rdx, [rsp+6D0h+var_660]
0x1800201b4  xorps   xmm0, xmm0
0x1800201b7  movups  xmmword ptr [rsp+6D0h+var_660], xmm0
0x1800201bc  mov     rax, [rcx]
0x1800201bf  mov     rax, [rax+68h]
0x1800201c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201c8  mov     ebx, eax
0x1800201ca  test    eax, eax
0x1800201cc  js      loc_18002032E
0x1800201d2  movaps  xmm0, xmmword ptr [rsp+6D0h+var_660]
0x1800201d7  lea     rax, [rsp+6D0h+ppidl]
0x1800201dc  mov     rcx, [rdi+48h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800201e0  lea     rdx, [rsp+6D0h+var_670]; struct _GUID *
0x1800201e5  movdqa  xmmword ptr [rsp+6D0h+var_670.Data1], xmm0
0x1800201eb  mov     [rsp+6D0h+var_6A0], rax; struct _ITEMIDLIST_ABSOLUTE **
0x1800201f0  call    CreateSearchOnAnyFolder
0x1800201f5  mov     ebx, eax
0x1800201f7  jmp     short loc_18002023D
0x1800201f9  mov     rcx, [rdi+68h]
0x1800201fd  lea     r9, [rsp+6D0h+punk]
0x180020202  mov     [rsp+6D0h+punk], 0
0x18002020b  call    ?CreateSearchWithNewFlags@@YAJPEAUIShellFolder3@@W4AUTOLISTFLAGS@@AEBU_GUID@@PEAPEAX@Z; CreateSearchWithNewFlags(IShellFolder3 *,AUTOLISTFLAGS,_GUID const &,void * *)
0x180020210  mov     ebx, eax
0x180020212  test    eax, eax
0x180020214  js      loc_18002032E
0x18002021a  mov     rcx, [rsp+6D0h+punk]; punk
0x18002021f  lea     rdx, [rsp+6D0h+ppidl]; ppidl
0x180020224  call    cs:__imp_SHGetIDListFromObject
0x18002022a  mov     rcx, [rsp+6D0h+punk]
0x18002022f  mov     ebx, eax
0x180020231  mov     rax, [rcx]
0x180020234  mov     rax, [rax+10h]
0x180020238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002023d  test    ebx, ebx
0x18002023f  js      loc_18002032E
0x180020245  cmp     [rsp+6D0h+ppidl], 0
0x18002024b  jz      loc_18002032E
0x180020251  mov     rcx, cs:g_hinst; hInstance
0x180020258  lea     r8, [rbp+5D0h+Buffer]; lpBuffer
0x18002025f  mov     ebx, 104h
0x180020264  mov     edx, 5D34h; uID
0x180020269  mov     r9d, ebx; cchBufferMax
0x18002026c  call    cs:__imp_LoadStringW
0x180020272  mov     rcx, cs:g_hinst; hInstance
0x180020279  lea     r8, [rbp+5D0h+var_440]; lpBuffer
0x180020280  mov     r9d, ebx; cchBufferMax
0x180020283  mov     edx, 5D35h; uID
0x180020288  call    cs:__imp_LoadStringW
0x18002028e  mov     rcx, cs:g_hinst; hInstance
0x180020295  lea     r8, [rbp+5D0h+var_650]; lpBuffer
0x180020299  mov     r9d, ebx; cchBufferMax
0x18002029c  mov     edx, 5D36h; uID
0x1800202a1  call    cs:__imp_LoadStringW
0x1800202a7  xor     r8d, r8d; uIconFlags
0x1800202aa  lea     rcx, pszIconPath; "imageres.dll"
0x1800202b1  lea     edx, [r8+3]; iIconIndex
0x1800202b5  call    cs:__imp_Shell_GetCachedImageIndexW
0x1800202bb  mov     rcx, [rsp+6D0h+ppidl]
0x1800202c0  lea     rdx, [rsp+6D0h+var_670]
0x1800202c5  mov     [rsp+6D0h+var_698], rdx
0x1800202ca  lea     r9, [rbp+5D0h+var_440]
0x1800202d1  mov     [rsp+6D0h+var_6A8], rcx
0x1800202d6  lea     r8, [rbp+5D0h+Buffer]
0x1800202dd  lea     rcx, [rbp+5D0h+var_650]
0x1800202e1  mov     qword ptr [rsp+6D0h+var_670.Data1], 0
0x1800202ea  mov     edx, eax
0x1800202ec  mov     qword ptr [rsp+6D0h+var_6B0], rcx
0x1800202f1  call    CreateTryHarderItem
0x1800202f6  mov     ebx, eax
0x1800202f8  test    eax, eax
0x1800202fa  js      short loc_180020323
0x1800202fc  mov     rax, [rsi]
0x1800202ff  mov     rcx, rsi
0x180020302  mov     rdx, qword ptr [rsp+6D0h+var_670.Data1]
0x180020307  mov     rax, [rax+28h]
0x18002030b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020310  mov     rcx, qword ptr [rsp+6D0h+var_670.Data1]
0x180020315  mov     ebx, eax
0x180020317  mov     rax, [rcx]
0x18002031a  mov     rax, [rax+10h]
0x18002031e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020323  mov     rcx, [rsp+6D0h+ppidl]; pidl
0x180020328  call    cs:__imp_ILFree
0x18002032e  mov     rcx, [rsp+6D0h+var_680]
0x180020333  mov     rax, [rcx]
0x180020336  mov     rax, [rax+10h]
0x18002033a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002033f  cmp     cs:Microsoft_Windows_Shell_CoreEnableBits, 0
0x180020346  jge     short loc_18002035E
0x180020348  lea     rax, [rsp+6D0h+var_660]
0x18002034d  lea     rdx, ShellTraceId_TryHarder_Calculate_Search_Subfolders_Stop
0x180020354  mov     qword ptr [rsp+6D0h+var_6B0], rax
0x180020359  call    McGenEventWrite_EtwEventWriteTransfer
0x18002035e  mov     eax, ebx
0x180020360  mov     rcx, [rbp+5D0h+var_20]
0x180020367  xor     rcx, rsp; StackCookie
0x18002036a  call    __security_check_cookie
0x18002036f  mov     rbx, [rsp+6D0h+arg_10]
0x180020377  add     rsp, 6C0h
0x18002037e  pop     rdi
0x18002037f  pop     rsi
0x180020380  pop     rbp
0x180020381  retn
```
