# Pal::WinRTPathInformation::getStorageFolderItem(ABI::Windows::Storage::IStorageFolder *,ABI::Windows::Storage::IStorageItem * *)

- ea: `0x180018460`
- end: `0x18001853f`
- name: `?getStorageFolderItem@WinRTPathInformation@Pal@@CAXPEAUIStorageFolder@Storage@Windows@ABI@@PEAPEAUIStorageItem@456@@Z`
- size: `223`
- prototype: `void __fastcall(struct ABI::Windows::Storage::IStorageFolder *, struct ABI::Windows::Storage::IStorageItem **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180018548`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000cd80`
- `0x18001006c`
- `0x180010b18`
- `0x180018460`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800184cf`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800184cf`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800184da`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x1800184da`

## pseudocode

```c
void __fastcall Pal::WinRTPathInformation::getStorageFolderItem(
        struct ABI::Windows::Storage::IStorageFolder *a1,
        struct ABI::Windows::Storage::IStorageItem **a2)
{
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v8[16]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v9[8]; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v10[232]; // [rsp+58h] [rbp-120h] BYREF
  _BYTE v11[32]; // [rsp+140h] [rbp-38h] BYREF

  v2 = (**(__int64 (__fastcall ***)(struct ABI::Windows::Storage::IStorageFolder *, GUID *, struct ABI::Windows::Storage::IStorageItem **))a1)(
         a1,
         &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
         a2);
  if ( v2 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v8);
    v3 = std::operator<<<std::char_traits<char>>(
           (__int64)v9,
           (__int64)"IOImplWinRT::getStorageFolderItem - QueryInterface failed for IStorageItem interface");
    v4 = std::operator<<<std::char_traits<char>>(v3, (__int64)" (HRESULT: 0x");
    v5 = std::ostream::operator<<(v4, std::hex);
    v6 = std::ostream::operator<<(v5, (unsigned int)v2);
    std::operator<<<std::char_traits<char>>(v6, (__int64)")");
    std::stringbuf::str(v10, v11);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180018460  push    rbx
0x180018462  sub     rsp, 170h
0x180018469  mov     rax, cs:__security_cookie
0x180018470  xor     rax, rsp
0x180018473  mov     [rsp+178h+var_18], rax
0x18001847b  mov     rax, [rcx]
0x18001847e  mov     r8, rdx
0x180018481  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180018488  mov     rax, [rax]
0x18001848b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018490  mov     ebx, eax
0x180018492  test    eax, eax
0x180018494  jns     loc_180018526
0x18001849a  lea     rcx, [rsp+178h+var_138]
0x18001849f  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800184a4  nop
0x1800184a5  lea     rdx, aIoimplwinrtGet; "IOImplWinRT::getStorageFolderItem - Que"...
0x1800184ac  lea     rcx, [rsp+178h+var_128]
0x1800184b1  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800184b6  mov     rcx, rax
0x1800184b9  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x1800184c0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800184c5  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800184cc  mov     rcx, rax
0x1800184cf  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800184d5  mov     edx, ebx
0x1800184d7  mov     rcx, rax
0x1800184da  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x1800184e0  mov     rcx, rax
0x1800184e3  lea     rdx, asc_180048470; ")"
0x1800184ea  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800184ef  lea     rdx, [rsp+178h+var_38]
0x1800184f7  lea     rcx, [rsp+178h+var_120]
0x1800184fc  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180018501  nop
0x180018502  lea     rdx, [rsp+178h+var_38]
0x18001850a  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18001850f  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180018514  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001851b  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180018520  call    _CxxThrowException_0
0x180018526  mov     rcx, [rsp+178h+var_18]
0x18001852e  xor     rcx, rsp; StackCookie
0x180018531  call    __security_check_cookie
0x180018536  add     rsp, 170h
0x18001853d  pop     rbx
0x18001853e  retn
```
