# winreCountOsLoaderEntries

- ea: `0x18003479c`
- end: `0x180034a9c`
- name: `winreCountOsLoaderEntries`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024ff0`

## callees

- `0x1800059fc`
- `0x180030f18`
- `0x18003479c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180034a6b`
- `ntdll!RtlNtStatusToDosError` at `0x180034a6b`
- `KERNEL32!HeapFree` at `0x180034a3e`
- `KERNEL32!HeapFree` at `0x180034a3e`
- `KERNEL32!HeapAlloc` at `0x1800348a4`
- `KERNEL32!HeapAlloc` at `0x1800348a4`
- `KERNEL32!GetProcessHeap` at `0x180034893`
- `KERNEL32!GetProcessHeap` at `0x180034a30`
- `KERNEL32!GetProcessHeap` at `0x180034893`
- `KERNEL32!GetProcessHeap` at `0x180034a30`
- `bcd!BcdEnumerateObjects` at `0x180034869`
- `bcd!BcdEnumerateObjects` at `0x1800348e6`
- `bcd!BcdEnumerateObjects` at `0x180034869`
- `bcd!BcdEnumerateObjects` at `0x1800348e6`
- `bcd!BcdCloseStore` at `0x180034a4d`
- `bcd!BcdCloseStore` at `0x180034a4d`
- `bcd!BcdCloseObject` at `0x180034914`
- `bcd!BcdCloseObject` at `0x180034a1d`
- `bcd!BcdCloseObject` at `0x180034914`
- `bcd!BcdCloseObject` at `0x180034a1d`
- `bcd!BcdGetElementData` at `0x18003496f`
- `bcd!BcdGetElementData` at `0x1800349a3`
- `bcd!BcdGetElementData` at `0x1800349d1`
- `bcd!BcdGetElementData` at `0x18003496f`
- `bcd!BcdGetElementData` at `0x1800349a3`
- `bcd!BcdGetElementData` at `0x1800349d1`
- `bcd!BcdOpenObject` at `0x180034947`
- `bcd!BcdOpenObject` at `0x180034947`
- `bcd!BcdOpenStore` at `0x18003482e`
- `bcd!BcdOpenStore` at `0x18003482e`

## string_xrefs

- `0x1800349f5`: `BcdOpenObject failed: 0x%x`
- `0x18003483a`: `open store failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCountOsLoaderEntries(unsigned int *a1)
{
  char *v1; // rbx
  NTSTATUS v3; // edi
  unsigned int v4; // r15d
  int v5; // eax
  const wchar_t *v6; // rdx
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  __int64 i; // r14
  HANDLE v10; // rax
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h] BYREF
  unsigned int dwBytes; // [rsp+40h] [rbp-30h] BYREF
  _WORD dwBytes_4[2]; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v16; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v17[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v18; // [rsp+58h] [rbp-18h] BYREF

  v1 = 0;
  v13 = 0;
  v12 = 0;
  dwBytes = 0;
  v16 = 0;
  dwBytes_4[0] = 0;
  v17[0] = 1;
  v17[1] = 270532611;
  v18 = 0;
  if ( !a1 )
  {
    v3 = 0;
    UnattendLogW(1, L"NULL parameter");
    v4 = 87;
    goto LABEL_32;
  }
  *a1 = 0;
  v4 = 0;
  v5 = BcdOpenStore(0, 0, &v13);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = L"open store failed: 0x%x";
LABEL_5:
    UnattendLogW(1, v6, (unsigned int)v5);
    goto LABEL_32;
  }
  v3 = BcdEnumerateObjects(v13, v17, 0, &dwBytes, &v16);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741789 )
  {
    UnattendLogW(1, L"failed to enumerate objects. error = 0x%x", (unsigned int)v3);
    goto LABEL_32;
  }
  v7 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v1 = (char *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( !v1 )
  {
    UnattendLogW(1, L"HeapAlloc (%u) failed.", dwBytes);
    v4 = 14;
    goto LABEL_32;
  }
  v5 = BcdEnumerateObjects(v13, v17, v1, &dwBytes, &v16);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = L"BcdEnumerateObjects() failed. error = 0x%x";
    goto LABEL_5;
  }
  for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
  {
    if ( v12 )
    {
      BcdCloseObject();
      v12 = 0;
    }
    v18 = *(_OWORD *)&v1[24 * i];
    LogGuid(L"Checking BCD guid: ", &v18);
    v5 = BcdOpenObject(v13, &v18, &v12);
    v3 = v5;
    if ( v5 < 0 )
    {
      v6 = L"BcdOpenObject failed: 0x%x";
      goto LABEL_5;
    }
    dwBytes = 2;
    if ( (int)BcdGetElementData(v12, 637534242, dwBytes_4, &dwBytes) >= 0 && LOBYTE(dwBytes_4[0]) )
    {
      UnattendLogW(0, L"Skipping WinPE object");
    }
    else
    {
      dwBytes = 0;
      if ( (unsigned int)BcdGetElementData(v12, 570425346, 0, &dwBytes) == -1073741789 )
      {
        dwBytes = 2;
        if ( (int)BcdGetElementData(v12, 1174405136, dwBytes_4, &dwBytes) >= 0 && LOBYTE(dwBytes_4[0]) )
          UnattendLogW(0, L"Skipping WinRE object");
        else
          ++*a1;
      }
      else
      {
        UnattendLogW(0, L"Skipping OS entry without system root");
      }
    }
  }
  v3 = 0;
  UnattendLogW(0, L"%lu OS Loader objects found", *a1);
