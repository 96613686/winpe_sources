# AppHostConfigPathNavigator::CreateConfigLocationNavigator(IAppHostConfigLocationsNavigator * *)

- ea: `0x180004a50`
- end: `0x180004ae6`
- name: `?CreateConfigLocationNavigator@AppHostConfigPathNavigator@@UEAAJPEAPEAUIAppHostConfigLocationsNavigator@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(AppHostConfigPathNavigator *__hidden this, struct IAppHostConfigLocationsNavigator **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x18000280c`
- `0x180004a50`

## pseudocode

```c
__int64 __fastcall AppHostConfigPathNavigator::CreateConfigLocationNavigator(
        AppHostConfigPathNavigator *this,
        struct IAppHostConfigLocationsNavigator **a2)
{
  __int64 result; // rax
  __int64 v5; // rcx
  struct ConfigNameTablePair *v6; // rdx
  struct ConfigSystemContext *v7; // rcx
  int v8; // ebx
  struct AppHostConfigLocationsNavigator *v9; // rax
  unsigned int v10; // [rsp+20h] [rbp-18h] BYREF
  struct AppHostConfigLocationsNavigator *v11; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v11 = 0;
  v5 = *((_QWORD *)this + 5);
  v6 = *(struct ConfigNameTablePair **)(v5 + 16);
  v7 = *(struct ConfigSystemContext **)(v5 + 160);
  try
  {
    v8 = AppHostConfigLocationsNavigator::CreateInstance(v7, v6, this, &v11);
    if ( v8 >= 0 )
    {
      v9 = v11;
      v11 = 0;
      *a2 = (struct IAppHostConfigLocationsNavigator *)(((unsigned __int64)v9 + 8) & -(__int64)(v9 != 0));
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
      result = 0;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
      result = (unsigned int)v8;
    }
  }
  catch ( long v10 )
  {
    return v10;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004a50  mov     [rsp+arg_0], rbx
0x180004a55  push    rdi
0x180004a56  sub     rsp, 30h
0x180004a5a  mov     rdi, rdx
0x180004a5d  mov     r8, rcx; struct AppHostConfigPathNavigator *
0x180004a60  test    rdx, rdx
0x180004a63  jnz     short loc_180004A6C
0x180004a65  mov     eax, 80070057h
0x180004a6a  jmp     short loc_180004ADA
0x180004a6c  mov     [rsp+38h+arg_8], 0
0x180004a75  mov     rcx, [rcx+28h]
0x180004a79  lea     r9, [rsp+38h+arg_8]; struct AppHostConfigLocationsNavigator **
0x180004a7e  mov     rdx, [rcx+10h]; struct ConfigNameTablePair *
0x180004a82  mov     rcx, [rcx+0A0h]; struct ConfigSystemContext *
0x180004a89  call    ?CreateInstance@AppHostConfigLocationsNavigator@@SAJPEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@PEAPEAV1@@Z; AppHostConfigLocationsNavigator::CreateInstance(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *,AppHostConfigLocationsNavigator * *)
0x180004a8e  mov     ebx, eax
0x180004a90  test    eax, eax
0x180004a92  jns     short loc_180004AA2
0x180004a94  lea     rcx, [rsp+38h+arg_8]
0x180004a99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a9e  mov     eax, ebx
0x180004aa0  jmp     short loc_180004ADA
0x180004aa2  mov     rax, [rsp+38h+arg_8]
0x180004aa7  mov     [rsp+38h+arg_8], 0
0x180004ab0  lea     rcx, [rax+8]
0x180004ab4  neg     rax
0x180004ab7  sbb     rax, rax
0x180004aba  and     rax, rcx
0x180004abd  mov     [rdi], rax
0x180004ac0  lea     rcx, [rsp+38h+arg_8]
0x180004ac5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004aca  nop
0x180004acb  xor     eax, eax
0x180004acd  jmp     short loc_180004ADA
0x180004acf  mov     eax, [rsp+38h+var_18]
0x180004ad3  jmp     short loc_180004ADA
0x180004ad5  mov     eax, 8000FFFFh
0x180004ada  mov     rbx, [rsp+38h+arg_0]
0x180004adf  add     rsp, 30h
0x180004ae3  pop     rdi
0x180004ae4  retn
```
