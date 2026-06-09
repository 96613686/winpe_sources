# winreSetRecoveryBCDEntry(void *,PartitionNode *,_GUID *)

- ea: `0x1800342f4`
- end: `0x18003458a`
- name: `?winreSetRecoveryBCDEntry@@YAKPEAXPEAUPartitionNode@@PEAU_GUID@@@Z`
- size: `662`
- prototype: `unsigned int __fastcall(void *, struct PartitionNode *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800356d4`

## callees

- `0x1800059fc`
- `0x1800342f4`
- `0x180034c8c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180034372`
- `ntdll!RtlNtStatusToDosError` at `0x18003450f`
- `ntdll!RtlNtStatusToDosError` at `0x180034372`
- `ntdll!RtlNtStatusToDosError` at `0x18003450f`
- `KERNEL32!HeapFree` at `0x180034525`
- `KERNEL32!HeapFree` at `0x180034525`
- `KERNEL32!HeapAlloc` at `0x18003440d`
- `KERNEL32!HeapAlloc` at `0x18003440d`
- `KERNEL32!GetProcessHeap` at `0x1800343ff`
- `KERNEL32!GetProcessHeap` at `0x180034517`
- `KERNEL32!GetProcessHeap` at `0x1800343ff`
- `KERNEL32!GetProcessHeap` at `0x180034517`
- `bcd!BcdSetElementData` at `0x1800344d1`
- `bcd!BcdSetElementData` at `0x1800344ed`
- `bcd!BcdSetElementData` at `0x1800344d1`
- `bcd!BcdSetElementData` at `0x1800344ed`
- `bcd!BcdCloseStore` at `0x180034562`
- `bcd!BcdCloseStore` at `0x180034562`
- `bcd!BcdCloseObject` at `0x180034534`
- `bcd!BcdCloseObject` at `0x18003454b`
- `bcd!BcdCloseObject` at `0x180034534`
- `bcd!BcdCloseObject` at `0x18003454b`
- `bcd!BcdGetElementData` at `0x1800343d7`
- `bcd!BcdGetElementData` at `0x180034443`
- `bcd!BcdGetElementData` at `0x1800343d7`
- `bcd!BcdGetElementData` at `0x180034443`
- `bcd!BcdOpenObject` at `0x1800343a1`
- `bcd!BcdOpenObject` at `0x1800344a6`
- `bcd!BcdOpenObject` at `0x1800343a1`
- `bcd!BcdOpenObject` at `0x1800344a6`
- `bcd!BcdOpenStore` at `0x180034350`
- `bcd!BcdOpenStore` at `0x180034350`

## string_xrefs

- `0x18003435f`: `Failed to open system store: 0x%x`
- `0x1800343ad`: `Failed to open target OS entry: 0x%x`
- `0x1800343f3`: `Failed to read locale size from parent OS: 0x%x`
- `0x180034452`: `Failed to read locale from parent OS: 0x%x`

## pseudocode

