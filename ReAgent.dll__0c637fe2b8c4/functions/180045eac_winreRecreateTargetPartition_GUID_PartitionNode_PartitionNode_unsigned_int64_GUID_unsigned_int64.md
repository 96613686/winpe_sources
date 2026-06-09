# winreRecreateTargetPartition(_GUID *,PartitionNode *,PartitionNode *,unsigned __int64,_GUID *,unsigned __int64 *)

- ea: `0x180045eac`
- end: `0x180046028`
- name: `?winreRecreateTargetPartition@@YAHPEAU_GUID@@PEAUPartitionNode@@1_K0PEA_K@Z`
- size: `380`
- prototype: `int(struct _GUID *, struct PartitionNode *, struct PartitionNode *, unsigned __int64, struct _GUID *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180036c38`

## callees

- `0x1800059fc`
- `0x18003e28c`
- `0x18003e324`
- `0x180044670`
- `0x1800449cc`
- `0x180045eac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180046007`
- `KERNEL32!GetLastError` at `0x180046007`
- `ole32!CoUninitialize` at `0x180046001`
- `ole32!CoUninitialize` at `0x180046001`
- `ole32!CoInitialize` at `0x180045f02`
- `ole32!CoInitialize` at `0x180045f02`

## string_xrefs

- `0x180045ff0`: `winreRecreateTargetPartition Invalid arguments`
- `0x180045ee7`: `winreRecreateTargetPartition Recreate a new WinRE partition of size: %I64u `
- `0x180045f0f`: `winreRecreateTargetPartition CoInitialize failed. Error: 0x%X `
- `0x180045f24`: `winreRecreateTargetPartition Target Partition details: {NTFS: %d, Mbr: %d, Active: %d, Boot: %d, BitlockerEnabled: %d, PartitionNumber: %d}`
- `0x180045f77`: `winreRecreateTargetPartition The WinRE partition is not located after the OS partition`
- `0x180045f9f`: `winreRecreateTargetPartition winreDeletePartition failed.`
- `0x180045fe0`: `winreRecreateTargetPartition winreGetNewPartition failed.`

## pseudocode

```c
__int64 __fastcall winreRecreateTargetPartition(
        struct _GUID *a1,
        struct PartitionNode *a2,
        struct PartitionNode *a3,
        __int64 a4,
        struct _GUID *a5,
        unsigned __int64 *a6)
{
  unsigned int v6; // esi
  unsigned int v7; // ebp
  HRESULT v12; // eax
  DWORD LastError; // eax
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+28h] [rbp-50h]
  int v17; // [rsp+30h] [rbp-48h]
  int v18; // [rsp+38h] [rbp-40h]

  v6 = 0;
  v7 = 0;
  if ( a1 && a2 && a3 )
  {
    UnattendLogW(0, L"winreRecreateTargetPartition Recreate a new WinRE partition of size: %I64u ", a4);
    AsmReCreateWinRePartitionStart(a2, a4);
    v12 = CoInitialize(0);
    if ( v12 < 0 )
      UnattendLogW(2, L"winreRecreateTargetPartition CoInitialize failed. Error: 0x%X ", (unsigned int)v12);
    v18 = *((_DWORD *)a2 + 325);
    v17 = *((_DWORD *)a2 + 330);
    v16 = *((_DWORD *)a2 + 329);
    v15 = *((_DWORD *)a2 + 328);
    UnattendLogW(
      0,
      L"winreRecreateTargetPartition Target Partition details: {NTFS: %d, Mbr: %d, Active: %d, Boot: %d, BitlockerEnabled:"
       " %d, PartitionNumber: %d}",
      *((unsigned int *)a2 + 326),
      *((unsigned int *)a2 + 327),
      v15,
      v16,
      v17,
      v18);
    if ( *((_DWORD *)a2 + 325) == *((_DWORD *)a3 + 325) + 1 )
    {
      if ( (unsigned int)winreDeletePartition(*((_DWORD *)a2 + 324), *((_QWORD *)a2 + 158)) )
      {
        if ( (unsigned int)winreGetNewPartition(a1, a4 - *((_QWORD *)a2 + 161), a4, 0, a5, a6) )
          v6 = 1;
        else
          UnattendLogW(2, L"winreRecreateTargetPartition winreGetNewPartition failed.");
      }
      else
      {
        UnattendLogW(1, L"winreRecreateTargetPartition winreDeletePartition failed.");
      }
    }
    else
    {
      UnattendLogW(0, L"winreRecreateTargetPartition The WinRE partition is not located after the OS partition");
      v7 = 1;
    }
  }
  else
  {
    UnattendLogW(1, L"winreRecreateTargetPartition Invalid arguments");
  }
  CoUninitialize();
  LastError = GetLastError();
  AsmReCreateWinRePartitionEnd(v6, v7, LastError);
  return v6;
}

```

## disassembly

