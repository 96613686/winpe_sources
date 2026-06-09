# RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)

- ea: `0x18004866c`
- end: `0x1800487b5`
- name: `?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z`
- size: `329`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, struct RemotePrintConfigData **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800246f0`

## callees

- `0x18002d8f0`
- `0x18004866c`
- `0x180048c38`
- `0x18004a728`
- `0x1800559c4`
- `0x180077010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180048793`
- `ADVAPI32!RegCloseKey` at `0x180048793`

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
    v10 = operator new(0x88u, (const struct std::nothrow_t *)byte_180081401);
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
      ParseDriverInfo(v12, (const unsigned __int16 **)v10 + 3);
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
0x18004866c  mov     [rsp+arg_0], rbx
0x180048671  mov     [rsp+arg_8], rbp
0x180048676  push    rsi
0x180048677  push    rdi
0x180048678  push    r14
0x18004867a  sub     rsp, 30h
0x18004867e  mov     r14, r8
0x180048681  mov     rsi, rdx
0x180048684  mov     rbp, rcx
0x180048687  test    r8, r8
0x18004868a  jnz     short loc_180048696
0x18004868c  mov     eax, 80070057h
0x180048691  jmp     loc_1800487A1
0x180048696  cmp     byte ptr [rdx+20h], 0
0x18004869a  lea     rcx, [rdx+18h]
0x18004869e  mov     qword ptr [r8], 0
0x1800486a5  mov     [rsp+48h+hKey], 0
0x1800486ae  jnz     short loc_1800486B4
0x1800486b0  mov     rcx, [rdx+10h]
0x1800486b4  mov     rcx, [rcx]; pszSrc
0x1800486b7  lea     r9, [rsp+48h+hKey]; HKEY *
0x1800486bc  call    ?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z; OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)
0x1800486c1  mov     edi, eax
0x1800486c3  test    eax, eax
0x1800486c5  jns     short loc_1800486D5
0x1800486c7  mov     [rsp+48h+hKey], 0
0x1800486d0  jmp     loc_18004879F
0x1800486d5  lea     rdx, byte_180081401; struct std::nothrow_t *
0x1800486dc  mov     ecx, 88h; unsigned __int64
0x1800486e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800486e6  mov     rbx, rax
0x1800486e9  test    rax, rax
0x1800486ec  jz      loc_18004877D
0x1800486f2  mov     rdi, [rsp+48h+hKey]
0x1800486f7  lea     rax, ??_7RemotePrintConfigData@@6B@; const RemotePrintConfigData::`vftable'
0x1800486fe  mov     [rbx], rax
0x180048701  mov     dword ptr [rbx+8], 0
0x180048708  mov     rcx, [rsi+8]
0x18004870c  test    rcx, rcx
0x18004870f  jnz     short loc_180048714
0x180048711  mov     rcx, [rsi]; struct _DRIVER_INFO_3W *
0x180048714  mov     qword ptr [rsi], 0
0x18004871b  lea     rdx, [rbx+18h]; struct DriverInfoFiles *
0x18004871f  mov     qword ptr [rsi+8], 0
0x180048727  mov     [rbx+10h], rcx
0x18004872b  mov     [rbx+70h], rbp
0x18004872f  mov     [rbx+78h], rdi
0x180048733  mov     qword ptr [rbx+80h], 0
0x18004873e  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x180048743  lea     rdx, [rbx+68h]; struct V4ConnectionFiles **
0x180048747  mov     rcx, rdi; hkey
0x18004874a  call    ?CreateV4ConnectionFileStruct@V4ConnectionFiles@@SAJPEAUHKEY__@@PEAPEAU1@@Z; V4ConnectionFiles::CreateV4ConnectionFileStruct(HKEY__ *,V4ConnectionFiles * *)
0x18004874f  mov     [rbx+8], eax
0x180048752  mov     edi, eax
0x180048754  mov     [r14], rbx
0x180048757  test    eax, eax
0x180048759  jns     short loc_18004879F
0x18004875b  test    rbx, rbx
0x18004875e  jz      short loc_180048774
0x180048760  mov     rax, [rbx]
0x180048763  mov     edx, 1
0x180048768  mov     rcx, rbx
0x18004876b  mov     rax, [rax+20h]
0x18004876f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048774  mov     qword ptr [r14], 0
0x18004877b  jmp     short loc_18004879F
0x18004877d  mov     rcx, [rsp+48h+hKey]; hKey
0x180048782  mov     edi, 8007000Eh
0x180048787  mov     qword ptr [r14], 0
0x18004878e  test    rcx, rcx
0x180048791  jz      short loc_18004879F
0x180048793  call    cs:__imp_RegCloseKey
0x18004879a  nop     dword ptr [rax+rax+00h]
0x18004879f  mov     eax, edi
0x1800487a1  mov     rbx, [rsp+48h+arg_0]
0x1800487a6  mov     rbp, [rsp+48h+arg_8]
0x1800487ab  add     rsp, 30h
0x1800487af  pop     r14
0x1800487b1  pop     rdi
0x1800487b2  pop     rsi
0x1800487b3  retn
```
