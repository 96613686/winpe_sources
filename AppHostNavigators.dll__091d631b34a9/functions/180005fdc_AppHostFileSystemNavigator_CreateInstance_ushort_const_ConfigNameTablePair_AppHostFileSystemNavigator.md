# AppHostFileSystemNavigator::CreateInstance(ushort const *,ConfigNameTablePair *,AppHostFileSystemNavigator * *)

- ea: `0x180005fdc`
- end: `0x180006120`
- name: `?CreateInstance@AppHostFileSystemNavigator@@SAJPEBGPEAVConfigNameTablePair@@PEAPEAV1@@Z`
- size: `324`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ConfigNameTablePair *, struct AppHostFileSystemNavigator **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c770`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180003a1c`
- `0x180005abc`
- `0x180005b24`
- `0x180005fdc`

## pseudocode

```c
__int64 __fastcall AppHostFileSystemNavigator::CreateInstance(
        const unsigned __int16 *a1,
        struct ConfigNameTablePair *a2,
        struct AppHostFileSystemNavigator **a3)
{
  FileSystemTree *v6; // rax
  FileSystemTree *v7; // rdi
  __int64 result; // rax
  _OWORD *v9; // rax
  AppHostFileSystemNavigator *v10; // rbx
  unsigned int v11; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v12[4]; // [rsp+28h] [rbp-20h] BYREF
  FileSystemTree *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  try
  {
    v6 = (FileSystemTree *)operator new(0x70u);
    v12[0] = v6;
    if ( v6 )
      v7 = FileSystemTree::FileSystemTree(v6, a1, a2);
    else
      v7 = 0;
    InvasivePtr<ConfigLocationsTree>::Reset(&v13);
    v13 = v7;
    if ( v7 )
    {
      v12[0] = 0;
      v9 = operator new(0x38u);
      if ( v9 )
      {
        *v9 = 0;
        v9[1] = 0;
        v9[2] = 0;
        *((_QWORD *)v9 + 6) = 0;
        v10 = AppHostFileSystemNavigator::AppHostFileSystemNavigator((AppHostFileSystemNavigator *)v9);
      }
      else
      {
        v10 = 0;
      }
      v12[0] = v10;
      if ( v10 )
      {
        *((_DWORD *)v10 + 8) = 0;
        if ( *((FileSystemTree **)v10 + 5) != v7 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
          InvasivePtr<ConfigLocationsTree>::Reset((char *)v10 + 40);
          *((_QWORD *)v10 + 5) = v7;
        }
        *((_QWORD *)v10 + 6) = (char *)v7 + 32;
        v12[0] = 0;
        *a3 = v10;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v12);
        InvasivePtr<ConfigLocationsTree>::Reset(&v13);
        result = 0;
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v12);
        InvasivePtr<ConfigLocationsTree>::Reset(&v13);
        result = 2147942414LL;
      }
    }
    else
    {
      InvasivePtr<ConfigLocationsTree>::Reset(&v13);
      result = 2147942414LL;
    }
  }
  catch ( long v11 )
  {
    return v11;
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
0x180005fdc  mov     [rsp+arg_0], rbx
0x180005fe1  mov     [rsp+arg_8], rsi
0x180005fe6  push    rdi
0x180005fe7  push    r14
0x180005fe9  push    r15
0x180005feb  sub     rsp, 30h
0x180005fef  mov     r15, r8
0x180005ff2  mov     rbx, rdx
0x180005ff5  mov     rdi, rcx
0x180005ff8  mov     [rsp+48h+arg_18], 0
0x180006001  mov     ecx, 70h ; 'p'; Size
0x180006006  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000600b  mov     [rsp+48h+var_20], rax
0x180006010  test    rax, rax
0x180006013  jz      short loc_180006028
0x180006015  mov     r8, rbx; struct ConfigNameTablePair *
0x180006018  mov     rdx, rdi; unsigned __int16 *
0x18000601b  mov     rcx, rax; this
0x18000601e  call    ??0FileSystemTree@@QEAA@PEBGPEAVConfigNameTablePair@@@Z; FileSystemTree::FileSystemTree(ushort const *,ConfigNameTablePair *)
0x180006023  mov     rdi, rax
0x180006026  jmp     short loc_18000602A
0x180006028  xor     edi, edi
0x18000602a  lea     rcx, [rsp+48h+arg_18]
0x18000602f  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006034  mov     [rsp+48h+arg_18], rdi
0x180006039  test    rdi, rdi
0x18000603c  jnz     short loc_180006052
0x18000603e  lea     rcx, [rsp+48h+arg_18]
0x180006043  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006048  mov     eax, 8007000Eh
0x18000604d  jmp     loc_18000610B
0x180006052  mov     [rsp+48h+var_20], 0
0x18000605b  mov     ecx, 38h ; '8'; Size
0x180006060  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006065  test    rax, rax
0x180006068  jz      short loc_18000608B
0x18000606a  xorps   xmm0, xmm0
0x18000606d  xor     ecx, ecx
0x18000606f  movups  xmmword ptr [rax], xmm0
0x180006072  movups  xmmword ptr [rax+10h], xmm0
0x180006076  movups  xmmword ptr [rax+20h], xmm0
0x18000607a  mov     [rax+30h], rcx
0x18000607e  mov     rcx, rax; this
0x180006081  call    ??0AppHostFileSystemNavigator@@QEAA@XZ; AppHostFileSystemNavigator::AppHostFileSystemNavigator(void)
0x180006086  mov     rbx, rax
0x180006089  jmp     short loc_18000608D
0x18000608b  xor     ebx, ebx
0x18000608d  mov     [rsp+48h+var_20], rbx
0x180006092  test    rbx, rbx
0x180006095  jnz     short loc_1800060B3
0x180006097  lea     rcx, [rsp+48h+var_20]
0x18000609c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800060a1  nop
0x1800060a2  lea     rcx, [rsp+48h+arg_18]
0x1800060a7  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800060ac  mov     eax, 8007000Eh
0x1800060b1  jmp     short loc_18000610B
0x1800060b3  lea     r14, [rdi+20h]
0x1800060b7  mov     dword ptr [rbx+20h], 0
0x1800060be  lea     rsi, [rbx+28h]
0x1800060c2  cmp     [rsi], rdi
0x1800060c5  jz      short loc_1800060D6
0x1800060c7  lock inc dword ptr [rdi+8]
0x1800060cb  mov     rcx, rsi
0x1800060ce  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800060d3  mov     [rsi], rdi
0x1800060d6  mov     [rbx+30h], r14
0x1800060da  mov     [rsp+48h+var_20], 0
0x1800060e3  mov     [r15], rbx
0x1800060e6  lea     rcx, [rsp+48h+var_20]
0x1800060eb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800060f0  nop
0x1800060f1  lea     rcx, [rsp+48h+arg_18]
0x1800060f6  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x1800060fb  nop
0x1800060fc  xor     eax, eax
0x1800060fe  jmp     short loc_18000610B
0x180006100  mov     eax, [rsp+48h+var_28]
0x180006104  jmp     short loc_18000610B
0x180006106  mov     eax, 8000FFFFh
0x18000610b  mov     rbx, [rsp+48h+arg_0]
0x180006110  mov     rsi, [rsp+48h+arg_8]
0x180006115  add     rsp, 30h
0x180006119  pop     r15
0x18000611b  pop     r14
0x18000611d  pop     rdi
0x18000611e  retn
```