```asm
0x180045eac  push    rbx
0x180045eae  push    rbp
0x180045eaf  push    rsi
0x180045eb0  push    rdi
0x180045eb1  push    r14
0x180045eb3  push    r15
0x180045eb5  sub     rsp, 48h
0x180045eb9  xor     esi, esi
0x180045ebb  xor     ebp, ebp
0x180045ebd  mov     r14, r9
0x180045ec0  mov     rbx, r8
0x180045ec3  mov     rdi, rdx
0x180045ec6  mov     r15, rcx
0x180045ec9  test    rcx, rcx
0x180045ecc  jz      loc_180045FF0
0x180045ed2  test    rdx, rdx
0x180045ed5  jz      loc_180045FF0
0x180045edb  test    rbx, rbx
0x180045ede  jz      loc_180045FF0
0x180045ee4  mov     r8, r9
0x180045ee7  lea     rdx, aWinrerecreatet; "winreRecreateTargetPartition Recreate a"...
0x180045eee  xor     ecx, ecx
0x180045ef0  call    UnattendLogW
0x180045ef5  mov     rdx, r14; unsigned __int64
0x180045ef8  mov     rcx, rdi; struct PartitionNode *
0x180045efb  call    ?AsmReCreateWinRePartitionStart@@YAXPEAUPartitionNode@@_K@Z; AsmReCreateWinRePartitionStart(PartitionNode *,unsigned __int64)
0x180045f00  xor     ecx, ecx; pvReserved
0x180045f02  call    cs:__imp_CoInitialize
0x180045f08  test    eax, eax
0x180045f0a  jns     short loc_180045F1E
0x180045f0c  mov     r8d, eax
0x180045f0f  lea     rdx, aWinrerecreatet_1; "winreRecreateTargetPartition CoInitiali"...
0x180045f16  lea     ecx, [rsi+2]
0x180045f19  call    UnattendLogW
0x180045f1e  mov     eax, [rdi+514h]
0x180045f24  lea     rdx, aWinrerecreatet_0; "winreRecreateTargetPartition Target Par"...
0x180045f2b  mov     r9d, [rdi+51Ch]
0x180045f32  xor     ecx, ecx
0x180045f34  mov     r8d, [rdi+518h]
0x180045f3b  mov     [rsp+78h+var_40], eax
0x180045f3f  mov     eax, [rdi+528h]
0x180045f45  mov     [rsp+78h+var_48], eax
0x180045f49  mov     eax, [rdi+524h]
0x180045f4f  mov     dword ptr [rsp+78h+var_50], eax
0x180045f53  mov     eax, [rdi+520h]
0x180045f59  mov     dword ptr [rsp+78h+var_58], eax
0x180045f5d  call    UnattendLogW
0x180045f62  mov     eax, [rbx+514h]
0x180045f68  mov     ebx, 1
0x180045f6d  add     eax, ebx
0x180045f6f  cmp     [rdi+514h], eax
0x180045f75  jz      short loc_180045F89
0x180045f77  lea     rdx, aWinrerecreatet_4; "winreRecreateTargetPartition The WinRE "...
0x180045f7e  xor     ecx, ecx
0x180045f80  call    UnattendLogW
0x180045f85  mov     ebp, ebx
0x180045f87  jmp     short loc_180046001
0x180045f89  mov     rdx, [rdi+4F0h]; unsigned __int64
0x180045f90  mov     ecx, [rdi+510h]; int
0x180045f96  call    ?winreDeletePartition@@YAHH_K@Z; winreDeletePartition(int,unsigned __int64)
0x180045f9b  test    eax, eax
0x180045f9d  jnz     short loc_180045FAA
0x180045f9f  lea     rdx, aWinrerecreatet_2; "winreRecreateTargetPartition winreDelet"...
0x180045fa6  mov     ecx, ebx
0x180045fa8  jmp     short loc_180045FFC
0x180045faa  mov     rax, [rsp+78h+arg_28]
0x180045fb2  mov     rdx, r14
0x180045fb5  sub     rdx, [rdi+508h]
0x180045fbc  xor     r9d, r9d
0x180045fbf  mov     [rsp+78h+var_50], rax
0x180045fc4  mov     r8, r14
0x180045fc7  mov     rax, [rsp+78h+arg_20]
0x180045fcf  mov     rcx, r15
0x180045fd2  mov     [rsp+78h+var_58], rax
0x180045fd7  call    ?winreGetNewPartition@@YAHPEBU_GUID@@_K1W4_WINRE_PARTITION_LOCATION@@PEAU1@PEA_K@Z; winreGetNewPartition(_GUID const *,unsigned __int64,unsigned __int64,_WINRE_PARTITION_LOCATION,_GUID *,unsigned __int64 *)
0x180045fdc  test    eax, eax
0x180045fde  jnz     short loc_180045FEC
0x180045fe0  lea     rdx, aWinrerecreatet_5; "winreRecreateTargetPartition winreGetNe"...
0x180045fe7  lea     ecx, [rax+2]
0x180045fea  jmp     short loc_180045FFC
0x180045fec  mov     esi, ebx
0x180045fee  jmp     short loc_180046001
0x180045ff0  lea     rdx, aWinrerecreatet_3; "winreRecreateTargetPartition Invalid ar"...
0x180045ff7  mov     ecx, 1
0x180045ffc  call    UnattendLogW
0x180046001  call    cs:__imp_CoUninitialize
0x180046007  call    cs:__imp_GetLastError
0x18004600d  mov     edx, ebp; int
0x18004600f  mov     ecx, esi; int
0x180046011  mov     r8d, eax; unsigned int
0x180046014  call    ?AsmReCreateWinRePartitionEnd@@YAXHHK@Z; AsmReCreateWinRePartitionEnd(int,int,ulong)
0x180046019  mov     eax, esi
0x18004601b  add     rsp, 48h
0x18004601f  pop     r15
0x180046021  pop     r14
0x180046023  pop     rdi
0x180046024  pop     rsi
0x180046025  pop     rbp
0x180046026  pop     rbx
0x180046027  retn
```
