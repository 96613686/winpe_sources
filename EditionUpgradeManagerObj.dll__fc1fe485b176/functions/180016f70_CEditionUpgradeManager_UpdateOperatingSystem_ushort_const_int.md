# CEditionUpgradeManager::UpdateOperatingSystem(ushort const *,int)

- ea: `0x180016f70`
- end: `0x18001709b`
- name: `?UpdateOperatingSystem@CEditionUpgradeManager@@UEAAJPEBGH@Z`
- size: `299`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x180012f54`
- `0x180016f70`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017000`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017014`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017028`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017000`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017014`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017086`
- `pkeyhelper!GetProductKeyFromContentId` at `0x180016fe7`
- `pkeyhelper!GetProductKeyFromContentId` at `0x180016fe7`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::UpdateOperatingSystem(
        CEditionUpgradeManager *this,
        const unsigned __int16 *a2,
        int a3)
{
  int ProductKeyFromContentId; // ebx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  int v11; // [rsp+58h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  hMem = 0;
  if ( !a2 )
  {
    ProductKeyFromContentId = -2147024809;
    goto LABEL_3;
  }
  v8 = CClipLicense::EnsureModernLicenseForContentIdWithUserTicket(a2, (int)a2, 0, 0, &v11);
  ProductKeyFromContentId = v8;
  if ( v8 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ProductKeyFromContentId);
  if ( ProductKeyFromContentId < 0 )
    goto LABEL_3;
  ProductKeyFromContentId = v11;
  if ( v11 < 0 )
    goto LABEL_3;
  ProductKeyFromContentId = GetProductKeyFromContentId(a2, &hMem);
  if ( ProductKeyFromContentId == -2147023728 )
  {
    if ( !(unsigned int)_o__wcsicmp(L"58d710c5-f40f-7346-5664-9162b21ef52e", a2)
      || !(unsigned int)_o__wcsicmp(L"c185aecd-f928-6ae8-32a4-986fa1a7d3f0", a2)
      || !(unsigned int)_o__wcsicmp(L"96c4f8f5-b3da-5efe-f12d-d1b6fcc52269", a2) )
    {
      ProductKeyFromContentId = 1;
      goto LABEL_17;
    }
    goto LABEL_3;
  }
  if ( ProductKeyFromContentId < 0 )
  {
LABEL_3:
    v7 = (unsigned int)ProductKeyFromContentId;
    goto LABEL_16;
  }
  v9 = (*(__int64 (__fastcall **)(CEditionUpgradeManager *, HLOCAL, __int64, __int64, int))(*(_QWORD *)this + 48LL))(
         this,
         hMem,
         1,
         1,
         a3);
  ProductKeyFromContentId = v9;
  if ( v9 >= 0 )
    goto LABEL_17;
  v7 = (unsigned int)v9;
LABEL_16:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ProductKeyFromContentId);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)ProductKeyFromContentId;
}

```

## disassembly

```asm
0x180016f70  mov     [rsp+arg_0], rbx
0x180016f75  push    rbp
0x180016f76  push    rsi
0x180016f77  push    rdi
0x180016f78  sub     rsp, 30h
0x180016f7c  mov     [rsp+48h+arg_8], 0
0x180016f84  mov     ebp, r8d
0x180016f87  mov     [rsp+48h+hMem], 0
0x180016f90  mov     rdi, rdx
0x180016f93  mov     rsi, rcx
0x180016f96  test    rdx, rdx
0x180016f99  jnz     short loc_180016FA7
0x180016f9b  mov     ebx, 80070057h
0x180016fa0  mov     ecx, ebx
0x180016fa2  jmp     loc_180017070
0x180016fa7  lea     rax, [rsp+48h+arg_8]
0x180016fac  xor     r9d, r9d; unsigned __int16 *
0x180016faf  xor     r8d, r8d; int
0x180016fb2  mov     [rsp+48h+var_28], rax; int *
0x180016fb7  mov     rcx, rdi; unsigned __int16 *
0x180016fba  call    ?EnsureModernLicenseForContentIdWithUserTicket@CClipLicense@@SAJPEBGHHPEAGPEAJ@Z; CClipLicense::EnsureModernLicenseForContentIdWithUserTicket(ushort const *,int,int,ushort *,long *)
0x180016fbf  mov     ebx, eax
0x180016fc1  test    eax, eax
0x180016fc3  jns     short loc_180016FCC
0x180016fc5  mov     ecx, eax
0x180016fc7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016fcc  mov     ecx, ebx
0x180016fce  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016fd3  test    ebx, ebx
0x180016fd5  js      short loc_180016FA0
0x180016fd7  mov     ebx, [rsp+48h+arg_8]
0x180016fdb  test    ebx, ebx
0x180016fdd  js      short loc_180016FA0
0x180016fdf  lea     rdx, [rsp+48h+hMem]
0x180016fe4  mov     rcx, rdi
0x180016fe7  call    cs:__imp_GetProductKeyFromContentId
0x180016fed  mov     ebx, eax
0x180016fef  cmp     eax, 80070490h
0x180016ff4  jnz     short loc_18001703D
0x180016ff6  mov     rdx, rdi
0x180016ff9  lea     rcx, a58d710c5F40f73; "58d710c5-f40f-7346-5664-9162b21ef52e"
0x180017000  call    cs:__imp__o__wcsicmp
0x180017006  test    eax, eax
0x180017008  jz      short loc_180017036
0x18001700a  mov     rdx, rdi
0x18001700d  lea     rcx, aC185aecdF9286a; "c185aecd-f928-6ae8-32a4-986fa1a7d3f0"
0x180017014  call    cs:__imp__o__wcsicmp
0x18001701a  test    eax, eax
0x18001701c  jz      short loc_180017036
0x18001701e  mov     rdx, rdi
0x180017021  lea     rcx, a96c4f8f5B3da5e; "96c4f8f5-b3da-5efe-f12d-d1b6fcc52269"
0x180017028  call    cs:__imp__o__wcsicmp
0x18001702e  test    eax, eax
0x180017030  jnz     loc_180016FA0
0x180017036  mov     ebx, 1
0x18001703b  jmp     short loc_180017075
0x18001703d  test    ebx, ebx
0x18001703f  js      loc_180016FA0
0x180017045  mov     rax, [rsi]
0x180017048  mov     ebx, 1
0x18001704d  mov     rdx, [rsp+48h+hMem]
0x180017052  mov     r9d, ebx
0x180017055  mov     r8d, ebx
0x180017058  mov     dword ptr [rsp+48h+var_28], ebp
0x18001705c  mov     rcx, rsi
0x18001705f  mov     rax, [rax+30h]
0x180017063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017068  mov     ebx, eax
0x18001706a  test    eax, eax
0x18001706c  jns     short loc_180017075
0x18001706e  mov     ecx, eax
0x180017070  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017075  mov     ecx, ebx
0x180017077  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001707c  mov     rcx, [rsp+48h+hMem]; hMem
0x180017081  test    rcx, rcx
0x180017084  jz      short loc_18001708C
0x180017086  call    cs:__imp_LocalFree
0x18001708c  mov     eax, ebx
0x18001708e  mov     rbx, [rsp+48h+arg_0]
0x180017093  add     rsp, 30h
0x180017097  pop     rdi
0x180017098  pop     rsi
0x180017099  pop     rbp
0x18001709a  retn
```
