# AttachUserAadToken(IBackgroundCopyJob *,ushort const *)

- ea: `0x140009f78`
- end: `0x14000a02e`
- name: `?AttachUserAadToken@@YAJPEAUIBackgroundCopyJob@@PEBG@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x1400074d4`
- `0x14000904c`
- `0x140009f78`
- `0x14001c010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000a00b`
- `KERNEL32!LocalFree` at `0x14000a00b`
- `DMCmnUtils!BigStrcat` at `0x140009fdd`
- `DMCmnUtils!BigStrcat` at `0x140009fdd`

## string_xrefs

- `0x140009f9a`: `AttachUserAadToken - pszAadToken == NULL, nothing to do.`
- `0x140009fd1`: `MDMUserToken: `

## pseudocode

```c
__int64 __fastcall AttachUserAadToken(struct IBackgroundCopyJob *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rdi
  int v4; // ebx
  unsigned __int16 *v5; // rax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v3 = 0;
  if ( a2 )
  {
    v4 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_f1bd1079_9f01_4bdc_8036_f09b70095066,
           &v7);
    if ( v4 >= 0 )
    {
      v5 = BigStrcat(3u, L"MDMUserToken: ", a2, L"\n");
      v3 = v5;
      if ( v5 )
        v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v7 + 56LL))(v7, v5);
      else
        v4 = -2147024882;
    }
  }
  else
  {
    LogInfo(L"AttachUserAadToken - pszAadToken == NULL, nothing to do.");
    v4 = 0;
  }
  LocalFree(v3);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009f78  mov     [rsp+arg_0], rbx
0x140009f7d  mov     [rsp+arg_10], rsi
0x140009f82  push    rdi
0x140009f83  sub     rsp, 20h
0x140009f87  mov     rsi, rdx
0x140009f8a  mov     [rsp+28h+arg_8], 0
0x140009f93  xor     edi, edi
0x140009f95  test    rdx, rdx
0x140009f98  jnz     short loc_140009FAA
0x140009f9a  lea     rcx, aAttachuseraadt; "AttachUserAadToken - pszAadToken == NUL"...
0x140009fa1  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140009fa6  xor     ebx, ebx
0x140009fa8  jmp     short loc_14000A008
0x140009faa  mov     rax, [rcx]
0x140009fad  lea     r8, [rsp+28h+arg_8]
0x140009fb2  lea     rdx, _GUID_f1bd1079_9f01_4bdc_8036_f09b70095066
0x140009fb9  mov     rax, [rax]
0x140009fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fc1  mov     ebx, eax
0x140009fc3  test    eax, eax
0x140009fc5  js      short loc_14000A008
0x140009fc7  lea     r9, asc_140021A58; "\n"
0x140009fce  mov     r8, rsi
0x140009fd1  lea     rdx, aMdmusertoken; "MDMUserToken: "
0x140009fd8  mov     ecx, 3
0x140009fdd  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140009fe3  mov     rdi, rax
0x140009fe6  test    rax, rax
0x140009fe9  jnz     short loc_140009FF2
0x140009feb  mov     ebx, 8007000Eh
0x140009ff0  jmp     short loc_14000A008
0x140009ff2  mov     rcx, [rsp+28h+arg_8]
0x140009ff7  mov     rax, [rcx]
0x140009ffa  mov     rdx, rdi
0x140009ffd  mov     rax, [rax+38h]
0x14000a001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a006  mov     ebx, eax
0x14000a008  mov     rcx, rdi; hMem
0x14000a00b  call    cs:__imp_LocalFree
0x14000a011  nop
0x14000a012  lea     rcx, [rsp+28h+arg_8]
0x14000a017  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x14000a01c  mov     eax, ebx
0x14000a01e  mov     rbx, [rsp+28h+arg_0]
0x14000a023  mov     rsi, [rsp+28h+arg_10]
0x14000a028  add     rsp, 20h
0x14000a02c  pop     rdi
0x14000a02d  retn
```
