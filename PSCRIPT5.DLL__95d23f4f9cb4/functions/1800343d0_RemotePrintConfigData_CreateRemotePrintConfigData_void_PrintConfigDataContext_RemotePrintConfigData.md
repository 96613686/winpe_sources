# RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)

- ea: `0x1800343d0`
- end: `0x180034512`
- name: `?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `322`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct RemotePrintConfigData **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003431c`

## callees

- `0x18000298c`
- `0x1800343d0`
- `0x180034518`
- `0x180035afc`
- `0x180035d1c`
- `0x18005d010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800344f7`
- `ADVAPI32!RegCloseKey` at `0x1800344f7`

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
    v10 = operator new(0x88u, (const struct std::nothrow_t *)byte_18006C430);
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
      ParseDriverInfo(v12, (const wchar_t **)v10 + 3);
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
0x1800343d0  mov     [rsp+arg_0], rbx
0x1800343d5  mov     [rsp+arg_8], rbp
0x1800343da  push    rsi
0x1800343db  push    rdi
0x1800343dc  push    r14
0x1800343de  sub     rsp, 30h
0x1800343e2  mov     r14, r8
0x1800343e5  mov     rsi, rdx
0x1800343e8  mov     rbp, rcx
0x1800343eb  test    r8, r8
0x1800343ee  jnz     short loc_1800343FA
0x1800343f0  mov     eax, 80070057h
0x1800343f5  jmp     loc_1800344FF
0x1800343fa  cmp     byte ptr [rdx+20h], 0
0x1800343fe  lea     rcx, [rdx+18h]
0x180034402  mov     qword ptr [r8], 0
0x180034409  mov     [rsp+48h+hKey], 0
0x180034412  jnz     short loc_180034418
0x180034414  mov     rcx, [rdx+10h]
0x180034418  mov     rcx, [rcx]; pszSrc
0x18003441b  lea     r9, [rsp+48h+hKey]; HKEY *
0x180034420  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x180034425  mov     edi, eax
0x180034427  test    eax, eax
0x180034429  jns     short loc_180034439
0x18003442b  mov     [rsp+48h+hKey], 0
0x180034434  jmp     loc_1800344FD
0x180034439  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x180034440  mov     ecx, 88h; unsigned __int64
0x180034445  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003444a  mov     rbx, rax
0x18003444d  test    rax, rax
0x180034450  jz      loc_1800344E1
0x180034456  mov     rdi, [rsp+48h+hKey]
0x18003445b  lea     rax, ??_7RemotePrintConfigData@@6B@; const RemotePrintConfigData::`vftable'
0x180034462  mov     [rbx], rax
0x180034465  mov     dword ptr [rbx+8], 0
0x18003446c  mov     rcx, [rsi+8]
0x180034470  test    rcx, rcx
0x180034473  jnz     short loc_180034478
0x180034475  mov     rcx, [rsi]; struct _DRIVER_INFO_3W *
0x180034478  mov     qword ptr [rsi], 0
0x18003447f  lea     rdx, [rbx+18h]; struct DriverInfoFiles *
0x180034483  mov     qword ptr [rsi+8], 0
0x18003448b  mov     [rbx+10h], rcx
0x18003448f  mov     [rbx+70h], rbp
0x180034493  mov     [rbx+78h], rdi
0x180034497  mov     qword ptr [rbx+80h], 0
0x1800344a2  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x1800344a7  lea     rdx, [rbx+68h]; struct V4ConnectionFiles **
0x1800344ab  mov     rcx, rdi; hkey
0x1800344ae  call    ?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z; V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)
0x1800344b3  mov     [rbx+8], eax
0x1800344b6  mov     edi, eax
0x1800344b8  mov     [r14], rbx
0x1800344bb  test    eax, eax
0x1800344bd  jns     short loc_1800344FD
0x1800344bf  test    rbx, rbx
0x1800344c2  jz      short loc_1800344D8
0x1800344c4  mov     rax, [rbx]
0x1800344c7  mov     edx, 1
0x1800344cc  mov     rcx, rbx
0x1800344cf  mov     rax, [rax+20h]
0x1800344d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344d8  mov     qword ptr [r14], 0
0x1800344df  jmp     short loc_1800344FD
0x1800344e1  mov     rcx, [rsp+48h+hKey]; hKey
0x1800344e6  mov     edi, 8007000Eh
0x1800344eb  mov     qword ptr [r14], 0
0x1800344f2  test    rcx, rcx
0x1800344f5  jz      short loc_1800344FD
0x1800344f7  call    cs:__imp_RegCloseKey
0x1800344fd  mov     eax, edi
0x1800344ff  mov     rbx, [rsp+48h+arg_0]
0x180034504  mov     rbp, [rsp+48h+arg_8]
0x180034509  add     rsp, 30h
0x18003450d  pop     r14
0x18003450f  pop     rdi
0x180034510  pop     rsi
0x180034511  retn
```
