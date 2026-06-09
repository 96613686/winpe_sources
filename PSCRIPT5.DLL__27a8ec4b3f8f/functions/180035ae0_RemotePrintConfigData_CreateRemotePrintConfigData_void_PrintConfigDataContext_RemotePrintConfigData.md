# RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)

- ea: `0x180035ae0`
- end: `0x180035c29`
- name: `?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `329`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct RemotePrintConfigData **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180035a2c`

## callees

- `0x1800029ec`
- `0x180035ae0`
- `0x180035c30`
- `0x1800372bc`
- `0x180037500`
- `0x18005f010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180035c07`
- `ADVAPI32!RegCloseKey` at `0x180035c07`

## pseudocode

```c
__int64 __fastcall RemotePrintConfigData::CreateRemotePrintConfigData(
        void *a1,
        struct PrintConfigDataContext *a2,
        struct RemotePrintConfigData **a3)
{
  bool v7; // zf
  STRSAFE_LPCWSTR *v8; // rcx
  int v9; // edi
  void *v10; // rbx
  HKEY v11; // rdi
  struct _DRIVER_INFO_3W *v12; // rcx
  int V4ConnectionFileStruct; // eax
  HKEY v14; // rcx
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v7 = *((_BYTE *)a2 + 32) == 0;
  v8 = (STRSAFE_LPCWSTR *)((char *)a2 + 24);
  *a3 = 0;
  hKey = 0;
  if ( v7 )
    v8 = (STRSAFE_LPCWSTR *)*((_QWORD *)a2 + 2);
  v9 = OpenConnectionRegistryKey(*v8, (__int64)a2, (__int64)a3, &hKey);
  if ( v9 >= 0 )
  {
    v10 = operator new(0x88u, (const struct std::nothrow_t *)byte_18006E400);
    if ( v10 )
    {
      v11 = hKey;
      *(_QWORD *)v10 = &RemotePrintConfigData::`vftable';
      *((_DWORD *)v10 + 2) = 0;
      v12 = (struct _DRIVER_INFO_3W *)*((_QWORD *)a2 + 1);
      if ( !v12 )
        v12 = *(struct _DRIVER_INFO_3W **)a2;
      *(_QWORD *)a2 = 0;
      *((_QWORD *)a2 + 1) = 0;
      *((_QWORD *)v10 + 2) = v12;
      *((_QWORD *)v10 + 14) = a1;
      *((_QWORD *)v10 + 15) = v11;
      *((_QWORD *)v10 + 16) = 0;
      ParseDriverInfo(v12, (LPWSTR *)v10 + 3);
      V4ConnectionFileStruct = V4ConnectionFiles::CreateV4ConnectionFileStruct(
                                 v11,
                                 (struct V4ConnectionFiles **)v10 + 13);
      *((_DWORD *)v10 + 2) = V4ConnectionFileStruct;
      v9 = V4ConnectionFileStruct;
      *a3 = (struct RemotePrintConfigData *)v10;
      if ( V4ConnectionFileStruct < 0 )
      {
        (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v10 + 32LL))(v10, 1);
        *a3 = 0;
      }
    }
    else
    {
      v14 = hKey;
      v9 = -2147024882;
      *a3 = 0;
      if ( v14 )
        RegCloseKey(v14);
    }
  }
  else
  {
    hKey = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035ae0  mov     [rsp+arg_0], rbx
0x180035ae5  mov     [rsp+arg_8], rbp
0x180035aea  push    rsi
0x180035aeb  push    rdi
0x180035aec  push    r14
0x180035aee  sub     rsp, 30h
0x180035af2  mov     r14, r8
0x180035af5  mov     rsi, rdx
0x180035af8  mov     rbp, rcx
0x180035afb  test    r8, r8
0x180035afe  jnz     short loc_180035B0A
0x180035b00  mov     eax, 80070057h
0x180035b05  jmp     loc_180035C15
0x180035b0a  cmp     byte ptr [rdx+20h], 0
0x180035b0e  lea     rcx, [rdx+18h]
0x180035b12  mov     qword ptr [r8], 0
0x180035b19  mov     [rsp+48h+hKey], 0
0x180035b22  jnz     short loc_180035B28
0x180035b24  mov     rcx, [rdx+10h]
0x180035b28  mov     rcx, [rcx]; pszSrc
0x180035b2b  lea     r9, [rsp+48h+hKey]; HKEY *
0x180035b30  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x180035b35  mov     edi, eax
0x180035b37  test    eax, eax
0x180035b39  jns     short loc_180035B49
0x180035b3b  mov     [rsp+48h+hKey], 0
0x180035b44  jmp     loc_180035C13
0x180035b49  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x180035b50  mov     ecx, 88h; unsigned __int64
0x180035b55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035b5a  mov     rbx, rax
0x180035b5d  test    rax, rax
0x180035b60  jz      loc_180035BF1
0x180035b66  mov     rdi, [rsp+48h+hKey]
0x180035b6b  lea     rax, ??_7RemotePrintConfigData@@6B@; const RemotePrintConfigData::`vftable'
0x180035b72  mov     [rbx], rax
0x180035b75  mov     dword ptr [rbx+8], 0
0x180035b7c  mov     rcx, [rsi+8]
0x180035b80  test    rcx, rcx
0x180035b83  jnz     short loc_180035B88
0x180035b85  mov     rcx, [rsi]; struct _DRIVER_INFO_3W *
0x180035b88  mov     qword ptr [rsi], 0
0x180035b8f  lea     rdx, [rbx+18h]; struct DriverInfoFiles *
0x180035b93  mov     qword ptr [rsi+8], 0
0x180035b9b  mov     [rbx+10h], rcx
0x180035b9f  mov     [rbx+70h], rbp
0x180035ba3  mov     [rbx+78h], rdi
0x180035ba7  mov     qword ptr [rbx+80h], 0
0x180035bb2  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x180035bb7  lea     rdx, [rbx+68h]; struct V4ConnectionFiles **
0x180035bbb  mov     rcx, rdi; hkey
0x180035bbe  call    ?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z; V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)
0x180035bc3  mov     [rbx+8], eax
0x180035bc6  mov     edi, eax
0x180035bc8  mov     [r14], rbx
0x180035bcb  test    eax, eax
0x180035bcd  jns     short loc_180035C13
0x180035bcf  test    rbx, rbx
0x180035bd2  jz      short loc_180035BE8
0x180035bd4  mov     rax, [rbx]
0x180035bd7  mov     edx, 1
0x180035bdc  mov     rcx, rbx
0x180035bdf  mov     rax, [rax+20h]
0x180035be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035be8  mov     qword ptr [r14], 0
0x180035bef  jmp     short loc_180035C13
0x180035bf1  mov     rcx, [rsp+48h+hKey]; hKey
0x180035bf6  mov     edi, 8007000Eh
0x180035bfb  mov     qword ptr [r14], 0
0x180035c02  test    rcx, rcx
0x180035c05  jz      short loc_180035C13
0x180035c07  call    cs:__imp_RegCloseKey
0x180035c0e  nop     dword ptr [rax+rax+00h]
0x180035c13  mov     eax, edi
0x180035c15  mov     rbx, [rsp+48h+arg_0]
0x180035c1a  mov     rbp, [rsp+48h+arg_8]
0x180035c1f  add     rsp, 30h
0x180035c23  pop     r14
0x180035c25  pop     rdi
0x180035c26  pop     rsi
0x180035c27  retn
```