LABEL_32:
  if ( v12 )
  {
    BcdCloseObject();
    v12 = 0;
  }
  if ( v1 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v1);
  }
  if ( v13 )
    BcdCloseStore(v13);
  if ( v3 < 0 )
  {
    UnattendLogW(1, L"winreCountOsLoaderEntries failed: 0x%x", (unsigned int)v3);
    return RtlNtStatusToDosError(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x18003479c  mov     [rsp-28h+arg_8], rbx
0x1800347a1  mov     [rsp-28h+arg_10], rsi
0x1800347a6  push    rbp
0x1800347a7  push    rdi
0x1800347a8  push    r13
0x1800347aa  push    r14
0x1800347ac  push    r15
0x1800347ae  mov     rbp, rsp
0x1800347b1  sub     rsp, 70h
0x1800347b5  mov     rax, cs:__security_cookie
0x1800347bc  xor     rax, rsp
0x1800347bf  mov     [rbp+var_8], rax
0x1800347c3  xor     ebx, ebx
0x1800347c5  mov     [rbp+var_38], 0
0x1800347cd  xor     eax, eax
0x1800347cf  mov     [rbp+var_40], 0
0x1800347d7  mov     dword ptr [rbp+dwBytes], 0
0x1800347de  xorps   xmm0, xmm0
0x1800347e1  mov     [rbp+var_28], 0
0x1800347e8  mov     rsi, rcx
0x1800347eb  mov     word ptr [rbp+dwBytes+4], ax
0x1800347ef  lea     r13d, [rbx+1]
0x1800347f3  mov     [rbp+var_20], r13d
0x1800347f7  mov     [rbp+var_1C], 10200003h
0x1800347fe  movups  [rbp+var_18], xmm0
0x180034802  test    rcx, rcx
0x180034805  jnz     short loc_180034821
0x180034807  xor     edi, edi
0x180034809  lea     rdx, aNullParameter; "NULL parameter"
0x180034810  mov     ecx, r13d
0x180034813  call    UnattendLogW
0x180034818  lea     r15d, [rsi+57h]
0x18003481c  jmp     loc_180034A14
0x180034821  mov     [rcx], eax
0x180034823  lea     r8, [rbp+var_38]
0x180034827  xor     ecx, ecx
0x180034829  xor     edx, edx
0x18003482b  xor     r15d, r15d
0x18003482e  call    cs:__imp_BcdOpenStore
0x180034834  mov     edi, eax
0x180034836  test    eax, eax
0x180034838  jns     short loc_180034851
0x18003483a  lea     rdx, aOpenStoreFaile_1; "open store failed: 0x%x"
0x180034841  mov     r8d, eax
0x180034844  mov     ecx, r13d
0x180034847  call    UnattendLogW
0x18003484c  jmp     loc_180034A14
0x180034851  mov     rcx, [rbp+var_38]
0x180034855  lea     rax, [rbp+var_28]
0x180034859  lea     r9, [rbp+dwBytes]
0x18003485d  mov     [rsp+70h+var_50], rax
0x180034862  xor     r8d, r8d
0x180034865  lea     rdx, [rbp+var_20]
0x180034869  call    cs:__imp_BcdEnumerateObjects
0x18003486f  mov     ecx, 80000000h
0x180034874  mov     edi, eax
0x180034876  add     eax, ecx
0x180034878  test    ecx, eax
0x18003487a  jnz     short loc_180034890
0x18003487c  cmp     edi, 0C0000023h
0x180034882  jz      short loc_180034890
0x180034884  mov     r8d, edi
0x180034887  lea     rdx, aFailedToEnumer; "failed to enumerate objects. error = 0x"...
0x18003488e  jmp     short loc_180034844
0x180034890  mov     ebx, dword ptr [rbp+dwBytes]
0x180034893  call    cs:__imp_GetProcessHeap
0x180034899  mov     r8d, ebx; dwBytes
0x18003489c  mov     edx, 8; dwFlags
0x1800348a1  mov     rcx, rax; hHeap
0x1800348a4  call    cs:__imp_HeapAlloc
0x1800348aa  mov     rbx, rax
0x1800348ad  test    rax, rax
0x1800348b0  jnz     short loc_1800348CE
0x1800348b2  mov     r8d, dword ptr [rbp+dwBytes]
0x1800348b6  lea     rdx, aHeapallocUFail; "HeapAlloc (%u) failed."
0x1800348bd  mov     ecx, r13d
0x1800348c0  call    UnattendLogW
0x1800348c5  lea     r15d, [rbx+0Eh]
0x1800348c9  jmp     loc_180034A14
0x1800348ce  mov     rcx, [rbp+var_38]
0x1800348d2  lea     rax, [rbp+var_28]
0x1800348d6  lea     r9, [rbp+dwBytes]
0x1800348da  mov     [rsp+70h+var_50], rax
0x1800348df  mov     r8, rbx
0x1800348e2  lea     rdx, [rbp+var_20]
0x1800348e6  call    cs:__imp_BcdEnumerateObjects
0x1800348ec  mov     edi, eax
0x1800348ee  test    eax, eax
0x1800348f0  jns     short loc_1800348FE
0x1800348f2  lea     rdx, aBcdenumerateob_0; "BcdEnumerateObjects() failed. error = 0"...
0x1800348f9  jmp     loc_180034841
0x1800348fe  xor     r14d, r14d
0x180034901  cmp     r14d, [rbp+var_28]
0x180034905  jnb     loc_180034A01
0x18003490b  mov     rcx, [rbp+var_40]
0x18003490f  test    rcx, rcx
0x180034912  jz      short loc_18003491E
0x180034914  call    cs:__imp_BcdCloseObject
0x18003491a  mov     [rbp+var_40], r15
0x18003491e  lea     rcx, [r14+r14*2]
0x180034922  movups  xmm0, xmmword ptr [rbx+rcx*8]
0x180034926  lea     rdx, [rbp+var_18]
0x18003492a  lea     rcx, aCheckingBcdGui; "Checking BCD guid: "
0x180034931  movdqu  [rbp+var_18], xmm0
0x180034936  call    LogGuid
0x18003493b  mov     rcx, [rbp+var_38]
0x18003493f  lea     r8, [rbp+var_40]
0x180034943  lea     rdx, [rbp+var_18]
0x180034947  call    cs:__imp_BcdOpenObject
0x18003494d  mov     edi, eax
0x18003494f  test    eax, eax
0x180034951  js      loc_1800349F5
0x180034957  mov     rcx, [rbp+var_40]
0x18003495b  lea     r9, [rbp+dwBytes]
0x18003495f  lea     r8, [rbp+dwBytes+4]
0x180034963  mov     dword ptr [rbp+dwBytes], 2
0x18003496a  mov     edx, 26000022h
0x18003496f  call    cs:__imp_BcdGetElementData
0x180034975  test    eax, eax
0x180034977  js      short loc_18003498F
0x180034979  cmp     byte ptr [rbp+dwBytes+4], r15b
0x18003497d  jz      short loc_18003498F
0x18003497f  lea     rdx, aSkippingWinpeO; "Skipping WinPE object"
0x180034986  xor     ecx, ecx
0x180034988  call    UnattendLogW
0x18003498d  jmp     short loc_1800349ED
0x18003498f  mov     rcx, [rbp+var_40]
0x180034993  lea     r9, [rbp+dwBytes]
0x180034997  xor     r8d, r8d
0x18003499a  mov     dword ptr [rbp+dwBytes], r15d
0x18003499e  mov     edx, 22000002h
0x1800349a3  call    cs:__imp_BcdGetElementData
0x1800349a9  cmp     eax, 0C0000023h
0x1800349ae  jz      short loc_1800349B9
0x1800349b0  lea     rdx, aSkippingOsEntr; "Skipping OS entry without system root"
0x1800349b7  jmp     short loc_180034986
0x1800349b9  mov     rcx, [rbp+var_40]
0x1800349bd  lea     r9, [rbp+dwBytes]
0x1800349c1  lea     r8, [rbp+dwBytes+4]
0x1800349c5  mov     dword ptr [rbp+dwBytes], 2
0x1800349cc  mov     edx, 46000010h
0x1800349d1  call    cs:__imp_BcdGetElementData
0x1800349d7  test    eax, eax
0x1800349d9  js      short loc_1800349EA
0x1800349db  cmp     byte ptr [rbp+dwBytes+4], r15b
0x1800349df  jz      short loc_1800349EA
0x1800349e1  lea     rdx, aSkippingWinreO; "Skipping WinRE object"
0x1800349e8  jmp     short loc_180034986
0x1800349ea  add     [rsi], r13d
0x1800349ed  add     r14d, r13d
0x1800349f0  jmp     loc_180034901
0x1800349f5  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x1800349fc  jmp     loc_180034841
0x180034a01  mov     r8d, [rsi]
0x180034a04  lea     rdx, aLuOsLoaderObje; "%lu OS Loader objects found"
0x180034a0b  xor     edi, edi
0x180034a0d  xor     ecx, ecx
0x180034a0f  call    UnattendLogW
0x180034a14  mov     rcx, [rbp+var_40]
0x180034a18  test    rcx, rcx
0x180034a1b  jz      short loc_180034A2B
0x180034a1d  call    cs:__imp_BcdCloseObject
0x180034a23  mov     [rbp+var_40], 0
0x180034a2b  test    rbx, rbx
0x180034a2e  jz      short loc_180034A44
0x180034a30  call    cs:__imp_GetProcessHeap
0x180034a36  mov     r8, rbx; lpMem
0x180034a39  xor     edx, edx; dwFlags
0x180034a3b  mov     rcx, rax; hHeap
0x180034a3e  call    cs:__imp_HeapFree
0x180034a44  mov     rcx, [rbp+var_38]
0x180034a48  test    rcx, rcx
0x180034a4b  jz      short loc_180034A53
0x180034a4d  call    cs:__imp_BcdCloseStore
0x180034a53  test    edi, edi
0x180034a55  jns     short loc_180034A74
0x180034a57  mov     r8d, edi
0x180034a5a  lea     rdx, aWinrecountoslo; "winreCountOsLoaderEntries failed: 0x%x"
0x180034a61  mov     ecx, r13d
0x180034a64  call    UnattendLogW
0x180034a69  mov     ecx, edi; Status
0x180034a6b  call    cs:__imp_RtlNtStatusToDosError
0x180034a71  mov     r15d, eax
0x180034a74  mov     eax, r15d
0x180034a77  mov     rcx, [rbp+var_8]
0x180034a7b  xor     rcx, rsp; StackCookie
0x180034a7e  call    __security_check_cookie
0x180034a83  lea     r11, [rsp+70h+var_s0]
0x180034a88  mov     rbx, [r11+38h]
0x180034a8c  mov     rsi, [r11+40h]
0x180034a90  mov     rsp, r11
0x180034a93  pop     r15
0x180034a95  pop     r14
0x180034a97  pop     r13
0x180034a99  pop     rdi
0x180034a9a  pop     rbp
0x180034a9b  retn
```
