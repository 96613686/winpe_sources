# GenerateInstallersFolder(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>,std::allocator<std::pair<DirQueItem,ushort const *>>> &)

- ea: `0x1800212f0`
- end: `0x18002155f`
- name: `?GenerateInstallersFolder@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x1800152d4`
- `0x18001c940`
- `0x18001f230`
- `0x18001faac`
- `0x18001fc6c`
- `0x1800212f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800213bd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800213bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002141b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002141b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002140d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002140d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213e4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021497`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021497`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021388`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021388`

## string_xrefs

- `0x18002135e`: `Installer`

## pseudocode

```c
__int64 __fastcall GenerateInstallersFolder(__int64 *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  __int16 v6; // ax
  __int64 v7; // r8
  unsigned __int16 *v8; // rdi
  void *v9; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  _OWORD *v16; // rdx
  unsigned __int16 *v17; // rax
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int64 v25; // rdx
  PWSTR ppszPath[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v27; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v28; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v31[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+278h] [rbp+178h]
  unsigned __int16 v33[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  memset_0(v33, 0, 0x208u);
  *(_QWORD *)&v27.Length = 524294;
  *(_QWORD *)&v28.Length = 1310738;
  v27.Buffer = L"\\\\?";
  v28.Buffer = L"Installer";
  *(_OWORD *)ppszPath = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)lpFileName = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath[1]);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x488,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v4,
      (int)ppszPath[0]);
    return (unsigned int)v5;
  }
  v6 = 2 * wcsnlen(ppszPath[1], 0x104u);
  LOWORD(ppszPath[0]) = v6;
  if ( v6 == 260 )
  {
    v5 = -2147417803;
  }
  else
  {
    WORD1(ppszPath[0]) = v6 + 2;
    v5 = CombinePathParts(&v27, (struct _UNICODE_STRING *)ppszPath, v7, (struct _UNICODE_STRING *)lpMem);
    if ( v5 >= 0 )
    {
      v5 = CombinePathParts((struct _UNICODE_STRING *)lpMem, &v28, v13, (struct _UNICODE_STRING *)lpFileName);
      if ( v5 >= 0 )
      {
        v8 = (unsigned __int16 *)lpFileName[1];
        if ( GetFileAttributesW(lpFileName[1]) == 22 )
        {
          v5 = StringCbCopyW(v33, v14, v8);
          if ( v5 >= 0 )
          {
            v15 = 4;
            v16 = v31;
            v17 = v33;
            do
            {
              v18 = *((_OWORD *)v17 + 1);
              *v16 = *(_OWORD *)v17;
              v19 = *((_OWORD *)v17 + 2);
              v16[1] = v18;
              v20 = *((_OWORD *)v17 + 3);
              v16[2] = v19;
              v21 = *((_OWORD *)v17 + 4);
              v16[3] = v20;
              v22 = *((_OWORD *)v17 + 5);
              v16[4] = v21;
              v23 = *((_OWORD *)v17 + 6);
              v16[5] = v22;
              v24 = *((_OWORD *)v17 + 7);
              v17 += 64;
              v16[6] = v23;
              v16[7] = v24;
              v16 += 8;
              --v15;
            }
            while ( v15 );
            *(_QWORD *)v16 = *(_QWORD *)v17;
            v25 = a2[1];
            v32 = *a1;
            if ( v25 == a2[2] )
              std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_reallocate<std::pair<DirQueItem,unsigned short const *>>(
                a2,
                v25,
                v31);
            else
              std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,unsigned short const *>>(
                (__int64)a2,
                (__int64)v31,
                128);
          }
        }
        else
        {
          v5 = -2147024893;
        }
        goto LABEL_6;
      }
    }
  }
  v8 = (unsigned __int16 *)lpFileName[1];
