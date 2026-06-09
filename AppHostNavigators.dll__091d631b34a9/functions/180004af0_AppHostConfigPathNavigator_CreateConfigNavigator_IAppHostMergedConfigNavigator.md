# AppHostConfigPathNavigator::CreateConfigNavigator(IAppHostMergedConfigNavigator * *)

- ea: `0x180004af0`
- end: `0x180004b86`
- name: `?CreateConfigNavigator@AppHostConfigPathNavigator@@UEAAJPEAPEAUIAppHostMergedConfigNavigator@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(AppHostConfigPathNavigator *__hidden this, struct IAppHostMergedConfigNavigator **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x180004af0`
- `0x180006cf4`

## pseudocode

```c
__int64 __fastcall AppHostConfigPathNavigator::CreateConfigNavigator(
        AppHostConfigPathNavigator *this,
        struct IAppHostMergedConfigNavigator **a2)
{
  int v4; // ebx
  struct AppHostMergedConfigNavigator *v5; // rax
  struct AppHostMergedConfigNavigator *v6; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v6 = 0;
  v4 = AppHostMergedConfigNavigator::CreateInstance(
         *(struct ConfigSystemContext **)(*((_QWORD *)this + 5) + 160LL),
         *(struct ConfigNameTablePair **)(*((_QWORD *)this + 5) + 16LL),
         this,
         &v6);
  if ( v4 >= 0 )
  {
    v5 = v6;
    v6 = 0;
    *a2 = (struct IAppHostMergedConfigNavigator *)(((unsigned __int64)v5 + 8) & -(__int64)(v5 != 0));
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
    return 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180004af0  mov     [rsp+arg_0], rbx
0x180004af5  push    rdi
0x180004af6  sub     rsp, 30h
0x180004afa  mov     rdi, rdx
0x180004afd  mov     r8, rcx; struct AppHostConfigPathNavigator *
0x180004b00  test    rdx, rdx
0x180004b03  jnz     short loc_180004B0C
0x180004b05  mov     eax, 80070057h
0x180004b0a  jmp     short loc_180004B7A
0x180004b0c  mov     [rsp+38h+arg_8], 0
0x180004b15  mov     rcx, [rcx+28h]
0x180004b19  lea     r9, [rsp+38h+arg_8]; struct AppHostMergedConfigNavigator **
0x180004b1e  mov     rdx, [rcx+10h]; struct ConfigNameTablePair *
0x180004b22  mov     rcx, [rcx+0A0h]; struct ConfigSystemContext *
0x180004b29  call    ?CreateInstance@AppHostMergedConfigNavigator@@SAJPEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@PEAPEAV1@@Z; AppHostMergedConfigNavigator::CreateInstance(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *,AppHostMergedConfigNavigator * *)
0x180004b2e  mov     ebx, eax
0x180004b30  test    eax, eax
0x180004b32  jns     short loc_180004B42
0x180004b34  lea     rcx, [rsp+38h+arg_8]
0x180004b39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b3e  mov     eax, ebx
0x180004b40  jmp     short loc_180004B7A
0x180004b42  mov     rax, [rsp+38h+arg_8]
0x180004b47  mov     [rsp+38h+arg_8], 0
0x180004b50  lea     rcx, [rax+8]
0x180004b54  neg     rax
0x180004b57  sbb     rax, rax
0x180004b5a  and     rax, rcx
0x180004b5d  mov     [rdi], rax
0x180004b60  lea     rcx, [rsp+38h+arg_8]
0x180004b65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b6a  nop
0x180004b6b  xor     eax, eax
0x180004b6d  jmp     short loc_180004B7A
0x180004b6f  mov     eax, [rsp+38h+var_18]
0x180004b73  jmp     short loc_180004B7A
0x180004b75  mov     eax, 8000FFFFh
0x180004b7a  mov     rbx, [rsp+38h+arg_0]
0x180004b7f  add     rsp, 30h
0x180004b83  pop     rdi
0x180004b84  retn
```
