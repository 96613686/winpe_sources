# CreateBitMapFileMapping(HMENU__ *,uint,uint,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> *,std::vector<ulong,std::allocator<ulong>> *)

- ea: `0x180001db0`
- end: `0x180002127`
- name: `?CreateBitMapFileMapping@@YAXPEAUHMENU__@@IIPEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@PEAV?$vector@KV?$allocator@K@std@@@3@@Z`
- size: `887`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180001db0`
- `0x18000314c`

## callees

- `0x180001db0`
- `0x180002130`
- `0x180003760`
- `0x1800037e4`
- `0x1800054d8`
- `0x180005540`
- `0x1800056ac`
- `0x18000844c`
- `0x180009da8`
- `0x180009dcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800020fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800020f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002111`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoA` at `0x180001e58`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoA` at `0x180001e58`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180001e07`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemCount` at `0x180001e07`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180001ef8`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180001ef8`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180001eef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall CreateBitMapFileMapping(HMENU a1, UINT a2, UINT a3, __int64 a4, __int64 a5)
{
  int v5; // r14d
  HMENU v8; // rdi
  unsigned int v9; // r8d
  int MenuItemCount; // r15d
  signed int i; // esi
  unsigned int v12; // r8d
  const char *v13; // r9
  char *v14; // r14
  HDC DC; // rbx
  unsigned int v17; // r8d
  const char *v18; // r9
  HBITMAP v19; // r9
  DWORD LastError; // edi
  HBITMAP hbmpChecked; // r9
  DWORD v22; // edi
  HBITMAP hbmpUnchecked; // r9
  int v24; // [rsp+20h] [rbp-61h]
  int hbmpItem; // [rsp+30h] [rbp-51h] BYREF
  HANDLE TargetHandle[3]; // [rsp+38h] [rbp-49h] BYREF
  tagMENUITEMINFOA mii; // [rsp+50h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v5 = a4;
  v8 = a1;
  if ( !(unsigned __int8)IsGetDCPresent()
    || !(unsigned __int8)IsDeleteDCPresent()
    || !(unsigned __int8)IsGetMenuItemInfoWPresent()
    || !(unsigned __int8)IsGetMenuItemInfoWPresent() )
  {
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x106, v9, (const char *)0x80004001LL, v24);
  }
  DC = GetDC(0);
  TargetHandle[1] = DC;
  if ( !DC )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x10A, v17, v18);
  MenuItemCount = GetMenuItemCount(v8);
  for ( i = 0; i < MenuItemCount; ++i )
  {
    memset(&mii.fType, 0, 72);
    mii.cbSize = 80;
    mii.fMask = 142;
    if ( !GetMenuItemInfoA(v8, i, 1, &mii) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x114, v12, v13);
    if ( mii.wID >= a2 && mii.wID <= a3 )
    {
      if ( mii.hSubMenu )
        CreateBitMapFileMapping(mii.hSubMenu, a2, a3, v5, a5);
      v14 = 0;
      TargetHandle[0] = 0;
      if ( mii.hbmpItem )
      {
        if ( (unsigned __int8)IsNewHBitmapToAddToFileMapping(a5, LODWORD(mii.hbmpItem)) )
        {
          TargetHandle[0] = 0;
          LoadSingleBitmapIntoSection(DC, v19, TargetHandle);
          v14 = (char *)TargetHandle[0];
          if ( (unsigned __int64)TargetHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::push_back(
              a4,
              TargetHandle);
            hbmpItem = (int)mii.hbmpItem;
            std::vector<unsigned long>::push_back(a5, &hbmpItem);
            v14 = (char *)TargetHandle[0];
          }
        }
      }
      if ( mii.hbmpChecked && (unsigned __int8)IsNewHBitmapToAddToFileMapping(a5, LODWORD(mii.hbmpChecked)) )
      {
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastError = GetLastError();
          CloseHandle(v14);
          SetLastError(LastError);
          hbmpChecked = mii.hbmpChecked;
          v8 = a1;
        }
        TargetHandle[0] = 0;
        LoadSingleBitmapIntoSection(DC, hbmpChecked, TargetHandle);
        v14 = (char *)TargetHandle[0];
        if ( (unsigned __int64)TargetHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::push_back(
            a4,
            TargetHandle);
          hbmpItem = (int)mii.hbmpChecked;
          std::vector<unsigned long>::push_back(a5, &hbmpItem);
          v14 = (char *)TargetHandle[0];
        }
      }
      if ( mii.hbmpUnchecked && (unsigned __int8)IsNewHBitmapToAddToFileMapping(a5, LODWORD(mii.hbmpUnchecked)) )
      {
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v22 = GetLastError();
          CloseHandle(v14);
          SetLastError(v22);
          hbmpUnchecked = mii.hbmpUnchecked;
          v8 = a1;
        }
        TargetHandle[0] = 0;
        LoadSingleBitmapIntoSection(DC, hbmpUnchecked, TargetHandle);
        v14 = (char *)TargetHandle[0];
        if ( (unsigned __int64)TargetHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::push_back(
            a4,
            TargetHandle);
          hbmpItem = (int)mii.hbmpUnchecked;
          std::vector<unsigned long>::push_back(a5, &hbmpItem);
          v14 = (char *)TargetHandle[0];
        }
      }
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
      v5 = a4;
    }
  }
  return DeleteDC(DC);
}

```

