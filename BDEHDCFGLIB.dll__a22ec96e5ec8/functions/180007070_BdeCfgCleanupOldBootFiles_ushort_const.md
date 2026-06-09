# BdeCfgCleanupOldBootFiles(ushort const *)

- ea: `0x180007070`
- end: `0x180007160`
- name: `?BdeCfgCleanupOldBootFiles@@YAJPEBG@Z`
- size: `240`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800101a0`

## callees

- `0x180007070`
- `0x180008020`
- `0x1800080f0`
- `0x180008aac`
- `0x180008e1c`
- `0x1800093e0`

## string_xrefs

- `0x1800070a5`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall BdeCfgCleanupOldBootFiles(const unsigned __int16 *a1)
{
  WCHAR *v1; // rbx
  WCHAR *v2; // rsi
  unsigned int v4; // edi
  unsigned int v5; // ebp
  int v6; // eax
  int v7; // eax
  int v8; // eax
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR lpPathName; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  lpFileName = 0;
  lpPathName = 0;
  if ( a1 )
  {
    BdeCfgpAcquireNamedPrivilege(L"SeRestorePrivilege");
    v5 = 0;
    while ( 1 )
    {
      v6 = BdeCfgpBuildVolumePath(a1, (&off_180016160)[2 * v5], (unsigned __int16 **)&lpFileName);
      v1 = (WCHAR *)lpFileName;
      v4 = v6;
      if ( v6 < 0 )
        break;
      v7 = BdeCfgpDeleteFile(lpFileName);
      v4 = v7;
      if ( v7 < 0 && (v7 != -2147024894 || *((_BYTE *)&off_180016160 + 16 * v5 + 8)) )
        break;
      BdeCfgpFree(v1);
      v1 = 0;
      ++v5;
      lpFileName = 0;
      if ( v5 >= 3 )
      {
        v8 = BdeCfgpBuildVolumePath(a1, L"\\Boot", (unsigned __int16 **)&lpPathName);
        v2 = (WCHAR *)lpPathName;
        v4 = v8;
        if ( v8 >= 0 )
          v4 = BdeCfgpRecursiveDelete(lpPathName);
        break;
      }
    }
  }
  else
  {
    v4 = -2147467261;
  }
  BdeCfgpFree(v1);
  BdeCfgpFree(v2);
  return v4;
}

```

## disassembly

```asm
0x180007070  mov     rax, rsp
0x180007073  mov     [rax+18h], rbx
0x180007077  mov     [rax+20h], rbp
0x18000707b  push    rsi
0x18000707c  push    rdi
0x18000707d  push    r12
0x18000707f  push    r14
0x180007081  push    r15
0x180007083  sub     rsp, 20h
0x180007087  xor     ebx, ebx
0x180007089  xor     esi, esi
0x18000708b  mov     [rax+8], rbx
0x18000708f  mov     r14, rcx
0x180007092  mov     [rax+10h], rsi
0x180007096  test    rcx, rcx
0x180007099  jnz     short loc_1800070A5
0x18000709b  mov     edi, 80004003h
0x1800070a0  jmp     loc_180007137
0x1800070a5  lea     rcx, Name; "SeRestorePrivilege"
0x1800070ac  call    ?BdeCfgpAcquireNamedPrivilege@@YAJPEAG@Z; BdeCfgpAcquireNamedPrivilege(ushort *)
0x1800070b1  xor     ebp, ebp
0x1800070b3  lea     r12, off_180016160; "\\bootmgr"
0x1800070ba  mov     r15d, ebp
0x1800070bd  lea     r8, [rsp+48h+lpFileName]; unsigned __int16 **
0x1800070c2  add     r15, r15
0x1800070c5  mov     rcx, r14; unsigned __int16 *
0x1800070c8  mov     rdx, [r12+r15*8]; unsigned __int16 *
0x1800070cc  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x1800070d1  mov     rbx, [rsp+48h+lpFileName]
0x1800070d6  mov     edi, eax
0x1800070d8  test    eax, eax
0x1800070da  js      short loc_180007137
0x1800070dc  mov     rcx, rbx; lpFileName
0x1800070df  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x1800070e4  mov     edi, eax
0x1800070e6  test    eax, eax
0x1800070e8  jns     short loc_1800070F8
0x1800070ea  cmp     eax, 80070002h
0x1800070ef  jnz     short loc_180007137
0x1800070f1  cmp     [r12+r15*8+8], sil
0x1800070f6  jnz     short loc_180007137
0x1800070f8  mov     rcx, rbx; lpMem
0x1800070fb  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180007100  xor     ebx, ebx
0x180007102  inc     ebp
0x180007104  mov     [rsp+48h+lpFileName], rbx
0x180007109  cmp     ebp, 3
0x18000710c  jb      short loc_1800070BA
0x18000710e  lea     r8, [rsp+48h+lpPathName]; unsigned __int16 **
0x180007113  mov     rcx, r14; unsigned __int16 *
0x180007116  lea     rdx, aBoot; "\\Boot"
0x18000711d  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x180007122  mov     rsi, [rsp+48h+lpPathName]
0x180007127  mov     edi, eax
0x180007129  test    eax, eax
0x18000712b  js      short loc_180007137
0x18000712d  mov     rcx, rsi; lpPathName
0x180007130  call    ?BdeCfgpRecursiveDelete@@YAJPEAG@Z; BdeCfgpRecursiveDelete(ushort *)
0x180007135  mov     edi, eax
0x180007137  mov     rcx, rbx; lpMem
0x18000713a  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x18000713f  mov     rcx, rsi; lpMem
0x180007142  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180007147  mov     rbx, [rsp+48h+arg_10]
0x18000714c  mov     eax, edi
0x18000714e  mov     rbp, [rsp+48h+arg_18]
0x180007153  add     rsp, 20h
0x180007157  pop     r15
0x180007159  pop     r14
0x18000715b  pop     r12
0x18000715d  pop     rdi
0x18000715e  pop     rsi
0x18000715f  retn
```