LABEL_6:
  if ( ppszPath[1] )
    CoTaskMemFree(ppszPath[1]);
  v9 = lpMem[1];
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  if ( v8 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800212f0  mov     [rsp-8+arg_0], rbx
0x1800212f5  mov     [rsp-8+arg_10], rsi
0x1800212fa  push    rbp
0x1800212fb  push    rdi
0x1800212fc  push    r14
0x1800212fe  lea     rbp, [rsp-3A0h]
0x180021306  sub     rsp, 4A0h
0x18002130d  mov     rax, cs:__security_cookie
0x180021314  xor     rax, rsp
0x180021317  mov     [rbp+3B0h+var_20], rax
0x18002131e  mov     rsi, rdx
0x180021321  mov     r14, rcx
0x180021324  xor     edx, edx; Val
0x180021326  lea     rcx, [rbp+3B0h+var_230]; void *
0x18002132d  mov     r8d, 208h; Size
0x180021333  call    memset_0
0x180021338  xorps   xmm0, xmm0
0x18002133b  mov     qword ptr [rsp+4B0h+var_480.Length], 80006h
0x180021344  lea     rax, asc_180033A78; "\\\\?"
0x18002134b  mov     qword ptr [rsp+4B0h+var_470.Length], 140012h
0x180021354  mov     [rsp+4B0h+var_480.Buffer], rax
0x180021359  lea     r9, [rsp+4B0h+ppszPath+8]; ppszPath
0x18002135e  lea     rax, aInstaller; "Installer"
0x180021365  xorps   xmm1, xmm1
0x180021368  xor     r8d, r8d; hToken
0x18002136b  mov     [rsp+4B0h+var_470.Buffer], rax
0x180021370  xor     edx, edx; dwFlags
0x180021372  lea     rcx, FOLDERID_Windows; rfid
0x180021379  movups  xmmword ptr [rsp+4B0h+ppszPath], xmm0; int
0x18002137e  movups  xmmword ptr [rsp+4B0h+lpMem], xmm0
0x180021383  movups  xmmword ptr [rsp+4B0h+lpFileName], xmm1
0x180021388  call    cs:__imp_SHGetKnownFolderPath
0x18002138e  mov     ebx, eax
0x180021390  test    eax, eax
0x180021392  jns     short loc_1800213B1
0x180021394  mov     rcx, [rbp+3B8h]; this
0x18002139b  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800213a2  mov     r9d, eax; char *
0x1800213a5  mov     edx, 488h; void *
0x1800213aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213af  jmp     short loc_180021421
0x1800213b1  mov     rcx, [rsp+4B0h+ppszPath+8]; Source
0x1800213b6  mov     ebx, 104h
0x1800213bb  mov     edx, ebx; MaxCount
0x1800213bd  call    cs:__imp_wcsnlen
0x1800213c3  add     ax, ax
0x1800213c6  mov     word ptr [rsp+4B0h+ppszPath], ax
0x1800213cb  cmp     ax, bx
0x1800213ce  jnz     short loc_18002144A
0x1800213d0  mov     ebx, 80010135h
0x1800213d5  mov     rdi, [rsp+4B0h+lpFileName+8]
0x1800213da  mov     rcx, [rsp+4B0h+ppszPath+8]; pv
0x1800213df  test    rcx, rcx
0x1800213e2  jz      short loc_1800213EA
0x1800213e4  call    cs:__imp_CoTaskMemFree
0x1800213ea  mov     rsi, [rsp+4B0h+lpMem+8]
0x1800213ef  test    rsi, rsi
0x1800213f2  jz      short loc_180021408
0x1800213f4  call    cs:__imp_GetProcessHeap
0x1800213fa  mov     r8, rsi; lpMem
0x1800213fd  xor     edx, edx; dwFlags
0x1800213ff  mov     rcx, rax; hHeap
0x180021402  call    cs:__imp_HeapFree
0x180021408  test    rdi, rdi
0x18002140b  jz      short loc_180021421
0x18002140d  call    cs:__imp_GetProcessHeap
0x180021413  mov     r8, rdi; lpMem
0x180021416  xor     edx, edx; dwFlags
0x180021418  mov     rcx, rax; hHeap
0x18002141b  call    cs:__imp_HeapFree
0x180021421  mov     eax, ebx
0x180021423  mov     rcx, [rbp+3B0h+var_20]
0x18002142a  xor     rcx, rsp; StackCookie
0x18002142d  call    __security_check_cookie
0x180021432  lea     r11, [rsp+4B0h+var_10]
0x18002143a  mov     rbx, [r11+20h]
0x18002143e  mov     rsi, [r11+30h]
0x180021442  mov     rsp, r11
0x180021445  pop     r14
0x180021447  pop     rdi
0x180021448  pop     rbp
0x180021449  retn
0x18002144a  add     ax, 2
0x18002144e  lea     r9, [rsp+4B0h+lpMem]; struct _UNICODE_STRING *
0x180021453  lea     rdx, [rsp+4B0h+ppszPath]; struct _UNICODE_STRING *
0x180021458  mov     word ptr [rsp+4B0h+ppszPath+2], ax
0x18002145d  lea     rcx, [rsp+4B0h+var_480]; struct _UNICODE_STRING *
0x180021462  call    ?CombinePathParts@@YAJPEAU_UNICODE_STRING@@0G0@Z; CombinePathParts(_UNICODE_STRING *,_UNICODE_STRING *,ushort,_UNICODE_STRING *)
0x180021467  mov     ebx, eax
0x180021469  test    eax, eax
0x18002146b  js      loc_1800213D5
0x180021471  lea     r9, [rsp+4B0h+lpFileName]; struct _UNICODE_STRING *
0x180021476  lea     rdx, [rsp+4B0h+var_470]; struct _UNICODE_STRING *
0x18002147b  lea     rcx, [rsp+4B0h+lpMem]; struct _UNICODE_STRING *
0x180021480  call    ?CombinePathParts@@YAJPEAU_UNICODE_STRING@@0G0@Z; CombinePathParts(_UNICODE_STRING *,_UNICODE_STRING *,ushort,_UNICODE_STRING *)
0x180021485  mov     ebx, eax
0x180021487  test    eax, eax
0x180021489  js      loc_1800213D5
0x18002148f  mov     rdi, [rsp+4B0h+lpFileName+8]
0x180021494  mov     rcx, rdi; lpFileName
0x180021497  call    cs:__imp_GetFileAttributesW
0x18002149d  cmp     eax, 16h
0x1800214a0  jz      short loc_1800214AC
0x1800214a2  mov     ebx, 80070003h
0x1800214a7  jmp     loc_1800213DA
0x1800214ac  mov     r8, rdi; unsigned __int16 *
0x1800214af  lea     rcx, [rbp+3B0h+var_230]; unsigned __int16 *
0x1800214b6  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800214bb  mov     ebx, eax
0x1800214bd  test    eax, eax
0x1800214bf  js      loc_1800213DA
0x1800214c5  mov     ecx, 4
0x1800214ca  lea     rdx, [rsp+4B0h+var_440]
0x1800214cf  lea     rax, [rbp+3B0h+var_230]
0x1800214d6  lea     r8d, [rcx+7Ch]
0x1800214da  movups  xmm0, xmmword ptr [rax]
0x1800214dd  movups  xmm1, xmmword ptr [rax+10h]
0x1800214e1  movups  xmmword ptr [rdx], xmm0
0x1800214e4  movups  xmm0, xmmword ptr [rax+20h]
0x1800214e8  movups  xmmword ptr [rdx+10h], xmm1
0x1800214ec  movups  xmm1, xmmword ptr [rax+30h]
0x1800214f0  movups  xmmword ptr [rdx+20h], xmm0
0x1800214f4  movups  xmm0, xmmword ptr [rax+40h]
0x1800214f8  movups  xmmword ptr [rdx+30h], xmm1
0x1800214fc  movups  xmm1, xmmword ptr [rax+50h]
0x180021500  movups  xmmword ptr [rdx+40h], xmm0
0x180021504  movups  xmm0, xmmword ptr [rax+60h]
0x180021508  movups  xmmword ptr [rdx+50h], xmm1
0x18002150c  movups  xmm1, xmmword ptr [rax+70h]
0x180021510  add     rax, r8
0x180021513  movups  xmmword ptr [rdx+60h], xmm0
0x180021517  movups  xmmword ptr [rdx+70h], xmm1
0x18002151b  add     rdx, r8
0x18002151e  sub     rcx, 1
0x180021522  jnz     short loc_1800214DA
0x180021524  mov     rax, [rax]
0x180021527  mov     rcx, rsi
0x18002152a  mov     [rdx], rax
0x18002152d  mov     rdx, [rsi+8]
0x180021531  mov     rax, [r14]
0x180021534  mov     [rbp+3B0h+var_238], rax
0x18002153b  cmp     rdx, [rsi+10h]
0x18002153f  jz      short loc_180021550
0x180021541  lea     rdx, [rsp+4B0h+var_440]
0x180021546  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAAEAU?$pair@UDirQueItem@@PEBG@1@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> &&)
0x18002154b  jmp     loc_1800213DA
0x180021550  lea     r8, [rsp+4B0h+var_440]
0x180021555  call    ??$_Emplace_reallocate@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAPEAU?$pair@UDirQueItem@@PEBG@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_reallocate<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> * const,std::pair<DirQueItem,ushort const *> &&)
0x18002155a  jmp     loc_1800213DA
```
