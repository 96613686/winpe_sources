# CSupportErrorInfo::SetErrorInfo(ushort const *,_GUID const &,bool)

- ea: `0x18001ee64`
- end: `0x18001ef44`
- name: `?SetErrorInfo@CSupportErrorInfo@@IEAAJPEBGAEBU_GUID@@_N@Z`
- size: `224`
- prototype: `__int64 __fastcall(CSupportErrorInfo *__hidden this, const unsigned __int16 *, const struct _GUID *, bool)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001980`
- `0x18001e270`
- `0x18001f530`
- `0x18002fcbd`
- `0x18002fd07`
- `0x180031a64`
- `0x180031a93`
- `0x180031c4d`
- `0x180031c94`

## callees

- `0x18000e490`
- `0x18001ee64`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ef05`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ef05`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001ee96`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001ee96`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSupportErrorInfo::SetErrorInfo(
        CSupportErrorInfo *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  HRESULT v5; // ebx
  IErrorInfo *perrinfo[2]; // [rsp+20h] [rbp-10h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp+10h] BYREF

  perrinfo[1] = (IErrorInfo *)-2LL;
  pperrinfo = 0;
  v5 = CreateErrorInfo(&pperrinfo);
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a3);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
             pperrinfo,
             a2);
      if ( v5 >= 0 )
      {
        perrinfo[0] = 0;
        v5 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
               pperrinfo,
               &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
               perrinfo);
        if ( v5 >= 0 )
        {
          v5 = SetErrorInfo(0, perrinfo[0]);
          if ( v5 >= 0 )
            v5 = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(perrinfo);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pperrinfo);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ee64  mov     rax, rsp
0x18001ee67  mov     [rax+8], rcx
0x18001ee6b  push    rbp
0x18001ee6c  mov     rbp, rsp
0x18001ee6f  sub     rsp, 30h
0x18001ee73  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18001ee7b  mov     [rax+10h], rbx
0x18001ee7f  mov     [rax+18h], rsi
0x18001ee83  mov     [rax+20h], rdi
0x18001ee87  mov     rdi, r8
0x18001ee8a  mov     rsi, rdx
0x18001ee8d  and     [rbp+pperrinfo], 0
0x18001ee92  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x18001ee96  call    cs:__imp_CreateErrorInfo
0x18001ee9d  nop     dword ptr [rax+rax+00h]
0x18001eea2  mov     ebx, eax
0x18001eea4  test    eax, eax
0x18001eea6  js      short loc_18001EF23
0x18001eea8  mov     rcx, [rbp+pperrinfo]
0x18001eeac  mov     rax, [rcx]
0x18001eeaf  mov     rdx, rdi
0x18001eeb2  mov     rax, [rax+18h]
0x18001eeb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebb  mov     ebx, eax
0x18001eebd  test    eax, eax
0x18001eebf  js      short loc_18001EF23
0x18001eec1  mov     rcx, [rbp+pperrinfo]
0x18001eec5  mov     rax, [rcx]
0x18001eec8  mov     rdx, rsi
0x18001eecb  mov     rax, [rax+28h]
0x18001eecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eed4  mov     ebx, eax
0x18001eed6  test    eax, eax
0x18001eed8  js      short loc_18001EF23
0x18001eeda  and     [rbp+perrinfo], 0
0x18001eedf  mov     rcx, [rbp+pperrinfo]
0x18001eee3  mov     rax, [rcx]
0x18001eee6  lea     r8, [rbp+perrinfo]
0x18001eeea  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x18001eef1  mov     rax, [rax]
0x18001eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eef9  mov     ebx, eax
0x18001eefb  test    eax, eax
0x18001eefd  js      short loc_18001EF19
0x18001eeff  mov     rdx, [rbp+perrinfo]; perrinfo
0x18001ef03  xor     ecx, ecx; dwReserved
0x18001ef05  call    cs:__imp_SetErrorInfo
0x18001ef0c  nop     dword ptr [rax+rax+00h]
0x18001ef11  mov     ebx, eax
0x18001ef13  test    eax, eax
0x18001ef15  js      short loc_18001EF19
0x18001ef17  xor     ebx, ebx
0x18001ef19  lea     rcx, [rbp+perrinfo]
0x18001ef1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ef22  nop
0x18001ef23  lea     rcx, [rbp+pperrinfo]
0x18001ef27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ef2c  mov     eax, ebx
0x18001ef2e  mov     rbx, [rsp+30h+arg_8]
0x18001ef33  mov     rsi, [rsp+30h+arg_10]
0x18001ef38  mov     rdi, [rsp+30h+arg_18]
0x18001ef3d  add     rsp, 30h
0x18001ef41  pop     rbp
0x18001ef42  retn
```
