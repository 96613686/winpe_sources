# RaiseException(long)

- ea: `0x18001d2c8`
- end: `0x18001d3e4`
- name: `?RaiseException@@YAXJ@Z`
- size: `284`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b00`
- `0x180006d90`
- `0x180007940`
- `0x180007dc0`
- `0x180007fc0`

## callees

- `0x18001d2c8`
- `0x18001e010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001d333`
- `KERNEL32!FormatMessageW` at `0x18001d333`
- `KERNEL32!LocalFree` at `0x18001d3a9`
- `KERNEL32!LocalFree` at `0x18001d3a9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d301`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d39a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d301`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d39a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d341`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d341`

## string_xrefs

- `0x18001d363`: `Active Directory`

## pseudocode

```c
void __fastcall RaiseException(DWORD dwMessageId)
{
  ICreateErrorInfo *pperrinfo; // [rsp+58h] [rbp+18h] BYREF
  HLOCAL Buffer; // [rsp+60h] [rbp+20h] BYREF
  IErrorInfo *perrinfo; // [rsp+68h] [rbp+28h] BYREF

  Buffer = 0;
  pperrinfo = 0;
  perrinfo = 0;
  if ( g_hActiveDs )
  {
    SetErrorInfo(0, 0);
    if ( FormatMessageW(0x1B00u, g_hActiveDs, dwMessageId, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      if ( CreateErrorInfo(&pperrinfo) >= 0 )
      {
        ((void (__fastcall *)(ICreateErrorInfo *, HLOCAL))pperrinfo->lpVtbl->SetDescription)(pperrinfo, Buffer);
        ((void (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
          pperrinfo,
          L"Active Directory");
        if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
               pperrinfo,
               &IID_IErrorInfo,
               &perrinfo) >= 0 )
          SetErrorInfo(0, perrinfo);
      }
    }
    if ( Buffer )
      LocalFree(Buffer);
    if ( perrinfo )
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    if ( pperrinfo )
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x18001d2c8  mov     [rsp-8+arg_0], rbx
0x18001d2cd  push    rbp
0x18001d2ce  mov     rbp, rsp
0x18001d2d1  sub     rsp, 40h
0x18001d2d5  cmp     cs:?g_hActiveDs@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hActiveDs
0x18001d2dd  mov     ebx, ecx
0x18001d2df  mov     [rbp+Buffer], 0
0x18001d2e7  mov     [rbp+pperrinfo], 0
0x18001d2ef  mov     [rbp+perrinfo], 0
0x18001d2f7  jz      loc_18001D3D9
0x18001d2fd  xor     edx, edx; perrinfo
0x18001d2ff  xor     ecx, ecx; dwReserved
0x18001d301  call    cs:__imp_SetErrorInfo
0x18001d307  mov     rdx, cs:?g_hActiveDs@@3PEAUHINSTANCE__@@EA; lpSource
0x18001d30e  lea     rax, [rbp+Buffer]
0x18001d312  mov     [rsp+40h+Arguments], 0; Arguments
0x18001d31b  xor     r9d, r9d; dwLanguageId
0x18001d31e  mov     [rsp+40h+nSize], 0; nSize
0x18001d326  mov     r8d, ebx; dwMessageId
0x18001d329  mov     ecx, 1B00h; dwFlags
0x18001d32e  mov     [rsp+40h+lpBuffer], rax; lpBuffer
0x18001d333  call    cs:__imp_FormatMessageW
0x18001d339  test    eax, eax
0x18001d33b  jz      short loc_18001D3A0
0x18001d33d  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x18001d341  call    cs:__imp_CreateErrorInfo
0x18001d347  test    eax, eax
0x18001d349  js      short loc_18001D3A0
0x18001d34b  mov     rcx, [rbp+pperrinfo]
0x18001d34f  mov     rdx, [rbp+Buffer]
0x18001d353  mov     rax, [rcx]
0x18001d356  mov     rax, [rax+28h]
0x18001d35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d35f  mov     rcx, [rbp+pperrinfo]
0x18001d363  lea     rdx, aActiveDirector; "Active Directory"
0x18001d36a  mov     rax, [rcx]
0x18001d36d  mov     rax, [rax+20h]
0x18001d371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d376  mov     rcx, [rbp+pperrinfo]
0x18001d37a  lea     r8, [rbp+perrinfo]
0x18001d37e  lea     rdx, IID_IErrorInfo
0x18001d385  mov     rax, [rcx]
0x18001d388  mov     rax, [rax]
0x18001d38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d390  test    eax, eax
0x18001d392  js      short loc_18001D3A0
0x18001d394  mov     rdx, [rbp+perrinfo]; perrinfo
0x18001d398  xor     ecx, ecx; dwReserved
0x18001d39a  call    cs:__imp_SetErrorInfo
0x18001d3a0  mov     rcx, [rbp+Buffer]; hMem
0x18001d3a4  test    rcx, rcx
0x18001d3a7  jz      short loc_18001D3AF
0x18001d3a9  call    cs:__imp_LocalFree
0x18001d3af  mov     rcx, [rbp+perrinfo]
0x18001d3b3  test    rcx, rcx
0x18001d3b6  jz      short loc_18001D3C4
0x18001d3b8  mov     rax, [rcx]
0x18001d3bb  mov     rax, [rax+10h]
0x18001d3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c4  mov     rcx, [rbp+pperrinfo]
0x18001d3c8  test    rcx, rcx
0x18001d3cb  jz      short loc_18001D3D9
0x18001d3cd  mov     rax, [rcx]
0x18001d3d0  mov     rax, [rax+10h]
0x18001d3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d9  mov     rbx, [rsp+40h+arg_0]
0x18001d3de  add     rsp, 40h
0x18001d3e2  pop     rbp
0x18001d3e3  retn
```