```c
__int64 __fastcall winreSetRecoveryBCDEntry(void *a1, struct PartitionNode *a2, struct _GUID *a3)
{
  int v6; // eax
  NTSTATUS v7; // edi
  NTSTATUS v8; // ecx
  ULONG v9; // ebx
  GUID v10; // xmm0
  int ElementData; // ebx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  void *v15; // rsi
  int v16; // eax
  NTSTATUS v17; // ebx
  NTSTATUS v18; // ecx
  ULONG v19; // eax
  int v20; // edi
  HANDLE v21; // rax
  __int64 v23; // [rsp+20h] [rbp-50h] BYREF
  __int64 v24; // [rsp+28h] [rbp-48h] BYREF
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  SIZE_T dwBytes; // [rsp+38h] [rbp-38h] BYREF
  GUID v27; // [rsp+40h] [rbp-30h] BYREF
  __int128 v28; // [rsp+50h] [rbp-20h] BYREF

  v25 = 0;
  v24 = 0;
  LODWORD(dwBytes) = 0;
  v23 = 0;
  v27 = 0;
  v28 = 0;
  v6 = BcdOpenStore(0, 0, &v25);
  v7 = v6;
  if ( v6 < 0 )
  {
    UnattendLogW(1, L"Failed to open system store: 0x%x", (unsigned int)v6);
    v8 = v7;
LABEL_3:
    v9 = RtlNtStatusToDosError(v8);
    goto LABEL_27;
  }
  if ( a3 )
    v10 = *a3;
  else
    v10 = GUID_CURRENT_BOOT_ENTRY;
  v27 = v10;
  ElementData = BcdOpenObject(v25, &v27, &v24);
  if ( ElementData < 0 )
  {
    UnattendLogW(1, L"Failed to open target OS entry: 0x%x", (unsigned int)ElementData);
LABEL_9:
    v8 = ElementData;
    goto LABEL_3;
  }
  ElementData = BcdGetElementData(v24, 301989893, 0, &dwBytes);
  if ( (int)(ElementData + 0x80000000) >= 0 && ElementData != -1073741789 )
  {
    UnattendLogW(1, L"Failed to read locale size from parent OS: 0x%x", (unsigned int)ElementData);
    goto LABEL_9;
  }
  v12 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 0, v12);
  v15 = v14;
  if ( !v14 )
  {
    UnattendLogW(1, L"Failed to allocate Locale buffer of %u bytes", (unsigned int)dwBytes);
    v9 = 14;
    goto LABEL_27;
  }
  v16 = BcdGetElementData(v24, 301989893, v14, &dwBytes);
  v17 = v16;
  if ( v16 < 0 )
  {
    UnattendLogW(1, L"Failed to read locale from parent OS: 0x%x", (unsigned int)v16);
    v18 = v17;
LABEL_25:
    v9 = RtlNtStatusToDosError(v18);
    goto LABEL_26;
  }
  v19 = winreCreateRecoveryEntryInBCDEx(a1, a2, (__int64)v15, &v28);
  v9 = v19;
  if ( !v19 )
  {
    v20 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v23);
    if ( v20 >= 0 )
    {
      v20 = BcdSetElementData(v23, 587202563, &v28, 16);
      if ( v20 >= 0 )
      {
        v20 = BcdSetElementData(v23, 603979777, &v28, 16);
        if ( v20 >= 0 )
          goto LABEL_26;
      }
      UnattendLogW(1, L"Failed to set default object in recovery BCD: 0x%x", (unsigned int)v20);
    }
    else
    {
      UnattendLogW(1, L"Failed to get bootmgr entry from recovery BCD: 0x%x", (unsigned int)v20);
    }
    v18 = v20;
    goto LABEL_25;
  }
  UnattendLogW(1, L"Failed to add entry for WinRE in recovery BCD: 0x%x", v19);
LABEL_26:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v15);
LABEL_27:
  if ( v23 )
  {
    BcdCloseObject();
    v23 = 0;
  }
  if ( v24 )
  {
    BcdCloseObject();
    v24 = 0;
  }
  if ( v25 )
    BcdCloseStore();
  return v9;
}

```

## disassembly

