# PropVariantToIDList

- ea: `0x18000a910`
- end: `0x18000ac01`
- name: `PropVariantToIDList`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a350`
- `0x180014d70`

## callees

- `0x18000a910`
- `0x180041620`
- `0x1800435e0`
- `0x180047660`
- `0x18008be24`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Read` at `0x18000aaeb`
- `SHCORE!IStream_Read` at `0x18000aaeb`
- `SHCORE!IStream_Size` at `0x18000aaa3`
- `SHCORE!IStream_Size` at `0x18000aaa3`
- `Windows.Storage!SHParseDisplayName` at `0x18000aa4c`
- `Windows.Storage!SHParseDisplayName` at `0x18000aa4c`
- `Windows.Storage!ILClone` at `0x18000a984`
- `Windows.Storage!ILClone` at `0x18000a984`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000a9ec`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000aa0a`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000aa2e`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000a9ec`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000aa0a`
- `Windows.Storage!SHGetSpecialFolderLocation` at `0x18000aa2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab17`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000ab37`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000ab37`

## pseudocode

```c
__int64 __fastcall PropVariantToIDList(unsigned __int16 *a1, struct _ITEMIDLIST_ABSOLUTE **a2)
{
  unsigned int v4; // eax
  HRESULT IDListFromObject; // edi
  unsigned int v6; // r10d
  unsigned int v7; // edx
  const ITEMIDLIST *v8; // r11
  const ITEMIDLIST *v9; // r8
  __int64 cb; // rax
  LPITEMIDLIST v11; // rax
  unsigned __int64 v13; // rdx
  int (__fastcall ***v14)(_QWORD, GUID *, IStream **); // rcx
  void *v15; // rcx
  ITEMIDLIST *v16; // rbx
  const struct _ITEMIDLIST_RELATIVE *v17; // r11
  struct IUnknown **v18; // rcx
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+8h] BYREF
  IStream *pstm; // [rsp+58h] [rbp+10h] BYREF
  void *pv; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = *a1;
  IDListFromObject = -2147024809;
  if ( v4 == 4113 )
  {
    v6 = *((_DWORD *)a1 + 2);
    v7 = 2;
    v8 = (const ITEMIDLIST *)*((_QWORD *)a1 + 2);
    v9 = v8;
    if ( v6 >= 2 )
    {
      while ( 1 )
      {
        cb = v9->mkid.cb;
        if ( (unsigned int)cb < 2 || (unsigned int)cb > v6 - v7 )
          break;
        v7 += cb;
        v9 = (const ITEMIDLIST *)((char *)v9 + cb);
        if ( v7 > v6 )
          return (unsigned int)IDListFromObject;
      }
      if ( !(_WORD)cb && v7 <= v6 )
      {
        if ( v8 )
        {
          v11 = ILClone(v8);
          IDListFromObject = 0;
          if ( !v11 )
            IDListFromObject = -2147024882;
        }
        else
        {
          v11 = 0;
        }
        *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v11;
      }
    }
  }
  else if ( v4 > 0x2011 )
  {
    if ( v4 == 16393 )
    {
      v18 = (struct IUnknown **)*((_QWORD *)a1 + 1);
      if ( v18 )
        return (unsigned int)_GetIDListFromObject(*v18, a2);
    }
  }
  else if ( v4 == 8209 )
  {
    if ( SafeArrayGetDim(*((SAFEARRAY **)a1 + 1)) == 1
      && IDListContainerIsConsistent(
           *(LPCITEMIDLIST *)(*((_QWORD *)a1 + 1) + 16LL),
           *(_DWORD *)(*((_QWORD *)a1 + 1) + 24LL)) )
    {
      return (unsigned int)SHILClone(v17, a2);
    }
  }
  else
  {
    switch ( *a1 )
    {
      case 2u:
        IDListFromObject = SHGetSpecialFolderLocation(0, (__int16)a1[4] | 0x8000, (LPITEMIDLIST *)a2);
        break;
      case 3u:
      case 0x13u:
        LODWORD(v13) = *((_DWORD *)a1 + 2);
        if ( (int)v13 < 0xFFFF )
          goto LABEL_19;
        break;
      case 8u:
      case 0x1Fu:
        IDListFromObject = SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
        break;
      case 9u:
      case 0xDu:
        IDListFromObject = _GetIDListFromObject(*((struct IUnknown **)a1 + 1), a2);
        break;
      case 0x14u:
      case 0x15u:
        v13 = *((_QWORD *)a1 + 1);
        if ( v13 < 0xFFFF )
LABEL_19:
          IDListFromObject = SHGetSpecialFolderLocation(0, v13 | 0x8000, (LPITEMIDLIST *)a2);
        break;
      case 0x42u:
        v14 = (int (__fastcall ***)(_QWORD, GUID *, IStream **))*((_QWORD *)a1 + 1);
        pstm = 0;
        if ( (**v14)(v14, &GUID_0000000c_0000_0000_c000_000000000046, &pstm) >= 0 )
        {
          pui.QuadPart = 0;
          IDListFromObject = IStream_Size(pstm, &pui);
          if ( IDListFromObject >= 0 )
          {
            IDListFromObject = -2147024809;
            if ( !pui.HighPart )
            {
              pv = 0;
              IDListFromObject = CTCoAllocPolicy::Alloc(v15, 1u, pui.LowPart, &pv);
              if ( IDListFromObject >= 0 )
              {
                v16 = (ITEMIDLIST *)pv;
                IDListFromObject = IStream_Read(pstm, pv, pui.LowPart);
                if ( IDListFromObject >= 0 )
                {
                  IDListFromObject = -2147024809;
                  if ( IDListContainerIsConsistent(v16, pui.LowPart) )
                  {
                    *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v16;
                    IDListFromObject = 0;
                    v16 = 0;
                  }
                }
                CoTaskMemFree(v16);
              }
            }
          }
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
        }
        break;
      default:
        return (unsigned int)IDListFromObject;
    }
  }
  return (unsigned int)IDListFromObject;
}

