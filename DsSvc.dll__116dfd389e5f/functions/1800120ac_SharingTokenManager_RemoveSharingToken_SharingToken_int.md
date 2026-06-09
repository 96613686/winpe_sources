# SharingTokenManager::RemoveSharingToken(SharingToken *,int)

- ea: `0x1800120ac`
- end: `0x180012134`
- name: `?RemoveSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@H@Z`
- size: `136`
- prototype: `__int64 __fastcall(SharingTokenManager *__hidden this, struct SharingToken *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d7b8`
- `0x18001213c`
- `0x180012194`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x1800120ac`
- `0x18001669c`

## string_xrefs

- `0x1800120e0`: `RemoveSharingToken: Ignoring DS_E_TOKEN_NOT_FOUND`
- `0x1800120ee`: `SharingTokenManager::RemoveSharingToken`
- `0x180012118`: `SharingTokenManager::RemoveSharingToken`

## pseudocode

```c
__int64 __fastcall SharingTokenManager::RemoveSharingToken(SharingTokenManager *this, struct SharingToken *a2, int a3)
{
  unsigned int v4; // ebx
  int v5; // eax
  int *v6; // rax
  int *v7; // rax

  if ( !*(_DWORD *)this )
  {
    v4 = -1055719422;
LABEL_7:
    v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)this);
    DSLogger::LogError((DSLogger *)v7, L"SharingTokenManager::RemoveSharingToken", 134, L"hr=0x%x.", v4);
    return v4;
  }
  v5 = SharingTokenDatabase::DeleteToken((SharingTokenManager *)((char *)this + 8), a2);
  v4 = v5;
  if ( v5 == -1055719418 )
  {
    if ( a3 )
      goto LABEL_7;
    v6 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)this);
    DSLogger::LogError(
      (DSLogger *)v6,
      L"SharingTokenManager::RemoveSharingToken",
      124,
      L"RemoveSharingToken: Ignoring DS_E_TOKEN_NOT_FOUND");
    return 0;
  }
  else if ( v5 < 0 )
  {
    goto LABEL_7;
  }
  return v4;
}

```

## disassembly

```asm
0x1800120ac  mov     [rsp+arg_0], rbx
0x1800120b1  push    rdi
0x1800120b2  sub     rsp, 30h
0x1800120b6  cmp     dword ptr [rcx], 0
0x1800120b9  mov     edi, r8d
0x1800120bc  jnz     short loc_1800120C5
0x1800120be  mov     ebx, 0C1130002h
0x1800120c3  jmp     short loc_180012102
0x1800120c5  add     rcx, 8; this
0x1800120c9  call    ?DeleteToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@@Z; SharingTokenDatabase::DeleteToken(SharingToken *)
0x1800120ce  mov     ebx, eax
0x1800120d0  cmp     eax, 0C1130006h
0x1800120d5  jnz     short loc_1800120FE
0x1800120d7  test    edi, edi
0x1800120d9  jnz     short loc_180012102
0x1800120db  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800120e0  lea     r9, aRemovesharingt; "RemoveSharingToken: Ignoring DS_E_TOKEN"...
0x1800120e7  mov     rcx, rax; this
0x1800120ea  lea     r8d, [rdi+7Ch]; unsigned int
0x1800120ee  lea     rdx, aSharingtokenma_4; "SharingTokenManager::RemoveSharingToken"
0x1800120f5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800120fa  xor     ebx, ebx
0x1800120fc  jmp     short loc_180012127
0x1800120fe  test    eax, eax
0x180012100  jns     short loc_180012127
0x180012102  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012107  lea     r9, aHr0xX; "hr=0x%x."
0x18001210e  mov     [rsp+38h+var_18], ebx
0x180012112  mov     r8d, 86h; unsigned int
0x180012118  lea     rdx, aSharingtokenma_4; "SharingTokenManager::RemoveSharingToken"
0x18001211f  mov     rcx, rax; this
0x180012122  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012127  mov     eax, ebx
0x180012129  mov     rbx, [rsp+38h+arg_0]
0x18001212e  add     rsp, 30h
0x180012132  pop     rdi
0x180012133  retn
```
