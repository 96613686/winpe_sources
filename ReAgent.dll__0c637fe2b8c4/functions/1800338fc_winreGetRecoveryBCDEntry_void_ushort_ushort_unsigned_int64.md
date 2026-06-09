# winreGetRecoveryBCDEntry(void *,ushort *,ushort *,unsigned __int64)

- ea: `0x1800338fc`
- end: `0x180033a8a`
- name: `?winreGetRecoveryBCDEntry@@YAKPEAXPEAG1_K@Z`
- size: `398`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800361ac`

## callees

- `0x1800059fc`
- `0x1800338fc`
- `0x180033a90`
- `0x18005ced6`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180033971`
- `ntdll!RtlNtStatusToDosError` at `0x180033971`
- `bcd!BcdCloseObject` at `0x180033a54`
- `bcd!BcdCloseObject` at `0x180033a6b`
- `bcd!BcdCloseObject` at `0x180033a54`
- `bcd!BcdCloseObject` at `0x180033a6b`
- `bcd!BcdGetElementData` at `0x180033994`
- `bcd!BcdGetElementData` at `0x1800339ca`
- `bcd!BcdGetElementData` at `0x180033994`
- `bcd!BcdGetElementData` at `0x1800339ca`
- `bcd!BcdOpenObject` at `0x18003394f`
- `bcd!BcdOpenObject` at `0x180033a0a`
- `bcd!BcdOpenObject` at `0x18003394f`
- `bcd!BcdOpenObject` at `0x180033a0a`

## string_xrefs

- `0x18003395b`: `Failed to open bootmgr in Recovery BCD: 0x%x`
- `0x180033a16`: `Couldn't open WinRE BCD object: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetRecoveryBCDEntry(void *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  NTSTATUS v6; // ebx
  ULONG WimPathFromBCDEntry; // eax
  int ElementData; // eax
  unsigned __int64 v9; // r9
  unsigned int v10; // ebx
  void *v12; // [rsp+20h] [rbp-30h] BYREF
  __int64 v13; // [rsp+28h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+30h] [rbp-20h] BYREF
  int Buf1; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+3Ch] [rbp-14h]
  int v17; // [rsp+44h] [rbp-Ch]

  v13 = 0;
  v16 = 0;
  v17 = 0;
  v12 = 0;
  v14 = 0;
  Buf1 = 0;
  v6 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v13);
  if ( v6 < 0 )
  {
    UnattendLogW(1, L"Failed to open bootmgr in Recovery BCD: 0x%x", (unsigned int)v6);
    goto LABEL_3;
  }
  v14 = 16;
  ElementData = BcdGetElementData(v13, 587202563, &Buf1, &v14);
  if ( ElementData < 0 )
  {
    UnattendLogW(
      2,
      L"Couldn't get default boot object (0x%x), will query display order instead",
      (unsigned int)ElementData);
    v14 = 16;
    v6 = BcdGetElementData(v13, 603979777, &Buf1, &v14);
    if ( v6 < 0 )
    {
      UnattendLogW(1, L" Failed to get top of the display order: 0x%x", (unsigned int)v6);
      goto LABEL_3;
    }
  }
  if ( v14 >= 0x10 && memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    v6 = BcdOpenObject(a1, &Buf1, &v12);
    if ( v6 >= 0 )
    {
      WimPathFromBCDEntry = winreGetWimPathFromBCDEntry(v12, a2, a3, v9);
      goto LABEL_12;
    }
    UnattendLogW(1, L"Couldn't open WinRE BCD object: 0x%x", (unsigned int)v6);
LABEL_3:
    WimPathFromBCDEntry = RtlNtStatusToDosError(v6);
LABEL_12:
    v10 = WimPathFromBCDEntry;
    goto LABEL_14;
  }
  UnattendLogW(1, L" The default entry is NULL or missing");
  v10 = 1168;
LABEL_14:
  if ( v12 )
  {
    BcdCloseObject();
    v12 = 0;
  }
  if ( v13 )
    BcdCloseObject();
  return v10;
}

```

## disassembly