```

## disassembly

```asm
0x18000a910  mov     [rsp+arg_18], rbx
0x18000a915  push    rbp
0x18000a916  push    rsi
0x18000a917  push    rdi
0x18000a918  sub     rsp, 30h
0x18000a91c  xor     ebp, ebp
0x18000a91e  mov     rsi, rdx
0x18000a921  mov     [rdx], rbp
0x18000a924  mov     rbx, rcx
0x18000a927  movzx   eax, word ptr [rcx]
0x18000a92a  mov     edi, 80070057h
0x18000a92f  cmp     eax, 1011h
0x18000a934  jnz     short loc_18000A9A9
0x18000a936  mov     r10d, [rcx+8]
0x18000a93a  mov     edx, 2
0x18000a93f  mov     r11, [rcx+10h]
0x18000a943  mov     r8, r11
0x18000a946  cmp     r10d, edx
0x18000a949  jb      short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a94b  nop     dword ptr [rax+rax+00h]
0x18000a950  movzx   eax, word ptr [r8]
0x18000a954  cmp     eax, 2
0x18000a957  jb      short loc_18000A96E
0x18000a959  mov     ecx, r10d
0x18000a95c  sub     ecx, edx
0x18000a95e  cmp     eax, ecx
0x18000a960  ja      short loc_18000A96E
0x18000a962  add     edx, eax
0x18000a964  add     r8, rax
0x18000a967  cmp     edx, r10d
0x18000a96a  jbe     short loc_18000A950
0x18000a96c  jmp     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a96e  cmp     bp, ax
0x18000a971  jnz     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a973  cmp     edx, r10d
0x18000a976  ja      short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a978  test    r11, r11
0x18000a97b  jz      loc_18000AB9A
0x18000a981  mov     rcx, r11; pidl
0x18000a984  call    cs:__imp_ILClone
0x18000a98a  mov     edi, ebp
0x18000a98c  mov     ecx, 8007000Eh
0x18000a991  test    rax, rax
0x18000a994  cmovz   edi, ecx
0x18000a997  mov     [rsi], rax
0x18000a99a  mov     rbx, [rsp+48h+arg_18]; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a99f  mov     eax, edi
0x18000a9a1  add     rsp, 30h
0x18000a9a5  pop     rdi
0x18000a9a6  pop     rsi
0x18000a9a7  pop     rbp
0x18000a9a8  retn
0x18000a9a9  cmp     eax, 2011h
0x18000a9ae  ja      loc_18000AB73
0x18000a9b4  jz      loc_18000AB33
0x18000a9ba  add     eax, 0FFFFFFFEh; switch 65 cases
0x18000a9bd  cmp     eax, 40h
0x18000a9c0  ja      short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a9c2  lea     rdx, __ImageBase
0x18000a9c9  cdqe
0x18000a9cb  movzx   eax, ds:(byte_18000ABC0 - 180000000h)[rdx+rax]
0x18000a9d3  mov     ecx, ds:(jpt_18000A9DD - 180000000h)[rdx+rax*4]
0x18000a9da  add     rcx, rdx
0x18000a9dd  jmp     rcx; switch jump
0x18000a9df  movsx   edx, word ptr [rbx+8]; jumptable 000000018000A9DD case 2
0x18000a9e3  mov     r8, rsi; ppidl
0x18000a9e6  bts     edx, 0Fh; csidl
0x18000a9ea  xor     ecx, ecx; hwnd
0x18000a9ec  call    cs:__imp_SHGetSpecialFolderLocation
0x18000a9f2  mov     edi, eax
0x18000a9f4  jmp     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000a9f6  mov     edx, [rbx+8]; jumptable 000000018000A9DD cases 3,19
0x18000a9f9  cmp     edx, 0FFFFh
0x18000a9ff  jge     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa01  bts     edx, 0Fh; csidl
0x18000aa05  mov     r8, rsi; ppidl
0x18000aa08  xor     ecx, ecx; hwnd
0x18000aa0a  call    cs:__imp_SHGetSpecialFolderLocation
0x18000aa10  mov     edi, eax
0x18000aa12  jmp     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa14  mov     rdx, [rbx+8]; jumptable 000000018000A9DD cases 20,21
0x18000aa18  cmp     rdx, 0FFFFh
0x18000aa1f  jnb     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa25  bts     edx, 0Fh; csidl
0x18000aa29  mov     r8, rsi; ppidl
0x18000aa2c  xor     ecx, ecx; hwnd
0x18000aa2e  call    cs:__imp_SHGetSpecialFolderLocation
0x18000aa34  mov     edi, eax
0x18000aa36  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa3b  mov     rcx, [rbx+8]; jumptable 000000018000A9DD cases 8,31
0x18000aa3f  xor     r9d, r9d; sfgaoIn
0x18000aa42  mov     r8, rsi; ppidl
0x18000aa45  mov     [rsp+48h+psfgaoOut], rbp; psfgaoOut
0x18000aa4a  xor     edx, edx; pbc
0x18000aa4c  call    cs:__imp_SHParseDisplayName
0x18000aa52  mov     edi, eax
0x18000aa54  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa59  mov     rcx, [rbx+8]; jumptable 000000018000A9DD cases 9,13
0x18000aa5d  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE **
0x18000aa60  call    ?_GetIDListFromObject@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObject(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x18000aa65  mov     edi, eax
0x18000aa67  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa6c  mov     rcx, [rbx+8]; jumptable 000000018000A9DD case 66
0x18000aa70  lea     r8, [rsp+48h+pstm]
0x18000aa75  mov     [rsp+48h+pstm], rbp
0x18000aa7a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000aa81  mov     rax, [rcx]
0x18000aa84  mov     rax, [rax]
0x18000aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa8c  test    eax, eax
0x18000aa8e  js      def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000aa94  mov     rcx, [rsp+48h+pstm]; pstm
0x18000aa99  lea     rdx, [rsp+48h+pui]; pui
0x18000aa9e  mov     qword ptr [rsp+48h+pui], rbp
0x18000aaa3  call    cs:__imp_IStream_Size
0x18000aaa9  mov     edi, eax
0x18000aaab  test    eax, eax
0x18000aaad  js      short loc_18000AB1D
0x18000aaaf  mov     edi, 80070057h
0x18000aab4  cmp     dword ptr [rsp+48h+pui+4], ebp
0x18000aab8  jnz     short loc_18000AB1D
0x18000aaba  mov     r8d, dword ptr [rsp+48h+pui]; unsigned __int64
0x18000aabf  lea     r9, [rsp+48h+pv]; void **
0x18000aac4  mov     edx, 1; unsigned int
0x18000aac9  mov     [rsp+48h+pv], rbp
0x18000aace  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000aad3  mov     edi, eax
0x18000aad5  test    eax, eax
0x18000aad7  js      short loc_18000AB1D
0x18000aad9  mov     rbx, [rsp+48h+pv]
0x18000aade  mov     r8d, dword ptr [rsp+48h+pui]; cb
0x18000aae3  mov     rdx, rbx; pv
0x18000aae6  mov     rcx, [rsp+48h+pstm]; pstm
0x18000aaeb  call    cs:__imp_IStream_Read
0x18000aaf1  mov     edi, eax
0x18000aaf3  test    eax, eax
0x18000aaf5  js      short loc_18000AB14
0x18000aaf7  mov     edx, dword ptr [rsp+48h+pui]; cbAlloc
0x18000aafb  mov     rcx, rbx; pidl
0x18000aafe  mov     edi, 80070057h
0x18000ab03  call    IDListContainerIsConsistent
0x18000ab08  test    eax, eax
0x18000ab0a  jz      short loc_18000AB14
0x18000ab0c  mov     [rsi], rbx
0x18000ab0f  mov     edi, ebp
0x18000ab11  mov     rbx, rbp
0x18000ab14  mov     rcx, rbx; pv
0x18000ab17  call    cs:__imp_CoTaskMemFree
0x18000ab1d  mov     rcx, [rsp+48h+pstm]
0x18000ab22  mov     rax, [rcx]
0x18000ab25  mov     rax, [rax+10h]
0x18000ab29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab2e  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab33  mov     rcx, [rcx+8]; psa
0x18000ab37  call    cs:__imp_SafeArrayGetDim
0x18000ab3d  cmp     eax, 1
0x18000ab40  jnz     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab46  mov     rdx, [rbx+8]
0x18000ab4a  mov     r11, [rdx+10h]
0x18000ab4e  mov     edx, [rdx+18h]; cbAlloc
0x18000ab51  mov     rcx, r11; pidl
0x18000ab54  call    IDListContainerIsConsistent
0x18000ab59  test    eax, eax
0x18000ab5b  jz      def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab61  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x18000ab64  mov     rcx, r11; struct _ITEMIDLIST_RELATIVE *
0x18000ab67  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18000ab6c  mov     edi, eax
0x18000ab6e  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab73  cmp     eax, 4009h
0x18000ab78  jnz     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab7e  mov     rcx, [rcx+8]
0x18000ab82  test    rcx, rcx
0x18000ab85  jz      def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab8b  mov     rcx, [rcx]; struct IUnknown *
0x18000ab8e  call    ?_GetIDListFromObject@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObject(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x18000ab93  mov     edi, eax
0x18000ab95  jmp     def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-7,10-12,14-18,22-30,32-65
0x18000ab9a  mov     rax, rbp
0x18000ab9d  jmp     loc_18000A997
```
