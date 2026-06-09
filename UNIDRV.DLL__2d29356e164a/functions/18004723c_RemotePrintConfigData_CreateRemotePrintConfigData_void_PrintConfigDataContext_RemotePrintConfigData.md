# RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)

- ea: `0x18004723c`
- end: `0x18004737e`
- name: `?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `322`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct RemotePrintConfigData **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800241ac`

## callees

- `0x18002d070`
- `0x18004723c`
- `0x180047790`
- `0x1800491e8`
- `0x180053f04`
- `0x180075010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180047363`
- `ADVAPI32!RegCloseKey` at `0x180047363`

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
  char *v10; // rbx
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
    v10 = (char *)operator new(0x88u, (const struct std::nothrow_t *)byte_18007F401);
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
      ParseDriverInfo(v12, (struct DriverInfoFiles *)(v10 + 24));
      V4ConnectionFileStruct = V4ConnectionFiles::CreateV4ConnectionFileStruct(
                                 v11,
                                 (struct V4ConnectionFiles **)v10 + 13);
      *((_DWORD *)v10 + 2) = V4ConnectionFileStruct;
      v9 = V4ConnectionFileStruct;
      *a3 = (struct RemotePrintConfigData *)v10;
      if ( V4ConnectionFileStruct < 0 )
      {
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 32LL))(v10, 1);
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
0x18004723c  mov     [rsp+arg_0], rbx
0x180047241  mov     [rsp+arg_8], rbp
0x180047246  push    rsi
0x180047247  push    rdi
0x180047248  push    r14
0x18004724a  sub     rsp, 30h
0x18004724e  mov     r14, r8
0x180047251  mov     rsi, rdx
0x180047254  mov     rbp, rcx
0x180047257  test    r8, r8
0x18004725a  jnz     short loc_180047266
0x18004725c  mov     eax, 80070057h
0x180047261  jmp     loc_18004736B
0x180047266  cmp     byte ptr [rdx+20h], 0
0x18004726a  lea     rcx, [rdx+18h]
0x18004726e  mov     qword ptr [r8], 0
0x180047275  mov     [rsp+48h+hKey], 0
0x18004727e  jnz     short loc_180047284
0x180047280  mov     rcx, [rdx+10h]
0x180047284  mov     rcx, [rcx]; pszSrc
0x180047287  lea     r9, [rsp+48h+hKey]; HKEY *
0x18004728c  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x180047291  mov     edi, eax
0x180047293  test    eax, eax
0x180047295  jns     short loc_1800472A5
0x180047297  mov     [rsp+48h+hKey], 0
0x1800472a0  jmp     loc_180047369
0x1800472a5  lea     rdx, byte_18007F401; struct std::nothrow_t *
0x1800472ac  mov     ecx, 88h; unsigned __int64
0x1800472b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800472b6  mov     rbx, rax
0x1800472b9  test    rax, rax
0x1800472bc  jz      loc_18004734D
0x1800472c2  mov     rdi, [rsp+48h+hKey]
0x1800472c7  lea     rax, ??_7RemotePrintConfigData@@6B@; const RemotePrintConfigData::`vftable'
0x1800472ce  mov     [rbx], rax
0x1800472d1  mov     dword ptr [rbx+8], 0
0x1800472d8  mov     rcx, [rsi+8]
0x1800472dc  test    rcx, rcx
0x1800472df  jnz     short loc_1800472E4
0x1800472e1  mov     rcx, [rsi]; struct _DRIVER_INFO_3W *
0x1800472e4  mov     qword ptr [rsi], 0
0x1800472eb  lea     rdx, [rbx+18h]; struct DriverInfoFiles *
0x1800472ef  mov     qword ptr [rsi+8], 0
0x1800472f7  mov     [rbx+10h], rcx
0x1800472fb  mov     [rbx+70h], rbp
0x1800472ff  mov     [rbx+78h], rdi
0x180047303  mov     qword ptr [rbx+80h], 0
0x18004730e  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x180047313  lea     rdx, [rbx+68h]; struct V4ConnectionFiles **
0x180047317  mov     rcx, rdi; hkey
0x18004731a  call    ?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z; V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)
0x18004731f  mov     [rbx+8], eax
0x180047322  mov     edi, eax
0x180047324  mov     [r14], rbx
0x180047327  test    eax, eax
0x180047329  jns     short loc_180047369
0x18004732b  test    rbx, rbx
0x18004732e  jz      short loc_180047344
0x180047330  mov     rax, [rbx]
0x180047333  mov     edx, 1
0x180047338  mov     rcx, rbx
0x18004733b  mov     rax, [rax+20h]
0x18004733f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047344  mov     qword ptr [r14], 0
0x18004734b  jmp     short loc_180047369
0x18004734d  mov     rcx, [rsp+48h+hKey]; hKey
0x180047352  mov     edi, 8007000Eh
0x180047357  mov     qword ptr [r14], 0
0x18004735e  test    rcx, rcx
0x180047361  jz      short loc_180047369
0x180047363  call    cs:__imp_RegCloseKey
0x180047369  mov     eax, edi
0x18004736b  mov     rbx, [rsp+48h+arg_0]
0x180047370  mov     rbp, [rsp+48h+arg_8]
0x180047375  add     rsp, 30h
0x180047379  pop     r14
0x18004737b  pop     rdi
0x18004737c  pop     rsi
0x18004737d  retn
```