```asm
0x1800342f4  mov     [rsp-28h+arg_18], rbx
0x1800342f9  push    rbp
0x1800342fa  push    rsi
0x1800342fb  push    rdi
0x1800342fc  push    r14
0x1800342fe  push    r15
0x180034300  mov     rbp, rsp
0x180034303  sub     rsp, 70h
0x180034307  mov     rax, cs:__security_cookie
0x18003430e  xor     rax, rsp
0x180034311  mov     [rbp+var_10], rax
0x180034315  xorps   xmm0, xmm0
0x180034318  mov     [rbp+var_40], 0
0x180034320  mov     rbx, r8
0x180034323  mov     [rbp+var_48], 0
0x18003432b  mov     r15, rdx
0x18003432e  mov     dword ptr [rbp+dwBytes], 0
0x180034335  mov     r14, rcx
0x180034338  mov     [rbp+var_50], 0
0x180034340  lea     r8, [rbp+var_40]
0x180034344  xor     edx, edx
0x180034346  xor     ecx, ecx
0x180034348  movups  [rbp+var_30], xmm0
0x18003434c  movups  [rbp+var_20], xmm0
0x180034350  call    cs:__imp_BcdOpenStore
0x180034356  mov     edi, eax
0x180034358  test    eax, eax
0x18003435a  jns     short loc_18003437F
0x18003435c  mov     r8d, eax
0x18003435f  lea     rdx, aFailedToOpenSy_2; "Failed to open system store: 0x%x"
0x180034366  mov     ecx, 1
0x18003436b  call    UnattendLogW
0x180034370  mov     ecx, edi; Status
0x180034372  call    cs:__imp_RtlNtStatusToDosError
0x180034378  mov     ebx, eax
0x18003437a  jmp     loc_18003452B
0x18003437f  test    rbx, rbx
0x180034382  jz      short loc_180034389
0x180034384  movups  xmm0, xmmword ptr [rbx]
0x180034387  jmp     short loc_180034390
0x180034389  movups  xmm0, xmmword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x180034390  mov     rcx, [rbp+var_40]
0x180034394  lea     r8, [rbp+var_48]
0x180034398  lea     rdx, [rbp+var_30]
0x18003439c  movdqu  [rbp+var_30], xmm0
0x1800343a1  call    cs:__imp_BcdOpenObject
0x1800343a7  mov     ebx, eax
0x1800343a9  test    eax, eax
0x1800343ab  jns     short loc_1800343C5
0x1800343ad  lea     rdx, aFailedToOpenTa; "Failed to open target OS entry: 0x%x"
0x1800343b4  mov     r8d, ebx
0x1800343b7  mov     ecx, 1
0x1800343bc  call    UnattendLogW
0x1800343c1  mov     ecx, ebx
0x1800343c3  jmp     short loc_180034372
0x1800343c5  mov     rcx, [rbp+var_48]
0x1800343c9  lea     r9, [rbp+dwBytes]
0x1800343cd  mov     edi, 12000005h
0x1800343d2  xor     r8d, r8d
0x1800343d5  mov     edx, edi
0x1800343d7  call    cs:__imp_BcdGetElementData
0x1800343dd  mov     ebx, eax
0x1800343df  mov     eax, 80000000h
0x1800343e4  lea     ecx, [rbx+rax]
0x1800343e7  test    eax, ecx
0x1800343e9  jnz     short loc_1800343FC
0x1800343eb  cmp     ebx, 0C0000023h
0x1800343f1  jz      short loc_1800343FC
0x1800343f3  lea     rdx, aFailedToReadLo_0; "Failed to read locale size from parent "...
0x1800343fa  jmp     short loc_1800343B4
0x1800343fc  mov     ebx, dword ptr [rbp+dwBytes]
0x1800343ff  call    cs:__imp_GetProcessHeap
0x180034405  mov     r8d, ebx; dwBytes
0x180034408  xor     edx, edx; dwFlags
0x18003440a  mov     rcx, rax; hHeap
0x18003440d  call    cs:__imp_HeapAlloc
0x180034413  mov     rsi, rax
0x180034416  test    rax, rax
0x180034419  jnz     short loc_180034436
0x18003441b  mov     r8d, dword ptr [rbp+dwBytes]
0x18003441f  lea     rdx, aFailedToAlloca_0; "Failed to allocate Locale buffer of %u "...
0x180034426  lea     ecx, [rax+1]
0x180034429  call    UnattendLogW
0x18003442e  lea     ebx, [rsi+0Eh]
0x180034431  jmp     loc_18003452B
0x180034436  mov     rcx, [rbp+var_48]
0x18003443a  lea     r9, [rbp+dwBytes]
0x18003443e  mov     r8, rsi
0x180034441  mov     edx, edi
0x180034443  call    cs:__imp_BcdGetElementData
0x180034449  mov     ebx, eax
0x18003444b  test    eax, eax
0x18003444d  jns     short loc_18003446A
0x18003444f  mov     r8d, eax
0x180034452  lea     rdx, aFailedToReadLo; "Failed to read locale from parent OS: 0"...
0x180034459  mov     ecx, 1
0x18003445e  call    UnattendLogW
0x180034463  mov     ecx, ebx
0x180034465  jmp     loc_18003450F
0x18003446a  lea     r9, [rbp+var_20]
0x18003446e  mov     r8, rsi
0x180034471  mov     rdx, r15; struct PartitionNode *
0x180034474  mov     rcx, r14; void *
0x180034477  call    winreCreateRecoveryEntryInBCDEx
0x18003447c  mov     ebx, eax
0x18003447e  test    eax, eax
0x180034480  jz      short loc_180034498
0x180034482  mov     r8d, eax
0x180034485  lea     rdx, aFailedToAddEnt; "Failed to add entry for WinRE in recove"...
0x18003448c  mov     ecx, 1
0x180034491  call    UnattendLogW
0x180034496  jmp     short loc_180034517
0x180034498  lea     r8, [rbp+var_50]
0x18003449c  mov     rcx, r14
0x18003449f  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800344a6  call    cs:__imp_BcdOpenObject
0x1800344ac  mov     edi, eax
0x1800344ae  test    eax, eax
0x1800344b0  jns     short loc_1800344BB
0x1800344b2  lea     rdx, aFailedToGetBoo; "Failed to get bootmgr entry from recove"...
0x1800344b9  jmp     short loc_180034500
0x1800344bb  mov     rcx, [rbp+var_50]
0x1800344bf  lea     r8, [rbp+var_20]
0x1800344c3  mov     r14d, 10h
0x1800344c9  mov     edx, 23000003h
0x1800344ce  mov     r9d, r14d
0x1800344d1  call    cs:__imp_BcdSetElementData
0x1800344d7  mov     edi, eax
0x1800344d9  test    eax, eax
0x1800344db  js      short loc_1800344F9
0x1800344dd  mov     rcx, [rbp+var_50]
0x1800344e1  lea     r8, [rbp+var_20]
0x1800344e5  mov     r9d, r14d
0x1800344e8  mov     edx, 24000001h
0x1800344ed  call    cs:__imp_BcdSetElementData
0x1800344f3  mov     edi, eax
0x1800344f5  test    eax, eax
0x1800344f7  jns     short loc_180034517
0x1800344f9  lea     rdx, aFailedToSetDef; "Failed to set default object in recover"...
0x180034500  mov     r8d, edi
0x180034503  mov     ecx, 1
0x180034508  call    UnattendLogW
0x18003450d  mov     ecx, edi; Status
0x18003450f  call    cs:__imp_RtlNtStatusToDosError
0x180034515  mov     ebx, eax
0x180034517  call    cs:__imp_GetProcessHeap
0x18003451d  mov     r8, rsi; lpMem
0x180034520  xor     edx, edx; dwFlags
0x180034522  mov     rcx, rax; hHeap
0x180034525  call    cs:__imp_HeapFree
0x18003452b  mov     rcx, [rbp+var_50]
0x18003452f  test    rcx, rcx
0x180034532  jz      short loc_180034542
0x180034534  call    cs:__imp_BcdCloseObject
0x18003453a  mov     [rbp+var_50], 0
0x180034542  mov     rcx, [rbp+var_48]
0x180034546  test    rcx, rcx
0x180034549  jz      short loc_180034559
0x18003454b  call    cs:__imp_BcdCloseObject
0x180034551  mov     [rbp+var_48], 0
0x180034559  mov     rcx, [rbp+var_40]
0x18003455d  test    rcx, rcx
0x180034560  jz      short loc_180034568
0x180034562  call    cs:__imp_BcdCloseStore
0x180034568  mov     eax, ebx
0x18003456a  mov     rcx, [rbp+var_10]
0x18003456e  xor     rcx, rsp; StackCookie
0x180034571  call    __security_check_cookie
0x180034576  mov     rbx, [rsp+70h+arg_18]
0x18003457e  add     rsp, 70h
0x180034582  pop     r15
0x180034584  pop     r14
0x180034586  pop     rdi
0x180034587  pop     rsi
0x180034588  pop     rbp
0x180034589  retn
```