```asm
0x1800338fc  push    rbp
0x1800338fe  push    rbx
0x1800338ff  push    rsi
0x180033900  push    rdi
0x180033901  push    r14
0x180033903  mov     rbp, rsp
0x180033906  sub     rsp, 50h
0x18003390a  mov     rax, cs:__security_cookie
0x180033911  xor     rax, rsp
0x180033914  mov     [rbp+var_8], rax
0x180033918  xor     eax, eax
0x18003391a  mov     [rbp+var_28], 0
0x180033922  mov     r14, r8
0x180033925  mov     [rbp+var_14], rax
0x180033929  mov     rsi, rdx
0x18003392c  mov     [rbp+var_C], eax
0x18003392f  lea     r8, [rbp+var_28]
0x180033933  mov     [rbp+var_30], rax
0x180033937  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18003393e  mov     [rbp+var_20], 0
0x180033945  mov     rdi, rcx
0x180033948  mov     [rbp+Buf1], 0
0x18003394f  call    cs:__imp_BcdOpenObject
0x180033955  mov     ebx, eax
0x180033957  test    eax, eax
0x180033959  jns     short loc_18003397C
0x18003395b  lea     rdx, aFailedToOpenBo; "Failed to open bootmgr in Recovery BCD:"...
0x180033962  mov     r8d, ebx
0x180033965  mov     ecx, 1
0x18003396a  call    UnattendLogW
0x18003396f  mov     ecx, ebx; Status
0x180033971  call    cs:__imp_RtlNtStatusToDosError
0x180033977  jmp     loc_180033A31
0x18003397c  mov     rcx, [rbp+var_28]
0x180033980  lea     r9, [rbp+var_20]
0x180033984  lea     r8, [rbp+Buf1]
0x180033988  mov     [rbp+var_20], 10h
0x18003398f  mov     edx, 23000003h
0x180033994  call    cs:__imp_BcdGetElementData
0x18003399a  test    eax, eax
0x18003399c  jns     short loc_1800339DF
0x18003399e  mov     r8d, eax
0x1800339a1  lea     rdx, aCouldnTGetDefa; "Couldn't get default boot object (0x%x)"...
0x1800339a8  mov     ecx, 2
0x1800339ad  call    UnattendLogW
0x1800339b2  mov     rcx, [rbp+var_28]
0x1800339b6  lea     r9, [rbp+var_20]
0x1800339ba  lea     r8, [rbp+Buf1]
0x1800339be  mov     [rbp+var_20], 10h
0x1800339c5  mov     edx, 24000001h
0x1800339ca  call    cs:__imp_BcdGetElementData
0x1800339d0  mov     ebx, eax
0x1800339d2  test    eax, eax
0x1800339d4  jns     short loc_1800339DF
0x1800339d6  lea     rdx, aFailedToGetTop; " Failed to get top of the display order"...
0x1800339dd  jmp     short loc_180033962
0x1800339df  cmp     [rbp+var_20], 10h
0x1800339e3  jb      short loc_180033A35
0x1800339e5  mov     r8d, 10h; Size
0x1800339eb  lea     rdx, GUID_NULL; Buf2
0x1800339f2  lea     rcx, [rbp+Buf1]; Buf1
0x1800339f6  call    memcmp_0
0x1800339fb  test    eax, eax
0x1800339fd  jz      short loc_180033A35
0x1800339ff  lea     r8, [rbp+var_30]
0x180033a03  mov     rcx, rdi
0x180033a06  lea     rdx, [rbp+Buf1]
0x180033a0a  call    cs:__imp_BcdOpenObject
0x180033a10  mov     ebx, eax
0x180033a12  test    eax, eax
0x180033a14  jns     short loc_180033A22
0x180033a16  lea     rdx, aCouldnTOpenWin; "Couldn't open WinRE BCD object: 0x%x"
0x180033a1d  jmp     loc_180033962
0x180033a22  mov     rcx, [rbp+var_30]; void *
0x180033a26  mov     r8, r14; unsigned __int16 *
0x180033a29  mov     rdx, rsi; unsigned __int16 *
0x180033a2c  call    ?winreGetWimPathFromBCDEntry@@YAKPEAXPEAG1_K@Z; winreGetWimPathFromBCDEntry(void *,ushort *,ushort *,unsigned __int64)
0x180033a31  mov     ebx, eax
0x180033a33  jmp     short loc_180033A4B
0x180033a35  lea     rdx, aTheDefaultEntr; " The default entry is NULL or missing"
0x180033a3c  mov     ecx, 1
0x180033a41  call    UnattendLogW
0x180033a46  mov     ebx, 490h
0x180033a4b  mov     rcx, [rbp+var_30]
0x180033a4f  test    rcx, rcx
0x180033a52  jz      short loc_180033A62
0x180033a54  call    cs:__imp_BcdCloseObject
0x180033a5a  mov     [rbp+var_30], 0
0x180033a62  mov     rcx, [rbp+var_28]
0x180033a66  test    rcx, rcx
0x180033a69  jz      short loc_180033A71
0x180033a6b  call    cs:__imp_BcdCloseObject
0x180033a71  mov     eax, ebx
0x180033a73  mov     rcx, [rbp+var_8]
0x180033a77  xor     rcx, rsp; StackCookie
0x180033a7a  call    __security_check_cookie
0x180033a7f  add     rsp, 50h
0x180033a83  pop     r14
0x180033a85  pop     rdi
0x180033a86  pop     rsi
0x180033a87  pop     rbx
0x180033a88  pop     rbp
0x180033a89  retn
```