## disassembly

```asm
0x180001db0  mov     [rsp-8+arg_8], rbx
0x180001db5  mov     [rsp-8+arg_18], r9
0x180001dba  mov     [rsp-8+arg_0], rcx
0x180001dbf  push    rbp
0x180001dc0  push    rsi
0x180001dc1  push    rdi
0x180001dc2  push    r12
0x180001dc4  push    r13
0x180001dc6  push    r14
0x180001dc8  push    r15
0x180001dca  lea     rbp, [rsp-1Fh]
0x180001dcf  sub     rsp, 0A0h
0x180001dd6  mov     r14, r9
0x180001dd9  mov     r12d, r8d
0x180001ddc  mov     r13d, edx
0x180001ddf  mov     rdi, rcx
0x180001de2  call    IsGetDCPresent
0x180001de7  test    al, al
0x180001de9  jnz     loc_18000202F
0x180001def  mov     rcx, [rbp+57h]; this
0x180001df3  mov     edx, 106h; void *
0x180001df8  mov     r9d, 80004001h; char *
0x180001dfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180001e04  mov     rcx, rdi; hMenu
0x180001e07  call    cs:__imp_GetMenuItemCount
0x180001e0d  mov     r15d, eax
0x180001e10  xor     eax, eax
0x180001e12  mov     esi, eax
0x180001e14  test    r15d, r15d
0x180001e17  jle     loc_180001ED2
0x180001e1d  mov     qword ptr [rbp+4Fh+mii.fType], rax
0x180001e21  xorps   xmm0, xmm0
0x180001e24  movdqa  xmmword ptr [rbp+4Fh+mii.wID], xmm0
0x180001e29  xorps   xmm1, xmm1
0x180001e2c  movdqa  xmmword ptr [rbp+4Fh+mii.hbmpChecked], xmm1
0x180001e31  movdqa  xmmword ptr [rbp+4Fh+mii.dwItemData], xmm0
0x180001e36  movdqa  xmmword ptr [rbp+4Fh+mii.cch], xmm1
0x180001e3b  mov     [rbp+4Fh+mii.cbSize], 50h ; 'P'
0x180001e42  mov     [rbp+4Fh+mii.fMask], 8Eh
0x180001e49  lea     r9, [rbp+4Fh+mii]; lpmii
0x180001e4d  mov     r8d, 1; fByPosition
0x180001e53  mov     edx, esi; item
0x180001e55  mov     rcx, rdi; hmenu
0x180001e58  call    cs:__imp_GetMenuItemInfoA
0x180001e5e  mov     rcx, [rbp+57h]; this
0x180001e62  test    eax, eax
0x180001e64  jz      loc_18000211C
0x180001e6a  mov     eax, [rbp+4Fh+mii.wID]
0x180001e6d  cmp     eax, r13d
0x180001e70  jb      short loc_180001EC4
0x180001e72  cmp     eax, r12d
0x180001e75  ja      short loc_180001EC4
0x180001e77  mov     rcx, [rbp+4Fh+mii.hSubMenu]
0x180001e7b  test    rcx, rcx
0x180001e7e  jnz     loc_18000205B
0x180001e84  xor     r14d, r14d
0x180001e87  mov     [rbp+4Fh+TargetHandle], r14
0x180001e8b  mov     r9, [rbp+4Fh+mii.hbmpItem]
0x180001e8f  test    r9, r9
0x180001e92  jnz     loc_180002077
0x180001e98  mov     r9, [rbp+4Fh+mii.hbmpChecked]
0x180001e9c  test    r9, r9
0x180001e9f  jnz     loc_180002090
0x180001ea5  mov     r9, [rbp+4Fh+mii.hbmpUnchecked]
0x180001ea9  test    r9, r9
0x180001eac  jnz     loc_1800020CF
0x180001eb2  lea     rax, [r14-1]
0x180001eb6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001eba  jbe     loc_18000210E
0x180001ec0  mov     r14, [rbp+4Fh+arg_18]
0x180001ec4  inc     esi
0x180001ec6  cmp     esi, r15d
0x180001ec9  jge     short loc_180001ED2
0x180001ecb  xor     eax, eax
0x180001ecd  jmp     loc_180001E1D
0x180001ed2  mov     rcx, rbx
0x180001ed5  mov     rbx, [rsp+0D0h+arg_8]
0x180001edd  add     rsp, 0A0h
0x180001ee4  pop     r15
0x180001ee6  pop     r14
0x180001ee8  pop     r13
0x180001eea  pop     r12
0x180001eec  pop     rdi
0x180001eed  pop     rsi
0x180001eee  pop     rbp
0x180001eef  jmp     cs:__imp_DeleteDC
0x180001ef6  xor     ecx, ecx; hWnd
0x180001ef8  call    cs:__imp_GetDC
0x180001efe  mov     rbx, rax
0x180001f01  mov     [rbp+4Fh+var_90], rax
0x180001f05  mov     rcx, [rbp+57h]; this
0x180001f09  test    rax, rax
0x180001f0c  jnz     loc_180001E04
0x180001f12  mov     edx, 10Ah; void *
0x180001f17  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180001f1d  mov     [rbp+4Fh+TargetHandle], 0
0x180001f25  lea     r8, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x180001f29  mov     rdx, r9; hbm
0x180001f2c  mov     rcx, rbx; hdc
0x180001f2f  call    ?LoadSingleBitmapIntoSection@@YAXPEAUHDC__@@PEAUHBITMAP__@@PEAPEAX@Z; LoadSingleBitmapIntoSection(HDC__ *,HBITMAP__ *,void * *)
0x180001f34  mov     r14, [rbp+4Fh+TargetHandle]
0x180001f38  lea     rax, [r14-1]
0x180001f3c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001f40  ja      loc_180001E98
0x180001f46  lea     rdx, [rbp+4Fh+TargetHandle]
0x180001f4a  mov     rcx, [rbp+4Fh+arg_18]
0x180001f4e  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180001f53  mov     eax, dword ptr [rbp+4Fh+mii.hbmpItem]
0x180001f56  mov     [rbp+4Fh+var_A0], eax
0x180001f59  lea     rdx, [rbp+4Fh+var_A0]
0x180001f5d  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x180001f61  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAX$$QEAK@Z; std::vector<ulong>::push_back(ulong &&)
0x180001f66  mov     r14, [rbp+4Fh+TargetHandle]
0x180001f6a  jmp     loc_180001E98
0x180001f6f  lea     rax, [r14-1]
0x180001f73  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001f77  jbe     loc_1800020A9
0x180001f7d  mov     [rbp+4Fh+TargetHandle], 0
0x180001f85  lea     r8, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x180001f89  mov     rdx, r9; hbm
0x180001f8c  mov     rcx, rbx; hdc
0x180001f8f  call    ?LoadSingleBitmapIntoSection@@YAXPEAUHDC__@@PEAUHBITMAP__@@PEAPEAX@Z; LoadSingleBitmapIntoSection(HDC__ *,HBITMAP__ *,void * *)
0x180001f94  mov     r14, [rbp+4Fh+TargetHandle]
0x180001f98  lea     rax, [r14-1]
0x180001f9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001fa0  ja      loc_180001EA5
0x180001fa6  lea     rdx, [rbp+4Fh+TargetHandle]
0x180001faa  mov     rcx, [rbp+4Fh+arg_18]
0x180001fae  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180001fb3  mov     eax, dword ptr [rbp+4Fh+mii.hbmpChecked]
0x180001fb6  mov     [rbp+4Fh+var_A0], eax
0x180001fb9  lea     rdx, [rbp+4Fh+var_A0]
0x180001fbd  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x180001fc1  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAX$$QEAK@Z; std::vector<ulong>::push_back(ulong &&)
0x180001fc6  mov     r14, [rbp+4Fh+TargetHandle]
0x180001fca  jmp     loc_180001EA5
0x180001fcf  lea     rax, [r14-1]
0x180001fd3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001fd7  jbe     loc_1800020E8
0x180001fdd  mov     [rbp+4Fh+TargetHandle], 0
0x180001fe5  lea     r8, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x180001fe9  mov     rdx, r9; hbm
0x180001fec  mov     rcx, rbx; hdc
0x180001fef  call    ?LoadSingleBitmapIntoSection@@YAXPEAUHDC__@@PEAUHBITMAP__@@PEAPEAX@Z; LoadSingleBitmapIntoSection(HDC__ *,HBITMAP__ *,void * *)
0x180001ff4  mov     r14, [rbp+4Fh+TargetHandle]
0x180001ff8  lea     rax, [r14-1]
0x180001ffc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002000  ja      loc_180001EB2
0x180002006  lea     rdx, [rbp+4Fh+TargetHandle]
0x18000200a  mov     rcx, [rbp+4Fh+arg_18]
0x18000200e  call    ?push_back@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180002013  mov     eax, dword ptr [rbp+4Fh+mii.hbmpUnchecked]
0x180002016  mov     [rbp+4Fh+var_A0], eax
0x180002019  lea     rdx, [rbp+4Fh+var_A0]
0x18000201d  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x180002021  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAX$$QEAK@Z; std::vector<ulong>::push_back(ulong &&)
0x180002026  mov     r14, [rbp+4Fh+TargetHandle]
0x18000202a  jmp     loc_180001EB2
0x18000202f  call    IsDeleteDCPresent
0x180002034  test    al, al
0x180002036  jz      loc_180001DEF
0x18000203c  call    IsGetMenuItemInfoWPresent
0x180002041  test    al, al
0x180002043  jz      loc_180001DEF
0x180002049  call    IsGetMenuItemInfoWPresent
0x18000204e  test    al, al
0x180002050  jz      loc_180001DEF
0x180002056  jmp     loc_180001EF6
0x18000205b  mov     rax, qword ptr [rbp+4Fh+arg_20]
0x18000205f  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180002064  mov     r9, r14
0x180002067  mov     r8d, r12d
0x18000206a  mov     edx, r13d
0x18000206d  call    ?CreateBitMapFileMapping@@YAXPEAUHMENU__@@IIPEAV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@PEAV?$vector@KV?$allocator@K@std@@@3@@Z; CreateBitMapFileMapping(HMENU__ *,uint,uint,std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> *,std::vector<ulong> *)
0x180002072  jmp     loc_180001E84
0x180002077  mov     edx, r9d
0x18000207a  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x18000207e  call    ?IsNewHBitmapToAddToFileMapping@@YA_NPEAV?$vector@KV?$allocator@K@std@@@std@@K@Z; IsNewHBitmapToAddToFileMapping(std::vector<ulong> *,ulong)
0x180002083  test    al, al
0x180002085  jz      loc_180001E98
0x18000208b  jmp     loc_180001F1D
0x180002090  mov     edx, r9d
0x180002093  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x180002097  call    ?IsNewHBitmapToAddToFileMapping@@YA_NPEAV?$vector@KV?$allocator@K@std@@@std@@K@Z; IsNewHBitmapToAddToFileMapping(std::vector<ulong> *,ulong)
0x18000209c  test    al, al
0x18000209e  jz      loc_180001EA5
0x1800020a4  jmp     loc_180001F6F
0x1800020a9  call    cs:__imp_GetLastError
0x1800020af  mov     edi, eax
0x1800020b1  mov     rcx, r14; hObject
0x1800020b4  call    cs:__imp_CloseHandle
0x1800020ba  mov     ecx, edi; dwErrCode
0x1800020bc  call    cs:__imp_SetLastError
0x1800020c2  mov     r9, [rbp+4Fh+mii.hbmpChecked]
0x1800020c6  mov     rdi, [rbp+4Fh+arg_0]
0x1800020ca  jmp     loc_180001F7D
0x1800020cf  mov     edx, r9d
0x1800020d2  mov     rcx, qword ptr [rbp+4Fh+arg_20]
0x1800020d6  call    ?IsNewHBitmapToAddToFileMapping@@YA_NPEAV?$vector@KV?$allocator@K@std@@@std@@K@Z; IsNewHBitmapToAddToFileMapping(std::vector<ulong> *,ulong)
0x1800020db  test    al, al
0x1800020dd  jz      loc_180001EB2
0x1800020e3  jmp     loc_180001FCF
0x1800020e8  call    cs:__imp_GetLastError
0x1800020ee  mov     edi, eax
0x1800020f0  mov     rcx, r14; hObject
0x1800020f3  call    cs:__imp_CloseHandle
0x1800020f9  mov     ecx, edi; dwErrCode
0x1800020fb  call    cs:__imp_SetLastError
0x180002101  mov     r9, [rbp+4Fh+mii.hbmpUnchecked]
0x180002105  mov     rdi, [rbp+4Fh+arg_0]
0x180002109  jmp     loc_180001FDD
0x18000210e  mov     rcx, r14; hObject
0x180002111  call    cs:__imp_CloseHandle
0x180002117  jmp     loc_180001EC0
0x18000211c  mov     edx, 114h; void *
0x180002121  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
